---
title: 'Lync Server 2013: Dokumentation'
description: 'Lync Server 2013: Dokumentation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Documentation
ms:assetid: 5a69c0a2-0986-49c3-809c-89bc175a34ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720335(v=OCS.15)
ms:contentKeyID: 63969609
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f128daa7941db8ae461b4bb12bcc9b97bbb5876e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49393815"
---
# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="9d346-103">Dokumentation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d346-103">Documentation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="9d346-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="9d346-104">

<span> </span></span></span>

<span data-ttu-id="9d346-105">_**Letztes Änderungsdatum des Themas:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="9d346-105">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="9d346-106">Das MOF-Modell besteht aus zahlreichen Dienstverwaltungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="9d346-106">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="9d346-107">Die Dokumentation dazu, wie und wann Aufgaben ausgeführt werden, kann für Mitglieder desselben Teams oder für andere Teams freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9d346-107">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="9d346-108">Die Methode zum Speichern und Freigeben von Dokumenten kann je nach Art der Funktion variieren.</span><span class="sxs-lookup"><span data-stu-id="9d346-108">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="9d346-109">Beispielsweise können die Verfahren für die Systemverwaltung als Word-Dokumente gespeichert werden, da Sie wahrscheinlich häufig gedruckt und referenziert werden.</span><span class="sxs-lookup"><span data-stu-id="9d346-109">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="9d346-110">Informationen zur Konfigurationsverwaltung werden möglicherweise automatisch generiert und in einer Datenbank gespeichert, um Sie einfacher suchen und indizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="9d346-110">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="9d346-111">Einige Dokumentationen sind möglicherweise vertraulich und sollten eingeschränkt sein.</span><span class="sxs-lookup"><span data-stu-id="9d346-111">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="9d346-112">Dokumentverwaltungssysteme</span><span class="sxs-lookup"><span data-stu-id="9d346-112">Document management systems</span></span>

<span data-ttu-id="9d346-113">Ein Dokumentations Verwaltungssystem fungiert als zentrales Repository für Dokumente und sorgt dafür, dass nur die neueste Revision eines Dokuments verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9d346-113">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="9d346-114">Sie können auch die Archivierung der älteren Version des Dokuments als Referenz verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d346-114">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="9d346-115">Lync Server bietet für diese Aufgabe geeignete Funktionen.</span><span class="sxs-lookup"><span data-stu-id="9d346-115">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="9d346-116">Datenbanken</span><span class="sxs-lookup"><span data-stu-id="9d346-116">Databases</span></span>

<span data-ttu-id="9d346-117">Es wurden verschiedene Tools und Verwaltungsfunktionen besprochen, die für die Verwendung von Datenbanken geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="9d346-117">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="9d346-118">Der Konfigurationsverwaltungsprozess verwendet wahrscheinlich automatisierte Prozesse, in denen große Datenmengen gespeichert werden, die indiziert und durchsucht werden müssen.</span><span class="sxs-lookup"><span data-stu-id="9d346-118">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="9d346-119">Support Mitarbeiter können bei der Behebung neuer Probleme eine Datenbank mit früheren Problemen und Lösungen durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="9d346-119">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="9d346-120">Es ist wahrscheinlich, dass verschiedene Datenbanken für unterschiedliche Zwecke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9d346-120">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="9d346-121">Entscheiden Sie, ob diese Datenbankenverknüpft oder kombiniert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9d346-121">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="9d346-122">Wenn der Service Desk beispielsweise mehrere Probleme mit einem allgemeinen Design identifiziert (wie etwa neue Software, die ein Problem mit einem bestimmten Netzwerkadapter verursacht), kann das Supportpersonal die Konfigurationsdatenbank Abfragen, um vorherzusagen, wie viele Computer betroffen sein könnten.</span><span class="sxs-lookup"><span data-stu-id="9d346-122">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

<span data-ttu-id="9d346-123"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="9d346-123"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

