---
title: 'Lync Server 2013: Testen von Push-Benachrichtigungen an Smartphones'
description: 'Lync Server 2013: Testen von Push-Benachrichtigungen an Smartphones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b92ef444a5331c9a673fd2db506631554e96eea
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49441228"
---
# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="65526-103">Testen von Push-Benachrichtigungen an Smartphones in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65526-103">Test push notifications to smart phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="65526-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="65526-104">

<span> </span></span></span>

<span data-ttu-id="65526-105">_**Letztes Änderungsdatum des Themas:** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="65526-105">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65526-106">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="65526-106">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="65526-107">Monatlich</span><span class="sxs-lookup"><span data-stu-id="65526-107">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65526-108">Test Tool</span><span class="sxs-lookup"><span data-stu-id="65526-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="65526-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="65526-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65526-110">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="65526-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="65526-111">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="65526-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="65526-112">Bei der Ausführung mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsMcxPushNotification-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="65526-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="65526-113">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="65526-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="65526-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65526-114">Description</span></span>

<span data-ttu-id="65526-115">Der Push-Benachrichtigungsdienst (Apple Push Notification Service und Microsoft Push Notification Service) kann Benachrichtigungen zu Ereignissen wie neuen Sofortnachrichten oder neuen Voicemails an mobile Geräte wie iPhones und Windows phones senden, selbst wenn der lync-Client auf diesen Geräten zurzeit angehalten oder im Hintergrund ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="65526-115">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="65526-116">Der Push-Benachrichtigungsdienst ist ein Cloud-basierter Dienst, der auf Microsoft-Servern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="65526-116">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="65526-117">Um die Vorteile von Push-Benachrichtigungen nutzen zu können, müssen Sie in der Lage sein, eine Verbindung mit der Push Notification Clearingstelle herzustellen und von ihr authentifiziert zu werden.</span><span class="sxs-lookup"><span data-stu-id="65526-117">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="65526-118">Mithilfe des Test-CsMcxPushNotification-Cmdlets können Administratoren überprüfen, ob Push-Benachrichtigungsanforderungen über den Edgeserver an das "Push Notification Clearing House" weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="65526-118">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="65526-119">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="65526-119">Running the test</span></span>

<span data-ttu-id="65526-120">Rufen Sie das Test-CsMcxPushNotification-Cmdlet auf, um den Push-Benachrichtigungsdienst zu testen.</span><span class="sxs-lookup"><span data-stu-id="65526-120">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="65526-121">Stellen Sie sicher, dass Sie den vollqualifizierten Domänennamen Ihres Edge-Servers angeben:</span><span class="sxs-lookup"><span data-stu-id="65526-121">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="65526-122">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .</span><span class="sxs-lookup"><span data-stu-id="65526-122">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="65526-123">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="65526-123">Determining success or failure</span></span>

<span data-ttu-id="65526-124">Wenn Test-CsMcxPushNotification erfolgreich ist, gibt das Cmdlet den Erfolg des Testergebnisses zurück:</span><span class="sxs-lookup"><span data-stu-id="65526-124">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="65526-125">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="65526-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="65526-126">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="65526-126">Result : Success</span></span>

<span data-ttu-id="65526-127">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="65526-127">Latency : 00:00:00</span></span>

<span data-ttu-id="65526-128">Fehler</span><span class="sxs-lookup"><span data-stu-id="65526-128">Error :</span></span>

<span data-ttu-id="65526-129">Diagnose</span><span class="sxs-lookup"><span data-stu-id="65526-129">Diagnosis :</span></span>

<span data-ttu-id="65526-130">Wenn Test-CsMcxPushNotification keine Verbindung mit dem Schiebe Benachrichtigungs-Clearing House herstellen kann, gibt das Cmdlet in der Regel kein Testergebnis des Fehlers zurück.</span><span class="sxs-lookup"><span data-stu-id="65526-130">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="65526-131">Stattdessen wird der Befehl in der Regel vollständig fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="65526-131">Instead the command will usually fail completely.</span></span> <span data-ttu-id="65526-132">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="65526-132">For example:</span></span>

<span data-ttu-id="65526-133">Test-CsMcxPushNotification: eine 504-Antwort (Server Timeout) wurde vom Netzwerk empfangen, und der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="65526-133">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="65526-134">Weitere Informationen finden Sie in den Ausnahmedetails.</span><span class="sxs-lookup"><span data-stu-id="65526-134">See the exception details for more information.</span></span>

<span data-ttu-id="65526-135">Zeile: 1 Zeichen: 27</span><span class="sxs-lookup"><span data-stu-id="65526-135">At line:1 char:27</span></span>

