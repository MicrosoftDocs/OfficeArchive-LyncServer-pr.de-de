---
title: 'Lync Server 2013: Zusammenfassungsbericht zur PSTN-Konferenz'
description: 'Lync Server 2013: PSTN-Konferenz Zusammenfassungsbericht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3bc468e494577c229562a1cb7cfddaf839f946f
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49436727"
---
# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="e0b88-103">Bericht zur PSTN-Konferenz Zusammenfassung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0b88-103">PSTN Conference Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="e0b88-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="e0b88-104">

<span> </span></span></span>

<span data-ttu-id="e0b88-105">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="e0b88-105">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e0b88-106">In Microsoft lync Server 2013 ist eine PSTN-Konferenz eine Konferenz, bei der sich mindestens ein Teilnehmer über ein PSTN-Telefon (Public Switched Telephone Network) in den Audioteil einwählt.</span><span class="sxs-lookup"><span data-stu-id="e0b88-106">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="e0b88-107">(Bei einem PSTN-Telefon handelt es sich um ein Festnetztelefon, ein Mobiltelefon oder ein anderes Telefon, das keine VoIP-Nutzung durchführt.) Obwohl Sie in den Überwachungsberichten als PSTN-Konferenzen bezeichnet werden, werden diese Konferenzen vielleicht häufiger als Einwahlkonferenzen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e0b88-107">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="e0b88-p102">Der „Zusammenfassende Bericht über PSTN-Konferenzen“ liefert Informationen zu allen in Ihrer Organisation durchgeführten PSTN-Konferenzen (das sind alle Konferenzen mit mindestens einem Einwahlbenutzer). Der Bericht enthält Informationen zur Gesamtanzahl der PSTN-Konferenzen, der Gesamtanzahl der Teilnehmer an diesen Konferenzen und vielleicht als wichtigste Information, die Gesamtanzahl der Einwahlbenutzer (Metrik der PSTN-Teilnehmer insgesamt).</span><span class="sxs-lookup"><span data-stu-id="e0b88-p102">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user). The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="e0b88-110">Zugreifen auf den „Zusammenfassenden Bericht über PSTN-Konferenzen“</span><span class="sxs-lookup"><span data-stu-id="e0b88-110">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="e0b88-p103">Auf der Startseite „Überwachungsberichte“ können Sie auf den „Zusammenfassenden Bericht über PSTN-Konferenzen“ zugreifen. Dieser Bericht ist nicht mit anderen Berichten verknüpft. Beachten Sie, dass Sie keine ausführlichen Anrufinformationen für eine PSTN-Konferenz abrufen können. Als teilweise Erklärung hierfür kann angeführt werden, dass die einzelnen Endpunkte für die Übertragung dieser Informationen verantwortlich sind. PSTN-Telefone können keine ausführlichen Anrufinformationen nachverfolgen oder übertragen.</span><span class="sxs-lookup"><span data-stu-id="e0b88-p103">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page. This report is not linked to any other reports. Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information. PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="e0b88-115">Optimale Nutzung des „Zusammenfassenden Berichts über PSTN-Konferenzen“</span><span class="sxs-lookup"><span data-stu-id="e0b88-115">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="e0b88-116">Um den Prozentsatz aller ihrer Konferenzen zu ermitteln, die Benutzer von Einwahl Benutzern einbeziehen, vergleichen Sie den Wert der Gesamt Metrik für PSTN-Konferenzen mit der Gesamtzahl der Konferenzen, die im [Bericht Konferenz Zusammenfassung in lync Server 2013](lync-server-2013-conference-summary-report.md)zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="e0b88-116">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="e0b88-117">Wenn Sie nicht so viele PSTN-Konferenzen sehen, wie Sie vielleicht erwartet hätten, sollten Sie Bedenken, dass die Möglichkeit zum Organisieren einer Konferenz, die Einwahlbenutzer ermöglicht, von der konferenzrichtlinie abhängt, die einem Benutzer zugewiesen wurde: Wenn nur wenige ihrer Benutzer PSTN-Konferenzen durchführen dürfen, sehen Sie offensichtlich nur sehr wenige PSTN-Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="e0b88-117">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences.</span></span> <span data-ttu-id="e0b88-118">Sie können schnell überprüfen, welche ihrer Konferenzrichtlinien (sofern vorhanden) es Benutzern ermöglichen, PSTN-Konferenzen zu planen, indem Sie den folgenden Befehl in der lync Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="e0b88-118">You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="e0b88-119">Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:</span><span class="sxs-lookup"><span data-stu-id="e0b88-119">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="e0b88-120">Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:</span><span class="sxs-lookup"><span data-stu-id="e0b88-120">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e0b88-121">Filter</span><span class="sxs-lookup"><span data-stu-id="e0b88-121">Filters</span></span>

