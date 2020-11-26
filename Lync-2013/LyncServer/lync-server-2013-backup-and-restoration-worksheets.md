---
title: 'Lync Server 2013: Arbeitsblätter zum Sichern und Wiederherstellen'
description: 'Lync Server 2013: Arbeitsblätter zum Sichern und wiederherstellen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1713e291ae7132cc96309fa499bd97bf7f4f5016
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437959"
---
# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="19807-103">Arbeitsblätter zum Sichern und Wiederherstellen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19807-103">Backup and restoration worksheets for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="19807-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="19807-104">

<span> </span></span></span>

<span data-ttu-id="19807-105">_**Letztes Änderungsdatum des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="19807-105">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="19807-106">Der Sicherungs-und Wiederherstellungsplan für Ihre Organisation sollte Details dazu enthalten, wie und wann Sie Daten und Einstellungen sichern.</span><span class="sxs-lookup"><span data-stu-id="19807-106">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="19807-107">Sie können die hier vorgestellten Arbeitsblätter dazu verwenden, diese Informationen für Ihre spezifische Bereitstellung und für die Sicherungs-und Wiederherstellungsanforderungen Ihrer Organisation zu dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="19807-107">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="19807-108">Verwenden Sie die folgenden Arbeitsblätter zum Aufzeichnen der Informationen, die Sie zum Sichern und Wiederherstellen von Datenbank-, Dateispeicher-und Einstellungsinformationen für einen lync Server-Pool oder Standard Edition-Server benötigen.</span><span class="sxs-lookup"><span data-stu-id="19807-108">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="19807-109">Bewahren Sie eine oder mehrere Kopien dieser Arbeitsblätter an einem sicheren Ort auf, damit Sie leicht zugänglich sind, wenn Sie lync Server wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="19807-109">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19807-110">Die Arbeitsblätter in diesem Abschnitt beziehen sich nur auf die Informationen, die erforderlich sind, um die Daten und Einstellungen der lync Server-Datenbanken und-Server wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="19807-110">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="19807-111">Wenn Sie andere Wiederherstellungsinformationen wie die Informationen zum erneuten Installieren von Betriebssystemen und anderer Software dokumentieren müssen, verwenden Sie die Bereitstellungspläne und Sicherungs-und Wiederherstellungspläne Ihrer Organisation, um diese Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="19807-111">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="19807-112">Arbeitsblatt für Datenbanksicherung und-Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="19807-112">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="19807-113">Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen von lync Server-Datenbanken benötigen.</span><span class="sxs-lookup"><span data-stu-id="19807-113">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="19807-114">Datenbankinformationen für Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="19807-114">Database Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19807-115">Datenbank</span><span class="sxs-lookup"><span data-stu-id="19807-115">Database</span></span></th>
<th><span data-ttu-id="19807-116">Server Name (FQDN)</span><span class="sxs-lookup"><span data-stu-id="19807-116">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="19807-117">Sicherungszeitplan</span><span class="sxs-lookup"><span data-stu-id="19807-117">Backup schedule</span></span></th>
<th><span data-ttu-id="19807-118">Datenbanksicherungstool</span><span class="sxs-lookup"><span data-stu-id="19807-118">Database backup tool</span></span></th>
<th><span data-ttu-id="19807-119">Sicherungssatz</span><span class="sxs-lookup"><span data-stu-id="19807-119">Backup set</span></span></th>
<th><span data-ttu-id="19807-120">Backup-Ziel</span><span class="sxs-lookup"><span data-stu-id="19807-120">Backup destination</span></span></th>
<th><span data-ttu-id="19807-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19807-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19807-122">RTC-Datenbank auf dem Back-End-Server für Benutzerdaten</span><span class="sxs-lookup"><span data-stu-id="19807-122">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="19807-123"><strong>Export-CsUserData-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="19807-123"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="19807-124">Namen</span><span class="sxs-lookup"><span data-stu-id="19807-124">Name:</span></span></p>
<p><span data-ttu-id="19807-125">Ablauf</span><span class="sxs-lookup"><span data-stu-id="19807-125">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19807-126">LcsLog (Standardname)-Datenbank auf dem Archivierungsdaten Bankserver</span><span class="sxs-lookup"><span data-stu-id="19807-126">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="19807-127">SQL Server-Verwaltungstool</span><span class="sxs-lookup"><span data-stu-id="19807-127">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="19807-128">Namen</span><span class="sxs-lookup"><span data-stu-id="19807-128">Name:</span></span></p>
<p><span data-ttu-id="19807-129">Ablauf</span><span class="sxs-lookup"><span data-stu-id="19807-129">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19807-130">LcsCdr-Datenbank zum Überwachen des Datenbankservers für Anruf Detaildatensätze (CDRs)</span><span class="sxs-lookup"><span data-stu-id="19807-130">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="19807-131">SQL Server-Verwaltungstool</span><span class="sxs-lookup"><span data-stu-id="19807-131">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="19807-132">Namen</span><span class="sxs-lookup"><span data-stu-id="19807-132">Name:</span></span></p>
<p><span data-ttu-id="19807-133">Ablauf</span><span class="sxs-lookup"><span data-stu-id="19807-133">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19807-134">Datenbank QoEMetrics werden-Datenbank zum Überwachen des Datenbankservers für QoE-Daten (Quality of Experience)</span><span class="sxs-lookup"><span data-stu-id="19807-134">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="19807-135">SQL Server-Verwaltungstool</span><span class="sxs-lookup"><span data-stu-id="19807-135">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="19807-136">Namen</span><span class="sxs-lookup"><span data-stu-id="19807-136">Name:</span></span></p>
<p><span data-ttu-id="19807-137">Ablauf</span><span class="sxs-lookup"><span data-stu-id="19807-137">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19807-138">Datenbank für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="19807-138">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="19807-139">SQL Server-Verwaltungstool oder <strong>Export-CsPersistentChatData-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="19807-139">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="19807-140">Namen</span><span class="sxs-lookup"><span data-stu-id="19807-140">Name:</span></span></p>
<p><span data-ttu-id="19807-141">Ablauf</span><span class="sxs-lookup"><span data-stu-id="19807-141">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="19807-142">Für die folgenden Datenbanken ist keine Sicherung oder Wiederherstellung erforderlich:</span><span class="sxs-lookup"><span data-stu-id="19807-142">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="19807-143">RTCDyn.</span><span class="sxs-lookup"><span data-stu-id="19807-143">Rtcdyn.</span></span> <span data-ttu-id="19807-144">Die flüchtigen Benutzerdaten in dieser Datenbank sind für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="19807-144">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="19807-145">RTCAb.</span><span class="sxs-lookup"><span data-stu-id="19807-145">Rtcab.</span></span> <span data-ttu-id="19807-146">Die Adressbuchdatenbank wird automatisch aus der globalen Adressliste (Global Address List, GAL) in den Active Directory-Domänendiensten neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="19807-146">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="19807-147">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="19807-147">Rgsdyn.</span></span> <span data-ttu-id="19807-148">Die Daten in dieser Datenbank für transiente Reaktionsgruppen Dienste sind für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="19807-148">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="19807-149">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="19807-149">Cpsdyn.</span></span> <span data-ttu-id="19807-150">Die dynamischen Informationen für die Anwendung für den Parken von Anrufen sind für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="19807-150">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="19807-151">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="19807-151">MgcComp.</span></span> <span data-ttu-id="19807-152">Die Kompatibilitätsdatenbank für beständigen Chat ist für die Wiederherstellung des Diensts nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="19807-152">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="19807-153">Arbeitsblatt zum Sichern und Wiederherstellen von Datei speichern</span><span class="sxs-lookup"><span data-stu-id="19807-153">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="19807-154">Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen der Dateispeicher benötigen.</span><span class="sxs-lookup"><span data-stu-id="19807-154">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="19807-155">Dateispeicher enthalten Daten wie Metadaten für Besprechungsinhalte, Besprechung von Kompatibilitäts Protokollen, Aktualisierungsprotokolle für Geräte Updates und Audiodateien für die Reaktionsgruppe, den Anruf Park und Ankündigungs Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="19807-155">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="19807-156">Dateispeicher Informationen für Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="19807-156">File Store Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19807-157">Inhalt</span><span class="sxs-lookup"><span data-stu-id="19807-157">Content</span></span></th>
<th><span data-ttu-id="19807-158">Server Name (FQDN)</span><span class="sxs-lookup"><span data-stu-id="19807-158">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="19807-159">Sicherungszeitplan</span><span class="sxs-lookup"><span data-stu-id="19807-159">Backup schedule</span></span></th>
<th><span data-ttu-id="19807-160">Dateisystem-Sicherungstool</span><span class="sxs-lookup"><span data-stu-id="19807-160">File system backup tool</span></span></th>
<th><span data-ttu-id="19807-161">Zu sichernde Dateifreigabe \*</span><span class="sxs-lookup"><span data-stu-id="19807-161">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="19807-162">Backup-Ziel</span><span class="sxs-lookup"><span data-stu-id="19807-162">Backup destination</span></span></th>
<th><span data-ttu-id="19807-163">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19807-163">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19807-164">Lync Server-Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="19807-164">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="19807-165">Standard Sicherungstool wie Robocopy</span><span class="sxs-lookup"><span data-stu-id="19807-165">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="19807-166">Auf Dateiserver für Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="19807-166">On file server for Enterprise Edition.</span></span> <span data-ttu-id="19807-167">Standardmäßig für die Standard Edition-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="19807-167">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="19807-168">In der Regel eine pro Website.</span><span class="sxs-lookup"><span data-stu-id="19807-168">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="19807-169">Dateien mit dem Namen " <strong>Meeting. Active</strong> " sollten nicht gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="19807-169">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="19807-170">Diese Dateien werden verwendet und sind gesperrt, während eine Besprechung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="19807-170">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="19807-171">Arbeitsblatt ' Sicherungs-und Wiederherstellungseinstellungen '</span><span class="sxs-lookup"><span data-stu-id="19807-171">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="19807-172">Verwenden Sie die folgende Tabelle, um die Informationen aufzuzeichnen, die Sie zum Sichern und Wiederherstellen von Einstellungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="19807-172">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="19807-173">Einstellungsinformationen für Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="19807-173">Settings Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19807-174">Datenbank</span><span class="sxs-lookup"><span data-stu-id="19807-174">Database</span></span></th>
<th><span data-ttu-id="19807-175">Server Name (FQDN)</span><span class="sxs-lookup"><span data-stu-id="19807-175">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="19807-176">Sicherungszeitplan</span><span class="sxs-lookup"><span data-stu-id="19807-176">Backup schedule</span></span></th>
<th><span data-ttu-id="19807-177">Sicherungstool</span><span class="sxs-lookup"><span data-stu-id="19807-177">Backup tool</span></span></th>
<th><span data-ttu-id="19807-178">Konfigurationsdatei-Name (XML)</span><span class="sxs-lookup"><span data-stu-id="19807-178">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="19807-179">Sicherungsspeicherort</span><span class="sxs-lookup"><span data-stu-id="19807-179">Backup location</span></span></th>
<th><span data-ttu-id="19807-180">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19807-180">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19807-181">XDS-Datenbank im zentralen Verwaltungsspeicher für Topologie-Konfiguration (Global)</span><span class="sxs-lookup"><span data-stu-id="19807-181">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="19807-182"><strong>Export-CsConfiguration-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="19807-182"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19807-183">LIS-Datenbank im zentralen Verwaltungsspeicher für E9-1-1-Standortinformationen (Global)</span><span class="sxs-lookup"><span data-stu-id="19807-183">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="19807-184"><strong>Export-CsLisConfiguration-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="19807-184"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19807-185">RgsConfig-Datenbank auf dem Back-End-Server für die Konfiguration der Reaktionsgruppe (Pool)</span><span class="sxs-lookup"><span data-stu-id="19807-185">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="19807-186"><strong>Export-CsRgsConfiguration-</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="19807-186"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table><span data-ttu-id="19807-187">


</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="19807-187">


</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

