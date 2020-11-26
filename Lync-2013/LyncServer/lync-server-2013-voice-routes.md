---
title: 'Lync Server 2013: VoIP-Routen'
description: 'Lync Server 2013: VoIP-Routen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91f3c548890c6d2a8c16808eebd9dd50e3ed2715
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49438792"
---
# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="db2f1-103">VoIP-Routen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db2f1-103">Voice routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="db2f1-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="db2f1-104">

<span> </span></span></span>

<span data-ttu-id="db2f1-105">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="db2f1-105">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="db2f1-106">Anrufrouten geben an, wie lync Server ausgehende Anrufe von Enterprise-VoIP-Benutzern abwickelt.</span><span class="sxs-lookup"><span data-stu-id="db2f1-106">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="db2f1-107">Wenn ein Benutzer eine Nummer wählt, normalisiert der Front-End-Server die Wählzeichenfolge bei Bedarf in das E. 164-Format und versucht, Sie mit einem SIP-URI zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="db2f1-107">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="db2f1-108">Wenn keine Zuordnung möglich ist, wendet der Server eine auf der Nummer basierende Routinglogik für ausgehende Anrufe an.</span><span class="sxs-lookup"><span data-stu-id="db2f1-108">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="db2f1-109">Der letzte Schritt zum Definieren der Logik besteht darin, eine separate benannte Anrufroute für jeden Satz von Zielrufnummern zu erstellen, die in den einzelnen Wählplänen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="db2f1-109">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="db2f1-110">Vor dem Definieren von Routen für ausgehende Anrufe sollten Sie die folgenden Schritte abschließen:</span><span class="sxs-lookup"><span data-stu-id="db2f1-110">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="db2f1-111">Stellen Sie einen oder mehrere Trunks bereit.</span><span class="sxs-lookup"><span data-stu-id="db2f1-111">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="db2f1-112">Erstellen Sie nach Bedarf Wählpläne für Standorte, Einzelpersonen und Kontaktobjekte.</span><span class="sxs-lookup"><span data-stu-id="db2f1-112">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="db2f1-113">Erstellen Sie PSTN-Verwendungseinträge (Public Switched Telephone Network, Telefonfestnetz)</span><span class="sxs-lookup"><span data-stu-id="db2f1-113">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="db2f1-p102">Sie müssen außerdem eine oder mehrere VoIP-Richtlinien erstellen und zuweisen, um das Routing ausgehender Anrufe zu aktivieren. Diese Aktion kann entweder vor oder nach der Definition ausgehender Anrufrouten durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="db2f1-p102">Additionally, to enable outbound call routing, you must create and assign one or more voice policies. You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="db2f1-116">Für jede Route müssen Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="db2f1-116">For each route, you must specify:</span></span>

  - <span data-ttu-id="db2f1-117">Einen Namen, mit dem die Route leicht identifiziert werden kann</span><span class="sxs-lookup"><span data-stu-id="db2f1-117">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="db2f1-118">Eine optionale Beschreibung in Fällen, in denen der Name allein möglicherweise nicht als Beschreibung der Route ausreicht</span><span class="sxs-lookup"><span data-stu-id="db2f1-118">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="db2f1-119">Den regulären Ausdruck für das Vergleichsmuster, das die Zielrufnummern identifiziert, auf die die Route angewendet wird, sowie Ausnahmen, auf die das Vergleichsmuster nicht angewendet wird</span><span class="sxs-lookup"><span data-stu-id="db2f1-119">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="db2f1-120">Einen oder mehrere Trunks, den Sie der Route zuweisen möchten</span><span class="sxs-lookup"><span data-stu-id="db2f1-120">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="db2f1-121">Die PSTN-Verwendungseinträge, über die Benutzer verfügen müssen, um Rufnummern anzurufen, die dem regulären Ausdruck für die Zielrufnummer entsprechen</span><span class="sxs-lookup"><span data-stu-id="db2f1-121">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="db2f1-122">Sie können in der lync Server-Systemsteuerung Anrufrouten angeben.</span><span class="sxs-lookup"><span data-stu-id="db2f1-122">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="db2f1-123">Diese Anrufrouten füllen die Server Routingtabelle aus, die von lync Server zum Weiterleiten von Anrufen verwendet wird, die für das PSTN bestimmt sind.</span><span class="sxs-lookup"><span data-stu-id="db2f1-123">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="db2f1-124">M:N-Trunkunterstützung</span><span class="sxs-lookup"><span data-stu-id="db2f1-124">M:N Trunk Support</span></span>

