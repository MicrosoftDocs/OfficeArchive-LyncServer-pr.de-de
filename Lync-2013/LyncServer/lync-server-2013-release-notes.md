---
title: 'Lync Server 2013: Anmerkungen zu dieser Version'
description: Lync Server 2013-Versionshinweise.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33fabb0912d7ea3defd91014df732368eced909e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49436552"
---
# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="06ecd-103">Anmerkungen zu dieser Version für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06ecd-103">Release notes for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="06ecd-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="06ecd-104">

<span> </span></span></span>

<span data-ttu-id="06ecd-105">_**Letztes Änderungsdatum des Themas:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="06ecd-105">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="06ecd-106">Willkommen bei den Versionshinweisen zu lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06ecd-106">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="06ecd-107">Informationen zu bekannten Problemen mit lync Server 2013 finden Sie in dieser Datei.</span><span class="sxs-lookup"><span data-stu-id="06ecd-107">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="06ecd-108">Informationen zu diesem Dokument</span><span class="sxs-lookup"><span data-stu-id="06ecd-108">About this document</span></span>

<span data-ttu-id="06ecd-109">Dieses Dokument enthält wichtige Informationen, die Sie vor der Bereitstellung und Verwendung von lync Server 2013 wissen sollten.</span><span class="sxs-lookup"><span data-stu-id="06ecd-109">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="06ecd-110">Details zu lync Server 2013 finden Sie in der Dokumentation zu [Microsoft lync Server 2013](microsoft-lync-server-2013.md) .</span><span class="sxs-lookup"><span data-stu-id="06ecd-110">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="06ecd-111">Dieses Dokument enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="06ecd-111">This document contains the following sections:</span></span>

  - <span data-ttu-id="06ecd-112">Lync 2013-Client</span><span class="sxs-lookup"><span data-stu-id="06ecd-112">Lync 2013 client</span></span>

  - <span data-ttu-id="06ecd-113">Lync Server</span><span class="sxs-lookup"><span data-stu-id="06ecd-113">Lync Server</span></span>

  - <span data-ttu-id="06ecd-114">Installation</span><span class="sxs-lookup"><span data-stu-id="06ecd-114">Installation</span></span>

  - <span data-ttu-id="06ecd-115">Mobilität</span><span class="sxs-lookup"><span data-stu-id="06ecd-115">Mobility</span></span>

  - <span data-ttu-id="06ecd-116">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="06ecd-116">Conferencing</span></span>

  - <span data-ttu-id="06ecd-117">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="06ecd-117">Enterprise Voice</span></span>

  - <span data-ttu-id="06ecd-118">Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="06ecd-118">Presence</span></span>

  - <span data-ttu-id="06ecd-119">Reaktionsgruppenanwendung und Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="06ecd-119">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="06ecd-120">Lync Server-Systemsteuerung, Topologie-Generator und Planungstool</span><span class="sxs-lookup"><span data-stu-id="06ecd-120">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="06ecd-121">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="06ecd-121">Localization</span></span>

  - <span data-ttu-id="06ecd-122">Copyright</span><span class="sxs-lookup"><span data-stu-id="06ecd-122">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="06ecd-123">Lync 2013-Client</span><span class="sxs-lookup"><span data-stu-id="06ecd-123">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="06ecd-124">Das übertragen einer Datei in einer Chatnachricht schlägt fehl, wenn die Datei in einer anderen Anwendung geöffnet ist</span><span class="sxs-lookup"><span data-stu-id="06ecd-124">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="06ecd-125">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-125">**Issue:**</span></span>

<span data-ttu-id="06ecd-126">Wenn Sie versuchen, eine Datei (beispielsweise ein Word-Dokument) zu übertragen, indem Sie Sie in eine Chatnachricht an einen anderen lync-Benutzer einbinden, scheint die Übertragung erfolgreich zu sein, kann die Datei jedoch tatsächlich nicht übertragen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-126">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="06ecd-127">Ein Symbol für den Dateityp wird im lync-Client angezeigt, aber die Datei kann nicht vom vorgesehenen Empfänger geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-127">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="06ecd-128">Es wird keine Fehlermeldung angezeigt, in der Sie darüber informiert werden, dass die Übertragung nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="06ecd-128">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="06ecd-129">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-129">**Workaround:**</span></span>

<span data-ttu-id="06ecd-130">Um dieses Problem zu umgehen, schließen Sie die geöffnete Datei oder Anwendung, die Sie geöffnet hat, bevor Sie versuchen, die Datei in einer Sofortnachricht zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-130">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="06ecd-131">Lync Server</span><span class="sxs-lookup"><span data-stu-id="06ecd-131">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="06ecd-132">Wenn die Datenreplikation des lync Server-Speicher Diensts fehlschlägt, müssen Administratoren Leistungsindikatoren für veraltete Speicherdienst-Warteschlangenelemente überprüfen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-132">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="06ecd-133">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-133">**Issue:**</span></span>

<span data-ttu-id="06ecd-134">Der lync Server-Speicherdienst verwendet Windows-Fabric für die Replikation.</span><span class="sxs-lookup"><span data-stu-id="06ecd-134">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="06ecd-135">Wenn Daten auf einem primären Front-End-Server gelöscht werden, der Löschvorgang auf einem sekundären Front-End-Server jedoch fehlschlägt, beispielsweise wenn ein unerwartetes Herunterfahren oder ein Fehler auf dem Front-End-Server vorliegt, können Daten zurückgelassen und "verwaist" werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-135">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="06ecd-136">Die verwaisten Daten können dazu führen, dass die Leistung beeinträchtigt und der Festplattenspeicherplatz abgenutzt wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-136">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="06ecd-137">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-137">**Workaround:**</span></span>

<span data-ttu-id="06ecd-138">Um dieses Problem zu umgehen, \_ \_ \_ \_ \_ \_ \_ \_ sollten Administratoren den Leistungsindikator auf dem Front-End-Server unter **ls: Lyss-Storage-Service-API** mit dem Namen **Lyss-aktuelle Anzahl von veralteten Warteschlangenelementen** überprüfen, wenn der Speicherplatz für die Ereignisse Lyss (ID = 32058) und Lyss-DB-Speicherplatz kritisch (ID = 32059) im Ereignisprotokoll generiert wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-138">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="06ecd-139">Wenn dieser Leistungsindikator einen höheren Wert aufweist, beispielsweise mehr als 50000, sollte der Administrator das CleanuUpStorageServiceData.exe-Tool im lync Server 2013 Resource Kit ausführen, wodurch alle verwaisten Daten aus dem Pool gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-139">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="06ecd-140">Details zum Tool finden Sie in der Dokumentation zum lync Server 2013 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="06ecd-140">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="06ecd-141">Wenn die IP-Adresskonfiguration für einen Server oder Pool geändert wird, müssen die lync Server-Dienste neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-141">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="06ecd-142">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-142">**Issue:**</span></span>

<span data-ttu-id="06ecd-143">Wenn die IP-Adressenkonfiguration für eine lync Server 2013-Bereitstellung geändert wird, wie beispielsweise das Wechseln von IPv4 zu Dual Stack oder von Dual Stack zu IPv6, greifen nicht alle Server Komponenten die Konfigurationsänderung an, bis die Dienste neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-143">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="06ecd-144">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-144">**Workaround:**</span></span>

<span data-ttu-id="06ecd-145">Um dieses Problem zu umgehen, starten Sie lync Server Services neu, nachdem Sie die IP-Adressenkonfiguration für die Bereitstellung geändert haben.</span><span class="sxs-lookup"><span data-stu-id="06ecd-145">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="06ecd-146">Führen Sie dazu die folgenden Cmdlets in der lync Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="06ecd-146">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="06ecd-147">Das Cmdlet "synthetische Einwahlkonferenzen" steht im lync Server 2013-Management Pack nicht mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="06ecd-147">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="06ecd-148">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-148">**Issue:**</span></span>

<span data-ttu-id="06ecd-149">Das Cmdlet **Test-CsDialInConferencing** für Einwahlkonferenz-synthetische Transaktionen steht im lync Server 2013-Management Pack nicht mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="06ecd-149">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="06ecd-150">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-150">**Workaround:**</span></span>

<span data-ttu-id="06ecd-151">Die Verwendung des Cmdlets **Test-CsDialInConferencing** für Einwahlkonferenzen in synthetischen Transaktionen wird nur intern für ein Unternehmen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-151">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="06ecd-152">Administratoren können das Cmdlet weiterhin zur Problembehandlung in der lync Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-152">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="06ecd-153">Falls erforderlich, kann ein Unternehmen auch ein privates Management Pack entwickeln, um das Cmdlet intern auszuführen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-153">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="06ecd-154">Der zentralisierte Protokollierungsdienst wird angehalten, wenn der Netzwerkdatenverkehr gestört wird, wenn Protokolldateien auf die Netzwerkfreigabe kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-154">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="06ecd-155">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-155">**Issue:**</span></span>

<span data-ttu-id="06ecd-156">Wenn der zentralisierte Protokollierungsdienst für die Verwendung eines Netzwerkpfads konfiguriert ist (der Wert des CacheFileNetworkFolder-Parameters des Cmdlets **Get-CsClsConfiguration** ist ein gültiger UNC-Pfad), werden zwischengespeicherte Protokolldateien in die Netzwerkfreigabe kopiert.</span><span class="sxs-lookup"><span data-stu-id="06ecd-156">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="06ecd-157">Wenn im Netzwerkdatenverkehr eine Unterbrechung auftritt, während die Dateien kopiert werden, wird eine Ausnahme ausgelöst, die dazu führt, dass der zentralisierte Protokollierungsdienst beendet wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-157">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="06ecd-158">Der Dienst ist so konfiguriert, dass er bis zu dreimal automatisch neu gestartet wird, sodass der Dienst nach den ersten drei Ausnahmen wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-158">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="06ecd-159">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-159">**Workaround:**</span></span>

<span data-ttu-id="06ecd-160">Für dieses Problem gibt es keine Problemumgehung.</span><span class="sxs-lookup"><span data-stu-id="06ecd-160">There is no workaround for this issue.</span></span> <span data-ttu-id="06ecd-161">Um das Problem zu identifizieren, überwachen Sie das Ereignisprotokoll für die Ereignis-ID 7031 aus dem "Dienststeuerungs-Manager", der protokolliert, wenn der Dienst "lync Server-zentralisierter Protokollierungsdienst-Agent" unerwartet beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="06ecd-161">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="06ecd-162">Wenn dies mehr als dreimal passiert, starten Sie den Dienst manuell mit dem Cmdlet **Start-CsWindowService** neu.</span><span class="sxs-lookup"><span data-stu-id="06ecd-162">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="06ecd-163">Speicherdienst-Warteschlangenelemente müssen manuell importiert werden</span><span class="sxs-lookup"><span data-stu-id="06ecd-163">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="06ecd-164">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-164">**Issue:**</span></span>

