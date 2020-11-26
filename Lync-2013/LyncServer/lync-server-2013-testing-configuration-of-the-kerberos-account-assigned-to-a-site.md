---
title: Testen der Konfiguration des einem Standort zugewiesenen Kerberos-Kontos
description: Testen der Konfiguration des einem Standort zugewiesenen Kerberos-Kontos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eab1618474a19753a4c6064d59aa4f8a856fceb
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49441067"
---
# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>Testen der Konfiguration des einem Standort zugewiesenen Kerberos-Kontos in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-06-05_


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
<p>Bei der Ausführung mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsKerberosAccountAssignment-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Test-CsKerberosAccountAssignment-Cmdlet können Sie überprüfen, ob ein Kerberos-Konto einer bestimmten Website zugeordnet ist, ob dieses Konto ordnungsgemäß konfiguriert ist und ob das Konto wie erwartet funktioniert. Kerberos-Konten sind Computerkonten, die als Authentifizierungs Prinzipal für alle Computer in einer Website fungieren können, auf denen Internet Information Server (IIS) ausgeführt wird. Da diese Konten das Kerberos-Authentifizierungsprotokoll verwenden, werden die Konten als Kerberos-Konten bezeichnet, und der neue Authentifizierungsprozess wird als Kerberos-Webauthentifizierung bezeichnet. Auf diese Weise können Sie alle IIS-Server mithilfe eines einzelnen Kontos verwalten.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Standardmäßig werden Test-CsKerberosAccountAssignment auf dem Bildschirm nur sehr wenig ausgegeben. Stattdessen werden vom Cmdlet zurückgegebene Informationen in eine HTML-Datei geschrieben. Aus diesem Grund empfehlen wir, dass Sie den Verbose-Parameter und den Berichtsparameter jederzeit einfügen, wenn Sie Test-CsKerberosAccountAssignment ausführen. Der Verbose-Parameter bietet eine etwas detailliertere Ausgabe auf dem Bildschirm, während das Cmdlet ausgeführt wird. Mit dem Parameter Report können Sie einen Dateipfad und einen Dateinamen für die von Test-CsKerberosAccountAssignment generierte HTML-Datei angeben. Wenn Sie den Berichtsparameter nicht angeben, wird die HTML-Datei automatisch in Ihrem Ordner "Benutzer" gespeichert, und Sie erhalten einen ähnlichen Namen wie den folgenden: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.

Sie müssen auch eine Websiteidentität angeben, wenn Sie Test-CsKerberosAccountAssignment ausführen. Kerberos-Konten werden im Website Bereich zugewiesen.

Der folgende Befehl führt Test-CsKerberosAccountAssignment und speichert die Ausgabe in einer Datei mit dem Namen C: \\ Logs \\KerberosTest.html:

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Das Test-CsKerberosAccountAssignment-Cmdlet gibt keinen einfachen Hinweis auf Erfolg oder Fehler zurück. Stattdessen müssen Sie die generierte HTML-Datei mit Internet Explorer anzeigen.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden finden Sie einige häufige Gründe, warum Test-CsKerberosAccountAssignment fehlschlagen kann:

  - Sie haben möglicherweise eine falsche Websiteidentität angegeben. Wenn Sie eine Liste der gültigen Websiteidentität zurückgeben möchten, verwenden Sie diesen Befehl:
    
        Get-CsSite | Select-Identity Identity
    
    Eine Websiteidentität sieht in der Regel wie folgt aus:
    
    Website: Redmond

  - Der angegebenen Website ist möglicherweise kein Kerberos-Konto zugewiesen. Sie können feststellen, ob einem Standort ein Kerberos-Konto zugewiesen ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - Ihr Kerberos-Konto hat möglicherweise ein Kennwort, das nicht gültig ist. Wenn die folgende Fehlermeldung im Bericht angezeigt wird, müssen Sie wahrscheinlich das Kennwort für das Kerberos-Konto zurücksetzen:
    
    InvalidKerberosConfiguration: die Kerberos-Konfiguration ist ungültig.
    
    InvalidKerberosConfiguration: die Kerberos-Konfiguration für ATL-cs001.litwareinc.com ist ungültig. Das erwartete zugewiesene Konto ist "litwareinc \\ kerberostest. Stellen Sie sicher, dass das Konto nicht abgelaufen ist und das konfigurierte Kennwort auf dem Computer dem Active Directory-Kennwort des Kontos entspricht.
    
    Sie können das Kennwort mit dem Cmdlet " [Satz-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) " festlegen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

