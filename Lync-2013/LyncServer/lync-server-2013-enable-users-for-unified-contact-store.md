---
title: 'Lync Server 2013: Aktivieren von Benutzern für den einheitlichen Kontaktspeicher'
description: 'Lync Server 2013: Aktivieren von Benutzern für den einheitlichen Kontaktspeicher.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2249249d314e13d840b276e46f1fe38ad271664a
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428818"
---
# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="3ca8e-103">Aktivieren von Benutzern für den einheitlichen Kontaktspeicher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ca8e-103">Enable users for unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="3ca8e-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="3ca8e-104">

<span> </span></span></span>

<span data-ttu-id="3ca8e-105">_**Letztes Änderungsdatum des Themas:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="3ca8e-105">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="3ca8e-106">Wenn Sie lync Server 2013 bereitstellen und die Topologie veröffentlichen, ist der Unified Contact Store standardmäßig für alle Benutzer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3ca8e-106">When you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="3ca8e-107">Sie müssen keine weiteren Schritte Unternehmen, um den Unified Contact Store nach der Bereitstellung von lync Server 2013 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3ca8e-107">You do not need to take any additional action to enable unified contact store after you deploy Lync Server 2013.</span></span> <span data-ttu-id="3ca8e-108">Sie können jedoch das Cmdlet " **festlegen-CsUserServicesPolicy** " verwenden, um die verfügbaren Unified Contact Store-Benutzer anzupassen.</span><span class="sxs-lookup"><span data-stu-id="3ca8e-108">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="3ca8e-109">Sie können dieses Feature Global, nach Website, nach Mandanten oder nach Einzelpersonen oder Gruppen von Personen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3ca8e-109">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>

<div>

## <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="3ca8e-110">So aktivieren Sie Benutzer für den einheitlichen Kontaktspeicher</span><span class="sxs-lookup"><span data-stu-id="3ca8e-110">To enable users for unified contact store</span></span>

1.  <span data-ttu-id="3ca8e-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="3ca8e-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3ca8e-112">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3ca8e-112">Do any of the following:</span></span>
    
      - <span data-ttu-id="3ca8e-113">Um den Unified Contact Store für alle lync Server-Benutzer Global zu aktivieren, geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="3ca8e-113">To enable unified contact store globally for all Lync Server users, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - <span data-ttu-id="3ca8e-114">Um den Unified Contact Store für die Benutzer an einer bestimmten Website zu aktivieren, geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="3ca8e-114">To enable unified contact store for the users at a specific site, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        <span data-ttu-id="3ca8e-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3ca8e-115">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - <span data-ttu-id="3ca8e-116">Um den Unified Contact Store nach Mandanten zu aktivieren, geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="3ca8e-116">To enable unified contact store by tenant, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        <span data-ttu-id="3ca8e-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3ca8e-117">For example:</span></span>
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - <span data-ttu-id="3ca8e-118">Wenn Sie den Unified Contact Store für bestimmte Benutzer aktivieren möchten, geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="3ca8e-118">To enable unified contact store for specific users, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3ca8e-119">Sie können anstelle des Benutzeranzeigenamens auch einen Benutzeralias oder einen SIP-URI verwenden.</span><span class="sxs-lookup"><span data-stu-id="3ca8e-119">You can also use user alias or SIP URI instead of the user display name.</span></span>

        
        </div>
        
        <span data-ttu-id="3ca8e-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3ca8e-120">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3ca8e-p102">Im vorstehenden Beispiel wird mit dem ersten Befehl eine neue benutzerbezogene Richtlinie mit dem Namen <EM>UCS Enabled Users</EM> erstellt, für die das Flag „UcsAllowed“ auf „True“ festgelegt ist. Mit dem zweiten Befehl wird die Richtlinie dem Benutzer mit dem Anzeigename „Ken Myer“ zugewiesen, d. h., Ken Myer ist ab sofort für den einheitlichen Kontaktspeicher aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3ca8e-p102">In the preceding example, the first command creates a new per-user policy named <EM>UCS Enabled Users</EM> with the UcsAllowed flag set to True. The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>

        
        <span data-ttu-id="3ca8e-123"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="3ca8e-123"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

