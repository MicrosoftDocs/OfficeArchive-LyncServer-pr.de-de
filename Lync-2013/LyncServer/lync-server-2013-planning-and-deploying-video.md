---
title: 'Lync Server 2013: Planen und Bereitstellen von Video'
description: 'Lync Server 2013: Planen und Bereitstellen von Video.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning and deploying video
ms:assetid: dadfb7f3-dfd6-4847-b137-17dacafd7368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205307(v=OCS.15)
ms:contentKeyID: 48185558
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9fd8a93f890295daebd2bc887414a2417b86395
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394166"
---
# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="79c3e-103">Planen und Bereitstellen von Video in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79c3e-103">Planning and deploying video in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="79c3e-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="79c3e-104">

<span> </span></span></span>

<span data-ttu-id="79c3e-105">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="79c3e-105">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="79c3e-106">Lync Server 2013 stellt die folgenden neuen Videofeatures vor:</span><span class="sxs-lookup"><span data-stu-id="79c3e-106">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="79c3e-107">**HD-Video**   Benutzer können Auflösungen bis zur Full High Definition (HD) (d. 1920 x 1080) in zweier-und Mehrparteienkonferenzen erleben.</span><span class="sxs-lookup"><span data-stu-id="79c3e-107">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="79c3e-108">**Katalogansicht**   In Videokonferenzen mit mehr als zwei Personen können Benutzer Videos der Teilnehmer an der Konferenz sehen.</span><span class="sxs-lookup"><span data-stu-id="79c3e-108">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="79c3e-109">Wenn die Konferenz mehr als fünf Teilnehmer umfasst, werden in der obersten Zeile nur Videos von den aktivsten Teilnehmern angezeigt, und für die anderen Teilnehmer wird ein Foto angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79c3e-109">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="79c3e-110">**H. 264-Video**   Der H. 264-Videocodec ist jetzt die Standardeinstellung für Videocodierung auf lync 2013-Clients.</span><span class="sxs-lookup"><span data-stu-id="79c3e-110">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="79c3e-111">H. 264-Video unterstützt eine größere Auswahl an Auflösungen und Frameraten und verbessert die Video Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="79c3e-111">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79c3e-112">Lync Server 2013 unterstützt weiterhin den VC1-Codec für die Interoperabilität mit früheren lync-Versionen.</span><span class="sxs-lookup"><span data-stu-id="79c3e-112">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="79c3e-113">Details und Hintergrundinformationen zum neuen Videocodec finden Sie im Blog-Artikel "Video Interoperabilität in lync 2013" unter Jeff Schertz <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A> .</span><span class="sxs-lookup"><span data-stu-id="79c3e-113">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="79c3e-114">In diesem Abschnitt wird beschrieben, wie Sie die Bandbreite für Video in lync Server 2013 verwalten und Videofeatures konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="79c3e-114">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="79c3e-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="79c3e-115">In This Section</span></span>

  - [<span data-ttu-id="79c3e-116">Konfigurieren der Videobandbreite in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79c3e-116">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="79c3e-117">Konfigurieren der Katalogansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79c3e-117">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="79c3e-118">Konfigurieren von Video Beispielszenarien für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79c3e-118">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="79c3e-119">Interoperabilitäts Überlegungen für Videokonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79c3e-119">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

<span data-ttu-id="79c3e-120"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="79c3e-120"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

