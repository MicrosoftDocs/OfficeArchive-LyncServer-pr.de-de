---
title: 'Lync Server 2013: Überwachen des Betriebssystems'
description: 'Lync Server 2013: Überwachen des Betriebssystems.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9454b91a5f55467f93b41752686b4b0d727d935
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425325"
---
# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="36b88-103">Überwachen des Betriebssystems in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36b88-103">Monitoring operating system in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="36b88-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="36b88-104">

<span> </span></span></span>

<span data-ttu-id="36b88-105">_**Letztes Änderungsdatum des Themas:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="36b88-105">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="36b88-106">Sie müssen die Leistung aller Server und Komponenten in lync Server 2013 überwachen.</span><span class="sxs-lookup"><span data-stu-id="36b88-106">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="36b88-107">Eine der wichtigsten Komponenten ist natürlich das Betriebssystem selbst.</span><span class="sxs-lookup"><span data-stu-id="36b88-107">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="36b88-108">Lync Server 2013 unterstützt x64-Editionen von:</span><span class="sxs-lookup"><span data-stu-id="36b88-108">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="36b88-109">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="36b88-109">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="36b88-110">Windows Server 2012 und Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="36b88-110">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="36b88-111">Die transparentere Methode zum Überwachen eines Betriebssystems ist die Verwendung des Windows Server-Betriebssystem-Management Packs.</span><span class="sxs-lookup"><span data-stu-id="36b88-111">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="36b88-112">Sie stellt die grundlegenden Überwachungs Grundlagen wie Leistung, Integrität und Verfügbarkeit für Computer bereit, auf denen Windows Server 2012, Windows Server 2012 R2 und Windows Server 2008 R2 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="36b88-112">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="36b88-113">Durch die Erkennung, Benachrichtigung und automatische Reaktion auf wichtige Ereignisse und Leistungsindikatoren reduzieren diese Management Packs die auflösungszeiten für Probleme und verbessern die allgemeine Verfügbarkeit und Leistung von Systemen, auf denen die Windows Server-Betriebssysteme ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="36b88-113">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="36b88-114">Neben den relevanten Windows Server-Management Packs für System Center Operations Manager können die folgenden System Tools und-Ressourcen verwendet werden, um den Zustand des Betriebssystems zu überwachen (je nach Betriebssystemversion).</span><span class="sxs-lookup"><span data-stu-id="36b88-114">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server-2008-r2"></a><span data-ttu-id="36b88-115">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="36b88-115">Windows Server 2008 R2</span></span>

<span data-ttu-id="36b88-116">Windows Server 2008 R2 umfasst die folgenden zusätzlichen Features und Tools, die Administratoren bei der grundlegenden Überwachung und Verwaltung des Betriebssystems helfen:</span><span class="sxs-lookup"><span data-stu-id="36b88-116">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="36b88-p103">Der **Windows-Ressourcenmonitor** ist ein leistungsstarkes Tool, um zu verstehen, wie Systemressourcen von Prozessen und Diensten verwendet werden. Zusätzlich zur Überwachung des Ressourceneinsatzes in Echtzeit kann ein Ressourcenmonitor dazu beitragen, nicht reagierende Prozesse zu analysieren, zu erkennen, welche Anwendungen Dateien verwenden, und Prozesse und Dienste zu steuern.</span><span class="sxs-lookup"><span data-stu-id="36b88-p103">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services. In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="36b88-p104">Die **Zuverlässigkeitsanalysekomponente** ist ein mitgelieferter Agent, der detaillierte Erfahrungsinformationen zur Systemauslastung und -zuverlässigkeit bereitstellt. Diese Informationen werden über eine WMI-Schnittstelle zur Verwendung durch tragbare Lesesysteme zur Verfügung gestellt. Entwickler können mit der über eine WMI-Schnittstelle verfügbar gemachten Zuverlässigkeitsanalysekomponente Anwendungen überwachen und analysieren und so die Zuverlässigkeit und Leistung steigern.</span><span class="sxs-lookup"><span data-stu-id="36b88-p104">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability. This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems. By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="36b88-122">**Windows Server 2008 R2** verwendet die integrierte Komponente für die Zuverlässigkeitsanalyse, um einen Zuverlässigkeits Index zu berechnen, der Informationen zur allgemeinen Systemnutzung und zur Stabilität im Laufe der Zeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="36b88-122">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="36b88-123">Die Komponente Zuverlässigkeitsanalyse verfolgt auch alle wichtigen Änderungen am System, die wahrscheinlich die Stabilität beeinflussen, wie etwa Windows-Updates und Anwendungsinstallationen.</span><span class="sxs-lookup"><span data-stu-id="36b88-123">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server-2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="36b88-124">Windows Server 2008 Windows-Zuverlässigkeits-und Leistungsüberwachung</span><span class="sxs-lookup"><span data-stu-id="36b88-124">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="36b88-p106">Die Windows-Zuverlässigkeits- und Leistungsüberwachung ist ein MMC-Snap-In, das die Funktionalität früherer eigenständiger Tools kombiniert, darunter Leistungsprotokolle und -warnungen, Server Performance Advisor und Systemmonitor. Es stellt eine grafische Oberfläche für das Anpassen der Leistungsdatenerfassung und Ereignisablaufverfolgungssitzungen bereit.</span><span class="sxs-lookup"><span data-stu-id="36b88-p106">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor. It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="36b88-127">Es umfasst zudem die Zuverlässigkeitsüberwachung, ein MMC Snap-In, das Änderungen am System nachverfolgt, mit Änderungen in der Systemstabilität vergleicht und eine grafische Ansicht der Beziehung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="36b88-127">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="36b88-128">Windows-Zuverlässigkeits- und Leistungsüberwachung
</span><span class="sxs-lookup"><span data-stu-id="36b88-128">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="36b88-129">Während die Windows-Zuverlässigkeits-und Leistungsüberwachung Funktionen einiger ehemaliger eigenständige Tools wie Leistungsprotokolle und-Warnungen sowie System Monitor und Server Leistungs Ratgeber kombinieren, bietet Sie auch einige neue Funktionen für Windows Server 2008 und Windows Server 2008 R2, wie etwa die folgenden:</span><span class="sxs-lookup"><span data-stu-id="36b88-129">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="36b88-130">Datensammlungssätze</span><span class="sxs-lookup"><span data-stu-id="36b88-130">Data Collector Sets</span></span>

  - <span data-ttu-id="36b88-131">Ressourcenansicht</span><span class="sxs-lookup"><span data-stu-id="36b88-131">Resource View</span></span>

  - <span data-ttu-id="36b88-132">Zuverlässigkeitsüberwachung</span><span class="sxs-lookup"><span data-stu-id="36b88-132">Reliability Monitor</span></span>

  - <span data-ttu-id="36b88-133">Assistenten und Vorlagen zum Erstellen von Protokollen</span><span class="sxs-lookup"><span data-stu-id="36b88-133">Wizards and templates for creating logs</span></span>

