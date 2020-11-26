---
title: 'Lync Server 2013: Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer'
description: 'Lync Server 2013: weisen Sie einem lync-aktivierten Benutzer eine Richtlinie für den externen Benutzer Zugriff zu.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2be3ea52e6e44400b3967d7c3346da2297220675
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49443496"
---
# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a><span data-ttu-id="b9e9d-103">Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9e9d-103">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="b9e9d-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="b9e9d-104">

<span> </span></span></span>

<span data-ttu-id="b9e9d-105">_**Letztes Änderungsdatum des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="b9e9d-105">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="b9e9d-106">Wenn ein Benutzer für lync Server aktiviert wurde, können Sie den SIP-Verbund, die XMPP-Föderation, den Remotebenutzerzugriff und die öffentliche Sofortnachrichten-Konnektivität in der lync Server-Systemsteuerung konfigurieren, indem Sie die entsprechenden Richtlinien auf bestimmte Benutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-106">If a user has been enabled for Lync Server, you can configure SIP federation, XMPP federation, remote user access, and public instant messaging (IM) connectivity in the Lync Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="b9e9d-107">Wenn Sie beispielsweise eine Richtlinie zur Unterstützung des Remotebenutzerzugriffs erstellt haben, müssen Sie Sie auf den Benutzer anwenden, bevor der Benutzer von einem Remotestandort aus eine Verbindung mit lync Server herstellen und mit internen Benutzern am Remotestandort zusammenarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-107">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Lync Server from a remote location and collaborate with internal users from the remote location.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9e9d-108">Wenn Sie den Zugriff durch externe Benutzer unterstützen möchten, müssen Sie die Unterstützung für jeden Typ von externem Benutzer Zugriff aktivieren, den Sie unterstützen möchten, und die entsprechenden Richtlinien und anderen Optionen zum Steuern der Verwendung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-108">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="b9e9d-109">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-support-for-external-user-access.md">Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013</A> in der Bereitstellungsdokumentation oder <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Verwalten des Föderations-und des externen Zugriffs auf lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-109">For details, see <A href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</A> in the Deployment documentation or <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Managing federation and external access to Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="b9e9d-110">Verwenden Sie das in diesem Thema beschriebene Verfahren, um eine zuvor erstellte Richtlinie für den Benutzer Zugriff auf ein oder mehrere Benutzerkonten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-110">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="b9e9d-111">So wenden Sie eine externe Benutzerrichtlinie auf ein Benutzerkonto an</span><span class="sxs-lookup"><span data-stu-id="b9e9d-111">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="b9e9d-112">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b9e9d-113">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b9e9d-114">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b9e9d-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b9e9d-115">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-115">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="b9e9d-116">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-116">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b9e9d-117">Wählen Sie in **lync Server-Benutzer bearbeiten** unter **Richtlinie für den externen Zugriff** die Benutzerrichtlinie aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-117">In **Edit Lync Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b9e9d-118">Die <STRONG> &lt; automatischen &gt; </STRONG> Einstellungen gelten für den Standardserver oder die globalen Richtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-118">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b9e9d-119">Zuweisen von Per-User Richtlinien für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="b9e9d-119">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b9e9d-120">Benutzerspezifische Richtlinien für den externen Zugriff können mithilfe von Windows PowerShell und dem Grant-CsExternalAccessPolicy-Cmdlet zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-120">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="b9e9d-121">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b9e9d-122">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="b9e9d-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="b9e9d-123">So weisen Sie einem einzelnen Benutzer eine Richtlinie für den externen Zugriff pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="b9e9d-123">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="b9e9d-124">Mit diesem Befehl wird dem Benutzer Ken Myers die Richtlinie für den externen Zugriff per Benutzer RedmondExternalAccessPolicy zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-124">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="b9e9d-125">So weisen Sie mehreren Benutzern eine Richtlinie für den externen Zugriff pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="b9e9d-125">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="b9e9d-126">Dieser Befehl weist allen Benutzern, die über Konten in der United States ou in Active Directory verfügen, die USAExternalAccessPolicy-Richtlinie für den externen Zugriff pro Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-126">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="b9e9d-127">Weitere Informationen zu dem in diesem Befehl verwendeten ou-Parameter finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="b9e9d-127">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="b9e9d-128">So heben Sie die Zuweisung einer externen Zugriffsrichtlinie für einzelne Benutzer auf</span><span class="sxs-lookup"><span data-stu-id="b9e9d-128">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="b9e9d-129">Mit diesem Befehl wird die Zuweisung einer externen Zugriffsrichtlinie für einzelne Benutzer aufheben, die Ken Myers zuvor zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-129">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="b9e9d-130">Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-130">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="b9e9d-131">Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="b9e9d-131">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="b9e9d-132">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="b9e9d-132">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>

<span data-ttu-id="b9e9d-133"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="b9e9d-133"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

