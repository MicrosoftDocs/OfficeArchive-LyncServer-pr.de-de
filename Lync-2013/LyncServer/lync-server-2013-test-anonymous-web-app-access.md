---
title: 'Lync Server 2013: Testen des anonymen Web App-Zugriffs'
description: 'Lync Server 2013: Testen des anonymen Web App-Zugriffs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c33840912fefcaeef069e14773cfefd0834a8b
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49441270"
---
# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="863f1-103">Testen des anonymen Web App-Zugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="863f1-103">Test anonymous Web App access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="863f1-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="863f1-104">

<span> </span></span></span>

<span data-ttu-id="863f1-105">_**Letztes Änderungsdatum des Themas:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="863f1-105">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="863f1-106">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="863f1-106">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="863f1-107">Monatlich</span><span class="sxs-lookup"><span data-stu-id="863f1-107">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="863f1-108">Test Tool</span><span class="sxs-lookup"><span data-stu-id="863f1-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="863f1-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="863f1-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="863f1-110">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="863f1-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="863f1-111">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="863f1-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="863f1-112">Bei der Ausführung mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsWebAppAnonymous-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="863f1-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="863f1-113">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="863f1-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="863f1-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="863f1-114">Description</span></span>

<span data-ttu-id="863f1-115">Das Test-CsWebAppAnonymous-Cmdlet überprüft, ob ein anonymer Benutzer mit lync Web App an lync Server-Konferenzen teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="863f1-115">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="863f1-116">Wenn Sie das Cmdlet ausführen, Test-CsWebAppAnonymous Kontakt mit dem Web Ticket-Dienst, um ein WebTICKET für den anonymen Benutzer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="863f1-116">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="863f1-117">Wenn es dem Cmdlet gelingt, dieses Ticket zu erhalten, wird Test-CsWebAppAnonymous sich an den lync-Server wenden und versuchen, getrennte Konferenzen für Chats, Anwendungsfreigabe und Datenzusammenarbeit einzurichten.</span><span class="sxs-lookup"><span data-stu-id="863f1-117">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="863f1-118">Beachten Sie, dass Test-CsWebAppAnonymous nur die APIs und Verbindungen überprüft, die zum Erstellen dieser Konferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="863f1-118">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="863f1-119">Das Cmdlet erstellt und führt keine Konferenzen aus.</span><span class="sxs-lookup"><span data-stu-id="863f1-119">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="863f1-120">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="863f1-120">Running the test</span></span>

<span data-ttu-id="863f1-121">Das Test-CsWebAppAnonymous-Cmdlet kann entweder mit einem Paar vorkonfigurierter Testkonten oder mit den Konten zweier Benutzer ausgeführt werden, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="863f1-121">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="863f1-122">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den vollqualifizierten Domänennamen des lync-Server Pools angeben, der getestet wird.</span><span class="sxs-lookup"><span data-stu-id="863f1-122">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="863f1-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="863f1-123">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="863f1-124">Damit diese Überprüfung mit tatsächlichen Benutzerkonten ausgeführt werden kann, müssen Sie für jedes Konto zwei Anmeldedaten Objekte der lync Server-Verwaltungsshell (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen.</span><span class="sxs-lookup"><span data-stu-id="863f1-124">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="863f1-125">Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsWebAppAnonymous aufrufen:</span><span class="sxs-lookup"><span data-stu-id="863f1-125">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="863f1-126">Weitere Informationen finden Sie im Hilfethema zum Cmdlet "Test-CsWebAppAnonymous".</span><span class="sxs-lookup"><span data-stu-id="863f1-126">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="863f1-127">Beachten Sie, dass Test-CsWebAppAnonymous für die Verwendung in lync Server 2013 veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="863f1-127">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="863f1-128">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="863f1-128">Determining success or failure</span></span>

<span data-ttu-id="863f1-129">Wenn Test-CsWebAppAnonymous dem anonymen Benutzer an seinen Konferenzen teilnehmen kann, gibt das Cmdlet den Erfolg des Testergebnisses zurück:</span><span class="sxs-lookup"><span data-stu-id="863f1-129">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="863f1-130">Ziel-FQDN:</span><span class="sxs-lookup"><span data-stu-id="863f1-130">Target Fqdn :</span></span>

<span data-ttu-id="863f1-131">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="863f1-131">Result : Success</span></span>

