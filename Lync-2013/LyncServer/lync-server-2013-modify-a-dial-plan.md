---
title: 'Lync Server 2013: Ändern eines Wählplans'
description: 'Lync Server 2013: Ändern eines Wählplans'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e173552970c6b1799076b3f3b05d59ed6f0719e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49445915"
---
# <a name="modify-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="19f00-103">Ändern eines Wählplans in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19f00-103">Modify a dial plan in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="19f00-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="19f00-104">

<span> </span></span></span>

<span data-ttu-id="19f00-105">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="19f00-105">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="19f00-106">Führen Sie die Schritte im folgenden Verfahren aus, um einen vorhandenen Wählplan zu ändern.</span><span class="sxs-lookup"><span data-stu-id="19f00-106">To modify an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="19f00-107">Wenn Sie einen neuen Wählplan erstellen möchten, lesen Sie [Erstellen eines Wähl Plans in lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="19f00-107">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-modify-a-dial-plan"></a><span data-ttu-id="19f00-108">So ändern Sie einen Satz mit Wähleinstellungen</span><span class="sxs-lookup"><span data-stu-id="19f00-108">To modify a dial plan</span></span>

1.  <span data-ttu-id="19f00-109">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="19f00-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="19f00-110">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="19f00-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="19f00-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="19f00-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="19f00-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="19f00-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="19f00-113">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Wählplan**.</span><span class="sxs-lookup"><span data-stu-id="19f00-113">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="19f00-114">Doppelklicken Sie auf der Seite **Wähleinstellungen** auf einen Satz mit Wähleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="19f00-114">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="19f00-p104">Bereich und Name der Wähleinstellungen wurden beim Erstellen der Wähleinstellungen festgelegt. Sie können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="19f00-p104">The dial plan scope and name were set when the dial plan was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="19f00-117">(Optional) Bearbeiten Sie im Abschnitt **Wähleinstellungen bearbeiten** das Feld **Einfacher Name** (dieses wird mit dem Namen im Feld **Name** vorausgefüllt), um einen beschreibenderen Namen einzugeben, der den Standort, Dienst oder Benutzer angibt, für den die Wähleinstellungen gelten.</span><span class="sxs-lookup"><span data-stu-id="19f00-117">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="19f00-118">Der <STRONG>einfache Name</STRONG> muss bei allen Wählplänen innerhalb der lync Server 2013-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="19f00-118">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="19f00-119">Der Name darf nicht mehr als 256 Unicode-Zeichen umfassen und kann Buchstaben oder Zahlen, Bindestriche (-), Punkte (.), Pluszeichen (+) oder Unterstriche (_) enthalten.</span><span class="sxs-lookup"><span data-stu-id="19f00-119">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).</span></span><BR><span data-ttu-id="19f00-120">Leerzeichen sind im Feld <STRONG>Einfacher Name</STRONG> nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="19f00-120">Spaces are not allowed in the <STRONG>Simple name</STRONG> field.</span></span>

    
    </div>

6.  <span data-ttu-id="19f00-121">(Optional) Geben Sie im Feld **Beschreibung** beschreibende Informationen zu den Wähleinstellungen ein.</span><span class="sxs-lookup"><span data-stu-id="19f00-121">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7.  <span data-ttu-id="19f00-p106">(Optional) Wenn Sie diesen Wählplan als eine Region für Einwählnummern verwenden möchten, geben Sie eine **Einwahlkonferenzregion** an. Wenn Sie diesen Wählplan nicht für Einwählnummern verwenden möchten, lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="19f00-p106">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="19f00-124">Regionen für Einwahlkonferenzen werden benötigt, um Einwählnummern für Konferenzen einem oder mehreren Wählplänen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="19f00-124">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

