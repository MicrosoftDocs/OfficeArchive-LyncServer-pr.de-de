---
title: 'Lync Server 2013: Konfigurieren der Orbittabelle für das Parken von Anrufen'
description: 'Lync Server 2013: Konfigurieren der Umlaufbahn Tabelle des Anruf Parks'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9fb35c2958a426888d83d075064c88ddae4bfa
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433633"
---
# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="8dd14-103">Konfigurieren der Orbittabelle für das Parken von Anrufen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dd14-103">Configure the Call Park orbit table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="8dd14-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="8dd14-104">

<span> </span></span></span>

<span data-ttu-id="8dd14-105">_**Letztes Änderungsdatum des Themas:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="8dd14-105">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="8dd14-106">Call Park verwendet Umlaufbahnen für Park Anrufe.</span><span class="sxs-lookup"><span data-stu-id="8dd14-106">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="8dd14-107">Bevor Benutzer Anrufe parken und abrufen können, müssen Sie die Umlaufbahn Tabelle des Anruf Parks konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8dd14-107">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="8dd14-108">Sie müssen die Bereiche der Durchwahlnummern (Orbits) angeben, die Ihre Organisation für Park Anrufe reserviert, und den Arbeitsplan für diese Bereiche definieren, indem Sie angeben, welcher Anruf Park Pool für jeden Bereich zuständig ist.</span><span class="sxs-lookup"><span data-stu-id="8dd14-108">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="8dd14-109">Wenn Sie Umlaufbahn Bereiche definieren, besteht das Ziel darin, genügend Umlaufbahnen zu haben, damit eine Umlaufbahn nicht zu schnell wieder verwendet wird, aber nicht so viele Umlaufbahnen, dass Sie die Anzahl der für Benutzer oder andere Dienste verfügbaren Erweiterungen einschränken.</span><span class="sxs-lookup"><span data-stu-id="8dd14-109">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="8dd14-110">Sie können für jeden lync Server-Pool, in dem die Park-Anwendung bereitgestellt wird, mehrere orbitbereiche für den Anruf Bereich erstellen.</span><span class="sxs-lookup"><span data-stu-id="8dd14-110">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="8dd14-111">Jeder Orbit-Bereich für das Parken von Anrufen muss einen global eindeutigen Namen und einen eindeutigen Satz von Erweiterungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8dd14-111">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8dd14-p102">Ein Orbitbereich umfasst normalerweise 100 oder weniger Orbits. Jeder Bereich kann deutlich größer sein, solange der Höchstwert von 10.000 Orbits pro Bereich nicht überschritten wird und Sie über weniger als 50.000 Orbits pro Pool verfügen. Ist ein Bereich zu klein, werden die Orbits zu schnell wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="8dd14-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="8dd14-115">Verwenden Sie für Ihre Orbitbereiche Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist).</span><span class="sxs-lookup"><span data-stu-id="8dd14-115">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8dd14-116">Das Zuweisen von Direktwahlnummern (DID) als Orbit-Nummern in der Orbit-Tabelle des Anruf Parks wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8dd14-116">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8dd14-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8dd14-117">In This Section</span></span>

[<span data-ttu-id="8dd14-118">Erstellen oder Ändern eines orbitbereichs für einen Anruf Bereich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dd14-118">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

<span data-ttu-id="8dd14-119"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="8dd14-119"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

