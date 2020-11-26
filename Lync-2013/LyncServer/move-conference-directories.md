---
title: Verschieben von Konferenz Verzeichnissen
description: Verschieben von Konferenz Verzeichnissen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a91c30c0bedc84c684a096f5ea482fa911dc798
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49438550"
---
# <a name="move-conference-directories"></a><span data-ttu-id="3c7fa-103">Verschieben von Konferenz Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="3c7fa-103">Move conference directories</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="3c7fa-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="3c7fa-104">

<span> </span></span></span>

<span data-ttu-id="3c7fa-105">_**Letztes Änderungsdatum des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="3c7fa-105">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="3c7fa-106">Bevor Sie einen Pool außer Betrieb nehmen, müssen Sie für jedes Konferenzverzeichnis in Ihrem Office Communications Server 2007 R2-Pool die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="3c7fa-106">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="3c7fa-107">So verschieben Sie ein Konferenzverzeichnis in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c7fa-107">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="3c7fa-108">Öffnen Sie die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="3c7fa-108">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="3c7fa-109">Führen Sie die folgenden Befehle aus, um die Identität der Konferenzverzeichnisse in Ihrer Organisation zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="3c7fa-109">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="3c7fa-110">Da dieses Cmdlet alle Konferenzverzeichnisse in Ihrer Organisation zurückgibt, möchten Sie möglicherweise die Ergebnisse auf den Pool beschränken, den Sie außer Betrieb nehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="3c7fa-110">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission.</span></span> <span data-ttu-id="3c7fa-111">Wenn Sie beispielsweise einen Pool mit dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) pool01.contoso.net:</span><span class="sxs-lookup"><span data-stu-id="3c7fa-111">For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="3c7fa-112">Dieses Cmdlet gibt alle Konferenzverzeichnisse zurück, in denen die Dienst-ID den FQDN-pool01.contoso.NET enthält.</span><span class="sxs-lookup"><span data-stu-id="3c7fa-112">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="3c7fa-113">Führen Sie für jedes Konferenzverzeichnis im Pool die folgenden Schritte aus, um Konferenzverzeichnisse zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="3c7fa-113">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="3c7fa-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3c7fa-114">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="3c7fa-115">Möglicherweise tritt ein Fehler auf, der nachfolgend gezeigt wird, der von der lync Server-Verwaltungsshell verursacht wird, die einen aktualisierten Satz von Berechtigungen aus Active Directory erfordert.</span><span class="sxs-lookup"><span data-stu-id="3c7fa-115">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="3c7fa-116">Wenn Sie den Fehler beheben möchten, schließen Sie das aktuelle Fenster, öffnen Sie eine neue lync Server-Verwaltungsshell, und führen Sie den Befehl erneut aus.</span><span class="sxs-lookup"><span data-stu-id="3c7fa-116">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="3c7fa-117">![Move-CsConferenceDirectory-Fehlerausgabe](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory Fehlerausgabe")</span><span class="sxs-lookup"><span data-stu-id="3c7fa-117">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

<span data-ttu-id="3c7fa-118"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="3c7fa-118"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

