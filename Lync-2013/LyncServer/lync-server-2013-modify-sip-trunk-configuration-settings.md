---
title: 'Lync Server 2013: Ändern der SIP-Trunk-Konfigurationseinstellungen'
description: 'Lync Server 2013: Ändern der SIP-Trunk-Konfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42cb213211a11494a96b5a762734a2b5db49dfbb
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425451"
---
# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="6badc-103">Ändern der SIP-Trunk-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6badc-103">Modify SIP trunk configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="6badc-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="6badc-104">

<span> </span></span></span>

<span data-ttu-id="6badc-105">_**Letztes Änderungsdatum des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="6badc-105">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="6badc-106">SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="6badc-106">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="6badc-107">Diese Einstellungen geben unter anderem Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="6badc-107">These settings do such things as specify:</span></span>

  - <span data-ttu-id="6badc-108">Ob Medienumgehung für die Trunks aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6badc-108">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="6badc-109">Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="6badc-109">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="6badc-110">Ob die SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden trunk erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="6badc-110">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="6badc-111">Wenn Sie Microsoft lync Server 2013 installieren, wird eine globale Sammlung von SIP-Trunk-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="6badc-111">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="6badc-112">Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).</span><span class="sxs-lookup"><span data-stu-id="6badc-112">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="6badc-113">Eine dieser Auflistungen kann später entweder mithilfe der lync Server-Systemsteuerung oder Windows PowerShell geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6badc-113">Any of these collections can later be modified using either Lync Server Control Panel or Windows PowerShell.</span></span>

