---
title: 'Lync Server 2013: Aktivieren von Benutzern für E9-1-1'
description: 'Lync Server 2013: Aktivieren von Benutzern für E9-1-1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ba29406dc0d7a1140c83a1a9d271afca5d6b0c7
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428706"
---
# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="0412a-103">Aktivieren von Benutzern für E9-1-1 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0412a-103">Enabling users for E9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="0412a-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="0412a-104">

<span> </span></span></span>

<span data-ttu-id="0412a-105">_**Letztes Änderungsdatum des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="0412a-105">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="0412a-106">Während der Clientregistrierung verwendet lync Server eine ortungsrichtlinie, um die E9-1-1-Eigenschaften für Enterprise-VoIP-Benutzer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0412a-106">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="0412a-107">Diese Richtlinie enthält die Einstellungen, die definieren, wie E9-1-1 implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="0412a-107">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="0412a-108">Beispielsweise enthält die Standortrichtlinie Informationen wie die Notrufnummern Zeichenfolge und ob ein Benutzer manuell einen Standort eingeben muss, wenn der standortinformationsdienst nicht automatisch einen Speicherort bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0412a-108">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="0412a-109">Eine vollständige Definition einer Standortrichtlinie finden Sie unter [Definieren der Standortrichtlinie für lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="0412a-109">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="0412a-110">Lync Server kann Clients, die auf einem Subnetz basieren, oder Benutzern, die auf einer globalen, pro-Site-oder pro-Benutzer-Richtlinie basieren, eine ortungsrichtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0412a-110">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="0412a-111">Damit Sie entscheiden können, wie Sie die Benutzer aktivieren können, sollten Sie zunächst die folgenden Fragen beantworten.</span><span class="sxs-lookup"><span data-stu-id="0412a-111">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="0412a-112">**Beabsichtigen Sie, alle Benutzer zu aktivieren oder die Unterstützung auf bestimmte geografische Bereiche des Unternehmens zu begrenzen?**</span><span class="sxs-lookup"><span data-stu-id="0412a-112">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="0412a-113">Sie können allen Benutzern in Ihrem Unternehmen einen Standort zuweisen, indem Sie eine globale Standortrichtlinie verwenden.</span><span class="sxs-lookup"><span data-stu-id="0412a-113">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="0412a-114">Wenn Sie jedoch eine Standortrichtlinie einer lync Server-Netzwerk Website zuweisen und dann Subnetze zur Website hinzufügen, können Sie die E9-1-1-Unterstützung auf ausgewählte Standorte innerhalb des Unternehmens begrenzen und das Routingverhalten von E9-1-1 pro Website angeben.</span><span class="sxs-lookup"><span data-stu-id="0412a-114">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="0412a-115">**Beabsichtigen Sie, einzelne Benutzer über eine Benutzerrichtlinie zu aktivieren?**</span><span class="sxs-lookup"><span data-stu-id="0412a-115">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="0412a-116">Sie können Standortrichtlinien bestimmten Benutzern oder öffentlichen Telefon Kontaktobjekten direkt zuweisen, wenn Sie Ihre E9-1-1-Unterstützung anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="0412a-116">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="0412a-117">**Wenn Clients außerhalb des Netzwerks oder mit einem nicht definierten Subnetz verbunden sind, sollten die Clients weiterhin für E9-1-1 aktiviert sein?**</span><span class="sxs-lookup"><span data-stu-id="0412a-117">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="0412a-118">Wenn Benutzern eine Global-, Site-oder pro-User-ortungsrichtlinie zugewiesen ist, kann es erforderlich sein, einen Standort manuell in den Client einzugeben, wenn sich der Client nicht in einem definierten Subnetz befindet oder vom standortinformationsdienst kein Standort gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="0412a-118">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="0412a-119">Ausführliche Informationen finden Sie unter [Definieren der Benutzeroberfläche für den manuellen Erwerb eines Speicherorts in lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="0412a-119">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

<span data-ttu-id="0412a-120"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="0412a-120"></div>

<span> </span>

</div>

</div>

</span></span></div>

