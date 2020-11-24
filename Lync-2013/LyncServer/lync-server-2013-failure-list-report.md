---
title: 'Lync Server 2013: fehlerlistenbericht'
description: 'Lync Server 2013: fehlerlistenbericht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7467144fe207ab61fd086cd35aac74779fd4f771
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49393979"
---
# <a name="failure-list-report-in-lync-server-2013"></a>Bericht zur Fehlerliste in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-07-02_

Der Fehlerlistenbericht enthält ausführliche Informationen über die einzelnen Teilnehmer, die an einer fehlerhaften Peer-to-Peer-Sitzung oder Konferenzsitzung beteiligt waren. Diese Informationen umfassen den URI des Benutzers, bei dem das Problem aufgetreten ist, sowie den SIP-Antwortcode und die Diagnose-ID, die dem Fehler zugeordnet sind.

<div>

## <a name="accessing-the-failure-list-report"></a>Zugriff auf den Fehlerlistenbericht

Auf den Bericht Fehlerliste wird zugegriffen, indem Sie auf eine der folgenden Metriken im [Fehler Verteilungs Bericht in lync Server 2013](lync-server-2013-failure-distribution-report.md)klicken:

  - Wichtigste Diagnosegründe (Sitzungen)

  - Wichtigste Modalitäten (Sitzungen)

  - Wichtigste Pools (Sitzungen)

  - Wichtigste Quellen (Sitzungen)

  - Wichtigste Komponenten (Sitzungen)

  - Wichtigste Absenderbenutzer (Sitzungen)

  - Wichtigste Empfängerbenutzer (Sitzungen)

  - Wichtigste Absenderbenutzer-Agenten (Sitzungen)

Im Bericht Fehlerliste können Sie auf den [Bericht Peer-to-Peer-Sitzungsdetails in lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) zugreifen, indem Sie auf die Sitzungs Detail Metrik für eine Peer-to-Peer-Sitzung klicken. Sie können ebenfalls auf den detaillierten Konferenzbericht zugreifen, indem Sie auf die Konferenzmetrik für eine Konferenz klicken.

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>Bestmögliche Verwendung des Fehlerlistenberichts

Im Fehlerlistenbericht können Sie eine Beschreibung für jeden Antwortcode bzw. jede Diagnose-ID sehen, indem Sie einfach den Mauszeiger über diesen Wert halten. Wenn Sie zum Beispiel Ihre Maus über die Diagnose-ID 7025 halten, wird in einer QuickInfo folgender Text angezeigt:

Interner Serverfehler erstellt Medien für Benutzer.

Dabei muss beachtet werden, dass der Fehlerlistenbericht weder eine einfache Methode zum direkten Abrufen einer Liste aller Benutzer, die an mindestens einer fehlerhaften Sitzung beteiligt waren, noch eine Methode zur Ermittlung der Benutzer, die am häufigsten an einer fehlerhaften Sitzung beteiligt waren, darstellt. (Zum einen hat der fehlerlistenbericht keine Filterfunktionen.) Wenn Sie die Daten exportieren und dann in eine Datei mit Komma getrennten Werten konvertieren, können Sie Windows PowerShell verwenden, um Antworten auf Fragen wie diese zu finden. Nehmen Sie beispielsweise an, dass Sie die Daten in a speichern. CSV-Datei mit dem Namen C: \\ Daten \\ Fehler \_List.csv. Auf Basis der in dieser Datei gespeicherten Daten können mithilfe dieses Befehls alle Benutzer aufgelistet werden, die an mindestens einer fehlerhaften Sitzung beteiligt waren:

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

Die Ausgabe für den Befehl ist eine Liste, die der folgenden Liste ähnelt:

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

Diese beiden Befehle melden die Gesamtzahl der fehlerhaften Sitzungen zurück, an denen Benutzer beteiligt waren:

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a>Filter

Keine. Sie können den Fehlerlistenbericht nicht filtern.

</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die im Fehlerlistenbericht enthaltenen Informationen für jeden fehlerhaften Anruf aufgeführt.

### <a name="failure-list-report-metrics"></a>Metriken des Fehlerlistenberichts

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Kann nach dieser Metrik sortiert werden?</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Gemeldeter Zeitpunkt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit der Aufzeichnung des Berichts.</p></td>
</tr>
<tr class="even">
<td><p><strong>Anforderung</strong></p></td>
<td><p>Nein</p></td>
<td><p>Typ der fehlerhaften SIP-Anforderung. Beispiel: INVITE oder BYE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Antwortcode</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Antwortcode, der bei einem Konferenzfehler gesendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Nein</p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Beitrittszeitraum (ms)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitraum (in Millisekunden), der erforderlich ist, damit der Benutzer der Konferenz beitreten kann.</p></td>
</tr>
<tr class="even">
<td><p><strong>Absenderbenutzer</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die SIP-Adresse des Benutzers, der den Anruf initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Von Benutzeragent</strong></p></td>
<td><p>Nein</p></td>
<td><p>Software, die vom Endpunkt des Benutzers, der den Anruf initiiert hat, verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>An Benutzer</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Adresse des Benutzers, der angerufen wurde.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