<span data-ttu-id="6badc-114">Wenn Sie die SIP-Trunk-Konfigurationseinstellungen mithilfe der lync Server-Systemsteuerung ändern, stehen Ihnen die folgenden Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="6badc-114">When modifying SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6badc-115">Benutzeroberflächeneinstellung</span><span class="sxs-lookup"><span data-stu-id="6badc-115">UI Setting</span></span></th>
<th><span data-ttu-id="6badc-116">PowerShell-Parameter</span><span class="sxs-lookup"><span data-stu-id="6badc-116">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="6badc-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6badc-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6badc-118">Name</span><span class="sxs-lookup"><span data-stu-id="6badc-118">Name</span></span></p></td>
<td><p><span data-ttu-id="6badc-119">Identität</span><span class="sxs-lookup"><span data-stu-id="6badc-119">Identity</span></span></p></td>
<td><p><span data-ttu-id="6badc-p103">Eindeutige ID für die Sammlung. Diese Eigenschaft ist schreibgeschützt. Sie können die Identität einer Sammlung von Trunkkonfigurationseinstellungen nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="6badc-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6badc-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6badc-122">Description</span></span></p></td>
<td><p><span data-ttu-id="6badc-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6badc-123">Description</span></span></p></td>
<td><p><span data-ttu-id="6badc-124">Bietet Administratoren eine Möglichkeit, zusätzliche Informationen zu den Einstellungen zu speichern (z. B. Zweck der Trunkkonfiguration).</span><span class="sxs-lookup"><span data-stu-id="6badc-124">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6badc-125">Maximal unterstützte frühe Dialoge</span><span class="sxs-lookup"><span data-stu-id="6badc-125">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="6badc-126">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="6badc-126">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="6badc-127">Die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) des Dienstanbieters auf an den Vermittlungsserver gesendete Einladungen empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="6badc-127">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6badc-128">Unterstützte Verschlüsselungsstufe</span><span class="sxs-lookup"><span data-stu-id="6badc-128">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="6badc-129">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="6badc-129">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="6badc-130">Legt den Umfang der Unterstützung zum Schutz von Mediendatenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway, der IP-Nebenstellenanlage oder dem SBC (Session Border Controller) des Dienstanbieters fest.</span><span class="sxs-lookup"><span data-stu-id="6badc-130">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="6badc-131">Bei der Medienumgehung muss dieser Wert mit der Einstellung „EncryptionLevel“ in der Medienkonfiguration kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="6badc-131">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="6badc-132">Die Medienkonfiguration wird mithilfe der Cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> und <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">CsMediaConfiguration</a> gesetzt.</span><span class="sxs-lookup"><span data-stu-id="6badc-132">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="6badc-133">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="6badc-133">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6badc-134">Erforderlich: Die SRTP-Verschlüsselung muss verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6badc-134">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="6badc-135">Optional: SRTP wird verwendet, wenn es vom Gateway unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6badc-135">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="6badc-136">Nicht unterstützt: Die SRTP-Verschlüsselung wird nicht unterstützt und daher auch nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="6badc-136">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="6badc-p105">„SRTPMode“ wird nur verwendet, wenn das Gateway zur Verwendung von TLS (Transport Layer Security) konfiguriert ist. Wenn das Gateway mit dem Transportprotokoll TCP (Transmission Control Protocol) konfiguriert ist, wird „SRTPMode“ intern auf „Nicht unterstützt“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6badc-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6badc-139">Support melden</span><span class="sxs-lookup"><span data-stu-id="6badc-139">Refer support</span></span></p></td>
<td><p><span data-ttu-id="6badc-140">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="6badc-140">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="6badc-141">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="6badc-141">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="6badc-142">Mit der Einstellung <strong>Senden der Weiterleitung an Gateway aktivieren</strong> unterstützt der Trunk den Empfang von Weiterleitungsanforderungen vom Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="6badc-142">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="6badc-143">Mit der Einstellung <strong>Weiterleitung mithilfe von Drittanbieteranrufsteuerung aktivieren</strong> kann das 3pcc-Protokoll verwendet werden, damit weitergeleitete Anrufe den gehosteten Standort umgehen können.</span><span class="sxs-lookup"><span data-stu-id="6badc-143">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="6badc-144">3PCC wird auch als &quot; Steuerung von Drittanbietern bezeichnet &quot; und tritt auf, wenn eine Drittpartei verwendet wird, um ein paar von Anrufern zu verbinden (beispielsweise einen Operator, der einen Anruf von Person a an Person B anlegt).</span><span class="sxs-lookup"><span data-stu-id="6badc-144">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6badc-145">Medienumgehung aktivieren</span><span class="sxs-lookup"><span data-stu-id="6badc-145">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="6badc-146">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="6badc-146">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="6badc-p107">Gibt an, ob die Medienumgehung für diesen Trunk aktiviert ist. Die Medienumgehung kann nur aktiviert werden, wenn auch <strong>Zentralisierte Medienverarbeitung</strong> aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6badc-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6badc-149">Zentralisierte Medienverarbeitung</span><span class="sxs-lookup"><span data-stu-id="6badc-149">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="6badc-150">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="6badc-150">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="6badc-p108">Gibt an, ob ein bekannter Medienendpunkt vorhanden ist. (Ein Beispiel für einen bekannten Medienendpunkt ist ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse hat wie der Signaldatenverkehrendpunkt.)</span><span class="sxs-lookup"><span data-stu-id="6badc-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6badc-153">RTP-Verriegelung aktivieren</span><span class="sxs-lookup"><span data-stu-id="6badc-153">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="6badc-154">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="6badc-154">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="6badc-p109">Gibt an, ob SIP-Trunks die RTP-Verriegelung unterstützen oder nicht. Die RTP-Verriegelung ist eine Technologie, die RTP-/RTCP-Verbindungen über NAT (Network Address Translator, Netzwerkadressenübersetzung) oder eine Firewall ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="6badc-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6badc-157">Weiterleitung der Anrufliste aktivieren</span><span class="sxs-lookup"><span data-stu-id="6badc-157">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="6badc-158">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="6badc-158">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="6badc-159">Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="6badc-159">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6badc-160">Weiterleitung von P-Asserted-Identity-Daten aktivieren</span><span class="sxs-lookup"><span data-stu-id="6badc-160">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="6badc-161">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="6badc-161">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="6badc-p110">Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6badc-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6badc-164">Failovertimer für Ausgangsrouting aktivieren</span><span class="sxs-lookup"><span data-stu-id="6badc-164">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="6badc-165">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="6badc-165">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="6badc-p111">Gibt an, ob ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden, an den nächsten verfügbaren Trunk weitergeleitet werden. Wenn keine weiteren Trunks verfügbar sind, wird der Anruf automatisch beendet. In einer Organisation mit langsamen Netzwerk- und Gatewayreaktionen könnte dies dazu führen, dass Anrufe unnötigerweise beendet werden.</span><span class="sxs-lookup"><span data-stu-id="6badc-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6badc-168">Zugeordnete PSTN-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="6badc-168">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="6badc-169">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="6badc-169">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="6badc-170">Dem Trunk zugewiesene Auflistung von PSTN-Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="6badc-170">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6badc-171">Übersetzte Nummer zum Testen</span><span class="sxs-lookup"><span data-stu-id="6badc-171">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="6badc-172">-</span><span class="sxs-lookup"><span data-stu-id="6badc-172">N/A</span></span></p></td>
<td><p><span data-ttu-id="6badc-173">Eine Telefonnummer, die für Ad-hoc-Tests der Trunkkonfigurationseinstellungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6badc-173">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6badc-174">Zugehörige Übersetzungsregeln</span><span class="sxs-lookup"><span data-stu-id="6badc-174">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="6badc-175">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="6badc-175">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="6badc-176">Sammlung an Regeln für die Telefonnummernübersetzung für Anrufe, die per Ausgangsrouting verarbeitet werden (Anrufe, die an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weitergeleitet werden).</span><span class="sxs-lookup"><span data-stu-id="6badc-176">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6badc-177">Übersetzungsregeln für die gewählte Nummer</span><span class="sxs-lookup"><span data-stu-id="6badc-177">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="6badc-178">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="6badc-178">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="6badc-179">Dem Trunk zugewiesene Auflistung von ausgehenden Übersetzungsregeln für Telefonnummern.</span><span class="sxs-lookup"><span data-stu-id="6badc-179">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6badc-180">Testtelefonnummer</span><span class="sxs-lookup"><span data-stu-id="6badc-180">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="6badc-181">-</span><span class="sxs-lookup"><span data-stu-id="6badc-181">N/A</span></span></p></td>
<td><p><span data-ttu-id="6badc-182">Eine Telefonnummer, die für Ad-hoc-Tests der Übersetzungsregeln verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6badc-182">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6badc-183">Anrufende Nummer</span><span class="sxs-lookup"><span data-stu-id="6badc-183">Calling number</span></span></p></td>
<td><p><span data-ttu-id="6badc-184">-</span><span class="sxs-lookup"><span data-stu-id="6badc-184">N/A</span></span></p></td>
<td><p><span data-ttu-id="6badc-185">Gibt an, dass die zu testende Telefonnummer die Telefonnummer des Anrufers ist.</span><span class="sxs-lookup"><span data-stu-id="6badc-185">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6badc-186">Angerufene Nummer</span><span class="sxs-lookup"><span data-stu-id="6badc-186">Called number</span></span></p></td>
<td><p><span data-ttu-id="6badc-187">-</span><span class="sxs-lookup"><span data-stu-id="6badc-187">N/A</span></span></p></td>
<td><p><span data-ttu-id="6badc-188">Gibt an, dass die zu testende Telefonnummer die Telefonnummer der Person ist, die angerufen wird.</span><span class="sxs-lookup"><span data-stu-id="6badc-188">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="6badc-189">Die lync Server CsTrunkConfiguration-Cmdlets unterstützen zusätzliche Eigenschaften, die in der lync Server-Systemsteuerung nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6badc-189">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="6badc-190">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Satz-CsTrunkConfiguration</A> ".</span><span class="sxs-lookup"><span data-stu-id="6badc-190">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="6badc-191">So ändern Sie die SIP-Trunk-Konfigurationseinstellungen mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="6badc-191">To modify SIP trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6badc-192">Klicken Sie in der lync Server-Systemsteuerung auf **VoIP-Routing**, und klicken Sie dann auf **trunk-Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6badc-192">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="6badc-p113">Doppelklicken Sie auf der Registerkarte **Trunkkonfiguration** auf die Trunkkonfigurationseinstellungen, die Sie ändern möchten. Beachten Sie, dass Sie immer nur eine Einstellung bearbeiten können. Wenn Sie die gleichen Änderungen an mehreren Sammlungen vornehmen möchten, verwenden Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6badc-p113">On the **Trunk Configuration** tab, double-click the trunk configuration settings to be modified. Note that you can only edit one collection of settings at a time. If you would like to make the same changes on multiple collections, use Windows PowerShell instead.</span></span>

3.  <span data-ttu-id="6badc-196">Nehmen Sie im Dialogfeld **Trunkkonfiguration bearbeiten** die gewünschten Einstellungen vor und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6badc-196">In the **Edit Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

4.  <span data-ttu-id="6badc-p114">Die Eigenschaft **State** für die Sammlung wird als **Commit nicht ausgeführt** angezeigt. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6badc-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

5.  <span data-ttu-id="6badc-199">Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6badc-199">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="6badc-200">Klicken Sie im Dialogfeld **Microsoft lync Server 2013-System** Steuerung auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6badc-200">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

<span data-ttu-id="6badc-201"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="6badc-201"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

