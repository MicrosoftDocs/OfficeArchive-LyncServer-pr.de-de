---
title: Einrichten von Richtlinien für die Archivierung bei Verwendung der Exchange Server-Integration
description: Einrichten von Richtlinien für die Archivierung bei Verwendung der Exchange Server-Integration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up policies for Archiving when using Exchange Server integration
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48184742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8281d27101c049b1029a2005ed062a934438afc5
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49444721"
---
# <a name="setting-up-policies-for-archiving-in-lync-server-2013-when-using-exchange-server-integration"></a><span data-ttu-id="7910b-103">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server-Integration</span><span class="sxs-lookup"><span data-stu-id="7910b-103">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="7910b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="7910b-104">

<span> </span></span></span>

<span data-ttu-id="7910b-105">_**Letztes Änderungsdatum des Themas:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="7910b-105">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="7910b-106">Wenn die Postfächer von Benutzern, die sich in Exchange 2013 befinden, in In-Place Speicher gesetzt werden, Steuern Exchange-In-Place Richtlinien die Archivierung für diese Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7910b-106">If users homed on Exchange 2013 have their mailboxes put on In-Place Hold, Exchange In-Place Hold policies control archiving for those users.</span></span> <span data-ttu-id="7910b-107">Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung verwenden, überschreiben Exchange 2013-Richtlinien lync Server-Archivierungsrichtlinien für Benutzer, die in Exchange 2013 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="7910b-107">If you use Microsoft Exchange integration for your deployment, Exchange 2013 policies override Lync Server Archiving policies for users who are homed on Exchange 2013.</span></span> <span data-ttu-id="7910b-108">Informationen zum Konfigurieren von Exchange-Archivierungsrichtlinien finden Sie in der Exchange 2013-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="7910b-108">For information about configuring Exchange Archiving policies, see the Exchange 2013 documentation.</span></span> <span data-ttu-id="7910b-109">Ausführliche Informationen zum Einrichten von Benutzerrichtlinien für Benutzer, die sich in lync Server 2013 befinden, finden Sie unter [Einrichten von Benutzerrichtlinien für die Archivierung in lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7910b-109">For details about setting up user policies for users homed on Lync Server 2013, see [Setting up user policies for Archiving in Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span> <span data-ttu-id="7910b-110">Ausführliche Informationen zur Funktionsweise von Richtlinien finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7910b-110">For details about how policies work, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7910b-111">Wenn Sie Exchange 2013 und lync Server 2013 in derselben Gesamtstruktur bereitstellen, steuern Ihre Exchange 2013-In-Place Richtlinien die Archivierung.</span><span class="sxs-lookup"><span data-stu-id="7910b-111">If you deploy Exchange 2013 and Lync Server 2013 in the same forest, your Exchange 2013 In-Place Hold policies control archiving.</span></span> <span data-ttu-id="7910b-112">Wenn Sie Exchange 2013 und lync Server 2013 in getrennten Gesamtstrukturen bereitstellen, lesen Sie "Bereitstellen von lync Server und Microsoft Exchange in verschiedenen Gesamtstrukturen" in der <A href="lync-server-2013-deployment-checklist-for-archiving.md">Bereitstellungsprüfliste für die Archivierung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7910b-112">If you deploy Exchange 2013 and Lync Server 2013 in separate forests, see “Deploying Lync Server and Microsoft Exchange in Different Forests” in <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>.</span></span>



<span data-ttu-id="7910b-113"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="7910b-113"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

