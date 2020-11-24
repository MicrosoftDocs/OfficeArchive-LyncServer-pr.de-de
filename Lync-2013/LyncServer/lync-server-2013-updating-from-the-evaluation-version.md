---
title: 'Lync Server 2013: Aktualisieren von der Evaluierungsversion'
description: 'Lync Server 2013: Aktualisierung aus der Evaluierungsversion.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 340badf9f5d2506c50cf8c03faa82223eabbd5af
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394843"
---
# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="b930f-103">Aktualisieren von der Evaluierungsversion von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b930f-103">Updating from the evaluation version of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="b930f-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="b930f-104">

<span> </span></span></span>

<span data-ttu-id="b930f-105">_**Letztes Änderungsdatum des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="b930f-105">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="b930f-106">Wenn Sie die Evaluierungsversion von Microsoft lync Server 2013 installiert haben, müssen Sie diese Installation eventuell mit einer lizenzierten Kopie der Software aktualisieren. Das liegt daran, dass die Evaluierungsversion 180 Tage nach der Installation abläuft.</span><span class="sxs-lookup"><span data-stu-id="b930f-106">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="b930f-107">Sie müssen die Evaluierungsversion jedoch nicht vollständig deinstallieren und dann die lizenzierte Version installieren.</span><span class="sxs-lookup"><span data-stu-id="b930f-107">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="b930f-108">Nachdem Sie einen gültigen Lizenzierungsschlüssel erhalten haben, können Sie stattdessen die Evaluierungsversion von lync Server 2013 aktualisieren, indem Sie auf jedem Computer, der als lync Server-Front-End-Server,-Director oder-Edgeserver fungiert, die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="b930f-108">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="b930f-109">Beachten Sie, dass Sie keine Computer aktualisieren müssen, die andere Serverrollen ausführen, beispielsweise einen Überwachungsserver oder einen Archivierungsserver.</span><span class="sxs-lookup"><span data-stu-id="b930f-109">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="b930f-110">Aktualisieren von der Evaluierungs Version von Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b930f-110">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="b930f-111">So aktualisieren Sie einen Computer aus der Evaluierungsversion von lync Server 2013 auf die lizenzierte Version der Software:</span><span class="sxs-lookup"><span data-stu-id="b930f-111">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="b930f-112">**Aktualisieren von der Evaluierungs Version von Microsoft lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="b930f-112">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="b930f-113">Melden Sie sich als lokaler Administrator am Computer an.</span><span class="sxs-lookup"><span data-stu-id="b930f-113">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="b930f-114">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b930f-114">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b930f-115">Geben Sie in der lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="b930f-115">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="b930f-116">Beachten Sie, dass Sie möglicherweise den vollständigen Pfad zur Datei server.msi angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="b930f-116">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="b930f-117">Diese Datei befindet sich im Setup-Ordner der lync Server Volume Media-Installationsdateien.</span><span class="sxs-lookup"><span data-stu-id="b930f-117">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="b930f-118">Nachdem die Ausführung von Setup beendet wurde, geben Sie Folgendes an der Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="b930f-118">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="b930f-119">Wiederholen Sie diesen Vorgang auf jedem anderen Front-End-Server, Director oder Edgeserver, auf dem eine Evaluierungskopie von lync Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b930f-119">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="b930f-120">Dieses Verfahren sollte auch für alle Branch Office-Server ausgeführt werden, die mithilfe der lync Server Media-Installationsdateien bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="b930f-120">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="b930f-121">Wenn Sie nicht sicher sind, ob die Evaluierungsversion von lync Server auf einem bestimmten Computer ausgeführt wird, können Sie dies überprüfen, indem Sie den folgenden Befehl in der lync Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="b930f-121">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="b930f-122">Mit dem Cmdlet [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) wird der lokale Computer analysiert und eine der folgenden Berichte zurückgemeldet:</span><span class="sxs-lookup"><span data-stu-id="b930f-122">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="b930f-123">, Dass der lync Server-Volumenlizenzschlüssel auf dem Computer installiert wurde, was bedeutet, dass keine Aktualisierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b930f-123">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="b930f-124">, Dass der lync Server-Evaluierungslizenz Schlüssel installiert wurde, was bedeutet, dass der Computer aktualisiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="b930f-124">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="b930f-125">, Dass auf dem Computer kein Volumenlizenzschlüssel erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b930f-125">That no volume license key is required on the computer.</span></span> <span data-ttu-id="b930f-126">Das Aktualisieren von der Evaluierungsversion auf die lizenzierte Version ist nur auf Front-End-Servern, Directors und Edge-Servern erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b930f-126">Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

<span data-ttu-id="b930f-127"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="b930f-127"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

