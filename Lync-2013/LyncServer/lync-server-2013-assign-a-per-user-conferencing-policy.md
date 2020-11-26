---
title: 'Lync Server 2013: Zuweisen einer konferenzrichtlinie für einzelne Benutzer'
description: 'Lync Server 2013: weisen Sie eine konferenzrichtlinie für einzelne Benutzer zu.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 819d1431a2a7a921ff8c306c47c8b5f86bf5d5bb
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49440514"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="df997-103">Zuweisen einer pro-Benutzer-konferenzrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df997-103">Assign a per-user conferencing policy in Lync Server 2013</span></span>

 


<span data-ttu-id="df997-104">Die konferenzrichtlinie ist eine der individuellen Einstellungen eines Benutzerkontos, das Sie in der lync Server-Systemsteuerung konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="df997-104">The conferencing policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel.</span></span>

<span data-ttu-id="df997-105">Die Bereitstellung einer oder mehrerer pro-Benutzer-Konferenzrichtlinien ist optional.</span><span class="sxs-lookup"><span data-stu-id="df997-105">Deploying one or more per-user conferencing policies is optional.</span></span> <span data-ttu-id="df997-106">Sie können auch nur eine konferenzrichtlinie auf globaler Ebene oder Konferenzrichtlinien auf Websiteebene bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="df997-106">You can also deploy only a global-level conferencing policy or site-level conferencing policy.</span></span> <span data-ttu-id="df997-107">Wenn Sie Richtlinien für einzelne Benutzer bereitstellen, müssen Sie diese explizit Benutzern, Gruppen oder Kontaktobjekten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="df997-107">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span> <span data-ttu-id="df997-108">Conferencing-Benutzerrechte und-Berechtigungen werden automatisch auf die in der konferenzrichtlinie auf globaler Ebene definierten Standardeinstellungen angewendet, wenn keine spezifische Richtlinie für Website-oder Benutzerberechtigungen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="df997-108">Conferencing user rights and permissions automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="df997-109">Nachdem Sie mindestens eine konferenzrichtlinie für einzelne Benutzer erstellt haben, verwenden Sie die Verfahren in diesem Thema, um die Richtlinie zuzuweisen, die die Benutzerrechte und-Berechtigungen angibt, die der Server den von einem bestimmten Benutzer organisierten Besprechungen erteilen soll.</span><span class="sxs-lookup"><span data-stu-id="df997-109">After creating at least one per-user conferencing policy, use the procedures in this topic to assign the policy that specifies the user rights and permissions that you want the server to grant to the meetings organized by a particular user.</span></span>

