---
title: 'Lync Server 2013: Definieren der Netzwerkelemente, die zum Ermitteln des Standorts verwendet werden'
description: 'Lync Server 2013: Definieren der Netzwerkelemente, die zum Ermitteln des Standorts verwendet werden.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a77ad0a7d704bf2cc43118db45d9bcfb89daa327
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49430973"
---
# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a><span data-ttu-id="e7dea-103">Definieren der Netzwerkelemente, die zum Ermitteln des Standorts in lync Server 2013 verwendet werden</span><span class="sxs-lookup"><span data-stu-id="e7dea-103">Defining the network elements used to determine location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="e7dea-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="e7dea-104">

<span> </span></span></span>

<span data-ttu-id="e7dea-105">_**Letztes Änderungsdatum des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="e7dea-105">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="e7dea-106">Wenn Sie Ihre lync Server-Infrastruktur zur Unterstützung der automatischen Erkennung von clientstandorten einrichten, müssen Sie zunächst entscheiden, welche Netzwerkelemente Sie verwenden möchten, um Anrufern Standorte zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e7dea-106">If you are setting up your Lync Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="e7dea-107">In lync Server 2013 können Sie die folgenden Layer 2-und Layer 3-Netzwerkelemente mit Speicherorten verknüpfen:</span><span class="sxs-lookup"><span data-stu-id="e7dea-107">In Lync Server 2013, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>

  - <span data-ttu-id="e7dea-108">Adressen für drahtlosen Zugriffspunkt (BSSID, Basic Service Set Identification) (Layer 2)</span><span class="sxs-lookup"><span data-stu-id="e7dea-108">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>

  - <span data-ttu-id="e7dea-109">LLDP-Switch-Port (Layer 2)</span><span class="sxs-lookup"><span data-stu-id="e7dea-109">LLDP switch port (Layer 2)</span></span>

  - <span data-ttu-id="e7dea-110">LLDP-Switch-Chassis-IDs (Layer 2)</span><span class="sxs-lookup"><span data-stu-id="e7dea-110">LLDP switch chassis IDs (Layer 2)</span></span>

  - <span data-ttu-id="e7dea-111">IP-Subnetze (Layer 3)</span><span class="sxs-lookup"><span data-stu-id="e7dea-111">IP subnets (Layer 3)</span></span>

  - <span data-ttu-id="e7dea-112">Client-MAC-Adressen (Layer 2)</span><span class="sxs-lookup"><span data-stu-id="e7dea-112">Client MAC addresses (Layer 2)</span></span>

<span data-ttu-id="e7dea-113">Die Netzwerkelemente werden gemäß ihrer Rangfolge aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="e7dea-113">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="e7dea-114">Wenn ein Client mithilfe von mehr als einem Netzwerkelement gefunden werden kann, verwendet lync Server die Rangfolge, um zu bestimmen, welcher Mechanismus verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7dea-114">If a client can be located by using more than one network element, Lync Server uses the order of precedence to determine which mechanism to use.</span></span>

<span data-ttu-id="e7dea-115">Die folgenden Abschnitte enthalten weitere Einzelheiten zur Verwendung der einzelnen Netzwerkelemente.</span><span class="sxs-lookup"><span data-stu-id="e7dea-115">The following sections provide more details for using each network element.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7dea-116">Wenn Sie Netzwerkelemente verwenden, um Anrufern Standorte zuzuordnen, ist es äußerst wichtig, dass Sie die Datenbank des Standort Informationsdiensts auf dem neuesten Stand halten.</span><span class="sxs-lookup"><span data-stu-id="e7dea-116">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="e7dea-117">Wenn Sie beispielsweise ein Netzwerkelement hinzufügen oder ändern (z. B. einen drahtlosen Zugriffspunkt), müssen Sie den alten Eintrag löschen und den neuen Eintrag in der Standortdatenbank hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e7dea-117">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span>



</div>

<div>

## <a name="wireless-access-point"></a><span data-ttu-id="e7dea-118">Drahtloser Zugriffspunkt</span><span class="sxs-lookup"><span data-stu-id="e7dea-118">Wireless Access Point</span></span>