<span data-ttu-id="06ecd-165">Lync Server 2013 speichert Daten zu Konferenzen und Instant Messaging, wie archivierte Nachrichten und CDR (Call Detail Recording), in einer Datenbank auf jedem Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="06ecd-165">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="06ecd-166">Die Daten werden während der Verarbeitung in der Datenbank gespeichert, bevor Sie an das vorgesehene Ziel übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-166">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="06ecd-167">Um die Leistung zu verbessern, exportiert lync Server 2013 in regelmäßigen Abständen die Warteschlangenelemente aus der lokalen Datenbank, die für einen längeren Zeitraum nicht verarbeitet werden, und speichert Sie im Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="06ecd-167">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="06ecd-168">Wenn der Dateispeicher nicht verfügbar ist, werden die Elemente auf jedem Front-End-Server gespeichert.</span><span class="sxs-lookup"><span data-stu-id="06ecd-168">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="06ecd-169">Derselbe Vorgang tritt auf, um Datenverluste während des Pool-Failovers zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="06ecd-169">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="06ecd-170">Während des Exportvorgangs zeichnet der lync Server-Speicherdienst alle Phasen im Ereignisprotokoll mit Ereignis-IDs von 32075 (vollständiger Flush-Vorgang wird gestartet), 32076 (vollständiger Flush ist abgeschlossen), 32082 (Maintenance Level Flush wird gestartet), 32083 (Maintenance Level Flush ist abgeschlossen), 32089 (Flush erfolgte aufgrund des Befüllens der Datenbank).</span><span class="sxs-lookup"><span data-stu-id="06ecd-170">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="06ecd-171">Diese Daten werden nicht automatisch zurück in das System importiert, um verarbeitet und an das endgültige Ziel (SQL Server oder Exchange Server) übermittelt zu werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-171">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="06ecd-172">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-172">**Workaround:**</span></span>

<span data-ttu-id="06ecd-173">Um die Daten in das System zu importieren, müssen Administratoren das ImportStorageServiceData-Tool im lync Server Resource Kit verwenden, das die Daten wieder in das System einfügt, damit Sie verarbeitet und an das endgültige Ziel übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-173">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="06ecd-174">Bei der Suche von Adressbuch-Webabfragen tritt ein Fehler auf, wenn der Standardwert für UseNormalizationRules in false geändert wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-174">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="06ecd-175">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-175">**Issue:**</span></span>

<span data-ttu-id="06ecd-176">Wenn der Standardwert für UseNormalizationRules in false geändert wird, schlägt die Suche nach Adressbuch-Webabfragen fehl.</span><span class="sxs-lookup"><span data-stu-id="06ecd-176">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="06ecd-177">Nachdem der Standardwert geändert wurde, können lync-Client Benutzer keine lync-Adressbuch-Webabfrage verwenden, um nach Benutzern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-177">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="06ecd-178">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-178">**Workaround:**</span></span>

<span data-ttu-id="06ecd-179">Wenn der Standardwert für UseNormalizationRules auf "false" festgelegt ist, damit Benutzer Telefonnummern verwenden können, die in Active Directory-Domänendiensten ohne lync Server 2013 angewendet werden, um Normalisierungsregeln anzuwenden, gehen Sie wie folgt vor, um dieses Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="06ecd-179">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="06ecd-180">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="06ecd-180">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="06ecd-181">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="06ecd-181">Do one of the following:</span></span>
    
      - <span data-ttu-id="06ecd-182">Wenn Ihre Bereitstellung nur lync Server 2013-Server umfasst, führen Sie das folgende Cmdlet auf globaler Ebene aus, um die Werte für UseNormalizationRules und IgnoreGenericRules auf "true" zu ändern:</span><span class="sxs-lookup"><span data-stu-id="06ecd-182">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="06ecd-183">Wenn Ihre Bereitstellung eine Kombination aus lync Server 2013 und lync Server 2010 oder Office Communications Server 2007 R2 umfasst, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem lync Server 2013-Pool in der Topologie zu:</span><span class="sxs-lookup"><span data-stu-id="06ecd-183">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="06ecd-184">Warten Sie, bis die CMS-Replikation in allen Pools durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-184">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="06ecd-185">Ändern Sie die Regeldatei für die Telefon Normalisierungsregeln für Ihre Bereitstellung, um den Inhalt zu löschen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-185">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="06ecd-186">Die Datei befindet sich auf der Dateifreigabe der einzelnen lync Server 2013-Pools.</span><span class="sxs-lookup"><span data-stu-id="06ecd-186">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="06ecd-187">Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit dem Namen "Firmen \_ Telefonnummer \_ \_ Normalisierung \_Rules.txt."</span><span class="sxs-lookup"><span data-stu-id="06ecd-187">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="06ecd-188">Warten Sie einige Minuten, bis alle Front-End-Pools die neuen Dateien gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="06ecd-188">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="06ecd-189">Führen Sie das folgende Cmdlet für jeden lync Server 2013-Pool in Ihrer Bereitstellung aus.</span><span class="sxs-lookup"><span data-stu-id="06ecd-189">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="06ecd-190">Das Adressbuch Server-Fehlerereignis 21054 wird einmal täglich für jeden lync 2013-Pool generiert.</span><span class="sxs-lookup"><span data-stu-id="06ecd-190">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="06ecd-191">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-191">**Issue:**</span></span>

<span data-ttu-id="06ecd-192">Der lync Server 2013-Adressbuchserver generiert das Fehlerereignis 21054 einmal täglich, wenn die tägliche Wartung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-192">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="06ecd-193">Der Fehler wird auch jedes Mal generiert, wenn ein Administrator das **Update-csAddressBook-** Cmdlet ausführt, auch wenn das Update erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="06ecd-193">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="06ecd-194">Dieses Fehlerereignis kann jedoch bedenkenlos ignoriert werden, wenn das Update erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="06ecd-194">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="06ecd-195">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-195">**Workaround:**</span></span>

<span data-ttu-id="06ecd-196">Wenn dieses Fehlerereignis auftritt, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="06ecd-196">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="06ecd-197">Wenn das Cmdlet meldet, dass keine nicht indizierten oder verlassenen Objekte vorhanden sind, kann das Fehlerereignis 21054 problemlos ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-197">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="06ecd-198">Darüber hinaus sollte der Schlüssel Integritätsindikator (Khi) "Adressbuch Benutzer richtig indiziert" in System Center Operations Manager deaktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="06ecd-198">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="06ecd-199">Anforderungen können fehlschlagen, wenn IPv6 in einem Edge-Pool konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="06ecd-199">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="06ecd-200">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-200">**Issue:**</span></span>

<span data-ttu-id="06ecd-201">Wenn IPv6 in einem Edge-Pool konfiguriert ist, treten möglicherweise einige Anforderungen an den Edge-Pool fehl.</span><span class="sxs-lookup"><span data-stu-id="06ecd-201">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="06ecd-202">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-202">**Workaround:**</span></span>

<span data-ttu-id="06ecd-203">Um dieses Problem zu umgehen, konfigurieren Sie keinen Edge-Pool mit IPv6.</span><span class="sxs-lookup"><span data-stu-id="06ecd-203">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="06ecd-204">Das Cmdlet "Invoke-csPoolFailback" schlägt möglicherweise während des Failback des Pools fehl</span><span class="sxs-lookup"><span data-stu-id="06ecd-204">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="06ecd-205">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-205">**Issue:**</span></span>

<span data-ttu-id="06ecd-206">Beim Versuch, einen Pool zurückzukehren, schlägt das Cmdlet **Invoke-csPoolFailback** möglicherweise mit dem Fehler "Fehler beim Durchführen des hydratations Prozesses nach wiederholtem Versuch" fehl.</span><span class="sxs-lookup"><span data-stu-id="06ecd-206">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="06ecd-207">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-207">**Workaround:**</span></span>

<span data-ttu-id="06ecd-208">Um dieses Problem zu umgehen, führen Sie das Cmdlet erneut aus, und warten Sie, bis das Cmdlet erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="06ecd-208">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="06ecd-209">Beachten Sie, dass die Ausführung des Failback-Vorgangs einige Minuten dauern kann.</span><span class="sxs-lookup"><span data-stu-id="06ecd-209">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="06ecd-210">Für einen Pool mit 20.000-Benutzern kann es bis zu 60 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="06ecd-210">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="06ecd-211">Datenverlust kann auftreten, wenn Sie einen Front-End-Server zu einem bereits eingerichteten Pool hinzufügen – Hybrid, Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="06ecd-211">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="06ecd-212">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-212">**Issue:**</span></span>

<span data-ttu-id="06ecd-213">Dieses Problem kann in einer Umgebung auftreten, in der ein Pool über mehr als einen Front-End-Server verfügt und Sie entweder einen der Front-End-Server neu starten oder einen neuen Front-End-Server hinzufügen, der zuvor nicht Teil des Pools war.</span><span class="sxs-lookup"><span data-stu-id="06ecd-213">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="06ecd-214">Benutzer, deren Daten archiviert werden, können Datenverluste erfahren, bis eine stabile Verteilung der Datenarchivierung für den Pool eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="06ecd-214">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="06ecd-215">Dieser Zeitraum des potenziellen Datenverlusts ist auf 15 Minuten für Gespräche zwischen zwei Personen und 30 Minuten für Konferenzen limitiert.</span><span class="sxs-lookup"><span data-stu-id="06ecd-215">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="06ecd-216">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-216">**Workaround:**</span></span>

<span data-ttu-id="06ecd-217">Wenn Sie die Wartung durchführen, sollten Sie statt der Front-End-Server einzeln im Pool einen Failover für den Pool zu einem anderen Pool durchführen und dann Wartungsaufgaben auf den Servern ausführen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-217">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="06ecd-218">Sie können den Dienst auch vor dem Ausführen von Wartungsaufgaben nicht mehr verfügbar machen und dann die Verfügbarkeit wiederherstellen, wenn die Wartung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="06ecd-218">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="06ecd-219">Administratoren können die Anzahl der Lizenznehmer nicht mithilfe des Get-CsClientAccessLicense-Cmdlets abrufen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-219">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="06ecd-220">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-220">**Issue:**</span></span>

<span data-ttu-id="06ecd-221">Administratoren können mit dem Cmdlet **Get-CsClientAccessLicense** keine genaue Clientlizenz Verwendung erhalten.</span><span class="sxs-lookup"><span data-stu-id="06ecd-221">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="06ecd-222">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-222">**Workaround:**</span></span>

<span data-ttu-id="06ecd-223">Zum Überprüfen des Server Lizenztyps können Sie das Cmdlet **Get-CsService** ausführen, um die vollqualifizierten Domänennamen (FDQNs) aller Datenbanken abzurufen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-223">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="06ecd-224">Wenn der FQDN des Front-End-Servers mit dem FQDN der Back-End-Datenbank identisch ist, handelt es sich bei der Lizenz um eine Standard Edition-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="06ecd-224">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="06ecd-225">Andernfalls handelt es sich bei der Lizenz um eine Enterprise Edition-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="06ecd-225">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="06ecd-226">Anzahl der Client-Lizenzen wird nicht genau gemeldet</span><span class="sxs-lookup"><span data-stu-id="06ecd-226">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="06ecd-227">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-227">**Issue:**</span></span>