<span data-ttu-id="65526-136">\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="65526-136">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="65526-137">\+ CategoryInfo: OperationStopped: (:) \[ Test-CsMcxPushNotification \] , FailureResponseException</span><span class="sxs-lookup"><span data-stu-id="65526-137">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="65526-138">\+ FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="65526-138">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="65526-139">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="65526-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="65526-140">Wenn der Push-Benachrichtigungsdienst fehlschlägt, der in der Regel auf Probleme bei der Kommunikation mit Ihrem Edgeserver oder auf Probleme bei der Kommunikation mit dem Clearing House für die Push-Benachrichtigung hinweist.</span><span class="sxs-lookup"><span data-stu-id="65526-140">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="65526-141">Wenn beim Ausführen von Test-CsMcxPushNotification Probleme auftreten, sollten Sie zunächst überprüfen, ob der Edgeserver ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="65526-141">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="65526-142">Eine Möglichkeit besteht darin, das Test-CsAVEdgeConnectivity-Cmdlet zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="65526-142">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="65526-143">Mit dieser Prüfung wird überprüft, ob ein angegebener Benutzer eine Verbindung mit dem Edgeserver herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="65526-143">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="65526-144">Wenn der Edgeserver anscheinend ordnungsgemäß funktioniert, bedeutet dies häufig, dass Sie keine Verbindung mit der Push Notification Clearing House herstellen können.</span><span class="sxs-lookup"><span data-stu-id="65526-144">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="65526-145">Das bedeutet wiederum in der Regel, dass Sie den Clearing House-URI entweder nicht richtig konfiguriert haben oder dass Sie keinen DNS-SRV-Eintrag haben, der auf diese URL verweist.</span><span class="sxs-lookup"><span data-stu-id="65526-145">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="65526-146">Sie können überprüfen, ob der URI auf den richtigen Wert (SIP:Push@Push.lync.com) festgesetzt ist, indem Sie folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="65526-146">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="65526-147">Wenn die PushNotificationProxyUri-Eigenschaft auf etwas anderes als SIP:Push@Push.lync.com festzulegen ist, können Sie dieses Problem mithilfe des Set-McxConfiguration-Cmdlets beheben.</span><span class="sxs-lookup"><span data-stu-id="65526-147">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="65526-148">Mit diesem Befehl wird beispielsweise der URI in Ihrer Organisation richtig festgelegt:</span><span class="sxs-lookup"><span data-stu-id="65526-148">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="65526-149">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) ".</span><span class="sxs-lookup"><span data-stu-id="65526-149">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="65526-150">Wenn der URI richtig konfiguriert ist, sollten Sie im nächsten Schritt überprüfen, ob ein DNS-SRV-Eintrag vorhanden ist, der in Ihre SIP-Domäne und Ihren Edge-Server aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="65526-150">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="65526-151">Weitere Informationen zum Konfigurieren dieser Einträge finden Sie im Hilfethema DNS-Anforderungen für Mobilität.</span><span class="sxs-lookup"><span data-stu-id="65526-151">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="65526-152">Beachten Sie, dass die folgende Fehlermeldung in der Regel auf ein Problem mit DNS-Einträgen hinweist:</span><span class="sxs-lookup"><span data-stu-id="65526-152">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="65526-153">Eine 504-Antwort (Server Timeout) wurde vom Netzwerk empfangen, und der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="65526-153">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="65526-154">Weitere Informationen finden Sie in den Ausnahmedetails.</span><span class="sxs-lookup"><span data-stu-id="65526-154">See the exception details for more information.</span></span>

<span data-ttu-id="65526-155">Es ist auch möglich, dass Test-CsMcxConfiguration mit dieser Fehlermeldung fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="65526-155">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="65526-156">Test-CsMcxPushNotification: die Push-Benachrichtigungsanforderung wurde abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="65526-156">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="65526-157">Zeile: 1 Zeichen: 27</span><span class="sxs-lookup"><span data-stu-id="65526-157">At line:1 char:27</span></span>

<span data-ttu-id="65526-158">\+ Test-CsMcxPushNotification \<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="65526-158">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="65526-159">\+ CategoryInfo: OperationStopped: (:) \[ Test-CsMcxPushNotification \] , SyntheticTransactionException</span><span class="sxs-lookup"><span data-stu-id="65526-159">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="65526-160">\+ FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="65526-160">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="65526-161">Die Meldung "Push-Benachrichtigungsanforderung wurde abgelehnt" tritt in der Regel auf, wenn Sie die URL-Filterung aktiviert haben und die Präfixe http: und https: blockieren.</span><span class="sxs-lookup"><span data-stu-id="65526-161">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="65526-162">Sie können bestimmen, welche Präfixe blockiert werden, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="65526-162">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="65526-163">Wenn "http:" oder "https:" in den Ergebnissen angezeigt wird, müssen Sie Sie aus der Liste der blockierten Präfixe entfernen, damit Push-Benachrichtigungen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="65526-163">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="65526-164">Dies kann mithilfe von Befehlen wie den folgenden erfolgen:</span><span class="sxs-lookup"><span data-stu-id="65526-164">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="65526-165">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)".</span><span class="sxs-lookup"><span data-stu-id="65526-165">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

<span data-ttu-id="65526-166"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="65526-166"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

