---
title: 'Lync Server 2013: Wiederherstellen eines Dateispeichers'
description: 'Lync Server 2013: Wiederherstellen eines Dateispeichers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 201c4b20f224fa3a25e931689e564410c60143e6
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49436251"
---
# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="f7104-103">Wiederherstellen eines Dateispeichers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7104-103">Restoring a file store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="f7104-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="f7104-104">

<span> </span></span></span>

<span data-ttu-id="f7104-105">_**Letztes Änderungsdatum des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="f7104-105">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="f7104-106">Dateispeicher für die Standard Edition befinden sich normalerweise auf dem Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="f7104-106">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="f7104-107">Dateispeicher für Enterprise Edition befinden sich in der Regel auf einem Dateiserver oder Cluster.</span><span class="sxs-lookup"><span data-stu-id="f7104-107">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="f7104-108">Im folgenden Verfahren wird beschrieben, wie Sie einen Dateispeicher wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="f7104-108">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="f7104-109">So stellen Sie einen Dateispeicher wieder her</span><span class="sxs-lookup"><span data-stu-id="f7104-109">To restore a File Store</span></span>

1.  <span data-ttu-id="f7104-110">Wenn ein Dateispeicher fehlschlägt, kopieren Sie den entsprechenden Dateispeicher aus $Backup \\ in den Dateispeicher Speicherort auf dem Dateiserver oder Standard Edition-Server, und geben Sie dann den Ordner frei.</span><span class="sxs-lookup"><span data-stu-id="f7104-110">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f7104-111">Der Pfad und Dateinamen für den wiederhergestellten Dateispeicher sollten exakt mit dem gesicherten Dateispeicher identisch sein, damit die Komponenten, die die Dateien verwenden, darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="f7104-111">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="f7104-112">Legen Sie bei Bedarf die Zugriffssteuerungslisten (ACLs) für den Dateispeicher ab.</span><span class="sxs-lookup"><span data-stu-id="f7104-112">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="f7104-113">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f7104-113">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7104-114">Sie müssen diesen Schritt nur ausführen, wenn Sie den Topology Builder während des Wiederherstellungsprozesses nicht anderweitig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="f7104-114">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    <span data-ttu-id="f7104-115"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="f7104-115"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

