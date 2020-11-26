---
title: Lync Server 2013-Benutzererfahrung beim Pool Fehler
description: Lync Server 2013-Benutzererfahrung während des Pool Fehlers.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0483a01b643d8195e7f8f6259c11ab6fc3561f2
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49440780"
---
# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="29bdb-103">Benutzererfahrung beim Pool Fehler in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29bdb-103">User experience during pool failure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="29bdb-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="29bdb-104">

<span> </span></span></span>

<span data-ttu-id="29bdb-105">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="29bdb-105">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="29bdb-106">Wenn ein Pool fehlerhaft ist, müssen sich alle Benutzer des betroffenen Pools abmelden und sich dann beim Sicherungspool anmelden.</span><span class="sxs-lookup"><span data-stu-id="29bdb-106">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="29bdb-107">Für einen kurzen Zeitraum befinden sich die Benutzer, die sich am Sicherungspool anmelden, möglicherweise im Ausfallsicherheitsmodus.</span><span class="sxs-lookup"><span data-stu-id="29bdb-107">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="29bdb-108">Im Resilienz-Modus können Benutzer keine Aufgaben ausführen, die zu einer dauerhaften Änderung auf lync Server führen, wie etwa das Hinzufügen eines Kontakts.</span><span class="sxs-lookup"><span data-stu-id="29bdb-108">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="29bdb-109">Nachdem das Failover abgeschlossen wurde, können alle Benutzer alle Dienste vom Sicherungspool beziehen.</span><span class="sxs-lookup"><span data-stu-id="29bdb-109">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="29bdb-110">Alle Sitzungen, die ein Benutzer hat, wenn der Pool ausfällt, werden gestört, und der Benutzer muss diese Sitzungen nach einem Failover erneut einrichten, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="29bdb-110">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="29bdb-111">Benutzer werden während eines Failovers oder Failbacks nicht verlagert.</span><span class="sxs-lookup"><span data-stu-id="29bdb-111">Users are not rehomed during failover or failback.</span></span> <span data-ttu-id="29bdb-112">Benutzer, die auf einem ausfallenden Pool verwaltet werden, werden temporär durch den Sicherungspool verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="29bdb-112">Users who are homed on a pool that fails will be temporarily serviced by the backup pool.</span></span> <span data-ttu-id="29bdb-113">Wenn der Home-Pool wiederhergestellt wird, kann der Administrator diese Benutzer zurückschlagen, um von Ihrem ursprünglichen privaten Pool gewartet zu werden.</span><span class="sxs-lookup"><span data-stu-id="29bdb-113">When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="29bdb-114">Hinweis in lync 2013 wird die Standort Informations Server-Datenbank nicht in den Sicherungspool repliziert.</span><span class="sxs-lookup"><span data-stu-id="29bdb-114">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="29bdb-115">Als bewährte Vorgehensweise sollte der Administrator die LIS-Datenbank regelmäßig sichern und die neueste Sicherungskopie verwenden, um die LIS-Datenbank im Sicherungspool nach dem Failover wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="29bdb-115">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="29bdb-116">Benutzerfreundlichkeit während eines Failovers</span><span class="sxs-lookup"><span data-stu-id="29bdb-116">User Experience During Failover</span></span>

<span data-ttu-id="29bdb-117">Wenn sich ein Benutzer in einem Pool befindet, der fehlschlägt, wird der Benutzer abgemeldet. Jede Peer-to-Peer-Sitzung, an der der Benutzer teilgenommen hat, wird beendet, ebenso wie Konferenzen, die von diesem Benutzer organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="29bdb-117">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user.</span></span> <span data-ttu-id="29bdb-118">Der Benutzer kann sich nicht wieder anmelden, bis entweder der Registrierungsausfallsicherheits-Zeitgeber abläuft oder der Administrator Failoverprozeduren initiiert, was auch immer zuerst eintritt.</span><span class="sxs-lookup"><span data-stu-id="29bdb-118">The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first.</span></span> <span data-ttu-id="29bdb-119">Wenn sich Benutzer wieder anmelden, werden sie im Sicherungspool angemeldet.</span><span class="sxs-lookup"><span data-stu-id="29bdb-119">When the user logs back in, they will log in to the backup pool.</span></span> <span data-ttu-id="29bdb-120">Wenn sie sich vor Abschluss des Failovers anmelden, befinden sie sich im Ausfallsicherheitsmodus, bis das Failover abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="29bdb-120">If they log in before the failover has completed, they will be in Resiliency mode until failover is complete.</span></span> <span data-ttu-id="29bdb-121">Nur dann kann der Benutzer neue Sitzungen einrichten oder frühere Sitzungen wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="29bdb-121">Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="29bdb-122">Benutzerfreundlichkeit während des Failback</span><span class="sxs-lookup"><span data-stu-id="29bdb-122">User Experience During Failback</span></span>

