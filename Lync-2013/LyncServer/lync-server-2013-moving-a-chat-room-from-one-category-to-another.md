---
title: 'Lync Server 2013: Verschieben eines Chatrooms von einer Kategorie in eine andere'
description: 'Lync Server 2013: Verschieben eines Chatrooms von einer Kategorie in eine andere.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4066732a90a94414b55d6a567fde0d496e4faf13
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425268"
---
# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>Verschieben eines Chatrooms von einer Kategorie in eine andere in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Wir empfehlen, dass Sie die Kategorie eines beständigen Chatrooms nach dem Erstellen des Chatrooms nicht ändern. Wenn der Chatroom-Manager jedoch über **Creator** -Privilegien in einer anderen Kategorie verfügt, kann er den Chatroom von einer Kategorie in eine andere verschieben. Der Raum wird nicht gelöscht und neu erstellt. Es handelt sich um eine Änderung der Zuordnung innerhalb der Datenbank.

Das Ändern einer Chatroom-Kategorie sollte selten erfolgen. Eine Kategorie bestimmt die zulässige Mitgliedschaft für den Chatroom, sodass beim Verschieben eines Chatrooms in eine andere Kategorie alle Systemzugriffssteuerungslisten (SACLs), die von der neuen Kategorie nicht mehr unterstützt werden, gelöscht werden. Wenn ein Benutzer beispielsweise Mitglied des Chatrooms und nicht mehr ein **AllowedMember** in der neuen Kategorie ist, wird die Raummitgliedschaft geändert, und der Benutzer wird aus dem Chatroom entfernt.

Ausführliche Informationen zum Verschieben eines Chatrooms mithilfe der Windows PowerShell-Befehlszeilenoberfläche finden Sie unter "Room Management" in [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Details zum Konfigurieren von Chatrooms finden Sie unter [Konfigurieren von Räumen in lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

