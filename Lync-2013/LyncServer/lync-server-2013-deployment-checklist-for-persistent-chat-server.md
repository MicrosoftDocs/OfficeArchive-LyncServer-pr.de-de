---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für den Server für beständigen Chat'
description: 'Lync Server 2013: Bereitstellungscheckliste für beständigen Chat Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d96da5e2961634e6a81450796e5d1ae3426819
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394619"
---
# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="c9e0b-103">Prüfliste zur Bereitstellung für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9e0b-103">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="c9e0b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="c9e0b-104">

<span> </span></span></span>

<span data-ttu-id="c9e0b-105">_**Letztes Änderungsdatum des Themas:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="c9e0b-105">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="c9e0b-106">Bereitstellung von lync Server 2013 erfordert der beständige Chat Server, dass Sie ihn in der richtigen Reihenfolge bereitstellen und alle erforderlichen Bereitstellungsschritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-106">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="c9e0b-107">Bereitstellungssequenz</span><span class="sxs-lookup"><span data-stu-id="c9e0b-107">Deployment Sequence</span></span>

<span data-ttu-id="c9e0b-108">Sie können beständigen Chat Server bereitstellen, nachdem Sie Ihre anfängliche Topologie bereitgestellt haben, einschließlich mindestens eines lync Server 2013, Front-End-Pools oder eines lync Server 2013, Standard Edition-Servers.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-108">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="c9e0b-109">In diesem Thema wird beschrieben, wie Sie den Server für beständigen Chat bereitstellen, indem Sie ihn einer vorhandenen Bereitstellung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-109">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="c9e0b-110">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="c9e0b-110">Deployment Process</span></span>

