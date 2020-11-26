---
title: 'Lync Server 2013: Testen der Monitor Knoten Konfiguration'
description: 'Lync Server 2013: Test Watcher-Knoten Konfiguration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1eeb141eee011d7e06f5dd49e483e026484d733
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49440927"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>Testen der Monitor Knoten Konfiguration in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-11-03_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Überprüfungszeitplan</p></td>
<td><p>Täglich</p></td>
</tr>
<tr class="even">
<td><p>Test Tool</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Erforderliche Berechtigungen</p></td>
<td><p>Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</p>
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsWatcherNodeConfiguration-</strong> Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Wenn Sie Microsoft System Center Operations Manager zum Überwachen von lync Server 2013 verwenden, haben Sie die Möglichkeit, "Watcher-Knoten" einzurichten: Computer, die regelmäßig und automatisch synthetische Transaktionen ausführen, um zu überprüfen, ob lync Server wie erwartet funktioniert. Watcher-Knoten werden Pools zugewiesen und mithilfe der **CsWatcherNodeConfiguration** -Cmdlets verwaltet. Beachten Sie, dass Sie keine Watcher-Knoten installieren müssen, wenn Sie System Center Operations Manager verwenden. Sie können Ihr System weiterhin überwachen, ohne Watcher-Knoten zu verwenden. Der einzige Unterschied besteht darin, dass alle synthetischen Transaktionen, die Sie ausführen möchten, manuell aufgerufen werden müssen, anstatt von Operations Manager automatisch aufgerufen zu werden.

Mit dem Cmdlet **Test-CsWatcherNodeConfiguration** können Sie überprüfen, ob ein Watcher-Knoten ordnungsgemäß konfiguriert wurde und einem gültigen lync Server 2013-Pool zugewiesen ist. Beachten Sie, dass das Cmdlet **Test-CsWatcherNodeConfiguration** auf dem Watcher-Knoten selbst ausgeführt werden muss. Das Cmdlet kann nicht für Remotecomputer ausgeführt werden.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Mit dem folgenden Befehl werden die Konfigurationseinstellungen für jeden Watcher-Knoten überprüft, der in der Organisation verwendet wird.

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Die folgende erfolgreiche Beispielausgabe zeigt ein System mit vier Edge-Servern.

Überprüfen des ATL-CS-001.litwareinc.com des Ziel Pools gegen Topologie.

Erfolg: Ziel Pool-ATL-CS-001.litwareinc.com ist in der Topologie vorhanden.

Erfolg: Ziel Pool ATL-CS-001.litwareinc.com hat die Registrierungsstelle Rolle installiert.

Erfolg: Ziel Pool-ATL-CS-001.litwareinc.com wird unterstützt.

Erfolgreich: Port Nummer für 5061 Ziel Pool ATL-CS-001.litwareinc.com ist richtig.

Das Überprüfen auf fehlende Pools in Watcher-Knoten Konfiguration wird gestartet. Wenn ein Fehler erkannt wird, wird er gedruckt.

Das Überprüfen auf fehlende Pools in Watcher-Knoten Konfiguration ist nicht mehr erfolgreich.

Die Überprüfung auf die Registrierungsschlüssel für Watcher-Knoten, die von Watcher-Knoten Installation erstellt wurden, wird gestartet. Wenn ein Fehler erkannt wird, wird er gedruckt.

Die Überprüfung der Registrierungsschlüssel für Watcher-Knoten, die von Watcher-Knoten Installation erstellt wurden, ist zu Ende. Der erkannte Authentifizierungstyp ist Negotiate.

Das vorhanden sein der Anmeldeinformationen des Testbenutzers wurde erfolgreich überprüft SIP: user1@ ATL-CS-001.litwareinc.com im Anmelde Informations Verwaltungsspeicher.

Das vorhanden sein der Anmeldeinformationen des Testbenutzers wurde erfolgreich überprüft SIP: User2@ ATL-CS-001.litwareinc.com im Anmelde Informations Verwaltungsspeicher.

Das Überprüfen auf fehlende Pools in Watcher-Knoten Konfiguration wird gestartet. Wenn ein Fehler erkannt wird, wird er gedruckt.

Warnung: Pool ATL-CS-001.litwareinc.com hat die Registrierungsstelle

Rolle installiert, aber es sind keine Testbenutzer konfiguriert.

Das Überprüfen auf fehlende Pools in Watcher-Knoten Konfiguration ist nicht mehr erfolgreich.

Überprüfen der Registrierungsschlüssel für Watcher-Knoten, die von Watcher-Knoten Installation erstellt wurden

begann. Wenn ein Fehler erkannt wird, wird er gedruckt.

Test-CsWatcherNodeConfiguration: der Integritäts Registrierungsschlüssel kann nicht gefunden werden

Software \\ Microsoft \\ -Echtzeitkommunikation. Stellen Sie sicher, dass Watcher Node. msi

ordnungsgemäß installiert.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsWatcherNodeConfiguration** möglicherweise fehlschlägt:

  - Watcher-Knoten ist nicht ordnungsgemäß installiert.

  - Es sind keine Testbenutzer konfiguriert.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[New-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[Remove-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[Set-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

