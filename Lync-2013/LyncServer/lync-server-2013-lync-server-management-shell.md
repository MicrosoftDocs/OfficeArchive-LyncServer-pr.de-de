---
title: 'Lync Server 2013: lync Server-Verwaltungsshell'
description: 'Lync Server 2013: lync Server-Verwaltungsshell.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45727c42899defcf20ce36e2a27a9268a52ecd71
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49426265"
---
# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="4ef78-103">Verwaltungsshell für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ef78-103">Lync Server 2013 Management Shell</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="4ef78-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="4ef78-104">

<span> </span></span></span>

<span data-ttu-id="4ef78-105">_**Letztes Änderungsdatum des Themas:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="4ef78-105">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ef78-106">Die Skype for Business-Cmdlet-Referenz wurde in docs.Microsoft.com verschoben.</span><span class="sxs-lookup"><span data-stu-id="4ef78-106">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="4ef78-107">Wenn Sie auf die Links unten klicken, gelangen Sie zur neuen docs.Microsoft.com-Seite.</span><span class="sxs-lookup"><span data-stu-id="4ef78-107">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="4ef78-108">Der Inhalt wird nun über GitHub freigegeben und steht für Community-Beiträge zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4ef78-108">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="4ef78-109">Möchten Sie einen Beitrag leisten?</span><span class="sxs-lookup"><span data-stu-id="4ef78-109">Interested in contributing?</span></span> <span data-ttu-id="4ef78-110">Schauen Sie sich die Readme-Datei im Repo hier an: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="4ef78-110">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="4ef78-111">Microsoft lync Server 2010 hat einen umfangreichen Satz neuer und verbesserter Features im Vergleich zu den in Microsoft Office Communications Server 2007 R2 verfügbaren Funktionen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4ef78-111">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="4ef78-112">Eine Verbesserung ist die Art und Weise, in der Sie Ihre Implementierung verwalten.</span><span class="sxs-lookup"><span data-stu-id="4ef78-112">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="4ef78-113">So gibt es beispielsweise eine neue Benutzeroberfläche, die so genannte lync Server-Systemsteuerung, die eine große Schicht von dem entspricht, was die meisten Personen mit der Microsoft Management Console gewohnt sind.</span><span class="sxs-lookup"><span data-stu-id="4ef78-113">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="4ef78-114">Eine weitere wesentliche Verbesserung der Verwaltbarkeit ist die Einbeziehung von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ef78-114">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="4ef78-115">Mit Windows PowerShell können Sie Microsoft-Anwendungen über die Befehlszeile verwalten.</span><span class="sxs-lookup"><span data-stu-id="4ef78-115">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="4ef78-116">Enthalten sind eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache.</span><span class="sxs-lookup"><span data-stu-id="4ef78-116">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="4ef78-117">Windows PowerShell wurde erst spät in 2006 als herunterladbare Version für das Windows-Betriebssystem eingeführt und als Befehlszeilenschnittstelle für die Verwaltbarkeit von Microsoft Exchange Server 2007 integriert.</span><span class="sxs-lookup"><span data-stu-id="4ef78-117">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="4ef78-118">Von diesem Zeitpunkt an wurde es weiter ausgebaut, und es wurde in die meisten Microsoft-Serverprodukte integriert, wobei es sich um die neueste Microsoft lync Server 2013 handelt.</span><span class="sxs-lookup"><span data-stu-id="4ef78-118">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="4ef78-119">Lync Server 2010 hat nahezu 550 produktspezifische Cmdlets eingeführt, mit denen Sie alle Aspekte Ihrer Bereitstellung verwalten können.</span><span class="sxs-lookup"><span data-stu-id="4ef78-119">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="4ef78-120">Die folgenden Abschnitte enthalten eine Liste der Cmdlets sowie Beschreibungen der Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="4ef78-120">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="4ef78-121">Diese Informationen stehen auch direkt über die Befehlszeile zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4ef78-121">This information is also available directly from the command line.</span></span> <span data-ttu-id="4ef78-122">Geben Sie einfach Folgendes an der Eingabeaufforderung der lync Server-Verwaltungsshell ein:</span><span class="sxs-lookup"><span data-stu-id="4ef78-122">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="4ef78-123">Wenn Sie beispielsweise Hilfeinformationen zum Cmdlet **New-CsVoicePolicy** von der Befehlszeile aus abrufen möchten, geben Sie folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="4ef78-123">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="4ef78-124">Wissenswertes zu Windows PowerShell in lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="4ef78-124">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="4ef78-125">Zum Ausführen der lync Server-Cmdlets öffnen Sie die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="4ef78-125">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4ef78-126">Wenn Sie ein Windows PowerShell-Fenster anstelle der lync Server-Verwaltungsshell öffnen, können Sie die lync Server-Cmdlets standardmäßig nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="4ef78-126">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="4ef78-127">Wenn Sie die lync Server-Cmdlets in Windows PowerShell ausführen möchten, geben Sie zuerst Folgendes an der Windows PowerShell-Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="4ef78-127">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="4ef78-128">Import-Module lync</span><span class="sxs-lookup"><span data-stu-id="4ef78-128">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="4ef78-129">Die lync Server-Verwaltungsshell wird automatisch auf jedem lync Server Enterprise Edition-Front-End-Server oder Standard Edition-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="4ef78-129">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="4ef78-130">Neue und aktualisierte Informationen, Beispielskripts und Hilfe für erste Schritte und weitere Informationen zu Windows PowerShell-und Microsoft lync Server 2013-Cmdlets finden Sie im lync Server Windows PowerShell-Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150) .</span><span class="sxs-lookup"><span data-stu-id="4ef78-130">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

<span data-ttu-id="4ef78-131"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="4ef78-131"></div>

<span> </span>

</div>

</div>

</span></span></div>