<span data-ttu-id="06ecd-228">Wenn Sie die Anzahl der Clientlizenzen ermitteln, treten möglicherweise die folgenden Bedingungen auf:</span><span class="sxs-lookup"><span data-stu-id="06ecd-228">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="06ecd-229">**Ungenaue Lizenzanzahl für mobile Benutzer**</span><span class="sxs-lookup"><span data-stu-id="06ecd-229">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="06ecd-230">Die Anzahl der Lizenzen basiert auf der Anzahl der eindeutigen IP-Adressen für gerätebasierte Benutzer.</span><span class="sxs-lookup"><span data-stu-id="06ecd-230">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="06ecd-231">Die Anzahl der Lizenzen ist wie folgt limitiert:</span><span class="sxs-lookup"><span data-stu-id="06ecd-231">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="06ecd-232">Lizenzen werden über gezählt, wenn sich die IP-Adresse des Benutzers während lync-Sitzungen ändert.</span><span class="sxs-lookup"><span data-stu-id="06ecd-232">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="06ecd-233">Dies kann auftreten, wenn ein Benutzer mit einem Desktop Client eine Verbindung mit lync Server von mehr als einem Standort herstellt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-233">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="06ecd-234">Lizenzen werden untersucht, wenn ein Benutzer eine Verbindung mit einem mobilen Client herstellt, weil die IP-Adresse für das Gerät nicht ermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="06ecd-234">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="06ecd-235">**Lizenzen werden zweimal für PSTN-Anrufe (Public Switched Telephone Network) an lync-Client, lync-Client Anrufe an PSTN-Leitungen und lync-Anrufe, die an PSTN-Leitungen weitergeleitet werden, gezählt.**</span><span class="sxs-lookup"><span data-stu-id="06ecd-235">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="06ecd-236">In den folgenden Szenarien werden zwei zusätzliche Lizenzen anstatt eines gezählt, weil sowohl die Telefonnummer als auch der lync-Benutzer gezählt werden, um die Anzahl der verwendeten Lizenzen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="06ecd-236">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="06ecd-237">Um genaue Lizenzierungsdaten zu erhalten, entfernen Sie manuell die von einer Telefonnummer generierten Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-237">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="06ecd-238">Ein PSTN-Telefonanruf an lync</span><span class="sxs-lookup"><span data-stu-id="06ecd-238">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="06ecd-239">Ein lync-Anruf an eine PSTN-Leitung</span><span class="sxs-lookup"><span data-stu-id="06ecd-239">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="06ecd-240">Ein PSTN-Anruf an lync, und lync leitet den Anruf an eine PSTN-Leitung weiter.</span><span class="sxs-lookup"><span data-stu-id="06ecd-240">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="06ecd-241">Eine der PSTN-Linien wird gezählt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-241">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="06ecd-242">**Eine Lizenz wird nicht für ein angemeldetes lync-Telefon gezählt**</span><span class="sxs-lookup"><span data-stu-id="06ecd-242">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="06ecd-243">Wenn ein Benutzer ein lync-zertifiziertes Telefon verwendet, wenn sich das Telefon anmeldet und verbunden bleibt, wodurch sein Anmeldestatus beibehalten wird, wird das Telefon nicht als Verwendung einer Lizenz gewertet, wenn die Abfrage für Lizenzen nach dem Einloggen des Telefons erfolgt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-243">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="06ecd-244">**Lizenzen für PSTN-Telefone, die an Konferenzen teilnehmen**</span><span class="sxs-lookup"><span data-stu-id="06ecd-244">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="06ecd-245">Wenn ein Benutzer mit einem PSTN-Telefon an einer Konferenz teilnimmt, wird eine Lizenz für die Teilnahme an der Konferenz ungenau gezählt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-245">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="06ecd-246">Es ist jedoch keine Lizenz erforderlich, um mit einem PSTN-Telefon an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-246">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="06ecd-247">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-247">**Workaround:**</span></span>

1.  <span data-ttu-id="06ecd-248">**Ungenaue Lizenzanzahl für mobile Benutzer**</span><span class="sxs-lookup"><span data-stu-id="06ecd-248">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="06ecd-249">Sie können die IP-Adressen, die zum gleichen Gerät gehören, manuell identifizieren und dann eine davon in der Anzahl der Lizenzen entfernen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-249">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="06ecd-250">Für dieses Problem gibt es keine Problemumgehung bei mobilen Geräten, die mit dem lync-Client verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="06ecd-250">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="06ecd-251">**Lizenzen werden zweimal für PSTN-Anrufe an lync-Client, lync-Client Anrufe an PSTN-Leitungen und lync-Anrufe an PSTN-Leitungen weitergeleitet.**</span><span class="sxs-lookup"><span data-stu-id="06ecd-251">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="06ecd-252">Sie müssen die PSTN-Telefonnummer manuell identifizieren und die für Sie generierte Lizenzanzahl entfernen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-252">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="06ecd-253">**Eine Lizenz wird nicht für ein angemeldetes lync-Telefon gezählt**</span><span class="sxs-lookup"><span data-stu-id="06ecd-253">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="06ecd-254">Sie können das lync-Telefon so konfigurieren, dass es sich abmeldet, und sich dann in regelmäßigen Abständen erneut anmelden, beispielsweise alle drei Monate.</span><span class="sxs-lookup"><span data-stu-id="06ecd-254">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="06ecd-255">**Lizenzen für PSTN-Telefone, die an Konferenzen teilnehmen**</span><span class="sxs-lookup"><span data-stu-id="06ecd-255">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="06ecd-256">Sie können die PSTN-Telefonnummer, die für die Teilnahme an der Konferenz verwendet wird, manuell identifizieren und die von der Telefonnummer generierte Lizenz entfernen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-256">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="06ecd-257">Die lync Server-Systemsteuerung funktioniert nach dem Upgrade auf Silverlight 5 nicht mehr in einer VMware-Umgebung</span><span class="sxs-lookup"><span data-stu-id="06ecd-257">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="06ecd-258">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-258">**Issue:**</span></span>

<span data-ttu-id="06ecd-259">Wenn Sie die lync Server-Systemsteuerung in einer VMware-Umgebung verwenden, funktioniert die lync Server-Systemsteuerung nach dem Upgrade von Microsoft Silverlight auf Version 5 möglicherweise nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="06ecd-259">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="06ecd-260">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-260">**Workaround:**</span></span>

<span data-ttu-id="06ecd-261">Führen Sie eine der folgenden Aktionen aus, um dieses Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="06ecd-261">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="06ecd-262">Deinstallieren Sie Silverlight 5, und installieren Sie Silverlight 4 aus [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156) .</span><span class="sxs-lookup"><span data-stu-id="06ecd-262">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="06ecd-263">Greifen Sie auf die lync Server-Systemsteuerung auf einem Computer zu, auf dem es sich nicht um einen virtuellen VMware-Computer handelt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-263">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="06ecd-264">Zu diesem Zweck können Sie die lync Server-Systemsteuerung über das Windows- **Startmenü** auf dem Server starten, wenn die lync Server-Verwaltungstools auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="06ecd-264">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="06ecd-265">Sie können auch mithilfe eines Webbrowsers auf die lync Server-Systemsteuerung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-265">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="06ecd-266">Die URL wird https:///CSCP. ähnlich sein. \<frontend\_pool\_fqdn\></span><span class="sxs-lookup"><span data-stu-id="06ecd-266">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="06ecd-267">Benutzerinformationen im Adressbuchdienst werden nicht aktualisiert, nachdem der Distinguished Name für den Benutzer in Active Directory geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="06ecd-267">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="06ecd-268">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-268">**Issue:**</span></span>

<span data-ttu-id="06ecd-269">Wenn der Distinguished Name eines Benutzers (auch bekannt als DN) in den Active Directory-Domänendiensten geändert wird, werden alle weiteren Änderungen im Adressbuchdienst (ABS) nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="06ecd-269">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="06ecd-270">Dies wirkt sich nicht auf die Anmeldung oder Anwesenheit des Benutzers aus, es wird jedoch die Kommunikation für den Benutzer verhindert, wenn die SIP-Adresse ebenfalls geändert wird, da durch Suchvorgänge eine veraltete SIP-Adresse zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-270">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="06ecd-271">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-271">**Workaround:**</span></span>

<span data-ttu-id="06ecd-272">Um dieses Problem zu umgehen, ändern Sie den DN eines Benutzers nicht.</span><span class="sxs-lookup"><span data-stu-id="06ecd-272">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="06ecd-273">Wenn Sie den DN für den Benutzer auf den vorherigen Wert zurücksetzen, werden Updates im Adressbuchdienst wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="06ecd-273">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="06ecd-274">Installation</span><span class="sxs-lookup"><span data-stu-id="06ecd-274">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="06ecd-275">Die Verwendung von nicht-ASCII-Zeichen kann dazu führen, dass lync Server nicht gestartet wird</span><span class="sxs-lookup"><span data-stu-id="06ecd-275">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="06ecd-276">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-276">**Issue:**</span></span>

<span data-ttu-id="06ecd-277">Das Setup schlägt fehl, wenn der Name des Zielordners nicht-ASCII-Zeichen enthält (einschließlich Unicode, Doppelbyte-Zeichensatz (DBCS), UTF-8 und UTF-16).</span><span class="sxs-lookup"><span data-stu-id="06ecd-277">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="06ecd-278">Darüber hinaus kann Setup erfolgreich ausgeführt werden, aber der Server wird nicht gestartet, wenn in einer der folgenden nicht-ASCII-Zeichen enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="06ecd-278">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="06ecd-279">Computer Name</span><span class="sxs-lookup"><span data-stu-id="06ecd-279">Computer name</span></span>

  - <span data-ttu-id="06ecd-280">Domänenname</span><span class="sxs-lookup"><span data-stu-id="06ecd-280">Domain name</span></span>

  - <span data-ttu-id="06ecd-281">Benutzername</span><span class="sxs-lookup"><span data-stu-id="06ecd-281">User name</span></span>

  - <span data-ttu-id="06ecd-282">SIP-URI des Benutzers</span><span class="sxs-lookup"><span data-stu-id="06ecd-282">User SIP URI</span></span>

  - <span data-ttu-id="06ecd-283">Dienstkontoname</span><span class="sxs-lookup"><span data-stu-id="06ecd-283">Service account name</span></span>

<span data-ttu-id="06ecd-284">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-284">**Workaround:**</span></span>

<span data-ttu-id="06ecd-285">Verwenden Sie nur ASCII-Zeichen im Zielordnernamen, Computername, Domänenname, Benutzername, SIP-URI des Benutzers und Dienstkontonamen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-285">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="06ecd-286">Der Hotfix für "Heap Beschädigung tritt auf, wenn ein Modul die InsertEntityBody-Methode in IIS 7,5" aufruft, muss vor der Installation von lync Server 2013 installiert werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-286">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="06ecd-287">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-287">**Issue:**</span></span>

<span data-ttu-id="06ecd-288">Der Hotfix für "Heap Beschädigungen tritt auf, wenn ein Modul die InsertEntityBody-Methode in IIS 7,5" () aufruft [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) , die im Microsoft Knowledge Base-Artikel 264886 () beschrieben wird [https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603) , muss vor der Installation von lync Server 2013 installiert werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-288">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="06ecd-289">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-289">**Workaround:**</span></span>

<span data-ttu-id="06ecd-290">Laden Sie den Hotfix aus dem Microsoft Download Center unter herunter, und installieren Sie ihn [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) .</span><span class="sxs-lookup"><span data-stu-id="06ecd-290">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="06ecd-291">Lync Server 2013 kann unter ITA Windows Server 2012 OS RTM-Version nicht installiert werden</span><span class="sxs-lookup"><span data-stu-id="06ecd-291">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="06ecd-292">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-292">**Issue:**</span></span>

<span data-ttu-id="06ecd-293">Die Installation von lync Server 2013 schlägt auf ITA Windows Server 2012 aufgrund einer fehlgeschlagenen Windows-Fabric-Installation fehl.</span><span class="sxs-lookup"><span data-stu-id="06ecd-293">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="06ecd-294">Die Windows-Fabric-Installation schlägt fehl, da Fabric-Ablaufverfolgungen mit dem Zeitformat HH: mm: SS erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-294">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="06ecd-295">In ITA Windows Server ist das Uhrzeitformat jedoch hh. MM.SS.</span><span class="sxs-lookup"><span data-stu-id="06ecd-295">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="06ecd-296">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-296">**Workaround:**</span></span>

