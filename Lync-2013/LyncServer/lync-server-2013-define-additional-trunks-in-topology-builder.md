---
title: 'Lync Server 2013: Definieren zusätzlicher Trunks im Topologie-Generator'
description: 'Lync Server 2013: Definieren zusätzlicher Trunks im Topologie-Generator'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57983d3e4d6a47c14f2dcdc153fe6872a33eb6e9
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431116"
---
# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="86772-103">Definieren zusätzlicher Trunks im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86772-103">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="86772-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="86772-104">

<span> </span></span></span>

<span data-ttu-id="86772-105">_**Letztes Änderungsdatum des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="86772-105">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="86772-106">Führen Sie die folgenden Schritte aus, um mithilfe des Topologie-Generators einen zusätzlichen trunk zu definieren, dem Sie einen *Peer* einem Vermittlungs Server zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="86772-106">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="86772-107">Ein Peer bietet Benutzern, die für Enterprise-VoIP aktiviert sind, Verbindungen mit dem öffentlich geschalteten Telefonnetz (PSTN).</span><span class="sxs-lookup"><span data-stu-id="86772-107">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="86772-108">Bei einem Peer kann es sich um ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten handeln.</span><span class="sxs-lookup"><span data-stu-id="86772-108">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="86772-109">Der trunk definiert diese Verbindung zwischen dem Vermittlungs Server und dem Peer.</span><span class="sxs-lookup"><span data-stu-id="86772-109">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="86772-110">Pro Vermittlungs Server können mehrere Trunks definiert werden.</span><span class="sxs-lookup"><span data-stu-id="86772-110">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="86772-111">Ein Vermittlungs Server kann mehreren Peers zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="86772-111">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="86772-112">Ein trunk ist eine logische Verbindung zwischen einem Vermittlungs Server und einem vom Tupel eindeutig identifizierten Gateway:</span><span class="sxs-lookup"><span data-stu-id="86772-112">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="86772-113">{Vermittlungsserver-FQDN, Abhör Port für Mediationsserver (TLS oder TCP): Gateway-IP und-FQDN, Gateway-Überwachungs Port}</span><span class="sxs-lookup"><span data-stu-id="86772-113">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86772-114">In diesem Thema wird davon ausgegangen, dass Sie ein PSTN-Gateway und einen Stamm Stamm mit mindestens einem zusammengefassten oder eigenständigen Vermittlungs Server oder-Pool eingerichtet haben, wie unter <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Definieren eines Gateways im Topologie-Generator in lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="86772-114">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="86772-115">In diesem Thema wird davon ausgegangen, dass Sie mindestens einen Front-End-Pool oder Standard Edition-Server an mindestens einem zentralen Standort eingerichtet haben, wie unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in lync Server 2013</A> beschrieben und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="86772-115">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="86772-116">So definieren Sie einen zusätzlichen trunk zwischen einem Vermittlungs Server und einem Gateway-Peer</span><span class="sxs-lookup"><span data-stu-id="86772-116">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="86772-117">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="86772-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="86772-118">Klicken Sie unter lync Server 2013, ihren Websitenamen, **freigegebene Komponenten**, mit der rechten Maustaste auf den Knoten **Trunks** , und klicken Sie dann auf **neuer trunk**.</span><span class="sxs-lookup"><span data-stu-id="86772-118">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="86772-119">![Bildschirm der Dateistruktur für lync Server Topology Builder](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Bildschirm der Dateistruktur für lync Server Topology Builder")</span><span class="sxs-lookup"><span data-stu-id="86772-119">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="86772-120">Geben Sie in **Neuen Trunk definieren** einen Anzeigenamen ein, um den Trunk eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="86772-120">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="86772-121">Zwei Trunks mit demselben Namen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="86772-121">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86772-122">Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie anstelle der IP-Adresse des Peers des Vermittlungsservers den FQDN angeben.</span><span class="sxs-lookup"><span data-stu-id="86772-122">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="86772-123">Wählen Sie unter **Zugeordnetes PSTN-Gateway** den PSTN-Gatewaypeer aus, der diesem Trunk zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="86772-123">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="86772-124">![Eigenschafteneinstellungen für PSTN-Gateway-Peer für trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Eigenschafteneinstellungen für PSTN-Gateway-Peer für trunk")</span><span class="sxs-lookup"><span data-stu-id="86772-124">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="86772-125">Geben Sie unter **Abhör-Port für PSTN-Gateway** den Abhör-Port ein, mit dem der Peer (PSTN-Gateway, IP-PBX oder SBC) SIP-Nachrichten vom Vermittlungs Server empfängt, der diesem trunk zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="86772-125">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="86772-126">Die standardmäßigen Peerports sind 5066 für TCP (Transmission Control Protocol) und 5067 für TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="86772-126">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="86772-127">Die Standardanschlüsse für Survivable Branch-Appliances sind 5081 für TCP und 5082 für TLS.</span><span class="sxs-lookup"><span data-stu-id="86772-127">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="86772-128">Klicken Sie unter **SIP-Transportprotokoll** auf den vom Peer verwendeten Transporttyp.</span><span class="sxs-lookup"><span data-stu-id="86772-128">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86772-129">Aus Sicherheitsgründen empfehlen wir dringend, einen Peer auf dem Vermittlungs Server bereitzustellen, der TLS verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="86772-129">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="86772-130">Wählen Sie unter **zugeordneter Vermittlungsserver** den vermittlungsserverpool aus, der dem Stamm Stamm dieses Peers zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="86772-130">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="86772-131">Geben Sie unter **zugeordneter Vermittlungsserver-Port** den Abhör-Port ein, auf dem der Vermittlungsserver SIP-Nachrichten vom Peer empfängt.</span><span class="sxs-lookup"><span data-stu-id="86772-131">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86772-132">Mit mehreren trunk-Unterstützung in lync Server 2013 können zwei Trunks mit unterschiedlichen trunk-Namen nicht mit dem gleichen <STRONG>zugeordneten Vermittlungs Server-Port</STRONG> und dem <STRONG>Überwachungs-Port für das IP/PSTN-Gateway</STRONG> konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="86772-132">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86772-133">Mit mehreren trunk-Unterstützung in lync Server 2013 können mehrere SIP-Signalisierungs Anschlüsse auf dem Vermittlungsserver für die Kommunikation mit mehreren Peers definiert werden.</span><span class="sxs-lookup"><span data-stu-id="86772-133">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="86772-134">Wenn Sie einen trunk definieren, muss sich die <STRONG>zugeordnete Vermittlungsserver-Port</STRONG> Nummer innerhalb des Bereichs der Abhör Anschlüsse für das jeweilige vom Vermittlungsserver zugelassene Protokoll befinden.</span><span class="sxs-lookup"><span data-stu-id="86772-134">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="86772-135">Dieser Portbereich ist unter lync Server 2013 und Mediation Server Pools definiert.</span><span class="sxs-lookup"><span data-stu-id="86772-135">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="86772-136">Klicken Sie mit der rechten Maustaste auf den entsprechenden Vermittlungs Server Pool, und wählen Sie <STRONG>Eigenschaften bearbeiten</STRONG>aus.</span><span class="sxs-lookup"><span data-stu-id="86772-136">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="86772-137">Geben Sie den Portbereich im Feld <STRONG>Abhör-Ports</STRONG> an.</span><span class="sxs-lookup"><span data-stu-id="86772-137">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="86772-138">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="86772-138">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="86772-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86772-139">See Also</span></span>


[<span data-ttu-id="86772-140">Ändern eines Trunks im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86772-140">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

<span data-ttu-id="86772-141"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="86772-141"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

