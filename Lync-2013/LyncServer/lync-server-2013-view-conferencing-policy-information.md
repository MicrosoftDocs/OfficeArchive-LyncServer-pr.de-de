---
title: 'Lync Server 2013: Anzeigen von Konferenzrichtlinien Informationen'
description: 'Lync Server 2013: Anzeigen von Konferenzrichtlinien Informationen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e463c500e48f4032c8dab3a3787715f7265be9c
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49438652"
---
# <a name="view-conferencing-policy-information-in-lync-server-2013"></a><span data-ttu-id="a1202-103">Anzeigen von Konferenzrichtlinien Informationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1202-103">View conferencing policy information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="a1202-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="a1202-104">

<span> </span></span></span>

<span data-ttu-id="a1202-105">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a1202-105">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a1202-106">In der lync Server 2013-Systemsteuerung verwenden Sie Konferenzrichtlinien, um zu steuern, wie Konferenzen in Ihrer Bereitstellung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="a1202-106">In Lync Server 2013 Control Panel, you use conferencing policies to control how conferencing is implemented in your deployment.</span></span> <span data-ttu-id="a1202-107">Dazu gehören die folgenden Konferenzrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="a1202-107">This includes the following conferencing policies:</span></span>

  - <span data-ttu-id="a1202-108">Eine globale Richtlinie, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a1202-108">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="a1202-109">Optionale Richtlinie auf Website-und Benutzerebene, die Sie erstellen und verwenden können, um anzugeben, wie Konferenzen für bestimmte Websites oder Benutzer implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="a1202-109">Optional site-level and user-level policy that you can create and use to specify how conferencing is implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-conferencing-policy-settings"></a><span data-ttu-id="a1202-110">So zeigen Sie konferenzrichtlinieneinstellungen an</span><span class="sxs-lookup"><span data-stu-id="a1202-110">To view conferencing policy settings</span></span>

1.  <span data-ttu-id="a1202-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a1202-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a1202-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a1202-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a1202-113">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a1202-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a1202-114">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** , und klicken Sie dann auf **konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="a1202-114">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="a1202-115">Doppelklicken Sie auf der Seite **Konferenzrichtlinie** auf die Konferenzrichtlinie, die angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1202-115">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>

5.  <span data-ttu-id="a1202-116">Wählen Sie im **Filter Datei bearbeiten** die Option **Details anzeigen aus.**</span><span class="sxs-lookup"><span data-stu-id="a1202-116">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="a1202-117">Aktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="a1202-117">check box.</span></span>
    
    <span data-ttu-id="a1202-118">**Bearbeiten von Konferenzrichtlinien \<policy\> –** Öffnet die Anzeige der Einstellungen für die ausgewählte Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="a1202-118">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="a1202-119">Details zum Konfigurieren der Einstellungen finden Sie unter [erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="a1202-119">For details about configuring the settings, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a1202-120">Anzeigen von Konferenzrichtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a1202-120">Viewing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a1202-121">Konferenzrichtlinien können mithilfe von Windows PowerShell und dem Cmdlet Get-CsConferencingPolicy angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a1202-121">Conferencing policies can be viewed by using Windows PowerShell and the Get-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="a1202-122">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a1202-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a1202-123">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="a1202-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-conferencing-policies"></a><span data-ttu-id="a1202-124">So zeigen Sie Konferenzrichtlinien an</span><span class="sxs-lookup"><span data-stu-id="a1202-124">To view conferencing policies</span></span>

  - <span data-ttu-id="a1202-125">Wenn Sie Informationen zu allen Konferenzrichtlinien anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="a1202-125">To view information about all your conferencing policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="a1202-126">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="a1202-126">That will return information similar to this:</span></span>
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

</div>

<span data-ttu-id="a1202-127">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="a1202-127">For more information, see the help topic for the [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) cmdlet.</span></span>

<span data-ttu-id="a1202-128"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="a1202-128"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

