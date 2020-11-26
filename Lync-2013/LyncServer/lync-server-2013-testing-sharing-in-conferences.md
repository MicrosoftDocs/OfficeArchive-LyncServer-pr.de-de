---
title: 'Lync Server 2013: Testen der Freigabe in Konferenzen'
description: 'Lync Server 2013: Testen der Freigabe in Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e569a97d102664b64c201af9b60061813df69ef5
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49439751"
---
# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="8fa94-103">Testen der Freigabe in Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8fa94-103">Testing sharing in conferences in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="8fa94-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="8fa94-104">

<span> </span></span></span>

<span data-ttu-id="8fa94-105">_**Letztes Änderungsdatum des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="8fa94-105">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fa94-106">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="8fa94-106">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8fa94-107">Täglich</span><span class="sxs-lookup"><span data-stu-id="8fa94-107">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fa94-108">Test Tool</span><span class="sxs-lookup"><span data-stu-id="8fa94-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8fa94-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8fa94-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fa94-110">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8fa94-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8fa94-111">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="8fa94-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8fa94-112">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsDataConference-</strong> Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="8fa94-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="8fa94-113">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="8fa94-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8fa94-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fa94-114">Description</span></span>

<span data-ttu-id="8fa94-115">In lync Server 2013 ist eine Datenkonferenz eine Konferenz, in der kollaborative Aktivitäten wie Whiteboards oder Anmerkungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8fa94-115">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="8fa94-116">Mit dem Cmdlet **Test-CsDataConference** können Sie überprüfen, ob ein Benutzer Paar an einer Datenkonferenz teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="8fa94-116">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8fa94-117">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="8fa94-117">Running the test</span></span>