<span data-ttu-id="06ecd-297">Um dieses Problem zu umgehen, aktualisieren Sie die Systemregistrierung, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="06ecd-297">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="06ecd-298">Der Registrierungsschlüssel, der aktualisiert werden muss, lautet: \_ HKEY \\ -Benutzer. Standardmäßiges \\ Control Panel für \\ internationale \\ sTimeFormat.</span><span class="sxs-lookup"><span data-stu-id="06ecd-298">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="06ecd-299">Ändern Sie den Wert von sTimeFormat in hh: mm: SS, indem Sie die Windows PowerShell-Befehlszeilenschnittstelle wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="06ecd-299">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="06ecd-300">Starten Sie Windows PowerShell, und führen Sie die folgenden Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="06ecd-300">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="06ecd-301">Führen Sie zum Anzeigen des aktuellen Werts das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="06ecd-301">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="06ecd-302">Notieren Sie sich den aktuellen Wert für sTimeFormat, damit er nach Abschluss der Installation wiederhergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="06ecd-302">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="06ecd-303">Wenn Sie auf neuen Wert setzen möchten, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="06ecd-303">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="06ecd-304">Nachdem lync Server 2013 erfolgreich installiert wurde, stellen Sie den ursprünglichen Wert für sTimeFormat wieder her, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="06ecd-304">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="06ecd-305">Set-ItemProperty $a-Name-sTimeFormat-Wert "<Wert, der in Schritt 3 notiert wurde.</span><span class="sxs-lookup"><span data-stu-id="06ecd-305">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="06ecd-306">über> "</span><span class="sxs-lookup"><span data-stu-id="06ecd-306">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="06ecd-307">Mobilität</span><span class="sxs-lookup"><span data-stu-id="06ecd-307">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="06ecd-308">Probleme für mobile Clients während des Server Failover-Prozesses</span><span class="sxs-lookup"><span data-stu-id="06ecd-308">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="06ecd-309">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-309">**Issue:**</span></span>

<span data-ttu-id="06ecd-310">Wenn ein lync-Server ausfällt und der Failoverprozess beginnt, können sich die folgenden Probleme auf Mobile Client-Benutzer auswirken:</span><span class="sxs-lookup"><span data-stu-id="06ecd-310">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="06ecd-311">Kein eingehender lync-Anruf oder Signal für bis zu 10 Minuten nach Beginn des Failovers.</span><span class="sxs-lookup"><span data-stu-id="06ecd-311">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="06ecd-312">Eingehende Chat-Anfragen können nicht akzeptiert werden</span><span class="sxs-lookup"><span data-stu-id="06ecd-312">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="06ecd-313">Teilnahme an Besprechungen ist nicht möglich, wenn der fehlerhafte Server der Stammserver für den Benutzer ist</span><span class="sxs-lookup"><span data-stu-id="06ecd-313">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="06ecd-314">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-314">**Workaround:**</span></span>

<span data-ttu-id="06ecd-315">Für dieses Problem gibt es keine Problemumgehung.</span><span class="sxs-lookup"><span data-stu-id="06ecd-315">There is no workaround for this issue.</span></span> <span data-ttu-id="06ecd-316">Die normale Funktionalität wird nach Abschluss des Failover-Vorgangs wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-316">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="06ecd-317">Wenn ein mobiler Benutzer einen eingehenden Anruf von einem anderen lync-Endpunkt ablehnt, wird der Anruf als verpasste Konvertierung auf lync Mobile-Clients angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-317">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="06ecd-318">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-318">**Issue:**</span></span>

<span data-ttu-id="06ecd-319">Wenn ein mobiler Benutzer einen eingehenden Anruf ablehnt und der Anruf von einem anderen lync-Endpunkt stammt, wird der Anruf im lync Mobile-Client anstelle eines Anrufs in der Geräte Anrufliste als verpasste Unterhaltung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-319">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="06ecd-320">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-320">**Workaround:**</span></span>

<span data-ttu-id="06ecd-321">Für dieses Problem gibt es keine Problemumgehung.</span><span class="sxs-lookup"><span data-stu-id="06ecd-321">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="06ecd-322">Beim Suchen nach Kontakten wird vom mobilen Client möglicherweise der Anzeigename des verbundenen Kontakts nicht angezeigt</span><span class="sxs-lookup"><span data-stu-id="06ecd-322">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="06ecd-323">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-323">**Issue:**</span></span>

<span data-ttu-id="06ecd-324">Der Anzeigename für Verbund Kontakte wird in einigen Szenarien möglicherweise nicht angezeigt, beispielsweise bei der Suche nach einem Verbundkontakt in der Kontaktliste.</span><span class="sxs-lookup"><span data-stu-id="06ecd-324">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="06ecd-325">Dies kann auftreten, wenn das Abonnement für den Kontakt nicht über den lync Mobile-Client vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="06ecd-325">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="06ecd-326">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-326">**Workaround:**</span></span>

<span data-ttu-id="06ecd-327">Für dieses Problem gibt es keine Problemumgehung.</span><span class="sxs-lookup"><span data-stu-id="06ecd-327">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="06ecd-328">In einer verpassten Unterhaltung, bei der es sich um eine Einladung zu einer Konferenz handelt, fehlen im mobilen Clientinformationen zu invite und TIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="06ecd-328">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="06ecd-329">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-329">**Issue:**</span></span>

<span data-ttu-id="06ecd-330">Wenn eine verpasste Unterhaltung im mobilen Client eine Einladung zu einer Konferenz ist, fehlen die Informationen zum einladen und Zeitstempel in der Nachricht für verpasste Unterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-330">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="06ecd-331">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-331">**Workaround:**</span></span>

<span data-ttu-id="06ecd-332">Für dieses Problem gibt es keine Problemumgehung.</span><span class="sxs-lookup"><span data-stu-id="06ecd-332">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="06ecd-333">Benutzer von mobilen Clients, die VoIP-Anrufe tätigen, können Voicemail nicht für Benutzer hinterlassen, deren Voicemail in Exchange 2010 oder früheren Versionen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="06ecd-333">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="06ecd-334">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-334">**Issue:**</span></span>

<span data-ttu-id="06ecd-335">Wenn ein mobiler Client-Benutzer VoIP für Anrufe verwendet, kann der Benutzer keine Voicemail-Nachrichten für Benutzer hinterlassen, die für die Verwendung von Voicemail in Microsoft Exchange Server 2007 oder Microsoft Exchange Server 2010 konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="06ecd-335">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="06ecd-336">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-336">**Workaround:**</span></span>

<span data-ttu-id="06ecd-337">Um dieses Problem zu umgehen, verwenden Sie Exchange 2010 mit SP1 oder einer höheren Version von Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="06ecd-337">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="06ecd-338">Bei Verwendung von Block mit URL für die Client Versions Konfiguration auf mobilen Clients wird möglicherweise eine falsche Fehlermeldung angezeigt</span><span class="sxs-lookup"><span data-stu-id="06ecd-338">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="06ecd-339">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-339">**Issue:**</span></span>

<span data-ttu-id="06ecd-340">Bei Verwendung von **Block mit URL** für die Client Versions Konfiguration auf mobilen Clients wird möglicherweise eine falsche Fehlermeldung angezeigt, wenn die Client Version nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-340">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="06ecd-341">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-341">**Workaround:**</span></span>

<span data-ttu-id="06ecd-342">Um dieses Problem zu umgehen, konfigurieren Sie die Client Versions Konfiguration so, dass **Block** anstelle von **Block mit URL** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-342">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="06ecd-343">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="06ecd-343">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013-front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="06ecd-344">Antivirensoftware, die auf den lync Server 2013-Front-End-Servern ausgeführt wird, kann zu einer Anwendungsdomänen Wiederverwendung führen, die den Dienst für lync Web App 2013, lync Mobile 2010 und lync Mobile 2013-Clients vorübergehend unterbricht.</span><span class="sxs-lookup"><span data-stu-id="06ecd-344">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="06ecd-345">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-345">**Issue:**</span></span>

<span data-ttu-id="06ecd-346">Antivirensoftware kann Neustart der Anwendungsdomäne auslösen, was dazu führen kann, dass lync Mobility Service 2013 und Unified Communications (UC) Web-API-Clientanwendungen (lync Web App 2013, lync Mobile 2010 und lync Mobile 2013) ihren Zustand verlieren.</span><span class="sxs-lookup"><span data-stu-id="06ecd-346">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="06ecd-347">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-347">**Workaround:**</span></span>

<span data-ttu-id="06ecd-348">Um dieses Problem zu umgehen, schließen Sie die Ordner, die Webkomponenten und .NET Framework enthalten, von der Antivirus-Prüfung aus.</span><span class="sxs-lookup"><span data-stu-id="06ecd-348">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="06ecd-349">Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 312592, "PRB: zufällige Anwendungsneustarts mit der Anwendung wird neu gestartet"-Fehler in ASP.net [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592) .</span><span class="sxs-lookup"><span data-stu-id="06ecd-349">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="06ecd-350">Die folgenden Ordner sollten ausgeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="06ecd-350">The following folders should be excluded:</span></span>

  - <span data-ttu-id="06ecd-351">% Programme% \\ Microsoft lync Server 2013 \\ Web Components \\ MCX \\ ext</span><span class="sxs-lookup"><span data-stu-id="06ecd-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="06ecd-352">% Programme% \\ Microsoft lync Server 2013 \\ Web Components \\ MCX \\ int</span><span class="sxs-lookup"><span data-stu-id="06ecd-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="06ecd-353">% Programme% \\ Microsoft lync Server 2013 \\ Web Components \\ Ucwa \\ int</span><span class="sxs-lookup"><span data-stu-id="06ecd-353">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="06ecd-354">% Programme% \\ Microsoft lync Server 2013 \\ Web Components \\ Ucwa \\ ext</span><span class="sxs-lookup"><span data-stu-id="06ecd-354">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="06ecd-355">% Windir% \\ Microsoft.net \\ Framework64 \\ v 4.0.30319 \\ config</span><span class="sxs-lookup"><span data-stu-id="06ecd-355">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="06ecd-356">ActiveX-Steuerelemente oder Native XMLHTTP-Unterstützung müssen in Windows Internet Explorer aktiviert sein, damit Sie erfolgreich an Konferenzen teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="06ecd-356">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="06ecd-357">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-357">**Issue:**</span></span>

<span data-ttu-id="06ecd-358">Wenn ein Benutzer sowohl ActiveX-Steuerelemente als auch die Native XMLHTTP-Unterstützung in den Internetbrowsereinstellungen von Windows Internet Explorer deaktiviert hat, kann der Benutzer nicht an einer Besprechung teilnehmen, wenn Internet Explorer als Standardbrowser ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="06ecd-358">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="06ecd-359">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-359">**Workaround:**</span></span>

<span data-ttu-id="06ecd-360">Aktivieren Sie entweder ActiveX-Steuerelemente oder "Native XMLHTTP-Unterstützung" in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="06ecd-360">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="06ecd-361">Der lync Server-Webkonferenzdienst kann im kritischen Modus nicht wiederhergestellt werden</span><span class="sxs-lookup"><span data-stu-id="06ecd-361">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="06ecd-362">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-362">**Issue:**</span></span>

<span data-ttu-id="06ecd-363">Wenn der kritische Modus für die Archivierung aktiviert ist, wird bei Systemfehlern der kritische Modus gestartet, und die Konferenzen funktionieren nicht mehr für die Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="06ecd-363">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="06ecd-364">Nachdem der Administrator die Systemfehler (wie das Beheben eines Datenbankproblems) behoben hat, wird der Datenkonferenzdienst nicht automatisch wiederhergestellt, und der Administrator muss den Konferenzdienst manuell neu starten, damit die Konferenz fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="06ecd-364">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="06ecd-365">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-365">**Workaround:**</span></span>

<span data-ttu-id="06ecd-366">Ein Administrator muss den Konferenzdienst manuell neu starten, nachdem der Systemfehler behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="06ecd-366">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="06ecd-367">Webkonferenzdienst ignoriert den HTTP-Proxy für externe Office Web App-Server</span><span class="sxs-lookup"><span data-stu-id="06ecd-367">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="06ecd-368">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-368">**Issue:**</span></span>

