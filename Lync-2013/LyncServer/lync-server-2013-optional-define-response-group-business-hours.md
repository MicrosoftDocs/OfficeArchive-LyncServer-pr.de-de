---
title: 'Lync Server 2013: (optional) definieren der Geschäftszeiten der Reaktionsgruppe'
description: 'Lync Server 2013: (optional) definieren Sie die Geschäftszeiten der Reaktionsgruppe.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group business hours
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205291(v=OCS.15)
ms:contentKeyID: 48185504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5780ee362ff11fc4b6fe2ccf8f119f35d0bee36
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49445277"
---
# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a><span data-ttu-id="d1dcd-103">Optional Definieren der Geschäftszeiten der Reaktionsgruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1dcd-103">(Optional) Define Response Group business hours in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="d1dcd-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="d1dcd-104">

<span> </span></span></span>

<span data-ttu-id="d1dcd-105">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d1dcd-105">_**Topic Last Modified:** 2012-11-01_</span></span>

<div>

## <a name="defining-business-hours"></a><span data-ttu-id="d1dcd-106">Definieren von Geschäftszeiten</span><span class="sxs-lookup"><span data-stu-id="d1dcd-106">Defining Business Hours</span></span>

<span data-ttu-id="d1dcd-107">Mit der Einstellung der Geschäftszeiten wird definiert, wann der Workflow zur Anrufbeantwortung zur Verfügung steht und es werden die Aktionen angegeben, die für Anrufe außerhalb der Geschäftszeiten ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d1dcd-107">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="d1dcd-108">Reaktionsgruppenadministratoren können mit dem **New-CsRgsHoursOfBusiness**-Cmdlet vordefinierte Zeitpläne erstellen, die Sie für eine beliebige Anzahl von Reaktionsgruppen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d1dcd-108">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d1dcd-109">Beim Erstellen oder Ändern eines Workflows können Sie einen benutzerdefinierten Zeitplan angeben, der nur für diesen Workflow gilt.</span><span class="sxs-lookup"><span data-stu-id="d1dcd-109">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="d1dcd-110">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">erstellen oder Ändern eines Sammel Arbeits Workflows in lync Server 2013</A> oder <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">erstellen oder Ändern eines interaktiven Workflows in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d1dcd-110">For details, see <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Create or modify a hunt group workflow in Lync Server 2013</A> or <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">Create or modify an interactive workflow in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d1dcd-111">Wenn ein Workflow als verwalteter Workflow definiert wird, kann jeder Benutzer, dem die Rolle CsResponseGroupManager zugewiesen ist, benutzerdefinierte Geschäftszeiten für die von ihnen verwalteten Workflows festlegen und ändern.</span><span class="sxs-lookup"><span data-stu-id="d1dcd-111">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d1dcd-112">Verwenden Sie das 24-Stunden-Format für die Parameter in den folgenden Cmdlets (z. B. 20:00=8:00 Uhr abends).</span><span class="sxs-lookup"><span data-stu-id="d1dcd-112">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span>



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="d1dcd-113">So erstellen Sie eine vordefinierte Geschäftszeitenauflistung</span><span class="sxs-lookup"><span data-stu-id="d1dcd-113">To create a predefined business hours collection</span></span>

1.  <span data-ttu-id="d1dcd-114">Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d1dcd-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="d1dcd-115">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d1dcd-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d1dcd-116">Führen Sie für jeden einzelnen Stundenbereich, den Sie definieren möchten, folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d1dcd-116">For each unique range of hours you want to define, run:</span></span>
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    <span data-ttu-id="d1dcd-117">Führen Sie zum Erstellen der Geschäftszeitenauflistung, welche die definierten Bereiche verwendet, folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d1dcd-117">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    <span data-ttu-id="d1dcd-p103">Im folgenden Beispiel werden für Werktage die Geschäftszeiten von 9:00 Uhr bis 17:00 Uhr, für Samstage von 8:00 Uhr bis 10:00 Uhr und von 14:00 Uhr bis 18:00 Uhr und für Sonntage keine Geschäftszeiten festgelegt:</span><span class="sxs-lookup"><span data-stu-id="d1dcd-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1dcd-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1dcd-125">See Also</span></span>


[<span data-ttu-id="d1dcd-126">Erstellen oder Ändern eines Sammel Ansuchen-Workflows in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1dcd-126">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="d1dcd-127">Erstellen oder Ändern eines interaktiven Workflows in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1dcd-127">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="d1dcd-128">Neu – CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="d1dcd-128">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[<span data-ttu-id="d1dcd-129">Neu – CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="d1dcd-129">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

<span data-ttu-id="d1dcd-130"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="d1dcd-130"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

