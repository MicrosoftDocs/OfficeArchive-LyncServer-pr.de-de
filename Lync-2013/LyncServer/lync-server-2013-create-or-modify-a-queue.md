---
title: 'Lync Server 2013: Erstellen oder Ändern einer Warteschlange'
description: 'Lync Server 2013: Erstellen oder Ändern einer Warteschlange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbd8d6d00df8d6a09ef5861d876bd1363db09e3d
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431757"
---
# <a name="create-or-modify-a-queue-in-lync-server-2013"></a><span data-ttu-id="18de8-103">Erstellen oder Ändern einer Warteschlange in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18de8-103">Create or modify a queue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="18de8-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="18de8-104">

<span> </span></span></span>

<span data-ttu-id="18de8-105">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="18de8-105">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="18de8-106">Verwenden Sie eines der folgenden Verfahren, um eine Warteschleife zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="18de8-106">Use one of the following procedures to create or modify a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="18de8-107">So verwenden Sie die lync Server-Systemsteuerung zum Erstellen oder Ändern einer Warteschlange</span><span class="sxs-lookup"><span data-stu-id="18de8-107">To use Lync Server Control Panel to create or modify a queue</span></span>

1.  <span data-ttu-id="18de8-108">Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="18de8-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18de8-109">Wenn Sie einer der delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Reaktionsgruppen-Warteschleifen erstellen und ändern und diese den von Ihnen verwalteten Workflows zuweisen.</span><span class="sxs-lookup"><span data-stu-id="18de8-109">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="18de8-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="18de8-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="18de8-111">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="18de8-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="18de8-112">Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Warteschleife**.</span><span class="sxs-lookup"><span data-stu-id="18de8-112">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="18de8-113">Führen Sie auf der Seite **Warteschleife** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="18de8-113">On the **Queue** page, do one of the following:</span></span>
    
      - <span data-ttu-id="18de8-114">Klicken Sie zum Erstellen einer neuen Warteschleife auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="18de8-114">To create a new queue, click **New**.</span></span> <span data-ttu-id="18de8-115">Geben Sie in **Dienst auswählen** den Namen des **ApplicationServer**-Diensts, zu dem Sie die Warteschleife hinzufügen möchten, vollständig oder teilweise in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="18de8-115">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="18de8-116">Klicken Sie in der Dienstliste auf den gewünschten Dienst und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="18de8-116">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="18de8-p103">Geben Sie den Warteschleifennamen vollständig oder teilweise in das Suchfeld ein, um eine vorhandene Warteschleife zu ändern. Klicken Sie in der Warteschleifenliste auf die gewünschte Warteschleife, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="18de8-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="18de8-119">Geben Sie bei **Name** einen Namen ein, mit dem die Warteschleife bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="18de8-119">In **Name**, type an identifying name for the queue.</span></span>

6.  <span data-ttu-id="18de8-120">Geben Sie in **Beschreibung** eine Beschreibung für die Warteschleife ein.</span><span class="sxs-lookup"><span data-stu-id="18de8-120">In **Description**, type a description for the queue.</span></span>

7.  <span data-ttu-id="18de8-p104">Geben Sie in **Gruppen** die Gruppen an, die Sie der Warteschleife zuweisen möchten. Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="18de8-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span>
    
      - <span data-ttu-id="18de8-p105">Klicken Sie auf **Auswählen**, um eine Gruppe zu der Warteschleife hinzuzufügen. Geben Sie im Suchfeld **Gruppen auswählen** den Namen der Agentgruppe, die Sie der Warteschleife zuweisen möchten, teilweise oder vollständig ein, klicken Sie auf die gewünschte Agentgruppe und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="18de8-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="18de8-125">Um eine Gruppe aus der Warteschleife zu entfernen, klicken Sie in der Liste der Agentgruppen auf die Gruppe, die Sie entfernen möchten und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="18de8-125">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="18de8-126">Um die Reihenfolge zu ändern, in der Agents durchsucht werden, klicken Sie in der Liste der Agentgruppen auf eine Gruppe und klicken Sie dann auf den Pfeil nach oben oder nach unten.</span><span class="sxs-lookup"><span data-stu-id="18de8-126">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="18de8-p106">Bei der Suche des Servers nach einem verfügbaren Agent werden Gruppen in der vorhandenen Reihenfolge durchlaufen. Die erste Gruppe in der Liste wird also zuerst durchsucht, dann die zweite Gruppe in der Liste usw.</span><span class="sxs-lookup"><span data-stu-id="18de8-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span>

        
        </div>

