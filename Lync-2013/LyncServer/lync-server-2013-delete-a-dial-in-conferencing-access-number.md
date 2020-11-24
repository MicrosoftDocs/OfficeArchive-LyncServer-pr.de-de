---
title: 'Lync Server 2013: Löschen einer Zugriffsnummer für Einwahlkonferenzen'
description: 'Lync Server 2013: Löschen einer Zugriffsnummer für Einwahlkonferenzen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa5bed6099f7464884c3bcde8e4ee86ad4207222
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49395106"
---
# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="774bb-103">Löschen einer Zugriffsnummer für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="774bb-103">Delete a dial-in conferencing access number in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="774bb-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="774bb-104">

<span> </span></span></span>

<span data-ttu-id="774bb-105">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="774bb-105">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="774bb-106">Führen Sie die folgenden Schritte aus, um eine Zugriffsnummer für Einwahlkonferenzen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="774bb-106">Follow these steps to delete a dial-in conferencing access number.</span></span>

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="774bb-107">So löschen Sie eine Zugriffsnummer für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="774bb-107">To delete a dial-in conferencing access number</span></span>

1.  <span data-ttu-id="774bb-108">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="774bb-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="774bb-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="774bb-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="774bb-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="774bb-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="774bb-111">Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.</span><span class="sxs-lookup"><span data-stu-id="774bb-111">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="774bb-112">Klicken Sie auf der Seite auf die Einwahlnummer, die Sie aus der Liste löschen möchten, dann auf **Bearbeiten** und schließlich auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="774bb-112">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="774bb-113">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="774bb-113">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="774bb-114">Entfernen von Einwahlkonferenz-Zugriffsnummern mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="774bb-114">Removing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="774bb-115">Zugriffsnummern für Einwahlkonferenzen können mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsDialInConferencingAccessNumber** gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="774bb-115">Dial-in conferencing access numbers can be deleted by using Windows PowerShell and the **Remove-CsDialInConferencingAccessNumber** cmdlet.</span></span> <span data-ttu-id="774bb-116">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="774bb-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="774bb-117">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="774bb-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a><span data-ttu-id="774bb-118">So entfernen Sie eine bestimmte Zugriffsnummer für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="774bb-118">To remove a specific dial-in conferencing access number</span></span>

  - <span data-ttu-id="774bb-119">Dieser Befehl löscht die Zugriffsnummer für Einwahlkonferenzen mit Identity SIP:RedmondDialInAccess@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="774bb-119">This command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a><span data-ttu-id="774bb-120">So entfernen Sie alle Zugriffsnummern für Einwahlkonferenzen, die einem bestimmten Bereich zugewiesen sind</span><span class="sxs-lookup"><span data-stu-id="774bb-120">To remove all the dial-in conferencing access numbers assigned to a specific region</span></span>

  - <span data-ttu-id="774bb-121">Dieser Befehl löscht alle Zugriffsnummern für Einwahlkonferenzen, die mit der Nordwest-Region verbunden sind:</span><span class="sxs-lookup"><span data-stu-id="774bb-121">This command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a><span data-ttu-id="774bb-122">So entfernen Sie Zugriffsnummern für Einwahlkonferenzen basierend auf der primären Sprache</span><span class="sxs-lookup"><span data-stu-id="774bb-122">To remove dial-in conferencing access numbers based on primary language</span></span>

  - <span data-ttu-id="774bb-123">Dieser Befehl löscht alle Einwahlkonferenz-Zugriffsnummern, wobei Italienisch die primäre Sprache ist:</span><span class="sxs-lookup"><span data-stu-id="774bb-123">This command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

<span data-ttu-id="774bb-124">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .</span><span class="sxs-lookup"><span data-stu-id="774bb-124">For more information, see the help topic for the [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet.</span></span>

<span data-ttu-id="774bb-125"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="774bb-125"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

