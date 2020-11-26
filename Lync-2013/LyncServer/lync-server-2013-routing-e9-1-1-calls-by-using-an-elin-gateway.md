---
title: 'Lync Server 2013: Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway'
description: 'Lync Server 2013: Routing von E9-1-1-Anrufen mithilfe eines Elin-Gateways.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9ddbdbbdf10f9eecbffecaaf8416718bbdcf224
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49442302"
---
# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a><span data-ttu-id="d6f8e-103">Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6f8e-103">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="d6f8e-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="d6f8e-104">

<span> </span></span></span>

<span data-ttu-id="d6f8e-105">_**Letztes Änderungsdatum des Themas:** 2013-02-05_</span><span class="sxs-lookup"><span data-stu-id="d6f8e-105">_**Topic Last Modified:** 2013-02-05_</span></span>

<span data-ttu-id="d6f8e-106">Einige Partner des Unified Communications Open Interoperability-Programms bieten qualifizierte Notfall Standort-Identifikationsnummern (Elin)-fähige Gateways, die als Alternative zu einer SIP Trunk-Verbindung zu einem qualifizierten E9-1-1-Service-Anbieter dienen können.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-106">Some partners in the Unified Communications Open Interoperability Program provide qualified Emergency Location Identification Number (ELIN)-capable gateways, which can serve as an alternative to a SIP trunk connection to a qualified E9-1-1 service provider.</span></span> <span data-ttu-id="d6f8e-107">Elin-Gateways unterstützen die ISDN-oder zentralisierte Cama-Konnektivität (Automatic Message Accounting) zu Public Switched Telephone Network (PSTN)-basierenden E9-1-1-Diensten.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-107">ELIN gateways support ISDN or Centralized Automatic Message Accounting (CAMA) connectivity to public switched telephone network (PSTN)-based E9-1-1 services.</span></span> <span data-ttu-id="d6f8e-108">Details zu Partnern, die Elin-Gateways und Links zu deren Dokumentation bereitstellen, finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425) .</span><span class="sxs-lookup"><span data-stu-id="d6f8e-108">For details about partners who provide ELIN gateways and links to their documentation, see [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425).</span></span>

<span data-ttu-id="d6f8e-109">Wie SIP-Trunk-Verbindungen mit E9-1-1-Service-Anbietern bieten Elin-Gateways auch die Möglichkeit, einen Notruf an den am besten geeigneten öffentlichen Sicherheits Beantwortungs Punkt (PSAP) des Anrufers zu leiten, doch diese Gateways verwenden eine Elin als Standort-ID.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-109">Like SIP trunk connections to E9-1-1 service providers, ELIN gateways also provide the means of routing an emergency call to the caller's most appropriate Public Safety Answering Point (PSAP), but these gateways use an ELIN as the location identifier.</span></span> <span data-ttu-id="d6f8e-110">Sie definieren Elins für jeden Emergency Response Location (ERL) in Ihrer Organisation (Details finden Sie unter [Verwalten von Speicherorten für Elin-Gateways in lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span><span class="sxs-lookup"><span data-stu-id="d6f8e-110">You define ELINs for each Emergency Response Location (ERL) in your organization (for details, see [Managing locations for ELIN gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span></span>

<span data-ttu-id="d6f8e-111">Wenn Sie ein Elin-Gateway für Notrufe verwenden, verwenden Sie dieselbe lync Server E9-1-1-Infrastruktur, die Sie für eine SIP-Trunk-Verbindung verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-111">When you use an ELIN gateway for emergency calls, you use the same Lync Server E9-1-1 infrastructure that you would use for a SIP trunk connection.</span></span> <span data-ttu-id="d6f8e-112">Das bedeutet, dass die standortinformationsdienst-Datenbank den Standort für den lync Server-Client bereitstellt und die Standortrichtlinie das Feature aktiviert und das Routing definiert.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-112">That is, the Location Information service database provides the location to the Lync Server client, and the location policy enables the feature and defines the routing.</span></span> <span data-ttu-id="d6f8e-113">Mit einem Elin-Gateway müssen Sie jedoch die Elins zur standortinformationsdienst-Datenbank hinzufügen und ihren PSTN-Netzbetreiber in die Datenbank "Automatic Location Identification (Ali)" hochladen.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-113">With an ELIN gateway, however, you need to add the ELINs to the Location Information service database and have your PSTN carrier upload them to the Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="d6f8e-114">Wenn ein lync-Client seinen Standort über den standortinformationsdienst erhält, enthält der Standort den Elin.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-114">When a Lync client obtains its location from the Location Information service, the location includes the ELIN.</span></span> <span data-ttu-id="d6f8e-115">Während eines Notrufs ist der Elin-Standort im Lieferumfang des Elin-Gateways enthalten.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-115">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span></span> <span data-ttu-id="d6f8e-116">Das Elin-Gateway identifiziert den Anruf als Notruf und tauscht die Nummer des Anrufers mit dem Elin aus.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-116">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span></span> <span data-ttu-id="d6f8e-117">Das Elin-Gateway leitet dann den Anruf an das PSTN mit dem Elin als Rufnummer weiter.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-117">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span></span> <span data-ttu-id="d6f8e-118">Der PSTN E9-1-1-Anbieter sucht nach dem Elin in der Ali-Datenbank, die eine Begleit Datenbank zur Master Street Address Guide (MSAG)-Datenbank ist.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-118">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span></span> <span data-ttu-id="d6f8e-119">Das PSTN sendet dann den Anruf an die am besten geeignete PSAP basierend auf dem Ali-Lookup, und der PSAP sendet erste Responder an den Standort des Anrufers, basierend auf dem Ali-Lookup.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-119">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span></span> <span data-ttu-id="d6f8e-120">Die Rufnummer wird für einen vordefinierten Zeitraum für Rückrufe auf dem Elin-Gateway zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-120">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span></span> <span data-ttu-id="d6f8e-121">Während eines Rückrufs erreicht der PSAP das Elin-Gateway, das die Elin-Nummer für die direkte Durchwahlnummer des Anrufers ersetzt.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-121">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span></span>