<span data-ttu-id="06ecd-369">Wenn Sie einen Office Web Apps-Server außerhalb des Webkonferenz Diensts (also einen Server, der sich nicht im internen Unternehmensnetzwerk befindet) im Internet, Umkreisnetzwerk und dem Webkonferenzdienst bereitgestellt haben, erfordert ein HTTP-Proxy eine Verbindung mit diesem, wird die Office Web Apps-Server Ermittlung nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-369">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="06ecd-370">Der Webkonferenzdienst ignoriert die http-Proxyeinstellung, wie Sie im Topologie-Generator für Office Web Apps Server-Setup definiert ist.</span><span class="sxs-lookup"><span data-stu-id="06ecd-370">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="06ecd-371">Infolgedessen kann der lync-Client keine Microsoft PowerPoint 2010-Freigabe für andere Teilnehmer an der Konferenz durchführen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-371">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="06ecd-372">Wenn Sie lync Server lokal installieren und auch Office Web Apps Server lokal im internen Netzwerk konfigurieren, ist keine Proxykonfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="06ecd-372">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="06ecd-373">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-373">**Workaround:**</span></span>

<span data-ttu-id="06ecd-374">Die einzige Problemumgehung besteht darin, keine Bereitstellungskonfiguration zu verwenden, die die Verwendung des HTTP-Proxys für die Kommunikation mit einem externen Office Web Apps-Server erfordert.</span><span class="sxs-lookup"><span data-stu-id="06ecd-374">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="06ecd-375">Das Hinzufügen von Video zu einer Konferenz für Audiokonferenz-Anbieter wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="06ecd-375">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="06ecd-376">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-376">**Issue:**</span></span>

<span data-ttu-id="06ecd-377">Das Hinzufügen eines Videos wird nicht unterstützt, wenn der Benutzer zu einer Konferenz für Audio-Konferenz für Audio beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="06ecd-377">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="06ecd-378">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-378">**Workaround:**</span></span>

<span data-ttu-id="06ecd-379">Für dieses Problem gibt es keine Problemumgehung.</span><span class="sxs-lookup"><span data-stu-id="06ecd-379">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="06ecd-380">Topologien mit aktiviertem IPv6 erzwingen die automatische Aktualisierung der lync Web App Silverlight-Plug-in, um sicherzustellen, dass die Bildschirmfreigabe Funktionalität in lync Web App funktionieren kann.</span><span class="sxs-lookup"><span data-stu-id="06ecd-380">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="06ecd-381">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-381">**Issue:**</span></span>

<span data-ttu-id="06ecd-382">Wenn eine Topologie mit aktiviertem IPv6 konfiguriert ist, können Benutzer Ihren Bildschirm nicht über den lync Web App-Client freigeben, wenn bereits eine frühere Version des Plug-Ins für die Bildschirmfreigabe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="06ecd-382">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="06ecd-383">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-383">**Workaround:**</span></span>

<span data-ttu-id="06ecd-384">Wenn Sie ein Update auf die neueste Version des Plug-ins "Bildschirmübertragung" erzwingen möchten, wenn Sie über lync Web App an einer Besprechung teilnehmen, ändern Sie den Wert von **MinSupportedBuildVersion** von "4.0.7457.0" in "4.0.7577.380" in den beiden folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="06ecd-384">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="06ecd-385">% Programme% \\ Microsoft lync Server 15 \\ -Webkomponenten \\ erreichen \\ int-Client- \\ \\ Plugins \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="06ecd-385">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="06ecd-386">% Programme% \\ Microsoft lync Server 15 \\ -Webkomponenten \\ erreichen \\ ext-Client- \\ \\ Plugins \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="06ecd-386">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="06ecd-387">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="06ecd-387">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="06ecd-388">In einigen Fällen unterstützt ein lync-Client, der auf einem Computer ausgeführt wird, der für die Verwendung von IPv4 und IPv6 Dual Stack konfiguriert ist, möglicherweise keine Funktionen, die im IP-Subnetz des Computers wie E911, medienumgehung, Anrufsteuerung und standortbasiertes Routing basieren.</span><span class="sxs-lookup"><span data-stu-id="06ecd-388">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="06ecd-389">Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server 2013: February 2013.</span><span class="sxs-lookup"><span data-stu-id="06ecd-389">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="06ecd-390">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-390">**Issue:**</span></span>

<span data-ttu-id="06ecd-391">Wenn ein lync-Client auf einem Computer ausgeführt wird, der für IPv4 und IPv6 Dual Stack aktiviert ist, und basierend auf der DNS-Auflösung des Proxyservers, kann der Client die IPv6-Adresse des Computers zur Anmeldung verwenden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-391">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="06ecd-392">Anschließend unterstützt der lync-Client nur die Funktionen, die für IPv6 unterstützt werden, was E911, medienumgehung, Anrufsteuerung und standortbasiertes Routing ausschließt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-392">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="06ecd-393">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-393">**Workaround:**</span></span>

<span data-ttu-id="06ecd-394">Um dieses Problem zu umgehen, deaktivieren Sie die IPv6-Unterstützung auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="06ecd-394">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="06ecd-395">Wenn Enterprise-VoIP nicht für einen Benutzer konfiguriert ist, muss der Benutzer das E164-Format verwenden, um aus einer Konferenz heraus zu wählen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-395">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="06ecd-396">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-396">**Issue:**</span></span>

<span data-ttu-id="06ecd-397">Wenn Enterprise-VoIP nicht für einen Benutzer konfiguriert ist, muss dieser Benutzer das E164-Format verwenden, um sich erfolgreich aus einer Konferenz zu wählen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-397">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="06ecd-398">Wenn das E164-Format nicht verwendet wird, kann der Benutzer nicht aus der Konferenz wählen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-398">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="06ecd-399">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-399">**Workaround:**</span></span>

<span data-ttu-id="06ecd-400">Um dieses Problem zu umgehen, sollten Benutzer, die nicht für Enterprise-VoIP aktiviert sind, mithilfe von Zahlen im E164-Format aus einer Konferenz wählen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-400">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="06ecd-401">Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="06ecd-401">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="06ecd-402">Wenn ein Benutzer "alle Einladungen und Kommunikationen blockieren" ausgewählt hat, während der Unified Contact Store für den Benutzer aktiviert ist, wird der Anwesenheitsstatus nicht zurückgewiesen, wenn er</span><span class="sxs-lookup"><span data-stu-id="06ecd-402">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="06ecd-403">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-403">**Issue:**</span></span>

<span data-ttu-id="06ecd-404">Wenn ein Benutzer "alle Einladungen und Kommunikationen blockieren" ausgewählt hat, während der Unified Contact Store für den Benutzer aktiviert ist, wird der Anwesenheitsstatus nicht zurückgewiesen, wenn er sein sollte.</span><span class="sxs-lookup"><span data-stu-id="06ecd-404">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="06ecd-405">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-405">**Workaround:**</span></span>

<span data-ttu-id="06ecd-406">Um dieses Problem zu umgehen, können Sie den einheitlichen Kontaktspeicher für den Benutzer deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="06ecd-406">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="06ecd-407">Führen Sie dazu die folgenden Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="06ecd-407">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="06ecd-408">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="06ecd-408">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="06ecd-409">Office Communications Server 2007 R2-Benutzer, die lokal gehostet werden, können den Anwesenheitsstatus von Skype for Business Online-Benutzern in hybridbereitstellungen nicht anzeigen – Hybrid</span><span class="sxs-lookup"><span data-stu-id="06ecd-409">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="06ecd-410">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-410">**Issue:**</span></span>

<span data-ttu-id="06ecd-411">Das Problem kann bei einer hybridbereitstellung auftreten, wenn Sie einen lync Server 2013-Director verwenden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-411">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="06ecd-412">Der Anwesenheitsstatus für Benutzer, die in Skype for Business Online verwaltet werden, wird als "Anwesenheitsstatus unbekannt" für lokale Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-412">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="06ecd-413">Darüber hinaus können Benutzer, die in Skype for Business Online verwaltet werden, den Anwesenheitsstatus für Office Communications Server R2-lokale Benutzer nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-413">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="06ecd-414">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-414">**Workaround:**</span></span>

<span data-ttu-id="06ecd-415">Um dieses Problem teilweise zu umgehen, ändern Sie den Home-Server (Attribut msRTCSIP-presencehomeserver) der Skype for Business Online-Benutzer so, dass Sie auf einen lokalen lync Server 2013-Pool anstatt auf den lync Server 2013-Director verweisen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-415">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="06ecd-416">Sie können diese Einstellung auf dem lokalen Front-End-Server ändern.</span><span class="sxs-lookup"><span data-stu-id="06ecd-416">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="06ecd-417">Mit dieser Problemumgehung wird der Anwesenheitsstatus von Benutzern, die in Office Communications Server 2007 R2 verwaltet werden, für Skype for Business Online-Benutzer korrekt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-417">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="06ecd-418">Antwortgruppen Anwendung, Anruf Park Anwendung und Gruppenanruf Abholung</span><span class="sxs-lookup"><span data-stu-id="06ecd-418">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="06ecd-419">Ein Anrufer kann während der Einrichtung eines Anrufs mit der abrufenden Person eine Sekunde Musik hören</span><span class="sxs-lookup"><span data-stu-id="06ecd-419">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="06ecd-420">Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server 2013: February 2013.</span><span class="sxs-lookup"><span data-stu-id="06ecd-420">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="06ecd-421">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-421">**Issue:**</span></span>

<span data-ttu-id="06ecd-422">Wenn ein Anruf über Gruppenanruf abgeholt wird, kann der Anrufer während der Einrichtung des Anrufs mit der Retriever-Partei eine Sekunde Musik hören.</span><span class="sxs-lookup"><span data-stu-id="06ecd-422">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="06ecd-423">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-423">**Workaround:**</span></span>

<span data-ttu-id="06ecd-424">Für dieses Problem gibt es keine Problemumgehung.</span><span class="sxs-lookup"><span data-stu-id="06ecd-424">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="06ecd-425">Ein Reaktionsgruppen-Agent kann sich über eine lync Server 2010-Agent-Konsole an lync Server 2010 formelle Agentengruppen anmelden und abmelden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-425">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="06ecd-426">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-426">**Issue:**</span></span>

<span data-ttu-id="06ecd-427">Ein lync Server 2013-Reaktionsgruppen-Agent kann sich über eine lync Server 2010-Agent-Konsole an lync Server 2010 formelle Agentengruppen anmelden und abmelden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-427">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="06ecd-428">In der lync Server 2010-Agent-Konsole können Benutzer nur die lync Server 2010-Reaktionsgruppe sehen, der Sie angehören.</span><span class="sxs-lookup"><span data-stu-id="06ecd-428">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="06ecd-429">Sie können keine der lync Server 2013-Antwortgruppen sehen, denen Sie angehören.</span><span class="sxs-lookup"><span data-stu-id="06ecd-429">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="06ecd-430">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-430">**Workaround:**</span></span>

<span data-ttu-id="06ecd-431">Wenn der Reaktionsgruppen-Agent ein lync Server 2013-Benutzer und Teil einer formellen Agentengruppe von lync Server 2013 ist, muss der Benutzer direkt über einen Weblink in einem Browser auf die lync Server 2013-Agent-Konsole zugreifen, um sich bei lync Server 2013-Agentengruppen anzumelden und sich abzumelden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-431">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010-response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013-response-group"></a><span data-ttu-id="06ecd-432">Ein lync Server 2010-Reaktionsgruppen-Agent kann keine Anrufe im Auftrag einer lync Server 2013-Reaktionsgruppe tätigen</span><span class="sxs-lookup"><span data-stu-id="06ecd-432">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="06ecd-433">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-433">**Issue:**</span></span>

