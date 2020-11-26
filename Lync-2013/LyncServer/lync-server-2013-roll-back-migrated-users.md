---
title: 'Lync Server 2013: Zurücksetzen von migrierten Benutzern'
description: 'Lync Server 2013: Rollback für migrierte Benutzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5993bfd530c84307d3ee5be627b3ed33814be73
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49442344"
---
# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="3b1bb-103">Zurücksetzen von migrierten Benutzern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b1bb-103">Roll back migrated users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="3b1bb-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="3b1bb-104">

<span> </span></span></span>

<span data-ttu-id="3b1bb-105">_**Letztes Änderungsdatum des Themas:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="3b1bb-105">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="3b1bb-106">Wenn Sie die Unified Contact Store-Funktion zurücksetzen müssen, setzen Sie die Kontakte nur zurück, wenn Sie den Benutzer wieder in Exchange 2010 oder lync Server 2010 zurück bewegen.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-106">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="3b1bb-107">Zum Zurücksetzen des Rollbacks deaktivieren Sie die Richtlinie für den Benutzer, und führen Sie dann das Cmdlet **Invoke-CsUcsRollback** aus.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-107">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="3b1bb-108">Nur die Ausführung von **Invoke-CsUcsRollback** allein reicht nicht aus, um einen dauerhaften Rollback zu gewährleisten, da die Migration von Unified Contact Store erneut initiiert wird, wenn die Richtlinie nicht deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-108">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="3b1bb-109">Wenn ein Benutzer beispielsweise zurückgesetzt wird, weil Exchange 2013 auf Exchange 2010 zurückgesetzt wird und dann das Postfach des Benutzers in Exchange 2013 verschoben wird, wird die Unified Contact Store-Migration sieben Tage nach dem Rollback erneut initiiert, sofern der Unified Contact Store weiterhin für den Benutzer in der Benutzer dienstrichtlinie aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-109">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3b1bb-110">Mit dem Cmdlet <STRONG>Move-CsUser</STRONG> wird in den folgenden Situationen automatisch der Kontaktspeicher des Benutzers von Exchange 2013 auf lync Server 2013 zurückgesetzt:</span><span class="sxs-lookup"><span data-stu-id="3b1bb-110">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="3b1bb-111">Wenn Benutzer von lync Server 2013 auf lync Server 2010 verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-111">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="3b1bb-112">Wenn Benutzer über einen Standort migriert werden, beispielsweise wenn ein Benutzer von lync online zu lync Server 2013 lokal oder umgekehrt verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-112">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3b1bb-p102">Durch das Importieren der Daten eines einheitlichen Kontaktspeichers aus einer Sicherungsdatenbank können Daten des einheitlichen Kontaktspeichers und Benutzerdaten beschädigt werden, falls der einheitliche Kontaktspeichermodus zwischen dem Export und dem Import geändert wurde. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3b1bb-p102">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="3b1bb-115">Wenn Sie Kontaktlisten exportieren, bevor die Kontakte der Benutzer nach Exchange 2013 migriert werden, und dann nach der Migration dieselben Daten importieren, werden die Unified Contact Store-Daten und Kontaktlisten beschädigt.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-115">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="3b1bb-116">Wenn Sie Benutzerdaten nach dem Migrieren von Benutzern zu Exchange 2013 exportieren, führen Sie eine Rollback für die Migration aus, und importieren Sie dann aus irgendeinem Grund die Daten aus der nach der Migration, werden die Unified Contact Store-Daten und Kontaktlisten beschädigt.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-116">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3b1bb-117">Bevor Sie ein Exchange-Postfach von Exchange 2013 auf Exchange 2010 verschieben, muss der Exchange-Administrator sicherstellen, dass der lync Server-Administrator zuerst die lync Server-Benutzer Kontakte von Exchange 2013 auf lync Server zurückgesetzt hat.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-117">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="3b1bb-118">Informationen zum Rollback von Unified Contact Store-Kontakten zu lync Server finden Sie unter Verfahren "So führen Sie einen Rollback für Unified Contact Store-Kontakte von Exchange 2013 zu lync Server 2013" weiter unten in diesem Abschnitt durch.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-118">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="3b1bb-119">Im folgenden Verfahren wird beschrieben, wie Sie ein Rollback für Benutzerkontakte ausführen.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-119">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="3b1bb-120">Wenn Sie das Cmdlet **Move-CsUser** verwenden, um Benutzer zwischen lync Server 2013 und lync Server 2010 zu verschieben, können Sie diese Schritte überspringen, da das Cmdlet **Move-CsUser** automatisch unifed Kontaktspeicher zurücksetzt, wenn Benutzer von lync Server 2013 nach lync Server 2010 verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-120">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="3b1bb-121">**Verschieben-CsUser** deaktiviert die Unified Contact Store-Richtlinie nicht, sodass die Migration in den Unified Contact Store wiederholt wird, wenn der Benutzer zurück zu lync Server 2013 verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-121">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="3b1bb-122">So führen Sie einen Rollback für Benutzer Kontakte von lync Server 2013 auf lync Server 2010 aus</span><span class="sxs-lookup"><span data-stu-id="3b1bb-122">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="3b1bb-123">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3b1bb-124">Deaktivieren Sie den einheitlichen Kontaktspeicher, damit die Benutzer zurückgesetzt werden können, damit Sie nach dem Rollback nicht erneut migriert werden.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-124">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback.</span></span> <span data-ttu-id="3b1bb-125">(Führen Sie diesen Schritt nur aus, wenn Sie sicherstellen möchten, dass Benutzer in Zukunft nicht mehr migriert werden.) Wenn Sie den Unified Contact Store für einzelne Benutzer deaktivieren möchten, geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="3b1bb-125">(Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="3b1bb-126">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3b1bb-126">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="3b1bb-127">Bevor Sie einen Benutzer von lync Server 2013 auf lync Server 2010 verschieben, können Sie die Kontaktliste für die angegebenen Benutzer auf dem lync-Server wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-127">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3b1bb-128">Wenn dieser Schritt ausgelassen wird, geht die Kontaktliste verloren.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-128">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="3b1bb-129">Wiederherstellen der angegebenen Benutzer</span><span class="sxs-lookup"><span data-stu-id="3b1bb-129">Roll back the specified users.</span></span> <span data-ttu-id="3b1bb-130">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="3b1bb-130">At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="3b1bb-131">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3b1bb-131">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3b1bb-132">Es wird nicht empfohlen, die Option – Force zu verwenden, um das Rollback zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-132">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="3b1bb-133">Wenn Sie diese Option verwenden, gehen die Kontakte der Benutzer verloren.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-133">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="3b1bb-134">So führen Sie einen Rollback für Unified Contact Store-Kontakte von Exchange 2013 auf lync Server 2013 aus</span><span class="sxs-lookup"><span data-stu-id="3b1bb-134">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="3b1bb-135">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-135">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3b1bb-136">Deaktivieren Sie den einheitlichen Kontaktspeicher, damit die Benutzer zurückgesetzt werden können, damit Sie nach dem Rollback nicht erneut migriert werden.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-136">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback.</span></span> <span data-ttu-id="3b1bb-137">Wenn Sie den Unified Contact Store für einzelne Benutzer deaktivieren möchten, geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="3b1bb-137">To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="3b1bb-138">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3b1bb-138">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="3b1bb-139">Wiederherstellen der angegebenen Benutzer</span><span class="sxs-lookup"><span data-stu-id="3b1bb-139">Roll back the specified users.</span></span> <span data-ttu-id="3b1bb-140">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="3b1bb-140">At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="3b1bb-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3b1bb-141">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3b1bb-142">Sie müssen zunächst den lync Server-Benutzer zurücksetzen und dann das Exchange 2013-Postfach verschieben.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-142">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="3b1bb-143">Der Exchange-Administrator ist vom Rollback von Exchange blockiert, bis der lync Server-Rollback abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-143">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="3b1bb-144">Es wird nicht empfohlen, die Option – Force zu verwenden, um das Rollback zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-144">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="3b1bb-145">Wenn Sie diese Option verwenden, gehen die Kontakte der Benutzer verloren.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-145">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="3b1bb-146">Nachdem Sie den Benutzer auf lync Server zurückgesetzt haben, kann der Exchange-Administrator den Exchange-Benutzer von Exchange 2013 auf Exchange 2010 zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="3b1bb-146">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

<span data-ttu-id="3b1bb-147"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="3b1bb-147"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

