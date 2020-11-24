---
title: 'Lync Server 2013: Features und Funktionen für Front-End-Server, Chat und Anwesenheit'
description: 'Lync Server 2013: Features und Funktionen von Front-End-Servern, Instant Messaging und Anwesenheitsinformationen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5c8bc3db255228da3366eb5aa142cd5adc233d1
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49393978"
---
# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Features und Funktionen für Front-End-Server, Chat und Anwesenheit in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-17_

Front-End-Server bieten die meisten lync Server-Funktionen. Es stehen zwei Versionen zur Verfügung: lync Server Enterprise Edition, die in erster Linie für größere Organisationen konzipiert ist, und lync Server Standard Edition, die in erster Linie für kleinere Organisationen konzipiert ist, die eine kleinere Hardware-Investition benötigen und keine höhere Verfügbarkeit erfordern. Beide Editionen unterstützen alle lync Server-Arbeitsauslastungen, einschließlich Chat, Anwesenheit, Konferenz und Enterprise-VoIP.

Mit der Chatfunktion können Benutzer auf ihren Computern in Echtzeit über textbasierte Nachrichten miteinander kommunizieren. Es werden sowohl Chatsitzungen mit zwei Teilnehmern als auch Sitzungen mit mehreren Teilnehmern unterstützt. Ein Teilnehmer an einer Chatsitzung mit zwei Teilnehmern kann der Unterhaltung jederzeit einen dritten Teilnehmer hinzufügen. Wenn dies geschieht, ändert sich das Unterhaltungsfenster, um Konferenzfunktionen zu unterstützen.

<div>


> [!IMPORTANT]
> Lync-und Communicator-Clients werden, wenn Sie an einer 1:1-Kommunikation beteiligt sind, häufig als Peer-to-Peer bezeichnet. Technisch gesehen kommunizieren die beiden Clients in einer 1:1-Konversation mit der Instant Messaging-Multipoint-Steuereinheit (IMMCU) in der Mitte. Die IMMCU ist eine Komponente des Front-End-Servers. Wenn Sie den IMMCU in den erforderlichen Kommunikations Workflow einfügen, können Sie die Anrufdetailaufzeichnung und andere Features, die der Front-End-Server ermöglicht, aufzeichnen. Die Kommunikation erfolgt von einem dynamischen Quell Port auf dem Client zum Front-End-Serverport TLS/TCP/5061 (unter der Voraussetzung, dass die empfohlene Transportschichtsicherheit verwendet wird). Die Peer-to-Peer-Kommunikation (ebenso wie die Chat Unterhaltung mit mehreren Teilnehmern) ist im Entwurf nur möglich, wenn lync Server und IMMCU aktiv und verfügbar sind.



</div>

*Anwesenheits* Informationen bieten Benutzern Informationen über den Status anderer Personen im Netzwerk. Der Anwesenheitsstatus eines Benutzers bietet Informationen, um anderen zu helfen, zu entscheiden, ob er versuchen soll, den Benutzer zu kontaktieren, und ob er Sofortnachrichten, Telefone oder e-Mails verwenden soll. Anwesenheitsinformationen unterstützt die sofortige Kommunikation, wenn möglich, bietet aber auch Informationen darüber, ob sich ein Benutzer in einer Besprechung oder außerhalb des Büros befindet, was darauf hinweist, dass eine sofortige Kommunikation nicht möglich ist. Dieser Anwesenheitsstatus wird in lync und anderen Anwendungen mit Anwesenheitsanzeige als Anwesenheitssymbol angezeigt, einschließlich des Microsoft Outlook-Messaging-und Zusammenarbeits Clients, Microsoft SharePoint Technologies, Microsoft Word und Microsoft Excel-Tabellenkalkulationssoftware. Das Anwesenheitssymbol steht für die aktuelle Verfügbarkeit und Kommunikationsbereitschaft des Benutzers.

</div>

<span> </span>

</div>

</div>

</div>

