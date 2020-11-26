---
title: 'Lync Server 2013: Testen des Directors'
description: 'Lync Server 2013: Testen des Directors'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f4cec23be01add5c02cc960cfe68c9256da07d8
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49441217"
---
# <a name="test-the-director-in-lync-server-2013"></a><span data-ttu-id="24ac7-103">Testen des Directors in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24ac7-103">Test the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="24ac7-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="24ac7-104">

<span> </span></span></span>

<span data-ttu-id="24ac7-105">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="24ac7-105">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="24ac7-106">Zu diesem Zeitpunkt haben Sie einen Director-oder Director-Pool konfiguriert, aber Ihre DNS-SRV-Einträge (Domain Name System) verweisen weiterhin auf Clients, um sich mit einem Pool oder einem Standard Edition-Server anzumelden.</span><span class="sxs-lookup"><span data-stu-id="24ac7-106">At this stage, you have a Director or Director pool configured, but your Domain Name System (DNS) SRV entries still point clients to log on by using a pool or Standard Edition server.</span></span> <span data-ttu-id="24ac7-107">Bevor Sie den DNS-Eintrag ändern, damit lync 2013-Clients sich automatisch mithilfe des Directors anmelden, testen Sie einen Client, indem Sie ihn manuell auf den Director verweisen.</span><span class="sxs-lookup"><span data-stu-id="24ac7-107">Before changing the DNS record to make Lync 2013 clients log on automatically by using the Director, test a client by manually pointing it to the Director.</span></span>

<div>

## <a name="to-test-the-deployment"></a><span data-ttu-id="24ac7-108">So testen Sie die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="24ac7-108">To test the deployment</span></span>

1.  <span data-ttu-id="24ac7-109">Melden Sie sich bei dem Computer an, auf dem Sie die lync Server-Systemsteuerung mit einem Domänenkonto installiert haben, das Teil der **CSAdministrator** -Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="24ac7-109">Log on to the computer on which you have the Lync Server Control Panel installed with a domain account that is part of the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="24ac7-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="24ac7-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="24ac7-111">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="24ac7-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="24ac7-112">Klicken Sie im Navigationsbereich auf **Topologie**, und bestätigen Sie in der Spalte **Status** , dass ein grüner Server mit einem Pfeil (also ![Serversymbol mit grünem Pfeil](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server Symbol mit grünem Pfeil")) für Ihren Director-oder Director-Pool vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="24ac7-112">In the navigation pane, click **Topology**, and in the **Status** column confirm that there is a green server with an arrow (that is, ![Server icon with green arrow](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server icon with green arrow")) for your Director or Director pool.</span></span>

4.  <span data-ttu-id="24ac7-113">Verbinden Sie zwei Clientcomputer, auf denen der lync Server 2013-Client installiert ist, und melden Sie sich mit einem anderen Benutzerkonto an, das für lync Server 2013 auf jedem Computer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="24ac7-113">Connect two client computers that have the Lync Server 2013 client installed and log on with a different user account enabled for Lync Server 2013 to each computer.</span></span>

5.  <span data-ttu-id="24ac7-114">Klicken Sie auf einem der Clientcomputer auf das Menü **Optionen** , wählen Sie die Gruppe **persönliche** Einstellungen aus, klicken Sie auf **erweitert**, klicken Sie auf **manuelle Konfiguration**, und legen Sie dann den **internen Server Namen oder die IP-Adresse** auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des neuen Director-oder Director-Pools.</span><span class="sxs-lookup"><span data-stu-id="24ac7-114">On one of the client computers, click the **Options** menu, select the **Personal** settings group, click **Advanced**, click **Manual Configuration**, and then set the **Internal Server name or IP address** to the fully qualified domain name (FQDN) of the new Director or Director pool.</span></span>

6.  <span data-ttu-id="24ac7-115">Melden Sie sich bei beiden Clients an, und stellen Sie sicher, dass sich der Client, der sich mit dem Director anmeldet, erfolgreich anmelden kann, den Anwesenheitsstatus des anderen Benutzers anzeigen und Sofortnachrichten austauschen können.</span><span class="sxs-lookup"><span data-stu-id="24ac7-115">Log on to both clients and verify that the client logging on by using the Director is able to log on successfully, see the presence status of the other user, and that they can exchange instant messages.</span></span>

<span data-ttu-id="24ac7-116"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="24ac7-116"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

