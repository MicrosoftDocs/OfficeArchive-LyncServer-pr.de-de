---
title: 'Lync Server 2013: Testen der Sitzung für Einwahlkonferenzen'
description: 'Lync Server 2013: Testen der Einwahlkonferenz Sitzung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d0c51b16df674dbf8bf7f0a2c6c4c93c2606d95
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394510"
---
# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="b1e52-103">Testen der Einwahlkonferenz Sitzung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1e52-103">Testing dial-in conferencing session in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="b1e52-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="b1e52-104">

<span> </span></span></span>

<span data-ttu-id="b1e52-105">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="b1e52-105">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1e52-106">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="b1e52-106">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b1e52-107">Täglich</span><span class="sxs-lookup"><span data-stu-id="b1e52-107">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1e52-108">Test Tool</span><span class="sxs-lookup"><span data-stu-id="b1e52-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b1e52-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1e52-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1e52-110">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b1e52-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b1e52-111">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="b1e52-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b1e52-112">Bei der Ausführung mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsDialInConferencing-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="b1e52-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="b1e52-113">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="b1e52-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b1e52-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1e52-114">Description</span></span>

<span data-ttu-id="b1e52-115">Das Test-CsDialInConferencing-Cmdlet überprüft, ob ein Benutzer an einer Einwahlkonferenz teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="b1e52-115">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="b1e52-116">Test-CsDialInConferencing versucht, einen Testbenutzer auf dem System zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="b1e52-116">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="b1e52-117">Wenn die Anmeldung erfolgreich ausgeführt wird, verwendet das Cmdlet dann die Anmeldeinformationen und Berechtigungen des Benutzers, um alle verfügbaren Zugriffsnummern für Einwahlkonferenzen zu testen.</span><span class="sxs-lookup"><span data-stu-id="b1e52-117">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="b1e52-118">Der Erfolg oder Misserfolg jedes Einwahlversuchs wird festgestellt, dann wird der Testbenutzer von lync Server abgemeldet. Test-CsDialInConferencing überprüft nur, ob die entsprechenden Verbindungen hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="b1e52-118">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="b1e52-119">Das Cmdlet führt tatsächlich keine Telefonanrufe durch oder erstellt keine Einwahlkonferenzen, an denen andere Benutzer teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="b1e52-119">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b1e52-120">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="b1e52-120">Running the test</span></span>

<span data-ttu-id="b1e52-121">Das Test-CsDialInConferencing-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b1e52-121">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="b1e52-122">Um diese Überprüfung mit einem Testkonto auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="b1e52-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="b1e52-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b1e52-123">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="b1e52-124">Damit diese Überprüfung mit einem tatsächlichen Benutzerkonto ausgeführt werden kann, müssen Sie ein Windows PowerShell-Anmeldeinformationsobjekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="b1e52-124">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="b1e52-125">Sie müssen dann das Credentials-Objekt und die SIP-Adresse des Kontos mit dem aufrufenden Test-CsDialInConferencing einfügen:</span><span class="sxs-lookup"><span data-stu-id="b1e52-125">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="b1e52-126">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .</span><span class="sxs-lookup"><span data-stu-id="b1e52-126">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b1e52-127">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="b1e52-127">Determining success or failure</span></span>

<span data-ttu-id="b1e52-128">Wenn sich der angegebene Benutzer bei lync Server anmelden und dann eine Verbindung mit einer der verfügbaren Zugriffsnummern für Einwahlkonferenzen herstellen kann, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="b1e52-128">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b1e52-129">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b1e52-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b1e52-130">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="b1e52-130">Result : Success</span></span>

<span data-ttu-id="b1e52-131">Latenz: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="b1e52-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="b1e52-132">Fehler</span><span class="sxs-lookup"><span data-stu-id="b1e52-132">Error :</span></span>

<span data-ttu-id="b1e52-133">Diagnose</span><span class="sxs-lookup"><span data-stu-id="b1e52-133">Diagnosis :</span></span>

<span data-ttu-id="b1e52-134">Wenn der angegebene Benutzer diese Verbindung nicht herstellen kann, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="b1e52-134">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b1e52-135">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b1e52-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b1e52-136">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="b1e52-136">Result : Failure</span></span>

<span data-ttu-id="b1e52-137">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b1e52-137">Latency : 00:00:00</span></span>

<span data-ttu-id="b1e52-138">Fehler: die Anmeldung wurde verweigert.</span><span class="sxs-lookup"><span data-stu-id="b1e52-138">Error : The log on was denied.</span></span> <span data-ttu-id="b1e52-139">Überprüfen Sie, ob die richtigen Anmeldeinformationen sind.</span><span class="sxs-lookup"><span data-stu-id="b1e52-139">Check that the proper credentials are</span></span>

<span data-ttu-id="b1e52-140">verwendet wird und das Konto aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="b1e52-140">being used and the account is active.</span></span>

<span data-ttu-id="b1e52-141">Innere Ausnahme: NegotiateSecurityAssociation ist fehlgeschlagen, Fehler:-</span><span class="sxs-lookup"><span data-stu-id="b1e52-141">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="b1e52-142">2146893044</span><span class="sxs-lookup"><span data-stu-id="b1e52-142">2146893044</span></span>

<span data-ttu-id="b1e52-143">Diagnose</span><span class="sxs-lookup"><span data-stu-id="b1e52-143">Diagnosis :</span></span>

<span data-ttu-id="b1e52-144">Die vorherige Ausgabe zeigt an, dass dem Testbenutzer der Zugriff auf lync Server selbst verweigert wurde.</span><span class="sxs-lookup"><span data-stu-id="b1e52-144">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="b1e52-145">Dies bedeutet in der Regel, dass die an Test-CsDialInConferencing übergebenen Benutzeranmeldeinformationen ungültig waren.</span><span class="sxs-lookup"><span data-stu-id="b1e52-145">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="b1e52-146">Sie sollten wiederum das Windows PowerShell-Anmeldeinformationsobjekt erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="b1e52-146">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="b1e52-147">Obwohl Sie das Kennwort für das Benutzerkonto abrufen können, können Sie die SIP-Adresse überprüfen, indem Sie einen ähnlichen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="b1e52-147">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b1e52-148">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="b1e52-148">Reasons why the test might have failed</span></span>

<span data-ttu-id="b1e52-149">Im folgenden finden Sie einige häufige Gründe, warum Test-CsDialInConferencing fehlschlagen kann:</span><span class="sxs-lookup"><span data-stu-id="b1e52-149">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="b1e52-150">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="b1e52-150">You specified a user account that is not valid.</span></span> <span data-ttu-id="b1e52-151">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="b1e52-151">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="b1e52-152">Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b1e52-152">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="b1e52-153">Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="b1e52-153">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="b1e52-154">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b1e52-154">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="b1e52-155">Möglicherweise verfügen Sie über eine falsche Zugriffsnummer für Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="b1e52-155">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="b1e52-156">Sie können die aktuell konfigurierte Liste der Zugriffsnummern für Einwahlkonferenzen mithilfe des folgenden Befehls zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="b1e52-156">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

<span data-ttu-id="b1e52-157"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="b1e52-157"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