<span data-ttu-id="db2f1-125">Lync Server bietet Flexibilität bei der Weiterleitung von Anrufen an das PSTN.</span><span class="sxs-lookup"><span data-stu-id="db2f1-125">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="db2f1-126">Eine VoIP-Route gibt eine Reihe von Trunks für das PSTN an, die für einen bestimmten Sprachanruf verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="db2f1-126">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="db2f1-127">Ein trunk ordnet einen Vermittlungs Server und eine Portnummer einem PSTN-Gateway und einer Abhör Portnummer zu.</span><span class="sxs-lookup"><span data-stu-id="db2f1-127">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="db2f1-128">Diese logische Zuordnung ermöglicht es einem Vermittlungs Server, mehreren Gateways zugeordnet zu werden und über mehrere Verbindungen mit dem gleichen Gateway zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="db2f1-128">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="db2f1-129">Wenn Sie eine Anrufroute definieren, geben Sie die Trunks an, die dieser Route zugeordnet sind, aber Sie geben nicht an, welche Vermittlungsserver der Route zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="db2f1-129">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="db2f1-130">Wenn Sie Trunks erstellen möchten, indem Sie die Beziehungen zwischen Vermittlungsservern und PSTN-Gateways, IP-PBX-Anlagen und Session Border Controllers (SBCS) definieren, verwenden Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="db2f1-130">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="db2f1-131">Kostenoptimierter Verbindungsaufbau</span><span class="sxs-lookup"><span data-stu-id="db2f1-131">Least-Cost Routing</span></span>

<span data-ttu-id="db2f1-p105">Durch das Festlegen von Trunks, an die verschiedene Rufnummern weitergeleitet werden, können Sie die Routen bestimmen, die die geringsten Kosten verursachen, und sie entsprechend implementieren. Normalerweise wählen Sie Trunks aus, indem Sie den Trunk mit dem nächstgelegenen Gateway zum Standort der Zielrufnummer auswählen, um die Gebühren für Ferngespräche möglichst gering zu halten. Wenn Sie sich z. B. in New York befinden und eine Rufnummer in Rom wählen, leiten Sie den Anruf über das IP-Netzwerk an den Trunk mit dem Gateway in Ihrer Niederlassung in Rom weiter, sodass nur Gebühren für ein Ortsgespräch anfallen.</span><span class="sxs-lookup"><span data-stu-id="db2f1-p105">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly. The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges. For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="db2f1-135">Das folgende Beispiel zeigt eine Verwendungsmöglichkeit des kostenoptimierten Verbindungsaufbaus: Fabrikam beschließt, dass deutsche Benutzer Rufnummern in den USA über den US-Trunk wählen sollen.</span><span class="sxs-lookup"><span data-stu-id="db2f1-135">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="db2f1-136">Fabrikam möchte das System auch so konfigurieren, dass alle Anrufe von US-lync-Server Benutzern nach Deutschland und benachbarte Länder/Regionen auf dem Stamm mit dem Gateway in Deutschland beendet werden.</span><span class="sxs-lookup"><span data-stu-id="db2f1-136">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="db2f1-137">Durch dieses Routing wird Geld gespart, da ein Anruf von Deutschland nach Österreich beispielsweise weniger kostspielig ist als ein Anruf aus den USA nach Österreich.</span><span class="sxs-lookup"><span data-stu-id="db2f1-137">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="db2f1-138">Übersetzen ausgehender Wählzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="db2f1-138">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="db2f1-139">Lync Server 2013 erfordert wie seine unmittelbaren Vorgänger, dass alle Wählzeichenfolgen im E. 164-Format normalisiert werden, um eine Reverse-Number-Lookup-Funktion (RNL) durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="db2f1-139">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="db2f1-140">Für Trunks mit Gateways oder Private Branch Exchanges (PBX), die Zahlen erfordern, die in lokale Wähl Formate übersetzt werden, ermöglicht Ihnen lync Server 2013 die Erstellung einer oder mehrerer Regeln, die beim Manipulieren der angerufenen Zahl (also Anforderungs-URI) helfen, bevor Sie Sie an den trunk weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="db2f1-140">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="db2f1-141">Sie können beispielsweise eine Regel schreiben, mit der die Vorwahl +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="db2f1-141">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="db2f1-142">Mit lync Server 2013 können Sie eine oder mehrere Regeln erstellen, die Ihnen helfen, die Rufnummer zu manipulieren, bevor Sie Sie an den trunk weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="db2f1-142">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="db2f1-143">Bei der Planung Ihrer Trunks, die Gateways zuordnen: Port-Paare mit Mediation Server: Port-Paare, kann es hilfreich sein, Trunks mit ähnlichen lokalen wählanforderungen zu gruppieren, und daher die Anzahl der erforderlichen Übersetzungsregeln und die Zeitdauer für den Schreibvorgang zu verringern.</span><span class="sxs-lookup"><span data-stu-id="db2f1-143">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="db2f1-144">Konfigurieren der Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="db2f1-144">Configuring Caller ID</span></span>

