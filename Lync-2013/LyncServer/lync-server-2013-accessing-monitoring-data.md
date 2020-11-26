---
title: 'Lync Server 2013: Zugreifen auf Überwachungsdaten'
description: 'Lync Server 2013: Zugriff auf Überwachungsdaten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c183a66c98072f2ab30bb49e561f9f95c753142f
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49439499"
---
# <a name="accessing-monitoring-data-in-lync-server-2013"></a><span data-ttu-id="d129a-103">Zugreifen auf Überwachungsdaten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d129a-103">Accessing monitoring data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="d129a-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="d129a-104">

<span> </span></span></span>

<span data-ttu-id="d129a-105">_**Letztes Änderungsdatum des Themas:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="d129a-105">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="d129a-p101">Überwachungsdaten werden paarweise in SQL Server-Datenbanken gespeichert: Datenbank „LcsCdr“ für Kommunikationsdatensätze und „QoEMetrics“ für QoE-Daten (Quality of Experience). Zu diesen beiden Datenbanken gibt es nichts Spezielles, d. h., dass auf die in diesen Datenbanken gespeicherten Daten mit allen Tools zugegriffen werden kann, die normalerweise zum Zugriff auf die SQL Server-Daten und zur Analyse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d129a-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>

<span data-ttu-id="d129a-108">Ein Tool, das Sie für den Zugriff auf und die Analyse von Überwachungsdaten in Frage stellen sollten, sind die lync Server-Überwachungsberichte.</span><span class="sxs-lookup"><span data-stu-id="d129a-108">One tool you should consider for accessing and analyzing monitoring data is the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="d129a-109">Überwachungsberichte sind eine Reihe von Standardberichten, die vom Microsoft SQL Server-Berichterstattungsdienst veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="d129a-109">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="d129a-110">Diese Berichte, auf die über einen Webbrowser zugegriffen werden kann, liefern Informationen zu Nutzung, Anrufdiagnose und Medienqualität basierend auf den KDS- und QoE-Datensätzen in den KDS- und QoE-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="d129a-110">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="d129a-111">Überwachungsberichte werden mit lync Server 2013 ausgeliefert und können über den lync Server-Bereitstellungs-Assistenten installiert werden, nachdem lync Server installiert und die Überwachung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="d129a-111">Monitoring Reports ship with Lync Server 2013 and can be installed from the Lync Server Deployment Wizard after Lync Server has been installed and monitoring has been configured.</span></span>

<span data-ttu-id="d129a-p103">Wie bereits an früherer Stelle angemerkt, ist für Monitoring-Berichte SQL Server Reporting Service erforderlich. SQL Server Reporting Service kann gleichzeitig mit SQL Server installiert werden oder auch nach der Installation von SQL Server installiert werden.</span><span class="sxs-lookup"><span data-stu-id="d129a-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>

<span data-ttu-id="d129a-114">Weitere Informationen finden Sie im Bereitstellungshandbuch für lync Server 2013 im Thema [Installieren der lync Server 2013-Überwachungsberichte](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) .</span><span class="sxs-lookup"><span data-stu-id="d129a-114">For more information, see the topic [Installing Lync Server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) in the Lync Server 2013 deployment guide.</span></span>

<span data-ttu-id="d129a-115"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="d129a-115"></div>

<span> </span>

</div>

</div>

</span></span></div>