<span data-ttu-id="e7dea-119">Wenn ein Client drahtlos eine Verbindung mit dem Netzwerk herstellt, verwendet die standortanforderung die BSSID-Adresse des WAP, um dessen Standort festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e7dea-119">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="e7dea-120">Wenn der Client Roaming hat, ist der angezeigte WAP möglicherweise nicht der nächstgelegene, und es ist sogar möglich, einen WAP aufzunehmen, der sich auf einer anderen Etage des Gebäudes befindet.</span><span class="sxs-lookup"><span data-stu-id="e7dea-120">If the client is roaming, the WAP indicated may not be the closest one, and it’s even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="e7dea-121">Um anzugeben, dass die Position Näherungswert ist, können Sie den Positionswert mit einem near-oder Close-Deskriptor voranstellen.</span><span class="sxs-lookup"><span data-stu-id="e7dea-121">To indicate that the location is approximate, you can prepend the location value with a Near or Close to descriptor.</span></span>

<span data-ttu-id="e7dea-122">Bei dieser Standortmethode wird davon ausgegangen, dass die BSSID der einzelnen Zugriffspunkte statisch ist.</span><span class="sxs-lookup"><span data-stu-id="e7dea-122">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="e7dea-123">Wenn der Zugriffspunktanbieter jedoch dynamisch zugewiesene BSSIDs verwendet, könnte sich die von einem Zugriffspunkt erhaltene BSSID ändern (dies kann beispielsweise bei einer Konfigurationsänderung für den Zugriffspunkt auftreten) und könnte für die drahtlosen Clients die Situation auftreten, dass sie keinen Standort erhalten.</span><span class="sxs-lookup"><span data-stu-id="e7dea-123">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don’t receive a location.</span></span> <span data-ttu-id="e7dea-124">Um diese Möglichkeit zu verhindern, müssen Sie die Datenbank für den standortinformationsdienst mit ERLs für alle möglichen BSSID-Adressen auffüllen, die von jedem WAP verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7dea-124">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span>

</div>

<div>

## <a name="lldp-ports-and-switches"></a><span data-ttu-id="e7dea-125">LLDP-Ports und -Switches</span><span class="sxs-lookup"><span data-stu-id="e7dea-125">LLDP Ports and Switches</span></span>

<span data-ttu-id="e7dea-p106">Verwaltete Ethernet-Switches, die LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) unterstützen, können die ID- und Portinformationen eines Netzwerks für einen kompatiblen LLDP-MED-Client bereitstellen, die dann wiederum bei der Standortdatenbank abgefragt werden, um den Standort des Geräts anzugeben. Sie können Erwartungsregellisten ausschließlich der Switch-Chassis-ID zuordnen oder sie alternativ auf Portebene zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e7dea-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7dea-128">Lync Server 2013 unterstützt die Verwendung von LLDP-MED zum Ermitteln von Speicherorten nur von lync Phone Edition-Geräten und lync 2013, die unter Windows 8 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e7dea-128">Lync Server 2013 supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Lync 2013 running on Windows 8.</span></span> <span data-ttu-id="e7dea-129">Wenn Sie Layer 2-Daten auf switchebene verwenden müssen, um den Speicherort anderer auf einem drahtgebundenen PC basierender lync-Clients zu ermitteln, müssen Sie die Client-Mac-Adressen Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7dea-129">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Lync clients, you need to use the client MAC address method.</span></span>



</div>

</div>

<div>

## <a name="subnet"></a><span data-ttu-id="e7dea-130">Subnetz</span><span class="sxs-lookup"><span data-stu-id="e7dea-130">Subnet</span></span>

<span data-ttu-id="e7dea-131">Layer 3-IP-Subnetze stellen einen Mechanismus bereit, der von allen lync Server-Clients unterstützt wird, die zum automatischen Erkennen des Client Standorts verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e7dea-131">Layer 3 IP subnets provide a mechanism supported by all Lync Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="e7dea-132">Die Verwendung von IP-Subnetzen ist die einfachste Methode zur Ermittlung von Standorten, um verkabelte Clients zu konfigurieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e7dea-132">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="e7dea-133">Bevor Sie sich für die Verwendung von Subnetzen entscheiden, sollten Sie jedoch anhand der folgenden Fragen ermitteln, ob die Standortgenauigkeit des Subnetzes für eine präzise Ermittlung des Clientstandorts ausreicht:</span><span class="sxs-lookup"><span data-stu-id="e7dea-133">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>

  - <span data-ttu-id="e7dea-134">Umfassen ein oder mehrere Client-Subnetze verschiedene Etagen?</span><span class="sxs-lookup"><span data-stu-id="e7dea-134">Do one or more client subnets cover multiple floors?</span></span>

  - <span data-ttu-id="e7dea-135">Umfassen ein oder mehrere Subnetze mehrere Gebäude?</span><span class="sxs-lookup"><span data-stu-id="e7dea-135">Do one or more subnets cover more than one building?</span></span>

  - <span data-ttu-id="e7dea-136">Welchen Etagenbereich umfassen die einzelnen Client-Subnetze?</span><span class="sxs-lookup"><span data-stu-id="e7dea-136">How much floor space is covered by each client subnet?</span></span>

