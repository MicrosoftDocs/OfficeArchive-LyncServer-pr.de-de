---
title: 'Lync Server 2013: Erstellen oder Bearbeiten eines neuen Chatrooms'
description: 'Lync Server 2013: Erstellen oder Bearbeiten eines neuen Chatrooms'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d822eb05993f77c57200e29364f0a6a68509450b
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431463"
---
# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="b3977-103">Erstellen oder Bearbeiten eines neuen Chatrooms in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3977-103">Creating or editing a new room in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="b3977-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="b3977-104">

<span> </span></span></span>

<span data-ttu-id="b3977-105">_**Letztes Änderungsdatum des Themas:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="b3977-105">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="b3977-106">Die Konfiguration beständiger Chatrooms wird häufig von Benutzern gehandhabt. ein beständiger Chat Administrator konfiguriert oder verwaltet in der Regel keine Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="b3977-106">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="b3977-107">Windows PowerShell-Cmdlets zum Verwalten von Räumen stehen nur **CsPersistentChatAdministrator** -Administratoren zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b3977-107">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="b3977-108">Benutzer, die in einer bestimmten Kategorie **Schöpfer** sind, können den lync-Client verwenden, um Räume zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b3977-108">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="b3977-109">Benutzer, die als Manager für einen bestimmten Chatroom festgelegt wurden, können auch die laufende Verwaltung des Raums durchführen, beispielsweise das Bearbeiten der Raumeigenschaften oder der Mitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="b3977-109">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="b3977-110">Administratoren für beständigen Chat können auch Ersteller sein, und Sie unterliegen nicht den Einschränkungen, die den Erstellern auferlegt werden.</span><span class="sxs-lookup"><span data-stu-id="b3977-110">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="b3977-111">Wenn Sie ein beständiger Chat-Administrator sind, können Sie optional eine Benutzeroberfläche verwenden, um Chatrooms zu erstellen und zu verwalten, anstatt Windows PowerShell-Cmdlets zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b3977-111">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="b3977-112">Aktivieren Sie dazu einen Administrator für beständigen Chat Server, und verwenden Sie dann den lync-Client, um Chatrooms zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b3977-112">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="b3977-113">Wenn Sie einen benutzerdefinierten Raum Verwaltungs Workflow für Ihre Benutzer erstellen möchten, können Sie die **RoomManagementUrl** -Eigenschaft für die Konfiguration des beständigen Chat Servers so festlegen, dass Benutzer vom lync-Client zu Ihrer benutzerdefinierten Lösung umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b3977-113">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="b3977-114">Weitere Informationen zum Konfigurieren von Chatrooms mithilfe der Windows PowerShell-Befehlszeilenschnittstelle finden Sie unter "Room Management" in [Konfigurieren des beständigen Chat Servers mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="b3977-114">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="b3977-115">Details zum Konfigurieren von Chatrooms finden Sie unter [Konfigurieren von Räumen in lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b3977-115">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3977-116">Der beständige Chat Server ermöglicht Benutzern, Chatrooms für eine bestimmte Website zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b3977-116">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="b3977-117">Benutzer können Chatrooms jedoch nicht auf anderen Websites innerhalb derselben Topologie erstellen oder verwalten.</span><span class="sxs-lookup"><span data-stu-id="b3977-117">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="b3977-118">Stellen Sie sicher, dass Sie für alle Websites in Ihrer Organisation Chatroom-Ersteller und-Manager angeben.</span><span class="sxs-lookup"><span data-stu-id="b3977-118">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b3977-119">Benutzer, die sich in einer Überlebenden lync Server-Branch-Appliance befinden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b3977-119">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



<span data-ttu-id="b3977-120"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="b3977-120"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

