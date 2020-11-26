---
title: 'Lync Server 2013: Konfigurieren der Mobilitätsrichtlinie'
description: 'Lync Server 2013: Konfigurieren der Mobilitätsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbbf7f9db54c8436f2db24d593dbd7a1372d5e00
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49432919"
---
# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="efff2-103">Konfigurieren der Mobilitätsrichtlinie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efff2-103">Configuring mobility policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="efff2-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="efff2-104">

<span> </span></span></span>

<span data-ttu-id="efff2-105">_**Letztes Änderungsdatum des Themas:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="efff2-105">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="efff2-106">Lync Server 2013 bietet mobilitätsrichtlinien, die bestimmen, wer Mobilitätsfunktionen nutzen, über Arbeit anrufen, VoIP (Voice over IP) oder Video verwenden kann und ob WLAN für VoIP oder Video erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="efff2-106">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="efff2-107">Mit der Funktion Anruf über Arbeit kann ein Mobilfunknutzer Anrufe auf einem Mobiltelefon tätigen und empfangen, indem er eine geschäftliche Telefonnummer anstelle der Mobiltelefonnummer verwendet.</span><span class="sxs-lookup"><span data-stu-id="efff2-107">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="efff2-108">Dieses Feature verhindert, dass der angerufene die Handynummer des Anrufers sieht und es einem Benutzer ermöglicht, ausgehende Gebühren zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="efff2-108">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="efff2-109">Die Konfiguration von VoIP und Video ermöglicht es Benutzern, VoIP-Anrufe und Videos zu empfangen und zu führen.</span><span class="sxs-lookup"><span data-stu-id="efff2-109">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="efff2-110">Einstellungen für die WLAN-Nutzung definieren, ob das Gerät eines Benutzers ein WLAN-Netzwerk über ein Mobilfunknetz verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="efff2-110">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="efff2-111">Standardmäßig sind Mobilität, Anruf über die Arbeit und die VoIP-und Videofunktionen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="efff2-111">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="efff2-112">Die Einstellungen für WLAN für VoIP und Video sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="efff2-112">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="efff2-113">Administratoren können ermitteln, wer Zugriff auf diese Features hat, indem Sie ein Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="efff2-113">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="efff2-114">Sie können Optionen Global, nach Website oder nach Benutzer deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="efff2-114">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="efff2-115">Um Mobilitätsfunktionen nutzen und über die Arbeit anrufen zu können, müssen die Benutzer die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="efff2-115">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="efff2-116">Benutzer müssen für lync Server 2013 aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="efff2-116">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="efff2-117">Benutzer müssen für Enterprise-VoIP aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="efff2-117">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="efff2-118">Benutzern muss eine Mobilitätsrichtlinie zugewiesen werden, bei der die **EnableMobility** -Option auf "true" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="efff2-118">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="efff2-119">Damit Benutzer den Anruf über die Arbeit nutzen können, müssen Sie die beiden folgenden zusätzlichen Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="efff2-119">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="efff2-120">Benutzern muss eine VoIP-Richtlinie zugewiesen sein, für die die Option **gleichzeitiges Anrufen von Telefonen aktivieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="efff2-120">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="efff2-121">Benutzern muss eine Mobilitätsrichtlinie zugewiesen werden, bei der die **EnableOutsideVoice** -Option auf "true" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="efff2-121">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="efff2-122">Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können Ihre mobilen Geräte verwenden, um lync zu lync-VoIP-Anrufen (Voice over IP) zu machen oder an Konferenzen teilzunehmen, indem Sie auf Ihren mobilen Geräten über den Link zum teilnehmen klicken, wenn Sie diesen Benutzern die entsprechenden Optionen für VoIP-Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="efff2-122">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="efff2-123">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-defining-your-mobility-requirements.md">Definieren Ihrer Mobilitätsanforderungen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="efff2-123">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="efff2-124">Details zum Aktivieren von Benutzern für lync Server 2013 finden Sie unter [deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="efff2-124">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="efff2-125">Details zum Aktivieren von Benutzern für Enterprise-VoIP finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="efff2-125">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="efff2-126">Details zum Festlegen von VoIP-Richtlinienoptionen finden Sie unter [Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="efff2-126">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="efff2-127">So ändern Sie die globale Mobilitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="efff2-127">To modify global mobility policy</span></span>

1.  <span data-ttu-id="efff2-128">Melden Sie sich bei einem beliebigen Computer an, auf dem die lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.</span><span class="sxs-lookup"><span data-stu-id="efff2-128">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="efff2-129">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="efff2-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="efff2-130">Deaktivieren Sie den Zugriff auf Mobilität, und rufen Sie über die Arbeit weltweit an.</span><span class="sxs-lookup"><span data-stu-id="efff2-130">Turn off access to mobility and Call via Work globally.</span></span> <span data-ttu-id="efff2-131">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="efff2-131">At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="efff2-132">Sie können den Anruf über die Arbeit ausschalten, ohne den Zugriff auf Mobilität zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="efff2-132">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="efff2-133">Sie können die Mobilität jedoch nicht deaktivieren, ohne dass Sie den Anruf über die Arbeit abschalten.</span><span class="sxs-lookup"><span data-stu-id="efff2-133">However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="efff2-134">So ändern Sie die mobilitätsrichtlinien nach Website</span><span class="sxs-lookup"><span data-stu-id="efff2-134">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="efff2-135">Melden Sie sich bei einem beliebigen Computer an, auf dem die lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.</span><span class="sxs-lookup"><span data-stu-id="efff2-135">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="efff2-136">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="efff2-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="efff2-137">Erstellen Sie eine Richtlinie auf Websiteebene, und deaktivieren Sie VoIP und Video, und aktivieren Sie WLAN für IP-Audio und für IP-Video nach Website anfordern.</span><span class="sxs-lookup"><span data-stu-id="efff2-137">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="efff2-138">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="efff2-138">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="efff2-139">So ändern Sie die mobilitätsrichtlinien nach Benutzern</span><span class="sxs-lookup"><span data-stu-id="efff2-139">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="efff2-140">Melden Sie sich bei einem beliebigen Computer an, auf dem die lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.</span><span class="sxs-lookup"><span data-stu-id="efff2-140">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="efff2-141">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="efff2-141">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="efff2-142">Erstellen Sie mobilitätsrichtlinien auf Benutzerebene, deaktivieren Sie Mobilität, und rufen Sie Sie über die Arbeit des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="efff2-142">Create user level mobility policies and turn off mobility and Call via Work by user.</span></span> <span data-ttu-id="efff2-143">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="efff2-143">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="efff2-144">Sie können den Anruf über die Arbeit ausschalten, ohne den Zugriff auf Mobilität zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="efff2-144">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="efff2-145">Sie können die Mobilität jedoch nicht deaktivieren, ohne dass Sie den Anruf über die Arbeit abschalten.</span><span class="sxs-lookup"><span data-stu-id="efff2-145">However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="efff2-146">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="efff2-146">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="efff2-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efff2-147">See Also</span></span>


[<span data-ttu-id="efff2-148">Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efff2-148">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="efff2-149">Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efff2-149">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="efff2-150">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efff2-150">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="efff2-151">Definieren der Mobilitätsanforderungen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efff2-151">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="efff2-152">New-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="efff2-152">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="efff2-153">Set-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="efff2-153">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="efff2-154">Get-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="efff2-154">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="efff2-155">Grant-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="efff2-155">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="efff2-156">Remove-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="efff2-156">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

<span data-ttu-id="efff2-157"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="efff2-157"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

