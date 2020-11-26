---
title: 'Lync Server 2013: Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers'
description: 'Lync Server 2013: Bereitstelleneiner Survivable Branch-Appliance oder eines Servers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c8610ab85b61d33a5f181f1d5f51d0e5095f49
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49430119"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="3bd17-103">Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bd17-103">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="3bd17-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="3bd17-104">

<span> </span></span></span>

<span data-ttu-id="3bd17-105">_**Letztes Änderungsdatum des Themas:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="3bd17-105">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="3bd17-106">Die flexible Enterprise-VoIP-Funktion bezieht sich auf die Flexibilität von Branch-Site, das heißt, die Möglichkeit zum Bereitstellen von kontinuierlichem Enterprise-VoIP-Service für Zweigstellenbenutzer, falls der Link zur zentralen Website nicht mehr zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="3bd17-106">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="3bd17-107">Für kleine und mittelständische Zweigstellen (Zweigstellen mit 25 bis 1.000 Benutzern) empfehlen wir die Bereitstellung einer Survival-Branch-Appliance, die PSTN-Anrufe (Public Switched Telephone Network) mit dem integrierten PSTN-Gateway oder einem SIP-Trunk zu einem Telefondienstanbieter beendet.</span><span class="sxs-lookup"><span data-stu-id="3bd17-107">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="3bd17-108">Eine Survivable Branch-Appliance ist ein Gerät eines Drittanbieters, das einen Blade-Server mit dem Betriebssystem Windows Server 2008 R2, lync Server 2013 Registrar, Mediation Server-Software und einem PSTN-Gateway umfasst, alles in einem einzigen Appliance-Chassis.</span><span class="sxs-lookup"><span data-stu-id="3bd17-108">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="3bd17-109">Für Zweigstellen mit 1.000-5.000-Benutzern und kein robustes WAN empfehlen wir einen Überlebenden Branch-Server, der mit einem PSTN-Gateway oder einem SIP-Trunk an einen Telefondienstanbieter angeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3bd17-109">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="3bd17-110">Ein Survivable Branch Server ist ein Windows Server-basierter Computer, auf dem die Registrierungsstelle und die Mediationsserver Software installiert ist.</span><span class="sxs-lookup"><span data-stu-id="3bd17-110">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3bd17-111">Für Zweigstellen, die mehr als 5.000-Benutzer und dedizierte lync Server-Administratoren sind, empfehlen wir eine vollständige lync Server 2013-Bereitstellung, die von der des zentralen Standorts getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="3bd17-111">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="3bd17-112">Ausführliche Informationen zum Auswählen der besten Resilienz-Lösung für die Zweigstellen in Ihrer Organisation, einschließlich Voraussetzungen und Planungsüberlegungen, finden Sie unter Anforderungen an die <A href="lync-server-2013-branch-site-resiliency-requirements.md">Stabilität der Zweigstelle für lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3bd17-112">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3bd17-113">Benutzer, die sich in einer Überlebenden lync Server-Branch-Appliance befinden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3bd17-113">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3bd17-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3bd17-114">In This Section</span></span>

  - [<span data-ttu-id="3bd17-115">Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013 – Aufgaben am zentralen Standort</span><span class="sxs-lookup"><span data-stu-id="3bd17-115">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="3bd17-116">Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013 – Aufgaben am Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="3bd17-116">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="3bd17-117">Konfigurieren von Benutzern für Ausfallsicherheit für Zweigstellenstandorte in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bd17-117">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="3bd17-118">Verwalten von Benutzern in einer Survivable Branch Appliance oder auf einem Survivable Branch Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bd17-118">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="3bd17-119">Anhänge: Survivable Branch Appliances und Survivable Branch Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bd17-119">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3bd17-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bd17-120">See Also</span></span>


[<span data-ttu-id="3bd17-121">Bereitstellen von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bd17-121">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

<span data-ttu-id="3bd17-122"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="3bd17-122"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

