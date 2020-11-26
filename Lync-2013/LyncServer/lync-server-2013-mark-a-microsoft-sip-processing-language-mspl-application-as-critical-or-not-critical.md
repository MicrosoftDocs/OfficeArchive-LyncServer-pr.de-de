---
title: 'Lync Server 2013: Kennzeichnen einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch'
description: 'Lync Server 2013: Kennzeichnen einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1f59fb6614416c1b0e4f49a766a1373483f509d
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425759"
---
# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="4aa07-103">Kennzeichnen einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aa07-103">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="4aa07-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="4aa07-104">

<span> </span></span></span>

<span data-ttu-id="4aa07-105">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4aa07-105">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4aa07-106">MSPL-Serveranwendungen (Microsoft SIP Processing Language) sind reine Skriptanwendungen, die die MSPL-Skriptsprache anstelle der Microsoft lync 2010-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="4aa07-106">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="4aa07-107">Einige MSPL-Serveranwendungen werden als kritisch angegeben.</span><span class="sxs-lookup"><span data-stu-id="4aa07-107">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="4aa07-108">Wenn ein Skript kritisch ist, muss das Skript beim Systemstart gestartet werden, damit lync Server 2013 gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4aa07-108">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="4aa07-109">Wenn das Skript fehlschlägt, während lync Server ausgeführt wird, wird der Server nicht heruntergefahren, aber er beendet das Senden von Datenverkehr an das Skript und schreibt Fehler im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="4aa07-109">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="4aa07-110">Mit der lync Server-Systemsteuerung können Sie MSPL-Serveranwendungen (Microsoft SIP Processing Language) als kritisch kennzeichnen oder die Markierung aufheben.</span><span class="sxs-lookup"><span data-stu-id="4aa07-110">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="4aa07-111">Diese Option wird nicht von allen Skripts unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4aa07-111">Not all scripts support this option.</span></span> <span data-ttu-id="4aa07-112">Das DefaultRouting-Skript wird beispielsweise als kritisch markiert, und diese Option kann für DefaultRouting nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4aa07-112">For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="4aa07-113">Markieren oder Aufheben der Markierung einer MSPL-Serveranwendung als kritisch</span><span class="sxs-lookup"><span data-stu-id="4aa07-113">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="4aa07-114">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="4aa07-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="4aa07-115">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4aa07-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4aa07-116">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4aa07-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4aa07-117">Klicken Sie in der linken Navigationsleiste auf **Topologie** , und klicken Sie dann auf **Server Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="4aa07-117">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="4aa07-118">Klicken Sie auf der Seite **Serveranwendung** auf eine Spaltenüberschrift, um die Anwendungen bei Bedarf zu sortieren, und klicken Sie dann auf die Serveranwendung, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="4aa07-118">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="4aa07-119">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="4aa07-119">Click **Action**.</span></span>

6.  <span data-ttu-id="4aa07-120">Klicken Sie auf **als kritisch kennzeichnen** oder **als kritisch aufheben** (das heißt, wenn das Skript diese Option unterstützt).</span><span class="sxs-lookup"><span data-stu-id="4aa07-120">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4aa07-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4aa07-121">See Also</span></span>


[<span data-ttu-id="4aa07-122">Aktivieren oder Deaktivieren einer Microsoft SIP Processing Language (MSPL)-Serveranwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aa07-122">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="4aa07-123">Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aa07-123">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="4aa07-124">Verwalten der Lync Server 2013-Topologie</span><span class="sxs-lookup"><span data-stu-id="4aa07-124">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

<span data-ttu-id="4aa07-125"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="4aa07-125"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