<span data-ttu-id="863f1-132">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="863f1-132">Latency : 00:00:00</span></span>

<span data-ttu-id="863f1-133">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="863f1-133">Error Message :</span></span>

<span data-ttu-id="863f1-134">Diagnose</span><span class="sxs-lookup"><span data-stu-id="863f1-134">Diagnosis :</span></span>

<span data-ttu-id="863f1-135">Wenn der anonyme Benutzer nicht an den erforderlichen Konferenzen teilnehmen kann, wird das Testergebnis als Fehler gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="863f1-135">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="863f1-136">In der Regel werden Test-CsWebAppAnonymous auch eine detaillierte Fehlermeldung und Diagnose zurückmelden:</span><span class="sxs-lookup"><span data-stu-id="863f1-136">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="863f1-137">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="863f1-137">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="863f1-138">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="863f1-138">Result : Failure</span></span>

<span data-ttu-id="863f1-139">Latenz: 00:00:05.9746266</span><span class="sxs-lookup"><span data-stu-id="863f1-139">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="863f1-140">Fehlermeldung: keine Antwort für Web-Ticket Dienst empfangen</span><span class="sxs-lookup"><span data-stu-id="863f1-140">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="863f1-141">Diagnose: die HTTP-Anforderung ist mit dem Client nicht autorisiert</span><span class="sxs-lookup"><span data-stu-id="863f1-141">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="863f1-142">Authentifizierungsschema "NTLM".</span><span class="sxs-lookup"><span data-stu-id="863f1-142">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="863f1-143">Die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="863f1-143">The authentication</span></span>

<span data-ttu-id="863f1-144">der vom Server empfangene Header lautet "Negotiate, NTLM".</span><span class="sxs-lookup"><span data-stu-id="863f1-144">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="863f1-145">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="863f1-145">Reasons why the test might have failed</span></span>

<span data-ttu-id="863f1-146">Test-CsWebAppAnonymous Fehler drehen sich in der Regel um Benutzer Authentifizierungsfehler: Sie müssen den Test mit einem gültigen Benutzerkonto ausführen, obwohl das Cmdlet die Möglichkeit eines anonymen Benutzers überprüft, eine Verbindung mit lync Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="863f1-146">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="863f1-147">Wenn Test-CsWebAppAnonymous fehlschlägt, sollten Sie überprüfen, ob der angegebene Benutzer ein lync Server-Benutzerkonto gültig ist.</span><span class="sxs-lookup"><span data-stu-id="863f1-147">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="863f1-148">Sie können lync Server-Kontoinformationen mithilfe eines Befehls wie den folgenden abrufen:</span><span class="sxs-lookup"><span data-stu-id="863f1-148">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="863f1-149">Wenn die Enabled-Eigenschaft nicht gleich true ist oder der Befehl fehlschlägt, bedeutet dies, dass der Benutzer kein gültiges lync Server-Konto hat.</span><span class="sxs-lookup"><span data-stu-id="863f1-149">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="863f1-150">Sie sollten auch sicherstellen, dass das Kennwort, das Sie beim Ausführen des Cmdlets angegeben haben, ein gültiges Kennwort ist.</span><span class="sxs-lookup"><span data-stu-id="863f1-150">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="863f1-151">Konfigurationsprobleme mit Office Web Apps Server können auch dazu führen, dass Test-CsWebAppAnonymous fehlschlägt. Das ist häufig der Fall, wenn Sie die folgende Diagnose erhalten:</span><span class="sxs-lookup"><span data-stu-id="863f1-151">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="863f1-152">Die HTTP-Anforderung ist mit dem Clientauthentifizierungsschema "NTLM" nicht autorisiert.</span><span class="sxs-lookup"><span data-stu-id="863f1-152">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="863f1-153">Der vom Server empfangene Authentifizierungsheader lautet "Negotiate, NTLM".</span><span class="sxs-lookup"><span data-stu-id="863f1-153">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="863f1-154">Weitere Informationen zum Diagnostizieren und Beheben von Problemen mit dem Office Web Apps-Server finden Sie im Blogbeitrag [Office Web Apps Server 2013 – Computer werden immer als](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)fehlerhaft gemeldet.</span><span class="sxs-lookup"><span data-stu-id="863f1-154">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

<span data-ttu-id="863f1-155"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="863f1-155"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