<span data-ttu-id="36b88-p107">Der **Datensammlungssatz** gruppiert Datensammlungen in wiederverwendbare Elemente, die in verschiedenen Leistungsüberwachungsszenarien verwendet werden können. Nachdem eine Gruppe von Datensammlungen als Datensammlungssatz gespeichert wurde, können Vorgänge wie eine Zeitplanung durch das Ändern einer einzigen Eigenschaft für den gesamten Satz angewendet werden. Die Windows-Zuverlässigkeits- und Leistungsüberwachung beinhaltet Standardvorlagen für Datensammlungssätze, mit denen Systemadministratoren sofort beginnen können, Leistungsdaten zu sammeln, die für eine Serverrolle oder ein Überwachungsszenario spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="36b88-p107">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios. After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="36b88-p108">Die Startseite der Windows-Zuverlässigkeits- und -Leistungsüberwachung ist die neue **Ressourcenansicht**. Auf diesem Bildschirm wird eine grafische Echtzeitübersicht über die CPU-, Datenträger-, Netzwerk- und Arbeitsspeicherauslastung bereitgestellt. Durch Erweiterung dieser überwachten Elemente können Systemadministratoren erkennen, welche Prozesse welche Ressourcen verwenden. In früheren Versionen von Windows waren diese prozessspezifischen Echtzeitdaten nur in begrenzter Form über den Task-Manager verfügbar.</span><span class="sxs-lookup"><span data-stu-id="36b88-p108">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage. By expanding each of these monitored elements, system administrators can identify which processes are using which resources. In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="36b88-p109">Die **Zuverlässigkeitsüberwachung** berechnet einen Systemstabilitätsindex, der darstellt, ob unerwartete Probleme die Zuverlässigkeit des Systems verringert haben. Ein Diagramm des Stabilitätsindex über die Zeit identifiziert schnell die Daten beim erstmaligen Auftreten der Probleme. Der begleitende Systemstabilitätsbericht stellt Details zur Verfügung, die die Problembehandlung der Ursache für die verringerte Zuverlässigkeit unterstützen. Durch Anzeigen von Änderungen am System (Installation oder Entfernen von Anwendungen, Updates am Betriebssystem oder Hinzufügen oder Ändern von Treibern) neben Fehlern (Anwendungsfehler, Betriebssystemabstürze oder Hardwareausfälle) kann schnell eine Strategie für die Lösung von Problemen entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="36b88-p109">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system. A graph of the Stability Index over time quickly identifies dates when issues began to occur. The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability. By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="36b88-p110">Das Hinzufügen von Leistungsindikatoren zu Protokolldateien und das Planen von Start, Beenden und Dauer dieser Leistungsindikatoren kann jetzt über eine **Assistenten-Oberfläche** durchgeführt werden. Darüber hinaus können Systemadministratoren durch das Speichern dieser Konfiguration als Vorlage dasselbe Protokoll auf anderen Computern erfassen, ohne die Prozesse für das Auswählen und Planen der Datensammlung wiederholen zu müssen. Features der Leistungsprotokolle und -warnungen wurden in die Windows-Zuverlässigkeits- und -Leistungsüberwachung integriert und können mit jeder Datensammlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="36b88-p110">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**. In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes. Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

<span data-ttu-id="36b88-146"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="36b88-146"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

