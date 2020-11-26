---
title: 'Lync Server 2013: Installieren des Planungstools'
description: 'Lync Server 2013: Installieren des Planungstools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11836e2c86cb01d6f911670a9eeafef0c31c0af4
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49426907"
---
# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="535a6-103">Installieren des Planungstools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="535a6-103">Installing the Planning Tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="535a6-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="535a6-104">

<span> </span></span></span>

<span data-ttu-id="535a6-105">_**Letztes Änderungsdatum des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="535a6-105">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="535a6-106">Bevor Sie mit dem Entwerfen und Planen Ihrer lync Server 2013-Infrastruktur mit dem Microsoft lync Server 2013, Planungstool beginnen, müssen Sie zuerst das Planungstool installieren.</span><span class="sxs-lookup"><span data-stu-id="535a6-106">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="535a6-107">Das Planungs Tool muss nicht auf einer Workstation oder einem Server bereitgestellt werden, die Teil der Domäne oder Infrastruktur ist, in der Sie lync Server 2013 installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="535a6-107">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="535a6-108">In der Readme-Datei, die dem Planungs Tool beigefügt ist, finden Sie wichtige Informationen zum Installieren und Verwenden des Tools.</span><span class="sxs-lookup"><span data-stu-id="535a6-108">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="535a6-109">Einige Informationen aus dieser Datei werden zur Verdeutlichung im Folgenden noch einmal aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="535a6-109">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="535a6-110">Das Planungs Tool erfordert die Installation durch einen Benutzer mit Administratorrechten und-Berechtigungen auf dem Computer, auf dem das Tool installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="535a6-110">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="535a6-111">Die unterstützten Betriebssysteme für die Installation und den Betrieb des Planungstools sind:</span><span class="sxs-lookup"><span data-stu-id="535a6-111">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="535a6-112">Windows 8</span><span class="sxs-lookup"><span data-stu-id="535a6-112">Windows 8</span></span>

  - <span data-ttu-id="535a6-113">Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="535a6-113">Windows 8.1</span></span>

  - <span data-ttu-id="535a6-114">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="535a6-114">Windows Server 2012</span></span>

  - <span data-ttu-id="535a6-115">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="535a6-115">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="535a6-116">Windows 7, 32-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="535a6-116">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="535a6-117">Windows 7, 64-Bit-Version unter Verwendung von Windows on Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="535a6-117">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="535a6-118">Windows Server 2008 R2 unter Verwendung von WOW</span><span class="sxs-lookup"><span data-stu-id="535a6-118">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="535a6-119">Darüber hinaus erfordert das Planungs Tool Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="535a6-119">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="535a6-120">Nachdem die Voraussetzungen für die Vorinstallation erfüllt sind, können Sie das Planungs Tool installieren.</span><span class="sxs-lookup"><span data-stu-id="535a6-120">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="535a6-121">So installieren Sie das Planungstool</span><span class="sxs-lookup"><span data-stu-id="535a6-121">To install the Planning Tool</span></span>

1.  <span data-ttu-id="535a6-122">Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.</span><span class="sxs-lookup"><span data-stu-id="535a6-122">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="535a6-123">Suchen Sie im Windows-Explorer oder einem Befehlsfenster nach dem Verzeichnis, in dem Sie die Installationsdateien des Planungstools heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="535a6-123">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="535a6-124">Suchen Sie den LyncPlanningTool.msi.</span><span class="sxs-lookup"><span data-stu-id="535a6-124">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="535a6-125">Machen Sie im Windows Explorer einen Doppelklick auf die Datei.</span><span class="sxs-lookup"><span data-stu-id="535a6-125">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="535a6-126">Geben Sie im Befehlsfenster den Namen der Datei ein und drücken Sie die **Eingabetaste**, um die Datei auszuführen.</span><span class="sxs-lookup"><span data-stu-id="535a6-126">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="535a6-127">Klicken Sie auf der Willkommensseite des **Microsoft lync Server 2013-Setup-Assistenten für Planungstools** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="535a6-127">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="535a6-128">Lesen Sie den **Endbenutzer-Lizenzvertrag**, wählen Sie die Option **Ich stimme den Bedingungen des Lizenzvertrags zu** aus, sofern Sie die Bedingungen akzeptieren, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="535a6-128">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="535a6-129">Geben Sie an, in welchem Verzeichnis die Dateien des Planungstools installiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="535a6-129">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="535a6-130">Der Standardspeicherort ist C: \\ Programmdateien (x86) \\ Microsoft lync Server 2013- \\ Planungs Tool.</span><span class="sxs-lookup"><span data-stu-id="535a6-130">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="535a6-131">Wenn Sie ein anderes Installationsverzeichnis auswählen möchten, klicken Sie auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="535a6-131">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="535a6-132">Navigieren Sie im Dialogfeld **Zielordner ändern** zum gewünschten Verzeichnis oder geben Sie ein Verzeichnis ein und klicken Sie nacheinander auf **OK** und auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="535a6-132">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="535a6-133">Das Installationsprogramm ist nun bereit, das Planungs Tool zu installieren.</span><span class="sxs-lookup"><span data-stu-id="535a6-133">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="535a6-134">Klicken Sie auf **Installieren**, um den Installationsvorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="535a6-134">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="535a6-135">Die Installation beginnt und der Installationsfortschritt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="535a6-135">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="535a6-136">Klicken Sie nach Abschluss der Installation auf **Fertigstellen**.</span><span class="sxs-lookup"><span data-stu-id="535a6-136">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="535a6-137">Das Planungs Tool ist einsatzbereit.</span><span class="sxs-lookup"><span data-stu-id="535a6-137">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="535a6-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="535a6-138">See Also</span></span>


[<span data-ttu-id="535a6-139">Installieren von optionaler Software in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="535a6-139">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

<span data-ttu-id="535a6-140"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="535a6-140"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

