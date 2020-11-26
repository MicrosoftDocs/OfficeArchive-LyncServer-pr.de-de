---
title: 'Lync Server 2013: Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern'
description: 'Lync Server 2013: Erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0ef5850b5e8016e0bd90512db45c2917c16a104
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431876"
---
# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Mit der öffentlichen Instant Messaging-Konnektivität (im) können Benutzer in Ihrer Organisation Chatnachrichten verwenden, um mit Benutzern von Chat Diensten zu kommunizieren, die von öffentlichen Chat Dienstanbietern, einschließlich Windows Live Messenger, Yahoo und AOL, bereitgestellt werden \! .

Lync Server 2013 verfügt über öffentliche Anbieter Konfigurationen für Amerika Online, Windows Live und Yahoo\! Sofortnachrichten. Jeder öffentliche Anbieter ist mit dem vollqualifizierten Domänennamen für den Edge-Server des Anbieters konfiguriert, und die Standard Überprüfungsstufe **ermöglicht Benutzern, nur mit Personen in der Kontaktliste zu kommunizieren, die diesen Anbieter verwenden**.

Als Standardeinstellung ist keiner der öffentlichen Anbieter aktiviert. Sie sollten den Lizenzvertrag und die Bereitstellungs Arbeit abschließen, bevor Sie die öffentlichen Anbieter aktivieren. Sie können den Anbieter aktivieren, bevor Sie die Lizenzierung und Bereitstellungs Arbeit abschließen. Die Benutzer können erst dann mit Kontakten an diesen Anbietern kommunizieren, wenn die Voraussetzungen für die Arbeit erfüllt sind. Details zur Lizenzierung und Bereitstellung öffentlicher Anbieter finden Sie unter Konfigurieren von [Richtlinien zum Steuern des Zugriffs öffentlicher Benutzer in lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).

Gehen Sie wie folgt vor, um öffentliche Anbieter zu erstellen oder zu bearbeiten:

<div>

## <a name="to-create-or-edit-public-providers"></a>So erstellen oder bearbeiten Sie öffentliche Anbieter

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Föderation und externer Zugriff**, und klicken Sie dann auf **SIP-Verbund Anbieter**.

4.  Wenn Sie einen neuen öffentlichen Anbieter erstellen müssen, klicken Sie auf **neu** , und klicken Sie dann auf **öffentlicher Anbieter**.

5.  Wenn Sie einen Eintrag aus der Liste der öffentlichen Anbieter bearbeiten möchten, wählen Sie einen öffentlichen Anbieter aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

6.  Auf der Seite **SIP-Verbund Anbieter bearbeiten** können Sie die folgenden Einstellungen eingeben oder bearbeiten:
    
      - **Aktivieren der Kommunikation mit diesem Anbieter**   Wenn Sie diese Einstellung aktivieren, wird im mit den Benutzern dieses Anbieters aktiviert.
    
      - **Anbietername:**   Eine erforderliche Eigenschaft, geben Sie den Namen des Anbieters ein, wie er in der Liste der SIP-Verbund Anbieter wiedergegeben wird.
    
      - **Access Edge Service (FQDN):**   Eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Access-Edgedienst des Anbieters ein, den Sie konfigurieren. Diese Informationen werden als Standardelement bereitgestellt und sollten nur geändert werden, wenn der öffentliche Anbieter eine Änderung an dem FQDN des Access Edge-Diensts beim öffentlichen Anbieter vornimmt.
    
      - **Standard Überprüfungsstufe:**   Die Standardeinstellung **ermöglicht Benutzern die Kommunikation mit Personen in Ihrer Kontaktliste, die diesen Anbieter verwenden** , beschränkt die Kommunikation auf Kontakte, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.
        
        **Wenn Sie Benutzern erlauben, mit allen Personen zu kommunizieren, die diesen Anbieter verwenden, wird** die Einschränkung entfernt, die Sie erhalten haben und eine Kontakt Einladung akzeptieren müssen. Diese Einstellung beschränkt nicht, wer Sie aus dem Netzwerk des öffentlichen Anbieters kontaktieren kann.

7.  Wenn Sie die Konfiguration der Einstellungen abgeschlossen haben, klicken **Sie zum Speichern auf übernehmen** , oder klicken Sie auf **Abbrechen** , um die Änderungen zu verwerfen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

