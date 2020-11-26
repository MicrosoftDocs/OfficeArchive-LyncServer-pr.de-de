---
title: 'Lync Server 2013: Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks befindet'
description: 'Lync Server 2013: Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks befindet.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66f40886e9784b5bd4182a60b955745b5daf2034
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427068"
---
# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a><span data-ttu-id="61e69-103">Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks von lync Server 2013 befindet</span><span class="sxs-lookup"><span data-stu-id="61e69-103">Installing a certificate on a watcher node located outside the perimeter network of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="61e69-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="61e69-104">

<span> </span></span></span>

<span data-ttu-id="61e69-105">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="61e69-105">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="61e69-106">System Center Operations Manager-Agents, die in einem Umkreisnetzwerk (wie einem lync Server-Edgeserver) ausgeführt werden, außerhalb des Unternehmens (beispielsweise ein externer synthetischer Transaktions Überwachungsknoten) oder über eine Vertrauensgrenze für Active Directory-Domänendienste verfügen, erfordern möglicherweise die Konfiguration eines System Center Operations Manager-Gatewayservers.</span><span class="sxs-lookup"><span data-stu-id="61e69-106">System Center Operations Manager agents running in a perimeter network (such as a Lync Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory Domain Services trust boundary, might require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="61e69-107">Mit dieser Serverrolle können Agents, die nicht über eine Vertrauensstellung mit dem Stammverwaltungsserver verfügen, Benachrichtigungen auslösen.</span><span class="sxs-lookup"><span data-stu-id="61e69-107">This server role allows agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="61e69-108">Ausführliche Informationen finden Sie unter "Verwalten von Gatewayservern in Operations Manager 2007" in der TechNet-Bibliothek für System Center Operations Manager unter [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703) .</span><span class="sxs-lookup"><span data-stu-id="61e69-108">For details, see "Managing Gateway Servers in Operations Manager 2007" in the System Center Operations Manager TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703).</span></span>

<span data-ttu-id="61e69-109">Wenn Sie einen Agenten an einem dieser Speicherorte bereitstellen, müssen Sie auch ein Zertifikat anfordern und konfigurieren, das dem Watcher-Knoten die Möglichkeit gibt, Benachrichtigungen an System Center Operations Manager zu senden.</span><span class="sxs-lookup"><span data-stu-id="61e69-109">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="61e69-110">Zur Vereinfachung dieses Prozesses hat das Operations Manager-Team einen Satz von Dienstprogrammen erstellt, mit denen Sie den richtigen Zertifikattyp auf dem Watcher-Knoten Computer anfordern und installieren können.</span><span class="sxs-lookup"><span data-stu-id="61e69-110">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="61e69-111">Informationen zum Herunterladen dieser Dienstprogramme finden Sie im Blog Artikel unter "Abrufen von Zertifikaten für nicht-Domänen verbundene Agents, die mit dem Assistenten für die Zertifikatgenerierung vereinfacht wurden" [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421) .</span><span class="sxs-lookup"><span data-stu-id="61e69-111">For details, and to download these utilities, see the "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" blog article at [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421).</span></span>

<span data-ttu-id="61e69-112"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="61e69-112"></div>

<span> </span>

</div>

</div>

</span></span></div>

