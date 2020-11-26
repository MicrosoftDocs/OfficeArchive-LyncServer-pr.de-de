---
title: Entfernen eines Front-End-Servers aus einem Pool
description: Entfernen eines Front-End-Servers aus einem Pool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45560a6f43288b47c0f85f880a190e31f2c8c04d
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49440325"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="422d6-103">Entfernen eines Front-End-Servers aus einem Pool</span><span class="sxs-lookup"><span data-stu-id="422d6-103">Remove a Front End Server from a pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="422d6-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="422d6-104">

<span> </span></span></span>

<span data-ttu-id="422d6-105">_**Letztes Änderungsdatum des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="422d6-105">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="422d6-106">Der Microsoft lync Server 2010 Enterprise Edition-Front-End-Server kann nicht als eigenständiger Computer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="422d6-106">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="422d6-107">Es muss als Front-End-Pool definiert werden, auch wenn es nur einen einzelnen Computer im Pool gibt.</span><span class="sxs-lookup"><span data-stu-id="422d6-107">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="422d6-108">Dieses Thema führt Sie durch den Vorgang zum Entfernen eines einzelnen Front-End-Servers aus einem vorhandenen Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="422d6-108">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="422d6-109">Wenn der Front-End-Server der letzte Server im Pool ist oder wenn Sie den Pool vollständig entfernen, lesen Sie [Entfernen des Front-End-Pools oder des Standard Edition-Servers](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="422d6-109">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="422d6-110">Es ist nicht erforderlich, die einzelnen Front-End-Server zu entfernen, bevor Sie den Front-End-Pool entfernen.</span><span class="sxs-lookup"><span data-stu-id="422d6-110">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="422d6-111">Wenn Sie den Pool entfernen, entfernen Sie jeden Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="422d6-111">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="422d6-112">So entfernen Sie einen Front-End-Server aus einem Pool</span><span class="sxs-lookup"><span data-stu-id="422d6-112">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="422d6-113">Öffnen Sie den lync Server 2013-Front-End-Server, öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="422d6-113">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="422d6-114">Navigieren Sie zum lync Server 2010-Knoten.</span><span class="sxs-lookup"><span data-stu-id="422d6-114">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="422d6-115">Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie den Front-End-Pool mit dem zu entfernenden Front-End-Server, klicken Sie mit der rechten Maustaste auf den Front-End-Server, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="422d6-115">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

<span data-ttu-id="422d6-116"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="422d6-116"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

