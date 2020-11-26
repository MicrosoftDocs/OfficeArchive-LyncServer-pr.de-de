---
title: 'Lync Server 2013: Ändern der Einstellungen für die Qualität der Benutzerfreundlichkeit'
description: 'Lync Server 2013: Ändern der Einstellungen für die Qualität der Benutzerfreundlichkeit.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e1372a41adaf8107e2e1ed02042cbcfe3223705
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425472"
---
# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="8f54e-103">Ändern der Einstellungen für die Qualität der Benutzerfreundlichkeit in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f54e-103">Modify Quality of Experience settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="8f54e-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="8f54e-104">

<span> </span></span></span>

<span data-ttu-id="8f54e-105">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8f54e-105">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8f54e-p101">In der Standardeinstellung werden QoE-Daten (Quality of Experience, Erlebnisqualität) nach 60 Tagen gelöscht. Sie können die Einstellungen auf der Seite **QoE-Daten** verwenden, um die Daten für einen längeren oder kürzeren Zeitraum zu speichern. Wenn Sie QoE deaktivieren, werden auch Daten gelöscht, die bei aktivierter QoE-Datenerfassung aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="8f54e-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f54e-p102">Sie sollten die Aufzeichnung von Kommunikationsdatensätzen (KDS) und QoE-Daten so konfigurieren, dass Daten für die gleiche Anzahl von Tagen gespeichert werden. Die Berichte zu den aufgezeichneten Kommunikationsdatensätzen (KDS), verfügbar auf der Webseite für Überwachungsberichte, umfassen KDS- und QoE-Informationen zu jedem Anruf. Wenn die Zeit bis zum Löschen für KDS und QoE abweicht, umfassen einige Anrufe möglicherweise nur KDS-Daten, während andere ausschließlich QoE-Daten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8f54e-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="8f54e-112">Das nachfolgende Verfahren beschreibt, wie Sie die Löscheinstellungen für QoE-Daten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8f54e-112">The following procedure describes how to configure purge settings for QoE data.</span></span>

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a><span data-ttu-id="8f54e-113">So legen Sie die Beibehaltung von QoE-Daten mithilfe der lync Server-Systemsteuerung fest</span><span class="sxs-lookup"><span data-stu-id="8f54e-113">To specify retention of QoE data by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8f54e-114">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="8f54e-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8f54e-115">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8f54e-115">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8f54e-116">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8f54e-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8f54e-117">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8f54e-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8f54e-118">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.</span><span class="sxs-lookup"><span data-stu-id="8f54e-118">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="8f54e-119">Klicken Sie auf der Seite **QoE-Daten** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="8f54e-119">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="8f54e-120">Wählen Sie die Option **Löschen für QoE aktivieren** aus, um die Löschung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8f54e-120">To turn on purging, select **Enable Purging of QoE**.</span></span>

6.  <span data-ttu-id="8f54e-121">Wählen Sie unter **Maximale Speicherdauer für die QuE-Aufzeichnung (Tage)** die maximale Anzahl von Tagen aus, für die QoE-Daten gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8f54e-121">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="8f54e-122">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8f54e-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8f54e-123">Angeben der QoE-Aufbewahrung mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="8f54e-123">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8f54e-124">Sie können QoE-Aufbewahrungseinstellungen mithilfe von Windows PowerShell und dem Cmdlet " **Satz-CsQoEConfiguration** " erstellen.</span><span class="sxs-lookup"><span data-stu-id="8f54e-124">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="8f54e-125">Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="8f54e-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8f54e-126">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="8f54e-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="8f54e-127">So geben Sie die QoE-Aufbewahrung für einen speziellen Standort an</span><span class="sxs-lookup"><span data-stu-id="8f54e-127">To specify QoE retention for a specific location</span></span>

  - <span data-ttu-id="8f54e-128">Dieser Befehl ermöglicht das Löschen von QoE-Daten für den Standort Redmond. Zudem wird damit für die QoE-Daten eine Aufbewahrungsdauer von 20 Tagen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8f54e-128">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="8f54e-129">So geben Sie die QoE-Aufbewahrung für mehrere Standorte an</span><span class="sxs-lookup"><span data-stu-id="8f54e-129">To specify QoE retention for multiple locations</span></span>

  - <span data-ttu-id="8f54e-130">Mit diesem Befehl wird die Beibehaltung von QoE-Daten für alle in einer Organisation verwendeten QoE-Konfigurationseinstellungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8f54e-130">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

<span data-ttu-id="8f54e-131">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) ".</span><span class="sxs-lookup"><span data-stu-id="8f54e-131">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8f54e-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f54e-132">See Also</span></span>


[<span data-ttu-id="8f54e-133">Bereitstellen der Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f54e-133">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

<span data-ttu-id="8f54e-134"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="8f54e-134"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