<span data-ttu-id="db2f1-145">Lync Server bietet eine Möglichkeit zum Manipulieren der Rufnummernanzeige für ausgehende Anrufe.</span><span class="sxs-lookup"><span data-stu-id="db2f1-145">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="db2f1-146">Wenn eine Organisation beispielsweise die Durchwahlnummern der Mitarbeiter maskieren und durch die generische Firmen-oder Abteilungsnummer ersetzen möchte, kann ein Administrator dies mithilfe der lync Server-Systemsteuerung durchführen, um die Rufnummernanzeige zu unterdrücken und durch eine angegebene alternative Rufnummernanzeige zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="db2f1-146">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="db2f1-147">Denken Sie bei der Planung der Routinglogik darüber nach, für welche Einzelpersonen, Gruppen oder Standorte Sie diese Optionen verwenden möchten oder ob Sie sie sogar für alle Mitarbeiter verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="db2f1-147">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db2f1-p109">Für Anrufe, die über das Telefonfestnetz (PSTN) umgeleitet werden, wird die allgemeine Anrufer-ID anstelle der ursprünglichen Anrufer-ID angezeigt. Dies kann dazu führen, dass „Nicht stören“- oder Privatsphäreneinstellungen umgangen werden, die der angerufene Teilnehmer möglicherweise konfiguriert hat.</span><span class="sxs-lookup"><span data-stu-id="db2f1-p109">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID. This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="db2f1-150">Zusätzliche Routinglogik</span><span class="sxs-lookup"><span data-stu-id="db2f1-150">Additional Routing Logic</span></span>

<span data-ttu-id="db2f1-151">Beachten Sie bei der Erstellung von Routen für ausgehende Anrufe die folgenden Faktoren, die sich auf die Routinglogik auswirken können:</span><span class="sxs-lookup"><span data-stu-id="db2f1-151">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="db2f1-152">Wenn ein Anruf über eine Verbundgrenze hinweg eingerichtet wird, wird der Anruf mithilfe der Domäne im URI an das Unternehmen weitergeleitet, das für die Anwendung der Ausgangsroutinglogik verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="db2f1-152">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="db2f1-153">Wenn die im Anforderungs-URI angegebene Domäne nicht für das Unternehmen unterstützt wird, verarbeitet die Ausgangsroutingkomponente auf dem Server den Anruf nicht.</span><span class="sxs-lookup"><span data-stu-id="db2f1-153">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="db2f1-154">Wenn ein Benutzer nicht für Enterprise-VoIP aktiviert ist, wendet der Server gegebenenfalls eine andere Routinglogik an.</span><span class="sxs-lookup"><span data-stu-id="db2f1-154">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="db2f1-p110">Wenn der Anruf an ein vollständig besetztes Gateway (bei dem alle Trunkleitungen belegt sind) geroutet wird, weist das Gateway den Anruf zurück und die Ausgangsroutingkomponente leitet ihn an die Route mit den zweitgeringsten Kosten um. Bedenken Sie dies sorgfältig, da ein Gateway, dessen Größe auf ein kleines Büro in Europa (im Beispiel: Zürich) ausgerichtet ist, möglicherweise einen umfangreichen nicht lokalen Datenverkehr für Auslandsgespräche mit der Schweiz übertragen muss. Wenn das Gateway nicht die richtige Größe für diesen zusätzlichen Datenverkehr aufweist, werden Anrufe aus den USA in die Schweiz möglicherweise über ein Gateway in Deutschland weitergeleitet, was höhere Telefongebühren bedeutet.</span><span class="sxs-lookup"><span data-stu-id="db2f1-p110">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route. Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland. If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

<span data-ttu-id="db2f1-158"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="db2f1-158"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