8.  <span data-ttu-id="18de8-129">Wenn Sie eine Höchstdauer für die Wartezeit eines Anrufers festlegen möchten, bevor ein Agent den Anruf entgegennimmt, aktivieren Sie das Kontrollkästchen **Timeout für Warteschleife aktivieren** und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="18de8-129">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="18de8-130">Geben Sie in **Timeout (Sekunden)** die maximale Anzahl von Sekunden an, die ein Anrufer auf die Entgegennahme des Anrufs durch einen Agent wartet.</span><span class="sxs-lookup"><span data-stu-id="18de8-130">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    2.  <span data-ttu-id="18de8-131">Wählen Sie in **Anrufaktion** die Aktion aus, die bei einem Timeout für einen Anruf durchgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="18de8-131">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="18de8-132">Klicken Sie auf **Trennen**, um die Verbindung nach Ablauf der angegebenen Zeitdauer zu trennen.</span><span class="sxs-lookup"><span data-stu-id="18de8-132">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="18de8-133">Um den Anruf an die Voicemail weiterzuleiten, klicken Sie auf **an Voicemail weiterleiten**, und geben Sie dann im Feld **SIP-Adresse** im Format SIP: (Beispiels \<username\> @ \<domainname\> Weise SIP:Bob@contoso.com) eine Voicemail-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="18de8-133">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="18de8-134">Wenn Sie den Anruf an eine andere Telefonnummer weiterleiten möchten, klicken Sie auf **an Telefonnummer weiterleiten**, und geben Sie dann im Feld **SIP-Adresse** die Telefonnummer im Format SIP: \<number\> @ \<domainname\> (beispielsweise SIP:+14255550121@contoso.com) ein.</span><span class="sxs-lookup"><span data-stu-id="18de8-134">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="18de8-135">Wenn Sie den Anruf an einen anderen Benutzer weiterleiten möchten, klicken Sie auf **an SIP-Adresse weiterleiten**, und geben Sie dann im Feld **SIP-Adresse** den URI für den Benutzer im Format SIP: ein \<username\> @ \<domainname\> .</span><span class="sxs-lookup"><span data-stu-id="18de8-135">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="18de8-136">Klicken Sie auf **An andere Warteschleife weiterleiten** und suchen Sie dann die gewünschte Warteschleife, um den Anruf an eine andere Warteschleife weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="18de8-136">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

9.  <span data-ttu-id="18de8-137">Um eine maximale Anzahl der Anrufe anzugeben, die in der Warteschleife enthalten sein können, aktivieren Sie das Kontrollkästchen **Warteschleifenüberlauf aktivieren** und führen Sie dann die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="18de8-137">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="18de8-138">Wählen Sie im Feld **Maximale Anzahl von Anrufen** die maximale Anzahl von Anrufen aus, die die Warteschleife enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="18de8-138">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span>
    
    2.  <span data-ttu-id="18de8-139">Wählen Sie in **Anruf weiterleiten** aus, welcher Anruf weitergeleitet werden soll, wenn die Warteschleife voll ist: **Neuester Anruf** oder **Ältester Anruf**.</span><span class="sxs-lookup"><span data-stu-id="18de8-139">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    3.  <span data-ttu-id="18de8-140">Wählen Sie in **Anrufaktion** die Aktion aus, die bei Erreichen des Schwellenwerts für den Überlauf durchgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="18de8-140">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="18de8-141">Klicken Sie auf **Trennen**, um die Verbindung nach Ablauf der angegebenen Zeitdauer zu trennen.</span><span class="sxs-lookup"><span data-stu-id="18de8-141">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="18de8-142">Um den Anruf an die Voicemail weiterzuleiten, klicken Sie auf **an Voicemail weiterleiten**, und geben Sie dann im Feld **SIP-Adresse** im Format SIP: (Beispiels \<username\> @ \<domainname\> Weise SIP:Bob@contoso.com) eine Voicemail-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="18de8-142">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="18de8-143">Wenn Sie den Anruf an eine andere Telefonnummer weiterleiten möchten, klicken Sie auf **an Telefonnummer weiterleiten**, und geben Sie dann im Feld **SIP-Adresse** die Telefonnummer im Format SIP: \<number\> @ \<domainname\> (beispielsweise SIP:+14255550121@contoso.com) ein.</span><span class="sxs-lookup"><span data-stu-id="18de8-143">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="18de8-144">Wenn Sie den Anruf an einen anderen Benutzer weiterleiten möchten, klicken Sie auf **an SIP-Adresse weiterleiten**, und geben Sie dann im Feld **SIP-Adresse** den URI für den Benutzer im Format SIP: ein \<username\> @ \<domainname\> .</span><span class="sxs-lookup"><span data-stu-id="18de8-144">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="18de8-145">Klicken Sie auf **An andere Warteschleife weiterleiten** und suchen Sie dann die gewünschte Warteschleife, um den Anruf an eine andere Warteschleife weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="18de8-145">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

