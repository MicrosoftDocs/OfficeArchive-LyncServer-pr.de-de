---
title: (Optional) Aktivieren und Deaktivieren von Konferenzankündigungen beim Beitreten und Verlassen
description: Optional Aktivieren und Deaktivieren der Konferenzteilnahme und des Belassens von Ankündigungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70cd6b452a44d7d40f23d5ca96b6e4b7b063d2ec
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49445239"
---
# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="fb70a-103">(Optional) Aktivieren und Deaktivieren von Konferenzankündigungen beim Beitreten und Verlassen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb70a-103">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="fb70a-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="fb70a-104">

<span> </span></span></span>

<span data-ttu-id="fb70a-105">_**Letztes Änderungsdatum des Themas:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="fb70a-105">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="fb70a-106">Wenn Einwahlbenutzer an einer Konferenz teilnehmen oder Sie verlassen, kann die APP für Konferenz Ankündigungen deren ein-oder Ausstieg ankündigen, indem Sie einen Ton abspielen oder ihre Namen sagen.</span><span class="sxs-lookup"><span data-stu-id="fb70a-106">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="fb70a-107">Sie können ändern, wie Ankündigungen funktionieren, indem Sie Cmdlets ausführen.</span><span class="sxs-lookup"><span data-stu-id="fb70a-107">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="fb70a-108">Dieser Schritt ist optional.</span><span class="sxs-lookup"><span data-stu-id="fb70a-108">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="fb70a-109">So ändern Sie das Verhalten von Ankündigungen beim Beitreten oder Verlassen einer Konferenz</span><span class="sxs-lookup"><span data-stu-id="fb70a-109">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="fb70a-110">Melden Sie sich bei dem Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der Rolle **CS-ServerAdministrator** oder **CsAdministrator** an.</span><span class="sxs-lookup"><span data-stu-id="fb70a-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="fb70a-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="fb70a-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fb70a-112">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="fb70a-112">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="fb70a-113">Mit diesem Cmdlet werden Informationen darüber abgerufen, ob Teilnehmer ihren Namen beim beitreten zu einer Konferenz aufzeichnen müssen und wie lync Server antwortet, wenn Teilnehmer an einer Einwahlkonferenz teilnehmen oder diese hinterlassen.</span><span class="sxs-lookup"><span data-stu-id="fb70a-113">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="fb70a-114">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="fb70a-114">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="fb70a-115">**EnableNameRecording**   Bestimmt, ob anonyme Teilnehmer aufgefordert werden, Ihren Namen aufzuzeichnen, bevor Sie die Konferenz betreten.</span><span class="sxs-lookup"><span data-stu-id="fb70a-115">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="fb70a-116">Der Standardwert ist "$true", was bedeutet, dass anonyme Teilnehmer aufgefordert werden, Ihren Namen anzugeben, wenn Sie einer Konferenz beitreten.</span><span class="sxs-lookup"><span data-stu-id="fb70a-116">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="fb70a-117">(Authentifizierte Teilnehmer zeichnen ihren Namen nicht auf, da stattdessen der Anzeigename verwendet wird.)</span><span class="sxs-lookup"><span data-stu-id="fb70a-117">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="fb70a-118">**EntryExitAnnouncementsEnabledByDefault**   Gibt an, ob Ankündigungen standardmäßig aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="fb70a-118">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="fb70a-119">Der Standardwert ist "$false", was bedeutet, dass standardmäßig keine Ankündigungen vorhanden sind, wenn Teilnehmer an einer Konferenz teilnehmen oder eine Konferenz beenden.</span><span class="sxs-lookup"><span data-stu-id="fb70a-119">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="fb70a-120">Der Besprechungsorganisator kann diese Einstellung beim Planen einer Besprechung außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="fb70a-120">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="fb70a-121">**EntryExitAnnouncementsType**   Zeigt die Aktion an, die ausgeführt wird, wenn ein Teilnehmer eine Konferenz anschließt oder verlässt, für die Ankündigungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="fb70a-121">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="fb70a-122">Der Standardwert ist "UseNames", was bedeutet, dass eine Ankündigung ähnlich der folgenden lautet: "Ken Myers hat sich der Konferenz angeschlossen", wenn Ankündigungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="fb70a-122">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="fb70a-p105">Sie können diese Einstellungen auf globaler oder Standortebene konfigurieren. Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="fb70a-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="fb70a-125">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fb70a-125">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="fb70a-126">In diesem Beispiel werden die Einstellungen für den Website Bereich für Redmond konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="fb70a-126">In this example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="fb70a-127">Die Ankündigungsfunktion ist aktiviert, Teilnehmer müssen jedoch nicht ihren Namen sagen, wenn sie einer Konferenz beitreten.</span><span class="sxs-lookup"><span data-stu-id="fb70a-127">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="fb70a-128">Ein Signalton wird wiedergegeben, wenn Teilnehmer eine Konferenz betreten oder belegen.</span><span class="sxs-lookup"><span data-stu-id="fb70a-128">A tone is played when participants enter or leave a conference.</span></span>

<span data-ttu-id="fb70a-129"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="fb70a-129"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

