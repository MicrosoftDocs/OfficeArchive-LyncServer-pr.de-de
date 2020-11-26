---
title: 'Lync Server 2013: Konfigurieren von lync Server in einer standortübergreifenden Umgebung'
description: 'Lync Server 2013: Konfigurieren von lync Server in einer standortübergreifenden Umgebung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1ec978cd8e0e34c01c1d5cabb5bba42debd16fd
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433015"
---
# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="865f1-103">Konfigurieren von Microsoft lync Server 2013 in einer standortübergreifenden Umgebung</span><span class="sxs-lookup"><span data-stu-id="865f1-103">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="865f1-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="865f1-104">

<span> </span></span></span>

<span data-ttu-id="865f1-105">_**Letztes Änderungsdatum des Themas:** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="865f1-105">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="865f1-106">In einer standortübergreifenden Konfiguration sind einige Ihrer Benutzer in einer lokalen Installation von Microsoft lync Server 2013, während andere Benutzer in der Microsoft 365-oder Office 365-Version von lync Server verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="865f1-106">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Microsoft 365 or Office 365 version of Lync Server.</span></span> <span data-ttu-id="865f1-107">Um die Server-zu-Server-Authentifizierung in einer standortübergreifenden Umgebung zu konfigurieren, müssen Sie zuerst Ihre lokale Installation von lync Server 2013 so konfigurieren, dass Sie dem Microsoft 365-autorisierungsserver vertraut.</span><span class="sxs-lookup"><span data-stu-id="865f1-107">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Microsoft 365 Authorization server.</span></span> <span data-ttu-id="865f1-108">Der erste Schritt in diesem Prozess kann durch Ausführen des folgenden Skripts der lync Server-Verwaltungsshell ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="865f1-108">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

    $TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
    
    $sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue
            
       if ($sts -eq $null)
          {
             New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
          }
       else
          {
             if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
                {
                   Remove-CsOAuthServer microsoft.sts
                   New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
                }
            }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
                 New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
              }
           else
              {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
              }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="865f1-p102">Beachten Sie, dass sich der Bereichsname für einen Mandanten normalerweise vom Namen der Organisation unterscheidet. Der Bereichsname entspricht stattdessen häufig der Mandanten-ID. Aus diesem Grund dient die erste Zeile des Skripts dazu, den Wert der TenantId-Eigenschaft für den angegebenen Mandanten zurückzugeben (in diesem Fall „fabrikam.com“) und den entsprechenden Namen anschließend der Variablen „$TenantId“ zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="865f1-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="865f1-111">Nachdem das Skript abgeschlossen ist, müssen Sie eine Vertrauensstellung zwischen lync Server 2013 und dem autorisierungsserver sowie eine zweite Vertrauensstellung zwischen Exchange 2013 und dem autorisierungsserver konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="865f1-111">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="865f1-112">Das ist nur mithilfe der Microsoft Online Services-Cmdlets möglich.</span><span class="sxs-lookup"><span data-stu-id="865f1-112">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="865f1-113">Wenn Sie die Microsoft Online Services-Cmdlets noch nicht installiert haben, müssen Sie zwei Schritte ausführen, bevor Sie fortfahren können.</span><span class="sxs-lookup"><span data-stu-id="865f1-113">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="865f1-114">Laden Sie die 64-Bit-Version des Microsoft Online Services-Anmeldeassistenten herunter, und installieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="865f1-114">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="865f1-115">Nachdem die Installation abgeschlossen ist, laden Sie die 64-Bit-Version des Microsoft Online Services-Moduls für Windows PowerShell herunter, und installieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="865f1-115">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="865f1-116">Detaillierte Informationen zum Installieren und Verwenden des Microsoft Online Services-Moduls finden Sie auf der Microsoft 365-oder Office 365-Website.</span><span class="sxs-lookup"><span data-stu-id="865f1-116">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 or Office 365 web site.</span></span> <span data-ttu-id="865f1-117">In diesen Anweisungen erfahren Sie auch, wie Sie das einmalige Anmelden, den Verbund und die Synchronisierung zwischen Microsoft 365 oder Office 36 und Active Directory konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="865f1-117">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 36 and Active Directory.</span></span><BR><span data-ttu-id="865f1-118">Wenn Sie diese Cmdlets nicht installiert haben, schlägt Ihr Skript fehl, weil das Get-CsTenant-Cmdlet nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="865f1-118">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="865f1-119">Nachdem Sie Microsoft 365 konfiguriert haben und nachdem Sie Microsoft 365-oder Office 365-Dienst Prinzipale für lync Server 2013 und Exchange 2013 erstellt haben, müssen Sie Ihre Anmeldeinformationen bei diesen Dienst Prinzipalen registrieren.</span><span class="sxs-lookup"><span data-stu-id="865f1-119">After you have configured Microsoft 365, and after you have created Microsoft 365 or Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="865f1-120">Zu diesem Zweck müssen Sie zunächst ein Base64-kodiertes X.509-Zertifikat anfordern, das als CER-Datei gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="865f1-120">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="865f1-121">Dieses Zertifikat wird dann auf die Microsoft 365-oder Office 365-Dienst Prinzipale angewendet.</span><span class="sxs-lookup"><span data-stu-id="865f1-121">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="865f1-122">Wenn Sie das X. 509-Zertifikat erhalten haben, starten Sie das Microsoft Online Services-Modul (Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Online Services**, und klicken Sie dann auf **Microsoft Online Services-Modul für Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="865f1-122">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="865f1-123">Nachdem das Modul Dienste geöffnet wurde, geben Sie Folgendes ein, um das Microsoft Online Windows PowerShell-Modul zu importieren, das die Cmdlets enthält, die zum Verwalten von Dienst Prinzipalen verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="865f1-123">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="865f1-124">Wenn das Modul importiert wurde, geben Sie den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE, um eine Verbindung mit Microsoft 365 herzustellen:</span><span class="sxs-lookup"><span data-stu-id="865f1-124">When the module has been imported, type the following command and then press ENTER in order to connect to Microsoft 365:</span></span>

    Connect-MsolService

