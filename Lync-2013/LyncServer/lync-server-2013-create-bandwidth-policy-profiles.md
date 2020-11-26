---
title: 'Lync Server 2013: Erstellen von Bandbreitenrichtlinien Profilen'
description: 'Lync Server 2013: Erstellen von Bandbreitenrichtlinien Profilen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9646657c84806bff8caef3352774cdc5ddeab862
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431981"
---
# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="5f4eb-103">Erstellen von Bandbreitenrichtlinien Profilen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f4eb-103">Create bandwidth policy profiles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="5f4eb-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="5f4eb-104">

<span> </span></span></span>

<span data-ttu-id="5f4eb-105">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5f4eb-105">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5f4eb-p101">*Bandbreitenrichtlinien* definieren Einschränkungen zur Bandbreitenauslastung für in Echtzeit übertragene Audio- und Videodaten. Bandbreitenrichtlinien werden auf *Bandbreitenrichtlinienprofile* angewendet, die zur Anrufsteuerung auf mehrere Netzwerkstandorte angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-p101">*Bandwidth policies* define limitations on bandwidth usage for real-time audio and video modalities. Bandwidth policies are applied to *bandwidth policy profiles*, which can be applied to multiple network sites for call admission control.</span></span>

<span data-ttu-id="5f4eb-108">Richtlinien darüber, welche Bandbreitengrenzwerte in ihrer CAC-Bereitstellung festgelegt werden sollten, finden Sie unter [Definieren Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-108">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Defining your requirements for call admission control in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="5f4eb-109">Details zum Arbeiten mit Bandbreitenrichtlinien und Richtlinienprofilen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="5f4eb-109">For details about working with bandwidth policies and policy profiles, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="5f4eb-110">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="5f4eb-110">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="5f4eb-111">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="5f4eb-111">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="5f4eb-112">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="5f4eb-112">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="5f4eb-113">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="5f4eb-113">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

<span data-ttu-id="5f4eb-114">Die im folgenden Verfahren erstellten Beispielrichtlinien legen Einschränkungen für den Audiodatenverkehr insgesamt, einzelne Audiositzungen, den Videodatenverkehr insgesamt und einzelne Videositzungen fest.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-114">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="5f4eb-115">So legt das Profil mit dem 5MB- \_ Link-bandbreitenrichtlinienprofil die folgenden Grenzwerte fest:</span><span class="sxs-lookup"><span data-stu-id="5f4eb-115">For example, the 5Mb\_Link bandwidth policy profile sets the following limits:</span></span>

  - <span data-ttu-id="5f4eb-116">Grenzwert für Audio: 2.000 KBit/s</span><span class="sxs-lookup"><span data-stu-id="5f4eb-116">Audio Limit: 2,000 kbps</span></span>

  - <span data-ttu-id="5f4eb-117">Grenzwert für Audiositzung: 200 KBit/s</span><span class="sxs-lookup"><span data-stu-id="5f4eb-117">Audio Session Limit: 200 kbps</span></span>

  - <span data-ttu-id="5f4eb-118">Grenzwert für Video: 1.400 KBit/s</span><span class="sxs-lookup"><span data-stu-id="5f4eb-118">Video Limit: 1,400 kbps</span></span>

  - <span data-ttu-id="5f4eb-119">Grenzwert für Videositzung: 700 KBit/s</span><span class="sxs-lookup"><span data-stu-id="5f4eb-119">Video Session Limit: 700 kbps</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="5f4eb-p103">Der Mindestgrenzwert für Audiositzungen ist 40 KBit/s. Der Mindestgrenzwert für Videositzungen ist 100 KBit/s.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span>



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a><span data-ttu-id="5f4eb-122">So erstellen Sie bandbreitenrichtlinienprofile mithilfe der Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="5f4eb-122">To create bandwidth policy profiles by using Management Shell</span></span>

1.  <span data-ttu-id="5f4eb-123">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5f4eb-124">Führen Sie für jedes Bandbreitenrichtlinienprofil, das Sie erstellen möchten, das Cmdlet „New-CsNetworkBandwidthPolicyProfile“ aus.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-124">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="5f4eb-125">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="5f4eb-125">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a><span data-ttu-id="5f4eb-126">So erstellen Sie bandbreitenrichtlinienprofile mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="5f4eb-126">To create bandwidth policy profiles by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5f4eb-127">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-127">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5f4eb-128">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5f4eb-128">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="5f4eb-129">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-129">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="5f4eb-130">Klicken Sie auf die Navigationsschaltfläche **Richtlinienprofil**.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-130">Click the **Policy Profile** navigation button.</span></span>

4.  <span data-ttu-id="5f4eb-131">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-131">Click **New**.</span></span>

5.  <span data-ttu-id="5f4eb-132">Klicken Sie auf der Seite **Neues Richtlinienprofil** auf **Name** und geben Sie einen Namen für das Bandbreitenrichtlinienprofil ein.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-132">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>

6.  <span data-ttu-id="5f4eb-133">Klicken Sie auf **Audiolimit** und geben Sie die Höchstzahl an KBit/s ein, die für alle Audiositzungen insgesamt zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-133">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>

7.  <span data-ttu-id="5f4eb-134">Klicken Sie auf **Grenzwert für Audiositzung** und geben Sie die Höchstzahl an KBit/s ein, die für jede einzelne Audiositzung zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-134">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>

8.  <span data-ttu-id="5f4eb-135">Klicken Sie auf **Videolimit** und geben Sie die Höchstzahl an KBit/s ein, die für alle Videositzungen insgesamt zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-135">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>

9.  <span data-ttu-id="5f4eb-136">Klicken Sie auf **Grenzwert für Videositzung** und geben Sie die Höchstzahl an KBit/s ein, die für jede einzelne Videositzung zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-136">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>

10. <span data-ttu-id="5f4eb-137">Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Bandbreitenrichtlinienprofils ein.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-137">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>

11. <span data-ttu-id="5f4eb-138">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-138">Click **Commit**.</span></span>

12. <span data-ttu-id="5f4eb-139">Wiederholen Sie die Schritte 4 bis 11 mit Einstellungen für andere Bandbreitenrichtlinienprofile, um die Erstellung von Bandbreitenrichtlinienprofilen für Ihre Topologie abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5f4eb-139">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>

<span data-ttu-id="5f4eb-140"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="5f4eb-140"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

