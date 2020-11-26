---
title: Voraussetzungen
description: Voraussetzungen.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 936e52961539ed57fe1b610d42fb1c9cf35589b0
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49446411"
---
# <a name="prerequisites"></a><span data-ttu-id="436df-103">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="436df-103">Prerequisites</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="436df-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="436df-104">

<span> </span></span></span>

<span data-ttu-id="436df-105">_**Letztes Änderungsdatum des Themas:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="436df-105">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="436df-106">Es gibt verschiedene Hardware-, Software-und Systemkonfigurations Anforderungen, die Sie zum Ausführen des lync Server 2013-Stress-und-Leistungstools benötigen.</span><span class="sxs-lookup"><span data-stu-id="436df-106">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="436df-107">Client Hardware Anforderungen</span><span class="sxs-lookup"><span data-stu-id="436df-107">Client Hardware Requirements</span></span>

<span data-ttu-id="436df-108">Zum Ausführen des lync Server 2013-Leistungs-und Leistungstools für die lync Server 2013-Bereitstellung benötigen Sie für jeden 4.500-Benutzer, dessen Auslastung Sie simulieren möchten, mindestens einen dedizierten Computer, der die folgenden minimalen Hardwareanforderungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="436df-108">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="436df-109">1 Gigabitnetzwerkadapter</span><span class="sxs-lookup"><span data-stu-id="436df-109">1 gigabit network adapter</span></span>

  - <span data-ttu-id="436df-110">8 GB Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="436df-110">8-GB ram</span></span>

  - <span data-ttu-id="436df-111">2 Dual-Core-Prozessoren (Central Processing Units, CPUs)</span><span class="sxs-lookup"><span data-stu-id="436df-111">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="436df-112">Client Software Anforderungen</span><span class="sxs-lookup"><span data-stu-id="436df-112">Client Software Requirements</span></span>

<span data-ttu-id="436df-113">Die unterstützten Betriebssysteme sind für das Ausführen des lync Server 2013-Stress-und-Leistungstools auf Ihrer lync Server 2013-Bereitstellung:</span><span class="sxs-lookup"><span data-stu-id="436df-113">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="436df-114">Betriebssystem Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="436df-114">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="436df-115">Windows Server 2008-Betriebssystem (64-Bit-Edition)</span><span class="sxs-lookup"><span data-stu-id="436df-115">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="436df-116">Ihr Clientcomputer muss die folgenden Softwareanforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="436df-116">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="436df-117">Sie müssen die [Microsoft .NET Framework 4,5](https://go.microsoft.com/fwlink/?linkid=143212) -Runtime installiert haben.</span><span class="sxs-lookup"><span data-stu-id="436df-117">You must have the [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="436df-118">Unter Windows Server 2008/Windows Server 2012 muss das Feature "Desktop Experience" aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="436df-118">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="436df-119">Sie müssen das [Microsoft Visual C++ 2012 Redistributable Package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installiert haben.</span><span class="sxs-lookup"><span data-stu-id="436df-119">You must have the [Microsoft Visual C++ 2012 redistributable package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="436df-120">Eine vollständig konfigurierte lync Server 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="436df-120">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="436df-121">Microsoft Unified Communications Managed API (UCMA) 4,0-Bibliotheken sind im Installationspaket enthalten, daher ist UCMA nicht erforderlich und sollte nicht auf Clientcomputern installiert werden.</span><span class="sxs-lookup"><span data-stu-id="436df-121">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="436df-122">Konfigurationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="436df-122">Configuration Requirements</span></span>

<span data-ttu-id="436df-123">Die Computer, auf denen das Stress-und Leistungs Tool lync Server 2013 ausgeführt wird, müssen entsprechend den folgenden Anforderungen konfiguriert sein:</span><span class="sxs-lookup"><span data-stu-id="436df-123">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="436df-124">Sie müssen als Mitglied der Gruppe "Domänen" oder "lokale Administratoren" angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="436df-124">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="436df-125">Das lync Server 2013-Stress-und-Leistungs Tool (LyncPerfTool.exe) kann nicht auf einem Computer ausgeführt werden, auf dem auch lync Server 2013-Komponenten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="436df-125">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="436df-126">Sie müssen das lync Server 2013-Benutzer Erstellungstool (UserProvisioningTool.exe) auf dem Front-End-Server oder auf dem Standard Edition-Server ausführen, auf dem sich die Benutzerkonten befinden.</span><span class="sxs-lookup"><span data-stu-id="436df-126">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="436df-127">Wenn das Tool mehrmals ausgeführt wird, muss jeder Benutzer, der für Microsoft Unified Communications aktiviert ist, über eine eindeutige Telefonnummer verfügen.</span><span class="sxs-lookup"><span data-stu-id="436df-127">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="436df-128">Die Größe der Auslagerungsdatei sollte vom System verwaltet werden, oder Sie sollte mindestens 1,5 mal so viel RAM auf dem System aufweisen.</span><span class="sxs-lookup"><span data-stu-id="436df-128">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

<span data-ttu-id="436df-129"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="436df-129"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

