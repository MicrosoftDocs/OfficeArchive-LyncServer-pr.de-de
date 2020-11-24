---
title: 'Lync Server 2013: Zusammenfassungsbericht für Peer-zu-Peer-Aktivitäten'
description: 'Lync Server 2013: Zusammenfassungsbericht für Peer-zu-Peer-Aktivitäten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f081f542a5063ed83be470d3e991c58e458b487
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394887"
---
# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="d266b-103">Zusammenfassungsbericht zur Peer-zu-Peer-Aktivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d266b-103">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="d266b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="d266b-104">

<span> </span></span></span>

<span data-ttu-id="d266b-105">_**Letztes Änderungsdatum des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="d266b-105">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="d266b-106">Der zusammenfassende Bericht über Peer-to-Peer-Aktivität bietet eine Übersicht über Peer-to-Peer-Kommunikationssitzungen.</span><span class="sxs-lookup"><span data-stu-id="d266b-106">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="d266b-107">Eine Peer-to-Peer-Sitzung umfasst in der Regel nur zwei Benutzer und erfordert keine Verwendung der lync Server-Konferenzdienste.</span><span class="sxs-lookup"><span data-stu-id="d266b-107">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="d266b-108">Im Vergleich dazu umfasst eine Konferenz in der Regel mehr als zwei Benutzer und erfordert die Verwendung von Microsoft lync Server 2013-Konferenzdiensten.</span><span class="sxs-lookup"><span data-stu-id="d266b-108">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="d266b-109">Konferenzaktivität wird im zusammenfassenden Konferenzbericht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="d266b-109">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="d266b-110">Der zusammenfassende Bericht über Peer-to-Peer-Aktivität hilft Ihnen bei der Beantwortung der folgenden Fragen:</span><span class="sxs-lookup"><span data-stu-id="d266b-110">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="d266b-111">Wie viele Peer-to-Peer-Chatnachrichten senden meine Benutzer an einem normalen Tag?</span><span class="sxs-lookup"><span data-stu-id="d266b-111">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="d266b-112">Nutzen alle meine Benutzer tatsächlich die Vorteile der lync Server-Anwendungsfreigabe und der Dateiübertragungsfunktionen?</span><span class="sxs-lookup"><span data-stu-id="d266b-112">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="d266b-p102">Die Benutzer haben sich darüber beklagt, dass das Netzwerk zu bestimmten Tageszeiten langsam ist. Wie viele Minuten werden in diesen Zeiten für Peer-to-Peer-Audio-/Videositzungen aufgewendet?</span><span class="sxs-lookup"><span data-stu-id="d266b-p102">Users have been complaining that the network seems slow at certain times of the day. How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="d266b-115">Zugriff auf den zusammenfassenden Bericht über Peer-to-Peer-Aktivität</span><span class="sxs-lookup"><span data-stu-id="d266b-115">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="d266b-116">Auf den zusammenfassenden Bericht über Peer-to-Peer-Aktivität greifen Sie über die Startseite für Überwachungsberichte zu.</span><span class="sxs-lookup"><span data-stu-id="d266b-116">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="d266b-117">Sie öffnen den [Peer-zu-Peer-Chat Bericht in lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="d266b-117">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="d266b-118">Peer-to-Peer-Chatsitzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="d266b-118">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="d266b-119">Peer-to-Peer-Chatnachrichten insgesamt</span><span class="sxs-lookup"><span data-stu-id="d266b-119">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="d266b-120">Entsprechend können Sie den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität öffnen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="d266b-120">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="d266b-121">Peer-to-Peer-Audiositzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="d266b-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="d266b-122">Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten</span><span class="sxs-lookup"><span data-stu-id="d266b-122">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="d266b-123">Peer-to-Peer-Audiositzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="d266b-123">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="d266b-124">Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten</span><span class="sxs-lookup"><span data-stu-id="d266b-124">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="d266b-125">Optimale Nutzung des zusammenfassenden Berichts über Peer-to-Peer-Aktivität</span><span class="sxs-lookup"><span data-stu-id="d266b-125">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="d266b-p104">Im unteren Bereich des zusammenfassenden Berichts über Peer-to-Peer-Aktivität finden Sie Gesamtwerte für Metriken wie z. B. „Peer-to-Peer-Chatsitzungen insgesamt“ und „Peer-to-Peer-Chatnachrichten insgesamt“. Dies ermöglicht einen schnellen Überblick über die detaillierten Informationen im eigentlichen Bericht.</span><span class="sxs-lookup"><span data-stu-id="d266b-p104">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages. This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d266b-128">Filter</span><span class="sxs-lookup"><span data-stu-id="d266b-128">Filters</span></span>

<span data-ttu-id="d266b-p105">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Mit dem zusammenfassenden Bericht über Peer-to-Peer-Aktivität können Sie beispielsweise wählen, wie Daten gruppiert werden sollen. In diesem Fall werden die Aktivitäten nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="d266b-p105">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped. In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="d266b-132">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im zusammenfassenden Bericht über Peer-to-Peer-Aktivität verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d266b-132">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="d266b-133">Filter im zusammenfassenden Bericht über Peer-to-Peer-Aktivität</span><span class="sxs-lookup"><span data-stu-id="d266b-133">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d266b-134">Name</span><span class="sxs-lookup"><span data-stu-id="d266b-134">Name</span></span></th>
<th><span data-ttu-id="d266b-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d266b-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d266b-136"><strong>Von</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-136"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-p106">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="d266b-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d266b-139">7/17/12012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="d266b-139">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="d266b-p107">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="d266b-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d266b-142">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="d266b-142">7/17/12012</span></span></p>
<p><span data-ttu-id="d266b-143">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="d266b-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d266b-144">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="d266b-144">7/13/2012</span></span></p>
<p><span data-ttu-id="d266b-145">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="d266b-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d266b-146"><strong>Bis</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-146"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-p108">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="d266b-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d266b-149">7/17/12012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="d266b-149">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="d266b-p109">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="d266b-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d266b-152">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="d266b-152">7/17/12012</span></span></p>
<p><span data-ttu-id="d266b-153">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="d266b-153">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d266b-154">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="d266b-154">7/13/2012</span></span></p>
<p><span data-ttu-id="d266b-155">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="d266b-155">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d266b-156"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-156"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-p110">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="d266b-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d266b-159">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="d266b-159">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d266b-160">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="d266b-160">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d266b-161">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="d266b-161">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d266b-162">Monatlich (maximal 12 Monate können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="d266b-162">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="d266b-163">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d266b-163">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="d266b-164">Wenn Sie beispielsweise das Tagesintervall mit einem Anfangstermin von 7/17/12012 und einem Enddatum von 2/28/2012 auswählen, werden die Daten für die Tage 8/7/12012 12:00 Uhr bis 9/7/12012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="d266b-164">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d266b-165">Metriken</span><span class="sxs-lookup"><span data-stu-id="d266b-165">Metrics</span></span>

<span data-ttu-id="d266b-166">In der folgenden Tabelle werden Metriken aufgelistet, die im zusammenfassenden Bericht über Peer-to-Peer-Aktivität angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d266b-166">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="d266b-167">Metriken im zusammenfassenden Bericht über Peer-to-Peer-Aktivität</span><span class="sxs-lookup"><span data-stu-id="d266b-167">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d266b-168">Name</span><span class="sxs-lookup"><span data-stu-id="d266b-168">Name</span></span></th>
<th><span data-ttu-id="d266b-169">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="d266b-169">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d266b-170">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d266b-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d266b-171"><strong>Stündlich</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-171"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="d266b-172"><strong>Täglich</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-172"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="d266b-173"><strong>Wöchentlich</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-173"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="d266b-174"><strong>Monatlich</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-174"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-175">Nein</span><span class="sxs-lookup"><span data-stu-id="d266b-175">No</span></span></p></td>
<td><p><span data-ttu-id="d266b-176">Gibt das auf der Filtersymbolleiste gewählte Zeitintervall an.</span><span class="sxs-lookup"><span data-stu-id="d266b-176">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="d266b-177">Sie können gegebenenfalls auf ein bestimmtes Zeitintervall klicken, um ausführliche Informationen zu diesem Intervall anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d266b-177">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="d266b-178">Wenn Sie beispielsweise das Tagesintervall verwenden und auf 7/17/12012 klicken, wird eine stündliche Aufschlüsselung der Benutzer Registrierungs Aktivität für dieses Datum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d266b-178">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d266b-179"><strong>Peer-to-Peer-Sitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-179"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-180">Nein</span><span class="sxs-lookup"><span data-stu-id="d266b-180">No</span></span></p></td>
<td><p><span data-ttu-id="d266b-181">Gesamtanzahl der abgehaltenen Peer-to-Peer-Sitzungen, unabhängig vom Sitzungstyp.</span><span class="sxs-lookup"><span data-stu-id="d266b-181">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d266b-182"><strong>Peer-to-Peer-Chatsitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-182"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-183">Nein</span><span class="sxs-lookup"><span data-stu-id="d266b-183">No</span></span></p></td>
<td><p><span data-ttu-id="d266b-p113">Gesamtanzahl der Peer-to-Peer-Chatnachrichtensitzungen. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Chatnachrichten für den gewählten Zeitraum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d266b-p113">Total number of peer-to-peer instant messaging (IM) sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d266b-186"><strong>Peer-to-Peer-Chatnachrichten insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-186"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-187">Nein</span><span class="sxs-lookup"><span data-stu-id="d266b-187">No</span></span></p></td>
<td><p><span data-ttu-id="d266b-p114">Gesamtanzahl der in Peer-to-Peer-Sitzungen gesendeten Chatnachrichten. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Chatnachrichten für den gewählten Zeitraum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d266b-p114">Total number of instant messages sent in peer-to-peer sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d266b-190"><strong>Peer-to-Peer-Audiositzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-190"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-191">Nein</span><span class="sxs-lookup"><span data-stu-id="d266b-191">No</span></span></p></td>
<td><p><span data-ttu-id="d266b-p115">Gesamtanzahl der Peer-to-Peer-Audioanrufe. Wenn Sie auf dieses Feld klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d266b-p115">Total number of peer-to-peer audio calls. When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d266b-194"><strong>Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-194"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-195">Nein</span><span class="sxs-lookup"><span data-stu-id="d266b-195">No</span></span></p></td>
<td><p><span data-ttu-id="d266b-196">Gesamtdauer der Peer-to-Peer-Audiositzungen.</span><span class="sxs-lookup"><span data-stu-id="d266b-196">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="d266b-197">Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d266b-197">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d266b-198"><strong>Durchschnittliche Dauer der Peer-to-Peer-Audiositzung in Minuten</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-198"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-199">Nein</span><span class="sxs-lookup"><span data-stu-id="d266b-199">No</span></span></p></td>
<td><p><span data-ttu-id="d266b-p117">Durchschnittliche Dauer einer Peer-to-Peer-Audiositzung. Wird errechnet, indem die Gesamtdauer der Audiositzungen durch die Gesamtanzahl der Audiositzungen geteilt wird.</span><span class="sxs-lookup"><span data-stu-id="d266b-p117">Average amount of time spent in peer-to-peer audio sessions. Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d266b-202"><strong>Peer-to-Peer-Videositzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-202"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-203">Nein</span><span class="sxs-lookup"><span data-stu-id="d266b-203">No</span></span></p></td>
<td><p><span data-ttu-id="d266b-p118">Gesamtanzahl der Peer-to-Peer-Videoanrufe. Beachten Sie, dass Videositzungen auch als Audiositzungen zählen; jede Videositzung zählt als eine Videositzung und eine Audiositzung. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d266b-p118">Total number of peer-to-peer video calls. Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d266b-207"><strong>Gesamtdauer der Peer-to-Peer-Videositzung in Minuten</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-207"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-208">Nein</span><span class="sxs-lookup"><span data-stu-id="d266b-208">No</span></span></p></td>
<td><p><span data-ttu-id="d266b-p119">Gesamtdauer der Peer-to-Peer-Videositzungen. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d266b-p119">Total amount of time spent in peer-to-peer video sessions. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d266b-211"><strong>Durchschnittliche Dauer der Peer-to-Peer-Videositzung in Minuten</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-211"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-212">Nein</span><span class="sxs-lookup"><span data-stu-id="d266b-212">No</span></span></p></td>
<td><p><span data-ttu-id="d266b-p120">Durchschnittliche Dauer einer Peer-to-Peer-Videositzung. Wird errechnet, indem die Gesamtdauer der Videositzungen durch die Gesamtanzahl der Videositzungen geteilt wird.</span><span class="sxs-lookup"><span data-stu-id="d266b-p120">Average amount of time spent in peer-to-peer video sessions. Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d266b-215"><strong>Peer-to-Peer-Dateiübertragungssitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-215"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-216">Nein</span><span class="sxs-lookup"><span data-stu-id="d266b-216">No</span></span></p></td>
<td><p><span data-ttu-id="d266b-217">Gesamtanzahl der Peer-to-Peer-Sitzungen mit Dateiübertragungen.</span><span class="sxs-lookup"><span data-stu-id="d266b-217">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d266b-218"><strong>Peer-to-Peer-Anwendungsfreigabesitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="d266b-218"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d266b-219">Nein</span><span class="sxs-lookup"><span data-stu-id="d266b-219">No</span></span></p></td>
<td><p><span data-ttu-id="d266b-220">Gesamtanzahl der Peer-to-Peer-Sitzungen mit Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="d266b-220">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table><span data-ttu-id="d266b-221">


</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="d266b-221">


</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

