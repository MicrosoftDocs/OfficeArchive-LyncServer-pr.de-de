---
title: 'Lync Server 2013: Bereitstellen von lync Web App'
description: 'Lync Server 2013: Bereitstellen von lync Web App.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce6fef02781afbd5bc5f315ce24bfb3bdb16df1c
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49429902"
---
# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="e7da1-103">Bereitstellen von lync Web App in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7da1-103">Deploying Lync Web App in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="e7da1-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="e7da1-104">

<span> </span></span></span>

<span data-ttu-id="e7da1-105">_**Letztes Änderungsdatum des Themas:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="e7da1-105">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="e7da1-106">Lync Web App ist ein Internetinformationsdienste (IIS)-WebClient, der mit lync Server 2013 installiert und standardmäßig aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e7da1-106">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="e7da1-107">Es sind keine weiteren Schritte erforderlich, um lync Web App auf dem Server zu aktivieren oder den WebClient für Benutzer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e7da1-107">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="e7da1-108">Wenn ein Benutzer auf eine Besprechungs-URL klickt, aber der lync 2013-Client nicht installiert ist, wird dem Benutzer die Option zur Teilnahme an der Besprechung mit der neuesten Version von lync Web App angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7da1-108">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="e7da1-109">Die sprach-, Video-und Freigabefunktionen in lync Web App erfordern ein Microsoft ActiveX-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e7da1-109">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="e7da1-110">Sie können entweder das ActiveX-Steuerelement im Voraus installieren oder es Benutzern ermöglichen, es zu installieren, wenn Sie dazu aufgefordert werden, was geschieht, wenn Sie lync Web App zum ersten Mal verwenden oder wenn Sie zum ersten Mal auf ein Feature zugreifen, das das ActiveX-Steuerelement erfordert.</span><span class="sxs-lookup"><span data-stu-id="e7da1-110">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="e7da1-111">In lync Server 2013-Edgeserver-Bereitstellungen ist für den lync Web App-Clientzugriff ein HTTPS-Reverseproxy im Umkreisnetzwerk erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e7da1-111">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="e7da1-112">Außerdem müssen Sie einfache URLs veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e7da1-112">You must also publish simple URLs.</span></span> <span data-ttu-id="e7da1-113">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse-Proxyservern für lync Server 2013</A> und <A href="lync-server-2013-planning-for-simple-urls.md">Planen einfacher URLs in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e7da1-113">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="e7da1-114">Aktivieren der mehrstufigen Authentifizierung für lync Web App</span><span class="sxs-lookup"><span data-stu-id="e7da1-114">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="e7da1-115">Die lync Server 2013-Version von lync Web App unterstützt die mehrstufige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="e7da1-115">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="e7da1-116">Zusätzlich zu Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden wie Smartcards oder Pins anfordern, um Benutzer zu authentifizieren, die von externen Netzwerken beitreten, wenn Sie sich bei lync-Besprechungen anmelden.</span><span class="sxs-lookup"><span data-stu-id="e7da1-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="e7da1-117">Sie können die mehrstufige Authentifizierung aktivieren, indem Sie den Active Directory Federation Service (AD FS)-Verbundserver bereitstellen und die passive Authentifizierung in lync Server 2013 aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e7da1-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="e7da1-118">Nach der Konfiguration von AD FS werden externe Benutzer, die versuchen, an lync-Besprechungen teilzunehmen, mit einer AD FS-Website mit mehrstufiger Authentifizierung angezeigt, die die Herausforderung Benutzername und Kennwort zusammen mit allen weiteren von Ihnen konfigurierten Authentifizierungsmethoden enthält.</span><span class="sxs-lookup"><span data-stu-id="e7da1-118">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="e7da1-119">Im Folgenden finden Sie wichtige Erwägungen, wenn Sie planen, Active Directory-Verbunddienste für die mehrstufige Authentifizierung zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="e7da1-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="e7da1-p105">Mehrstufige ADFS-Authentifizierung funktioniert, wenn der Besprechungsteilnehmer und der Organisator sich beide in der gleichen Organisation befinden oder beide aus einer AD FS-Partnerverbundorganisation stammen. Die mehrstufige ADFS-Authentifizierung funktioniert nicht für Lync-Partnerverbundbenutzer, da sie von der Webinfrastruktur von Lync Server aktuell nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="e7da1-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="e7da1-122">Wenn Sie Hardwarelastenausgleichs verwenden, aktivieren Sie die Beibehaltung von Cookies auf den Lastenausgleichsgeräten, damit alle Anforderungen vom lync Web App-Client vom gleichen Front-End-Server verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e7da1-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="e7da1-123">Wenn Sie eine vertrauende Vertrauensstellung zwischen lync Server und AD FS-Servern einrichten, weisen Sie eine Lebensdauer von Token zu, die lang genug ist, um die maximale Länge ihrer lync-Besprechungen zu überspannen.</span><span class="sxs-lookup"><span data-stu-id="e7da1-123">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="e7da1-124">Normalerweise genügt eine Tokengültigkeitsdauer von 240 Minuten.</span><span class="sxs-lookup"><span data-stu-id="e7da1-124">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="e7da1-125">Diese Konfiguration gilt nicht für mobile Lync-Clients.</span><span class="sxs-lookup"><span data-stu-id="e7da1-125">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="e7da1-126">**So konfigurieren Sie die mehrstufige Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="e7da1-126">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="e7da1-127">Installieren Sie eine AD FS-Verbundserverrolle.</span><span class="sxs-lookup"><span data-stu-id="e7da1-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="e7da1-128">Ausführliche Informationen finden Sie im Bereitstellungshandbuch für Active Directory-Verbunddienste 2,0 unter <https://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="e7da1-128">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="e7da1-129">Erstellen Sie Zertifikate für AD FS.</span><span class="sxs-lookup"><span data-stu-id="e7da1-129">Create certificates for AD FS.</span></span> <span data-ttu-id="e7da1-130">Weitere Informationen finden Sie im Abschnitt "Verbundserver Zertifikate" im Abschnitt Planen und Bereitstellen von AD FS für die Verwendung mit dem Thema für einmaliges Anmelden unter [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) .</span><span class="sxs-lookup"><span data-stu-id="e7da1-130">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="e7da1-131">Führen Sie über die Windows PowerShell-Befehlszeilenschnittstelle den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="e7da1-131">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="e7da1-132">Richten Sie durch Ausführen des folgenden Befehls eine Partnerschaft ein:</span><span class="sxs-lookup"><span data-stu-id="e7da1-132">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="e7da1-133">Legen Sie die folgenden vertrauenswürdigen Parteienregeln fest:</span><span class="sxs-lookup"><span data-stu-id="e7da1-133">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a><span data-ttu-id="e7da1-134">BranchCache-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e7da1-134">BranchCache Configuration</span></span>

