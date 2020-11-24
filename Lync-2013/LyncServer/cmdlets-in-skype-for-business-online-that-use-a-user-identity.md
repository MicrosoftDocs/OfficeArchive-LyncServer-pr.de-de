---
title: Cmdlets in Skype for Business Online, die eine Benutzeridentität verwenden
description: Cmdlets in Skype for Business Online, die eine Benutzeridentität verwenden.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29f838317f8b2779de862eb2df82ae1b348871e4
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394235"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="3b2e1-103">Cmdlets in Skype for Business Online, die eine Benutzeridentität verwenden</span><span class="sxs-lookup"><span data-stu-id="3b2e1-103">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="3b2e1-104">In Skype for Business Online gibt es eine Reihe von unterschiedlichen Möglichkeiten, auf eine einzelne Benutzeridentität zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="3b2e1-104">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="3b2e1-105">Verwenden Sie den Anzeigenamen der Active Directory-Domänendienste des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="3b2e1-105">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="3b2e1-106">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3b2e1-106">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="3b2e1-107">Verwenden Sie die SIP-Adresse des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="3b2e1-107">Use the user’s SIP address.</span></span> <span data-ttu-id="3b2e1-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3b2e1-108">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="3b2e1-109">Verwenden Sie den UPN des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="3b2e1-109">Use the user’s UPN.</span></span> <span data-ttu-id="3b2e1-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3b2e1-110">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="3b2e1-111">Verwenden Sie den Distinguished Name für den Active Directory-Domänendienst des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="3b2e1-111">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="3b2e1-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3b2e1-112">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="3b2e1-113">Die folgenden Cmdlets akzeptieren eine Benutzeridentität:</span><span class="sxs-lookup"><span data-stu-id="3b2e1-113">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="3b2e1-114">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b2e1-114">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b2e1-115">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b2e1-115">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b2e1-116">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b2e1-116">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b2e1-117">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b2e1-117">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b2e1-118">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b2e1-118">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b2e1-119">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b2e1-119">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b2e1-120">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b2e1-120">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b2e1-121">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b2e1-121">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b2e1-122">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b2e1-122">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b2e1-123">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b2e1-123">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b2e1-124">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b2e1-124">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b2e1-125">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b2e1-125">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="3b2e1-126">Beachten Sie, dass Sie beim Aufrufen eines der **Get-CS-** Cmdlets keine Benutzeridentität angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="3b2e1-126">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="3b2e1-127">In diesem Fall geben die Cmdlets alle Instanzen des angegebenen Elements zurück.</span><span class="sxs-lookup"><span data-stu-id="3b2e1-127">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="3b2e1-128">Dieser Befehl gibt beispielsweise Informationen zu allen Benutzern zurück, die für Skype for Business Online aktiviert wurden:</span><span class="sxs-lookup"><span data-stu-id="3b2e1-128">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="3b2e1-129">Der Parameter Identity ist nur erforderlich, wenn Sie Informationen für einen bestimmten Benutzer zurückgeben möchten:</span><span class="sxs-lookup"><span data-stu-id="3b2e1-129">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="3b2e1-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b2e1-130">See Also</span></span>


[<span data-ttu-id="3b2e1-131">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3b2e1-131">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="3b2e1-132">[Die Lync Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b2e1-132">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

