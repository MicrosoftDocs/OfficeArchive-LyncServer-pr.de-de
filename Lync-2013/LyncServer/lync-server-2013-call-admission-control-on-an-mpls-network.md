---
title: 'Lync Server 2013: Anrufsteuerung in einem MPLS-Netzwerk'
description: 'Lync Server 2013: Anrufsteuerung in einem MPLS-Netzwerk.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e26ba95a9191b567520978ee9512cbbc12e934ec
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49435883"
---
# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a><span data-ttu-id="e8e40-103">Anrufsteuerung in einem MPLS-Netzwerk mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8e40-103">Call admission control on an MPLS network with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="e8e40-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="e8e40-104">

<span> </span></span></span>

<span data-ttu-id="e8e40-105">_**Letztes Änderungsdatum des Themas:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="e8e40-105">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="e8e40-p101">In einem MPLS-Netzwerk (Multiprotocol Label Switching) sind alle Standorte vollständig miteinander vernetzt, d. h. alle Standorte sind direkt mit dem MPLS-Backbone des Internetdienstanbieters verbunden und jedem Standort wird Bandbreite für eine WAN-Verbindung mit der MPLS-Cloud zur Verfügung gestellt. Es ist kein Netzwerkhub oder zentraler Standort zur Steuerung des IP-Routings vorhanden. Die folgende Abbildung zeigt ein einfaches Beispiel für ein auf der MPLS-Technologie basierendes Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="e8e40-p101">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="e8e40-110">**Beispiel eines MPLS-Netzwerks**</span><span class="sxs-lookup"><span data-stu-id="e8e40-110">**Example MPLS network**</span></span>

<span data-ttu-id="e8e40-111">![Anrufsteuerung mit MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "Anrufsteuerung mit MPLS")</span><span class="sxs-lookup"><span data-stu-id="e8e40-111">![CAC with MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC with MPLS")</span></span>

<span data-ttu-id="e8e40-p102">Zur Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) in einem MPLS-Netzwerk erstellen Sie eine Netzwerkregion für die MPLS-Cloud und Netzwerkstandorte für jeden MPLS-Zweigstellenstandort. Die folgende Abbildung zeigt, wie Netzwerkregion und Netzwerkstandorte konfiguriert sein sollten, um das MPLS-Beispielnetzwerk aus der Abbildung oben darzustellen. Die Bandbreitenbeschränkungen insgesamt sowie die Bandbreitenbeschränkung pro Sitzung basieren auf der Kapazität der WAN-Verbindung zwischen jedem Netzwerkstandort und der Netzwerkregion, die die MPLS-Cloud darstellt.</span><span class="sxs-lookup"><span data-stu-id="e8e40-p102">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="e8e40-115">**Netzwerkregion und Netzwerkstandorte für ein MPLS-Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="e8e40-115">**Network region and network sites for an MPLS network**</span></span>

<span data-ttu-id="e8e40-116">![Anrufsteuerung mit MPLS (Diagramm)](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Anrufsteuerung mit MPLS (Diagramm)")</span><span class="sxs-lookup"><span data-stu-id="e8e40-116">![Call Admission Control (CAC) with MPLS diagram](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Call Admission Control (CAC) with MPLS diagram")</span></span>

<span data-ttu-id="e8e40-117"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="e8e40-117"></div>

<span> </span>

</div>

</div>

</span></span></div>

