---
title: 'Lync Server 2013: Manuelles Erstellen oder Ändern einer Normalisierungsregel'
description: 'Lync Server 2013: Manuelles Erstellen oder Ändern einer Normalisierungsregel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7cc61706dd91b52822747d59693c8998d244c08
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431764"
---
# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a><span data-ttu-id="eb6a3-103">Manuelles Erstellen oder Ändern einer Normalisierungsregel in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb6a3-103">Create or modify a normalization rule manually in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="eb6a3-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="eb6a3-104">

<span> </span></span></span>

<span data-ttu-id="eb6a3-105">_**Letztes Änderungsdatum des Themas:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="eb6a3-105">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="eb6a3-106">Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel manuell erstellen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-106">Complete the following steps if you want to create or modify a normalization rule manually.</span></span> <span data-ttu-id="eb6a3-107">Wenn Sie eine Normalisierungsregel erstellen oder ändern möchten, indem Sie eine Normalisierungsregel in der lync Server-Systemsteuerung verwenden, finden Sie Informationen dazu unter Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung [in lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span><span class="sxs-lookup"><span data-stu-id="eb6a3-107">If you want to create or modify a normalization rule by using Build a Normalization Rule in Lync Server Control Panel, see [Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span></span>

<div>

## <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="eb6a3-108">So definieren Sie eine Normalisierungsregel manuell</span><span class="sxs-lookup"><span data-stu-id="eb6a3-108">To define a normalization rule manually</span></span>

1.  <span data-ttu-id="eb6a3-109">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="eb6a3-110">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="eb6a3-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="eb6a3-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eb6a3-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="eb6a3-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eb6a3-113">Optional Führen Sie die Schritte unter [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md) aus, oder [Ändern Sie einen Wählplan in lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="eb6a3-113">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

4.  <span data-ttu-id="eb6a3-114">Geben Sie unter **Neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten** im Feld **Name** einen beschreibenden Namen für das zu normalisierende Nummernmuster ein (weisen Sie der Normalisierungsregel beispielsweise den Namen **5DigitExtension** zu).</span><span class="sxs-lookup"><span data-stu-id="eb6a3-114">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule **5DigitExtension**).</span></span>

5.  <span data-ttu-id="eb6a3-115">(Optional) Geben Sie im Feld **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise „Übersetzt 5-stellige Durchwahlnummern“).</span><span class="sxs-lookup"><span data-stu-id="eb6a3-115">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="eb6a3-116">Klicken Sie in **Normalisierungsregel erstellen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-116">In **Build a Normalization Rule**, click **Edit**.</span></span>

7.  <span data-ttu-id="eb6a3-117">Geben Sie in **Regulären Ausdruck eingeben** Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="eb6a3-117">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="eb6a3-118">Geben Sie in **Dieses Muster abgleichen** das Muster an, das für den Abgleich der gewählten Telefonnummer verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-118">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    
      - <span data-ttu-id="eb6a3-119">Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-119">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>
    
    <span data-ttu-id="eb6a3-120">Wenn Sie beispielsweise **^ ( \\ d {7} ) $** in **Übereinstimmung mit diesem Muster** und **+ 1425 $1** in der **Übersetzungsregel** eingeben, normalisiert die Regel 5550100 auf + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-120">For example, if you enter **^(\\d{7})$** in **Match this pattern** and **+1425$1** in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="eb6a3-121">(Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl**.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-121">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="eb6a3-p104">(Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-p104">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb6a3-124">Sie können eine Normalisierungsregel speichern, die den Test nicht bestanden hat und sie später neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-124">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="eb6a3-125">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-125">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="eb6a3-126">Klicken Sie auf **OK**, um die Normalisierungsregel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-126">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="eb6a3-127">Klicken Sie auf **OK**, um die Wähleinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-127">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="eb6a3-128">Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-128">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb6a3-129">Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-129">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="eb6a3-130">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="eb6a3-130">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eb6a3-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb6a3-131">See Also</span></span>


[<span data-ttu-id="eb6a3-132">Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb6a3-132">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[<span data-ttu-id="eb6a3-133">Erstellen eines Wählplans in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb6a3-133">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="eb6a3-134">Ändern eines Wählplans in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb6a3-134">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="eb6a3-135">Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb6a3-135">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="eb6a3-136">Testen des VoIP-Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb6a3-136">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

<span data-ttu-id="eb6a3-137"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="eb6a3-137"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

