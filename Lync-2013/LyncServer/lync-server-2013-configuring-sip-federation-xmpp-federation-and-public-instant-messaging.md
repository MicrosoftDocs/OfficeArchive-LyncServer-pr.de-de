---
title: Konfigurieren von SIP-Partnerverbünden, XMPP-Partnerverbünden und öffentlichem Chat
description: Konfigurieren von SIP Federation, XMPP Federation und Public Instant Messaging.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b83c29da75c99e7a338bfd7732aec8ec49cbf47
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49432653"
---
# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="8c75a-103">Konfigurieren von SIP-Partnerverbünden, XMPP-Partnerverbünden und öffentlichem Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c75a-103">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="8c75a-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="8c75a-104">

<span> </span></span></span>

<span data-ttu-id="8c75a-105">_**Letztes Änderungsdatum des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="8c75a-105">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="8c75a-106">Föderation, öffentliche Instant Messaging-Konnektivität und XMPP (Extensible Messaging and Presence Protocol) definieren eine andere Klasse externer Benutzer – Föderationsbenutzer.</span><span class="sxs-lookup"><span data-stu-id="8c75a-106">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="8c75a-107">Benutzer einer Föderations-lync Server-Bereitstellung oder XMPP-Bereitstellung haben Zugriff auf eine begrenzte Anzahl von Diensten und werden von der externen Bereitstellung authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8c75a-107">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="8c75a-108">Remote Benutzer sind Mitglieder ihrer lync Server-Bereitstellung und haben Zugriff auf alle Dienste, die von Ihrer Bereitstellung angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="8c75a-108">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8c75a-109">Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="8c75a-109">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="8c75a-110">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="8c75a-110">has been announced.</span></span> <span data-ttu-id="8c75a-111">Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8c75a-111">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="8c75a-112">Die öffentliche Instant Messaging-Konnektivität ist ein spezieller Föderations, mit dem ein lync Server-Client über lync 2013 auf konfigurierte öffentliche Instant Messaging-Partner zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="8c75a-112">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="8c75a-113">Die aktuellen öffentlichen Instant Messaging-Verbindungspartner sind:</span><span class="sxs-lookup"><span data-stu-id="8c75a-113">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="8c75a-114">America Online</span><span class="sxs-lookup"><span data-stu-id="8c75a-114">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="8c75a-115">Windows Live</span><span class="sxs-lookup"><span data-stu-id="8c75a-115">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="8c75a-116">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="8c75a-116">Yahoo\!</span></span>

<span data-ttu-id="8c75a-117">Eine öffentliche Instant Messaging-Verbindungskonfiguration ermöglicht lync-Benutzern den Zugriff auf öffentliche Instant Messaging-Konnektivitäts-Benutzer durch:</span><span class="sxs-lookup"><span data-stu-id="8c75a-117">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="8c75a-118">Chat und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="8c75a-118">IM and Presence</span></span>

  - <span data-ttu-id="8c75a-119">Sichtbarkeit der öffentlichen Chat-Verbindungs Kontakte in lync-Client</span><span class="sxs-lookup"><span data-stu-id="8c75a-119">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="8c75a-120">Chat Unterhaltungen für Personen mit Kontakten</span><span class="sxs-lookup"><span data-stu-id="8c75a-120">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="8c75a-121">Audio-und Videoanrufe mit Windows Live-Benutzern</span><span class="sxs-lookup"><span data-stu-id="8c75a-121">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="8c75a-122">Der lync Server-Verbund definiert eine Vereinbarung zwischen Ihrer lync Server-Bereitstellung und anderen Office Communications Server 2007 R2-oder lync Server-Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="8c75a-122">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments.</span></span> <span data-ttu-id="8c75a-123">Eine lync Server-Verbund Konfiguration ermöglicht lync-Benutzern den Zugriff auf Verbundbenutzer durch:</span><span class="sxs-lookup"><span data-stu-id="8c75a-123">A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="8c75a-124">Chat und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="8c75a-124">IM and Presence</span></span>

  - <span data-ttu-id="8c75a-125">Erstellen von verbundkontakten im lync-Client</span><span class="sxs-lookup"><span data-stu-id="8c75a-125">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="8c75a-126">Die XMPP-Föderation definiert eine externe Bereitstellung auf der Grundlage des erweiterbaren Messaging-und Anwesenheits Protokolls.</span><span class="sxs-lookup"><span data-stu-id="8c75a-126">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol.</span></span> <span data-ttu-id="8c75a-127">Eine XMPP-Konfiguration ermöglicht lync-Benutzern den Zugriff auf zulässige XMPP-Domänenbenutzer durch:</span><span class="sxs-lookup"><span data-stu-id="8c75a-127">An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="8c75a-128">Chat und Anwesenheit – nur Person zu Person</span><span class="sxs-lookup"><span data-stu-id="8c75a-128">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="8c75a-129">Erstellen von XMPP-verbundkontakten im lync-Client</span><span class="sxs-lookup"><span data-stu-id="8c75a-129">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="8c75a-p106">Die XMPP-Fähigkeit von Lync Server 2013 wird von Microsoft für den Instant-Messaging-Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich bei anderen XMPP-Systemen an den Drittanbieter, um zu überprüfen, ob dieser den Partnerverbund mit Lync Server 2013 unterstützt, und Empfehlungen bei Bereitstellung und Problembehandlung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8c75a-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="8c75a-132">Edge-Server-externer Verbund, öffentliche Instant Messaging-Konnektivität und Bereitstellungsprozess für XMPP-Benutzer</span><span class="sxs-lookup"><span data-stu-id="8c75a-132">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c75a-133">Phase</span><span class="sxs-lookup"><span data-stu-id="8c75a-133">Phase</span></span></th>
