---
title: 'Lync Server 2013: Konfigurieren von lync Server für die Verwendung des einheitlichen Kontaktspeichers'
description: 'Lync Server 2013: Konfigurieren von lync Server für die Verwendung des einheitlichen Kontaktspeichers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6905d2e393fec36fe5db3e40ee20087c0cca0991
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49432961"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a><span data-ttu-id="b5520-103">Konfigurieren von Microsoft lync Server 2013 für die Verwendung des einheitlichen Kontaktspeichers</span><span class="sxs-lookup"><span data-stu-id="b5520-103">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="b5520-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="b5520-104">

<span> </span></span></span>

<span data-ttu-id="b5520-105">_**Letztes Änderungsdatum des Themas:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="b5520-105">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="b5520-106">Der Unified Contact Store ermöglicht es Benutzern, eine einzelne Kontaktliste zu verwalten und diese Kontakte dann in mehreren Anwendungen zur Verfügung zu haben, einschließlich Microsoft lync 2013, Microsoft Outlook 2013 und Microsoft Outlook Web App 2013.</span><span class="sxs-lookup"><span data-stu-id="b5520-106">The unified contact store enables users to maintain a single contacts list and then have those contacts available in multiple applications, including Microsoft Lync 2013, Microsoft Outlook 2013, and Microsoft Outlook Web App 2013.</span></span> <span data-ttu-id="b5520-107">Wenn Sie den Unified Contact Store für einen Benutzer aktivieren, werden die Kontakte des Benutzers nicht in Microsoft lync Server 2013 gespeichert und dann über das SIP-Protokoll abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b5520-107">When you enable the unified contact store for a user that user's contacts are not stored in Microsoft Lync Server 2013 and then retrieved using the SIP protocol.</span></span> <span data-ttu-id="b5520-108">Stattdessen werden seine Kontakte in Microsoft Exchange Server 2013 gespeichert und mithilfe von Exchange-Webdiensten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b5520-108">Instead, his or her contacts are stored in Microsoft Exchange Server 2013 and are retrieved by using Exchange Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5520-109">Technisch gesehen werden die Kontaktinformationen in einem Paar von Ordnern gespeichert, die im Exchange 2013-Postfach des Benutzers gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="b5520-109">Technically, contact information is stored in a pair of folders found in the user's Exchange 2013 mailbox.</span></span> <span data-ttu-id="b5520-110">Die Kontakte selbst werden in einem Ordner namens lync-Kontakte gespeichert, der für Endbenutzer sichtbar ist. Metadaten zu den Kontakten werden in einem Unterordner gespeichert, der für Endbenutzer nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="b5520-110">The contacts themselves are stored in a folder named Lync Contacts which is visible to end users; metadata about the contacts are stored in a subfolder that is not visible to end users.</span></span>



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a><span data-ttu-id="b5520-111">Aktivieren des einheitlichen Kontaktspeichers für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="b5520-111">Enabling the Unified Contact Store for a User</span></span>

<span data-ttu-id="b5520-112">Wenn Sie die Server-zu-Server-Authentifizierung bereits zwischen lync Server 2013 und Exchange 2013 konfiguriert haben, haben Sie auch die Verwendung des einheitlichen Kontaktspeichers aktiviert. Es ist keine zusätzliche Serverkonfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b5520-112">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you have also enabled the use of the unified contact store; no additional server configuration is required.</span></span> <span data-ttu-id="b5520-113">Beim Benutzerkonto sind jedoch noch Konfigurationsschritte erforderlich, damit die Kontakte des Benutzers in den einheitlichen Kontaktspeicher verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b5520-113">However, additional user account configuration is required in order to move a user's contacts into the unified contact store.</span></span> <span data-ttu-id="b5520-114">Standardmäßig werden Benutzer Kontakte in lync Server und nicht im Unified Contact Store aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="b5520-114">By default, user contacts are kept in Lync Server and not in the unified contact store.</span></span>

