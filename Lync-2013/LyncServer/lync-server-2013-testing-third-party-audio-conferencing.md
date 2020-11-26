---
title: 'Lync Server 2013: Testen von Audiokonferenzen von Drittanbietern'
description: 'Lync Server 2013: Testen von Audiokonferenzen von Drittanbietern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f009d95834768d8a4e6619a79ff1f3be0a2b92bd
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49440955"
---
# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="0716d-103">Testen von Audiokonferenzen von Drittanbietern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0716d-103">Testing third-party audio conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="0716d-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="0716d-104">

<span> </span></span></span>

<span data-ttu-id="0716d-105">_**Letztes Änderungsdatum des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="0716d-105">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0716d-106">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="0716d-106">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0716d-107">Täglich</span><span class="sxs-lookup"><span data-stu-id="0716d-107">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0716d-108">Test Tool</span><span class="sxs-lookup"><span data-stu-id="0716d-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0716d-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0716d-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0716d-110">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0716d-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0716d-111">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="0716d-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0716d-112">Bei der Ausführung mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsAudioConferencingProvider-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="0716d-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="0716d-113">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="0716d-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0716d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0716d-114">Description</span></span>

<span data-ttu-id="0716d-115">Bei einem Audiokonferenzdienst handelt es sich um ein drittanbieterunternehmen, das Organisationen Konferenzdienste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0716d-115">An audio conferencing provider is a third-party company that provides organizations with conferencing services.</span></span> <span data-ttu-id="0716d-116">Audiokonferenz-Anbieter ermöglichen unter anderem, dass Benutzer, die sich außerhalb des Standorts befinden und nicht mit dem Unternehmensnetzwerk oder dem Internet verbunden sind, am Audioteil einer Konferenz oder Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="0716d-116">Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting.</span></span> <span data-ttu-id="0716d-117">Audiokonferenz-Anbieter bieten häufig Highend-Dienste wie Live-Übersetzungen, Transkriptionen und Live-Unterstützung für pro-Konferenz-Nutzer.</span><span class="sxs-lookup"><span data-stu-id="0716d-117">Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="0716d-118">Das Cmdlet **Test-CsAudioConferencingProvider** wird verwendet, um zu überprüfen, ob ein Benutzer eine Verbindung mit seinem Audiokonferenz-Anbieter herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="0716d-118">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="0716d-119">Beachten Sie, dass dieses Cmdlet auf eine von zwei Arten ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0716d-119">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="0716d-120">Viele Administratoren verwenden die CsHealthMonitoringConfiguration-Cmdlets, um Testbenutzer für die einzelnen registrierungspools einzurichten.</span><span class="sxs-lookup"><span data-stu-id="0716d-120">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="0716d-121">Diese Testbenutzer stellen ein paar Benutzerkonten dar, die für die Verwendung mit synthetischen Transaktionen vorkonfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="0716d-121">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="0716d-122">(In der Regel handelt es sich hierbei um Testkonten und nicht um Konten, die tatsächlichen Benutzern gehören.) Wenn Testbenutzer für einen Pool konfiguriert sind, können Administratoren das Cmdlet **Test-CsAudioConferencingProvider** für diesen Pool ausführen, ohne die Identität des an dem Test beteiligten Benutzerkontos angeben zu müssen (und die Anmeldeinformationen einzugeben).</span><span class="sxs-lookup"><span data-stu-id="0716d-122">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="0716d-123">Alternativ können Administratoren das Cmdlet **Test-CsAudioConferencingProvider** unter Verwendung eines tatsächlichen Benutzerkontos ausführen.</span><span class="sxs-lookup"><span data-stu-id="0716d-123">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="0716d-124">Wenn Sie den Test mit einem tatsächlichen Benutzerkonto durchführen möchten, müssen Sie den Anmeldenamen und das Kennwort für dieses Konto angeben.</span><span class="sxs-lookup"><span data-stu-id="0716d-124">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0716d-125">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="0716d-125">Running the test</span></span>