<span data-ttu-id="865f1-125">Nach Drücken der EINGABETASTE wird ein Dialogfeld zur Eingabe Ihrer Anmeldeinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="865f1-125">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="865f1-126">Geben Sie im Dialogfeld Ihren Microsoft 365-oder Office 365-Benutzernamen und das Kennwort ein, und klicken Sie dann auf OK.</span><span class="sxs-lookup"><span data-stu-id="865f1-126">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="865f1-127">Sobald Sie mit Microsoft 365 verbunden sind, können Sie den folgenden Befehl ausführen, um Informationen zu ihren Dienst Prinzipalen zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="865f1-127">As soon as you are connected to Microsoft 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="865f1-128">Sie sollten ähnliche Informationen wie die folgenden für alle Ihre Dienstprinzipale erhalten:</span><span class="sxs-lookup"><span data-stu-id="865f1-128">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="865f1-129">Der nächste Schritt besteht darin, das X.509-Zertifikat zu importieren, zu codieren und zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="865f1-129">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="865f1-130">Verwenden Sie zum Importieren und Codieren des Zertifikats die folgenden Windows PowerShell-Befehle, wobei Sie sicherstellen möchten, dass der vollständige Dateipfad zu Ihrem. CER-Datei beim Aufrufen der Import-Methode:</span><span class="sxs-lookup"><span data-stu-id="865f1-130">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="865f1-131">Nachdem das Zertifikat importiert und codiert wurde, können Sie das Zertifikat Ihren Microsoft 365-Dienst Prinzipalen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="865f1-131">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 service principals.</span></span> <span data-ttu-id="865f1-132">Verwenden Sie dazu zunächst die Get-MsolServicePrincipal, um den Wert der AppPrincipalId-Eigenschaft sowohl für den lync-Server als auch für die Microsoft Exchange-Dienst Prinzipale abzurufen. der Wert der AppPrincipalId-Eigenschaft wird verwendet, um den Dienstprinzipal zu identifizieren, dem das Zertifikat zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="865f1-132">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="865f1-133">Mit dem AppPrincipalId-Eigenschaftswert für lync Server 2013 verwenden Sie den folgenden Befehl, um das Zertifikat der Microsoft 365-Version von lync Server zuzuweisen (die Eigenschaften StartDate und EndDate sollten dem Gültigkeitszeitraum für das Zertifikat entsprechen):</span><span class="sxs-lookup"><span data-stu-id="865f1-133">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Microsoft 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="865f1-134">Sie sollten diesen Befehl dann wiederholen, indem Sie dieses Mal den AppPrincipalId-Eigenschaftswert für Exchange 2013 verwenden.</span><span class="sxs-lookup"><span data-stu-id="865f1-134">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="865f1-135">Falls Sie das Zertifikat zu einem späteren Zeitpunkt löschen müssen, rufen Sie dazu zunächst die KeyID für das Zertifikat ab:</span><span class="sxs-lookup"><span data-stu-id="865f1-135">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="865f1-136">Der entsprechende Befehl gibt in etwa folgende Daten zurück:</span><span class="sxs-lookup"><span data-stu-id="865f1-136">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="865f1-137">Sie können das Zertifikat mit einem ähnlichen Befehl wie diesem löschen:</span><span class="sxs-lookup"><span data-stu-id="865f1-137">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="865f1-138">Neben dem Zuweisen eines Zertifikats müssen Sie auch den Microsoft 365-Dienstprinzipal für Exchange Online konfigurieren, indem Sie den Server Prinzipalnamen für Ihre lokale Version von lync Server 2013 hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="865f1-138">In addition to assigning a certificate you must also configure the Microsoft 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="865f1-139">Dies kann durch Ausführen der folgenden vier Zeilen in einer Microsoft Online Services PowerShell-Sitzung erfolgen:</span><span class="sxs-lookup"><span data-stu-id="865f1-139">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

<span data-ttu-id="865f1-140"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="865f1-140"></div>

<span> </span>

</div>

</div>

</span></span></div>

