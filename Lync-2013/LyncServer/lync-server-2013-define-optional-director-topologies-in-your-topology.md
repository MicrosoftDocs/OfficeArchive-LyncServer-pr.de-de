---
title: 'Lync Server 2013: Definieren von optionalen Director-Topologien in einer Topologie'
description: 'Lync Server 2013: definieren Optionaler Director-Topologien in Ihrer Topologie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bc82108d4277969489739fc81db07ec6f96bb96
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431050"
---
# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="89074-103">Definieren von optionalen Director-Topologien in einer Topologie für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89074-103">Define optional Director topologies in your topology for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="89074-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="89074-104">

<span> </span></span></span>

<span data-ttu-id="89074-105">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="89074-105">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="89074-106">Die lync Server 2013-Directors können Single-Instance-Server sein oder als Lastenausgleichspool mehrerer Directors installiert werden, um höhere Verfügbarkeit und Kapazität zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="89074-106">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="89074-107">Sowohl der Hardwarelastenausgleich als auch der DNS-Lastenausgleich (Domain Name System) werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="89074-107">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="89074-108">In diesem Thema wird erläutert, wie Sie den DNS-Lastenausgleich für Director-Pools konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="89074-108">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="89074-109">Um eine Topologie erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, wenn Sie eine Serverrolle hinzufügen oder entfernen, sollten Sie als Benutzer angemeldet sein, der Mitglied der Gruppen **RTCUniversalServerAdmins** und **Domänenadministratoren** ist.</span><span class="sxs-lookup"><span data-stu-id="89074-109">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="89074-110">Sie können auch die richtigen Administratorrechte und-Berechtigungen für das Hinzufügen von Serverrollen delegieren.</span><span class="sxs-lookup"><span data-stu-id="89074-110">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="89074-111">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Dokumentation zur Standard Edition-Server-oder Enterprise Edition-Server Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="89074-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="89074-112">Bei anderen Konfigurationsänderungen ist nur die Mitgliedschaft in der **RTCUniversalServerAdmins** -Gruppe erforderlich.</span><span class="sxs-lookup"><span data-stu-id="89074-112">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="89074-113">In diesem Thema werden die Schritte zum Definieren und Veröffentlichen der Topologie für die beiden Director-Topologien beschrieben:</span><span class="sxs-lookup"><span data-stu-id="89074-113">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="89074-114">So definieren Sie den Director (einzelne Instanz)</span><span class="sxs-lookup"><span data-stu-id="89074-114">To define the Director (single instance)</span></span>

  - <span data-ttu-id="89074-115">So definieren Sie den Director (mehrere Director-Pools)</span><span class="sxs-lookup"><span data-stu-id="89074-115">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="89074-116">So definieren Sie den Director (einzelne Instanz)</span><span class="sxs-lookup"><span data-stu-id="89074-116">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="89074-117">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="89074-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="89074-118">Klicken Sie auf der Seite Willkommen auf **Topologie aus vorhandener Bereitstellung herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="89074-118">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="89074-119">Geben Sie im Dialogfeld **Topologie speichern** unter den Namen und den Speicherort der lokalen Kopie der vorhandenen Topologie ein, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="89074-119">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="89074-120">Erweitern Sie die Website, auf der Sie den Director hinzufügen möchten, klicken Sie mit der rechten Maustaste auf **Director-Pools**, und klicken Sie dann auf **Neuer Director-Pool**.</span><span class="sxs-lookup"><span data-stu-id="89074-120">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="89074-121">Gehen Sie im Dialogfeld **Director-Pool-FQDN definieren** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="89074-121">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="89074-122">Geben Sie in **Pool FQDN** den FQDN für den Director-Pool ein.</span><span class="sxs-lookup"><span data-stu-id="89074-122">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="89074-123">Klicken Sie auf **Einzelcomputer Pool**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="89074-123">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="89074-124">Führen Sie im Dialogfeld **Dateifreigabe definieren** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="89074-124">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="89074-125">Wenn Sie eine vorhandene Dateifreigabe verwenden möchten, klicken Sie auf **zuvor definierte Dateifreigabe verwenden**, wählen Sie eine Dateifreigabe aus der Liste aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="89074-125">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="89074-126">Wenn Sie eine neue Dateifreigabe erstellen möchten, klicken Sie auf **neue Dateifreigabe definieren**, geben Sie den FQDN für den Speicherort der Dateifreigabe unter **Datei Server-FQDN** ein, geben Sie den Namen der Freigabe in **Dateifreigabe** ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="89074-126">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="89074-127">Die Dateifreigabe, die Sie in diesem Schritt angeben oder erstellen, muss vor dem Veröffentlichen der Topologie vorhanden sein oder erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="89074-127">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="89074-128">Die einem Director zugewiesene Dateifreigabe wird nicht tatsächlich verwendet, sodass Sie die Dateifreigabe eines beliebigen Pools in der Organisation zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="89074-128">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="89074-129">Geben Sie im Dialogfeld **URL für Webdienste angeben** in **externe Basis-URL** den FQDN für die Directors an, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="89074-129">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="89074-130">Der Name muss von Internet-DNS-Servern aufgelöst werden und auf die öffentliche IP-Adresse des Reverse-Proxys verweisen, der auf HTTP/HTTPS-Anforderungen an diese URL wartet und diese an das virtuelle Verzeichnis externer Webdienste in diesem Director abgibt.</span><span class="sxs-lookup"><span data-stu-id="89074-130">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="89074-131">Wenn Sie über mehr als einen Front-End-Pool oder Front-End-Server verfügen, muss der FQDN der externen Webdienste eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="89074-131">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="89074-132">Wenn Sie beispielsweise den FQDN eines externen Webdiensts eines Front-End-Servers als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="89074-132">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="89074-133">Wenn Sie Directors auch bereitstellen, müssen die für Director-oder Director-Pools definierten externen Webdienst-FQDN für jeden anderen Director-oder Director-Pool sowie für jeden Front-End-Pool oder Front-End-Server eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="89074-133">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="89074-134">Wenn Sie beschließen, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="89074-134">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="89074-135">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="89074-135">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="89074-136">So definieren Sie den Director (mehrere Director-Pools)</span><span class="sxs-lookup"><span data-stu-id="89074-136">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="89074-137">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="89074-137">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="89074-138">Klicken Sie auf der Seite Willkommen auf **Topologie aus vorhandener Bereitstellung herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="89074-138">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="89074-139">Geben Sie im Dialogfeld **Topologie speichern** unter den Namen und den Speicherort der lokalen Kopie der vorhandenen Topologie ein, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="89074-139">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="89074-140">Erweitern Sie die Website, auf der Sie den Director hinzufügen möchten, klicken Sie mit der rechten Maustaste auf **Director-Pools**, und klicken Sie dann auf **Neuer Director-Pool**.</span><span class="sxs-lookup"><span data-stu-id="89074-140">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="89074-141">Gehen Sie im Dialogfeld **Director-Pool-FQDN definieren** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="89074-141">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="89074-142">Geben Sie in **Pool FQDN** den FQDN für den Director-Pool ein.</span><span class="sxs-lookup"><span data-stu-id="89074-142">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="89074-143">Klicken Sie auf **Pool mit mehreren Computern**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="89074-143">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="89074-144">Gehen Sie im Dialogfeld **Computer in diesem Pool definieren** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="89074-144">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="89074-145">Geben Sie den Computer-FQDN des ersten Pool Mitglieds an, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="89074-145">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="89074-146">Wiederholen Sie den vorherigen Schritt für jeden Computer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="89074-146">Repeat the previous step for each computer that you want to add.</span></span> <span data-ttu-id="89074-147">Wenn Sie den Vorgang beenden, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="89074-147">When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="89074-148">Führen Sie im Dialogfeld **Dateifreigabe definieren** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="89074-148">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="89074-149">Wenn Sie eine vorhandene Dateifreigabe verwenden möchten, klicken Sie auf **zuvor definierte Dateifreigabe verwenden**, wählen Sie eine Dateifreigabe aus der Liste aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="89074-149">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="89074-150">Wenn Sie eine neue Dateifreigabe erstellen möchten, klicken Sie auf **neue Dateifreigabe definieren**, geben Sie den FQDN für den Speicherort der Dateifreigabe unter **Datei Server-FQDN** ein, geben Sie den Namen der Freigabe in **Dateifreigabe** ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="89074-150">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="89074-151">Die Dateifreigabe, die Sie in diesem Schritt angeben oder erstellen, muss vor dem Veröffentlichen der Topologie vorhanden sein oder erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="89074-151">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="89074-152">Die einem Director zugewiesene Dateifreigabe wird nicht tatsächlich verwendet, sodass Sie die Dateifreigabe eines beliebigen Pools in der Organisation zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="89074-152">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="89074-153">Geben Sie im Dialogfeld **URL für Webdienste angeben** in **externe Basis-URL** den FQDN für die Directors an, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="89074-153">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="89074-154">Der Name muss von Internet-DNS-Servern aufgelöst werden und auf die öffentliche IP-Adresse des Reverse-Proxys verweisen, der auf HTTP/HTTPS-Anforderungen wartet, die an diese URL gesendet werden, und Sie an das virtuelle Verzeichnis externer Webdienste in diesem Director-Pool weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="89074-154">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="89074-155">Wenn Sie über mehr als einen Front-End-Pool oder Front-End-Server verfügen, muss der FQDN der externen Webdienste eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="89074-155">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="89074-156">Wenn Sie beispielsweise den FQDN eines externen Webdiensts eines Front-End-Servers als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="89074-156">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="89074-157">Wenn Sie Directors auch bereitstellen, müssen die für Director-oder Director-Pools definierten externen Webdienst-FQDN für jeden anderen Director-oder Director-Pool sowie für jeden Front-End-Pool oder Front-End-Server eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="89074-157">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="89074-158">Wenn Sie beschließen, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="89074-158">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="89074-159">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="89074-159">Publish the topology.</span></span>

<span data-ttu-id="89074-160"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="89074-160"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

