---
title: 'Lync Server 2013: Zuweisen einer benutzerbezogenen Wähl Plan Richtlinie'
description: 'Lync Server 2013: Zuweisen einer benutzerseitigen Wähl Plan Richtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 654c1f15ccb1efa4d1aa35d957df7a2654fa41d7
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49443202"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="bf773-103">Zuweisen einer benutzerseitigen Wähl Plan Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf773-103">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="bf773-104">Um die Konfiguration des Benutzerkontos für Benutzer von Enterprise-VoIP oder Benutzer von Einwahlkonferenzen abzuschließen, muss dem Benutzer ein Wählplan zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="bf773-104">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="bf773-105">Benutzerkonten verwenden automatisch den globalen Wählplan oder, falls vorhanden, den Wählplan auf Websiteebene, wenn Sie nicht explizit einen vorhandenen Wählplan für einzelne Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bf773-105">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="bf773-106">Wenn Sie den Global-oder Website-Wählplan für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen.</span><span class="sxs-lookup"><span data-stu-id="bf773-106">If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="bf773-107">So weisen Sie mithilfe der lync Server 2013-Systemsteuerung einen Wählplan zu</span><span class="sxs-lookup"><span data-stu-id="bf773-107">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="bf773-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="bf773-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bf773-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bf773-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bf773-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bf773-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bf773-111">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="bf773-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="bf773-112">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="bf773-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="bf773-113">Klicken Sie in der Tabelle auf das Benutzerkonto, dem Sie einen Wählplan zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="bf773-113">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="bf773-114">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="bf773-114">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="bf773-115">Klicken Sie auf der Seite **lync Server-Benutzer bearbeiten** unter **Telefonie** auf **Enterprise-VoIP**.</span><span class="sxs-lookup"><span data-stu-id="bf773-115">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="bf773-116">Klicken Sie auf **Wähl Plan Richtlinie**, und wählen Sie dann den gewünschten Wählplan aus.</span><span class="sxs-lookup"><span data-stu-id="bf773-116">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="bf773-117">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bf773-117">Click **Commit**.</span></span>

<span data-ttu-id="bf773-118">Details zum Konfigurieren von Wählplänen finden Sie im Thema [Konfigurieren von Wählplänen in lync Server 2013](lync-server-2013-configuring-dial-plans.md) .</span><span class="sxs-lookup"><span data-stu-id="bf773-118">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bf773-119">Zuweisen einer Per-User Wähleinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="bf773-119">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bf773-120">Sie können Wählpläne für einzelne Benutzer mit Windows PowerShell und dem Cmdlet **Grant-CsdialPlan** zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bf773-120">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="bf773-121">Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="bf773-121">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bf773-122">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="bf773-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="bf773-123">So weisen Sie einem einzelnen Benutzer einen benutzerbasierten Wählplan zu</span><span class="sxs-lookup"><span data-stu-id="bf773-123">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="bf773-124">Mit dem folgenden Befehl wird dem Benutzer Ken Myers der benutzerspezifische Wählplan redmonddialplan "zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="bf773-124">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="bf773-125">So weisen Sie mehreren Benutzern einen benutzerbasierten Wählplan zu</span><span class="sxs-lookup"><span data-stu-id="bf773-125">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="bf773-126">Dieser Befehl weist allen Benutzern, die in Redmond arbeiten, den benutzerseitigen Wähl Plan redmonddialplan "zu.</span><span class="sxs-lookup"><span data-stu-id="bf773-126">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="bf773-127">Weitere Informationen zu dem in diesem Befehl verwendeten LdapFilter-Parameter finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="bf773-127">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="bf773-128">So heben Sie die Zuweisung eines benutzerbasierten Wählplans auf</span><span class="sxs-lookup"><span data-stu-id="bf773-128">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="bf773-129">Mit dem folgenden Befehl werden alle benutzerseitigen Wähleinstellungen, die Ken Myers zuvor zugewiesen wurden, aufheben.</span><span class="sxs-lookup"><span data-stu-id="bf773-129">The following command unassigns any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="bf773-130">Nachdem der benutzerspezifische Wählplan nicht zugewiesen wurde, wird Ken Myers automatisch mithilfe des globalen Wählplans, seines Orts Wähl Plans (sofern vorhanden) oder des Dienstbereichs-Wählplans verwaltet, der seiner Registrierungsstelle oder einem PSTN-Gateway zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="bf773-130">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="bf773-131">Ein Dienstbereichs-Wählplan hat Vorrang vor jedem Website Wählplan, und ein Website Wählplan hat Vorrang vor dem globalen Wählplan.</span><span class="sxs-lookup"><span data-stu-id="bf773-131">A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="bf773-132">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="bf773-132">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf773-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf773-133">See Also</span></span>


[<span data-ttu-id="bf773-134">Konfigurieren von Wählplänen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf773-134">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="bf773-135">Für lync Server 2013 aktivierte Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="bf773-135">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

