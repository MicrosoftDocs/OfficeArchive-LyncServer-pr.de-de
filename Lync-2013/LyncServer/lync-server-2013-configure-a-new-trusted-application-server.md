---
title: 'Lync Server 2013: Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers'
description: 'Lync Server 2013: Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3cc13c747c5755297b01ae36f27f06d19591acc
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394018"
---
# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="01341-103">Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01341-103">Configure a new trusted application server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="01341-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="01341-104">

<span> </span></span></span>

<span data-ttu-id="01341-105">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="01341-105">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="01341-106">Bei einer vertrauenswürdigen Anwendung handelt es sich um eine Anwendung, die auf dem Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK basiert, das von Microsoft lync Server 2013 als vertrauenswürdig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="01341-106">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="01341-107">Ausführliche Informationen zu UCMA-Anwendungen finden Sie unter "Unified Communications Managed API 3,0 Core SDK Documentation" unter [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320) .</span><span class="sxs-lookup"><span data-stu-id="01341-107">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="01341-108">Informationen zum Konfigurieren von Microsoft Outlook Web Access (OWA) und lync Server 2013 finden Sie unter "Konfigurieren der Integration von Outlook Web App und lync Server 2010" in der Microsoft Exchange Server 2013-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="01341-108">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="01341-109">Um eine Topologie beim Hinzufügen oder Entfernen einer Serverrolle erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, sollten Sie als Benutzer angemeldet sein, der Mitglied der Gruppen RTCUniversalServerAdmins und Domänenadministratoren ist.</span><span class="sxs-lookup"><span data-stu-id="01341-109">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="01341-110">Es ist auch möglich, die richtigen Administratorberechtigungen und-Rechte für das Hinzufügen von Serverrollen zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="01341-110">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="01341-111">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="01341-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="01341-112">Bei anderen Konfigurationsänderungen ist nur die Mitgliedschaft in der RTCUniversalServerAdmins-Gruppe erforderlich.</span><span class="sxs-lookup"><span data-stu-id="01341-112">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="01341-113">So konfigurieren Sie einen vertrauenswürdigen Anwendungsserver</span><span class="sxs-lookup"><span data-stu-id="01341-113">To configure a trusted application server</span></span>

1.  <span data-ttu-id="01341-114">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="01341-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="01341-115">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="01341-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="01341-116">Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen aus**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="01341-116">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="01341-117">Klicken Sie im Dialogfeld **Topologie speichern** unter auf die Topologie-Generator-Datei, die Sie verwenden möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="01341-117">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="01341-118">Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver**, und klicken Sie dann auf **neuer vertrauenswürdiger Anwendungs Pool**.</span><span class="sxs-lookup"><span data-stu-id="01341-118">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="01341-119">Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, wählen Sie aus, ob es sich um einen Einzelserver-oder mehrere Server handelt, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="01341-119">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="01341-120">Wählen Sie auf der Seite **Nächster Hop auswählen** in der Liste den lync Server 2013-Front-End-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="01341-120">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="01341-121">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="01341-121">Click **Finish**.</span></span>

9.  <span data-ttu-id="01341-122">Wählen Sie den obersten Knoten **lync Server 2013** aus, und klicken Sie dann im Menü **Aktionen** auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="01341-122">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="01341-123">Der **Vertrauenswürdige Anwendungspool** sollte erfolgreich erstellt und dem richtigen Front-End-Pool zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="01341-123">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

<span data-ttu-id="01341-124"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="01341-124"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

