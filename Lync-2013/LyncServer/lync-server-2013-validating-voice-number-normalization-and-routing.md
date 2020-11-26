---
title: 'Lync Server 2013: Überprüfen der Normalisierung und des Routings von sprach Nummern'
description: 'Lync Server 2013: Überprüfen der Normalisierung und des Routings von sprach Nummern.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f28f679cbb991bdb90362eb61c9c7b68879791e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49438624"
---
# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="4a87d-103">Überprüfen der Normalisierung und des Routings von sprach Nummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a87d-103">Validating voice number normalization and routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="4a87d-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="4a87d-104">

<span> </span></span></span>

<span data-ttu-id="4a87d-105">_**Letztes Änderungsdatum des Themas:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="4a87d-105">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="4a87d-106">Korrekte Zahlen Normalisierung und-Routing ist für die funktionelle Enterprise-VoIP-Umgebung sehr wichtig.</span><span class="sxs-lookup"><span data-stu-id="4a87d-106">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="4a87d-107">Besonders bei Migrationen von der privaten Branch Exchange (PBX) zur eigenständigen lync Server-Umgebung besteht einer der Schlüssel für eine erfolgreiche Migration darin, alle vorhandenen Wählregeln anzuzeigen und zu dokumentieren und geeignete Normalisierungsregeln, VoIP-Richtlinien, Telefonverwendungen und-Routen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4a87d-107">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="4a87d-108">Das Überprüfen der Normalisierung und des Routings von Zahlen ist nicht nur bei Migrationen wichtig, sondern auch im normalen, stabilen Betrieb des Systems.</span><span class="sxs-lookup"><span data-stu-id="4a87d-108">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="4a87d-109">Wir empfehlen, diese Überprüfung täglich mithilfe der lync Server-Systemsteuerung durchzuführen, beginnend mit der Entwicklung einer robusten Reihe von Testfällen für den aktuellen Satz von Normalisierungsregeln, die in den globalen lync Server-Einstellungen veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="4a87d-109">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="4a87d-110">Diese Testfälle sollten täglich ausgeführt werden, um alle unerwünschten Änderungen hervorzuheben, die an den Wähleinstellungen vorgenommen und zugesichert wurden.</span><span class="sxs-lookup"><span data-stu-id="4a87d-110">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="4a87d-111">Die lync Server-Systemsteuerung unterstützt Sie auch beim visualisieren, testen, ändern, archivieren und Freigeben von Konfigurationsinformationen zum VoIP-Routing sowie zum Ändern von Regeln für die Normalisierung von Unternehmens-und sprach Nummern, Wählpläne, VoIP-Richtlinien und Routen.</span><span class="sxs-lookup"><span data-stu-id="4a87d-111">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="4a87d-112">Es bietet zusätzliche Funktionen für folgende Aktionen:</span><span class="sxs-lookup"><span data-stu-id="4a87d-112">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="4a87d-113">Exportieren und importieren oder Sichern von VoIP-Routingdaten zwischen Systemen.</span><span class="sxs-lookup"><span data-stu-id="4a87d-113">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="4a87d-114">Testen Sie Konfigurationsänderungen, bevor Sie Sie in ein Live System hochladen.</span><span class="sxs-lookup"><span data-stu-id="4a87d-114">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="4a87d-115">Erstellen und Ausführen von Konfigurations Testfälle, um die Nutzbarkeit von Routingdaten nach dem vornehmen von Änderungen zu gewährleisten, aber bevor Sie die Änderungen an einem bereitgestellten System durchführen.</span><span class="sxs-lookup"><span data-stu-id="4a87d-115">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="4a87d-116">Erstellen und Ändern von Nummern Normalisierungsregeln, Standortprofilen, VoIP-Richtlinien und Routingdaten, ohne die erforderlichen regulären Ausdrücke zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="4a87d-116">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="4a87d-117">Analysieren eines Standortprofils zur Kompatibilität mit der lync Server Phone Edition</span><span class="sxs-lookup"><span data-stu-id="4a87d-117">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="4a87d-118">Weitere Informationen zu VoIP-Routing Tests finden Sie unter [Testen des VoIP-Routings in lync Server 2013](lync-server-2013-test-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="4a87d-118">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4a87d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a87d-119">See Also</span></span>


[<span data-ttu-id="4a87d-120">Testen des VoIP-Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a87d-120">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

<span data-ttu-id="4a87d-121"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="4a87d-121"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