<span data-ttu-id="d6f8e-122">ELIN-Gateways unterstützen Notrufe nur innerhalb des Netzwerks Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-122">ELIN gateways support emergency calls only from within your organization's network.</span></span> <span data-ttu-id="d6f8e-123">Notrufe von außerhalb dieses Netzwerks werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-123">They do not support emergency calls made from outside your network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6f8e-124">Details zur Verwendung einer SIP Trunk-Verbindung für Notrufe finden Sie unter <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing von E9-1-1-Anrufen mithilfe eines SIP-Trunks in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-124">For details about using a SIP trunk connection for emergency calls, see <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="d6f8e-125">Das folgende Diagramm zeigt, wie ein Notfall Anruf von lync Server an die PSAP weitergeleitet wird, wenn Sie ein Elin-Gateway verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-125">The following diagram shows how an emergency call is routed from Lync Server to the PSAP when you use an ELIN gateway.</span></span>

<span data-ttu-id="d6f8e-126">**Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway**</span><span class="sxs-lookup"><span data-stu-id="d6f8e-126">**Routing E9-1-1 calls with an ELIN gateway**</span></span>

<span data-ttu-id="d6f8e-127">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span><span class="sxs-lookup"><span data-stu-id="d6f8e-127">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span></span>

1.  <span data-ttu-id="d6f8e-128">Eine SIP-Einladung, die den Standort, die Rückrufnummer des Anrufers und die (optionale) Benachrichtigungs-URL und die Konferenz-Rückrufnummer enthält, wird an lync Server weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-128">A SIP INVITE containing the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="d6f8e-129">Lync Server vergleicht die Notrufnummer und leitet den Anruf (basierend auf dem in der jeweiligen Standortrichtlinie definierten **PSTN-Nutzungs** Wert) an einen Vermittlungsserver und von dort aus an ein Elin-Gateway weiter.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-129">Lync Server matches the emergency number and then routes the call (based on the **PSTN Usage** value defined in the applicable location policy) to a Mediation Server, and from there to an ELIN gateway.</span></span>

3.  <span data-ttu-id="d6f8e-130">Das ELIN-Gateway leitet den Anruf über einen ISDN- oder CAMA-Trunk an das PSTN weiter.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-130">The ELIN gateway routes the call over an ISDN or CAMA trunk to the PSTN.</span></span>

4.  <span data-ttu-id="d6f8e-p106">Das PSTN identifiziert den Anruf als Notruf und leitet ihn an einen selektiven E9-1-1-Router im Netzwerk weiter. Der selektive E9-1-1-Router schlägt die Nummer des Anrufers in der ALI-Datenbank nach, um seinen geografischen Standort zu bestimmen. Anschließend sendet der selektive E9-1-1-Router den Anruf an den (nach der ALI-Datenbank) nächstgelegenen PSAP. </span><span class="sxs-lookup"><span data-stu-id="d6f8e-p106">The PSTN identifies the call as an emergency call and routes it to an E9-1-1 selective router in the network. The E9-1-1 selective router looks up the caller's number in the ALI database to obtain the geographical location. The E9-1-1 selective router sends the call to the most appropriate PSAP based on the location information that was retrieved from the ALI database.</span></span>

5.  <span data-ttu-id="d6f8e-134">Wenn Sie die ortungsrichtlinie für Benachrichtigungen konfiguriert haben, werden einem oder mehreren Sicherheitsbeauftragten Ihrer Organisation eine spezielle Sofortnachricht zur lync-Notfallbenachrichtigung gesendet.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-134">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="d6f8e-135">Diese Meldung wird immer auf dem Bildschirm des Security Officers eingeblendet und enthält den Namen des Anrufers, die Telefonnummer, die Uhrzeit und den Standort, sodass das Sicherheitspersonal schnell auf den Notruf Anrufer reagieren kann, indem er eine Sofortnachricht oder eine Stimme verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-135">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

6.  <span data-ttu-id="d6f8e-p108">Wenn der Anruf vorzeitig unterbrochen wird, kontaktiert der PSAP den Anrufer mithilfe der ELIN direkt. Das ELIN-Gateway tauscht die ELIN mit der DID des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d6f8e-p108">If the call is broken prematurely, the PSAP uses the ELIN to contact the caller directly. The ELIN gateway swaps the ELIN for the caller's DID.</span></span>

<span data-ttu-id="d6f8e-138"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="d6f8e-138"></div>

<span> </span>

</div>

</div>

</span></span></div>

