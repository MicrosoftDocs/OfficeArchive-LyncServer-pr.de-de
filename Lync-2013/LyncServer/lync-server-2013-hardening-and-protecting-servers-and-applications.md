---
title: 'Lync Server 2013: Sichern und Schützen von Servern und Anwendungen'
description: 'Lync Server 2013: Härten und schützen von Servern und Anwendungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed1205439208dfdadf5396b976d5d4876fb0aa24
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427754"
---
# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="bd521-103">Sichern und Schützen von Servern und Anwendungen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd521-103">Hardening and protecting servers and applications for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="bd521-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="bd521-104">

<span> </span></span></span>

<span data-ttu-id="bd521-105">_**Letztes Änderungsdatum des Themas:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="bd521-105">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="bd521-106">Sie sollten Ihr Betriebssystem und ihre Anwendungen entsprechend den bewährten Methoden für diese bestimmte Komponente verhärten und schützen.</span><span class="sxs-lookup"><span data-stu-id="bd521-106">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="bd521-107">In diesem Abschnitt wird beschrieben, wie Anwendungsserver gehärtet und Gruppenrichtlinien zum Implementieren von Sicherheits Sperrungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd521-107">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd521-108">Sie können auch die Datenbanken verhärten und schützen, die für die Bereitstellung von Microsoft lync Server 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd521-108">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="bd521-109">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hardening-and-protecting-databases.md">Härten und schützen der Datenbanken von lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bd521-109">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="bd521-110">Sichern von Anwendungsservern</span><span class="sxs-lookup"><span data-stu-id="bd521-110">Securing Application Servers</span></span>

<span data-ttu-id="bd521-111">Bei Anwendungsservern sollten das Betriebssystem und die Anwendung gehärtet werden.</span><span class="sxs-lookup"><span data-stu-id="bd521-111">For applications servers, the operating system and the application should be hardened.</span></span> <span data-ttu-id="bd521-112">Beispielsweise sollte ein Windows Server 2008-Computer, der für die Ausführung von Microsoft Internet Security and Acceleration (ISA) Server 2006 dediziert ist, aus dem Betriebssystem und aus der Anwendungsperspektive gehärtet werden.</span><span class="sxs-lookup"><span data-stu-id="bd521-112">For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective.</span></span> <span data-ttu-id="bd521-113">Das Minimieren der Anzahl der Dienste, die vom Server ausgeführt und bereitgestellt werden, sollte ein Hauptziel sein.</span><span class="sxs-lookup"><span data-stu-id="bd521-113">Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="bd521-114">Sichern von virtuellen Servern</span><span class="sxs-lookup"><span data-stu-id="bd521-114">Securing Virtual Servers</span></span>

<span data-ttu-id="bd521-115">Snapshots virtueller Server enthalten Kopien der Datenlaufwerke des Servers und enthalten auch Speicherabbilder von Daten im Arbeitsspeicher, die beide vertrauliche kryptografische Daten enthalten können, die zu Angriffen führen können.</span><span class="sxs-lookup"><span data-stu-id="bd521-115">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="bd521-116">Bei Produktionsservern, die mithilfe von Virtualisierung implementiert werden, sollten Sie alle Server-Snapshots deaktivieren oder auf sehr kontrollierte Weise verwalten.</span><span class="sxs-lookup"><span data-stu-id="bd521-116">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="bd521-117">Details zum Sichern von virtuellen Hyper-v-Servern finden Sie im Hyper-v-Sicherheitshandbuch unter: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176) .</span><span class="sxs-lookup"><span data-stu-id="bd521-117">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="bd521-118">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="bd521-118">Group Policy</span></span>