<span data-ttu-id="b5520-115">Der Zugriff auf den einheitlichen Kontaktspeicher wird mithilfe von lync Server-Benutzer Dienst Richtlinien verwaltet.</span><span class="sxs-lookup"><span data-stu-id="b5520-115">Access to the unified contact store is managed by using Lync Server user services policies.</span></span> <span data-ttu-id="b5520-116">Benutzerdienst-Richtlinien verfügen nur über eine einzige Eigenschaft (UcsAllowed), die angibt, wo die Kontakte eines Benutzers gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b5520-116">User server policies have only a single property (UcsAllowed); this property is used to determine the location where a user's contacts are stored.</span></span> <span data-ttu-id="b5520-117">Wenn ein Benutzer von einer Richtlinie für Benutzer Dienste verwaltet wird, in der UcsAllowed auf "true" ($true) festgelegt wurde, werden die Kontakte des Benutzers im Unified Contact Store gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b5520-117">If a user is managed by a user services policy where UcsAllowed has been set to True ($True) then the user's contacts will be stored in the unified contact store.</span></span> <span data-ttu-id="b5520-118">Wenn der Benutzer von einer Richtlinie für Benutzer Dienste verwaltet wird, in der UcsAllowed auf false ($false) festgelegt wurde, werden seine Kontakte in lync Server gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b5520-118">If the user is managed by a user services policy where UcsAllowed has been set to False ($False) then his or her contacts will be stored in Lync Server.</span></span>

<span data-ttu-id="b5520-119">Wenn Sie lync Server 2013 installieren, wird eine Richtlinie für einzelne Benutzer Dienste installiert, die auch im globalen Bereich konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="b5520-119">When you install Lync Server 2013 a single user services policy (configured at the global scope) is installed as well.</span></span> <span data-ttu-id="b5520-120">Der Wert „UcsAllowed“ in dieser Richtlinie ist auf „True“ festgelegt, was bedeutet, dass Benutzerkontakte standardmäßig im einheitlichen Kontaktspeicher gespeichert werden (vorausgesetzt, dass dieser bereitgestellt und konfiguriert wurde).</span><span class="sxs-lookup"><span data-stu-id="b5520-120">The UcsAllowed value in this policy is set to True, meaning that, by default, user contacts will be stored in the unified contact store (assuming this has been deployed and configured).</span></span> <span data-ttu-id="b5520-121">Wenn Sie alle Benutzerkontakte zum einheitlichen Kontaktspeicher migrieren möchten, müssen Sie nichts weiter tun.</span><span class="sxs-lookup"><span data-stu-id="b5520-121">If you want to migrate all of your user contacts to the unified contact store you do not have to do anything at all.</span></span>

<span data-ttu-id="b5520-122">Wenn Sie lieber nicht alle Kontakte zum einheitlichen Kontaktspeicher migrieren möchten, können Sie den einheitlichen Kontaktspeicher für alle Benutzer deaktivieren, indem Sie die Eigenschaft „UcsAllowed“ in der globalen Richtlinie auf „False“ setzen:</span><span class="sxs-lookup"><span data-stu-id="b5520-122">If you would prefer not to migrate all your contacts to the unified contact store you can disable the unified contact store for all users by setting the UcsAllowed property in the global policy to False:</span></span>

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

<span data-ttu-id="b5520-123">Nachdem Sie den Unified Contact Store in der globalen Richtlinie deaktiviert haben, können Sie eine benutzerspezifische Richtlinie erstellen, die die Verwendung des einheitlichen Kontaktspeichers ermöglicht. auf diese Weise können einige Benutzer Ihre Kontakte im Unified Contact Store behalten, während andere Benutzer Ihre Kontakte weiterhin in lync Server behalten.</span><span class="sxs-lookup"><span data-stu-id="b5520-123">After you have disabled the unified contact store in the global policy you can then create a per-user policy that enables the use of the unified contact store; this allows you to have some users keep their contacts in the unified contact store while other users continue to keep their contacts in Lync Server.</span></span> <span data-ttu-id="b5520-124">Sie können eine Benutzer dienstrichtlinie pro Benutzer erstellen, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="b5520-124">You can create a per-user user services policy by using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

<span data-ttu-id="b5520-p107">Nachdem Sie die neue Richtlinie erstellt haben, müssen Sie sie jedem Benutzer zuweisen, der Zugang zum einheitlichen Kontaktspeicher haben soll. Das Zuweisen von benutzerbezogenen Richtlinien zu Benutzern führen Sie mit Befehlen wie dem folgenden durch:</span><span class="sxs-lookup"><span data-stu-id="b5520-p107">After you have created the new policy you must then assign that policy to any user who should have access to the unified contact store. Per-user policies can be assigned to users by using commands similar to this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