<span data-ttu-id="0716d-126">Beispiel 1 überprüft, ob ein für den Pool ATL-CS-001.litwareinc.com definierter Testbenutzer in der Lage ist, eine Verbindung mit seinem Audiokonferenz-Anbieter herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0716d-126">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="0716d-127">Dieser Befehl setzt voraus, dass mindestens ein Testbenutzer für den Pool definiert ist.</span><span class="sxs-lookup"><span data-stu-id="0716d-127">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="0716d-128">Wenn für ATL-CS-001.litwareinc.com keine Testbenutzer definiert wurden, schlägt der Befehl fehl; Das liegt daran, dass das Cmdlet **Test-CsAudioConferencingProvider** nicht weiß, welcher Benutzer im Test verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0716d-128">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="0716d-129">Wenn Sie für einen Pool keine Testbenutzer definiert haben, müssen Sie den "usersipaddress"-Parameter und die Anmeldeinformationen des Benutzerkontos angeben, das der Befehl verwenden soll, wenn die Verbindung mit einem Audiokonferenzdienst überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="0716d-129">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="0716d-130">Die in Beispiel 2 gezeigten Befehle testen die Möglichkeit eines bestimmten Benutzers ("litwareinc \\ kenmyer), eine Verbindung zu seinem Audiokonferenz-Anbieter herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0716d-130">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="0716d-131">Dazu wird im ersten Befehl im Beispiel das Get-Credential-Cmdlet verwendet, um ein Windows PowerShell-Befehlszeilenschnittstellen-Anmeldeinformationsobjekt zu erstellen, das den Namen und das Kennwort des Benutzers Ken Myers enthält.</span><span class="sxs-lookup"><span data-stu-id="0716d-131">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="0716d-132">(Da der Anmeldename "litwareinc \\ kenmyer als Parameter enthalten ist, muss das Windows PowerShell-Dialogfeld Anmeldeinformationen anfordern nur dem Administrator das Kennwort für das Ken Myers-Konto eingeben.) Das resultierende Credentials-Objekt wird in einer Variablen mit dem Namen $Credential gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0716d-132">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="0716d-133">Der zweite Befehl überprüft dann, ob dieser Benutzer eine Verbindung mit seinem Audiokonferenz-Anbieter herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="0716d-133">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="0716d-134">Um diese Aufgabe auszuführen, wird das Test-CsAudioConferencingProvider-Cmdlet zusammen mit drei Parametern aufgerufen: TargetFqdn (dem FQDN des registrierungspools); UserCredential (das Windows PowerShell-Objekt, das die Benutzeranmeldeinformationen von Ken Myers enthält); und "usersipaddress" (die SIP-Adresse, die den angegebenen Benutzeranmeldeinformationen entspricht).</span><span class="sxs-lookup"><span data-stu-id="0716d-134">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0716d-135">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="0716d-135">Determining success or failure</span></span>

<span data-ttu-id="0716d-136">Wenn der Audiokonferenz-Anbieter ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als **erfolgreich** markiert ist:</span><span class="sxs-lookup"><span data-stu-id="0716d-136">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="0716d-137">Ziel-FQDN: ATL-SQL-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0716d-137">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="0716d-138">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="0716d-138">Result : Success</span></span>

<span data-ttu-id="0716d-139">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="0716d-139">Latency : 00:00:00</span></span>

<span data-ttu-id="0716d-140">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="0716d-140">Error Message :</span></span>

<span data-ttu-id="0716d-141">Diagnose</span><span class="sxs-lookup"><span data-stu-id="0716d-141">Diagnosis :</span></span>

<span data-ttu-id="0716d-142">Wenn sich der angegebene Benutzer nicht anmelden oder sich abmelden kann, wird das Ergebnis als **Fehler** angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="0716d-142">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="0716d-143">Ziel-FQDN: ATL-SQL-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0716d-143">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="0716d-144">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="0716d-144">Result : Failure</span></span>

<span data-ttu-id="0716d-145">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="0716d-145">Latency : 00:00:00</span></span>

<span data-ttu-id="0716d-146">Fehlermeldung: 10060, Fehler bei einem Verbindungsversuch, weil die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="0716d-146">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="0716d-147">hat nach einer bestimmten Zeit nicht richtig reagiert, oder</span><span class="sxs-lookup"><span data-stu-id="0716d-147">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="0716d-148">Fehler beim Herstellen einer Verbindung, weil der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="0716d-148">established connection failed because connected host has</span></span>

<span data-ttu-id="0716d-149">Fehler bei der Antwort \[ 2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="0716d-149">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="0716d-150">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="0716d-150">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="0716d-151">die verbundene Partei hat nach einer gewissen Zeit nicht richtig reagiert</span><span class="sxs-lookup"><span data-stu-id="0716d-151">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="0716d-152">Zeit, oder die Verbindung konnte nicht hergestellt werden, weil der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="0716d-152">time, or established connection failed because connected host</span></span>

<span data-ttu-id="0716d-153">hat nicht reagiert</span><span class="sxs-lookup"><span data-stu-id="0716d-153">has failed to respond</span></span>

<span data-ttu-id="0716d-154">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="0716d-154">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="0716d-155">Diagnose</span><span class="sxs-lookup"><span data-stu-id="0716d-155">Diagnosis :</span></span>

<span data-ttu-id="0716d-156">Die vorherige Ausgabe enthält beispielsweise die Notiz "die verbundene Partei hat nicht richtig reagiert", die in der Regel auf ein Problem mit dem Edgeserver hindeutet.</span><span class="sxs-lookup"><span data-stu-id="0716d-156">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0716d-157">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="0716d-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="0716d-158">Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsAudioConferencingProvider** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="0716d-158">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="0716d-159">Es wurde ein falscher Parameterwert angegeben.</span><span class="sxs-lookup"><span data-stu-id="0716d-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="0716d-160">Wie im vorherigen Beispiel gezeigt, müssen die optionalen Parameter richtig konfiguriert sein, oder der Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="0716d-160">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="0716d-161">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="0716d-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="0716d-162">Beachten Sie, dass der Test fehlschlägt, wenn dem vom **Test-CsAudioConferencingProvider-** Cmdlet verwendeten Benutzer kein Audiokonferenz-Anbieter zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="0716d-162">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="0716d-163">Dieser Befehl schlägt fehl, wenn der Edgeserver falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="0716d-163">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

<span data-ttu-id="0716d-164"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="0716d-164"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

