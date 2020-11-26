---
title: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Edgeserver'
description: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Edgeserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7798ca2f7b38865a2b4ea373546dd4e7203f5b8e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49430199"
---
# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a><span data-ttu-id="778b6-103">Bereitstellen von IP-Adresstypen auf einem Edgeserver für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="778b6-103">Deploy IP address types on an Edge Server for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="778b6-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="778b6-104">

<span> </span></span></span>

<span data-ttu-id="778b6-105">_**Letztes Änderungsdatum des Themas:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="778b6-105">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="778b6-106">Führen Sie mithilfe des Topologie-Generators die Schritte im folgenden Verfahren aus, um IP-Adresstypen auf einem Edgeserver bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="778b6-106">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on an Edge Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="778b6-107">So stellen Sie IP-Adresstypen auf dem Edgeserver bereit</span><span class="sxs-lookup"><span data-stu-id="778b6-107">To deploy IP address types on an Edge Server</span></span>

1.  <span data-ttu-id="778b6-108">Klicken Sie im Topologie-Generator unter **Edge-Pools** mit der rechten Maustaste auf den Server in einem Pool, und wählen Sie dann **Eigenschaften bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="778b6-108">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="778b6-109">(Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)</span><span class="sxs-lookup"><span data-stu-id="778b6-109">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="778b6-p102">Wählen Sie im Fenster **Eigenschaften bearbeiten** die IP-Adresskonfiguration, die Sie unterstützen möchten. In den folgenden Abbildungen wird eine Dualstapelkonfiguration für die interne und die externe Schnittstelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="778b6-p102">In the **Edit Properties** window, select the IP address configuration that you want to support. The following figures show a dual stack configuration for the internal interface and the external interface.</span></span>
    
    <span data-ttu-id="778b6-112">**Interne Dualstapelschnittstelle für Edge Server**</span><span class="sxs-lookup"><span data-stu-id="778b6-112">**Dual stacked Edge Server internal interface**</span></span>
    
    <span data-ttu-id="778b6-113">![Seite "Allgemeine Eigenschaften von lync Server"](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Seite "Allgemeine Eigenschaften von lync Server"")</span><span class="sxs-lookup"><span data-stu-id="778b6-113">![Lync Server general properties page](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server general properties page")</span></span>
    
    <span data-ttu-id="778b6-114">**Externe Dualstapelschnittstelle für Edge Server**</span><span class="sxs-lookup"><span data-stu-id="778b6-114">**Dual stacked Edge Server external interface**</span></span>
    
    <span data-ttu-id="778b6-115">![Lync Server-nächster Hop/externe Konfigurationsseite](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server-nächster Hop/externe Konfigurationsseite")</span><span class="sxs-lookup"><span data-stu-id="778b6-115">![Lync Server next hop/external configuration page](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server next hop/external configuration page")</span></span>

3.  <span data-ttu-id="778b6-116">Für jeden Adresstyp, den Sie auswählen, müssen Sie die geeigneten internen und externen Adressen auswählen.</span><span class="sxs-lookup"><span data-stu-id="778b6-116">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>

<span data-ttu-id="778b6-117"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="778b6-117"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