<span data-ttu-id="e7dea-p109">Wenn das Subnetz einen zu großen Bereich umfasst, müssen Sie möglicherweise eine andere Methode zum Ermitteln der Clients verwenden. Es wird empfohlen, dass Kunden – sofern möglich – ihre IP-Subnetzverwendung neu anordnen, um die Anforderungen für die Standortgenauigkeit in Erwartungsregellisten zu erfüllen, statt die Kosten und Komplexität von SNMP-basierten Drittanbieter-Lösungen tragen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="e7dea-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>

</div>

<div>

## <a name="client-mac-address"></a><span data-ttu-id="e7dea-139">Client-MAC-Adresse</span><span class="sxs-lookup"><span data-stu-id="e7dea-139">Client MAC Address</span></span>

<span data-ttu-id="e7dea-140">Wenn Sie die Mac-Adresse eines Clientcomputers zum Auffinden eines Anrufers verwenden möchten, benötigen Sie verwaltete Ethernet-Switches, und Sie müssen eine SNMP-Lösung eines Drittanbieters bereitstellen, die die Mac-Adressen von lync-Clients ermitteln kann, die mit diesen Switches verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="e7dea-140">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Lync clients connected to (or through) those switches.</span></span> <span data-ttu-id="e7dea-141">Die SNMP-Lösung fragt kontinuierlich die verwalteten Switches ab, um die aktuellen Zuordnungen der Endpunkt-Mac-Adressen abzurufen, die mit jedem Port verbunden sind, und ruft die entsprechenden Port-IDs ab.</span><span class="sxs-lookup"><span data-stu-id="e7dea-141">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="e7dea-142">Während der Anforderung eines lync-Clients an den standortinformationsdienst fragt der standortinformationsdienst die Drittanbieteranwendung mithilfe der Mac-Adresse des Clients ab und gibt dann alle übereinstimmenden Switch-IP-Adressen und Port-IDs zurück.</span><span class="sxs-lookup"><span data-stu-id="e7dea-142">During a Lync client’s request to the Location Information service, the Location Information service queries the third-party application by using the client’s MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="e7dea-143">Der standortinformationsdienst verwendet diese Informationen, um seinen veröffentlichten Layer 2-Wiremap nach einem übereinstimmenden Datensatz abzufragen, und gibt den Speicherort an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="e7dea-143">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="e7dea-144">Wenn Sie diese Option verwenden, stellen Sie sicher, dass die Switch-Port-IDs zwischen der SNMP-Anwendung und den veröffentlichten Speicherort-Datensätzen konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="e7dea-144">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7dea-145">Einige SNMP-Lösungen von Drittanbietern können nicht verwaltete Zugriffs Schalter unterstützen. Wenn der Switch, der den lync-Client nicht verwaltet, aber über einen Uplink zu einem verwalteten Verteilungs Schalter verfügt, kann der verwaltete Switch der SNMP-Anwendung die Mac-Adressen der Clients melden, die mit dem Zugriffs Schalter verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="e7dea-145">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Lync client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="e7dea-146">Mithilfe dieser Informationen kann der standortinformationsdienst den Standort des Benutzers ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e7dea-146">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="e7dea-147">Es ist jedoch möglich, allen Anschlüssen des nicht verwalteten Switches nur ein einzelnes Erl zuzuweisen, sodass die Standort Spezifität nur auf der Chassis-Ebene des Zugriffs Schalters und nicht auf der Portebene verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e7dea-147">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span>



<span data-ttu-id="e7dea-148"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="e7dea-148"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