<span data-ttu-id="b5520-127">Nachdem die Richtlinie zugewiesen wurde, beginnt lync Server damit, die Kontakte des Benutzers in den Unified Contact Store zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="b5520-127">After the policy has been assigned Lync Server will begin to migrate the user's contacts to the unified contact store.</span></span> <span data-ttu-id="b5520-128">Nach Abschluss der Migration werden die Kontakte in Exchange anstatt in lync Server gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b5520-128">After migration is complete, the user will then have his or her contacts stored in Exchange rather than Lync Server.</span></span> <span data-ttu-id="b5520-129">Wenn der Benutzer zu dem Zeitpunkt, zu dem die Migration abgeschlossen ist, bei lync 2013 angemeldet ist, wird ein Meldungsfeld angezeigt, in dem er oder Sie aufgefordert wird, sich bei lync abzumelden und dann erneut anzumelden, um den Prozess abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b5520-129">If the user happens to be logged on to Lync 2013 at the time migration completes, a message box will appear and he or she will be asked to log off of Lync and then log back on in order to finalize the process.</span></span> <span data-ttu-id="b5520-130">Die Kontakte von Benutzern, denen diese benutzerbezogene Richtlinie zugewiesen wurde, werden nicht zum einheitlichen Kontaktspeicher migriert.</span><span class="sxs-lookup"><span data-stu-id="b5520-130">Users who have not been assigned this per-user policy will not have their contacts migrated to the unified contact store.</span></span> <span data-ttu-id="b5520-131">Der Grund ist, dass diese Benutzer von der globalen Richtlinie verwaltet werden und die Verwendung des einheitlichen Kontaktspeichers in der globalen Richtlinie deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="b5520-131">That’s because those users are being managed by the global policy, and use of the unified contact store has been disabled in the global policy.</span></span>

<span data-ttu-id="b5520-132">Sie können überprüfen, ob die Kontakte eines Benutzers erfolgreich in den Unified Contact Store migriert wurden, indem Sie das Cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) in der lync Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="b5520-132">You can verify that a user's contacts have successfully been migrated to the unified contact store by running the [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) cmdlet from within the Lync Server Management Shell:</span></span>

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="b5520-133">Wenn das Cmdlet Test-CsUnifiedContactStore einen Erfolg meldet, bedeutet dies, dass die Kontakte für den Benutzer „sip:kenmyer@litwareinc.com“ zum einheitlichen Kontaktspeicher migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="b5520-133">If Test-CsUnifiedContactStore succeeds that means that the contacts for the user sip:kenmyer@litwareinc.com have been migrated to the unified contact store.</span></span>

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a><span data-ttu-id="b5520-134">Zurückverlegung aus dem einheitlichen Kontaktspeicher</span><span class="sxs-lookup"><span data-stu-id="b5520-134">Rolling Back the Unified Contact Store</span></span>

<span data-ttu-id="b5520-135">Wenn Sie die Kontakte eines Benutzers aus dem Unified Contact Store entfernen müssen (wenn der Benutzer beispielsweise auf Microsoft lync Server 2010 verlagert werden muss und daher den einheitlichen Kontaktspeicher nicht mehr verwenden kann), müssen Sie zwei Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="b5520-135">If you need to remove a user's contacts from the unified contact store (for example, if the user needs to be rehomed on Microsoft Lync Server 2010 and thus can no longer use the unified contact store) you must do two things.</span></span> <span data-ttu-id="b5520-136">Zunächst müssen Sie dem Benutzer eine neue Richtlinie für Benutzer Dienste zuweisen, die verhindert, dass Kontakte im Unified Contact Store gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b5520-136">First, you must assign the user a new user services policy, one that prohibits storing contacts in the unified contact store.</span></span> <span data-ttu-id="b5520-137">(Dies ist eine Richtlinie, bei der die UcsAllowed-Eigenschaft auf $false festgesetzt wurde.) Wenn Sie nicht über eine solche Richtlinie verfügen, können Sie Sie mithilfe eines Befehls wie den folgenden erstellen:</span><span class="sxs-lookup"><span data-stu-id="b5520-137">(That is, a policy where the UcsAllowed property has been set to $False.) If you do not have such a policy you can create one using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

<span data-ttu-id="b5520-138">Anschließend können Sie diese neue benutzerbezogene Richtlinie (NoUnifiedContactStore) mit dem folgenden Befehl zuweisen:</span><span class="sxs-lookup"><span data-stu-id="b5520-138">You can then assign this new per-user policy (NoUnifiedContactStore) by using a command like this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

