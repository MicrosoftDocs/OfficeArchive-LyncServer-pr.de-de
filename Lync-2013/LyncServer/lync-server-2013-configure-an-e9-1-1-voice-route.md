---
title: 'Lync Server 2013: Konfigurieren einer E9-1-1-VoIP-Route'
description: 'Lync Server 2013: Konfigurieren einer E9-1-1-VoIP-Route'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 869e9eaeb454943ccd877e90a21461c73065873e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49434144"
---
# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a><span data-ttu-id="2d748-103">Konfigurieren einer E9-1-1-VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d748-103">Configure an E9-1-1 voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="2d748-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="2d748-104">

<span> </span></span></span>

<span data-ttu-id="2d748-105">_**Letztes Änderungsdatum des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="2d748-105">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="2d748-106">Für die Bereitstellung von E9-1-1 müssen Sie zunächst eine VoIP-Route für Notrufe konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2d748-106">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="2d748-107">Details zum Erstellen von VoIP-Routen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="2d748-107">For details about creating voice routes, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span> <span data-ttu-id="2d748-108">Sie können auch mehrere Routen definieren, zum Beispiel wenn Ihre Bereitstellung einen primären und einen sekundären SIP-Trunk enthält.</span><span class="sxs-lookup"><span data-stu-id="2d748-108">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d748-109">Wenn Sie Standortinformationen in einen E9-1-1-INVITE-Befehl aufnehmen möchten, müssen Sie zunächst den SIP-Trunk konfigurieren, der zum Routen von Notrufen über das Gateway eine Verbindung mit dem E9-1-1-Dienstanbieter herstellt.</span><span class="sxs-lookup"><span data-stu-id="2d748-109">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="2d748-110">Legen Sie zu diesem Zweck im Cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> das Flag „EnablePIDFLOSupport“ auf „True“ fest.</span><span class="sxs-lookup"><span data-stu-id="2d748-110">To do this, set the EnablePIDFLOSupport flag on the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to True.</span></span> <span data-ttu-id="2d748-111">Der Standardwert für „EnablePIDFLOSupport“ lautet „False“.</span><span class="sxs-lookup"><span data-stu-id="2d748-111">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="2d748-112">Zum Beispiel: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span><span class="sxs-lookup"><span data-stu-id="2d748-112">For example: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span></span><BR><span data-ttu-id="2d748-113">Es ist nicht erforderlich, Empfangsstandorte für Ausweich-PSTN-Gateways und -ELIN-Gateways (Emergency Location Identification Number) zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2d748-113">It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>



</div>

<span data-ttu-id="2d748-114">Details zum Arbeiten mit VoIP-Routen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="2d748-114">For details about working with voice routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="2d748-115">**Set-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="2d748-115">**Set-CsPstnUsage**</span></span>

  - <span data-ttu-id="2d748-116">**Get-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="2d748-116">**Get-CsPstnUsage**</span></span>

  - <span data-ttu-id="2d748-117">**Neu – CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="2d748-117">**New-CsVoiceRoute**</span></span>

  - <span data-ttu-id="2d748-118">**Get-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="2d748-118">**Get-CsVoiceRoute**</span></span>

  - <span data-ttu-id="2d748-119">**Satz-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="2d748-119">**Set-CsVoiceRoute**</span></span>

  - <span data-ttu-id="2d748-120">**Remove-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="2d748-120">**Remove-CsVoiceRoute**</span></span>

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="2d748-121">So konfigurieren Sie eine E9-1-1-VoIP-Route</span><span class="sxs-lookup"><span data-stu-id="2d748-121">To configure an E9-1-1 voice route</span></span>

1.  <span data-ttu-id="2d748-122">Melden Sie sich mit einem Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsVoiceAdministrator“ ist, am Computer an.</span><span class="sxs-lookup"><span data-stu-id="2d748-122">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>

2.  <span data-ttu-id="2d748-123">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="2d748-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2d748-124">Führen Sie das folgende Cmdlet aus, um einen neuen PSTN-Verwendungsdatensatz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d748-124">Run the following cmdlet to create a new PSTN usage record.</span></span>
    
    <span data-ttu-id="2d748-125">Der Name muss dem Namen entsprechen, den Sie für die Einstellung **PSTN** in der Standortrichtlinie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="2d748-125">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="2d748-126">Obgleich Ihre Bereitstellung mehrere Telefonverwendungsdatensätze enthalten wird, fügt das folgende Beispiel der aktuellen Liste der verfügbaren PSTN-Verwendungen den Datensatz „Notfallverwendung“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="2d748-126">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="2d748-127">Ausführliche Informationen finden Sie unter [Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen, um die Anruffunktionen und-Berechtigungen in lync Server 2013 zu autorisieren](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="2d748-127">For details, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  <span data-ttu-id="2d748-128">Führen Sie das folgende Cmdlet aus, um eine neue VoIP-Route unter Verwendung des im vorherigen Schritte erstellten PSTN-Verwendungsdatensatzes zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d748-128">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="2d748-129">Das Nummernmuster muss dem Nummernmuster entsprechen, das in der Einstellung **Notrufwählzeichenfolge** in der Standortrichtlinie verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d748-129">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="2d748-130">Ein "+"-Zeichen ist erforderlich, da lync "+" zu Notrufen hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="2d748-130">A "+" sign is needed because Lync adds "+" to emergency calls.</span></span> <span data-ttu-id="2d748-131">„Co1-pstngateway-1“ ist die Dienst-ID des SIP-Trunks für den E9-1-1-Dienstanbieter oder für das ELIN-Gateway.</span><span class="sxs-lookup"><span data-stu-id="2d748-131">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="2d748-132">Im folgenden Beispiel wird für die VoIP-Route der Name „EmergencyRoute“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2d748-132">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  <span data-ttu-id="2d748-p105">Bei SIP-Trunkverbindungen wird optional die Ausführung des folgenden Cmdlets empfohlen, um eine lokale Route für Anrufe zu erstellen, die nicht über den SIP-Trunk des E9-1-1-Dienstanbieters verarbeitet werden. Diese Route wird verwendet, wenn die Verbindung zum E9-1-1-Dienstanbieter nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2d748-p105">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available.</span></span>
    
    <span data-ttu-id="2d748-135">Im folgenden Beispiel wird davon ausgegangen, dass der Benutzer in seiner VoIP-Richtlinie über die Verwendung „Local“ verfügt.</span><span class="sxs-lookup"><span data-stu-id="2d748-135">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

<span data-ttu-id="2d748-136"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="2d748-136"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

