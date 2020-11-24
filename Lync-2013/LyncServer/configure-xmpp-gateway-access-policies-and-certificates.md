---
title: Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways
description: Konfigurieren Sie die Zugriffsrichtlinien und Zertifikate des XMPP-Gateways.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e958100501ad9ca87d1ab970162f4be8c7692a99
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394098"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-15_

Die XMPP-Föderation definiert eine externe Bereitstellung, die auf dem Extensible Messaging and Presence Protocol (XMPP) basiert. Eine XMPP-Konfiguration ermöglicht lync-Benutzern den Zugriff auf XMPP-Domänenbenutzer durch:

  - Chat und Anwesenheit – nur Person zu Person

  - Erstellen von XMPP-verbundkontakten im lync-Client

Wenn Sie Richtlinien für die Unterstützung von Verbundpartnern für Extensible Messaging and Presence Protocol (XMPP) konfigurieren, gelten die Richtlinien für Benutzer von XMPP-Verbunddomänen, nicht aber für Benutzer von SIP-Chat Diensten (Session Initiation Protocol) (im)-Dienstanbieter (beispielsweise Windows Live) oder SIP-Verbunddomänen. Sie konfigurieren einen XMPP-Verbund Partner für jede XMPP-Verbunddomäne, die es Ihren Benutzern ermöglichen soll, Kontakte hinzuzufügen und mit Ihnen zu kommunizieren. Sobald die Richtlinien vorhanden sind, müssen Sie die XMPP-Gateway-Zertifikate konfigurieren.

<div>


> [!NOTE]  
> Um mit der XMPP-Gateway-Migration zu beginnen, müssen Sie das lync Server 2013 XMPP-Gateway bereitstellen und Zugriffsrichtlinien konfigurieren, um Benutzer für lync Server 2013 XMPP-Gateway zu aktivieren. Bevor Sie diese Schritte ausführen, müssen alle Benutzer in die lync Server 2013-Bereitstellung verschoben werden. Ausführliche Informationen finden Sie unter <A href="configure-xmpp-gateway-on-lync-server-2013.md">Konfigurieren des XMPP-Gateways unter lync Server 2013</A>.



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>Konfigurieren einer Richtlinie für den externen Zugriff zum Aktivieren von Benutzern für lync Server 2013 XMPP-Gateway

1.  Öffnen Sie die Lync Server-Systemsteuerung.

2.  Klicken Sie in der linken Navigationsleiste auf **Föderation und externer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.

3.  Klicken Sie auf **neu** , und klicken Sie dann auf **Benutzerrichtlinie**.

4.  Geben Sie einen Namen für die Benutzerrichtlinie für den externen Zugriff ein.

5.  Geben Sie eine Beschreibung für die Benutzerrichtlinie für den externen Zugriff an.

6.  Wählen Sie **Kommunikation mit Verbundbenutzern aktivieren** aus.

7.  Wählen Sie **Kommunikation mit XMPP-Verbundbenutzern aktivieren** aus.

8.  Klicken Sie auf **Commit** , um Ihre Änderungen an der Website-oder Benutzerrichtlinie zu speichern.

</div>

</div>

<span> </span>

</div>

</div>

</div>

