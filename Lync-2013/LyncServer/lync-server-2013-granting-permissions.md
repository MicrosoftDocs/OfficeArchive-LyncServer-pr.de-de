---
title: 'Lync Server 2013: Gewähren von Berechtigungen'
description: 'Lync Server 2013: Erteilen von Berechtigungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bdb2b1ef39b85caa89c7597f455e6e4fc08e44e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49395015"
---
# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="48948-103">Gewähren von Berechtigungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48948-103">Granting permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="48948-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="48948-104">

<span> </span></span></span>

<span data-ttu-id="48948-105">_**Letztes Änderungsdatum des Themas:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="48948-105">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="48948-106">Für Setup können Sie der universellen RTCUniversalServerAdmins-Gruppe für eine bestimmte Active Directory-Organisationseinheit Berechtigungen erteilen, sodass Mitglieder der RTCUniversalServerAdmins-Gruppe in dieser OU lync Server 2013 in der angegebenen Domäne installieren können.</span><span class="sxs-lookup"><span data-stu-id="48948-106">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="48948-107">Wenn Sie Berechtigungen für eine OU erteilen, werden die folgenden Berechtigungen gewährt:</span><span class="sxs-lookup"><span data-stu-id="48948-107">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="48948-108">Lesen</span><span class="sxs-lookup"><span data-stu-id="48948-108">Read</span></span>

  - <span data-ttu-id="48948-109">Schreiben</span><span class="sxs-lookup"><span data-stu-id="48948-109">Write</span></span>

  - <span data-ttu-id="48948-110">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="48948-110">ReadSPN</span></span>

  - <span data-ttu-id="48948-111">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="48948-111">WriteSPN</span></span>

<span data-ttu-id="48948-112">Für die Verwaltung können Sie den angegebenen OUs Berechtigungen hinzufügen, sodass Mitglieder der universellen RTC-Gruppen, die von der Gesamtstrukturvorbereitung erstellt wurden, auf die OUs zugreifen können, ohne dass Sie Mitglieder der Gruppe der Domänenadministratoren sein müssen.</span><span class="sxs-lookup"><span data-stu-id="48948-112">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="48948-113">Die der angegebenen Organisationseinheit hinzugefügten Berechtigungen sind dieselben Berechtigungen, die das Cmdlet **enable-CsAdDomain** den OU-Containern Computer und Benutzer hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="48948-113">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="48948-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="48948-114">In This Section</span></span>

  - [<span data-ttu-id="48948-115">Gewähren von Setupberechtigungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48948-115">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="48948-116">Gewähren von Berechtigungen für die Organisationseinheit in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48948-116">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

<span data-ttu-id="48948-117"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="48948-117"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