<span data-ttu-id="df997-110">Eine Liste aller verfügbaren konferenzrichtlinieneinstellungen finden Sie unter [Konferenzrichtlinien Einstellungsreferenz für lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="df997-110">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<span data-ttu-id="df997-111">Details zum Erstellen von Konferenzrichtlinien finden Sie unter [erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="df997-111">For details about creating conferencing policies, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy"></a><span data-ttu-id="df997-112">So weisen Sie eine konferenzrichtlinie für einzelne Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="df997-112">To assign a per-user conferencing policy</span></span>

1.  <span data-ttu-id="df997-113">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="df997-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="df997-114">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="df997-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="df997-115">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="df997-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="df997-116">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="df997-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="df997-117">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="df997-117">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="df997-118">Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="df997-118">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="df997-119">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="df997-119">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="df997-120">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="df997-120">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="df997-121">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="df997-121">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="df997-122">Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="df997-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="df997-123">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="df997-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="df997-124">Geben Sie je nach gewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein oder klicken Sie auf den Pfeil in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="df997-124">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="df997-125">Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="df997-125">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="df997-126">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="df997-126">Click **Find**.</span></span>

6.  <span data-ttu-id="df997-127">Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **Richtlinien zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="df997-127">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="df997-128">Wenn dieselbe konferenzrichtlinie für einzelne Benutzer für mehrere Benutzer gelten soll, wählen Sie in den Suchergebnissen mehrere Benutzer aus, klicken Sie dann auf <STRONG>Aktionen</STRONG>, und klicken Sie dann auf <STRONG>Richtlinien zuweisen</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="df997-128">If you want the same per-user conferencing policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="df997-129">Führen Sie in **Richtlinien zuweisen** unter **konferenzrichtlinie** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="df997-129">In **Assign Policies**, under **Conferencing policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="df997-130">Da es mehrere Richtlinien gibt, die Sie unter <STRONG>Zuweisen von Richtlinien</STRONG>konfigurieren können, ist für jede Richtlinie im Dialogfeld standardmäßig <STRONG> &lt; &gt; beibehalten</STRONG> aktiviert.</span><span class="sxs-lookup"><span data-stu-id="df997-130">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="df997-131">Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="df997-131">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="df997-132">Wählen Sie aus **\<Automatic\>** , um zu ermöglichen, dass lync Server 2013 automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Websiteebene wählt.</span><span class="sxs-lookup"><span data-stu-id="df997-132">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="df997-133">Klicken Sie auf den Namen einer benutzerdefinierten konferenzrichtlinie, die Sie zuvor auf der Seite **konferenzrichtlinie** definiert haben.</span><span class="sxs-lookup"><span data-stu-id="df997-133">Click the name of a per-user conferencing policy you previously defined on the **Conferencing Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="df997-134">Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="df997-134">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="df997-135">Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="df997-135">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="df997-136">Zuweisen einer Per-User konferenzrichtlinie mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="df997-136">Assigning a Per-User Conferencing Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="df997-137">Benutzerspezifische Konferenzrichtlinien können mithilfe von Windows PowerShell und dem Grant-CsConferencingPolicy-Cmdlet zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="df997-137">Per-user conferencing policies can be assigned by using Windows PowerShell and the Grant-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="df997-138">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="df997-138">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="df997-139">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="df997-139">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a><span data-ttu-id="df997-140">So weisen Sie einem einzelnen Benutzer eine konferenzrichtlinie für einzelne Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="df997-140">To assign a per-user conferencing policy to a single user</span></span>

  - <span data-ttu-id="df997-141">Mit dem folgenden Befehl wird die benutzerspezifische Konferenzrichtlinien-RedmondConferencingPolicy dem Benutzer Ken Myers zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="df997-141">The following command assigns the per-user conferencing policy RedmondConferencingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a><span data-ttu-id="df997-142">So weisen Sie mehreren Benutzern eine konferenzrichtlinie für einzelne Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="df997-142">To assign a per-user conferencing policy to multiple users</span></span>

  - <span data-ttu-id="df997-143">Dieser Befehl weist allen Benutzern, die für die Personalabteilung arbeiten, die Richtlinien für die benutzerspezifische Konferenz HRConferencingPolicy zu.</span><span class="sxs-lookup"><span data-stu-id="df997-143">This command assigns the per-user conferencing policy HRConferencingPolicy to all the users who work for the Human Resources department.</span></span> <span data-ttu-id="df997-144">Weitere Informationen zu dem in diesem Befehl verwendeten LdapFilter-Parameter finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="df997-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a><span data-ttu-id="df997-145">So heben Sie die Zuweisung einer konferenzrichtlinie für einzelne Benutzer auf</span><span class="sxs-lookup"><span data-stu-id="df997-145">To unassign a per-user conferencing policy</span></span>

  - <span data-ttu-id="df997-146">Mit dem folgenden Befehl werden alle benutzerbezogenen Konferenzrichtlinien, die Ken Myers zuvor zugewiesen wurden, aufheben.</span><span class="sxs-lookup"><span data-stu-id="df997-146">The following command unassigns any per-user conferencing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="df997-147">Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="df997-147">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="df997-148">Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="df997-148">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="df997-149">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="df997-149">For more information, see the help topic for the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="df997-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df997-150">See Also</span></span>


[<span data-ttu-id="df997-151">Erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df997-151">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[<span data-ttu-id="df997-152">Zuweisen von Richtlinien für einzelne Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df997-152">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

