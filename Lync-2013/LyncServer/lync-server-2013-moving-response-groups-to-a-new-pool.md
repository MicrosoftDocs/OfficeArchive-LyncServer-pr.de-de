---
title: 'Lync Server 2013: Verschieben von Reaktionsgruppen in einen neuen Pool'
description: 'Lync Server 2013: Verschieben von Reaktionsgruppen in einen neuen Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b696963a28abbcd258f53fae12c3e281efa6ae4d
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425264"
---
# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="755a9-103">Verschieben von Reaktionsgruppen in einen neuen Pool in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="755a9-103">Moving response groups to a new pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="755a9-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="755a9-104">

<span> </span></span></span>

<span data-ttu-id="755a9-105">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="755a9-105">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="755a9-106">Lync Server 2013 führt eine neue Cmdlet-Unterstützung für das Verschieben von Reaktionsgruppen aus einem Pool in einen anderen Pool ein, selbst wenn der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) anders ist.</span><span class="sxs-lookup"><span data-stu-id="755a9-106">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="755a9-107">Führen Sie die Schritte in der folgenden Vorgehensweise aus, um Reaktionsgruppen aus einem Front-End-Pool in einen anderen Front-End-Pool mit einem anderen FQDN zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="755a9-107">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="755a9-108">In einer Koexistenz-Umgebung können Sie Reaktionsgruppen nur zwischen lync Server 2013 &nbsp; -Front-End-Pools verschieben.</span><span class="sxs-lookup"><span data-stu-id="755a9-108">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="755a9-109">So verschieben Sie Antwortgruppen in einen Pool mit einem anderen FQDN</span><span class="sxs-lookup"><span data-stu-id="755a9-109">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="755a9-110">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="755a9-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="755a9-111">Exportieren Sie die Antwortgruppen im Quell Pool.</span><span class="sxs-lookup"><span data-stu-id="755a9-111">Export the response groups in the source pool.</span></span> <span data-ttu-id="755a9-112">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="755a9-112">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="755a9-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="755a9-113">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="755a9-114">Wenn Sie die Antwortgruppen aus dem Quell Pool während des Exports entfernen möchten, schließen Sie den Parameter – RemoveExportedConfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="755a9-114">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter.</span></span> <span data-ttu-id="755a9-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="755a9-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="755a9-116">Importieren Sie die Antwortgruppen in den Ziel Pool, und weisen Sie den Ziel Pool als neuen Besitzer zu.</span><span class="sxs-lookup"><span data-stu-id="755a9-116">Import the response groups to the destination pool and assign the destination pool as the new owner.</span></span> <span data-ttu-id="755a9-117">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="755a9-117">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="755a9-118">Wenn Sie auch die Einstellungen für die Reaktionsgruppe auf Anwendungsebene aus dem Quell Pool in den Ziel Pool kopieren möchten, schließen Sie den Parameter – ReplaceExistingRgsSettings ein.</span><span class="sxs-lookup"><span data-stu-id="755a9-118">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="755a9-119">Pro Pool können Sie nur eine Gruppe von Einstellungen auf Anwendungsebene definieren.</span><span class="sxs-lookup"><span data-stu-id="755a9-119">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="755a9-120">Wenn Sie die Einstellungen auf Anwendungsebene aus dem Quell Pool in den Ziel Pool kopieren, ersetzen die Einstellungen des Quell Pools die Einstellungen für den Ziel Pool.</span><span class="sxs-lookup"><span data-stu-id="755a9-120">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="755a9-121">Wenn Sie die Einstellungen auf Anwendungsebene nicht aus dem Quell Pool kopieren, gelten die vorhandenen Einstellungen aus dem Ziel Pool für die importierten Antwortgruppen.</span><span class="sxs-lookup"><span data-stu-id="755a9-121">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="755a9-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="755a9-122">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="755a9-123">Zu den Einstellungen auf Anwendungsebene gehören die standardmäßige Musik-in-situ-Konfiguration, die standardmäßige Musik-in-halten-Audiodatei, die Kulanzzeit für den Agenten-Rückruf und die Kontextkonfiguration des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="755a9-123">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="755a9-124">Führen Sie das Cmdlet " <STRONG>Get-CsRgsConfiguration</STRONG> " aus, um diese Konfigurationseinstellungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="755a9-124">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="755a9-125">Details zu diesem Cmdlet finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="755a9-125">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="755a9-126">Überprüfen Sie, ob der Import erfolgreich war, indem Sie die Konfiguration der importierten Reaktionsgruppe wie folgt anzeigen:</span><span class="sxs-lookup"><span data-stu-id="755a9-126">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="755a9-127">Überprüfen Sie, ob alle Workflows importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="755a9-127">Verify that all the workflows were imported.</span></span> <span data-ttu-id="755a9-128">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="755a9-128">At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="755a9-129">Überprüfen Sie, ob alle Warteschlangen importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="755a9-129">Verify that all the queues were imported.</span></span> <span data-ttu-id="755a9-130">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="755a9-130">At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="755a9-131">Überprüfen Sie, ob alle Agentengruppen importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="755a9-131">Verify that all the agent groups were imported.</span></span> <span data-ttu-id="755a9-132">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="755a9-132">At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="755a9-133">Überprüfen Sie, ob alle Geschäftszeiten importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="755a9-133">Verify that all the hours of business were imported.</span></span> <span data-ttu-id="755a9-134">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="755a9-134">At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="755a9-135">Überprüfen Sie, ob alle Feiertagssätze importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="755a9-135">Verify that all the holiday sets were imported.</span></span> <span data-ttu-id="755a9-136">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="755a9-136">At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="755a9-137">Überprüfen Sie, ob der Import erfolgreich war, indem Sie eine der Antwortgruppen anrufen und überprüfen, ob der Anruf richtig gehandhabt wurde.</span><span class="sxs-lookup"><span data-stu-id="755a9-137">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="755a9-138">Anfordern von Agents, die Mitglieder von formellen Agentengruppen sind, um sich bei ihren Agentengruppen im Ziel Pool anzumeldet.</span><span class="sxs-lookup"><span data-stu-id="755a9-138">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="755a9-139">Wenn Sie die Antwortgruppen zuvor nicht aus dem Quell Pool entfernt haben, entfernen Sie die Antwortgruppen aus dem Quell Pool.</span><span class="sxs-lookup"><span data-stu-id="755a9-139">If you did not previously remove response groups from the source pool, remove the response groups from the source pool.</span></span> <span data-ttu-id="755a9-140">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="755a9-140">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="755a9-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="755a9-141">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

<span data-ttu-id="755a9-142"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="755a9-142"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

