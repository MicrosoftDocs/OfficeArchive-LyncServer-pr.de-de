---
title: 'Lync Server 2013: Konfigurieren von Einwahlnummern für Einwahlkonferenzen'
description: 'Lync Server 2013: Konfigurieren von Zugriffsnummern für Einwahlkonferenzen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0edb3492c243b36b69c4b48df8c22adc4ece7999
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49395147"
---
# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="84613-103">Konfigurieren von Einwahlnummern für Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84613-103">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="84613-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="84613-104">

<span> </span></span></span>

<span data-ttu-id="84613-105">_**Letztes Änderungsdatum des Themas:** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="84613-105">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="84613-106">Beim Bereitstellen von Einwahlkonferenzen müssen Sie Telefonnummern einrichten, die Benutzer aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) wählen können, um am Audioteil einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="84613-106">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="84613-107">Diese Zugriffsnummern für die Einwahl werden in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="84613-107">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="84613-108">Vor dem Erstellen von Zugriffsnummern für die Einwahl müssen Sie zunächst die Regionen Ihrer Einwahlkonferenzen planen und anschließend Wählpläne für die Regionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="84613-108">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="84613-109">Details zu Regionen finden Sie unter [Anforderungen für Einwahlkonferenzen in lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="84613-109">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="84613-110">Details zum Konfigurieren von Wählplänen für Einwahlkonferenzen finden Sie unter [Konfigurieren von Wählplänen für Einwahlkonferenzen in lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="84613-110">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="84613-111">Sie können erst dann eine neue Einwahl Zugriffsnummer verwenden, wenn die Active Directory-Domänendienste (AD &nbsp; DS)-Replikation dieser Zugriffsnummer abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="84613-111">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="84613-112">Die Replikation kann mehrere Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="84613-112">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="84613-113">Nach dem Erstellen von Zugriffsnummern für die Einwahl können Sie den Anzeigenamen für die Active Directory-Kontaktobjekte modifizieren, sodass Benutzer die richtige Zugriffsnummer einfacher identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="84613-113">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="84613-114">Verwenden Sie das Cmdlet " <STRONG>Satz-CsDialInConferencingAccessNumber</STRONG> ", um den Anzeigenamen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="84613-114">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="84613-115">Active Directory-Objekte sollten nicht manuell geändert werden.</span><span class="sxs-lookup"><span data-stu-id="84613-115">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="84613-116">Details zum Ändern einer Zugriffsnummer finden Sie unter Dokumentation zur lync Server-Verwaltungsshell für das Cmdlet " <STRONG>Satz-CsDialInConferencingAccessNumber</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="84613-116">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="84613-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="84613-117">In This Section</span></span>

[<span data-ttu-id="84613-118">Erstellen oder Ändern einer Einwahlnummer für Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84613-118">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="84613-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84613-119">See Also</span></span>


[<span data-ttu-id="84613-120">Anforderungen für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84613-120">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="84613-121">Konfigurieren von Wählplänen für Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84613-121">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

<span data-ttu-id="84613-122"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="84613-122"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

