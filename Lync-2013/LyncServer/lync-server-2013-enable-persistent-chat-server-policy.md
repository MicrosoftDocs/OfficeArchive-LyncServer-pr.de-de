---
title: 'Lync Server 2013: Aktivieren der Richtlinie für den Server für beständigen Chat'
description: 'Lync Server 2013: Aktivieren der Server Richtlinie für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58da577679795f00492af72b43ca72106d40f4f
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428839"
---
# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Aktivieren der Richtlinie für den Server für beständigen Chat in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

In der lync Server 2013-Systemsteuerung können Sie die Seite " **beständiger Chat** " der Gruppe " **beständiger Chat** " verwenden, um Richtlinien auf globaler, Pool-, Website-oder Benutzerebene zu verwalten, einschließlich der Konfiguration der globalen Standardrichtlinie und dem Erstellen einer oder mehrerer zusätzlicher Benutzer-und Website Richtlinien für Ihre Bereitstellung. Wenn ein Benutzer nach Richtlinie für beständigen Chat Server aktiviert ist, wird die Server Umgebung für beständigen Chat in seinem lync 2013-Client angezeigt.

<div>


> [!NOTE]  
> In der Topologie gelten Website Richtlinien für beständigen Chat Server global, pro Benutzerpool oder pro Benutzer Website oder pro Benutzer.



</div>

Die globale Richtlinie wird automatisch erstellt, wenn Sie den beständigen Chat Server bereitstellen, und Sie kann konfiguriert, aber nicht gelöscht werden. Da die globale Richtlinie auf alle Benutzern angewendet wird, muss sie nicht für jeden Benutzer einzeln festgelegt werden.

Sie können mehrere Website-und Benutzerrichtlinien erstellen und konfigurieren, die zusammen mit der globalen Richtlinie Benutzern für beständigen Chat Server ermöglichen. Pool-und Website-Server Richtlinien für persistente Chats setzen die globale Richtlinie für beständigen Chats außer Kraft, allerdings nur für Benutzer dieser Website. Benutzerrichtlinien setzen sowohl die globale als auch die Pool- und Standortrichtlinien für diejenigen Benutzer außer Kraft, denen die Benutzerrichtlinie zugewiesen wird.

<div>


> [!NOTE]  
> Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um der Topologie Unterstützung für beständigen Chat Server hinzuzufügen und dann die Topologie zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigem Chat Server zu Ihrer Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren der globalen Richtlinie für beständigen Chat in Lync Server 2013](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Erstellen einer Standortrichtlinie für beständigen Chat in Lync Server 2013](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Erstellen einer Benutzerrichtlinie für beständigen Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Anwenden einer Richtlinie für beständigen Chat auf einen Benutzer oder eine Benutzergruppe in Lync Server 2013](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

