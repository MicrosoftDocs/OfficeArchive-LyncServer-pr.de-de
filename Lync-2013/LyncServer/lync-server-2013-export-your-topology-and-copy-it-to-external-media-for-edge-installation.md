---
title: Exportieren der Topologie und Kopieren auf externe Medien zur Edgeinstallation
description: Exportieren Sie Ihre Topologie, und kopieren Sie Sie für die Edge-Installation auf externe Medien.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47fcee032b4c0e667455ae7f35afe8b99c2d12cc
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49393782"
---
# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="f0122-103">Exportieren der Lync Server 2013-Topologie und Kopieren auf externe Medien zur Edgeinstallation</span><span class="sxs-lookup"><span data-stu-id="f0122-103">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="f0122-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="f0122-104">

<span> </span></span></span>

<span data-ttu-id="f0122-105">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="f0122-105">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="f0122-106">Nachdem Sie Ihre Topologie veröffentlicht haben, benötigt der lync Server-Bereitstellungs-Assistent Zugriff auf die Daten des zentralen Verwaltungsspeichers, um den Bereitstellungsprozess auf dem Server zu starten.</span><span class="sxs-lookup"><span data-stu-id="f0122-106">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="f0122-107">Im internen Netzwerk stehen die Daten direkt von den Servern zur Verfügung, aber Edgeserver, die nicht zur internen Domäne gehören, können nicht auf die Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f0122-107">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="f0122-108">Damit die Topologie-Konfigurationsdaten für eine Edge-Server-Bereitstellung zur Verfügung stehen, müssen Sie die Topologiedaten in eine Datei exportieren und auf externe Medien (beispielsweise ein USB-Laufwerk oder eine Netzwerkfreigabe, die vom Edgeserver verfügbar ist) kopieren, bevor Sie den lync Server-Bereitstellungs-Assistenten auf dem Edgeserver ausführen.</span><span class="sxs-lookup"><span data-stu-id="f0122-108">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="f0122-109">Gehen Sie wie folgt vor, um Ihre Topologie-Konfigurationsdaten auf dem von Ihnen bereitgestellten Edgeserver zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="f0122-109">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f0122-110">Nachdem Sie lync Server 2013 auf einem Edgeserver installiert haben, können Sie den Edgeserver mithilfe der Verwaltungstools im internen Netzwerk verwalten, die die Konfiguration automatisch auf alle Edgeserver in Ihrer Bereitstellung replizieren.</span><span class="sxs-lookup"><span data-stu-id="f0122-110">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="f0122-111">Die einzige Ausnahme ist das zuweisen und Installieren von Zertifikaten sowie das Beenden und starten von Diensten, die beide auf dem Edgeserver ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f0122-111">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="f0122-112">So stellen Sie Ihre Topologiedaten mithilfe der lync Server-Verwaltungsshell auf einem Edgeserver zur Verfügung</span><span class="sxs-lookup"><span data-stu-id="f0122-112">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="f0122-113">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f0122-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f0122-114">Führen Sie in der lync Server-Verwaltungsshell das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="f0122-114">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="f0122-115">Kopieren Sie die exportierte Datei auf externe Medien (beispielsweise ein USB-Laufwerk oder eine Netzwerkfreigabe, die während der Bereitstellung vom Edgeserver verfügbar ist).</span><span class="sxs-lookup"><span data-stu-id="f0122-115">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

<span data-ttu-id="f0122-116"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="f0122-116"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

