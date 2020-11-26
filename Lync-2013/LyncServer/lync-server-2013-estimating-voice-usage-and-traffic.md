---
title: 'Lync Server 2013: Schätzen von VoIP-Nutzung und -Datenverkehr'
description: 'Lync Server 2013: schätzt die Verwendung von VoIP und den Datenverkehr.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc288e6da65e8e6f221a05c6c82f0588414c8af
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428451"
---
# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a><span data-ttu-id="6cb27-103">Schätzen von VoIP-Nutzung und -Datenverkehr für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cb27-103">Estimating voice usage and traffic for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="6cb27-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="6cb27-104">

<span> </span></span></span>

<span data-ttu-id="6cb27-105">_**Letztes Änderungsdatum des Themas:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="6cb27-105">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="6cb27-106">Das Planungs Tool für Microsoft lync Server 2013 verwendet die folgende Metrik, um den Benutzerdatenverkehr an jedem Standort und die Anzahl der Ports zu schätzen, die für die Unterstützung des Datenverkehrs erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6cb27-106">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>

  - <span></span>  
    <span data-ttu-id="6cb27-107">Für **geringes Datenverkehrsaufkommen** (ein Festnetzanruf pro Benutzer und Stunde) gehen Sie von 15 Benutzern pro Anschluss aus.</span><span class="sxs-lookup"><span data-stu-id="6cb27-107">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="6cb27-108">Für **mittleres Datenverkehrsaufkommen** (zwei Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 10 Benutzern pro Anschluss aus.</span><span class="sxs-lookup"><span data-stu-id="6cb27-108">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="6cb27-109">Für **hohes Datenverkehrsaufkommen** (drei oder mehr Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 5 Benutzern pro Anschluss aus.</span><span class="sxs-lookup"><span data-stu-id="6cb27-109">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>

<span data-ttu-id="6cb27-110">Die Anzahl der Ports wiederum bestimmt die Anzahl der Vermittlungsserver und Gateways, die erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6cb27-110">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="6cb27-111">Die PSTN-Gateways (Public Switched Telephone Network), die in den meisten Organisationen für die Bereitstellung von Bereichsgröße von 2 Anschlüssen bis zu 960-Ports in Frage kämen.</span><span class="sxs-lookup"><span data-stu-id="6cb27-111">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="6cb27-112">(Es gibt sogar größere Gateways, die aber hauptsächlich von Telefondienstanbietern verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="6cb27-112">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>

<span data-ttu-id="6cb27-p102">Eine Organisation mit 10.000 Benutzern und mittlerem Datenverkehrsaufkommen würde z. B. 1000 Ports benötigen. Die Anzahl der erforderlichen Gateways entspricht der Gesamtzahl der erforderlichen Ports, die durch die Gesamtkapazität der Gateways bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="6cb27-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>

<span data-ttu-id="6cb27-115"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="6cb27-115"></div>

<span> </span>

</div>

</div>

</span></span></div>