<span data-ttu-id="06ecd-434">Ein lync Server 2010-Benutzer, der ein Agent einer lync Server 2013-Reaktionsgruppe ist, kann keinen Anruf im Namen der Reaktionsgruppe tätigen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-434">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="06ecd-435">Die lync Server 2013-Reaktionsgruppe ist im lync-Client nicht verfügbar, um einen Anruf zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-435">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="06ecd-436">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-436">**Workaround:**</span></span>

<span data-ttu-id="06ecd-437">Um dieses Problem zu umgehen, müssen Sie den lync Server 2010-Benutzer in lync Server 2013 verschieben.</span><span class="sxs-lookup"><span data-stu-id="06ecd-437">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="06ecd-438">Wenn Sie eine Reaktionsgruppe aus lync Server 2010 entfernen, nachdem Sie zu lync Server 2013 migriert wurde, wird verhindert, dass die Reaktionsgruppe eingehende Anrufe akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="06ecd-438">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="06ecd-439">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-439">**Issue:**</span></span>

<span data-ttu-id="06ecd-440">Wenn eine Reaktionsgruppe, die von lync Server 2010 zu lync Server 2013 migriert wurde, aus lync Server 2010 über die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell entfernt wird, wird die Antwortgruppe in lync Server 2013 keine eingehenden Anrufe mehr empfangen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-440">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="06ecd-441">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-441">**Workaround:**</span></span>

<span data-ttu-id="06ecd-442">Um dieses Problem zu umgehen, entfernen Sie keine Antwortgruppen aus lync Server 2010, die von lync Server 2010 zu lync Server 2013 migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-442">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="06ecd-443">Wenn die Reaktionsgruppe bereits entfernt wurde, sollten Sie Sie in lync Server 2013 erneut bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-443">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="06ecd-444">Wenn ein neuer verwalteter Workflow bei der Erstellung auf inaktiv eingestellt ist, schlägt die Bereitstellung des Workflows fehl</span><span class="sxs-lookup"><span data-stu-id="06ecd-444">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="06ecd-445">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-445">**Issue:**</span></span>

<span data-ttu-id="06ecd-446">Wenn ein neuer verwalteter Workflow bei der Erstellung auf inaktiv eingestellt ist, schlägt die Bereitstellung des Workflows fehl.</span><span class="sxs-lookup"><span data-stu-id="06ecd-446">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="06ecd-447">Dieses Problem tritt auf, wenn der Workflow bei der Erstellung auf inaktiv festgesetzt wird, sich aber nicht auf einen Workflow auswirkt, der bearbeitet wird, um ihn nach der Bereitstellung von is auf inaktiv festzulegen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-447">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="06ecd-448">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-448">**Workaround:**</span></span>

<span data-ttu-id="06ecd-449">Wenn Sie einen Workflow erstellen und bereitstellen, legen Sie den Workflow als aktiv und dann bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-449">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="06ecd-450">Nachdem der Workflow erfolgreich bereitgestellt wurde, kann der Workflow bearbeitet und auf inaktiv eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-450">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="06ecd-451">Durch das Entfernen einer Reaktionsgruppe aus dem Besitzer Pool wird verhindert, dass die Reaktionsgruppe des Sicherungs Pools eingehende Anrufe während eines Failovers akzeptiert, wenn die Reaktionsgruppe in den Sicherungspool importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="06ecd-451">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="06ecd-452">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-452">**Issue:**</span></span>

<span data-ttu-id="06ecd-453">Wenn eine Reaktionsgruppe, die im Besitz des primären Pools ist, in den Sicherungspool importiert wurde, ohne den Besitzer zu überschreiben, und die Reaktionsgruppe aus dem Besitzer Pool entfernt wird, akzeptiert die Reaktionsgruppe im Sicherungspool keine eingehenden Anrufe während eines Failovers.</span><span class="sxs-lookup"><span data-stu-id="06ecd-453">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="06ecd-454">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-454">**Workaround:**</span></span>

<span data-ttu-id="06ecd-455">Sie müssen die Reaktionsgruppe im primären Pool erneut bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-455">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="06ecd-456">Sie müssen dann die Konfiguration der Reaktionsgruppe aus dem primären Pool exportieren und erneut in den Sicherungspool importieren.</span><span class="sxs-lookup"><span data-stu-id="06ecd-456">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="06ecd-457">Sie können die Reaktionsgruppe auch im Sicherungspool neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-457">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="06ecd-458">In diesem Fall ist der Sicherungspool der Besitzer Pool der Reaktionsgruppe.</span><span class="sxs-lookup"><span data-stu-id="06ecd-458">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="06ecd-459">Ein geparkter Anruf kann nicht aus der Anwendung für den Anruf Park abgerufen werden, wenn die Abrufanforderung im Auftrag einer Reaktionsgruppe erfolgt</span><span class="sxs-lookup"><span data-stu-id="06ecd-459">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="06ecd-460">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-460">**Issue:**</span></span>

<span data-ttu-id="06ecd-461">Wenn die folgenden Bedingungen erfüllt sind, schlägt eine Abrufanforderung für einen geparkten Anruf fehl:</span><span class="sxs-lookup"><span data-stu-id="06ecd-461">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="06ecd-462">Ein Agent ist Teil einer anonymen Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="06ecd-462">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="06ecd-463">Der Agent versucht, einen geparkten Anruf aus der Anwendung "Anruf parken" über die Gruppe "anonyme Antwort" abzurufen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-463">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="06ecd-464">Der Agent versucht, den Anruf abzurufen, indem er die Umlaufbahn Nummer über die Option "Anruf im Auftrag" oder über die gleiche Option im lync Attendant-Client anwählt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-464">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="06ecd-465">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-465">**Workaround:**</span></span>

<span data-ttu-id="06ecd-466">Für dieses Problem gibt es keine Problemumgehungen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-466">There are no workarounds for this issue.</span></span> <span data-ttu-id="06ecd-467">Der geparkte Anruf sollte ohne diese Vorgehensweise im Namen einer Reaktionsgruppe abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-467">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="06ecd-468">Lync Server-Systemsteuerung, Topologie-Generator und Planungstool</span><span class="sxs-lookup"><span data-stu-id="06ecd-468">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="06ecd-469">Einschränkungen des Planungstools</span><span class="sxs-lookup"><span data-stu-id="06ecd-469">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="06ecd-470">Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server 2013: February 2013.</span><span class="sxs-lookup"><span data-stu-id="06ecd-470">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="06ecd-471">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-471">**Issue:**</span></span>

<span data-ttu-id="06ecd-472">Das Planungs Tool weist bei der Planung der Bereitstellung die folgenden Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="06ecd-472">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="06ecd-473">Es werden maximal 10 zentrale Websites unterstützt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-473">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="06ecd-474">Jede zentrale Website kann maximal 14 Zweigstellen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-474">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="06ecd-475">Für jeden zentralen Standort können maximal 240.000-Benutzer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="06ecd-475">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="06ecd-476">Darüber hinaus enthält das Planungs Tool beim Berechnen der empfohlenen Topologie keine Werte für die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="06ecd-476">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="06ecd-477">Die Anzahl der Benutzer, die Online verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="06ecd-477">The number of users that are homed online</span></span>

  - <span data-ttu-id="06ecd-478">Der Prozentsatz der Benutzer, die für die XMPP-Föderation aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="06ecd-478">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="06ecd-479">Prozentsatz der Benutzer, die lync Web App verwenden</span><span class="sxs-lookup"><span data-stu-id="06ecd-479">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="06ecd-480">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-480">**Workaround:**</span></span>

