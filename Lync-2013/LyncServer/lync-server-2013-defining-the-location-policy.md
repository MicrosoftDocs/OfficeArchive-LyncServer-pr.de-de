---
title: 'Lync Server 2013: Definieren der Standortrichtlinie'
description: 'Lync Server 2013: Definieren der Standortrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fddd5b2ce34e44240162e886672a236789857e7b
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49430980"
---
# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="1f7f3-103">Definieren der Standortrichtlinie für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f7f3-103">Defining the location policy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="1f7f3-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="1f7f3-104">

<span> </span></span></span>

<span data-ttu-id="1f7f3-105">_**Letztes Änderungsdatum des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="1f7f3-105">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="1f7f3-106">Jede Standortrichtlinie enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="1f7f3-106">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="1f7f3-107">**Notfalldienste aktiviert**</span><span class="sxs-lookup"><span data-stu-id="1f7f3-107">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="1f7f3-108">Wenn dieser Wert **Ja** ist, ist der Client für E9-1-1 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-108">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="1f7f3-109">Wenn ein Client registriert wird, versucht er, einen Standort vom standortinformationsdienst abzurufen, und die Standortinformationen werden als Teil eines Notrufs aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-109">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="1f7f3-110">**Ort erforderlich**</span><span class="sxs-lookup"><span data-stu-id="1f7f3-110">**Location Required**</span></span>  
    <span data-ttu-id="1f7f3-111">Diese Einstellung wird nur verwendet, wenn " **Emergency Services Enabled** " auf " **Ja**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-111">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="1f7f3-112">Sie können die Einstellung **Standort erforderlich** konfigurieren, um das Clientverhalten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-112">You can configure the **Location Required** setting to define the client behavior.</span></span> <span data-ttu-id="1f7f3-113">Wenn der Wert auf **Nein** festgelegt wird, bedeutet dies, dass der Benutzer nicht zur Angabe eines Standorts aufgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-113">Setting the value to **No** means that the user will not be prompted for a location.</span></span> <span data-ttu-id="1f7f3-114">Wenn der Wert auf **Ja** festgelegt wird, bedeutet dies, dass der Benutzer zur Angabe eines Standorts aufgefordert wird; er kann die Aufforderung aber verwerfen.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-114">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="1f7f3-115">Wenn Sie den Wert auf **Disclaimer** setzen, wird der Benutzer aufgefordert, einen Speicherort einzugeben, und es wird auch ein Haftungsausschluss angezeigt, wenn er versucht, die Eingabeaufforderung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-115">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="1f7f3-116">In allen Fällen kann der Benutzer den Client weiterhin verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-116">In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f7f3-p103">Der Haftungsausschluss wird nicht angezeigt, wenn der Benutzer vor der Aktivierung für E9-1-1 bereits manuell einen Standort eingegeben hat. Aktualisierte Versionen des Haftungsausschlusses werden Benutzern nicht angezeigt, die den Haftungsausschluss bereits angezeigt haben. </span><span class="sxs-lookup"><span data-stu-id="1f7f3-p103">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="1f7f3-119">**Haftungsausschluss der erweiterten Notfalldienste**</span><span class="sxs-lookup"><span data-stu-id="1f7f3-119">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="1f7f3-120">Diese Einstellung gibt den Haftungsausschluss an, der Benutzern angezeigt wird, wenn sie die Eingabeaufforderung für einen Standort verwerfen.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-120">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="1f7f3-121">In lync Server 2013 können Sie mithilfe der ortungsrichtlinie verschiedene Haftungsausschlüsse für verschiedene Gebietsschemas oder verschiedene Gruppen von Benutzern festlegen.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-121">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f7f3-122">Diese Einstellung für Standortrichtlinien unterscheidet sich von lync Server 2010, bei dem Sie das Cmdlet " <STRONG>festlegen-CsEnhancedEmergencyServiceDisclaimer</STRONG> " verwendet haben, um einen globalen Haftungsausschluss für die gesamte Organisation festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-122">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="1f7f3-123">Wenn bereits ein globaler Haftungsausschluss vorhanden ist, müssen Sie diesen Haftungsausschluss in der Standortrichtlinie angeben.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-123">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="1f7f3-124">Das bedeutet, dass lync Server 2013 nur in der Standortrichtlinie angegebene Haftungsausschlüsse verwendet.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-124">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="1f7f3-125">**Notfall Wahl Zeichenfolge**</span><span class="sxs-lookup"><span data-stu-id="1f7f3-125">**Emergency Dial String**</span></span>  
    <span data-ttu-id="1f7f3-126">Diese Wählzeichenfolge (abzüglich des führenden "+", aber einschließlich einer Normalisierung, die vom Wählplan des lync-Benutzers ausgeführt wird) bedeutet, dass ein Anruf ein Notruf ist.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-126">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="1f7f3-127">Die **Notrufwählzeichenfolge** veranlasst den Client, Standort- und Rückrufinformationen mit dem Anruf zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f7f3-128">Wenn in Ihrer Organisation kein Präfix für den Zugriff auf externe Leitungen verwendet wird, müssen Sie keine entsprechende Normalisierungsregel für Wähleinstellungen erstellen, die der 911-Zeichenfolge vor dem Senden des Anrufs an ausgehendes Routing auf einem lync-Pool Server ein "+" hinzufügt. Das "+" wird dem lync-Client automatisch als Ergebnis der ortungsrichtlinie vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="1f7f3-129">Wenn Ihre Website jedoch ein externes Zugriffs Präfix verwendet, müssen Sie der entsprechenden Wähl Plan Richtlinie eine Normalisierungsregel hinzufügen, die das Präfix für den externen Zugriff abstreift und das "+" hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="1f7f3-130">Wenn Ihr Standort beispielsweise ein Präfix für den externen Zugriff von 9 verwendet und ein Benutzer 9 911 anwählt, &nbsp; um einen Notruf zu tätigen, wird der Client seine Wähl Plan Richtlinie verwenden, um diese auf + 911 zu normalisieren, bevor die gewählte Nummer von den Routen im Standortprofil des Anrufers ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-130">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="1f7f3-131">**Notrufnummern-Zeichenfolgen Masken**</span><span class="sxs-lookup"><span data-stu-id="1f7f3-131">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="1f7f3-132">Eine durch Semikolons getrennte Liste von Wählzeichenfolgen, die in die angegebene **Notruf Zeichenfolge** übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="1f7f3-133">So können Sie beispielsweise 112 hinzufügen, die für den größten Teil Europas die Notrufnummer ist.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="1f7f3-134">Ein Besucher von lync-Benutzern aus Europa weiß möglicherweise nicht, dass 911 die US-Notfallnummer ist, aber Sie können 112 anrufen und dasselbe Ergebnis erzielen.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-134">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="1f7f3-135">Geben Sie wie bei der Notruf Zeichenfolge keine "+" vor jeder Zahl ein, und wenn Sie die Zugriffscodes für externe Leitungen verwenden, stellen Sie sicher, dass in der Wähl Plan Richtlinie des Benutzers Normalisierungsregeln vorhanden sind, um die Zugriffscode Ziffer abzustreifen.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-135">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="1f7f3-136">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="1f7f3-136">**PSTN Usage**</span></span>  
    <span data-ttu-id="1f7f3-137">Der Name der PSTN-Verwendung mit den Routingpfaden, die bestimmen, an welchen SIP-Trunk bzw. an welches PSTN- oder ELIN-Gateway Notrufe weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f7f3-p109">Einer Standortrichtlinie kann nur eine Verwendung zugewiesen werden. Diese PSTN-Verwendung setzt die PSTN-Verwendungen außer Kraft, die der VoIP-Richtlinie des Benutzers zugewiesen sind. Dies gilt jedoch nur für Anrufe, die mit der Notrufwählzeichenfolge oder einer der Masken für Notrufwählzeichenfolgen abgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-p109">Only one usage can be assigned to a location policy. This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="1f7f3-140">**Benachrichtigungs-URI**</span><span class="sxs-lookup"><span data-stu-id="1f7f3-140">**Notification URI**</span></span>  
    <span data-ttu-id="1f7f3-p110">Gibt mindestens einen SIP-URI des Sicherheitspersonals an, das bei einem Notruf per Sofortnachricht benachrichtigt wird. Verteilergruppen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-p110">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="1f7f3-143">**Konferenz-URI**</span><span class="sxs-lookup"><span data-stu-id="1f7f3-143">**Conference URI**</span></span>  
    <span data-ttu-id="1f7f3-144">Gibt eine DID-Nummer (Direct Inward Dialing) an (in der Regel eine Sicherheitsdesknummer), die bei einem Notruf per Konferenz zugeschaltet werden soll.  </span><span class="sxs-lookup"><span data-stu-id="1f7f3-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="1f7f3-145">**Konferenzmodus**</span><span class="sxs-lookup"><span data-stu-id="1f7f3-145">**Conference Mode**</span></span>  
    <span data-ttu-id="1f7f3-146">Gibt an, ob bei der Zuschaltung des Konferenz-URI zum Notruf eine unidirektionale oder bidirektionale Kommunikation verwendet wird. </span><span class="sxs-lookup"><span data-stu-id="1f7f3-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="1f7f3-147">**Standortaktualisierungsintervall**</span><span class="sxs-lookup"><span data-stu-id="1f7f3-147">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="1f7f3-148">Gibt die Zeitspanne (in Stunden) zwischen Clientanforderungen für ein Standort Update vom standortinformationsdienst an.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="1f7f3-149">Dieser Wert kann auf einen beliebigen Wert zwischen 1 und 12 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="1f7f3-150">Der Standardwert lautet 4.</span><span class="sxs-lookup"><span data-stu-id="1f7f3-150">The default value is 4.</span></span>

<span data-ttu-id="1f7f3-151"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="1f7f3-151"></div>

<span> </span>

</div>

</div>

</span></span></div>

