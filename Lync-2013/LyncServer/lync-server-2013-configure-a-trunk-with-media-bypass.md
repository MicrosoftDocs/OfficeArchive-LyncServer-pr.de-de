---
title: 'Lync Server 2013: Konfigurieren eines Trunks mit medienumgehung'
description: 'Lync Server 2013: Konfigurieren eines Trunks mit medienumgehung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51bd58a685e1f4c222a863c21022b3c9dc7c70d6
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49434167"
---
# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="e30d6-103">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e30d6-103">Configure a trunk with media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="e30d6-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="e30d6-104">

<span> </span></span></span>

<span data-ttu-id="e30d6-105">_**Letztes Änderungsdatum des Themas:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="e30d6-105">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="e30d6-106">Führen Sie die folgenden Schritte aus, um einen Trunk mit aktivierter Medienumgehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e30d6-106">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="e30d6-107">Informationen zum Konfigurieren eines Trunks mit deaktivierter medienumgehung finden Sie unter [Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="e30d6-107">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="e30d6-108">Die medienumgehung ist nützlich, wenn Sie die Anzahl der bereitgestellten Vermittlungsserver minimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e30d6-108">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="e30d6-109">In der Regel wird ein Vermittlungs Server Pool an einem zentralen Standort bereitgestellt, und er steuert Gateways an Zweigstellen.</span><span class="sxs-lookup"><span data-stu-id="e30d6-109">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="e30d6-110">Durch Aktivierung der Medienumgehung können Mediendaten für PSTN-Anrufe (Telefonfestnetz) von Clients an Zweigstellenstandorten direkt durch die Gateways an diesen Standorten geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e30d6-110">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="e30d6-111">Lync Server 2013-ausgehende Anrufrouten und Enterprise-VoIP-Richtlinien müssen ordnungsgemäß konfiguriert sein, damit PSTN-Anrufe von Clients an einem Zweigstellenstandort an das entsprechende Gateway weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e30d6-111">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="e30d6-112">Es wird dringend empfohlen, die Medienumgehung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e30d6-112">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="e30d6-113">Bevor Sie die Medienumgehung aber für einen SIP-Trunk aktivieren, müssen Sie sicherstellen, dass Ihr qualifizierter SIP-Trunkanbieter die Medienumgehung unterstützt und die Anforderungen für eine erfolgreiche Aktivierung des Szenarios erfüllt.</span><span class="sxs-lookup"><span data-stu-id="e30d6-113">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="e30d6-114">Insbesondere muss der Anbieter über die IP-Adressen der Server im internen Netzwerk Ihrer Organisation verfügen.</span><span class="sxs-lookup"><span data-stu-id="e30d6-114">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="e30d6-115">Wenn der Anbieter dieses Szenario nicht unterstützenkann, ist die medienumgehung nicht erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="e30d6-115">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="e30d6-116">Ausführliche Informationen finden Sie unter [Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e30d6-116">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e30d6-117">Die medienumgehung funktioniert nicht mit jedem PSTN-Gateway (Public Switched Telephone Network), IP-PBX und Session Border Controller (SBC).</span><span class="sxs-lookup"><span data-stu-id="e30d6-117">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="e30d6-118">Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="e30d6-118">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="e30d6-119">Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program – lync Server unter aufgeführt sind <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="e30d6-119">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="e30d6-p104">Eine Trunkkonfiguration wie die unten beschriebene gruppiert Parametersätze, die auf Trunks angewendet werden, denen die entsprechende Trunkkonfiguration zugewiesen ist. Eine bestimmte Trunkkonfiguration kann globale Reichweite haben (für alle Trunks, die keine spezifischere Standort- oder Poolkonfiguration haben) oder einen Standort oder Pool betreffen. Eine Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="e30d6-p104">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="e30d6-123">So konfigurieren Sie einen Trunk mit Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="e30d6-123">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="e30d6-124">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="e30d6-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e30d6-125">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e30d6-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e30d6-126">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e30d6-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e30d6-127">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e30d6-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e30d6-128">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-128">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="e30d6-129">Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e30d6-129">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="e30d6-130">Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e30d6-130">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="e30d6-131">Klicken Sie auf **Neu** und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:</span><span class="sxs-lookup"><span data-stu-id="e30d6-131">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="e30d6-132">**Website trunk:** Wählen Sie die Website für diese trunk-Konfiguration aus **Wählen Sie eine Website** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-132">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="e30d6-133">Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e30d6-133">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="e30d6-134">Diese Trunkkonfiguration wird auf alle Trunks am Standort angewendet.</span><span class="sxs-lookup"><span data-stu-id="e30d6-134">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="e30d6-135">**Pool trunk:** Wählen Sie den Namen des Trunks aus, für den diese trunk-Konfiguration gilt.</span><span class="sxs-lookup"><span data-stu-id="e30d6-135">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="e30d6-136">Dieser Stamm kann der Stamm Stamm oder alle zusätzlichen Trunks sein, die im Topologie-Generator definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e30d6-136">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="e30d6-137">Klicken Sie im Dialogfeld **Dienst auswählen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-137">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="e30d6-138">Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, wird der Trunk nicht im Dialogfeld **Dienst auswählen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e30d6-138">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e30d6-139">Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e30d6-139">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="e30d6-140">Das Feld <STRONG>Name</STRONG> ist bereits mit dem Namen des der Trunkkonfiguration zugeordneten Standorts oder Diensts ausgefüllt und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e30d6-140">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="e30d6-p109">Geben Sie in **Höchstzahl unterstützter Earlydialoge** einen Wert ein. Dies ist die maximale Anzahl von gegabelten Antworten auf an den Vermittlungsserver gesendete INVITE-Anforderungen, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) beim Dienstanbieter empfangen kann. Der Standardwert lautet 20.</span><span class="sxs-lookup"><span data-stu-id="e30d6-p109">Specify a value in **Maximum early dialogs supported**. This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server. The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e30d6-144">Bevor Sie diesen Wert ändern, setzen Sie sich mit Ihrem Dienstanbieter oder Gerätehersteller in Verbindung, um genaue Informationen zu den Funktionen Ihres Systems zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e30d6-144">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="e30d6-145">Wählen Sie unter **Unterstützte Verschlüsselungsstufe** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="e30d6-145">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="e30d6-146">**Erforderlich:** Die SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) muss verwendet werden, um den Datenverkehr zwischen dem Vermittlungs Server und dem Gateway oder der PBX (Private Branch Exchange) zu schützen.</span><span class="sxs-lookup"><span data-stu-id="e30d6-146">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="e30d6-147">**Optional:** Die SRTP-Verschlüsselung wird verwendet, wenn Sie vom Dienstanbieter oder Gerätehersteller unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="e30d6-147">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="e30d6-148">**Nicht unterstützt:** Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und wird daher nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e30d6-148">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="e30d6-149">Aktivieren Sie das Kontrollkästchen **Medienumgehung aktivieren**, wenn Sie eine Umgehung des Vermittlungsservers zur Verarbeitung durch den Trunkpeer wünschen.</span><span class="sxs-lookup"><span data-stu-id="e30d6-149">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e30d6-150">Damit die Medienumgehung ordnungsgemäß funktioniert, müssen das PSTN-Gateway, die IP-Nebenstellenanlage oder der SBC beim Dienstanbieter bestimmte Funktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e30d6-150">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="e30d6-151">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-media-bypass.md">Planen der medienumgehung in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e30d6-151">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="e30d6-p111">Aktivieren Sie das Kontrollkästchen **Zentralisierte Medienverarbeitung**, wenn ein bekannter Medienendpunkt vorhanden ist (beispielsweise ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse aufweist wie der signalgebende Endpunkt). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.</span><span class="sxs-lookup"><span data-stu-id="e30d6-p111">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="e30d6-154">Wenn der trunk-Peer das Empfangen von SIP-Refer-Anforderungen vom Vermittlungs Server unterstützt, aktivieren Sie das Kontrollkästchen **senden verweisen auf das Gateway** .</span><span class="sxs-lookup"><span data-stu-id="e30d6-154">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e30d6-155">Wenn Sie diese Option deaktivieren, während die Option <STRONG>Medienumgehung aktivieren</STRONG> ausgewählt ist, sind zusätzliche Einstellungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e30d6-155">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="e30d6-156">Wenn der Trunkpeer den Empfang von SIP REFER-Anforderungen vom Vermittlungsserver nicht unterstützt und die Medienumgehung aktiviert ist, müssen Sie außerdem das Cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> zur Deaktivierung von RTCP für aktive und gehaltene Anrufe ausführen, um geeignete Bedingungen für die Medienumgehung zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="e30d6-156">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="e30d6-157">Ausführliche Informationen finden Sie in der Dokumentation zur <A href="lync-server-2013-lync-server-management-shell.md">lync Server 2013-Verwaltungsshell</A> .</span><span class="sxs-lookup"><span data-stu-id="e30d6-157">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="e30d6-158">Alternativ können Sie <STRONG>Weiterleitung mithilfe von Drittanbieteranrufsteuerung aktivieren</STRONG> auswählen, wenn Sie möchten, dass für übertragene Anrufe eine Medienumgehung stattfinden soll, und das Gateway keine SIP REFER-Anforderungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e30d6-158">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="e30d6-159">(Optional) Für die Aktivierung der Weiterleitung zwischen Trunks ordnen Sie dieser Trunkkonfiguration PSTN-Verwendungsdatensätze zu und konfigurieren Sie diese.</span><span class="sxs-lookup"><span data-stu-id="e30d6-159">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="e30d6-160">Die PSTN-Nutzungen, die dieser trunk-Konfiguration zugeordnet sind, werden für alle eingehenden Anrufe über den trunk übernommen, der nicht von einem lync-Endpunkt stammt.</span><span class="sxs-lookup"><span data-stu-id="e30d6-160">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint.</span></span> <span data-ttu-id="e30d6-161">Für die Verwaltung der einer Trunkkonfiguration zugeordneten PSTN-Verwendungsdatensätze können Sie eines der folgenden Verfahren nutzen:</span><span class="sxs-lookup"><span data-stu-id="e30d6-161">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="e30d6-162">Wenn Sie einen oder mehrere Datensätze aus einer Liste aller für Ihre Enterprise-VoIP-Bereitstellung verfügbaren PSTN-Verwendungsdaten Sätze auswählen möchten, klicken Sie auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-162">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e30d6-163">Markieren Sie die Datensätze, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-163">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="e30d6-164">Markieren Sie einen Datensatz und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus der Trunkkonfiguration zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e30d6-164">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="e30d6-165">Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser Trunkkonfiguration zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="e30d6-165">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="e30d6-166">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-166">Click **New**.</span></span>
        
        2.  <span data-ttu-id="e30d6-167">Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz an.</span><span class="sxs-lookup"><span data-stu-id="e30d6-167">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="e30d6-p115">Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e30d6-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="e30d6-170">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungsdatensatz zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e30d6-170">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="e30d6-171">Wenn Sie eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung auswählen möchten, klicken Sie auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-171">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e30d6-172">Markieren Sie die Routen, die Sie dem PSTN-Verwendungsdatensatz zuordnen möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-172">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="e30d6-173">Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz wählen Sie die Route aus und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-173">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="e30d6-174">Zur Definition einer neuen Route und ihrer Zuordnung zu diesem PSTN-Verwendungsdatensatz klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-174">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="e30d6-175">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e30d6-175">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="e30d6-176">Zum Bearbeiten einer Route, die diesem PSTN-Verwendungsdatensatz zugeordnet wurde, wählen Sie die Route aus und klicken Sie auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-176">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="e30d6-177">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e30d6-177">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="e30d6-178">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-178">Click **OK**.</span></span>
    
      - <span data-ttu-id="e30d6-179">Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der dieser Trunkkonfiguration bereits zugeordnet ist:</span><span class="sxs-lookup"><span data-stu-id="e30d6-179">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="e30d6-180">Wählen Sie den PSTN-Verwendungsdatensatz aus, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-180">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="e30d6-181">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungsdatensatz zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e30d6-181">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="e30d6-182">Wenn Sie eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung auswählen möchten, klicken Sie auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-182">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e30d6-183">Markieren Sie die Routen, die Sie dem PSTN-Verwendungsdatensatz zuordnen möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-183">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="e30d6-184">Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz wählen Sie die Route aus und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-184">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="e30d6-185">Zur Definition einer neuen Route und ihrer Zuordnung zu diesem PSTN-Verwendungsdatensatz klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-185">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="e30d6-186">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e30d6-186">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="e30d6-187">Zum Bearbeiten einer Route, die diesem PSTN-Verwendungsdatensatz zugeordnet wurde, wählen Sie die Route aus und klicken Sie auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-187">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="e30d6-188">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e30d6-188">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="e30d6-189">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-189">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e30d6-190">Es ist wichtig, die PSTN-Verwendungsdaten Sätze entsprechend dem Mediation Server-Peer zuzuordnen, der dem zu konfigurierenden trunk zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e30d6-190">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="e30d6-191">Wenn es sich bei dem Vermittlungs Server-Peer um ein PSTN-Gateway oder einen Session Border Controller (SBC) handelt, wird dringend empfohlen, dass die trunk-Konfiguration keinem PSTN-Verwendungsdaten Satz zugeordnet ist, der zu einem PSTN-Ziel oder anderen Downstream-Systemen weitergeleitet wird, die über lync Server verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="e30d6-191">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="e30d6-p123">Ordnen Sie die PSTN-Verwendungsdatensätze zur Erzielung einer optimalen Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, wählen Sie den PSTN-Verwendungsdatensatz aus und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.</span><span class="sxs-lookup"><span data-stu-id="e30d6-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e30d6-194">Die Reihenfolge, in der PSTN-Verwendungsdatensätze in der Trunkkonfiguration aufgeführt werden, ist maßgeblich.</span><span class="sxs-lookup"><span data-stu-id="e30d6-194">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="e30d6-195">Lync Server durchläuft die Liste von oben nach unten.</span><span class="sxs-lookup"><span data-stu-id="e30d6-195">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="e30d6-196">Aktivieren Sie **RTP-Verriegelung aktivieren**, um Umgehungsmedien für Clients hinter einer NAT oder Firewall und einem SBC, der die Verriegelung unterstützt, zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e30d6-196">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="e30d6-197">**Aktivieren Sie das Weiterleitungs Anrufprotokoll** , um das Senden von Anrufverlaufs Informationen an den Gateway-Peer des Vermittlungsservers zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e30d6-197">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="e30d6-198">**Enable Forward p-asserted – Identitätsdaten** sollten ausgewählt werden, damit die p-asserted-Identity (Pai)-Anruf Absenderinformationen zwischen dem Vermittlungs Server und dem Gateway (und umgekehrt) weitergeleitet werden, wenn vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e30d6-198">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="e30d6-199">**Failovertimer für Ausgangsrouting aktivieren** sollte aktiviert sein, um ein schnelles Failover zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e30d6-199">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="e30d6-200">Das diesem Trunk zugeordnete Gateway kann innerhalb von zehn Sekunden eine Benachrichtigung ausgeben, dass ein ausgehender Anruf verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="e30d6-200">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="e30d6-201">Das erneute Routing zu einem anderen trunk erfolgt, wenn diese Benachrichtigung nicht vom Vermittlungs Server empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="e30d6-201">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="e30d6-202">In Netzwerken, in denen die Latenz die Antwortzeit möglicherweise verzögert oder in denen das Gateway für die Antwort mehr als zehn Sekunden benötigt, sollte das schnelle Failover deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e30d6-202">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="e30d6-203">(Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die wählende Nummer** für den Trunk.</span><span class="sxs-lookup"><span data-stu-id="e30d6-203">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="e30d6-204">Diese Übersetzungsregeln gelten für anrufende Nummern für ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="e30d6-204">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="e30d6-205">Wenn Sie eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auswählen möchten, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-205">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e30d6-206">Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-206">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="e30d6-207">Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e30d6-207">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="e30d6-208">Details zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e30d6-208">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="e30d6-209">Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e30d6-209">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="e30d6-210">Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e30d6-210">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="e30d6-211">Wenn Sie eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel verwenden möchten, klicken Sie auf den Regelnamen, auf **Kopieren** und anschließend auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-211">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="e30d6-212">Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="e30d6-212">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="e30d6-213">Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-213">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e30d6-214">Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.</span><span class="sxs-lookup"><span data-stu-id="e30d6-214">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="e30d6-p131">(Optional) Ordnen Sie **Übersetzungsregeln für die gewählte Nummer** für den Trunk zu und konfigurieren Sie diese. Die Übersetzungsregeln gelten für die angerufene Nummer in einem ausgehenden Anruf.</span><span class="sxs-lookup"><span data-stu-id="e30d6-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="e30d6-217">Wenn Sie eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auswählen möchten, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-217">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e30d6-218">Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-218">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="e30d6-219">Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e30d6-219">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="e30d6-220">Details zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e30d6-220">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="e30d6-221">Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e30d6-221">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="e30d6-222">Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e30d6-222">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="e30d6-223">Wenn Sie eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel verwenden möchten, klicken Sie auf den Regelnamen, auf **Kopieren** und anschließend auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-223">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="e30d6-224">Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="e30d6-224">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="e30d6-225">Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-225">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e30d6-226">Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.</span><span class="sxs-lookup"><span data-stu-id="e30d6-226">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="e30d6-p136">Stellen Sie sicher, dass die Übersetzungsregeln für den Trunk in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.</span><span class="sxs-lookup"><span data-stu-id="e30d6-p136">Make sure that the trunk’s translation rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e30d6-229">Lync Server 2013 durchläuft die Übersetzungsregel Liste von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht.</span><span class="sxs-lookup"><span data-stu-id="e30d6-229">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="e30d6-230">Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehreren Übersetzungsregeln übereinstimmen kann, müssen Sie sicherstellen, dass die stärker einschränkenden Regeln über den weniger einschränkenden Regeln angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e30d6-230">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="e30d6-231">Wenn Sie beispielsweise eine Übersetzungsregel verwenden, die mit einer beliebigen elfstelligen Nummer übereinstimmt, und eine andere Übersetzungsregel auf elfstellige Nummern zutrifft, die mit +1425 beginnen, muss die Regel für eine beliebige elfstellige Nummer <EM>unter</EM> der restriktiveren Regel platziert werden.</span><span class="sxs-lookup"><span data-stu-id="e30d6-231">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="e30d6-232">Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-232">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="e30d6-233">Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e30d6-233">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e30d6-234">Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e30d6-234">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="e30d6-235">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e30d6-235">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="e30d6-236">Nachdem Sie den trunk konfiguriert haben, fahren Sie mit dem Konfigurieren der medienumgehung fort, indem Sie zwischen globalen Medien Umgehungs Optionen wählen, wie unter [globale Medien Umgehungs Optionen in lync Server 2013](lync-server-2013-global-media-bypass-options.md) in der Bereitstellungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e30d6-236">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e30d6-237">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e30d6-237">See Also</span></span>


[<span data-ttu-id="e30d6-238">Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e30d6-238">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="e30d6-239">Konfigurieren der Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e30d6-239">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="e30d6-240">Globale Medien Umgehungs Optionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e30d6-240">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="e30d6-241">Definieren von Übersetzungsregeln in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e30d6-241">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

<span data-ttu-id="e30d6-242"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="e30d6-242"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

