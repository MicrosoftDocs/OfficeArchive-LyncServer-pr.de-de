---
title: 'Lync Server 2013: Deaktivieren der Netzwerkmedien Umgehung'
description: 'Lync Server 2013: Deaktivieren der Netzwerkmedien Umgehung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1472711417218aa87936a3ccabe1bb465dd07c20
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49429098"
---
# <a name="disabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="a2a38-103">Deaktivieren der Netzwerkmedien Umgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2a38-103">Disabling network media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="a2a38-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="a2a38-104">

<span> </span></span></span>

<span data-ttu-id="a2a38-105">_**Letztes Änderungsdatum des Themas:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="a2a38-105">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="a2a38-106">Medienumgehungseinstellungen gelten global für eine Microsoft lync Server 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a2a38-106">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="a2a38-107">Die medienumgehung ermöglicht Anrufe, den Vermittlungs Server zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="a2a38-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="a2a38-108">Ausführliche Informationen zur Verwendung der medienumgehung finden Sie unter [Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) im Abschnitt Planung. Sie können die medienumgehung in der lync Server-Systemsteuerung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a2a38-108">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.You can disable media bypass from the Lync Server Control Panel.</span></span> <span data-ttu-id="a2a38-109">Details zum Aktivieren und Konfigurieren der medialen Umgehung finden Sie unter [Aktivieren der Netzwerkmedien Umgehung in lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="a2a38-109">For details on enabling and configuring medial bypass, see [Enabling network media bypass in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span></span>

<div>

## <a name="to-disable-media-bypass"></a><span data-ttu-id="a2a38-110">So deaktivieren Sie die medienumgehung</span><span class="sxs-lookup"><span data-stu-id="a2a38-110">To disable media bypass</span></span>

1.  <span data-ttu-id="a2a38-111">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a2a38-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a2a38-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a2a38-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a2a38-113">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a2a38-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a2a38-114">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Global**.</span><span class="sxs-lookup"><span data-stu-id="a2a38-114">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="a2a38-115">Klicken Sie auf der Seite **Global** auf die **globale** Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a2a38-115">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="a2a38-116">Es gibt immer nur eine Konfiguration, und Sie wird immer als "Global" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a2a38-116">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="a2a38-117">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a2a38-117">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="a2a38-118">Deaktivieren Sie auf der Seite **globale Einstellungen bearbeiten** das Kontrollkästchen **medienumgehung aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="a2a38-118">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="a2a38-119">Klicken Sie auf **Commit** , um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a2a38-119">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a2a38-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2a38-120">See Also</span></span>


[<span data-ttu-id="a2a38-121">Aktivieren der Netzwerkmedien Umgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2a38-121">Enabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-network-media-bypass.md)  
  

<span data-ttu-id="a2a38-122"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="a2a38-122"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

