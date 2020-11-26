---
title: 'Lync Server 2013: Starten von Diensten auf Servern'
description: 'Lync Server 2013: Starten Sie Dienste auf Servern.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c238d7ddbba66604314d146a2e7f86eaa85eeb9f
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49441557"
---
# <a name="start-services-on-servers-for-lync-server-2013"></a><span data-ttu-id="ef695-103">Starten von Diensten auf Servern für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef695-103">Start services on servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="ef695-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="ef695-104">

<span> </span></span></span>

<span data-ttu-id="ef695-105">_**Letztes Änderungsdatum des Themas:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="ef695-105">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="ef695-106">Um dieses Verfahren erfolgreich abzuschließen, sollten Sie als Benutzer angemeldet sein, der ein Mitglied der RTCUniversalServerAdmins-Gruppe ist oder über die richtigen Berechtigungen delegiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ef695-106">To successfully complete this procedure you should be logged in as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="ef695-107">Details zum Delegieren von Berechtigungen finden Sie im Thema [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ef695-107">For details about delegating permissions, see the topic [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

<span data-ttu-id="ef695-108">Nachdem Sie den lokalen Konfigurationsspeicher auf Ihren Servern installiert, die lync Server 2013-Komponenten installiert und Zertifikate auf einem Front-End-Server oder Front-End-Server konfiguriert haben, müssen Sie die lync Server 2013-Dienste auf dem Server starten.</span><span class="sxs-lookup"><span data-stu-id="ef695-108">After you install the Local Configuration store on your servers, install the Lync Server 2013 components, and configure certificates on a Front End Server or Front End Server, you must start the Lync Server 2013 services on the server.</span></span> <span data-ttu-id="ef695-109">Gehen Sie wie folgt vor, um Dienste auf jedem Front-End-Server in Ihrer Bereitstellung zu starten.</span><span class="sxs-lookup"><span data-stu-id="ef695-109">Use the following procedure to start services on each Front End Server in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a><span data-ttu-id="ef695-110">So starten Sie Dienste auf einer Standard Edition oder einem Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="ef695-110">To start services on a Standard Edition or Front End Server</span></span>

1.  <span data-ttu-id="ef695-111">Klicken Sie im lync Server-Bereitstellungs-Assistenten auf der **lync Server 2013** -Seite neben **Schritt 4: Starten von Diensten** auf **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="ef695-111">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click **Run** next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="ef695-112">Klicken Sie auf der Seite **Dienste starten** auf **weiter** , um die lync Server-Dienste auf dem Server zu starten.</span><span class="sxs-lookup"><span data-stu-id="ef695-112">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="ef695-113">Klicken Sie nach dem erfolgreichen Start aller Dienste auf der Seite **Befehle ausführen** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ef695-113">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ef695-114">Der Befehl zum Starten der Dienste auf dem Server ist die beste Methode, um zu melden, dass die Dienste tatsächlich gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="ef695-114">The command to start the services on the server is a best effort method to report that the services have in fact started.</span></span> <span data-ttu-id="ef695-115">Diese Anzeige spiegelt jedoch möglicherweise nicht den tatsächlichen Status des jeweiligen Diensts wider.</span><span class="sxs-lookup"><span data-stu-id="ef695-115">It might not reflect the actual state of the service.</span></span> <span data-ttu-id="ef695-116">Wir empfehlen, dass Sie den Schritt <STRONG>Dienst Status (optional)</STRONG> unmittelbar nach dem <STRONG>Start der Dienste</STRONG> verwenden, um die Microsoft Management Console (MMC) zu öffnen und zu bestätigen, dass die Dienste erfolgreich gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="ef695-116">We recommend that you use the step <STRONG>Service Status (Optional)</STRONG> immediately following <STRONG>Start Services</STRONG> to open the Microsoft Management Console (MMC) and confirm that the services have started successfully.</span></span> <span data-ttu-id="ef695-117">Wenn ein lync Server-Dienst nicht gestartet wurde, können Sie mit der rechten Maustaste auf diesen Dienst in der MMC klicken, und klicken Sie dann auf <STRONG>Start</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ef695-117">If any Lync Server service has not started, you can right-click that service in the MMC, and then click <STRONG>Start</STRONG>.</span></span>

    
    <span data-ttu-id="ef695-118"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="ef695-118"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