<span data-ttu-id="e0b88-122">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e0b88-122">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="e0b88-123">Beispielsweise können Sie im zusammenfassenden Bericht über PSTN-Konferenz festlegen, wie Daten gruppiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e0b88-123">For example, the PSTN Conference Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="e0b88-124">In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="e0b88-124">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="e0b88-125">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Bericht über PSTN-Konferenz verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e0b88-125">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="e0b88-126">Filter im Zusammenfassenden Bericht über PSTN-Konferenz</span><span class="sxs-lookup"><span data-stu-id="e0b88-126">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0b88-127">Name</span><span class="sxs-lookup"><span data-stu-id="e0b88-127">Name</span></span></th>
<th><span data-ttu-id="e0b88-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0b88-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0b88-129"><strong>Von</strong></span><span class="sxs-lookup"><span data-stu-id="e0b88-129"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e0b88-p106">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="e0b88-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e0b88-132">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="e0b88-132">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e0b88-p107">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="e0b88-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e0b88-135">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e0b88-135">7/7/2012</span></span></p>
<p><span data-ttu-id="e0b88-136">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="e0b88-136">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e0b88-137">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e0b88-137">7/3/2012</span></span></p>
<p><span data-ttu-id="e0b88-138">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="e0b88-138">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0b88-139"><strong>Bis</strong></span><span class="sxs-lookup"><span data-stu-id="e0b88-139"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e0b88-p108">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="e0b88-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e0b88-142">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="e0b88-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e0b88-p109">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="e0b88-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e0b88-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e0b88-145">7/7/2012</span></span></p>
<p><span data-ttu-id="e0b88-146">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="e0b88-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e0b88-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e0b88-147">7/3/2012</span></span></p>
<p><span data-ttu-id="e0b88-148">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="e0b88-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0b88-149"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="e0b88-149"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="e0b88-p110">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="e0b88-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e0b88-152">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="e0b88-152">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e0b88-153">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="e0b88-153">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e0b88-154">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="e0b88-154">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e0b88-155">Monatlich (maximal 12 Monate können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="e0b88-155">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="e0b88-156">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e0b88-156">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="e0b88-157">Wenn Sie beispielsweise das Tagesintervall mit einem Anfangstermin von 7/7/2012 und einem Enddatum von 2/28/2012 auswählen, werden die Daten für die Tage 8/7/2012 12:00 Uhr bis 9/7/2012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="e0b88-157">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e0b88-158">Metriken</span><span class="sxs-lookup"><span data-stu-id="e0b88-158">Metrics</span></span>