<span data-ttu-id="bd521-119">In Windows Server 2008 und Windows Server 2008 R2 bietet die Gruppenrichtlinie die verzeichnisbasierte Verwaltung der Desktopkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="bd521-119">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management.</span></span> <span data-ttu-id="bd521-120">Sie können Gruppenrichtlinien zum Implementieren von Sicherheits Sperrungen verwenden, indem Sie für die folgenden Computer-und Benutzereinstellungen in einem Gruppenrichtlinienobjekt definieren:</span><span class="sxs-lookup"><span data-stu-id="bd521-120">You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="bd521-121">Registrierungsbasierte Richtlinien</span><span class="sxs-lookup"><span data-stu-id="bd521-121">Registry-based policies</span></span>

  - <span data-ttu-id="bd521-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="bd521-122">Security</span></span>

  - <span data-ttu-id="bd521-123">Software Installation</span><span class="sxs-lookup"><span data-stu-id="bd521-123">Software installation</span></span>

  - <span data-ttu-id="bd521-124">Skripts</span><span class="sxs-lookup"><span data-stu-id="bd521-124">Scripts</span></span>

  - <span data-ttu-id="bd521-125">Ordnerumleitung</span><span class="sxs-lookup"><span data-stu-id="bd521-125">Folder redirection</span></span>

  - <span data-ttu-id="bd521-126">Remoteinstallationsdienste</span><span class="sxs-lookup"><span data-stu-id="bd521-126">Remote installation services</span></span>

<span data-ttu-id="bd521-127">Zum Bereitstelleneiner Benutzeroberfläche für den Administrator zum Konfigurieren dieser Einstellungen werden administrative Vorlagen mit Betriebssystemversionen, Service Pack-Versionen und einigen Anwendungen, einschließlich lync Server 2013, ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="bd521-127">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="bd521-128">Die Datei "Communicator. adm" ist eine administrative Vorlage, die mit lync Server 2013 ausgeliefert wird, im Verzeichnis% windir% inf installiert ist \\ \\ und eine Schnittstelle zu den Gruppenrichtlinieneinstellungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="bd521-128">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="bd521-129">Jede Einstellung in Communicator. adm entspricht einer Einstellung in der Registrierung, die sich auf das Anwendungsverhalten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="bd521-129">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="bd521-130">Auf die Einstellungen kann über GPedit.dll zugegriffen werden, die über die Konsole "Active Directory-Benutzer und-Computer" und die Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC) zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="bd521-130">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="bd521-131">Sicherheitseinstellungen für Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="bd521-131">Group Policy Security Settings</span></span>

<span data-ttu-id="bd521-132">Gruppenrichtlinien enthalten Sicherheitseinstellungen für ein GPO unter Computer Konfiguration/Windows-Einstellungen/Sicherheitseinstellungen, wenn von GPedit.dll aus darauf zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="bd521-132">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="bd521-133">Sie können Sicherheitsvorlagen importieren, um Sicherheitseinstellungen für das Gruppenrichtlinienobjekt zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bd521-133">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="bd521-134">Im Windows Server 2008-Sicherheitshandbuch [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) und im Windows Server 2008 R2 Security Compliance Management Toolkit [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) finden Sie eine Reihe von Beispielvorlagen, die Sie Ihren Anforderungen entsprechend ändern können.</span><span class="sxs-lookup"><span data-stu-id="bd521-134">The Windows Server 2008 Security Guide at [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="bd521-135">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="bd521-135">Best Practices</span></span>

  - <span data-ttu-id="bd521-136">Härten Sie alle Server Betriebssysteme und-Anwendungen aus.</span><span class="sxs-lookup"><span data-stu-id="bd521-136">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="bd521-137">Schützen Sie Server-Snapshots, und verbessern Sie die Sicherheit aller virtuellen Server.</span><span class="sxs-lookup"><span data-stu-id="bd521-137">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="bd521-138">Verwenden Sie Gruppenrichtlinien, um Sicherheits Sperrungen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="bd521-138">Use Group Policy to implement security lockdowns.</span></span>

<span data-ttu-id="bd521-139"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="bd521-139"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

