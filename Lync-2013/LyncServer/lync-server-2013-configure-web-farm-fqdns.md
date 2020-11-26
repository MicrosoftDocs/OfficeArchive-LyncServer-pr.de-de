---
title: 'Lync Server 2013: Konfigurieren von Webfarm-FQDNs'
description: 'Lync Server 2013: Konfigurieren von FQDNs für Webfarmen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a07faac4d4809ffe10e7ca3699e7441e6dbcb7b
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433549"
---
# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="a9eb2-103">Konfigurieren von Webfarm-FQDNs für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9eb2-103">Configure web farm FQDNs for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="a9eb2-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="a9eb2-104">

<span> </span></span></span>

<span data-ttu-id="a9eb2-105">_**Letztes Änderungsdatum des Themas:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="a9eb2-105">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="a9eb2-106">Wenn Sie die Konfiguration des Standard Edition-Servers, des Front-End-Pools, des Director-oder Director-Pools in Topology Builder definiert haben, konfigurieren Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für externe Webdienste.</span><span class="sxs-lookup"><span data-stu-id="a9eb2-106">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="a9eb2-107">Während des Anmeldeprozesses eines Clients, der sich im Standard Edition-Server oder-Front-End-Pool befindet, werden die konfigurierten Webdienste-FQDNs über die in-Band-Bereitstellung gesendet.</span><span class="sxs-lookup"><span data-stu-id="a9eb2-107">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="a9eb2-108">Wenn Sie die externe Webdienste-URL hinzufügen oder ändern müssen, verwenden Sie den Topologie-Generator, um die Webdienstkonfiguration mithilfe des in diesem Thema beschriebenen Verfahrens zu konfigurieren oder neu zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a9eb2-108">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="a9eb2-109">So konfigurieren Sie einen externen Pool-FQDN für Webdienste</span><span class="sxs-lookup"><span data-stu-id="a9eb2-109">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="a9eb2-110">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="a9eb2-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a9eb2-111">Klicken Sie im Topologie-Generator in der Konsolenstruktur unter **Front Ends der Standard Edition**, **Enterprise Edition-Front-Ends** und **Directors** mit der rechten Maustaste auf den Namen des Pools, den Sie bearbeiten möchten, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a9eb2-111">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="a9eb2-112">Fügen Sie im Abschnitt **Webdienst** den **FQDN externer Webdienste** hinzu, oder bearbeiten Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="a9eb2-112">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="a9eb2-113">Überprüfen und Anpassen der **Abhör Anschlüsse** für http und HTTPS</span><span class="sxs-lookup"><span data-stu-id="a9eb2-113">Review and adjust the **Listening ports** for both HTTP and HTTPS.</span></span> <span data-ttu-id="a9eb2-114">Die Standardeinstellungen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a9eb2-114">The defaults will be:</span></span>
    
      - <span data-ttu-id="a9eb2-115">**Abhör Anschlüsse:** HTTP 8080, HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="a9eb2-115">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="a9eb2-116">**Veröffentlichte Ports:** HTTP 80, HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="a9eb2-116">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="a9eb2-117">Hierbei handelt **es sich um den Port** , in dem die externen Webdienste so konfiguriert werden, dass Sie Anforderungen vom Reverseproxy empfangen, und die **veröffentlichten** Ports sind die Ports, die extern vom Reverse-Proxy veröffentlicht werden und während der in-Band-Bereitstellung an Clients mitgeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="a9eb2-117">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="a9eb2-118">Wenn Sie Ihre Ergänzungen und Updates abgeschlossen haben, klicken Sie auf **OK** , um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="a9eb2-118">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="a9eb2-119">Klicken Sie mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="a9eb2-119">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a9eb2-120">Nachdem die Veröffentlichung erfolgreich abgeschlossen wurde, wird möglicherweise ein Link angezeigt, der Sie darüber informiert, dass weitere Schritte ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a9eb2-120">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="a9eb2-121">Wenn Sie auf den Link klicken, wird eine Liste der Server geöffnet, die von den im Topologie-Generator vorgenommenen Änderungen betroffen sind, die erfordern, dass Sie den lync Server-Bereitstellungs-Assistenten auf jedem aufgelisteten Server erneut ausführen, um die Konfiguration für hinzugefügte, entfernte oder geänderte Komponenten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a9eb2-121">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="a9eb2-122">Wiederholen Sie diese Schritte für jeden Standard Edition-Server, Front-End-Pool, Director-oder Director-Pool in der Organisation.</span><span class="sxs-lookup"><span data-stu-id="a9eb2-122">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

<span data-ttu-id="a9eb2-123"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="a9eb2-123"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

