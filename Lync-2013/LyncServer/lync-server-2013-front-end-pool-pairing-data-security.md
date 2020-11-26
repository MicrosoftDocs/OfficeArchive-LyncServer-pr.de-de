---
title: 'Lync Server 2013: Datensicherheit beim Bilden von Front-End-Poolpaaren'
description: 'Lync Server 2013: Front-End-Pool-Kopplung von Datensicherheit.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32a2ce72752819392429c8407649e663494f1daf
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428048"
---
# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="8a5c0-103">Datensicherheit beim Bilden von Front-End-Poolpaaren in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a5c0-103">Front End pool pairing data security in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="8a5c0-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="8a5c0-104">

<span> </span></span></span>

<span data-ttu-id="8a5c0-105">_**Letztes Änderungsdatum des Themas:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="8a5c0-105">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="8a5c0-106">Bei dem Sicherungsdienst handelt es sich um einen in lync Server 2013 eingeführten Datenreplikationsmechanismus, der Benutzerdaten und Konferenzinhalte zwischen zwei gekoppelten Front-End-Pools kontinuierlich über zwei Rechenzentren für Disaster Recovery überträgt.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-106">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="8a5c0-107">Die Benutzerdaten enthalten Benutzer-SIP-URIs sowie Kontaktlisten und-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-107">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="8a5c0-108">Konferenzinhalte umfassen Microsoft PowerPoint 2010-Uploads sowie Whiteboards, die in Konferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-108">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="8a5c0-109">Aus dem Quell Pool werden Benutzerdaten und Konferenzinhalte aus dem lokalen Speicher exportiert, gezippt, in den Ziel Pool übertragen, wo Sie entpackt und in den lokalen Speicher importiert werden.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-109">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="8a5c0-110">Der Sicherungsdienst geht davon aus, dass die Kommunikationsverbindung zwischen den beiden Rechenzentren innerhalb des Unternehmensnetzwerks besteht, das vor dem Internet geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-110">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="8a5c0-111">Sie verschlüsseln weder die übertragenen Daten zwischen den beiden Rechenzentren, noch ist Sie nativ in einem sicheren Protokoll wie HTTPS gekapselt.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-111">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="8a5c0-112">Deshalb ist ein man-in-the-Middle-Angriff durch internes Personal innerhalb des Unternehmensnetzwerks möglich.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-112">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="8a5c0-113">Auswerten von Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="8a5c0-113">Evaluating Security Risks</span></span>

<span data-ttu-id="8a5c0-114">Alle Unternehmen, die lync Server 2013 in mehreren Rechenzentren bereitstellen und das Disaster Recovery-Feature verwenden, müssen sicherstellen, dass der Verkehr zwischen Datencentern durch das Unternehmens Intranet geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-114">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="8a5c0-115">Unternehmen, die sich um internen Angriffsschutz kümmern, müssen die Kommunikationsverbindungen zwischen den Rechenzentren sichern.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-115">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="8a5c0-116">Die Annahme, dass Rechenzentren eines Unternehmens hinter dem Unternehmens Intranet geschützt sind, ist Standard.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-116">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard.</span></span> <span data-ttu-id="8a5c0-117">Es gibt viele andere Arten vertraulicher Unternehmensdaten, die zwischen diesen Rechenzentren übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-117">There are many other types of corporate sensitive data transferred among these data centers.</span></span> <span data-ttu-id="8a5c0-118">Die IT-Infrastruktur des Unternehmens ist mit einem unsicheren Risiko behaftet, wenn diese quer Datencenter-Links nicht geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-118">The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="8a5c0-119">Das Risiko von Man-in-the-Middle-Angriffen innerhalb des Unternehmensnetzwerks besteht zwar, doch ist es im Vergleich zur Gefährdung des Datenverkehrs im Internet relativ begrenzt.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-119">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet.</span></span> <span data-ttu-id="8a5c0-120">Insbesondere sind die vom Sicherungsdienst (wie SIP-URIs) verfügbar gemachten Benutzerdaten im Allgemeinen für alle Mitarbeiter im Unternehmen über andere Mittel wie das globale Adressbuch von Exchange oder einer anderen Verzeichnis Software verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-120">Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software.</span></span> <span data-ttu-id="8a5c0-121">Daher sollte der Fokus auf dem Sichern des WAN zwischen den beiden Rechenzentren liegen, wenn der Sicherungsdienst zum Kopieren von Daten zwischen den beiden gekoppelten Pools verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-121">Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="8a5c0-122">Verringern von Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="8a5c0-122">Mitigating Security Risks</span></span>

<span data-ttu-id="8a5c0-123">Es gibt viele Möglichkeiten, den Sicherheitsschutz für den Backup-Dienst Datenverkehr zu verbessern, vom Einschränken des Zugriffs auf die Rechenzentren bis hin zum Sichern des WAN-Transports zwischen den beiden Rechenzentren.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-123">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="8a5c0-124">In den meisten Fällen verfügen Unternehmen, die lync Server 2013 bereitstellen, möglicherweise bereits über die erforderliche Sicherheitsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-124">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="8a5c0-125">Für Unternehmen, die nach Anleitungen suchen, bietet Microsoft eine Lösung als Beispiel für die Erstellung einer sicheren IT-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-125">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="8a5c0-126">Dies impliziert jedoch nicht, dass es sich um die einzige Lösung handelt, und es impliziert auch nicht, dass es sich um die bevorzugte Lösung für lync Server handelt.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-126">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="8a5c0-127">Es wird empfohlen, dass Unternehmenskunden die Lösung auswählen, die ihren spezifischen Anforderungen entspricht, basierend auf Ihrer IT-Sicherheitsinfrastruktur und-Anforderungen. Die Microsoft-Beispiellösung verwendet IPSec und Gruppenrichtlinien für die Server-und Domänenisolierung.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-127">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="8a5c0-128">Ausführliche Informationen finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544) .</span><span class="sxs-lookup"><span data-stu-id="8a5c0-128">For details, see [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="8a5c0-129">Wenden Sie sich bei Fragen und Kommentaren an SecWish@Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-129">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="8a5c0-130">Eine weitere mögliche Lösung besteht in der Verwendung von IPSec ausschließlich zur Sicherung der vom Sicherungsdienst selbst gesendeten Daten.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-130">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="8a5c0-131">Wenn Sie sich für diese Methode entscheiden, konfigurieren Sie die IPSec-Regeln für das SMB-Protokoll auf den folgenden Servern, wenn Pool A und Pool B zwei verbundene Front-End-Pools sind.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-131">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="8a5c0-132">Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool A an den von Pool B verwendeten Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-132">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="8a5c0-133">Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool B an den von Pool A verwendeten Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-133">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="8a5c0-134">IPsec ist nicht als Ersatz für Sicherheit auf Anwendungsebene wie etwa SSL/TLS gedacht.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-134">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="8a5c0-135">Ein Vorteil der Verwendung von IPsec liegt darin, dass es Sicherheit für Netzwerkdatenverkehr für vorhandene Apps bereitstellen kann, ohne dass diese geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-135">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="8a5c0-136">Unternehmen, die einfach nur den Transport zwischen den beiden Rechenzentren schützen möchten, sollten sich bei den Herstellern der jeweiligen Netzwerkhardware erkundigen, wie sie mit den betreffenden Geräten sichere WAN-Verbindungen einrichten können.</span><span class="sxs-lookup"><span data-stu-id="8a5c0-136">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



<span data-ttu-id="8a5c0-137"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="8a5c0-137"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

