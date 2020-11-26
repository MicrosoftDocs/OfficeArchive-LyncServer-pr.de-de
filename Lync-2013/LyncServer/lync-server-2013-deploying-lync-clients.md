---
title: 'Lync Server 2013: Bereitstellen von lync-Clients'
description: 'Lync Server 2013: Bereitstellen von lync-Clients.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09b501fc721ac880c5cf7da0293e3aa9c6443722
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49429986"
---
# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="c8ac4-103">Bereitstellen von lync-Clients in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8ac4-103">Deploying Lync clients in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="c8ac4-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="c8ac4-104">

<span> </span></span></span>

<span data-ttu-id="c8ac4-105">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c8ac4-105">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c8ac4-106">Lync 2013 führt einen anderen Ansatz für die Clientbereitstellung ein.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-106">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="c8ac4-107">In einer Abweichung von vorherigen Versionen verfügt lync 2013 nicht mehr über ein eigenes Installationsprogramm.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-107">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="c8ac4-108">Stattdessen ist lync im Office 2013-Setupprogramm enthalten.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-108">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="c8ac4-109">Wenn Sie lync 2013 für Ihre Benutzer bereitstellen möchten, können Sie die Office 2013-Installationsmethoden und Anpassungstools verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-109">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="c8ac4-110">**Office 2013 Windows Installer** ist ein Windows Installer-basiertes Installationspaket, das aus mehreren MSI-Dateien besteht.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-110">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="c8ac4-111">Ein MSI-Paket mit sprachneutralem Kern wird mit einem oder mehreren sprachenspezifischen Paketen zu einem vollständigen Produkt kombiniert.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-111">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="c8ac4-112">Setup fügt die einzelnen Pakete zusammen und führt während und nach der Installation von Office auf den Computern der Benutzer Anpassungs- und Wartungsaufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-112">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="c8ac4-113">In den Themen in diesem Abschnitt wird beschrieben, wie Sie das Office 2013 Windows Installer zum Bereitstellen von lync 2013 verwenden und anpassen.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-113">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="c8ac4-114">**Office 2013 Klick-und-Los** ist ein Installationsprogramm, das die Office-Setupdateien aus dem Microsoft 365 Admin Center an den Benutzer streamt.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-114">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft 365 admin center.</span></span> <span data-ttu-id="c8ac4-115">Administratoren können die Installation mithilfe des Office-Bereitstellungstools für Klick-und-Los maßschneidern.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-115">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="c8ac4-116">Da Office 2013 Klick-und-Los in erster Linie in der Microsoft 365-Umgebung verwendet wird, wird diese Installationsmethode nicht ausführlich in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-116">Because Office 2013 Click-to-Run is primarily used in the Microsoft 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="c8ac4-117">Detaillierte Informationen zur Verwendung und Anpassung der Klick-und-Los-Installation finden Sie in der Dokumentation zum Office 2013 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-117">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="c8ac4-118">Administratoren können auch das Office 2013-Klick-und-Los-Programm und die sprach Quelldateien in einen lokalen Speicherort herunterladen, was nützlich ist, wenn Sie die Netzwerk Nachfrage minimieren oder verhindern möchten, dass Benutzer Software aus dem Internet installieren, weil Sie die Sicherheitsanforderungen der Unternehmen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-118">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="c8ac4-119">Die Themen in diesem Abschnitt konzentrieren sich auf die Bereitstellung von Clients mithilfe des MSI-basierten Installationsprogramms von Office 2013.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-119">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="c8ac4-120">Ihr primärer Bezug sollte die Office 2013 Resource Kit-Dokumentation sein, in der ausführlich beschrieben wird, wie Sie Ihre Infrastruktur vorbereiten, Setup anpassen und Office 2013 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-120">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="c8ac4-121">Sie sollten die Office-Dokumentation jedoch in Verbindung mit den Themen in diesem Abschnitt verwenden, die auf Bereitstellungsüberlegungen verweisen, die für lync 2013 spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-121">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="c8ac4-122">Das Online Besprechungs-Add-in für lync 2013, das die Besprechungsverwaltung innerhalb des Outlook-Messaging-und Zusammenarbeits Clients unterstützt, wird automatisch mit lync 2013 installiert.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-122">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="c8ac4-123">Das Office 2013-Setupprogramm deinstalliert keine früheren Versionen von lync oder Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="c8ac4-123">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="c8ac4-124">Der lync 2013-Client wird nebeneinander mit anderen lync-oder Office Communicator-Clients installiert</span><span class="sxs-lookup"><span data-stu-id="c8ac4-124">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c8ac4-125">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c8ac4-125">In This Section</span></span>

  - [<span data-ttu-id="c8ac4-126">Anpassen der Clientinstallation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8ac4-126">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="c8ac4-127">Anpassen des lync-Verhaltens und der Benutzeroberfläche in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8ac4-127">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="c8ac4-128">Anpassen des Online Besprechungs-Add-Ins in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8ac4-128">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="c8ac4-129">Konfigurieren der Seite für den Besprechungsbeitritt in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8ac4-129">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="c8ac4-130">Konfigurieren von unterstützten Clientversionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8ac4-130">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="c8ac4-131">Konfigurieren des erweiterten Anwesenheitsdaten Schutzmodus in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8ac4-131">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

<span data-ttu-id="c8ac4-132"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="c8ac4-132"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