<span data-ttu-id="b5520-139">Dieser Befehl weist die neue Richtlinie dem Benutzer „Ken Myer“ zu und verhindert, dass dessen Kontakte zum einheitlichen Kontaktspeicher migriert werden.</span><span class="sxs-lookup"><span data-stu-id="b5520-139">The preceding command assigns the new policy to the user Ken Myer, and also prevents Ken's contacts from being migrated to the unified contact store.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5520-140">In einigen Fällen können Sie denselben Nettoeffekt erzielen, indem Sie einfach die Zuweisung der aktuellen Benutzer Dienste-Richtlinie des Benutzers aufheben.</span><span class="sxs-lookup"><span data-stu-id="b5520-140">In some cases you can achieve the same net effect by simply unassigning the user's current user services policy.</span></span> <span data-ttu-id="b5520-141">Das wäre z. B. der Fall, wenn dem Benutzer „Ken Myer“ eine benutzerbezogene Benutzerdienst-Richtlinie zugewiesen ist, die den einheitlichen Kontaktspeicher aktiviert, während die globale Richtlinie die Verwendung des einheitlichen Kontaktspeichers verbietet.</span><span class="sxs-lookup"><span data-stu-id="b5520-141">For example, suppose Ken Myer has a per-user user services policy the enables the unified contact store, but your global policy prohibits the use of the unified contact store.</span></span> <span data-ttu-id="b5520-142">In diesem Fall können Sie die Zuweisung der benutzerbezogenen dienstrichtlinie für Ken aufheben.</span><span class="sxs-lookup"><span data-stu-id="b5520-142">In that case, you could unassign Ken's per-user services policy.</span></span> <span data-ttu-id="b5520-143">Ken würde dann automatisch von der globalen Richtlinie verwaltet werden und somit keinen Zugriff auf den einheitlichen Kontaktspeicher mehr besitzen.</span><span class="sxs-lookup"><span data-stu-id="b5520-143">When you do that, Ken will automatically be managed by the global policy, and thus will no longer have access to the unified contact store.</span></span><BR><span data-ttu-id="b5520-144">Wenn Sie eine zuvor zugewiesene Richtlinie für einzelne Benutzer aufheben möchten, verwenden Sie den gleichen Befehl wie zuvor, aber legen Sie diesen Parameter auf einen Nullwert fest:</span><span class="sxs-lookup"><span data-stu-id="b5520-144">To unassign a previously-assigned per-user policy, use the same command as shown before, but this time set the PolicyName parameter to a null value:</span></span><BR><span data-ttu-id="b5520-145">Grant-CsUserServicesPolicy –Identity „Ken Myer“ –PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="b5520-145">Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



</div>

<span data-ttu-id="b5520-146">Die Terminologie "verhindert, dass Ken-Kontakte in den einheitlichen Kontaktspeicher migriert werden" ist wichtig, wenn Sie mit dem Unified Contact Store arbeiten.</span><span class="sxs-lookup"><span data-stu-id="b5520-146">The terminology "prevents Ken's contacts from being migrated to the unified contact store" is important to keep in mind when working with the unified contact store.</span></span> <span data-ttu-id="b5520-147">Wenn Sie einfach Ken eine neue Richtlinie für Benutzer Dienste zuweisen, werden die Kontakte nicht aus dem Unified Contact Store verschoben.</span><span class="sxs-lookup"><span data-stu-id="b5520-147">Simply assigning Ken a new user services policy will not move his contacts out of the unified contact store.</span></span> <span data-ttu-id="b5520-148">Wenn sich ein Benutzer bei lync Server 2013 anmeldet, überprüft das System die Benutzer Dienste-Richtlinie des Benutzers, um festzustellen, ob seine Kontakte im Unified Contact Store aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b5520-148">When a user logs on to Lync Server 2013, the system checks the user's user services policy to see whether his or her contacts should be kept in the unified contact store.</span></span> <span data-ttu-id="b5520-149">Wenn die Antwort ja lautet (das heißt, wenn die UcsAllowed-Eigenschaft auf $true festgesetzt ist), werden diese Kontakte in den Unified Contact Store migriert (vorausgesetzt, diese Kontakte sind noch nicht im Unified Contact Store).</span><span class="sxs-lookup"><span data-stu-id="b5520-149">If the answer is yes (that is, if the UcsAllowed property is set to $True) then those contacts will be migrated to the unified contact store (assuming that those contacts are not already in the unified contact store).</span></span> <span data-ttu-id="b5520-150">Wenn die Antwort nein lautet, ignoriert lync Server einfach die Kontakte des Benutzers und wechselt zur nächsten Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="b5520-150">If the answer is no, then Lync Server simply ignores the user's contacts and moves on to its next task.</span></span> <span data-ttu-id="b5520-151">Das bedeutet, dass lync Server die Kontakte eines Benutzers nicht automatisch aus dem Unified Contact Store verschieben wird, unabhängig vom Wert der UcsAllowed-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b5520-151">That means that Lync Server will not automatically move a user's contacts from out of the unified contact store, regardless of the value of the UcsAllowed property.</span></span>