<span data-ttu-id="06ecd-481">Für diese Probleme gibt es keine Problemumgehung.</span><span class="sxs-lookup"><span data-stu-id="06ecd-481">There is no workaround for these issues.</span></span> <span data-ttu-id="06ecd-482">Weitere Informationen zum Planungstool finden Sie unter [Entwerfen der Topologie für lync Server 2013 mithilfe des Planungstools](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span><span class="sxs-lookup"><span data-stu-id="06ecd-482">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="06ecd-483">Das Planungs Tool verwendet beim Aktualisieren von Optionen möglicherweise nicht zuvor definierte IP-Adressen für das Edge-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="06ecd-483">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="06ecd-484">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-484">**Issue:**</span></span>

<span data-ttu-id="06ecd-485">Nachdem Sie Ihren Entwurf mithilfe des Planungstools abgeschlossen haben, können Sie, wenn Sie Änderungen an den Edge-Netzwerkoptionen vornehmen, dem Entwurf zusätzliche IP-Adressen hinzugefügt werden, anstatt die vorhandenen IP-Adressen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="06ecd-485">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="06ecd-486">Dies kann auftreten, wenn Sie die Details des Edge-Netzwerkdiagramms anzeigen, wählen Sie **Klicken Sie hier, um Ihre Optionen zu aktualisieren** aus, und wählen Sie dann im Dialogfeld Konfigurationsoptionen die Option Edge-Netzwerk auswählen **Ich möchte dieselben FQDNs und IP-Adressen verwenden, aber verschiedene Ports für die Edgedienst auf meinem Edgeserver** aus.</span><span class="sxs-lookup"><span data-stu-id="06ecd-486">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="06ecd-487">Das Anwenden von Änderungen kann dazu führen, dass neue IP-Adressen und Edgeserver dem Entwurf hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-487">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="06ecd-488">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-488">**Workaround:**</span></span>

<span data-ttu-id="06ecd-489">Für dieses Problem gibt es zurzeit keine Problemumgehung.</span><span class="sxs-lookup"><span data-stu-id="06ecd-489">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="06ecd-490">In der lync Server-Systemsteuerung ist "alle Benutzer in Pool verschieben" möglicherweise nicht erwartungsgemäß</span><span class="sxs-lookup"><span data-stu-id="06ecd-490">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="06ecd-491">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-491">**Issue:**</span></span>

<span data-ttu-id="06ecd-492">Wenn Sie die lync Server-Systemsteuerung verwenden, um alle Benutzer von einem Pool in einen anderen Pool in einer komplexen Active Directory-Umgebung zu verschieben, wie etwa eine mit mehreren Domänencontrollern und übergeordneten/untergeordneten Domänen, wird möglicherweise eine Fehlermeldung zurückgegeben, die besagt, dass "angegebene Benutzer kein Legacy Benutzer ist, stattdessen Move-CsUser Cmdlet verwenden".</span><span class="sxs-lookup"><span data-stu-id="06ecd-492">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="06ecd-493">Dies ist ein Ergebnis längerer Replikationszeiten in komplexen Active Directory-Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-493">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="06ecd-494">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-494">**Workaround:**</span></span>

<span data-ttu-id="06ecd-495">Führen Sie eine der folgenden Aktionen aus, um dieses Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="06ecd-495">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="06ecd-496">Verwenden Sie Filter in der lync Server-Systemsteuerung, um nach Legacy Benutzern zu suchen, wählen Sie diese Benutzer aus, und verwenden Sie dann den **Befehl ausgewählte Benutzer in Pool verschieben,** anstatt **alle Benutzer in Pool zu verschieben**.</span><span class="sxs-lookup"><span data-stu-id="06ecd-496">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="06ecd-497">Verwenden Sie die lync Server-Verwaltungsshell, um ältere Benutzer in Batches mithilfe von lync Server-Cmdlets zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="06ecd-497">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="06ecd-498">Die lync Server-Systemsteuerung funktioniert nicht mehr in einer VMware-Umgebung, nachdem das Microsoft Silverlight-Browser-Plug-in auf Version 5 aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="06ecd-498">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="06ecd-499">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-499">**Issue:**</span></span>

<span data-ttu-id="06ecd-500">Wenn Sie die lync Server-Systemsteuerung in einer VMware-Umgebung verwenden, funktioniert die lync Server-Systemsteuerung nach dem Upgrade von Silverlight auf Version 5 möglicherweise nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="06ecd-500">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="06ecd-501">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-501">**Workaround:**</span></span>

<span data-ttu-id="06ecd-502">Führen Sie eine der folgenden Aktionen aus, um dieses Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="06ecd-502">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="06ecd-503">Deinstallieren Sie Silverlight 5, und installieren Sie dann Silverlight 4 aus [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0) .</span><span class="sxs-lookup"><span data-stu-id="06ecd-503">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="06ecd-504">Öffnen Sie die lync Server-Systemsteuerung von einem Computer, auf dem es sich nicht um einen virtuellen VMware-Computer handelt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-504">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="06ecd-505">Wenn Sie die lync Server-Systemsteuerung von einem Remotecomputer aus öffnen möchten, installieren Sie die lync Server-Verwaltungstools auf dem Computer, und starten Sie dann die lync Server-Systemsteuerung über das Windows- **Startmenü** .</span><span class="sxs-lookup"><span data-stu-id="06ecd-505">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="06ecd-506">Sie können die lync Server-Systemsteuerung auch öffnen, indem Sie die URL in einem Webbrowser eingeben.</span><span class="sxs-lookup"><span data-stu-id="06ecd-506">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="06ecd-507">Die URL wird https:///CSCP. ähnlich sein. \<frontend\_pool\_fqdn\></span><span class="sxs-lookup"><span data-stu-id="06ecd-507">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="06ecd-508">Ein Administrator kann das Cmdlet "deinstallieren-csMirrorDB" nach dem Entfernen der Spiegelungsdatenbank im Topologie-Generator nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-508">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="06ecd-509">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-509">**Issue:**</span></span>

<span data-ttu-id="06ecd-510">Wenn ein Administrator eine Spiegelungsdatenbank im Topologie-Generator deaktiviert und dann die Spiegelungsdatenbank im Topologie-Generator löscht, wird eine Meldung in der Aufgabenliste angezeigt, damit der Administrator das Cmdlet " **deinstallieren-csMirrorDatabase** " ausführt, um die Spiegelung von SQL Server zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-510">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="06ecd-511">Wenn der Administrator versucht, das Cmdlet auszuführen, schlägt er fehl.</span><span class="sxs-lookup"><span data-stu-id="06ecd-511">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="06ecd-512">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-512">**Workaround:**</span></span>

<span data-ttu-id="06ecd-513">Um die SQL-Spiegelung eines Pools in Topology Builder zu entfernen, müssen Sie zuerst ein Cmdlet verwenden, um die Spiegelung in SQL Server zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-513">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="06ecd-514">Anschließend können Sie mithilfe des Topologie-Generators den Spiegel aus der Topologie entfernen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-514">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="06ecd-515">Verwenden Sie das folgende Cmdlet, um den Spiegel in SQL Server zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="06ecd-515">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="06ecd-516">Wenn Sie beispielsweise die Spiegelung entfernen und die Datenbanken für die Benutzerdatenbanken löschen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="06ecd-516">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="06ecd-517">Der *DropExistingDatabasesOnMirror* -Parameter bewirkt, dass die betroffenen Datenbanken aus der Spiegelung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-517">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="06ecd-518">Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="06ecd-518">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="06ecd-519">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="06ecd-519">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="06ecd-520">Deaktivieren Sie **SQL Store-Spiegelung aktivieren** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="06ecd-520">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="06ecd-521">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="06ecd-521">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="06ecd-522">Wenn Sie eine Änderung an einer Back-End-Daten Bank Spiegelungs Beziehung vornehmen, müssen Sie alle Front-End-Server im Pool neu starten.</span><span class="sxs-lookup"><span data-stu-id="06ecd-522">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="06ecd-523">Validierungsfehler werden im Topologie-Generator zurückgegeben, wenn ein Administrator versucht, eine Bereitstellung mit einem Front-End-Pool zu entfernen, der einen zugeordneten Zeugen Speicher hat.</span><span class="sxs-lookup"><span data-stu-id="06ecd-523">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="06ecd-524">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-524">**Issue:**</span></span>

<span data-ttu-id="06ecd-525">Wenn ein Administrator versucht, mithilfe des Befehls " **Bereitstellung entfernen** " im Topologie-Generator eine Bereitstellung zu entfernen, die einen Front-End-Pool mit einem zugeordneten Zeugen Speicher enthält, wird im Topologie-Generator ein Validierungsfehler angezeigt, und die Aktion wird nicht fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-525">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="06ecd-526">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-526">**Workaround:**</span></span>

<span data-ttu-id="06ecd-527">Führen Sie eine der folgenden Aktionen aus, um dieses Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="06ecd-527">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="06ecd-528">Entfernen Sie den Zeugen Speicher, bevor Sie versuchen, die Bereitstellung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-528">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="06ecd-529">Fügen Sie einen Zeugen Speicher für den Front-End-Pool hinzu, und entfernen Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="06ecd-529">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="06ecd-530">Bereitstellungsinformationen für beständigen Chat Server sind inkonsistent zwischen dem Planungs Tool und dem Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="06ecd-530">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="06ecd-531">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-531">**Issue:**</span></span>

<span data-ttu-id="06ecd-532">Wenn vom lync Server 2013, Planungs Tool das Website Topologie-Diagramm für eine persistent Chat Server-Bereitstellung mit aktivierter Disaster Recovery-Funktion ausgegeben wird, enthält das Standorttopologie-Diagramm mehrere (physische) Websites mit gleichmäßig zugewiesenen beständigen Chatservern an jedem Standort.</span><span class="sxs-lookup"><span data-stu-id="06ecd-532">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="06ecd-533">Im Topologie-Generator werden alle beständigen Chat Server als einer einzelnen (logischen) Website dargestellt und unter dem gleichen beständigen Chat Server-Poolknoten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-533">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="06ecd-534">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-534">**Workaround:**</span></span>

<span data-ttu-id="06ecd-535">Derzeit gibt es keine Problemumgehung für dieses Problem.</span><span class="sxs-lookup"><span data-stu-id="06ecd-535">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="06ecd-536">Der Benutzer sollte die Ausgabe des Planungstools für die Bereitstellung des beständigen Chat Servers analysieren und den Plan so ändern, dass er seinen spezifischen Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="06ecd-536">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="06ecd-537">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="06ecd-537">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="06ecd-538">Überwachung</span><span class="sxs-lookup"><span data-stu-id="06ecd-538">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="06ecd-539">Der Assistent zum Bereitstellen von Überwachungsberichten zeigt unter bestimmten Umständen falsche Zeichen an, wenn die ostasiatische Version von lync Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-539">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="06ecd-540">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-540">**Issue:**</span></span>

<span data-ttu-id="06ecd-541">Bei Verwendung einer ostasiatischen Version von lync Server 2013 – beispielsweise Chinesisch (vereinfacht), Chinesisch (traditionell), Japanisch oder Koreanisch – unter einem Betriebssystem, bei dem das Systemgebietsschema nicht auf eine ostasiatische Sprache festgesetzt ist, werden im Assistenten zum Bereitstellen von Überwachungsberichten Fragezeichen oder andere Zeichen anstelle lokalisierter Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-541">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="06ecd-542">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-542">**Workaround:**</span></span>

<span data-ttu-id="06ecd-543">Um dieses Problem zu beheben, setzen Sie das Gebietsschema für das Betriebssystem und lync Server 2013 auf die gleiche Sprache, in der alle Nachrichten ordnungsgemäß angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-543">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="06ecd-544">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="06ecd-544">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="06ecd-545">In bestimmten Fällen verschwindet das erste Element in der oberen Navigationsleiste auf einer Seite der lync Server-Systemsteuerung, wenn auf das letzte Element in der oberen Navigationsleiste geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-545">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="06ecd-546">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-546">**Issue:**</span></span>

<span data-ttu-id="06ecd-547">Es gibt drei bekannte Fälle, in denen beim Klicken auf das letzte Element auf der oberen Navigationsleiste auf einer Seite der lync Server-Systemsteuerung das erste Element in der oberen Navigationsleiste ausgeblendet wird:</span><span class="sxs-lookup"><span data-stu-id="06ecd-547">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="06ecd-548">In der Version Französisch auf der Seite "Féderation et accès externe" verschwindet das Element "stratégie accès externe", wenn auf "Partenaires Fédérés XMPP" geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-548">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="06ecd-549">In der deutschen Version wird auf der Seite "Clients" das Element "Clientversionskonfiguration" nicht mehr angezeigt, wenn auf "Pushbenachrichtigungskonfiguration" geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-549">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="06ecd-550">In der russischen Version wird auf der Seite "Конфигурация сети" das Element "Глобально" nicht mehr angezeigt, wenn auf "Маршрут региона" geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="06ecd-550">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="06ecd-551">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-551">**Workaround:**</span></span>

<span data-ttu-id="06ecd-552">Um dieses Problem zu umgehen, aktualisieren Sie die Seite der lync Server-Systemsteuerung in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="06ecd-552">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="06ecd-553">Die Seite wird im Browser geladen, wobei alle Elemente in der oberen Navigationsleiste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-553">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="06ecd-554">Adressbuch</span><span class="sxs-lookup"><span data-stu-id="06ecd-554">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="06ecd-555">Die Indizierung im Adressbuch funktioniert in einigen Sprachen nicht erwartungsgemäß</span><span class="sxs-lookup"><span data-stu-id="06ecd-555">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="06ecd-556">Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server 2013: February 2013.</span><span class="sxs-lookup"><span data-stu-id="06ecd-556">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="06ecd-557">Wenn die Eigenschaften eines Benutzers ein indiziertes Feld enthalten und dieses Feld nur Zeichen enthält, die nicht indiziert werden können, wird der Benutzer nicht in Suchvorgängen angezeigt, die im Adressbuch durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-557">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="06ecd-558">Die folgenden Zeichen und Gebietsschemas können nicht indiziert werden:</span><span class="sxs-lookup"><span data-stu-id="06ecd-558">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="06ecd-559">Großbuchstaben für Kyrillisch, Griechisch und Armenische Zeichen</span><span class="sxs-lookup"><span data-stu-id="06ecd-559">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="06ecd-560">Großbuchstaben mit Akzenten</span><span class="sxs-lookup"><span data-stu-id="06ecd-560">Upper-case accented characters</span></span>

  - <span data-ttu-id="06ecd-561">Thai</span><span class="sxs-lookup"><span data-stu-id="06ecd-561">Thai</span></span>

  - <span data-ttu-id="06ecd-562">Laos</span><span class="sxs-lookup"><span data-stu-id="06ecd-562">Lao</span></span>

  - <span data-ttu-id="06ecd-563">Myanmar</span><span class="sxs-lookup"><span data-stu-id="06ecd-563">Myanmar</span></span>

  - <span data-ttu-id="06ecd-564">Devanagari</span><span class="sxs-lookup"><span data-stu-id="06ecd-564">Devanagari</span></span>

  - <span data-ttu-id="06ecd-565">Äthiopisch</span><span class="sxs-lookup"><span data-stu-id="06ecd-565">Ethiopic</span></span>

  - <span data-ttu-id="06ecd-566">Tibetischen</span><span class="sxs-lookup"><span data-stu-id="06ecd-566">Tibetan</span></span>

  - <span data-ttu-id="06ecd-567">Bengali</span><span class="sxs-lookup"><span data-stu-id="06ecd-567">Bengali</span></span>

  - <span data-ttu-id="06ecd-568">Gujarati</span><span class="sxs-lookup"><span data-stu-id="06ecd-568">Gujarati</span></span>

  - <span data-ttu-id="06ecd-569">Telugu</span><span class="sxs-lookup"><span data-stu-id="06ecd-569">Telugu</span></span>

  - <span data-ttu-id="06ecd-570">Alle anderen indischen Skripts</span><span class="sxs-lookup"><span data-stu-id="06ecd-570">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="06ecd-571">Lync Web App, Web Scheduler und Web Components</span><span class="sxs-lookup"><span data-stu-id="06ecd-571">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="06ecd-572">Sprach-Fallback für bestimmte Sprachen in lync Web Scheduler, Einwahl, Teilnehmer-Startfeld, beständige chatroomverwaltung und OCTab funktionieren möglicherweise nicht erwartungsgemäß</span><span class="sxs-lookup"><span data-stu-id="06ecd-572">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="06ecd-573">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-573">**Issue:**</span></span>

<span data-ttu-id="06ecd-574">Bei der Auswahl eines neutralen Gebietsschemas in einem Webbrowser (in Internet Explorer) so kann beispielsweise der Sprachname ohne weitere Angabe, wie "Norwegisch \[ Nein \] ") statt eines Gebietsschemas, das die Sprache, das Skript und das Gebietsschema angibt (wie "Norwegian, Norwegisch (Norwegen) \[ nb-no \] "), zu einem unerwarteten Anzeigeverhalten für bestimmte Sprachen in lync Web Scheduler, Einwahl-, Start-und OCTab, beständiger chatroomverwaltung führen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-574">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="06ecd-575">Beispielsweise können Benutzer die englische Seite sehen, wenn eine der folgenden Sprachen ausgewählt ist:</span><span class="sxs-lookup"><span data-stu-id="06ecd-575">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="06ecd-576">Norwegisch</span><span class="sxs-lookup"><span data-stu-id="06ecd-576">Norwegian</span></span>

  - <span data-ttu-id="06ecd-577">Portugiesisch</span><span class="sxs-lookup"><span data-stu-id="06ecd-577">Portuguese</span></span>

  - <span data-ttu-id="06ecd-578">Serbisch</span><span class="sxs-lookup"><span data-stu-id="06ecd-578">Serbian</span></span>

