---
title: 'Lync Server 2013: Anzeigen von clientversionsrichtlinien Regeln'
description: 'Lync Server 2013: Anzeigen von clientversionsrichtlinien Regeln.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e04075f136d53fe149c6b0655699324a99e0a52
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49443398"
---
# <a name="view-client-version-policy-rules-in-lync-server-2013"></a><span data-ttu-id="146f4-103">Anzeigen von clientversionsrichtlinien Regeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="146f4-103">View client version policy rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="146f4-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="146f4-104">

<span> </span></span></span>

<span data-ttu-id="146f4-105">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="146f4-105">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="146f4-106">Eine clientversionsrichtlinie besteht aus einer Reihe von clientversionsrichtlinien Regeln.</span><span class="sxs-lookup"><span data-stu-id="146f4-106">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="146f4-107">Mit diesen Regeln werden die Aktionen definiert, die ausgeführt werden sollen, wenn Benutzer sich mit bestimmten Clients und Clientversionen anmelden möchten.</span><span class="sxs-lookup"><span data-stu-id="146f4-107">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="146f4-108">Sie können clientversionsrichtlinien Regeln in der lync Server 2013-Systemsteuerung oder in der lync Server 2013-Verwaltungsshell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="146f4-108">You can view client version policy rules from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="146f4-109">So zeigen Sie clientversionsrichtlinien Regeln mithilfe der lync Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="146f4-109">To view client version policy rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="146f4-110">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="146f4-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="146f4-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="146f4-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="146f4-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="146f4-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="146f4-113">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Schaltfläche für die **Client Versionsrichtlinien** -Navigation.</span><span class="sxs-lookup"><span data-stu-id="146f4-113">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="146f4-114">Doppelklicken Sie auf der Seite **clientversionsrichtlinie** auf eine clientversionsrichtlinie, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="146f4-114">On the **Client Version Policy** page, double-click a client version policy you want to view.</span></span>

5.  <span data-ttu-id="146f4-115">Die Regeln werden auf der Seite **Richtlinie zum Bearbeiten der Client Version** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="146f4-115">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="146f4-116">Wenn Sie die Details einer Regel anzeigen möchten, wählen Sie die Regel aus, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="146f4-116">To view the details for a rule, select the rule, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="146f4-117">Anzeigen von Client Versionsrichtlinien Regeln mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="146f4-117">Viewing Client Version Policy Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="146f4-118">Sie können clientversionsrichtlinien Regeln mithilfe der lync Server-Verwaltungsshell und dem Cmdlet **Get-CsClientVersionPolicyRule** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="146f4-118">You can view client version policy rules by using Lync Server Management Shell and the **Get-CsClientVersionPolicyRule** cmdlet.</span></span> <span data-ttu-id="146f4-119">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="146f4-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="146f4-120">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="146f4-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-policy-rules"></a><span data-ttu-id="146f4-121">So zeigen Sie clientversionsrichtlinien Regeln an</span><span class="sxs-lookup"><span data-stu-id="146f4-121">To view client version policy rules</span></span>

  - <span data-ttu-id="146f4-122">Geben Sie zum Anzeigen der clientversionsrichtlinien Regeln in der lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="146f4-122">To view the client version policy rules, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionPolicyRule
    
    <span data-ttu-id="146f4-123">Damit werden für jede konfigurierte Regel ähnliche Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="146f4-123">That will return information similar to this for each configured rule:</span></span>
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

<span data-ttu-id="146f4-124">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) .</span><span class="sxs-lookup"><span data-stu-id="146f4-124">For details, see the help topic for the [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet.</span></span>

<span data-ttu-id="146f4-125"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="146f4-125"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