<span data-ttu-id="e0b88-159">In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Bericht über PSTN-Konferenz angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e0b88-159">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="e0b88-160">Metriken im Zusammenfassenden Bericht über PSTN-Konferenz</span><span class="sxs-lookup"><span data-stu-id="e0b88-160">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0b88-161">Name</span><span class="sxs-lookup"><span data-stu-id="e0b88-161">Name</span></span></th>
<th><span data-ttu-id="e0b88-162">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="e0b88-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e0b88-163">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0b88-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0b88-164"><strong>Stündlich</strong></span><span class="sxs-lookup"><span data-stu-id="e0b88-164"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="e0b88-165"><strong>Täglich</strong></span><span class="sxs-lookup"><span data-stu-id="e0b88-165"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="e0b88-166"><strong>Wöchentlich</strong></span><span class="sxs-lookup"><span data-stu-id="e0b88-166"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="e0b88-167"><strong>Monatlich</strong></span><span class="sxs-lookup"><span data-stu-id="e0b88-167"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="e0b88-168">Nein</span><span class="sxs-lookup"><span data-stu-id="e0b88-168">No</span></span></p></td>
<td><p><span data-ttu-id="e0b88-169">Gibt das ausgewählte Zeitintervall an.</span><span class="sxs-lookup"><span data-stu-id="e0b88-169">Indicates the selected time interval.</span></span> <span data-ttu-id="e0b88-170">Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e0b88-170">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="e0b88-171">Wenn Sie beispielsweise das Tagesintervall verwenden und auf 7/7/2012 klicken, wird eine stündliche Aufschlüsselung der Benutzer Registrierungs Aktivität für dieses Datum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e0b88-171">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0b88-172"><strong>PSTN-Konferenzen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="e0b88-172"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="e0b88-173">Nein</span><span class="sxs-lookup"><span data-stu-id="e0b88-173">No</span></span></p></td>
<td><p><span data-ttu-id="e0b88-174">Die Gesamtzahl der Konferenzen, die Zugriff per Einwahl erlaubten.</span><span class="sxs-lookup"><span data-stu-id="e0b88-174">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0b88-175"><strong>Teilnehmer insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="e0b88-175"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="e0b88-176">Nein</span><span class="sxs-lookup"><span data-stu-id="e0b88-176">No</span></span></p></td>
<td><p><span data-ttu-id="e0b88-177">Die Gesamtzahl der Personen, die an Konferenzen mit Einwahlzugriff teilnahmen.</span><span class="sxs-lookup"><span data-stu-id="e0b88-177">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0b88-178"><strong>Gesamtdauer der A/V-Konferenzen in Minuten</strong></span><span class="sxs-lookup"><span data-stu-id="e0b88-178"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="e0b88-179">Nein</span><span class="sxs-lookup"><span data-stu-id="e0b88-179">No</span></span></p></td>
<td><p><span data-ttu-id="e0b88-180">Die Gesamtdauer von Konferenzen mit Audio oder Video.</span><span class="sxs-lookup"><span data-stu-id="e0b88-180">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0b88-181"><strong>Gesamtdauer (in Minuten), die Teilnehmer in der A/V-Konferenz verbleiben</strong></span><span class="sxs-lookup"><span data-stu-id="e0b88-181"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="e0b88-182">Nein</span><span class="sxs-lookup"><span data-stu-id="e0b88-182">No</span></span></p></td>
<td><p><span data-ttu-id="e0b88-p113">Die Gesamtdauer, die Teilnehmer in Konferenzen mit Audio bzw. Video verbrachten. Beispiel: Angenommen, ein Teilnehmer hat 5 Minuten in einer A/V-Konferenz verbracht und ein zweiter Benutzer war 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 8 Minuten.</span><span class="sxs-lookup"><span data-stu-id="e0b88-p113">Total amount of audio/visual participant time. For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0b88-185"><strong>PSTN-Teilnehmer insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="e0b88-185"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="e0b88-186">Nein</span><span class="sxs-lookup"><span data-stu-id="e0b88-186">No</span></span></p></td>
<td><p><span data-ttu-id="e0b88-187">Die Gesamtzahl der Benutzer, die sich in Konferenzen einwählten, die Zugriff per Einwahl erlaubten.</span><span class="sxs-lookup"><span data-stu-id="e0b88-187">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0b88-188"><strong>PSTN-Teilnehmerminuten insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="e0b88-188"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="e0b88-189">Nein</span><span class="sxs-lookup"><span data-stu-id="e0b88-189">No</span></span></p></td>
<td><p><span data-ttu-id="e0b88-p114">Die Gesamtdauer, die Einwahlbenutzer in Konferenzen verbrachten. Beispiel: Angenommen, ein Einwahlteilnehmer hat 5 Minuten in einer Konferenz verbracht und ein zweiter Teilnehmer war 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 8 Minuten.</span><span class="sxs-lookup"><span data-stu-id="e0b88-p114">Total amount of conference time spent by dial-in users. For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0b88-192"><strong>Eindeutige Konferenzorganisatoren</strong></span><span class="sxs-lookup"><span data-stu-id="e0b88-192"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="e0b88-193">Nein</span><span class="sxs-lookup"><span data-stu-id="e0b88-193">No</span></span></p></td>
<td><p><span data-ttu-id="e0b88-p115">Die Gesamtzahl der Benutzer, die mindestens eine Konferenz mit Einwahlzugriff organisiert haben. Benutzer, die mehr als eine Konferenz organisiert haben, zählen als ein eindeutiger Organisator, genauso wie Benutzer, die nur eine einzige Konferenz organisiert haben.</span><span class="sxs-lookup"><span data-stu-id="e0b88-p115">Total number of users who organized at least one conference that allowed dial-in access. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table><span data-ttu-id="e0b88-196">


</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="e0b88-196">


</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

