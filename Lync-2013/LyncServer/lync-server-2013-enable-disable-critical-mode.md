---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des kritischen Modus zum Blockieren oder Zulassen von Chat-und Webkonferenz Sitzungen, wenn die Archivierung fehlschlägt'
description: 'Lync Server 2013: Aktivieren oder Deaktivieren des kritischen Modus zum Blockieren oder Zulassen von Chat-und Webkonferenz Sitzungen, wenn die Archivierung fehlschlägt.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling critical mode to block or allow IM and web conferencing sessions if Archiving fails
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48185927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac318a04d8ed3b952e45bf5b8718a78432391d29
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437588"
---
# <a name="enabling-or-disabling-critical-mode-in-lync-server-2013-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails"></a><span data-ttu-id="a547b-103">Aktivieren oder Deaktivieren des kritischen Modus in lync Server 2013 zum Blockieren oder Zulassen von Chat-und Webkonferenz Sitzungen, wenn die Archivierung fehlschlägt</span><span class="sxs-lookup"><span data-stu-id="a547b-103">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="a547b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="a547b-104">

<span> </span></span></span>

<span data-ttu-id="a547b-105">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a547b-105">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a547b-106">In der lync Server 2013-Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um den kritischen Modus zu aktivieren und zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a547b-106">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable critical mode.</span></span> <span data-ttu-id="a547b-107">Dies umfasst die folgenden Archivierungs Konfigurationen:</span><span class="sxs-lookup"><span data-stu-id="a547b-107">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="a547b-108">Eine globale Konfiguration, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a547b-108">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="a547b-109">Optionale Konfigurationen auf Websiteebene und auf Poolebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Websites oder Pools implementiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a547b-109">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="a547b-110">Sie haben zunächst Archivierungs Konfigurationen eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen.</span><span class="sxs-lookup"><span data-stu-id="a547b-110">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="a547b-111">Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a547b-111">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a547b-112">Um die Archivierung verwenden zu können, müssen Sie Archivierungsrichtlinien so konfigurieren, dass Sie angeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für Benutzer, die in lync Server 2013 verwaltet werden, aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a547b-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="a547b-113">Standardmäßig ist die Archivierung für die interne oder externe Kommunikation nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a547b-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="a547b-114">Bevor Sie die Archivierung in einer beliebigen Richtlinie aktivieren, sollten Sie die geeigneten Archivierungs Konfigurationen für Ihre Bereitstellung und optional für bestimmte Websites und Pools angeben, wie in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a547b-114">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="a547b-115">Details zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a547b-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="a547b-116">Wenn Sie nach der Bereitstellung der Archivierung entscheiden, dass Sie die Exchange Server-Integration verwenden möchten, um Archivierungsdaten und Dateien auf Exchange 2013-Servern zu speichern, und alle Ihre Benutzer auf Ihren Exchange 2013-Servern verwaltet werden, sollten Sie die SQL Server-Datenbankkonfiguration aus Ihrer Topologie entfernen.</span><span class="sxs-lookup"><span data-stu-id="a547b-116">If you decide after you deploy Archiving that you want to use Exchange Server integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="a547b-117">Dazu müssen Sie den Topology Builder verwenden.</span><span class="sxs-lookup"><span data-stu-id="a547b-117">You must use Topology Builder to do this.</span></span> <span data-ttu-id="a547b-118">Ausführliche Informationen finden Sie unter Ändern der Optionen für die <A href="lync-server-2013-changing-archiving-database-options.md">Archivierungsdatenbank in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a547b-118">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-blocking-of-im-and-web-conferencing-sessions-if-archiving-fails"></a><span data-ttu-id="a547b-119">So aktivieren oder deaktivieren Sie die Blockierung von Chat-und Webkonferenz Sitzungen, wenn die Archivierung fehlschlägt</span><span class="sxs-lookup"><span data-stu-id="a547b-119">To enable or disable blocking of IM and web conferencing sessions if archiving fails</span></span>

1.  <span data-ttu-id="a547b-120">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a547b-120">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a547b-121">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a547b-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a547b-122">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a547b-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a547b-123">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="a547b-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="a547b-124">Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der betreffenden Konfiguration auf globaler, Standort- oder Poolebene. Klicken Sie auf **Bearbeiten** und auf **Details anzeigen** und führen Sie dann eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a547b-124">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>

5.  <span data-ttu-id="a547b-125">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um das Archivierungsverhalten bei einem Fehler festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a547b-125">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>

6.  <span data-ttu-id="a547b-126">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a547b-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-and-disabling-critical-mode-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a547b-127">Aktivieren und Deaktivieren des kritischen Modus mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a547b-127">Enabling and Disabling Critical Mode by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a547b-128">Sie können den kritischen Modus mithilfe des Cmdlets " **festlegen-CsArchivingConfiguration** " aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a547b-128">You can enable or disable critical mode using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="a547b-129">Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="a547b-129">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a547b-130">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="a547b-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-critical-mode"></a><span data-ttu-id="a547b-131">So aktivieren Sie den kritischen Modus</span><span class="sxs-lookup"><span data-stu-id="a547b-131">To enable critical mode</span></span>

  - <span data-ttu-id="a547b-132">Um den kritischen Modus zu aktivieren, legen Sie den Wert der BlockOnArchiveFailure-Eigenschaft auf true ($true) fest.</span><span class="sxs-lookup"><span data-stu-id="a547b-132">To enable critical mode, set the value of the BlockOnArchiveFailure property to True ($True).</span></span> <span data-ttu-id="a547b-133">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a547b-133">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

</div>

<div>

## <a name="to-disable-critical-mode"></a><span data-ttu-id="a547b-134">So deaktivieren Sie den kritischen Modus</span><span class="sxs-lookup"><span data-stu-id="a547b-134">To disable critical mode</span></span>

  - <span data-ttu-id="a547b-135">Wenn Sie den kritischen Modus deaktivieren möchten, legen Sie den Wert der BlockOnArchiveFailure-Eigenschaft auf false ($false) fest.</span><span class="sxs-lookup"><span data-stu-id="a547b-135">To disable critical mode, set the value of the BlockOnArchiveFailure property to False ($False).</span></span> <span data-ttu-id="a547b-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a547b-136">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

</div>

<span data-ttu-id="a547b-137">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) ".</span><span class="sxs-lookup"><span data-stu-id="a547b-137">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a547b-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a547b-138">See Also</span></span>


[<span data-ttu-id="a547b-139">Ändern der Optionen für die Archivierungsdatenbank in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a547b-139">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)  


[<span data-ttu-id="a547b-140">Funktionsweise der Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a547b-140">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="a547b-141">Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, ihre Websites und Pools</span><span class="sxs-lookup"><span data-stu-id="a547b-141">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

<span data-ttu-id="a547b-142"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="a547b-142"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

