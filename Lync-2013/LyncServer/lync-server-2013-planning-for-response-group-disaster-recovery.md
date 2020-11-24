---
title: 'Lync Server 2013: Planen der Notfallwiederherstellung für Reaktionsgruppen'
description: 'Lync Server 2013: Planen der Disaster Recovery einer Reaktionsgruppe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5294ddf7dbd42d95c5eb17acd6be6a5abc7a5917
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49395331"
---
# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="97740-103">Planen der Notfallwiederherstellung für Reaktionsgruppen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97740-103">Planning for response group disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="97740-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="97740-104">

<span> </span></span></span>

<span data-ttu-id="97740-105">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="97740-105">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="97740-106">In diesem Abschnitt werden einige Möglichkeiten beschrieben, wie Sie Reaktionsgruppen für die Disaster Recovery vorbereiten und eine Übersicht über den Disaster Recovery-Prozess erhalten.</span><span class="sxs-lookup"><span data-stu-id="97740-106">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="97740-107">Vorbereiten der Disaster Recovery einer Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="97740-107">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="97740-108">Beachten Sie bei der Vorbereitung und Durchführung von Disaster Recovery-Verfahren Folgendes:</span><span class="sxs-lookup"><span data-stu-id="97740-108">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97740-109">In einer Koexistenz-Umgebung werden nur die lync Server 2013-Reaktionsgruppen für die in diesem Dokument beschriebenen Disaster Recovery-Verfahren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="97740-109">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="97740-110">Planen Sie die Disaster Recovery, wenn Sie Ihre Kapazitätsplanung durchführen.</span><span class="sxs-lookup"><span data-stu-id="97740-110">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="97740-111">Für die Disaster Recovery-Kapazität sollten alle Pools in einem gekoppelten Pool in der Lage sein, die Arbeitslasten aller Reaktionsgruppen in beiden Pools zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="97740-111">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="97740-112">Details zur Kapazitätsplanung der Reaktionsgruppe finden Sie unter [Kapazitätsplanung für die Reaktionsgruppe in lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="97740-112">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="97740-113">Nehmen Sie regelmäßige Sicherungskopien aller Reaktionsgruppen Konfigurationen in allen Front-End-Pools auf, in denen Sie die Antwortgruppen Anwendung mithilfe des in diesem Dokument beschriebenen Exportvorgangs bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="97740-113">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="97740-114">Ausführliche Informationen finden Sie unter [Disaster Recovery-Verfahren für die Reaktionsgruppe in lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="97740-114">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="97740-115">Bewahren Sie die Sicherungskopien an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="97740-115">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="97740-116">Bewahren Sie eine separate Sicherungskopie aller Original-Audiodateien auf, die Sie für die reaktionsgruppenanwendung verwendet haben, einschließlich Aufnahmen und Musik-in-halten-Dateien.</span><span class="sxs-lookup"><span data-stu-id="97740-116">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="97740-117">Bewahren Sie die Sicherungsdateien an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="97740-117">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="97740-118">Bei der Disaster-Wiederherstellung in lync Server 2013 müssen alle Einstellungen für die Reaktionsgruppe eindeutige Namen für Ihre Bereitstellung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="97740-118">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="97740-119">Diese Anforderung gilt für Workflows, Warteschlangen, Agentengruppen, Feiertagssätze und Geschäftsstunden.</span><span class="sxs-lookup"><span data-stu-id="97740-119">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="97740-120">Überprüfen Sie, ob diese Anforderung erfüllt ist, wenn die primären und die Sicherungs Pools noch aktiv sind, und bevor Sie eine Failover-Prozedur initiieren müssen.</span><span class="sxs-lookup"><span data-stu-id="97740-120">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="97740-121">Wenn beim Importieren von Antwortgruppen Daten in den Sicherungspool Namenskonflikte auftreten, schlägt der Import fehl.</span><span class="sxs-lookup"><span data-stu-id="97740-121">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="97740-122">Um das Import-und FailoverVerfahren abzuschließen, müssen Sie die Namenskonflikte lösen, indem Sie das Reaktionsgruppen Objekt im Sicherungspool umbenennen oder das Cmdlet " **Import-CsRgsConfiguration** " mit dem Parameter "– ResolveNameConflicts" verwenden, um den Konflikt automatisch zu beheben, indem Sie eine eindeutige identifizierende Nummer an das Antwortgruppen Objekt anfügen.</span><span class="sxs-lookup"><span data-stu-id="97740-122">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="97740-123">Im Allgemeinen empfehlen wir, dass Sie tägliche Sicherungen durchführen, aber wenn Sie über eine große Anzahl von Änderungen verfügen, möchten Sie möglicherweise häufigere Sicherungen planen.</span><span class="sxs-lookup"><span data-stu-id="97740-123">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="97740-124">Die Menge der Informationen, die Sie bei einem Notfall verlieren können, hängt von der Häufigkeit Ihrer Sicherungen sowie von Häufigkeit und Umfang der Änderungen ab.</span><span class="sxs-lookup"><span data-stu-id="97740-124">The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="97740-125">Es ist möglich, Antwortgruppen in einen Backup-Pool zu importieren, bevor ein Notfall-oder Failover-Vorgang stattfindet.</span><span class="sxs-lookup"><span data-stu-id="97740-125">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="97740-126">Wenn Sie Reaktionsgruppen im Voraus importieren, verringert sich die Ausfallzeit, da der lync Server Response Group-Dienst im Sicherungspool wiederhergestellt werden kann, sobald Anrufe an den Sicherungspool weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="97740-126">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="97740-127">Die reaktionsgruppenanwendung kann keine Agents erreichen, die in einem inaktiven Pool verwaltet werden, bis das Failover abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="97740-127">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="97740-128">Während dieser Zeit verarbeitet die reaktionsgruppenanwendung Anrufe, als ob diese Agents nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="97740-128">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="97740-129">Disaster Recovery-Prozess der Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="97740-129">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="97740-130">Im Fall eines Notfalls können Sie Reaktionsgruppen mithilfe einer der folgenden Wiederherstellungsmethoden wiederherstellen:</span><span class="sxs-lookup"><span data-stu-id="97740-130">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="97740-131">Führen Sie einen Failover zu einem Sicherungspool durch, und führen Sie dann einen Fehler zurück zum ursprünglichen Pool aus.</span><span class="sxs-lookup"><span data-stu-id="97740-131">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="97740-132">Führen Sie einen Failover zu einem Sicherungspool durch, erstellen Sie einen neuen Pool mit einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN), und importieren Sie dann die Antwortgruppen in den neuen Pool.</span><span class="sxs-lookup"><span data-stu-id="97740-132">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="97740-133">Während der Failover-Phase der Disaster Recovery befinden sich die Reaktionsgruppen in mehreren Pools: im primären Pool (der nicht verfügbar ist) und im Sicherungspool.</span><span class="sxs-lookup"><span data-stu-id="97740-133">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="97740-134">Die Antwortgruppen in beiden Pools haben denselben Namen und denselben Besitzer (den primären Pool), haben aber unterschiedliche übergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="97740-134">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="97740-135">Wenn Sie eine Wiederherstellung durch Erstellen eines neuen Pools mit einem anderen FQDN durchführen, müssen Sie den neuen Pool als Besitzer der Antwortgruppen zuweisen, wenn Sie ihn importieren.</span><span class="sxs-lookup"><span data-stu-id="97740-135">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="97740-136">Der Besitz von Reaktionsgruppen verbleibt mit dem ursprünglichen Pool, es sei denn, dass Sie den Besitz mithilfe des-OverwriteOwner-Parameters mit dem **Import-CsRgsConfiguration-** Cmdlet explizit neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="97740-136">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97740-137">Sie müssen auch den – OverwriteOwner-Parameter verwenden, wenn Sie den Pool während der Wiederherstellung neu erstellt haben (also die Antwortgruppen Datenbank leer ist), unabhängig davon, ob Sie den gleichen FQDN verwenden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="97740-137">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="97740-138">Sie müssen den-OverwriteOwner-Parameter nicht verwenden, wenn Sie den Pool nicht neu erstellt haben, es jedoch zulässig ist, diesen Parameter immer dann zu verwenden, wenn Sie Antwortgruppen wieder in den primären Pool importieren.</span><span class="sxs-lookup"><span data-stu-id="97740-138">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="97740-139">Pro Pool können Sie nur einen Satz von Reaktionsgruppen-Konfigurationseinstellungen auf Anwendungsebene definieren.</span><span class="sxs-lookup"><span data-stu-id="97740-139">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="97740-140">Zu diesen Einstellungen gehören die standardmäßige Musik-in-halten-Konfiguration, die standardmäßige Musik-in-halten-Audiodatei, die Kulanzzeit für den Agenten-Rückruf und die Kontextkonfiguration des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="97740-140">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="97740-141">Führen Sie das Cmdlet " **Get-CsRgsConfiguration** " aus, um diese Konfigurationseinstellungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="97740-141">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="97740-142">Details zum Cmdlet **Get-CsRgsConfiguration** finden Sie unter [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="97740-142">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="97740-143">Sie können diese Einstellungen auf Anwendungsebene von einem Pool zu einem anderen übertragen, indem Sie das Cmdlet " **Import-CsRgsConfiguration** " mit dem Parameter "– ReplaceExistingSettings" verwenden, aber dadurch werden die Einstellungen im Ziel Pool überschrieben.</span><span class="sxs-lookup"><span data-stu-id="97740-143">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="97740-144">Diese Einschränkung beim Übertragen von Einstellungen in einen anderen Pool gilt nur für die Einstellungen auf Anwendungsebene und die standardmäßige Musik-in-Halt-Audiodatei.</span><span class="sxs-lookup"><span data-stu-id="97740-144">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file.</span></span> <span data-ttu-id="97740-145">Sie gilt nicht für Agentengruppen, Warteschlangen, Workflows, Geschäftszeiten und Feiertagssätze.</span><span class="sxs-lookup"><span data-stu-id="97740-145">It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="97740-146">Wenn Sie die Einstellungen auf Anwendungsebene im Sicherungspool während eines Notfalls nicht ersetzen möchten und der primäre Pool nicht wiederhergestellt werden kann, gehen die Einstellungen auf Anwendungsebene des primären Pools verloren.</span><span class="sxs-lookup"><span data-stu-id="97740-146">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost.</span></span> <span data-ttu-id="97740-147">Wenn Sie einen neuen Pool erstellen müssen, um den primären Pool während der Wiederherstellung zu ersetzen, entweder mit demselben FQDN oder mit einem anderen FQDN, können Sie die ursprünglichen Einstellungen auf Anwendungsebene nicht wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="97740-147">If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings.</span></span> <span data-ttu-id="97740-148">In diesem Fall müssen Sie den neuen Pool mit diesen Einstellungen konfigurieren und die Musik-in-Halt-Audiodatei aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="97740-148">In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="97740-149">Wenn Sie sich entscheiden, das Cmdlet " **Import-CsRgsConfiguration** " zu verwenden, um während eines Notfalls Einstellungen auf Anwendungsebene aus dem primären Pool in den Sicherungspool zu übertragen, können Sie die Einstellungen während der Wiederherstellung auf die gleiche Weise aus dem Sicherungspool in den neuen Pool übertragen, wie Sie Sie vom primären Pool an den Sicherungspool übertragen haben.</span><span class="sxs-lookup"><span data-stu-id="97740-149">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="97740-150">Die folgende Tabelle enthält eine Übersicht über die Schritte, die beim erneuten Herstellen von Reaktionsgruppen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="97740-150">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="97740-151">Ausführliche Informationen zum Ausführen dieser Schritte finden Sie unter [Disaster Recovery-Verfahren für die Reaktionsgruppe in lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="97740-151">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="97740-152">Notfall Wiederherstellungsschritte für die Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="97740-152">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97740-153">Phase</span><span class="sxs-lookup"><span data-stu-id="97740-153">Phase</span></span></th>
<th><span data-ttu-id="97740-154">Schritte</span><span class="sxs-lookup"><span data-stu-id="97740-154">Steps</span></span></th>
<th><span data-ttu-id="97740-155">Erforderliche Gruppen und Rollen</span><span class="sxs-lookup"><span data-stu-id="97740-155">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97740-156">Vor einem Ausfall</span><span class="sxs-lookup"><span data-stu-id="97740-156">Before outage</span></span></p></td>
<td><p><span data-ttu-id="97740-157">Führen Sie das Cmdlet <strong>Export-CsRgsConfiguration</strong> routinemäßig aus, um Sicherungen aller Reaktionsgruppen Konfigurationen in allen Front-End-Pools zu erstellen, in denen die Antwortgruppen Anwendung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="97740-157">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="97740-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="97740-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="97740-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="97740-159">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97740-160">Bei einem Ausfall</span><span class="sxs-lookup"><span data-stu-id="97740-160">During outage</span></span></p></td>
<td><p><span data-ttu-id="97740-161">Führen Sie das Cmdlet " <strong>Import-CsRgsConfiguration</strong> " aus, um die gesicherte Konfiguration des lync Server-Reaktionsgruppendiensts aus dem primären Pool in den Sicherungspool zu importieren.</span><span class="sxs-lookup"><span data-stu-id="97740-161">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="97740-162">Verwenden Sie den Parameter – ReplaceExistingSettings, wenn Sie die Einstellungen für die Reaktionsgruppe auf Anwendungsebene im Sicherungspool durch die Einstellungen des primären Pools ersetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="97740-162">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="97740-163">Wenn Sie die Einstellungen auf Anwendungsebene nicht vom primären Pool in den Sicherungspool übertragen und der primäre Pool nicht wiederhergestellt werden kann, gehen die Einstellungen des primären Pools verloren.</span><span class="sxs-lookup"><span data-stu-id="97740-163">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="97740-164">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="97740-164">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="97740-165">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="97740-165">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97740-166">Nach dem Import</span><span class="sxs-lookup"><span data-stu-id="97740-166">After importing</span></span></p></td>
<td><p><span data-ttu-id="97740-167">Führen Sie die Cmdlets für die Reaktionsgruppe mit dem Parameter – ShowAll (zum Anzeigen aller Antwortgruppen) oder des Parameters "– Owner" aus, um zu überprüfen, ob alle Reaktionsgruppen Konfigurationen in den Sicherungspool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="97740-167">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="97740-168">Wenn Sie weder den-ShowAll-Parameter noch den – owner-Parameter verwenden, werden die Reaktionsgruppen, die Sie in den Sicherungspool importiert haben, nicht in den Ergebnissen aufgelistet, die von den Cmdlets zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="97740-168">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="97740-169">Führen Sie die folgenden Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="97740-169">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="97740-170"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="97740-170"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="97740-171"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="97740-171"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="97740-172"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="97740-172"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="97740-173"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="97740-173"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="97740-174"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="97740-174"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97740-175">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="97740-175">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="97740-176">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="97740-176">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97740-177">Nach dem Failover</span><span class="sxs-lookup"><span data-stu-id="97740-177">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="97740-178">Setzen Sie einen Testanruf an eine Reaktionsgruppe, die in den Sicherungspool importiert wurde, und überprüfen Sie, ob der Anruf richtig gehandhabt wird.</span><span class="sxs-lookup"><span data-stu-id="97740-178">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="97740-179">Alle formellen Agents müssen sich bei ihren formalen Gruppen im Sicherungspool erneut anmelden.</span><span class="sxs-lookup"><span data-stu-id="97740-179">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="97740-180">Verwalten von Konfigurationsänderungen:</span><span class="sxs-lookup"><span data-stu-id="97740-180">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="97740-181">Reaktionsgruppen im Sicherungspool, ob Sie in den Backup-Pool importiert oder im Besitz des Sicherungs Pools sind, können während des Ausfalls wie gewohnt geändert werden.</span><span class="sxs-lookup"><span data-stu-id="97740-181">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="97740-182">Sie müssen die lync Server-Verwaltungsshell zum Verwalten der Reaktionsgruppen verwenden, die Sie in den Sicherungspool importiert haben.</span><span class="sxs-lookup"><span data-stu-id="97740-182">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="97740-183">Sie können die lync Server-Systemsteuerung nicht verwenden, um diese Reaktionsgruppen zu verwalten, während Sie sich im Sicherungspool befinden.</span><span class="sxs-lookup"><span data-stu-id="97740-183">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="97740-184">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="97740-184">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97740-185">Nach der Wiederherstellung vor dem Failback</span><span class="sxs-lookup"><span data-stu-id="97740-185">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="97740-186">Führen Sie das Cmdlet <strong>Export-CsRgsConfiguration</strong> aus, indem Sie den-source-Parameter als Backup-Pool und den Parameter-Owner als primären Pool angeben, um die Reaktionsgruppen zu exportieren, die im Besitz des primären Pools aus dem Sicherungspool sind.</span><span class="sxs-lookup"><span data-stu-id="97740-186">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="97740-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="97740-187">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="97740-188">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="97740-188">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97740-189">Nach dem Failback</span><span class="sxs-lookup"><span data-stu-id="97740-189">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="97740-190">Führen Sie das Cmdlet " <strong>Import-CsRgsConfiguration</strong> " aus, um die Reaktionsgruppen wieder in den primären Pool zu importieren.</span><span class="sxs-lookup"><span data-stu-id="97740-190">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="97740-191">Wenn der primäre Pool nicht wiederhergestellt werden kann und Sie einen neuen Pool zum Ersetzen bereitstellen, verwenden Sie den Parameter – ReplaceExistingSettings, um die Einstellungen auf Anwendungsebene aus dem Sicherungspool in den neuen Pool zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="97740-191">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool.</span></span> <span data-ttu-id="97740-192">Wenn Sie die Einstellungen nicht aus dem Sicherungspool übertragen, verwendet der neue Pool die Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="97740-192">If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="97740-193">Führen Sie die folgenden Cmdlets mit dem-ShowAll-Parameter (zum Anzeigen aller Antwortgruppen) oder des – Owner-Parameters (zum Anzeigen nur importierter Antwortgruppen) aus, um zu überprüfen, ob alle Reaktionsgruppen Konfigurationen erfolgreich wieder in den primären Pool importiert wurden:</span><span class="sxs-lookup"><span data-stu-id="97740-193">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="97740-194"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="97740-194"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="97740-195"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="97740-195"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="97740-196"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="97740-196"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="97740-197"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="97740-197"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="97740-198"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="97740-198"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="97740-199">Setzen Sie einen Testanruf an eine Reaktionsgruppe, die zurück in den primären Pool importiert wurde, und überprüfen Sie, ob der Anruf richtig gehandhabt wird.</span><span class="sxs-lookup"><span data-stu-id="97740-199">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="97740-200">Führen Sie optional das Cmdlet <strong>Export-CsRgsConfiguration</strong> im Sicherungspool mit dem Parameter – RemoveExportedConfiguration aus, um die Reaktionsgruppen zu entfernen, die im Besitz des primären Pools des Sicherungs Pools sind.</span><span class="sxs-lookup"><span data-stu-id="97740-200">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97740-201">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="97740-201">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="97740-202">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="97740-202">CsResponseGroupAdministrator</span></span></p></td><span data-ttu-id="97740-203">
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="97740-203">
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