<span data-ttu-id="e7da1-135">Das BranchCache-Feature in Windows 7 und Windows Server 2008 R2 kann die Web-Komponenten von lync Web App stören.</span><span class="sxs-lookup"><span data-stu-id="e7da1-135">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="e7da1-136">Um Probleme mit lync Web App-Benutzern zu vermeiden, stellen Sie sicher, dass BranchCache nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e7da1-136">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="e7da1-137">Ausführliche Informationen zum Deaktivieren von BranchCache finden Sie im BranchCache-Bereitstellungshandbuch, das im Microsoft Download Center unter [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) und im HTML-Format in der technischen Bibliothek für Windows Server 2008 R2 unter auf Word-Format verfügbar ist [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789) .</span><span class="sxs-lookup"><span data-stu-id="e7da1-137">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="e7da1-138">Überprüfen der lync Web App-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="e7da1-138">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="e7da1-139">Mit dem Cmdlet „Test-CsUcwaConference“ können Sie überprüfen, ob zwei Testbenutzer über die Unified Communications-Web-API (UCWA) an einer Konferenz teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="e7da1-139">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="e7da1-140">Details zu diesem Cmdlet finden Sie unter [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e7da1-140">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="e7da1-141">Problembehandlung der Plug-in-Installation unter Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="e7da1-141">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="e7da1-142">Wenn die Installation des Plug-Ins auf einem Computer mit Windows Server 2008 R2 fehlschlägt, müssen Sie möglicherweise die Internet Explorer-Sicherheitseinstellung oder die DisableMSI-Registrierungsschlüsseleinstellung ändern.</span><span class="sxs-lookup"><span data-stu-id="e7da1-142">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="e7da1-143">**So ändern Sie die Sicherheitseinstellung in Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="e7da1-143">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="e7da1-144">Öffnen Sie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e7da1-144">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="e7da1-145">Klicken Sie auf **Extras**, auf **Internetoptionen** und anschließend auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="e7da1-145">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="e7da1-146">Scrollen Sie nach unten zum Abschnitt **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="e7da1-146">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="e7da1-147">Deaktivieren Sie **Verschlüsselte Seiten nicht auf dem Datenträger speichern**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7da1-147">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="e7da1-148">Wenn diese Option ausgewählt ist, wird auch beim Versuch, eine Anlage aus lync Web App herunterzuladen, ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e7da1-148">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="e7da1-149">Nehmen Sie an der Besprechung erneut teil.</span><span class="sxs-lookup"><span data-stu-id="e7da1-149">Rejoin the meeting.</span></span> <span data-ttu-id="e7da1-150">Das Plug-In sollte ohne Fehler Elemente herunterladen.</span><span class="sxs-lookup"><span data-stu-id="e7da1-150">The plug-in should download without errors.</span></span>

<span data-ttu-id="e7da1-151">**So ändern Sie die Registrierungseinstellung "DisableMSI"**</span><span class="sxs-lookup"><span data-stu-id="e7da1-151">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="e7da1-152">Klicken Sie auf  **Start** und dann auf  **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e7da1-152">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="e7da1-153">Geben Sie **regedit** ein, um auf den Registrierungs-Editor zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="e7da1-153">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="e7da1-154">Navigieren Sie zu den HKEY \_ \_ \\ -Software Richtlinien für lokale Computer \\ \\ Microsoft \\ Windows \\ Installer.</span><span class="sxs-lookup"><span data-stu-id="e7da1-154">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="e7da1-155">Bearbeiten oder fügen Sie den Registrierungsschlüssel DisableMSI vom Typ reg DWORD hinzu, \_ und setzen Sie ihn auf 0.</span><span class="sxs-lookup"><span data-stu-id="e7da1-155">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="e7da1-156">Nehmen Sie an der Besprechung erneut teil.</span><span class="sxs-lookup"><span data-stu-id="e7da1-156">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7da1-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7da1-157">See Also</span></span>


[<span data-ttu-id="e7da1-158">Konfigurieren der Seite für den Besprechungsbeitritt in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7da1-158">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="e7da1-159">Lync Web App-unterstützte Plattformen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7da1-159">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

<span data-ttu-id="e7da1-160"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="e7da1-160"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