<span data-ttu-id="06ecd-579">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-579">**Workaround:**</span></span>

<span data-ttu-id="06ecd-580">Wenn Sie eine Sprache mit einem neutralen Gebietsschema auswählen möchten, stellen Sie immer sicher, dass Sie auch die Sprache mit einem bestimmten Gebietsschema (mit Skript und/oder Landesvorwahl) als zusätzliche Sprache in der Liste der Spracheinstellungen Ihres Browsers hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-580">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="06ecd-581">Bei der Verwendung von lync Web Scheduler, Einwahl, Startfeld-Startprogramm, beständiger chatroomverwaltung und OCTab in einigen Webbrowsern ist die Unterstützung für aserbaidschanische und usbekische Gebietsschemas nur bedingt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="06ecd-581">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="06ecd-582">Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server 2013: February 2013.</span><span class="sxs-lookup"><span data-stu-id="06ecd-582">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="06ecd-583">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-583">**Issue:**</span></span>

<span data-ttu-id="06ecd-584">Wenn Sie Internet Explorer 8 oder Internet Explorer 9 verwenden und die Browsersprache auf Aserbaidschanisch (lateinisch) oder Usbekistan (lateinisch) festlegen, werden die Seiten für Einwahl-und Teilnehmer-Startfeld in englischer Sprache oder in der bevorzugten Sprache angezeigt, die im Browser eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="06ecd-584">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="06ecd-585">Wenn Sie Firefox-oder Chrome-Browser verwenden und die Browsersprache auf Aserbaidschanisch (lateinisch) oder Usbekistan (lateinisch) festlegen, werden lync Web App, lync Web Scheduler und RGS-OCTab in englischer Sprache oder in der bevorzugten Sprache für den Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-585">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="06ecd-586">Das usbekische Gebietsschema wird im Safari-Browser nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-586">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="06ecd-587">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-587">**Workaround:**</span></span>

<span data-ttu-id="06ecd-588">Für diese Probleme gibt es keine Problemumgehung.</span><span class="sxs-lookup"><span data-stu-id="06ecd-588">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="06ecd-589">Der Dropdownpfeil fehlt für die Liste "an Besprechung teilnehmen" in der rumänischen Version von lync Web App.</span><span class="sxs-lookup"><span data-stu-id="06ecd-589">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="06ecd-590">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-590">**Issue:**</span></span>

<span data-ttu-id="06ecd-591">Wenn ein Benutzer, der die rumänische Version von lync Web App verwendet, die folgenden Schritte ausführt, wird der Dropdownpfeil für die Teilnahme an einer **Besprechung** in der Dropdownliste nicht angezeigt:</span><span class="sxs-lookup"><span data-stu-id="06ecd-591">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="06ecd-592">Wählen Sie auf der Registerkarte **Allgemein** auf **diesem Computer speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="06ecd-592">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="06ecd-593">Wählen Sie die Registerkarte **Telefon** .</span><span class="sxs-lookup"><span data-stu-id="06ecd-593">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="06ecd-594">Klicken Sie auf die Dropdownliste für an **Besprechung teilnehmen**.</span><span class="sxs-lookup"><span data-stu-id="06ecd-594">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="06ecd-595">Benutzern wird kein Pfeil angezeigt, der angibt, dass es mehr Optionen als die **lync Web App** gibt, die Folgendes beinhalten: **keine Teilnahme an Audio** (in Rumänisch, "Nu SE asociaža La Componenta Audio") und **neue Nummer**(in rumänischer Sprache, "Număr Nou").</span><span class="sxs-lookup"><span data-stu-id="06ecd-595">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="06ecd-596">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-596">**Workaround:**</span></span>

<span data-ttu-id="06ecd-597">Auch wenn der Pfeil für diese Dropdownliste nicht angezeigt wird, können die Benutzer weiterhin die zusätzlichen Einstellungen in der Liste auswählen, indem Sie auf den Standardwert klicken.</span><span class="sxs-lookup"><span data-stu-id="06ecd-597">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="06ecd-598">Bei Verwendung der türkischen Version von lync Web Scheduler kann eine Besprechung nicht gespeichert werden, wenn die Option "Personen, die ich wähle" unter "Wer ist ein Referent" ist</span><span class="sxs-lookup"><span data-stu-id="06ecd-598">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="06ecd-599">**Problem**</span><span class="sxs-lookup"><span data-stu-id="06ecd-599">**Issue:**</span></span>

<span data-ttu-id="06ecd-600">Wenn Sie eine Besprechung in der türkischen Version des lync Web Scheduler erstellen oder bearbeiten, wird die Option "Personen, die ich wähle" unter "Wer ist ein Referent" nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="06ecd-600">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="06ecd-601">Wenn diese Option ausgewählt ist, kann die Besprechung nicht gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-601">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="06ecd-602">Stattdessen wird eine Fehlermeldung angezeigt, die besagt, dass eine oder mehrere Personen keine Referenten darstellen können.</span><span class="sxs-lookup"><span data-stu-id="06ecd-602">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="06ecd-603">**Workaround**</span><span class="sxs-lookup"><span data-stu-id="06ecd-603">**Workaround:**</span></span>

<span data-ttu-id="06ecd-604">Um dieses Problem zu umgehen, können Benutzer die Standardoption "Personen aus meinem Unternehmen" oder eine beliebige andere Wahl verwenden, beispielsweise "nur Organisator" oder "jeder, einschließlich Personen außerhalb meines Unternehmens".</span><span class="sxs-lookup"><span data-stu-id="06ecd-604">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="06ecd-605">Der Organisator kann später, nachdem er der Besprechung beigetreten ist, Personen zu den richtigen Rollen zurückstufen oder heraufstufen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-605">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="06ecd-606">Alternativ können Benutzer, die eine andere Sprache verstehen, die Sprachauswahl in Ihrem Browser auf eine der anderen 43-unterstützten Sprachen ändern und versuchen, die Option "Personen, die ich wähle" zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-606">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="06ecd-607">Copyright</span><span class="sxs-lookup"><span data-stu-id="06ecd-607">Copyright</span></span>

<span data-ttu-id="06ecd-608">Dieses Dokument unterstützt eine Vorabversion eines Softwareprodukts, das vor der endgültigen kommerziellen Veröffentlichung erheblich geändert werden kann, und ist die vertrauliche und proprietäre Information der Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="06ecd-608">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="06ecd-609">Sie wird gemäß einer Vertraulichkeitsvereinbarung zwischen dem Empfänger und Microsoft veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="06ecd-609">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="06ecd-610">Dieses Dokument wird nur zu Informationszwecken bereitgestellt, und Microsoft übernimmt in diesem Dokument keine Garantien, weder ausdrücklich noch implizit.</span><span class="sxs-lookup"><span data-stu-id="06ecd-610">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="06ecd-611">Die Informationen in diesem Dokument, einschließlich der URL und anderer Verweise auf Internet Websites, können ohne Vorankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-611">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="06ecd-612">Das gesamte Risiko der Nutzung oder der Ergebnisse der Nutzung dieses Dokuments verbleibt beim Nutzer.</span><span class="sxs-lookup"><span data-stu-id="06ecd-612">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="06ecd-613">Sofern nicht anders angegeben, sind die Unternehmen, Organisationen, Produkte, Domänennamen, e-Mail-Adressen, Logos, Personen, Orte und Ereignisse, die in Beispielen hierin dargestellt sind, fiktiv.</span><span class="sxs-lookup"><span data-stu-id="06ecd-613">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="06ecd-614">Keine Assoziation mit einem wirklichen Unternehmen, einer Organisation, einem Produkt, einem Domänennamen, einer e-Mail-Adresse, einem Logo, einer Person, einem Ort oder einem Ereignis ist beabsichtigt oder sollte abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-614">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="06ecd-615">Die Einhaltung aller anwendbaren Urheberrechtsgesetze obliegt dem Nutzer.</span><span class="sxs-lookup"><span data-stu-id="06ecd-615">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="06ecd-616">Ohne die Rechte unter dem Urheberrecht zu begrenzen, darf kein Teil dieses Dokuments reproduziert, gespeichert oder in ein Retrievalsystem aufgenommen oder in irgendeiner Form oder auf andere Weise (elektronisch, mechanisch, Fotokopieren, aufzeichnen oder auf andere Weise) oder zu einem beliebigen Zweck ohne die ausdrückliche schriftliche Genehmigung der Microsoft Corporation übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="06ecd-616">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="06ecd-617">Microsoft hat möglicherweise Patente, Patentanmeldungen, Marken, Urheberrechte oder andere Rechte an geistigem Eigentum, die Inhalte dieses Dokuments abdecken.</span><span class="sxs-lookup"><span data-stu-id="06ecd-617">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="06ecd-618">Sofern nicht ausdrücklich in einem schriftlichen Lizenzvertrag von Microsoft vorgesehen, gibt Ihnen die Einrichtung dieses Dokuments keine Lizenz für diese Patente, Marken, Urheberrechte oder sonstiges geistiges Eigentum.</span><span class="sxs-lookup"><span data-stu-id="06ecd-618">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="06ecd-619">© 2012 Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="06ecd-619">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="06ecd-620">Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="06ecd-620">All rights reserved.</span></span>

<span data-ttu-id="06ecd-621">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook und SQL Server sind entweder eingetragene Marken oder Marken der Microsoft Corporation in den Vereinigten Staaten und/oder anderen Ländern/Regionen.</span><span class="sxs-lookup"><span data-stu-id="06ecd-621">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="06ecd-622">Alle anderen Marken sind Eigentum ihrer jeweiligen Eigentümer.</span><span class="sxs-lookup"><span data-stu-id="06ecd-622">All other trademarks are property of their respective owners.</span></span>

<span data-ttu-id="06ecd-623"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="06ecd-623"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

