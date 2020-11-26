---
title: 'Lync Server 2013: Verschieben von Benutzern in einen anderen Pool'
description: 'Lync Server 2013: Verschieben von Benutzern in einen anderen Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21012e0df7567a79bca018d194878c85b8653ae4
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425283"
---
# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="68f54-103">Verschieben von Benutzern in einen anderen Pool in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68f54-103">Move users to another pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="68f54-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="68f54-104">

<span> </span></span></span>

<span data-ttu-id="68f54-105">_**Letztes Änderungsdatum des Themas:** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="68f54-105">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="68f54-106">Sie können die lync Server-Systemsteuerung verwenden, um Benutzer einem bestimmten Server oder Pool zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="68f54-106">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="68f54-107">Das Verschieben aller vorhandenen Benutzer aus einem Quell Pool, auf dem lync Server 2010 oder früher ausgeführt wird, in einen lync Server 2013-Ziel Pool in einer komplexen Active Directory-Umgebung kann zu einer langsameren Active Directory-Replikation führen.</span><span class="sxs-lookup"><span data-stu-id="68f54-107">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="68f54-108">Um dies zu vermeiden, können Sie mithilfe von Suchfiltern Benutzer aus Pools verschieben, auf denen lync Server 2010 oder früher separat ausgeführt wird, oder Sie können die lync Server-Verwaltungsshell verwenden, um Benutzer mit Cmdlets zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="68f54-108">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="68f54-109">Darüber hinaus kann die Filterfunktionalität mit lync Server 2013-Benutzern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68f54-109">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="68f54-110">So verschieben Sie ausgewählte Benutzer auf einen anderen Server oder Pool</span><span class="sxs-lookup"><span data-stu-id="68f54-110">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="68f54-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="68f54-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="68f54-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="68f54-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="68f54-113">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="68f54-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="68f54-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="68f54-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="68f54-115">Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="68f54-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="68f54-116">Wählen Sie in der Tabelle einen bestimmten Benutzer oder Benutzer in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="68f54-116">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="68f54-117">Klicken Sie im Menü **Aktion** auf **ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="68f54-117">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="68f54-118">Wählen Sie in **Benutzer verschieben** den Pool aus, in den Sie die Benutzer in den **Ziel Registrierungspool** verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="68f54-118">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="68f54-119">Optional Aktivieren Sie das Kontrollkästchen **erzwingen** , wenn der Zielserver oder-Pool nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="68f54-119">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="68f54-120">Wenn Sie <STRONG>erzwingen</STRONG>auswählen, wird das Benutzerkonto verschoben, aber zugeordnete Benutzerdaten wie geplante Konferenzen und Kontakte werden nicht verschoben.</span><span class="sxs-lookup"><span data-stu-id="68f54-120">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="68f54-121">So verschieben Sie alle Benutzer von einem Server oder Pool auf einen anderen Server oder Pool</span><span class="sxs-lookup"><span data-stu-id="68f54-121">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="68f54-122">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="68f54-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="68f54-123">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="68f54-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="68f54-124">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="68f54-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="68f54-125">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="68f54-125">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="68f54-126">Klicken Sie im Menü **Aktion** auf **alle Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="68f54-126">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="68f54-127">Wählen Sie in **Benutzer verschieben** den Pool aus, der die Benutzerkonten enthält, die Sie im **Quell Registrierungspool** verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="68f54-127">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="68f54-128">Wählen Sie im **Ziel Registrierungspool** den Pool aus, in den Sie die Benutzer verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="68f54-128">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="68f54-129">Optional Aktivieren Sie das Kontrollkästchen **erzwingen** , wenn der Zielserver oder-Pool nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="68f54-129">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="68f54-130">Wenn Sie <STRONG>erzwingen</STRONG>auswählen, wird das Benutzerkonto verschoben, aber zugeordnete Benutzerdaten wie geplante Konferenzen und Kontakte werden nicht verschoben.</span><span class="sxs-lookup"><span data-stu-id="68f54-130">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="68f54-131">So verschieben Sie Benutzer mithilfe eines Filters aus einem Pool in einen anderen Pool</span><span class="sxs-lookup"><span data-stu-id="68f54-131">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="68f54-132">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="68f54-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="68f54-133">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="68f54-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="68f54-134">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="68f54-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="68f54-135">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="68f54-135">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="68f54-136">Klicken Sie in der **Benutzersuche** auf **Suchen**, und klicken Sie dann auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="68f54-136">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="68f54-137">Wählen Sie in den Suchkriterien den Eintrag **Registrierungspool** aus, wählen Sie **gleich** aus, wählen Sie **Aktueller Pool-FQDN** aus, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="68f54-137">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="68f54-138">Klicken Sie im Menü **Aktion** auf **alle Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="68f54-138">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68f54-139">Wenn ein Filter auf eine vorhandene Gruppe von Benutzern angewendet wird, befindet sich die Option <STRONG>alle Benutzer in Pool verschieben</STRONG> im Kontext der gefilterten Teilmenge von Benutzern, nicht <STRONG><EM>aller</EM></STRONG> möglichen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="68f54-139">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="68f54-140">Wählen Sie in **Benutzer verschieben** den Pool aus, der die Benutzerkonten enthält, die Sie im **Quell Registrierungspool** verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="68f54-140">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="68f54-141">Wählen Sie im **Ziel Registrierungspool** den Pool aus, in den Sie die Benutzer verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="68f54-141">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="68f54-142">Optional Aktivieren Sie das Kontrollkästchen **erzwingen** , wenn der Zielserver oder-Pool nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="68f54-142">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="68f54-143">Wenn Sie <STRONG>erzwingen</STRONG>auswählen, wird das Benutzerkonto verschoben, aber zugeordnete Benutzerdaten wie geplante Konferenzen und Kontakte werden nicht verschoben.</span><span class="sxs-lookup"><span data-stu-id="68f54-143">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="68f54-144">So verschieben Sie Benutzer mithilfe von Windows PowerShell-Cmdlets aus einem Pool in einen anderen</span><span class="sxs-lookup"><span data-stu-id="68f54-144">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="68f54-145">Je nachdem, wie Sie Windows PowerShell-Befehle ausführen (lokal oder Remote), müssen Sie sich wie folgt als Mitglied der richtigen lync Server 2013-Administratorrollen anmelden:</span><span class="sxs-lookup"><span data-stu-id="68f54-145">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="68f54-146">Wenn Sie die Befehle auf dem lokalen Computer ausführen (beispielsweise melden Sie sich direkt bei einem Front-End-Server an): Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe installiert ist, oder mit den erforderlichen Benutzerrechten, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="68f54-146">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="68f54-147">Wenn Sie die Befehle Remote auf einem anderen Computer ausführen (beispielsweise melden Sie sich bei Ihrem Computer an, und führen Sie die Befehle Remote auf einem Standard Edition-Front-End-Server aus): Melden Sie sich von einem Benutzerkonto, das der CsUserAdministrator-Rolle oder der CsAdministrator-Rolle zugewiesen ist, bei einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="68f54-147">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="68f54-148">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="68f54-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="68f54-149">Verwenden Sie das Cmdlet Move-CsUser wie folgt, um einzelne Benutzer zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="68f54-149">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="68f54-150">Der Benutzer, der verschoben werden soll, ist der Benutzer Pilar Ackerman, und der Benutzer wird aus dem aktuell zugewiesenen privaten Pool in den Pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="68f54-150">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="68f54-151">Wenn Sie eine große Anzahl von Benutzern verschieben möchten, verwenden Sie Filter mit dem Cmdlet **Get-CsUser** , und übergeben Sie die resultierenden Benutzersätze an **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="68f54-151">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="68f54-152">Die kombinierten Befehle von **Get-CsUser** und **Move-CsUser** können dazu führen:</span><span class="sxs-lookup"><span data-stu-id="68f54-152">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68f54-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68f54-153">See Also</span></span>


[<span data-ttu-id="68f54-154">Ändern von Benutzerkontoeigenschaften in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68f54-154">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="68f54-155"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="68f54-155"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