<span data-ttu-id="b5520-152">Das bedeutet auch, dass Sie nach dem Zuweisen des Benutzers zu einer neuen Richtlinie für Benutzer Dienste das [Invoke-CsUcsRollback-](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) Cmdlet ausführen müssen, um die Kontakte des Benutzers aus Exchange 2013 und zurück zu lync Server 2013 zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="b5520-152">That also means that, after assigning the user a new user services policy, you must then run the [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) cmdlet in order to move the user's contacts out of Exchange 2013 and back to Lync Server 2013.</span></span> <span data-ttu-id="b5520-153">Beispiel: Nachdem Sie dem Benutzer „Ken Myer“ eine neue Benutzerdienst-Richtlinie zugewiesen haben, können Sie seine Kontakte mit dem folgenden Befehl aus dem einheitlichen Kontaktspeicher verlegen:</span><span class="sxs-lookup"><span data-stu-id="b5520-153">For example, after assigning Ken Myer a new user services policy you can then move his contacts out of the unified contact store by using the following command:</span></span>

    Invoke-CsUcsRollback -Identity "Ken Myer"

<span data-ttu-id="b5520-154">Wenn Sie die Benutzerdienst-Richtlinie ändern, ohne anschließend das Cmdlet Invoke-CsUcsRollback auszuführen, bleiben die Kontakte von Ken im einheitlichen Kontaktspeicher.</span><span class="sxs-lookup"><span data-stu-id="b5520-154">If you change the user services policy but do not run the Invoke-CsUcsRollback cmdlet Ken's contacts will not be removed from the unified contact store.</span></span> <span data-ttu-id="b5520-155">Und was wäre, wenn Sie das Invoke-CsUcsRollback-Cmdlet ausführen, ohne die Benutzerdienste-Richtlinie von Ken Myer zu ändern?</span><span class="sxs-lookup"><span data-stu-id="b5520-155">What if you run Invoke-CsUcsRollback but do not change Ken Myer's user services policy?</span></span> <span data-ttu-id="b5520-156">In diesem Fall werden die Kontakte von Ken nur vorübergehend aus dem einheitlichen Kontaktspeicher entfernt.</span><span class="sxs-lookup"><span data-stu-id="b5520-156">In that case, Ken's contacts will be temporarily removed from the unified contact store.</span></span> <span data-ttu-id="b5520-157">Achten Sie hierbei bitte auf das Wort „vorübergehend“!</span><span class="sxs-lookup"><span data-stu-id="b5520-157">The fact that this removal is temporary is important to keep in mind.</span></span> <span data-ttu-id="b5520-158">Nachdem die Kontakte von Ken aus dem Unified Contact Store entfernt wurden, wartet lync Server 2013 7 Tage, und überprüfen Sie dann, welche Benutzer Dienste-Richtlinie Ken zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="b5520-158">After Ken's contacts have been removed from the unified contact store, Lync Server 2013 will wait 7 days and then check to see which user services policy has been assigned to Ken.</span></span> <span data-ttu-id="b5520-159">Wenn Ken weiterhin eine Richtlinie zugewiesen ist, die ihn für den einheitlichen Kontaktspeicher aktiviert, werden seine Kontakte automatisch wieder zurück in den Kontaktspeicher verschoben.</span><span class="sxs-lookup"><span data-stu-id="b5520-159">If Ken is still assigned a policy that enables the user of the unified contact store, then his contacts will automatically be moved back to into the contact store.</span></span> <span data-ttu-id="b5520-160">Um die Kontakte dauerhaft aus dem einheitlichen Kontaktspeicher zu entfernen, müssen Sie nicht nur das Invoke-CsUcsRollback-Cmdlet ausführen, sondern zusätzlich auch seine Benutzerdienste-Richtlinie ändern.</span><span class="sxs-lookup"><span data-stu-id="b5520-160">To permanently remove contacts from the unified contact store you must change the user services policy in addition to running the Invoke-CsUcsRollback cmdlet.</span></span>

<span data-ttu-id="b5520-p114">Aufgrund der zahlreichen Variablen, die sich auf die Migration auswirken können, kann schwer geschätzt werden, wie viel Zeit erforderlich ist, bis Konten vollständig zum einheitlichen Kontaktspeicher migriert sind. Als allgemeine Regel lässt sich jedoch sagen, dass die Migration nicht unmittelbar in Kraft tritt: Auch wenn Sie nur sehr wenige Kontakte migrieren, kann es zehn Minuten oder länger dauern, bis die Verschiebung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b5520-p114">Due to the large number of variables that can affect migration, it is difficult to estimate how long it will take before accounts are fully migrated to the unified contact store. As a general rule, however, migration does not take effect immediately: even when migrating a small number of contacts it might take 10 minutes or more before the move is complete.</span></span>

<span data-ttu-id="b5520-163"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="b5520-163"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

