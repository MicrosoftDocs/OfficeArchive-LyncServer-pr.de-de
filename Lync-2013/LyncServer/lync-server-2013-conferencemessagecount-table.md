---
title: 'Lync Server 2013: ConferenceMessageCount-Tabelle'
description: 'Lync Server 2013: ConferenceMessageCount-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 271b654c09ab1aef194eb613e660de208aea1534
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49434452"
---
# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="74ef6-103">ConferenceMessageCount-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74ef6-103">ConferenceMessageCount table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="74ef6-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="74ef6-104">

<span> </span></span></span>

<span data-ttu-id="74ef6-105">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="74ef6-105">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="74ef6-106">Jeder Datensatz in dieser Tabelle steht für einen Benutzer in einer Chat Konferenz und enthält die Anzahl der von diesem Benutzer gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="74ef6-106">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="74ef6-107">Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. ein Datensatz für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="74ef6-107">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74ef6-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="74ef6-108">Column</span></span></th>
<th><span data-ttu-id="74ef6-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="74ef6-109">Data Type</span></span></th>
<th><span data-ttu-id="74ef6-110">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="74ef6-110">Key/Index</span></span></th>
<th><span data-ttu-id="74ef6-111">Details</span><span class="sxs-lookup"><span data-stu-id="74ef6-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74ef6-112"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="74ef6-112"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74ef6-113">datetime</span><span class="sxs-lookup"><span data-stu-id="74ef6-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="74ef6-114">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="74ef6-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="74ef6-115">Uhrzeit der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="74ef6-115">Time of conference instance.</span></span> <span data-ttu-id="74ef6-116">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="74ef6-116">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="74ef6-117">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ef6-117">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ef6-118"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="74ef6-118"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="74ef6-119">int</span><span class="sxs-lookup"><span data-stu-id="74ef6-119">int</span></span></p></td>
<td><p><span data-ttu-id="74ef6-120">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="74ef6-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="74ef6-121">Die ID-Nummer zum Identifizieren der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="74ef6-121">ID number to identify the conference instance.</span></span> <span data-ttu-id="74ef6-122">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="74ef6-122">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="74ef6-123">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="74ef6-123">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ef6-124"><strong>UserID</strong></span><span class="sxs-lookup"><span data-stu-id="74ef6-124"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="74ef6-125">int</span><span class="sxs-lookup"><span data-stu-id="74ef6-125">int</span></span></p></td>
<td><p><span data-ttu-id="74ef6-126">Fremd</span><span class="sxs-lookup"><span data-stu-id="74ef6-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="74ef6-127">Eindeutige Nummer, die diesen Benutzer identifiziert, auf die <a href="lync-server-2013-users-table.md">in der Tabelle "Benutzer" in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="74ef6-127">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ef6-128"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="74ef6-128"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="74ef6-129">smallint</span><span class="sxs-lookup"><span data-stu-id="74ef6-129">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="74ef6-130">Die Anzahl der Nachrichten, die dieser Benutzer während dieser Konferenz gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="74ef6-130">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table><span data-ttu-id="74ef6-131">


</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="74ef6-131">


</div>

<span> </span>

</div>

</div>

</span></span></div>