8.  <span data-ttu-id="19f00-125">(Optional) Geben Sie im Feld **Präfix für externen Zugriff** nur dann einen Wert an, wenn Benutzer eine oder mehrere zusätzliche Nummern wählen müssen, um eine externe Leitung zu erhalten (z. B. 9).</span><span class="sxs-lookup"><span data-stu-id="19f00-125">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="19f00-126">Sie können einen Präfixwert mit bis zu vier Zeichen (also,, \# \* und 0-9) eingeben.</span><span class="sxs-lookup"><span data-stu-id="19f00-126">You can type in a prefix value of up to four characters (that is, \#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="19f00-127">Wenn Sie ein Präfix für den externen Zugriff eingeben, müssen Sie keine neue Normalisierungsregel zur Unterstützung des Präfix erstellen.</span><span class="sxs-lookup"><span data-stu-id="19f00-127">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

9.  <span data-ttu-id="19f00-128">Zuordnen und Konfigurieren von Normalisierungsregeln für die Wähleinstellungen:</span><span class="sxs-lookup"><span data-stu-id="19f00-128">Associate and configure normalization rules for the dial plan:</span></span>
    
      - <span data-ttu-id="19f00-129">Wenn Sie eine oder mehrere Regeln aus einer Liste aller Normalisierungsregeln auswählen möchten, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="19f00-129">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="19f00-130">Klicken Sie im Dialogfeld **Normalisierungsregeln auswählen** auf die Regeln, die Sie den Wähleinstellungen zuordnen möchten und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="19f00-130">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="19f00-131">Klicken Sie auf **Neu**, um eine neue Normalisierungsregel zu definieren und dem Wählplan zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="19f00-131">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="19f00-132">Details zum Definieren einer neuen Regel finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="19f00-132">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="19f00-133">Klicken Sie auf den Regelnamen und anschließend auf **Details einblenden**, um eine Normalisierungsregel zu bearbeiten, die bereits dem Wählplan zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="19f00-133">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="19f00-134">Ausführliche Informationen zum Bearbeiten der Regel finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="19f00-134">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="19f00-135">Um eine vorhandene Normalisierungsregel als Startpunkt für die Definition einer neuen Regel zu verwenden, markieren Sie den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="19f00-135">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="19f00-136">Details zum Bearbeiten der Kopie finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="19f00-136">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="19f00-137">Wenn Sie eine Normalisierungsregel aus dem Wählplan entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="19f00-137">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="19f00-138">Jedem Wählplan muss mindestens eine Normalisierungsregel zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="19f00-138">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="19f00-139">Details zum Ermitteln aller Normalisierungsregeln, die für einen Wählplan erforderlich sind, finden Sie unter <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Wählpläne und Normalisierungsregeln in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="19f00-139">For details about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

10. <span data-ttu-id="19f00-p113">Stellen Sie sicher, dass die Normalisierungsregeln für den Wählplan in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.</span><span class="sxs-lookup"><span data-stu-id="19f00-p113">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="19f00-142">Lync Server durchsucht die Normalisierungsregel Liste von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht.</span><span class="sxs-lookup"><span data-stu-id="19f00-142">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="19f00-143">Wenn Sie einen Wählplan so konfigurieren, dass eine gewählte Nummer mit mehr als einer Normalisierungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="19f00-143">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="19f00-144">Die Standard <STRONG>Keep All</STRONG> mäßige Normalisierungsregel <STRONG>^ (\d {11} ) $</STRONG> entspricht einer beliebigen 11-stelligen Zahl.</span><span class="sxs-lookup"><span data-stu-id="19f00-144">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="19f00-145">Wenn Sie beispielsweise eine Normalisierungsregel hinzufügen, die mit 11-stelligen Zahlen übereinstimmt, die mit 1425 beginnen, stellen Sie sicher, dass <STRONG>Alle beibehalten</STRONG> unter die restriktivere <STRONG>^ (1425 \ d {7} ) $</STRONG> -Regel sortiert ist.</span><span class="sxs-lookup"><span data-stu-id="19f00-145">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

11. <span data-ttu-id="19f00-p116">(Optional) Geben Sie eine Nummer zum Testen des Wählplans ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="19f00-p116">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="19f00-148">Sie können einen Wählplan speichern, der den Test nicht bestanden hat, und ihn später neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="19f00-148">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="19f00-149">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="19f00-149">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="19f00-150">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="19f00-150">Click **OK**.</span></span>

13. <span data-ttu-id="19f00-151">Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="19f00-151">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="19f00-152">Jedes Mal, wenn Sie einen Wählplan erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="19f00-152">Any time you create or modify a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="19f00-153">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="19f00-153">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="19f00-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19f00-154">See Also</span></span>


[<span data-ttu-id="19f00-155">Erstellen eines Wählplans in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19f00-155">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="19f00-156">Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19f00-156">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="19f00-157">Definieren von Normalisierungsregeln in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19f00-157">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

<span data-ttu-id="19f00-158"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="19f00-158"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

