---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für die Archivierung'
description: 'Lync Server 2013: Konfigurieren der Unterstützung für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Archiving
ms:assetid: 579283fe-909c-46f2-a0c9-52ca1e7d63d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204905(v=OCS.15)
ms:contentKeyID: 48184187
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4209614ed1248ab0caf3cf438a922d569ba79630
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49432632"
---
# <a name="configuring-support-for-archiving-in-lync-server-2013"></a><span data-ttu-id="7dfad-103">Konfigurieren der Unterstützung für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dfad-103">Configuring support for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="7dfad-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="7dfad-104">

<span> </span></span></span>

<span data-ttu-id="7dfad-105">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7dfad-105">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7dfad-106">Nachdem Sie der Topologie eine Archivierung hinzugefügt und die neue Topologie veröffentlicht haben, müssen Sie die Optionen für die anfängliche Implementierung der Archivierung in Ihrer Bereitstellung konfigurieren und dann eine oder mehrere Archivierungsrichtlinien konfigurieren, um die Archivierung für Ihre Bereitstellung und optional für bestimmte Websites und Benutzer zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7dfad-106">After adding Archiving to your topology and publishing the new topology, you need to configure options for how Archiving is initially implemented in your deployment, and then configure one or more Archiving policies to enable Archiving for your deployment and, optionally, for specific sites and users.</span></span> <span data-ttu-id="7dfad-107">Sie können hierzu die lync Server 2013-Systemsteuerung verwenden.</span><span class="sxs-lookup"><span data-stu-id="7dfad-107">You can use Lync Server 2013 Control Panel to do this.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7dfad-108">Nach der Bereitstellung können Sie Archivierungseinstellungen ändern, um die Archivierung zu deaktivieren oder zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7dfad-108">After deployment, you can change Archiving settings to disable or enable Archiving.</span></span> <span data-ttu-id="7dfad-109">Ausführliche Informationen dazu, wie Sie Archivierungsunterstützung für die tägliche Verwaltung implementieren oder neue Anforderungen in Ihrer Organisation nach der Bereitstellung erfüllen, finden Sie unter <A href="lync-server-2013-managing-archiving.md">Verwalten der lync Server 2013-Archivierung</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7dfad-109">For details about how to implement archiving support for day-to-day management or to meet new requirements in your organization after deployment, see <A href="lync-server-2013-managing-archiving.md">Managing Lync Server 2013 Archiving</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7dfad-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7dfad-110">In This Section</span></span>

  - [<span data-ttu-id="7dfad-111">Konfigurieren von Archivierungsoptionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dfad-111">Configuring Archiving options in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options.md)

  - [<span data-ttu-id="7dfad-112">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dfad-112">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)

  - [<span data-ttu-id="7dfad-113">Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dfad-113">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

<span data-ttu-id="7dfad-114"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="7dfad-114"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

