---
title: 'Lync Server 2013: Anzeigen von PSTN-Nutzungsdaten Sätzen'
description: 'Lync Server 2013: Anzeigen von PSTN-Nutzungsdaten Sätzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924ea74a4bb19b36da91bf97f51fbf4af54835a5
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49444091"
---
# <a name="view-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="09b09-103">Anzeigen von PSTN-Nutzungsdaten Sätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09b09-103">View PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="09b09-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="09b09-104">

<span> </span></span></span>

<span data-ttu-id="09b09-105">_**Letztes Änderungsdatum des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="09b09-105">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="09b09-106">Ein PSTN-Nutzungsdaten Satz (Public Switched Telephone Network) gibt eine Anruf Klasse (wie internes, lokales oder Ferngespräch) an, die von verschiedenen Benutzern oder Gruppen von Benutzern in einer Organisation vorgenommen werden kann.</span><span class="sxs-lookup"><span data-stu-id="09b09-106">A public switched telephone network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="09b09-107">Ausführliche Informationen finden Sie in der Planning-Dokumentation unter [PSTN-Verwendungsdaten Sätze in lync Server 2013](lync-server-2013-pstn-usage-records.md) .</span><span class="sxs-lookup"><span data-stu-id="09b09-107">For details, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) in the Planning documentation.</span></span>

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a><span data-ttu-id="09b09-108">So zeigen Sie einen PSTN-Verwendungs Eintrag mithilfe der lync Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="09b09-108">To view a PSTN usage record by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="09b09-109">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="09b09-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="09b09-110">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="09b09-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="09b09-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="09b09-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="09b09-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="09b09-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="09b09-113">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **PSTN-Verwendung**.</span><span class="sxs-lookup"><span data-stu-id="09b09-113">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

4.  <span data-ttu-id="09b09-114">Markieren Sie auf der Seite **PSTN-Verwendung** den PSTN-Verwendungsdatensatz, den Sie anzeigen möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="09b09-114">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="09b09-115">Auf einer schreibgeschützten Seite des ausgewählten PSTN-Verwendungsdatensatzes werden die zugehörigen Routen und VoIP-Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="09b09-115">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="09b09-116">Anzeigen von Informationen zur PSTN-Nutzung mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="09b09-116">Viewing PSTN Usage Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="09b09-117">Sie können PSTN-Nutzungen auch mithilfe von Windows PowerShell und dem Cmdlet **Get-CsPstnUsage** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="09b09-117">You can also view PSTN usages by using Windows PowerShell and the **Get-CsPstnUsage** cmdlet.</span></span> <span data-ttu-id="09b09-118">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="09b09-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="09b09-119">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="09b09-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="09b09-120">So zeigen Sie die Informationen zur PSTN-Nutzung mithilfe von Windows PowerShell-Cmdlets an</span><span class="sxs-lookup"><span data-stu-id="09b09-120">To view PSTN usage information by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="09b09-121">Wenn Sie Informationen zu allen PSTN-Verwendungen anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="09b09-121">To view information about all of your PSTN usages, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsPstnUsage
    
    <span data-ttu-id="09b09-122">Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="09b09-122">This command returns information similar to the following:</span></span>
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

<span data-ttu-id="09b09-123">Ausführliche Informationen finden Sie unter [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span><span class="sxs-lookup"><span data-stu-id="09b09-123">For details, see [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="09b09-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09b09-124">See Also</span></span>


[<span data-ttu-id="09b09-125">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09b09-125">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="09b09-126">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09b09-126">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

<span data-ttu-id="09b09-127"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="09b09-127"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