<th><span data-ttu-id="8c75a-134">Schritte</span><span class="sxs-lookup"><span data-stu-id="8c75a-134">Steps</span></span></th>
<th><span data-ttu-id="8c75a-135">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8c75a-135">Permissions</span></span></th>
<th><span data-ttu-id="8c75a-136">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="8c75a-136">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c75a-137">Bestimmen der Optionen, die der vorhandenen Edge-Bereitstellung hinzugefügt werden sollen</span><span class="sxs-lookup"><span data-stu-id="8c75a-137">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="8c75a-138">Führen Sie den Topologie-Generator aus, um die Edge-Server Einstellungen zu bearbeiten und die Topologie zu erstellen und zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="8c75a-138">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="8c75a-139">Durch Ihre vorhandene Edge-Topologie werden Änderungen vom zentralen Verwaltungsspeicher auf den Edgeserver repliziert.</span><span class="sxs-lookup"><span data-stu-id="8c75a-139">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="8c75a-140">Gruppe "Domänen-Admins" und RTCUniversalServerAdmins-Gruppe</span><span class="sxs-lookup"><span data-stu-id="8c75a-140">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="8c75a-141">Sie können eine Topologie mit einem Konto bearbeiten, das ein Mitglied der Gruppe "lokale Benutzer" ist, aber die Veröffentlichung einer Topologie erfordert ein Konto, das ein Mitglied der Gruppe "Domain Admins" und der Gruppe "RTCUniversalServerAdmins" ist.</span><span class="sxs-lookup"><span data-stu-id="8c75a-141">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="8c75a-142"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Erstellen einer Edge- und Director-Topologie in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8c75a-142"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c75a-143">Vorbereiten des Setups</span><span class="sxs-lookup"><span data-stu-id="8c75a-143">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8c75a-144">Stellen Sie sicher, dass die Systemvoraussetzungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="8c75a-144">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="8c75a-145">Konfigurieren interner und externer DNS-Einträge zur Unterstützung der öffentlichen Instant Messaging-Konnektivität, lync Federation und XMPP Federation</span><span class="sxs-lookup"><span data-stu-id="8c75a-145">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="8c75a-146">Konfigurieren von Ports und Protokollen in der Firewall zur Unterstützung der von Ihnen bereitgestellten Föderations Typen</span><span class="sxs-lookup"><span data-stu-id="8c75a-146">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="8c75a-147">Abrufen und installieren öffentlicher Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="8c75a-147">Obtain and install public certificates.</span></span> <span data-ttu-id="8c75a-148">Die zum Abrufen von Zertifikaten erforderliche Zeit hängt davon ab, welche Zertifizierungsstelle das Zertifikat ausgibt.</span><span class="sxs-lookup"><span data-stu-id="8c75a-148">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="8c75a-149">Dieser Schritt ist an diesem Punkt in der Bereitstellung optional.</span><span class="sxs-lookup"><span data-stu-id="8c75a-149">This step is optional at this point in the deployment.</span></span> <span data-ttu-id="8c75a-150">Wenn Sie diesen Schritt an diesem Punkt nicht ausführen, müssen Sie dies während der Edgeserver-Konfiguration tun.</span><span class="sxs-lookup"><span data-stu-id="8c75a-150">If you do not perform this step at this point, you must do it during Edge Server configuration.</span></span> <span data-ttu-id="8c75a-151">Der Edge-Server Dienst kann erst gestartet werden, nachdem Zertifikate abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="8c75a-151">The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8c75a-152">Entsprechend Ihrer Organisation, da diese Rollen in der Regel auf zahlreiche Arbeitsgruppen aufgeteilt sind</span><span class="sxs-lookup"><span data-stu-id="8c75a-152">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="8c75a-153"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planen von SIP, XMPP Federation und Public Instant Messaging in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8c75a-153"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c75a-154">Einrichten von Edgeserver für Verbundszenarien</span><span class="sxs-lookup"><span data-stu-id="8c75a-154">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8c75a-155">Transportieren der exportierten Topologie-Konfigurationsdatei auf jeden Edgeserver oder zulassen der vollständigen Replikation</span><span class="sxs-lookup"><span data-stu-id="8c75a-155">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="8c75a-156">Re-Run des Bereitstellungs-Assistenten, um unterstützende Komponenten für den Verbund zu installieren</span><span class="sxs-lookup"><span data-stu-id="8c75a-156">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="8c75a-157">Konfigurieren der Edgeserver</span><span class="sxs-lookup"><span data-stu-id="8c75a-157">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="8c75a-158">Anfordern und Installieren von Zertifikaten für jeden Edgeserver</span><span class="sxs-lookup"><span data-stu-id="8c75a-158">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="8c75a-159">Starten Sie die Edge-Server Dienste neu</span><span class="sxs-lookup"><span data-stu-id="8c75a-159">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8c75a-160">Gruppe "Administratoren"</span><span class="sxs-lookup"><span data-stu-id="8c75a-160">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="8c75a-161"><a href="lync-server-2013-setting-up-lync-federation.md">Einrichten eines Lync-Partnerverbunds in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8c75a-161"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="8c75a-162"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Einrichten der öffentlichen Chatkonnektivität in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8c75a-162"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="8c75a-163"><a href="lync-server-2013-setting-up-xmpp-federation.md">Einrichten eines XMPP-Partnerverbunds in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8c75a-163"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c75a-164">Konfigurieren Sie die Unterstützung für den Zugriff durch externe Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8c75a-164">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8c75a-165">Verwenden des externen Benutzerzugriffs in der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="8c75a-165">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="8c75a-166">Konfigurieren der Richtlinie für den externen Zugriff, um die Kommunikation mit Verbundbenutzern oder öffentlichen Benutzern zu ermöglichen</span><span class="sxs-lookup"><span data-stu-id="8c75a-166">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="8c75a-167">Konfigurieren von SIP-Verbunddomänen zum Zulassen oder Blockieren von Domänen</span><span class="sxs-lookup"><span data-stu-id="8c75a-167">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="8c75a-168">Aktivieren von SIP-Verbund Anbietern für öffentliche Instant Messaging-Verbindungsanbieter</span><span class="sxs-lookup"><span data-stu-id="8c75a-168">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="8c75a-169">Konfigurieren von XMPP-Verbundpartnern pro XMPP-Domäne</span><span class="sxs-lookup"><span data-stu-id="8c75a-169">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8c75a-170">RTCUniversalServerAdmins-Gruppe oder ein Benutzerkonto, das der CSAdministrator-Rolle zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="8c75a-170">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="8c75a-171"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Konfigurieren der Unterstützung für den externen Benutzerzugriff in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8c75a-171"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="8c75a-172"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Konfigurieren der Medienverschlüsselung für öffentliche Anbieter in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8c75a-172"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c75a-173">Überprüfen der Edgeserver-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8c75a-173">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="8c75a-174">Überprüfen der Serverkonnektivität und Replikation von Konfigurationsdaten von internen Servern</span><span class="sxs-lookup"><span data-stu-id="8c75a-174">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="8c75a-175">Zur Überprüfung der Replikation, der RTCUniversalServerAdmins-Gruppe oder des Benutzerkontos, das der CSAdministrator-Verb Verifizierung der Benutzerkonnektivität zugewiesen ist, wird ein Benutzer für jeden Typ von Verbundbenutzer</span><span class="sxs-lookup"><span data-stu-id="8c75a-175">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="8c75a-176"><a href="lync-server-2013-verifying-your-edge-deployment.md">Überprüfen der Edgebereitstellung in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8c75a-176"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="8c75a-177"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Beispiel für eine XMPP-Konfiguration in Lync Server 2013 – XMPP-Partnerverbund mit Google Talk</a></span><span class="sxs-lookup"><span data-stu-id="8c75a-177"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr><span data-ttu-id="8c75a-178">
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="8c75a-178">
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

