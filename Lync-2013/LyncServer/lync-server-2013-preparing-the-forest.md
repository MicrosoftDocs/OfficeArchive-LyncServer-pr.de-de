---
title: 'Lync Server 2013: Vorbereiten der Gesamtstruktur'
description: 'Lync Server 2013: Vorbereiten der Gesamtstruktur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 275d861ebfe7e0350e7baf120b6e6f2bae6a26ad
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49424109"
---
# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="79e00-103">Vorbereiten der Gesamtstruktur für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79e00-103">Preparing the forest for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="79e00-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="79e00-104">

<span> </span></span></span>

<span data-ttu-id="79e00-105">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="79e00-105">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="79e00-106">Die Gesamtstrukturvorbereitung erstellt Active Directory-globale Einstellungen und-Objekte sowie universelle Active Directory-Gruppen für die Verwendung durch lync Server 2013 und gewährt geeignete Zugriffsberechtigungen für die Active Directory-Objekte.</span><span class="sxs-lookup"><span data-stu-id="79e00-106">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="79e00-107">Eine Beschreibung der universellen Gruppen und der globalen Einstellungen und Objekte, die von der Gesamtstrukturvorbereitung erstellt wurden, finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in lync Server 2013 vorgenommen](lync-server-2013-changes-made-by-forest-preparation.md)wurden.</span><span class="sxs-lookup"><span data-stu-id="79e00-107">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="79e00-108">Die Gesamtstrukturvorbereitung erstellt auch Objekte, die Eigenschaftensätze und Anzeigebezeichner enthalten, die von lync Server 2013 verwendet werden, und speichert Sie im Konfigurationscontainer.</span><span class="sxs-lookup"><span data-stu-id="79e00-108">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="79e00-109">Stellen Sie sicher, dass die Schema Vorbereitungs Änderungen auf alle Domänencontroller repliziert wurden, bevor Sie das Verfahren für die Gesamtstrukturvorbereitung durchführen.</span><span class="sxs-lookup"><span data-stu-id="79e00-109">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="79e00-110">Wenn die Replikation nicht abgeschlossen ist, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="79e00-110">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="79e00-111">Wenn Sie eine neue lync Server-Bereitstellung durchführen, müssen Sie die globalen Einstellungen im Container Konfiguration speichern.</span><span class="sxs-lookup"><span data-stu-id="79e00-111">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="79e00-112">Wenn Sie ein Upgrade von einer früheren Version durchführen und die globalen Einstellungen weiterhin im Systemcontainer speichern, können Sie den Systemcontainer weiterhin verwenden.</span><span class="sxs-lookup"><span data-stu-id="79e00-112">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="79e00-113">Sie müssen ein Mitglied der Gruppe "Organisations-Admins" oder "Domänen-Admins" für die Gesamtstruktur-Stammdomäne sein, um dieses Verfahren ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="79e00-113">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="79e00-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="79e00-114">In This Section</span></span>

  - [<span data-ttu-id="79e00-115">Ausführen der Gesamtstrukturvorbereitung für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79e00-115">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="79e00-116">Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79e00-116">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

<span data-ttu-id="79e00-117"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="79e00-117"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