<span data-ttu-id="c9e0b-111">In der folgenden Tabelle sind die grundlegenden Schritte zum Bereitstellen des beständigen Chat Servers sowie Links für weitere Details aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-111">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="c9e0b-112">Bereitstellungsprozess für beständigen Chat Server</span><span class="sxs-lookup"><span data-stu-id="c9e0b-112">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9e0b-113">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="c9e0b-113">Task</span></span></th>
<th><span data-ttu-id="c9e0b-114">Schritte</span><span class="sxs-lookup"><span data-stu-id="c9e0b-114">Steps</span></span></th>
<th><span data-ttu-id="c9e0b-115">Erforderliche Rollen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="c9e0b-115">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="c9e0b-116">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c9e0b-116">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9e0b-117"><strong>Installieren der erforderlichen Hardware und Software</strong></span><span class="sxs-lookup"><span data-stu-id="c9e0b-117"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="c9e0b-118">Installieren Sie die folgenden Komponenten auf einem Hardwaresystem, das die Systemanforderungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="c9e0b-118">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c9e0b-119">Auf den beständigen Chat Server-Front-End-Servern:</span><span class="sxs-lookup"><span data-stu-id="c9e0b-119">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="c9e0b-120">Ein Betriebssystem, das die Systemanforderungen erfüllt</span><span class="sxs-lookup"><span data-stu-id="c9e0b-120">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="c9e0b-121">Software Voraussetzungen für Computer mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9e0b-121">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="c9e0b-122">SQL Server auf dem Server, auf dem die persistente Chat Server-Datenbank gehostet wird</span><span class="sxs-lookup"><span data-stu-id="c9e0b-122">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="c9e0b-123">Wenn die beständige Chat Server-Kompatibilität erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="c9e0b-123">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="c9e0b-124">SQL Server auf dem Server, auf dem die Compliance-Datenbank des beständigen Chat Servers gehostet wird</span><span class="sxs-lookup"><span data-stu-id="c9e0b-124">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c9e0b-125">Jeder Benutzer, der Mitglied der lokalen Gruppe „Administratoren“ ist.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-125">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="c9e0b-126"><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> in der Dokumentation zur Unterstützung</span><span class="sxs-lookup"><span data-stu-id="c9e0b-126"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="c9e0b-127"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Unterstützung für Server Software und-Infrastruktur in lync Server 2013</a> in der Dokumentation zur Unterstützung</span><span class="sxs-lookup"><span data-stu-id="c9e0b-127"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="c9e0b-128"><a href="lync-server-2013-determining-your-system-requirements.md">Ermitteln Ihrer Systemanforderungen für Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c9e0b-128"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="c9e0b-129"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technische Anforderungen für den Server für beständigen Chat in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c9e0b-129"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9e0b-130"><strong>Erstellen der geeigneten internen Topologie zur Unterstützung des beständigen Chat Servers (und optional die Compliance für beständigen Chat)</strong></span><span class="sxs-lookup"><span data-stu-id="c9e0b-130"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="c9e0b-131">Führen Sie den Topologie-Generator aus, um Ihrer Topologie einen beständigen Chat Server Pool hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="c9e0b-131">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="c9e0b-132">Hinzufügen von persistenten Chat Server-Komponenten zur Topologie</span><span class="sxs-lookup"><span data-stu-id="c9e0b-132">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="c9e0b-133">Erstellen einer SQL Server-Datenbank für den beständigen Chat Server Speicher (und ein Backup SQL Server für Disaster Recovery)</span><span class="sxs-lookup"><span data-stu-id="c9e0b-133">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="c9e0b-134">Definieren eines neuen lync-Dateispeichers oder Verwenden eines vorhandenen lync-Dateispeichers für persistente Chat Server Dateien</span><span class="sxs-lookup"><span data-stu-id="c9e0b-134">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="c9e0b-135">Zuordnen des lync Server 2013-Pools, der Anforderungen an diesen beständigen Chat Serverpool weiterleiten kann</span><span class="sxs-lookup"><span data-stu-id="c9e0b-135">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="c9e0b-136">Wenn die Kompatibilität für den beständigen Chat erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="c9e0b-136">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="c9e0b-137">Kompatibilitäts Speicher für beständigen Chat hinzufügen</span><span class="sxs-lookup"><span data-stu-id="c9e0b-137">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="c9e0b-138">Aktivieren Sie das Kontrollkästchen Definition des beständigen Chat Server Pools, um die Kompatibilität zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="c9e0b-138">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="c9e0b-139">Veröffentlichen der Topologie</span><span class="sxs-lookup"><span data-stu-id="c9e0b-139">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="c9e0b-140">Wenn Sie den Server für beständigen Chat auf Standard Edition installieren, muss der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Server Pools für beständigen Chat dem Standard Edition-Server entsprechen, und die SQL Server-Datenbanken sind auf dem Standard Edition-Server auf der SQL Server Express-Instanz zusammengefasst</span><span class="sxs-lookup"><span data-stu-id="c9e0b-140">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="c9e0b-141">Zum Definieren einer Topologie. Ein Konto, das Mitglieder der lokalen Gruppe „Benutzer“ ist.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-141">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="c9e0b-142">Um die Topologie zu veröffentlichen, muss ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist, und der Benutzer auch über die Berechtigung "Vollzugriff" (Lesen/Schreiben/ändern) im lync-Dateispeicher für persistente Chat Server Dateien verfügen (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann).</span><span class="sxs-lookup"><span data-stu-id="c9e0b-142">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="c9e0b-143"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigem Chat Server zu Ihrer Bereitstellung in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="c9e0b-143"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9e0b-144"><strong>Bereitstellen des Servers für beständigen Chat</strong></span><span class="sxs-lookup"><span data-stu-id="c9e0b-144"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="c9e0b-145">Führen Sie das lync Server-Setup auf allen Computern aus, auf denen der beständige Chat Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-145">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="c9e0b-146">Das Setup des beständigen Chat Servers ist in den lync Server 2013-Bereitstellungs-Assistenten integriert, in dem die folgenden Anweisungen enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="c9e0b-146">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="c9e0b-147">Den lokalen Verwaltungsspeicher bereitstellen</span><span class="sxs-lookup"><span data-stu-id="c9e0b-147">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="c9e0b-148">Installieren von beständigen Chat Server Diensten</span><span class="sxs-lookup"><span data-stu-id="c9e0b-148">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="c9e0b-149">Zertifikate anfordern und zuweisen</span><span class="sxs-lookup"><span data-stu-id="c9e0b-149">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="c9e0b-150">Dienste ausführen und starten</span><span class="sxs-lookup"><span data-stu-id="c9e0b-150">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c9e0b-151">Jeder Benutzer, der Mitglied der lokalen Gruppe „Administratoren“ ist.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-151">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="c9e0b-152"><a href="lync-server-2013-deploying-persistent-chat-server.md">Bereitstellen des beständigen Chat Servers in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="c9e0b-152"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9e0b-153"><strong>Erstellen eines Administrators für beständigen Chat</strong></span><span class="sxs-lookup"><span data-stu-id="c9e0b-153"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="c9e0b-154">Fügen Sie der Sicherheitsgruppe „CsPersistentChatAdministrator“ Benutzer hinzu.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-154">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="c9e0b-155">Jeder Benutzer, der Mitglied der Domänenadministratoren ist.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-155">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="c9e0b-156"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Hinzufügen eines Administrators für beständigen Chat in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="c9e0b-156"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9e0b-157"><strong>Konfigurieren des Server für beständigen Chat</strong></span><span class="sxs-lookup"><span data-stu-id="c9e0b-157"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="c9e0b-158">Konfigurieren von Benutzern:</span><span class="sxs-lookup"><span data-stu-id="c9e0b-158">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="c9e0b-159">Der Benutzer muss durch eine Richtlinie für den Zugriff auf beständigen Chat Server aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-159">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="c9e0b-160">Die Richtlinie ist standardmäßig für alle Benutzer deaktiviert und kann auf globaler, Standort-, Pool- und Benutzerebene definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-160">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="c9e0b-161">Einstellungen konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c9e0b-161">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c9e0b-p104">Der Benutzer muss Mitglied von „CsPersistentChatAdministrator“ sein. Benutzer müssen sich zum Ändern der Richtlinie mindestens in „CsUserAdministrator“ befinden.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-p104">User must be a member of CsPersistentChatAdministrator. To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="c9e0b-164"><a href="lync-server-2013-configuring-persistent-chat-server.md">Konfigurieren des beständigen Chat Servers in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="c9e0b-164"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="c9e0b-165">Sie können einen oder mehrere beständige Chat Server Pools bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-165">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="c9e0b-166">Wir unterstützen mehrere Server Pools für beständige Chats aus regulatorischen Gründen, wobei in einer bestimmten Region generierte Daten erforderlich sind, um in dieser Region zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-166">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="c9e0b-167">Wenn Sie beispielsweise einen Serverpool für beständigen Chat in Chicago und einen anderen in Zürich bereitstellen, um den Richtlinien für Daten in der Schweiz zu entsprechen, können Benutzer in den beständigen Chat Server Pools Verbindungen mit Chatrooms herstellen, vorausgesetzt, Sie haben Zugriff.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-167">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



<span data-ttu-id="c9e0b-168"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="c9e0b-168"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

