---
title: 'Lync Server 2013: Testen der Benutzerverbindung mit Exchange um'
description: 'Lync Server 2013: Testen der Benutzerverbindung mit Exchange um.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea6f7d446fe3fd98db67bab4ffee9cc976202689
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49440934"
---
# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="bbc5d-103">Testen der Benutzerverbindung mit Exchange um in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbc5d-103">Testing user connection to Exchange UM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="bbc5d-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="bbc5d-104">

<span> </span></span></span>

<span data-ttu-id="bbc5d-105">_**Letztes Änderungsdatum des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="bbc5d-105">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bbc5d-106">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="bbc5d-106">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bbc5d-107">Täglich</span><span class="sxs-lookup"><span data-stu-id="bbc5d-107">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbc5d-108">Test Tool</span><span class="sxs-lookup"><span data-stu-id="bbc5d-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bbc5d-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc5d-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbc5d-110">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bbc5d-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bbc5d-111">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bbc5d-112">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsExUMConnectivity-</strong> Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="bbc5d-113">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="bbc5d-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bbc5d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bbc5d-114">Description</span></span>

<span data-ttu-id="bbc5d-115">Das Cmdlet **Test-CsExUMConnectivity** überprüft, ob der angegebene Benutzer eine Verbindung mit dem Microsoft Exchange Server 2013 Unified Messaging-Dienst herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-115">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="bbc5d-116">Beachten Sie, dass dieses Cmdlet nur überprüft, ob eine Verbindung mit dem Dienst hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-116">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="bbc5d-117">Der Dienst selbst wird nicht getestet.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-117">It does not test the service itself.</span></span> <span data-ttu-id="bbc5d-118">Verwenden Sie zum Testen des Unified Messaging-Diensts (durch Ausführen eines synthetischen Transaktions-Cmdlets, das eine Voicemail-Nachricht im Postfach eines Benutzers verlässt) das Test-CsExUMVoiceMail-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-118">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bbc5d-119">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="bbc5d-119">Running the test</span></span>

<span data-ttu-id="bbc5d-120">Im folgenden Beispiel wird die Exchange Unified Messaging-Konnektivität für den Pool ATL-CS-001.litwareinc.com getestet.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-120">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="bbc5d-121">Dieser Befehl funktioniert nur, wenn Testbenutzer für den Pool ATL-CS-001.litwareinc.com definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-121">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="bbc5d-122">Wenn ja, bestimmt der Befehl, ob der erste Testbenutzer eine Verbindung mit Unified Messaging herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-122">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="bbc5d-123">Wenn Testbenutzer nicht für den Pool konfiguriert wurden, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-123">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="bbc5d-124">Die im folgenden Beispiel gezeigten Befehle testen die Exchange Unified Messaging-Konnektivität für den Benutzer "litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-124">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="bbc5d-125">Dazu wird im ersten Befehl im Beispiel das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Befehlszeilenschnittstellen-Anmeldeinformationsobjekt für den Benutzer "litwareinc kenmyer zu erstellen \\ .</span><span class="sxs-lookup"><span data-stu-id="bbc5d-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="bbc5d-126">Beachten Sie, dass Sie das Kennwort für dieses Konto angeben müssen, um ein gültiges Anmeldeinformationsobjekt zu erstellen und sicherzustellen, dass das **Test-CsExUMConnectivity-** Cmdlet seine Überprüfung ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-126">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="bbc5d-127">Der zweite Befehl im Beispiel verwendet das angegebene Credentials-Objekt ($x) und die SIP-Adresse des Benutzers "litwareinc \\ kenmyer, um zu ermitteln, ob dieser Benutzer eine Verbindung mit Exchange Unified Messaging herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="bbc5d-128">Der im nächsten Beispiel angezeigte Befehl ist eine Variation des soeben gezeigten Befehls.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-128">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="bbc5d-129">In diesem Fall ist der OutLoggerVariable-Parameter enthalten, um ein detailliertes Protokoll aller Schritte zu generieren, die vom **Test-CsExUMConnectivity** cmdletand den Erfolg oder Misserfolg jedes dieser Schritte durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-129">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="bbc5d-130">Dazu wird der OutLoggerVariable-Parameter zusammen mit dem Parameterwert ExumText hinzugefügt. Dies bewirkt, dass detaillierte Protokollierungsinformationen in einer Variablen mit dem Namen $ExumTest gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-130">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="bbc5d-131">Im letzten Befehl im Beispiel wird die ToXml ()-Methode verwendet, um die Protokollinformationen in das XML-Format zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-131">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="bbc5d-132">Diese XML-Daten werden dann mit dem Out-File-Cmdlet in eine Datei mit dem Namen C: \\ Logs \\ExumTest.xml geschrieben.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-132">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bbc5d-133">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="bbc5d-133">Determining success or failure</span></span>

