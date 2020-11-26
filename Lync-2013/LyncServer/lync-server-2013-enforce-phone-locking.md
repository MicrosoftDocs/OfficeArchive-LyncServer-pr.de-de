---
title: 'Lync Server 2013: Erzwingen der Telefon Sperrung'
description: 'Lync Server 2013: Erzwingen der Telefon Sperrung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5afae4fa27edf9378bacc39a29697c9607b25c07
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428650"
---
# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="c7601-103">Erzwingen der Telefon Sperrung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7601-103">Enforce phone locking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="c7601-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="c7601-104">

<span> </span></span></span>

<span data-ttu-id="c7601-105">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c7601-105">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c7601-106">Lync Phone Edition-Geräte können aus Sicherheitsgründen gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="c7601-106">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="c7601-107">Wenn Sie die Telefonsperre erzwingen, sperrt das Gerät, auf dem lync Phone Edition ausgeführt wird, nach einer von Ihnen konfigurierten Zeitspanne.</span><span class="sxs-lookup"><span data-stu-id="c7601-107">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="c7601-108">Wenn ein Telefon gesperrt ist, kann ein Benutzer Anrufe tätigen, kann aber nicht auf Kalender-und Kontaktinformationen, Voicemail oder Anrufprotokolle zugreifen oder die Suchfunktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7601-108">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="c7601-109">Um das Telefon zu entsperren, gibt der Benutzer eine PIN ein.</span><span class="sxs-lookup"><span data-stu-id="c7601-109">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="c7601-110">Wenn Sie die Telefonsperre erzwingen möchten, aktivieren und konfigurieren Sie Sie mithilfe der lync Server Control Panel-oder lync Server PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c7601-110">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="c7601-111">Sie können die Telefonsperre Global oder nur innerhalb der Website erzwingen, für die Sie konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c7601-111">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="c7601-112">So konfigurieren und erzwingen Sie die Telefonsperre</span><span class="sxs-lookup"><span data-stu-id="c7601-112">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="c7601-113">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="c7601-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c7601-114">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c7601-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c7601-115">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c7601-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c7601-116">Klicken Sie auf **Clients**, und klicken Sie dann auf **Gerätekonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c7601-116">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="c7601-117">Doppelklicken Sie auf der Registerkarte **Gerätekonfiguration** in der Liste der Gerätekonfigurationen auf die Konfiguration, für die Sie die Einstellungen für die Telefonsperre ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c7601-117">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="c7601-118">Überprüfen Sie im Dialogfeld **Gerätekonfiguration bearbeiten** , ob das Kontrollkästchen **Gerätesperrung erzwingen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c7601-118">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="c7601-119">Übernehmen Sie in **minimaler PIN-Länge** den Standardwert für die Mindestanzahl von stellen, die die Unlock-Pin enthalten muss, oder geben Sie einen neuen Wert an.</span><span class="sxs-lookup"><span data-stu-id="c7601-119">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="c7601-120">Der Bereich für die PIN-Länge beträgt vier bis fünfzehn Ziffern, der Standardwert ist 6.</span><span class="sxs-lookup"><span data-stu-id="c7601-120">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="c7601-121">Über **nehmen Sie den** Standardwert für die Mindestzeitdauer, bevor das Telefon sich selbst sperrt, oder geben Sie einen neuen Wert an.</span><span class="sxs-lookup"><span data-stu-id="c7601-121">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="c7601-122">Der Bereich für das Timeout beträgt 0 bis 60 Minuten, und der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="c7601-122">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="c7601-123">Geben Sie den Wert im Format HH:MM:SS ein.</span><span class="sxs-lookup"><span data-stu-id="c7601-123">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="c7601-124">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c7601-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c7601-125">Erzwingen der Telefon Sperrung mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c7601-125">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c7601-126">Das Sperren von Telefonen kann mithilfe des Set-CsUCPhoneConfiguration-Cmdlets erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="c7601-126">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="c7601-127">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c7601-127">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c7601-128">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="c7601-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="c7601-129">So aktivieren Sie die Telefon Sperrung</span><span class="sxs-lookup"><span data-stu-id="c7601-129">To enable phone locking</span></span>

  - <span data-ttu-id="c7601-130">Mit dem folgenden Befehl wird die Telefon Sperrung für die Redmond-Website aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c7601-130">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="c7601-131">Um die Telefon Sperrung zu deaktivieren, setzen Sie die EnforcePhoneLock-Eigenschaft auf false ($false).</span><span class="sxs-lookup"><span data-stu-id="c7601-131">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="c7601-132">So aktivieren Sie das Sperren von Telefonen und Ändern des Timeouts für Telefon sperren</span><span class="sxs-lookup"><span data-stu-id="c7601-132">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="c7601-133">Dieser Befehl ermöglicht das Sperren von Telefonen und legt das Timeout für die Telefonsperre auf 30 Minuten fest.</span><span class="sxs-lookup"><span data-stu-id="c7601-133">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="c7601-134">So aktivieren Sie die Telefon Sperrung in der gesamten Organisation</span><span class="sxs-lookup"><span data-stu-id="c7601-134">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="c7601-135">In diesem Beispiel ist die Telefon Sperrung für alle UC-Telefon Konfigurationseinstellungen aktiviert, die in der Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7601-135">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="c7601-136">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) ".</span><span class="sxs-lookup"><span data-stu-id="c7601-136">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7601-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7601-137">See Also</span></span>


[<span data-ttu-id="c7601-138">Verwalten der lync Server 2013-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c7601-138">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="c7601-139">Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7601-139">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

<span data-ttu-id="c7601-140"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="c7601-140"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