<span data-ttu-id="8fa94-118">Der in Beispiel 1 gezeigte Befehl überprüft, ob eine Datenkonferenz im Pool ATL-CS-001.litwareinc.com durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8fa94-118">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="8fa94-119">Bei diesem Befehl wird davon ausgegangen, dass Sie ein paar Testbenutzer für den angegebenen Pool konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="8fa94-119">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="8fa94-120">Wenn keine solchen Testbenutzer vorhanden sind, wird der Befehl nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8fa94-120">If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="8fa94-121">Die in Beispiel 2 gezeigten Befehle testen die Möglichkeit eines Paars von Benutzern ("litwareinc \\ Pilar und" litwareinc \\ kenmyer), sich bei lync Server 2013 anzumelden und dann eine Datenkonferenz durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="8fa94-121">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="8fa94-122">Dazu wird im ersten Befehl im Beispiel das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Anmeldeinformationsobjekt für die Befehlszeilenschnittstelle zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält.</span><span class="sxs-lookup"><span data-stu-id="8fa94-122">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="8fa94-123">(Da der Anmeldename, "litwareinc \\ Pilar, als Parameter hinzugefügt wurde, erfordert das Dialogfeld Windows PowerShell-Anmeldeinformationen nur, dass der Administrator das Kennwort für das Pilar Ackerman-Konto eingegeben hat.) Das resultierende Anmeldeinformationsobjekt wird dann in einer Variablen mit dem Namen $cred 1 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8fa94-123">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="8fa94-124">Der zweite Befehl führt dieselbe Aufgabe aus, wobei dieses Mal ein Anmeldeinformationsobjekt für das Ken Myers-Konto zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8fa94-124">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="8fa94-125">Wenn die Anmeldeinformationsobjekte in der Hand sind, bestimmt der dritte Befehl, ob sich diese beiden Benutzer bei lync Server 2013 anmelden und eine Datenkonferenz durchführen können.</span><span class="sxs-lookup"><span data-stu-id="8fa94-125">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="8fa94-126">Um diese Aufgabe auszuführen, wird das Cmdlet **Test-CsDataConference** zusammen mit den folgenden Parametern aufgerufen: TargetFqdn (der FQDN des registrierungspools); SenderSipAddress (die SIP-Adresse des ersten Testbenutzers); SenderCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für denselben Benutzer enthält); ReceiverSipAddress (die SIP-Adresse des anderen Testbenutzers); und ReceiverCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für den anderen Testbenutzer enthält).</span><span class="sxs-lookup"><span data-stu-id="8fa94-126">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8fa94-127">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="8fa94-127">Determining success or failure</span></span>

<span data-ttu-id="8fa94-128">Wenn Datenkonferenzen ordnungsgemäß konfiguriert sind, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="8fa94-128">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="8fa94-129">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8fa94-129">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8fa94-130">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="8fa94-130">Result : Success</span></span>

<span data-ttu-id="8fa94-131">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8fa94-131">Latency : 00:00:00</span></span>

<span data-ttu-id="8fa94-132">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="8fa94-132">Error Message :</span></span>

<span data-ttu-id="8fa94-133">Diagnose</span><span class="sxs-lookup"><span data-stu-id="8fa94-133">Diagnosis :</span></span>

<span data-ttu-id="8fa94-134">Wenn die angegebenen Benutzer die Datenfreigabe nicht verwenden können, wird das Ergebnis als **Fehler** angezeigt, und zusätzliche Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="8fa94-134">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="8fa94-135">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8fa94-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8fa94-136">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="8fa94-136">Result : Failure</span></span>

<span data-ttu-id="8fa94-137">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8fa94-137">Latency : 00:00:00</span></span>

<span data-ttu-id="8fa94-138">Fehlermeldung: 10060, Fehler bei einem Verbindungsversuch, weil die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="8fa94-138">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="8fa94-139">hat nach einer bestimmten Zeit nicht richtig reagiert, oder</span><span class="sxs-lookup"><span data-stu-id="8fa94-139">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="8fa94-140">Fehler beim Herstellen einer Verbindung, weil der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="8fa94-140">established connection failed because connected host has</span></span>

<span data-ttu-id="8fa94-141">Fehler bei der Antwort \[ 2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="8fa94-141">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="8fa94-142">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="8fa94-142">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="8fa94-143">die verbundene Partei hat nach einer gewissen Zeit nicht richtig reagiert</span><span class="sxs-lookup"><span data-stu-id="8fa94-143">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="8fa94-144">Zeit, oder die Verbindung konnte nicht hergestellt werden, weil der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="8fa94-144">time, or established connection failed because connected host</span></span>

<span data-ttu-id="8fa94-145">hat nicht reagiert</span><span class="sxs-lookup"><span data-stu-id="8fa94-145">has failed to respond</span></span>

<span data-ttu-id="8fa94-146">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="8fa94-146">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="8fa94-147">Diagnose</span><span class="sxs-lookup"><span data-stu-id="8fa94-147">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8fa94-148">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="8fa94-148">Reasons why the test might have failed</span></span>

<span data-ttu-id="8fa94-149">Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsDataConference** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="8fa94-149">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="8fa94-150">Es wurde ein falscher Parameterwert angegeben.</span><span class="sxs-lookup"><span data-stu-id="8fa94-150">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="8fa94-151">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="8fa94-151">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="8fa94-152">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="8fa94-152">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="8fa94-153">Die Möglichkeit zum Durchführen einer Datenkonferenz hängt von der konferenzrichtlinie ab, die dem Benutzer zugewiesen wurde, der die Konferenz organisiert hat (im Fall des **Test-CsDataConference-** Cmdlets, bei dem es sich um den Absender handelt).</span><span class="sxs-lookup"><span data-stu-id="8fa94-153">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="8fa94-154">Wenn es dem Organisator nicht gestattet ist, in seiner Besprechung kollaborative Aktivitäten einzubeziehen (Wenn beispielsweise die EnableDataCollaboration-Eigenschaft der konferenzrichtlinie auf "false" festgelegt ist), schlägt das **Test-CsDataConference-** Cmdlet fehl.</span><span class="sxs-lookup"><span data-stu-id="8fa94-154">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="8fa94-155">Dieser Befehl schlägt fehl, wenn der Edgeserver falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="8fa94-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

<span data-ttu-id="8fa94-156"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="8fa94-156"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