<span data-ttu-id="29bdb-123">Pool-Failbacks können auftreten, wenn der betroffene Benutzer während des Failbacks weiterhin an einem Sicherungspool angemeldet ist und arbeitet.</span><span class="sxs-lookup"><span data-stu-id="29bdb-123">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback.</span></span> <span data-ttu-id="29bdb-124">Beachten Sie, dass der Failback-Vorgang mehrere Minuten in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="29bdb-124">Note that the failback process takes several minute to complete.</span></span>  <span data-ttu-id="29bdb-125">Zur Orientierung: Erwartungsgemäß dauert dies bei einem Pool mit 20.000 Benutzern bis zu 60 Minuten.</span><span class="sxs-lookup"><span data-stu-id="29bdb-125">For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="29bdb-126">In den folgenden Tabellen werden weitere Details dazu angezeigt, wie ein Benutzer mit einem lync 2013-Client oder einem Microsoft lync 2010-Client während und nach dem Failback betroffen ist, und wie Benutzer in anderen Pools einen Benutzer in einem Pool sehen und mit ihm interagieren, der wieder fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="29bdb-126">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="29bdb-127">Benutzer mit Microsoft Office Communicator 2007 R2-Clients können sich erst anmelden, wenn der Front-End-Pool komplett Fehler zurück ist.)</span><span class="sxs-lookup"><span data-stu-id="29bdb-127">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="29bdb-128">Der Begriff *betroffener Benutzer* bezieht sich auf sämtliche Benutzer, bei denen ein Failover im Home-Pool aufgetreten ist und die daher vom Sicherungspool verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="29bdb-128">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool.</span></span> <span data-ttu-id="29bdb-129">Definitionsgemäß ist jeder Benutzer, der ursprünglich im Sicherungspool beheimatet ist, kein betroffener Benutzer.</span><span class="sxs-lookup"><span data-stu-id="29bdb-129">By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="29bdb-130">Benutzererfahrung eines betroffenen Benutzers bei einem Pool in Failback</span><span class="sxs-lookup"><span data-stu-id="29bdb-130">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29bdb-131">Benutzerstatus oder -aufgabe</span><span class="sxs-lookup"><span data-stu-id="29bdb-131">User state or task</span></span></th>
<th><span data-ttu-id="29bdb-132">Während des Failbacks</span><span class="sxs-lookup"><span data-stu-id="29bdb-132">During failback</span></span></th>
<th><span data-ttu-id="29bdb-133">Nach abgeschlossenem Failback</span><span class="sxs-lookup"><span data-stu-id="29bdb-133">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29bdb-134">Benutzerstatus des bereits angemeldeten Benutzers</span><span class="sxs-lookup"><span data-stu-id="29bdb-134">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="29bdb-p108">Benutzer bleibt angemeldet und mit dem Sicherungspool verbunden. Zu einem gewissen Punkt wird der Benutzer abgemeldet und wieder im ursprünglichen Home-Pool angemeldet, und zwar im Ausfallsicherheitsmodus.</span><span class="sxs-lookup"><span data-stu-id="29bdb-p108">User stays signed in and connected to backup pool. At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="29bdb-137">Benutzer bleibt angemeldet und wechselt in den regulären Modus.</span><span class="sxs-lookup"><span data-stu-id="29bdb-137">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29bdb-138">Neuer Benutzer meldet sich an.</span><span class="sxs-lookup"><span data-stu-id="29bdb-138">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="29bdb-139">Benutzer können sich am Home-Pool im Ausfallsicherheitsmodus anmelden.</span><span class="sxs-lookup"><span data-stu-id="29bdb-139">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="29bdb-140">Benutzer können sich am ursprünglichen Home-Pool im regulären Modus anmelden.</span><span class="sxs-lookup"><span data-stu-id="29bdb-140">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29bdb-141">Von betroffenen Benutzern organisierte laufende Konferenzen</span><span class="sxs-lookup"><span data-stu-id="29bdb-141">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="29bdb-p109">Alle Modalitäten der Konferenz werden abgebrochen. Die Schaltfläche zum erneuten Teilnehmen wird angezeigt. Benutzer können jedoch nicht erneut teilnehmen, während sich der betroffene Benutzer im Ausfallsicherheitsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="29bdb-p109">All modalities of conference are terminated. Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="29bdb-p110">Alle Modalitäten funktionieren nun. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="29bdb-p110">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29bdb-146">Von nicht betroffenen Benutzern organisierte laufende Konferenzen</span><span class="sxs-lookup"><span data-stu-id="29bdb-146">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="29bdb-p111">Die Konferenz wird weiterhin ausgeführt und der betroffene Benutzer kann in der Konferenz verbleiben. Der betroffene Benutzer ist auf die Aktionen beschränkt, die er im Ausfallsicherheitsmodus ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="29bdb-p111">Conference continues and affected user can stay in the conference. Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="29bdb-149">Die Konferenz wird weiterhin ausgeführt und der betroffene Benutzer kann in der Konferenz verbleiben. Zudem funktionieren alle Modalitäten, nachdem der Benutzer den Ausfallsicherheitsmodus verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="29bdb-149">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29bdb-150">Planen oder Ändern von geplanten Änderungen, Erstellen von Ad-hoc-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="29bdb-150">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="29bdb-151">Nicht möglich, während sich der Benutzer im Ausfallsicherheitsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="29bdb-151">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="29bdb-152">Für alle Modalitäten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="29bdb-152">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29bdb-153">Anwesenheit, wie sie von anderen Benutzern im selben Pool gesehen wird</span><span class="sxs-lookup"><span data-stu-id="29bdb-153">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="29bdb-154">Die Anwesenheit ist unbekannt, während der Benutzer am Sicherungspool während des Ausfallsicherheitsmodus angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="29bdb-154">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="29bdb-155">Zeigt den letzten vom Benutzer festgelegten Anwesenheitsstatus. Anwesenheitsänderungen werden nun reflektiert.</span><span class="sxs-lookup"><span data-stu-id="29bdb-155">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29bdb-156">Verfügbarkeit von Kontaktlisten und Adressbuchdienst</span><span class="sxs-lookup"><span data-stu-id="29bdb-156">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="29bdb-157">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="29bdb-157">Not available</span></span></p></td>
<td><p><span data-ttu-id="29bdb-158">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="29bdb-158">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29bdb-159">Alle Peer-zu-Peer-Sitzungen und -modalitäten</span><span class="sxs-lookup"><span data-stu-id="29bdb-159">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="29bdb-160">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="29bdb-160">Available</span></span></p></td>
<td><p><span data-ttu-id="29bdb-161">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="29bdb-161">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="29bdb-162">Benutzererfahrung mit einem verwalteten Benutzer in einem nicht betroffenen Pool während eines Failbacks eines anderen Pools</span><span class="sxs-lookup"><span data-stu-id="29bdb-162">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29bdb-163">Benutzeraufgabe</span><span class="sxs-lookup"><span data-stu-id="29bdb-163">User task</span></span></th>
<th><span data-ttu-id="29bdb-164">Während des Failbacks</span><span class="sxs-lookup"><span data-stu-id="29bdb-164">During failback</span></span></th>
<th><span data-ttu-id="29bdb-165">Nach abgeschlossenem Failback</span><span class="sxs-lookup"><span data-stu-id="29bdb-165">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29bdb-166">Anwesenheitsinformationen des betroffenen Benutzers anzeigen</span><span class="sxs-lookup"><span data-stu-id="29bdb-166">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="29bdb-167">Zeigt den letzten vom betroffenen Benutzer festgelegten Anwesenheitsstatus an.</span><span class="sxs-lookup"><span data-stu-id="29bdb-167">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="29bdb-p112">In Bearbeitung. Nicht betroffene Benutzer sehen Updates, die von betroffenen Benutzern vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="29bdb-p112">Working. Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29bdb-170">Von betroffenen Benutzern organisierte laufende Konferenzen</span><span class="sxs-lookup"><span data-stu-id="29bdb-170">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="29bdb-171">Alle Modalitäten der Konferenz werden abgebrochen</span><span class="sxs-lookup"><span data-stu-id="29bdb-171">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="29bdb-p113">Alle Modalitäten funktionieren nun. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="29bdb-p113">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29bdb-174">Von nicht betroffenen Benutzern organisierte laufende Konferenzen</span><span class="sxs-lookup"><span data-stu-id="29bdb-174">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="29bdb-175">Die Konferenz wird weiterhin ausgeführt, der betroffene Benutzer kann in der Konferenz verbleiben und alle Modalitäten funktionieren.</span><span class="sxs-lookup"><span data-stu-id="29bdb-175">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="29bdb-176">Die Konferenz wird weiterhin ausgeführt, der betroffene Benutzer kann in der Konferenz verbleiben und alle Modalitäten funktionieren.</span><span class="sxs-lookup"><span data-stu-id="29bdb-176">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29bdb-177">Alle Peer-zu-Peer-Sitzungen und -modalitäten</span><span class="sxs-lookup"><span data-stu-id="29bdb-177">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="29bdb-178">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="29bdb-178">Available</span></span></p></td>
<td><p><span data-ttu-id="29bdb-179">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="29bdb-179">Available</span></span></p></td>
</tr>
</tbody>
</table><span data-ttu-id="29bdb-180">


</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="29bdb-180">


</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

