---
title: 'Lync Server 2013: Konfigurieren der medienumgehung, um den Vermittlungsserver immer zu umgehen'
description: 'Lync Server 2013: Konfigurieren Sie die medienumgehung so, dass der Vermittlungsserver immer umgangen wird.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b4981c7b12700d2f0bbf0bf05c8a51623bb8ba9
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433913"
---
# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Configure media bypass in Lync Server 2013 to always bypass the Mediation Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-25_

<div>


> [!NOTE]  
> In diesem Thema wird davon ausgegangen, dass Sie die medienumgehung für alle trunk-Verbindungen mit einem Peer (einem öffentlichen Switched Telephone Network (PSTN)-Gateway, einer IP-Telefonanlage oder einem Session Border Controller (SBC) bei einem Internet-Telefoniedienstanbieter (ITSP)) für eine bestimmte Website oder einen bestimmten Dienst konfiguriert haben, für die Medien den Vermittlungs Server umgehen sollen.<BR>Sie können Medien nicht so konfigurieren, dass der Vermittlungs Server immer umgangen wird, während die Anrufsteuerung ebenfalls aktiviert ist. Diese Einstellungen sind nicht kompatibel und sind daher gegenseitig ausschließende Einstellungen in der Benutzeroberfläche der lync Server-Systemsteuerung.



</div>

Zusätzlich zum Aktivieren der medienumgehung für einzelne trunk-Verbindungen, die einem Peer zum Vermittlungs Server zugeordnet sind, müssen Sie auch die globalen Einstellungen für die medienumgehung konfigurieren. Wenn Sie die Schritte in diesem Thema zum Konfigurieren globaler Einstellungen für die medienumgehung verwenden, wird davon ausgegangen, dass Sie über eine gute Konnektivität zwischen lync-Endpunkten und allen Peers verfügen, für die Sie die medienumgehung für die trunk-Verbindung konfiguriert haben.

Wenn Sie keine gute Verbindung zwischen lync Server-Endpunkten und allen Peers mit dem Vermittlungsserver haben, deren jeweilige trunk-Verbindungen für die medienumgehung aktiviert wurden, müssen Sie die globalen Einstellungen für die medienumgehung so konfigurieren, dass Sie bei Verwendung der medienumgehung Website-und Regionsinformationen verwenden. Auf diese Weise können Sie festlegen, wann Medien den Vermittlungs Server umgeht. Führen Sie dazu die Schritte unter Konfigurieren der [globalen Einstellungen für medienumgehung in lync Server 2013 aus, um Website-und Regionsinformationen zu verwenden](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) und stattdessen [ein Subnetz mit einer Netzwerk Website in lync Server 2013 zu verknüpfen](lync-server-2013-associate-a-subnet-with-a-network-site.md) .

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>So aktivieren Sie die Medienumgehung global zur dauerhaften Umgehung des Vermittlungsservers

1.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Doppelklicken Sie in der Liste auf die Konfiguration **Global**.

4.  Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.

5.  Klicken Sie auf **Immer umgehen**.

6.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren der Medienumgehung in Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Globale Medien Umgehungs Optionen in lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
[Medienumgehung und Vermittlungsserver in Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  


[Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

