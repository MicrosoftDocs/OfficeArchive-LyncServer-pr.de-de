---
title: 'Lync Server 2013: Ausfallsicherheitslösungen für Zweigstellenstandorte'
description: 'Lync Server 2013: Lösungen für die Stabilität von Branch-Site.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 796ed22344f02bca16571ff5f156c6bb80b1fcfd
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49435981"
---
# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="17fc1-103">Ausfallsicherheitslösungen für Zweigstellenstandorte in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17fc1-103">Branch-site resiliency solutions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="17fc1-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="17fc1-104">

<span> </span></span></span>

<span data-ttu-id="17fc1-105">_**Letztes Änderungsdatum des Themas:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="17fc1-105">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="17fc1-106">Es gibt offensichtliche Vorteile für die Bereitstellung von Ausfallsicherheit für Zweigstellen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="17fc1-106">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="17fc1-107">Insbesondere wenn Sie die Verbindung mit dem zentralen Standort verlieren, verfügen die Benutzer von Zweigstellenbenutzern weiterhin über Enterprise-VoIP-Dienst und Voicemail (wenn Sie die Einstellungen für die Neukonfiguration von Voicemail konfigurieren; Einzelheiten finden Sie unter Anforderungen an die [Standort Stabilität von lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="17fc1-107">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="17fc1-108">Bei Websites mit weniger als 25 Benutzern bietet eine Lösung für Ausfallsicherheit möglicherweise keine ausreichende Rentabilität.</span><span class="sxs-lookup"><span data-stu-id="17fc1-108">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="17fc1-109">Wenn Sie sich für die Bereitstellung von Ausfallsicherheit für Zweigstellen entscheiden, stehen Ihnen drei Optionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="17fc1-109">If you decide to provide branch-site resiliency, you have three options.</span></span> <span data-ttu-id="17fc1-110">In der folgenden Tabelle können Sie die beste Option für Ihre Organisation ermitteln.</span><span class="sxs-lookup"><span data-stu-id="17fc1-110">The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17fc1-111">Wenn Sie...</span><span class="sxs-lookup"><span data-stu-id="17fc1-111">If you…</span></span></th>
<th><span data-ttu-id="17fc1-112">Wir empfehlen die Verwendung einer...</span><span class="sxs-lookup"><span data-stu-id="17fc1-112">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17fc1-113">Hosten Sie zwischen 25 und 1000 Benutzern an ihrer Zweigstelle, und wenn die Kapitalrendite keine vollständige Bereitstellung unterstützt oder wenn die lokale administrative Unterstützung nicht verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="17fc1-113">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="17fc1-114">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="17fc1-114">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="17fc1-115">Die Survivable Branch-Appliance ist ein branchenüblicher Blade-Server mit einer lync Server-Registrierungsstelle und einem Vermittlungsserver, die unter Windows Server 2008 R2 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="17fc1-115">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="17fc1-116">Die Survivable Branch-Appliance enthält auch ein PSTN-Gateway (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="17fc1-116">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="17fc1-117">Qualifizierte Drittanbietergeräte (entwickelt von Microsoft-Partnern im SBA-Qualifizierungs-/-Zertifizierungsprogramm) bieten eine durchgehende PSTN-Verbindung im Fall eines WAN-Fehlers, doch dieser Ansatz bietet keine belastbaren Anwesenheits-und Konferenzfunktionen, da diese Features von Front-End-Servern am zentralen Standort abhängen.</span><span class="sxs-lookup"><span data-stu-id="17fc1-117">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="17fc1-118">Details zu Überlebenden Branch-Appliances finden Sie &quot; &quot; weiter unten in diesem Thema unter Survivable Branch Appliance Details.</span><span class="sxs-lookup"><span data-stu-id="17fc1-118">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="17fc1-119"><strong>Hinweis:</strong> Wenn Sie sich entscheiden, auch einen SIP-Trunk für Ihre Survivable Branch-Appliance zu verwenden, wenden Sie sich an den Anbieter von Survivable Branch Appliance, um zu erfahren, welcher Dienstanbieter für Ihre Organisation am besten geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="17fc1-119"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17fc1-120">Hosten zwischen 1000-und 2000-Benutzern an ihrer Zweigstelle, keine robuste WAN-Verbindung und geschulte lync Server-Administratoren verfügbar</span><span class="sxs-lookup"><span data-stu-id="17fc1-120">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="17fc1-121">Überlebensfähiger Branch-Server oder zwei überlebensfähige Branch-Appliances.</span><span class="sxs-lookup"><span data-stu-id="17fc1-121">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="17fc1-122">Bei dem Überlebenden Verzweigungs Server handelt es sich um eine Windows Server-Besprechung, die die Hardwareanforderungen enthält, auf denen die lync Server Registrar-und Mediation Server-Software installiert ist.</span><span class="sxs-lookup"><span data-stu-id="17fc1-122">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="17fc1-123">Sie muss mit einem PSTN-Gateway oder einem SIP-Trunk an einen Telefondienstanbieter angeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="17fc1-123">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="17fc1-124">Details zu Überlebenden Verzweigungs Servern finden Sie &quot; &quot; weiter unten in diesem Thema unter Informationen zu Überlebenden Verzweigungs Servern.</span><span class="sxs-lookup"><span data-stu-id="17fc1-124">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17fc1-125">Wenn Sie zusätzlich zu den Sprachfeatures für bis zu 5000-Benutzer Anwesenheits-und Konferenzfeatures benötigen und die lync Server-Administratoren verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="17fc1-125">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="17fc1-126">Bereitstellen als zentrale Website mit einem Standard Edition-Server und nicht als Verzweigungs Website</span><span class="sxs-lookup"><span data-stu-id="17fc1-126">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="17fc1-127">Eine umfassende lync Server-Bereitstellung bietet eine durchgehende PSTN-Verbindung sowie eine zuverlässige Anwesenheits-und Konferenzfunktion bei einem WAN-Fehler.</span><span class="sxs-lookup"><span data-stu-id="17fc1-127">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="17fc1-128">Details zum Vorbereiten dieser Lösung finden Sie unter <a href="lync-server-2013-planning-for-your-organization.md">Organisationsplanung für lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Ermitteln der Systemanforderungen für lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Ermitteln der Infrastrukturanforderungen für lync Server 2013</a>und anderer relevanter Abschnitte der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="17fc1-128">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="17fc1-129">Stabilitäts Topologien</span><span class="sxs-lookup"><span data-stu-id="17fc1-129">Resiliency Topologies</span></span>

<span data-ttu-id="17fc1-130">Die folgende Abbildung zeigt die empfohlenen Topologien für die Ausfallsicherheit von Zweigstellen.</span><span class="sxs-lookup"><span data-stu-id="17fc1-130">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="17fc1-131">**Stabilitäts Optionen für Zweigstellenstandorte**</span><span class="sxs-lookup"><span data-stu-id="17fc1-131">**Branch site resiliency options**</span></span>

<span data-ttu-id="17fc1-132">![Optionen für die Widerstandsfähigkeit der sprach Verzweigung](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Optionen für die Widerstandsfähigkeit der sprach Verzweigung")</span><span class="sxs-lookup"><span data-stu-id="17fc1-132">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="17fc1-133">Details zu Survivable Branch Appliances</span><span class="sxs-lookup"><span data-stu-id="17fc1-133">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="17fc1-134">Die lync Server Survivable Branch-Appliance umfasst die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="17fc1-134">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="17fc1-135">Eine Registrierungsstelle für Benutzerauthentifizierung, Registrierung und Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="17fc1-135">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="17fc1-136">Ein Vermittlungs Server für die Verarbeitung der Signalübertragung zwischen der Registrierungsstelle und einem PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="17fc1-136">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="17fc1-137">Ein PSTN-Gateway zum Weiterleiten von Anrufen an das PSTN als Fall Back Transport bei einem WAN-Ausfall</span><span class="sxs-lookup"><span data-stu-id="17fc1-137">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="17fc1-138">SQL Server Express für den lokalen Benutzerdatenspeicher</span><span class="sxs-lookup"><span data-stu-id="17fc1-138">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="17fc1-139">Die Survivable Branch-Appliance umfasst außerdem PSTN-Stämme, analoge Anschlüsse und einen Ethernet-Adapter.</span><span class="sxs-lookup"><span data-stu-id="17fc1-139">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="17fc1-140">Wenn die WAN-Verbindung der Zweigstelle zu einem zentralen Standort nicht mehr zur Verfügung steht, werden Benutzer der internen Verzweigung weiterhin bei der Überlebenden Branch Appliance-Registrierungsstelle registriert, und Sie erhalten unterbrechungsfreien Sprachdienst mithilfe der überlebensfähigen Branch Appliance-Verbindung mit dem PSTN.</span><span class="sxs-lookup"><span data-stu-id="17fc1-140">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="17fc1-141">Zweigstellenbenutzer, die eine Verbindung von zu Hause aus oder aus anderen Remotestandorten herstellen, können sich bei einem Registrierungsstellen Server an einem zentralen Standort registrieren, wenn die WAN-Verbindung zur Zweigstelle nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="17fc1-141">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="17fc1-142">Diese Benutzer verfügen über eine vollständige Unified Communications-Funktion, mit der Ausnahme, dass eingehende Anrufe an die Zweigstelle an die Voicemail weitergesendet werden.</span><span class="sxs-lookup"><span data-stu-id="17fc1-142">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="17fc1-143">Wenn die WAN-Verbindung verfügbar wird, sollte die vollständige Funktionalität für Benutzer der Verzweigungs Website wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="17fc1-143">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="17fc1-144">Weder das Failover auf die Survivable Branch-Appliance noch die Wiederherstellung des Diensts erfordert das vorhanden sein eines IT-Administrators.</span><span class="sxs-lookup"><span data-stu-id="17fc1-144">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="17fc1-145">Lync Server unterstützt bis zu zwei überlebensfähige Branch-Appliances an einer Zweigstelle.</span><span class="sxs-lookup"><span data-stu-id="17fc1-145">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17fc1-146">Benutzer, die sich in einer Überlebenden lync Server-Branch-Appliance befinden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.</span><span class="sxs-lookup"><span data-stu-id="17fc1-146">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="17fc1-147">Übersicht über Survivable Branch Appliance-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="17fc1-147">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="17fc1-148">Die Survivable Branch Appliance wird von Herstellern von Originalgeräten in Partnerschaft mit Microsoft hergestellt und in deren Auftrag von Wert Schöpfungs Händlern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="17fc1-148">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="17fc1-149">Diese Bereitstellung sollte erst erfolgen, nachdem lync Server am zentralen Standort bereitgestellt wurde, eine WAN-Verbindung mit der Zweigstelle vorhanden ist und die Benutzer von Zweigstellenbenutzern für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="17fc1-149">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="17fc1-150">Ausführliche Informationen zu diesen Phasen finden Sie unter [Bereitstelleneiner Survivable Branch-Appliance oder eines Servers mit lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="17fc1-150">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17fc1-151">Phase</span><span class="sxs-lookup"><span data-stu-id="17fc1-151">Phase</span></span></th>
<th><span data-ttu-id="17fc1-152">Schritte</span><span class="sxs-lookup"><span data-stu-id="17fc1-152">Steps</span></span></th>
<th><span data-ttu-id="17fc1-153">Benutzerrechte</span><span class="sxs-lookup"><span data-stu-id="17fc1-153">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17fc1-154">Einrichten von Active Directory-Domänendiensten für die Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="17fc1-154">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="17fc1-155"><strong>Auf der zentralen Website:</strong></span><span class="sxs-lookup"><span data-stu-id="17fc1-155"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="17fc1-156">Erstellen Sie ein Domänenbenutzerkonto (oder eine Unternehmensidentität) für den Techniker, der die Survivable Branch-Appliance auf der Zweigstelle installieren und aktivieren wird.</span><span class="sxs-lookup"><span data-stu-id="17fc1-156">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="17fc1-157">Erstellen Sie ein Computerkonto (mit dem entsprechenden vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN)) für Survivable Branch Appliance in den Active Directory-Domänendiensten.</span><span class="sxs-lookup"><span data-stu-id="17fc1-157">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="17fc1-158">Erstellen und veröffentlichen Sie im Topologie-Generator die Survivable Branch-Appliance.</span><span class="sxs-lookup"><span data-stu-id="17fc1-158">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="17fc1-159">Das Techniker Benutzerkonto muss ein Mitglied von RTCUniversalSBATechnicians sein.</span><span class="sxs-lookup"><span data-stu-id="17fc1-159">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="17fc1-160">Die Survivable Branch-Appliance muss zur RTCSBAUniversalServices-Gruppe gehören, die automatisch erfolgt, wenn Sie den Topology Builder verwenden.</span><span class="sxs-lookup"><span data-stu-id="17fc1-160">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17fc1-161">Installieren Sie die Survivable Branch-Appliance, und aktivieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="17fc1-161">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="17fc1-162"><strong>Auf der Zweigstelle:</strong></span><span class="sxs-lookup"><span data-stu-id="17fc1-162"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="17fc1-163">Verbinden Sie die Survivable Branch-Appliance mit einem Ethernet-Port und einem PSTN-Anschluss.</span><span class="sxs-lookup"><span data-stu-id="17fc1-163">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="17fc1-164">Starten Sie die Survivable Branch-Appliance.</span><span class="sxs-lookup"><span data-stu-id="17fc1-164">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="17fc1-165">Nehmen Sie an der Überlebenden Branch-Appliance mit dem Domänenbenutzerkonto Teil, das für die Survivable Branch-Appliance am zentralen Standort erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="17fc1-165">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="17fc1-166">Legen Sie den FQDN und die IP-Adresse so ein, dass er dem FQDN entspricht, der im Computerkonto erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="17fc1-166">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="17fc1-167">Konfigurieren Sie die Survivable Branch-Appliance mithilfe der OEM-Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="17fc1-167">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="17fc1-168">Testen Sie die PSTN-Konnektivität.</span><span class="sxs-lookup"><span data-stu-id="17fc1-168">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="17fc1-169">Das Techniker Benutzerkonto muss ein Mitglied von RTCUniversalSBATechnicians sein.</span><span class="sxs-lookup"><span data-stu-id="17fc1-169">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="17fc1-170">Informationen zu Überlebenden Verzweigungs Servern</span><span class="sxs-lookup"><span data-stu-id="17fc1-170">Survivable Branch Server Details</span></span>

<span data-ttu-id="17fc1-171">Erstellen Sie im Topologie-Generator die Verzweigungs Website, fügen Sie den Überlebenden Verzweigungs Server zu dieser Website hinzu, und führen Sie dann den lync Server-Bereitstellungs-Assistenten auf dem Computer aus, auf dem Sie die Rolle installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="17fc1-171">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17fc1-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17fc1-172">See Also</span></span>


[<span data-ttu-id="17fc1-173">Bereitstellen von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17fc1-173">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

<span data-ttu-id="17fc1-174"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="17fc1-174"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