<span data-ttu-id="bbc5d-134">Wenn die Exchange-Integration ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als **erfolgreich** markiert ist:</span><span class="sxs-lookup"><span data-stu-id="bbc5d-134">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="bbc5d-135">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bbc5d-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bbc5d-136">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="bbc5d-136">Result : Success</span></span>

<span data-ttu-id="bbc5d-137">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="bbc5d-137">Latency : 00:00:00</span></span>

<span data-ttu-id="bbc5d-138">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="bbc5d-138">Error Message :</span></span>

<span data-ttu-id="bbc5d-139">Diagnose</span><span class="sxs-lookup"><span data-stu-id="bbc5d-139">Diagnosis :</span></span>

<span data-ttu-id="bbc5d-140">Wenn der angegebene Benutzer keine Benachrichtigungen empfangen kann, wird das Ergebnis als **Fehler** angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="bbc5d-140">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="bbc5d-141">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bbc5d-141">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bbc5d-142">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="bbc5d-142">Result : Failure</span></span>

<span data-ttu-id="bbc5d-143">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="bbc5d-143">Latency : 00:00:00</span></span>

<span data-ttu-id="bbc5d-144">Fehlermeldung: 10060, Fehler bei einem Verbindungsversuch, weil die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="bbc5d-144">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="bbc5d-145">hat nach einer bestimmten Zeit nicht richtig reagiert, oder</span><span class="sxs-lookup"><span data-stu-id="bbc5d-145">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="bbc5d-146">Fehler beim Herstellen einer Verbindung, weil der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="bbc5d-146">established connection failed because connected host has</span></span>

<span data-ttu-id="bbc5d-147">Fehler beim Antworten 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="bbc5d-147">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="bbc5d-148">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="bbc5d-148">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="bbc5d-149">die verbundene Partei hat nach einer gewissen Zeit nicht richtig reagiert</span><span class="sxs-lookup"><span data-stu-id="bbc5d-149">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="bbc5d-150">Zeit, oder die Verbindung konnte nicht hergestellt werden, weil der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="bbc5d-150">time, or established connection failed because connected host</span></span>

<span data-ttu-id="bbc5d-151">Fehler beim Antworten 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="bbc5d-151">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="bbc5d-152">Diagnose</span><span class="sxs-lookup"><span data-stu-id="bbc5d-152">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bbc5d-153">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="bbc5d-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="bbc5d-154">Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsExUMConnectivity** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="bbc5d-154">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="bbc5d-155">Es wurde ein falscher Parameterwert angegeben.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-155">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="bbc5d-156">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-156">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="bbc5d-157">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-157">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="bbc5d-158">Dieser Befehl schlägt fehl, wenn der Exchange-Server falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-158">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="bbc5d-159">Dieser Befehl schlägt fehl, wenn der Exchange-Server nicht über Ihr Netzwerk erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-159">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bbc5d-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bbc5d-160">See Also</span></span>


[<span data-ttu-id="bbc5d-161">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="bbc5d-161">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

<span data-ttu-id="bbc5d-162"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="bbc5d-162"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