10. <span data-ttu-id="18de8-146">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="18de8-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a><span data-ttu-id="18de8-147">So verwenden Sie Windows PowerShell zum Erstellen oder Ändern einer Warteschlange</span><span class="sxs-lookup"><span data-stu-id="18de8-147">To use Windows PowerShell to create or modify a queue</span></span>

1.  <span data-ttu-id="18de8-148">Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="18de8-148">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18de8-149">Wenn Sie einer der delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Agentgruppen und Warteschleifen erstellen und Warteschleifen Agentgruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="18de8-149">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span>

    
    </div>

2.  <span data-ttu-id="18de8-150">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="18de8-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="18de8-p107">Erstellen Sie die Ansage, die abgespielt werden soll, wenn der Schwellenwert für den Warteschleifen-Timeout erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="18de8-p107">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="18de8-153">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="18de8-153">For example:</span></span>
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18de8-154">Verwenden Sie das <STRONG>Import-CsRgsAudioFile</STRONG>-Cmdlet, um eine Audiodatei als Ansage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="18de8-154">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="18de8-155">Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">importieren-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="18de8-155">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="18de8-p109">Legen Sie die auszuführende Aktion fest, wenn der Schwellenwert für den Warteschleifen-Timeout erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="18de8-p109">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18de8-158">Details zu möglichen Aktionen und deren Syntax finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="18de8-158">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="18de8-159">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="18de8-159">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  <span data-ttu-id="18de8-p110">Erstellen Sie die Ansage, die abgespielt werden soll, wenn der Schwellenwert für den Warteschleifen-Überlauf erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="18de8-p110">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="18de8-162">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="18de8-162">For example:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18de8-163">Verwenden Sie das <STRONG>Import-CsRgsAudioFile</STRONG>-Cmdlet, um eine Audiodatei als Ansage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="18de8-163">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="18de8-164">Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">importieren-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="18de8-164">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="18de8-p112">Legen Sie die auszuführende Aktion fest, wenn der Schwellenwert für den Warteschleifen-Überlauf erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="18de8-p112">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18de8-167">Details zu möglichen Aktionen und deren Syntax finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="18de8-167">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="18de8-168">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="18de8-168">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  <span data-ttu-id="18de8-p113">Rufen Sie den Dienstnamen für den Reaktionsgruppendienst ab und weisen Sie ihn einer Variablen zu. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="18de8-p113">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  <span data-ttu-id="18de8-p114">Identität einer Agentgruppe abrufen, die der Warteschleife zugeordnet werden soll. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="18de8-p114">Get the identity of the agent group to be assigned to the queue. At the command line, run:</span></span>
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18de8-173">Details zum Erstellen der Agentengruppe finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span><span class="sxs-lookup"><span data-stu-id="18de8-173">For details about creating the agent group, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span></span>

    
    </div>

9.  <span data-ttu-id="18de8-p115">Die Warteschleife erstellen. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="18de8-p115">Create the queue. At the command line, run:</span></span>
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    <span data-ttu-id="18de8-176">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="18de8-176">For example:</span></span>
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. <span data-ttu-id="18de8-p116">Bestätigen Sie, dass die Warteschleife erstellt wurde. Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="18de8-p116">Confirm that the queue is created. Run:</span></span>
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="18de8-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18de8-179">See Also</span></span>


[<span data-ttu-id="18de8-180">Neu – CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="18de8-180">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[<span data-ttu-id="18de8-181">Satz-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="18de8-181">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[<span data-ttu-id="18de8-182">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="18de8-182">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="18de8-183">Neu – CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="18de8-183">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[<span data-ttu-id="18de8-184">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="18de8-184">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[<span data-ttu-id="18de8-185">Importieren-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="18de8-185">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[<span data-ttu-id="18de8-186">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="18de8-186">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

<span data-ttu-id="18de8-187"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="18de8-187"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

