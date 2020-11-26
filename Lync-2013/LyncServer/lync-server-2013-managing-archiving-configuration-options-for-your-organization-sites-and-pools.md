---
title: 'Lync Server 2013: Verwalten von Archivierungs Konfigurationsoptionen für Ihre Organisation, ihre Websites und Pools'
description: 'Lync Server 2013: Verwalten von Archivierungs Konfigurationsoptionen für Ihre Organisation, Websites und Pools.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41eca448fcb9863f117bcb7e52e3290270fefa47
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425983"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="8d88c-103">Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, ihre Websites und Pools</span><span class="sxs-lookup"><span data-stu-id="8d88c-103">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="8d88c-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="8d88c-104">

<span> </span></span></span>

<span data-ttu-id="8d88c-105">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8d88c-105">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8d88c-106">In der lync Server 2013-Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um anzugeben, wie die Archivierung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8d88c-106">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="8d88c-107">Dies umfasst die folgenden Archivierungs Konfigurationen:</span><span class="sxs-lookup"><span data-stu-id="8d88c-107">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="8d88c-108">Eine globale Konfiguration, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="8d88c-108">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="8d88c-109">Optionale Konfigurationen auf Websiteebene und auf Poolebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Websites oder Pools implementiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8d88c-109">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="8d88c-110">Sie haben zunächst Archivierungs Konfigurationen eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen.</span><span class="sxs-lookup"><span data-stu-id="8d88c-110">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="8d88c-111">In der lync Server 2013-Systemsteuerung können Sie auf **der Seite Archivierungs** -und Überwachungsgruppe auf der Seite Archivierungs **-und Überwachungs** Einstellungen Konfigurationen auf globaler Ebene, Websiteebene und Poolebene verwalten.</span><span class="sxs-lookup"><span data-stu-id="8d88c-111">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="8d88c-112">Ausführliche Informationen dazu, wie Archivierungs Konfigurationen implementiert werden, einschließlich der Optionen, die Sie angeben können, und die Hierarchie der Archivierungs Konfigurationen finden Sie unter [wie funktioniert die Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8d88c-112">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d88c-113">Um die Archivierung verwenden zu können, müssen Sie Archivierungsrichtlinien so konfigurieren, dass Sie angeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für alle Benutzer, die in lync Server 2013 verwaltet werden, aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8d88c-113">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="8d88c-114">Standardmäßig ist die Archivierung für die interne oder externe Kommunikation nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8d88c-114">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="8d88c-115">Wenn Sie die Microsoft Exchange-Integration verwenden, müssen Sie Exchange 2013 aktivieren und konfigurieren, um die Archivierung für alle Benutzer zu unterstützen, die sich in Exchange 2013 befinden und deren Postfächer in In-Place Haltebereich gesetzt wurden.</span><span class="sxs-lookup"><span data-stu-id="8d88c-115">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="8d88c-116">Vor der Aktivierung der Archivierung sollten Sie die geeigneten Archivierungs Konfigurationen für Ihre Bereitstellung und optional für bestimmte Websites und Pools angeben, wie in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8d88c-116">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="8d88c-117">Details zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8d88c-117">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="8d88c-118">**So zeigen Sie Informationen zur Archivierungskonfiguration mithilfe von Windows PowerShell-Cmdlets an**</span><span class="sxs-lookup"><span data-stu-id="8d88c-118">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="8d88c-119">Sie können die Informationen zur Archivierungskonfiguration mithilfe von Windows PowerShell und dem Cmdlet **Get-CsArchivingConfiguration** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8d88c-119">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="8d88c-120">Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="8d88c-120">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8d88c-121">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="8d88c-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="8d88c-122">Verwenden Sie in der lync Server-Verwaltungsshell den folgenden Befehl, um Informationen zu allen Archivierungs Konfigurationseinstellungen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="8d88c-122">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="8d88c-123">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8d88c-123">In This Section</span></span>

  - [<span data-ttu-id="8d88c-124">Erstellen einer Archivierungskonfiguration in lync Server 2013 zum Verwalten der Archivierung für bestimmte Websites oder Pools</span><span class="sxs-lookup"><span data-stu-id="8d88c-124">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="8d88c-125">Aktivieren oder Deaktivieren der Archivierung von Chat-oder Konferenzsitzungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d88c-125">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="8d88c-126">Aktivieren oder Deaktivieren des Bereinigens archivierter Daten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d88c-126">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="8d88c-127">Aktivieren oder Deaktivieren des kritischen Modus in lync Server 2013 zum Blockieren oder Zulassen von Chat-und Webkonferenz Sitzungen, wenn die Archivierung fehlschlägt</span><span class="sxs-lookup"><span data-stu-id="8d88c-127">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enable-disable-critical-mode.md)

  - [<span data-ttu-id="8d88c-128">Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d88c-128">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="8d88c-129">Aktivieren oder Deaktivieren der Integration von lync Server 2013 mit Exchange-Speicher</span><span class="sxs-lookup"><span data-stu-id="8d88c-129">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="8d88c-130">Löschen einer Archivierungskonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d88c-130">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8d88c-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d88c-131">See Also</span></span>


[<span data-ttu-id="8d88c-132">Verwalten der Lync Server 2013-Archivierung</span><span class="sxs-lookup"><span data-stu-id="8d88c-132">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

<span data-ttu-id="8d88c-133"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="8d88c-133"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

