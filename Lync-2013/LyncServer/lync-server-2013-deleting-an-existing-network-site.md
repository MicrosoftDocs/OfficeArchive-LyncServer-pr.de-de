---
title: 'Lync Server 2013: Löschen einer vorhandenen Netzwerk Website'
description: 'Lync Server 2013: Löschen einer vorhandenen Netzwerk Website.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cef4774ee71aaf6851757d5b88d30138fc34997
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49430357"
---
# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a><span data-ttu-id="0c9b0-103">Löschen einer vorhandenen Netzwerk Website in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c9b0-103">Deleting an existing network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="0c9b0-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="0c9b0-104">

<span> </span></span></span>

<span data-ttu-id="0c9b0-105">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0c9b0-105">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0c9b0-106">Netzwerk Websites sind die Büros oder Standorte, die in den einzelnen Regionen einer Anrufannahme Steuerung oder erweiterten 9-1-1-Bereitstellung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-106">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="0c9b0-107">Sie können die lync Server 2013-Systemsteuerung verwenden, um Websites zu konfigurieren und Sie mit Regionen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-107">You can use the Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="0c9b0-108">Beispielsweise kann eine netzwerkregion für Nordamerika mit Netzwerken wie Chicago, Redmond und Vancouver verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-108">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="0c9b0-109">Eine CAC-Netzwerk Website muss für jede Website innerhalb einer Organisation erstellt werden, selbst wenn diese Website keine Bandbreiteneinschränkungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-109">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="0c9b0-110">In der lync Server-Systemsteuerung können Sie Netzwerk Websites erstellen, ändern und löschen.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-110">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="0c9b0-111">Gehen Sie wie folgt vor, um eine vorhandene Netzwerk Website zu löschen.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-111">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="0c9b0-112">Details zum Erstellen oder Ändern von Netzwerk Websites finden Sie unter [erstellen oder Ändern von Netzwerk Websites in lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span><span class="sxs-lookup"><span data-stu-id="0c9b0-112">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span></span>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="0c9b0-113">So löschen Sie eine Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="0c9b0-113">To delete a network site</span></span>

1.  <span data-ttu-id="0c9b0-114">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0c9b0-115">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0c9b0-116">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0c9b0-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0c9b0-117">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-117">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="0c9b0-118">Klicken Sie auf der Seite **Website** auf die Website, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-118">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0c9b0-119">Sie können mehr als eine Website gleichzeitig löschen.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-119">You can delete more than one site at a time.</span></span> <span data-ttu-id="0c9b0-120">Drücken Sie dazu STRG, und wählen Sie mehrere Websites aus, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-120">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="0c9b0-121">Wenn Sie alle Websites auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="0c9b0-121">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="0c9b0-122">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-122">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="0c9b0-123">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-123">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="0c9b0-124">Sie können eine Netzwerk Website nicht entfernen, wenn Sie einem Netzwerk-Subnetz zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-124">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="0c9b0-125">Wenn Sie versuchen, eine Website zu entfernen, die einem Subnetz zugeordnet ist, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c9b0-125">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="0c9b0-126">Wenn Sie feststellen möchten, ob eine Website mit Subnetzen verknüpft ist, klicken Sie auf die Website, und klicken Sie dann im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="0c9b0-126">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    <span data-ttu-id="0c9b0-127"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="0c9b0-127"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

