---
title: 'Lync Server 2013: Überprüfen der trunk-Konfiguration für eine Telefonnummer'
description: 'Lync Server 2013: Überprüfen der trunk-Konfiguration für eine Telefonnummer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cdfe1a2a9c5c87310ad561464960c5a01fea7b5
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49434984"
---
# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>Überprüfen der trunk-Konfiguration für eine Telefonnummer in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Überprüfungszeitplan</p></td>
<td><p>Monatlich</p></td>
</tr>
<tr class="even">
<td><p>Test Tool</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Erforderliche Berechtigungen</p></td>
<td><p>Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</p>
<p>Bei der Ausführung mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsTrunkConfiguration-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

SIP-Trunks verbinden das interne lync Server Enterprise-VoIP-Netzwerk mit einer der folgenden Optionen:

  - Das öffentlich geschaltete Telefonnetz (PSTN).

  - Eine IP-Public Branch Exchange (PBX).

  - Ein Session Border Controller (SBC).

Das Test-CsTrunkConfiguration-Cmdlet überprüft, ob eine Telefonnummer (wie von einem Benutzer gewählt) in das E. 164-Netzwerk konvertiert und über einen angegebenen SIP-Stamm weitergeleitet werden kann.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Zum Ausführen des Test-CsTrunkConfiguration-Cmdlets müssen Sie zuerst das Cmdlet Get-CsTrunkConfiguration verwenden, um eine Instanz Ihrer SIP-Trunk-Konfigurationseinstellungen abzurufen. Diese Instanz wird dann an Test-CsTrunkConfiguration umgeleitet:

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Das Ausführen von Test-CsTrunkConfiguration, ohne zuerst Get-CsTrunkConfiguration auszuführen, funktioniert nicht. Dieser Befehl schlägt beispielsweise fehl, ohne dass Daten zurückgegeben werden:

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

Wenn Sie über mehrere Sammlungen von SIP Trunk-Konfigurationseinstellungen verfügen, können Sie einen Befehl wie den folgenden verwenden, um gleichzeitig jede Sammlung mit derselben Telefonnummer zu testen:

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Weitere Informationen finden Sie in der Hilfedokumentation für das Cmdlet "Test-CsTrunkConfiguration".

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn Test-CsTrunkConfiguration einen Anruf an die gewählte Nummer tätigen kann, wird die übersetzte Rufnummer (im E. 164-Format) und die für die Übersetzung dieser Rufnummer verwendete Regel auf dem Bildschirm angezeigt:

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219 Global/Redmond

Wenn der Test fehlschlägt, gibt Test-CsTrunkConfiguration leere Eigenschaftswerte zurück:

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn Test-CsTrunkConfiguration keine Übereinstimmung zurückgibt, die in der Regel bedeutet, dass die zu testende trunk-Konfigurationseinstellungen keine Übersetzungen für ausgehende Rufnummern enthalten, die in der Lage sind, die gewählte Nummer in das E. 164-Format umzuwandeln. Um die Übersetzungsregeln abzurufen, die einer Sammlung von trunk-Konfigurationseinstellungen zugewiesen wurden, können Sie eine Syntax verwenden, die der folgenden ähnelt:

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

Damit werden für jede Übersetzungsregel ähnliche Informationen zurückgegeben:

Beschreibung: Telefonnummern ohne Landesvorwahl oder Ortsvorwahl.

Muster: ^ \\ + ( \\ d \* ) $

`Translation : $1`

Name: NoAreaCode

An diesem Punkt überprüfen Sie den Wert der Pattern-Eigenschaft (die eine [reguläre Ausdrucks](https://go.microsoft.com/fwlink/?linkid=400464) Zeichenfolge ist), um festzustellen, ob eine der Übersetzungsregeln für die Behandlung der gewählten Nummer konfiguriert ist. Wenn dies nicht der Fall ist, müssen Sie entweder eine der vorhandenen Regeln ("CsOutboundTranslationRule") ändern oder das New-CsOutboundTranslationRule-Cmdlet verwenden, um der Sammlung eine neue Regel hinzuzufügen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

