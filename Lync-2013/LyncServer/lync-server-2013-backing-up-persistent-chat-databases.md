---
title: 'Lync Server 2013: Sichern von persistenten Chat Datenbanken'
description: 'Lync Server 2013: sichern beständiger Chat Datenbanken.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9885eaf0065f5b558922c056fb1f669a5b821460
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49438022"
---
# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Sichern von persistenten Chat Datenbanken in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-17_

Beständiger Chatroom-Inhalt wird in der persistent Chat-Datenbank (MGC. mdf) gespeichert. Es handelt sich hierbei um unternehmenswichtige Daten, die regelmäßig gesichert werden sollten. Zusätzlich zu den Chatroom-Inhalten speichert die persistente Chat-Datenbank auch Informationen zu den Prinzipalen (wie Benutzer und Benutzergruppen) sowie zu den Rollen und dem Zugriff, die Sie für Chatrooms und Chatrooms haben.

Es gibt zwei Möglichkeiten, persistente Chat-Daten zu sichern.

  - Die SQL Server-Sicherung

  - Das `Export-CsPersistentChatData` Cmdlet, das persistente Chat-Daten als Datei exportiert

Daten, die mit der SQL Server-Sicherung erstellt werden, erfordern erheblich mehr Speicherplatz – möglicherweise 20 mal mehr – als die von Ihnen erstellten `Export-CsPersistentChatData` , aber die SQL Server-Sicherung ist wahrscheinlicher eine Prozedur, mit der Administratoren vertraut sind.

</div>

<span> </span>

</div>

</div>

</div>

