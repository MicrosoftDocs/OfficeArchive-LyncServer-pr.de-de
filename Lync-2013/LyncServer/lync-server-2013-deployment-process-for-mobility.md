---
title: 'Lync Server 2013: Bereitstellungsprozess für Mobilität'
description: 'Lync Server 2013: Bereitstellungsprozess für Mobilität.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b49d69af899f6d9f2ac1db5040d017a9d62ce9eb
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394902"
---
# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="7a482-103">Bereitstellungsprozess für Mobilität in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a482-103">Deployment process for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="7a482-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="7a482-104">

<span> </span></span></span>

<span data-ttu-id="7a482-105">_**Letztes Änderungsdatum des Themas:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="7a482-105">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="7a482-106">In diesem Abschnitt werden die Schritte beschrieben, die für die Bereitstellung des lync Server 2013-Mobilitätsfeatures erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7a482-106">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="7a482-107">Mobilitäts Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="7a482-107">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a482-108">Phase</span><span class="sxs-lookup"><span data-stu-id="7a482-108">Phase</span></span></th>
<th><span data-ttu-id="7a482-109">Schritte</span><span class="sxs-lookup"><span data-stu-id="7a482-109">Steps</span></span></th>
<th><span data-ttu-id="7a482-110">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7a482-110">Permissions</span></span></th>
<th><span data-ttu-id="7a482-111">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="7a482-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a482-112">Erstellen von DNS-Einträgen (Domain Name System)</span><span class="sxs-lookup"><span data-stu-id="7a482-112">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7a482-113">Erstellen Sie einen internen DNS-CNAME-oder einen (Host-, wenn IPv6-, AAAA)-Eintrag, um die interne AutoErmittlungsdienst-URL aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="7a482-113">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="7a482-114">Erstellen Sie einen externen DNS-CNAME-oder einen (Host-, wenn IPv6-, AAAA)-Eintrag, um die URL des externen AutoErmittlungsdiensts aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="7a482-114">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7a482-115">Domänen-Admins</span><span class="sxs-lookup"><span data-stu-id="7a482-115">Domain Admins</span></span></p>
<p><span data-ttu-id="7a482-116">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="7a482-116">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="7a482-117"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Erstellen von DNS-Einträgen für den AutoErmittlungsdienst in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7a482-117"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a482-118">Ändern von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="7a482-118">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="7a482-119">Hinzufügen von Einträgen für Alternativen Betreff für die folgenden Zertifikate zur Unterstützung sicherer Verbindungen für mobile Benutzer:</span><span class="sxs-lookup"><span data-stu-id="7a482-119">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="7a482-120">Director-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="7a482-120">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="7a482-121">Front-End-Pool Zertifikat</span><span class="sxs-lookup"><span data-stu-id="7a482-121">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="7a482-122">Reverse-Proxy Zertifikat</span><span class="sxs-lookup"><span data-stu-id="7a482-122">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7a482-123">Lokaler Administrator</span><span class="sxs-lookup"><span data-stu-id="7a482-123">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="7a482-124"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Ändern der Zertifikate für Mobilität in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7a482-124"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a482-125">Konfigurieren des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="7a482-125">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7a482-126">Weisen Sie dem SSL-Listener (Secure Sockets Layer) Zertifikate zu, die mit alternativen Subjektnamen aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="7a482-126">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="7a482-127">Konfigurieren Sie die Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL neu.</span><span class="sxs-lookup"><span data-stu-id="7a482-127">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="7a482-128">Stellen Sie sicher, dass eine Webveröffentlichungsregel für die externe lync Server 2013-Webdienste-URL im Front-End-Pool vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7a482-128">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="7a482-129">Oder</span><span class="sxs-lookup"><span data-stu-id="7a482-129">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="7a482-130">Wenn Sie sich für die Verwendung von http für die ursprüngliche AutoErmittlungs-Anforderung entscheiden und die Listen Betreff alternativer Namen nicht auf den Zertifikaten aktualisieren, konfigurieren Sie eine neue Webveröffentlichungsregel, oder konfigurieren Sie eine vorhandene Veröffentlichungsregel für Port 80 http neu.</span><span class="sxs-lookup"><span data-stu-id="7a482-130">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7a482-131">Lokaler Administrator</span><span class="sxs-lookup"><span data-stu-id="7a482-131">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="7a482-132"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Konfigurieren des Reverseproxys für Mobilität in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7a482-132"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a482-133">Testen Ihrer Mobilitätsbereitstellung für lync 2010 Mobile mithilfe des MCX-mobilitätsdiensts</span><span class="sxs-lookup"><span data-stu-id="7a482-133">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="7a482-134">Führen Sie <strong>Test-CsMcxP2PIM</strong> aus, um das Senden einer Chatnachricht von einer Person an eine andere zu testen.</span><span class="sxs-lookup"><span data-stu-id="7a482-134">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="7a482-135">Eine vollständige Liste der Optionen finden Sie in der Dokumentation zum lync Server-Verwaltungsshell-Cmdlet für <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> .</span><span class="sxs-lookup"><span data-stu-id="7a482-135">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="7a482-136">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a482-136">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="7a482-137"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Überprüfen der Mobilitätsbereitstellung in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7a482-137"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a482-138">Testen Ihrer Mobilitätsbereitstellung für Mobile lync 2013-Clients mithilfe der UCWA-Webkomponenten</span><span class="sxs-lookup"><span data-stu-id="7a482-138">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="7a482-139">Verwenden Sie das Cmdlet <strong>Test-CsUcwaConference</strong> , um zu testen und zu überprüfen, ob vordefinierte Test Benutzer oder ein paar von tatsächlichen Benutzern UCWA zum Erstellen und teilnehmen an einer Konferenz verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7a482-139">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="7a482-140">Eine vollständige Liste der Optionen finden Sie in der Dokumentation zum lync Server-Verwaltungsshell-Cmdlet für <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> .</span><span class="sxs-lookup"><span data-stu-id="7a482-140">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="7a482-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a482-141">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="7a482-142"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Überprüfen der Mobilitätsbereitstellung in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7a482-142"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a482-143">Konfigurieren von Pushbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="7a482-143">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7a482-144">Bei lync Server 2013-Edgeserver fügen Sie einen lync Server Online-Hostinganbieter hinzu, und konfigurieren Sie den Hostinganbieter.</span><span class="sxs-lookup"><span data-stu-id="7a482-144">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="7a482-145">Bei lync Server 2010-Edgeserver fügen Sie einen lync Server Online-Hostinganbieter hinzu, und konfigurieren Sie den Hostinganbieter.</span><span class="sxs-lookup"><span data-stu-id="7a482-145">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="7a482-146">Fügen Sie für Office Communications Server 2007 R2-Edgeserver einen Verbundpartner hinzu.</span><span class="sxs-lookup"><span data-stu-id="7a482-146">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="7a482-147">Wenn Sie Push-Benachrichtigungen über ein Wi-Fi Netzwerk unterstützen möchten, konfigurieren Sie eine Firewall-Regel ausgehend für TCP-Port 5223.</span><span class="sxs-lookup"><span data-stu-id="7a482-147">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="7a482-148">Verwenden Sie das Cmdlet " <strong>Satz-CsPushNotificationConfiguration</strong> ", um Push-Benachrichtigungen für den Apple Push Notification Service (APNS) und den Microsoft Push Notification Service (MPNS) zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7a482-148">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="7a482-149">Dieses Feature ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7a482-149">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="7a482-150">Verwenden Sie das Cmdlet <strong>Test-CsFederatedPartner</strong> , um die Verbund Konfiguration und das <strong>Test-CsMCXPushNotification-</strong> Cmdlet zu testen, um Push-Benachrichtigungen zu testen.</span><span class="sxs-lookup"><span data-stu-id="7a482-150">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7a482-151">Push-Benachrichtigungen werden für Mobile lync 2010-Clients auf Apple-Geräten und Windows Phone verwendet</span><span class="sxs-lookup"><span data-stu-id="7a482-151">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="7a482-152">Für lync 2013 Mobile-Clients nur auf Windows Phone ist eine Push-Benachrichtigung erforderlich</span><span class="sxs-lookup"><span data-stu-id="7a482-152">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="7a482-153">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7a482-153">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="7a482-154"><a href="lync-server-2013-configuring-for-push-notifications.md">Konfigurieren von Pushbenachrichtigungen in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7a482-154"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a482-155">Konfigurieren von mobilitätsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7a482-155">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="7a482-156">Verwenden Sie das Cmdlet " <strong>Satz-CsMobilityPolicy</strong> ", um Folgendes zuzulassen oder zu verhindern:</span><span class="sxs-lookup"><span data-stu-id="7a482-156">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="7a482-157">Anruf über den Arbeitsplatz</span><span class="sxs-lookup"><span data-stu-id="7a482-157">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="7a482-158">Aktivieren von IP-Audio und IP-Video</span><span class="sxs-lookup"><span data-stu-id="7a482-158">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="7a482-159">WLAN für IP-Audio und/oder IP-Video erforderlich</span><span class="sxs-lookup"><span data-stu-id="7a482-159">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7a482-160">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a482-160">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="7a482-161"><a href="lync-server-2013-configuring-mobility-policy.md">Konfigurieren der Mobilitätsrichtlinie in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7a482-161"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr><span data-ttu-id="7a482-162">
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="7a482-162">
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</span></span></div>

