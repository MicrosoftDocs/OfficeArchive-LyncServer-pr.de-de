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
# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Konfigurieren von Einwahlnummern für Einwahlkonferenzen in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2011-07-17_

Beim Bereitstellen von Einwahlkonferenzen müssen Sie Telefonnummern einrichten, die Benutzer aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) wählen können, um am Audioteil einer Konferenz teilzunehmen. Diese Zugriffsnummern für die Einwahl werden in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.

Vor dem Erstellen von Zugriffsnummern für die Einwahl müssen Sie zunächst die Regionen Ihrer Einwahlkonferenzen planen und anschließend Wählpläne für die Regionen konfigurieren. Details zu Regionen finden Sie unter [Anforderungen für Einwahlkonferenzen in lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in der Planungsdokumentation. Details zum Konfigurieren von Wählplänen für Einwahlkonferenzen finden Sie unter [Konfigurieren von Wählplänen für Einwahlkonferenzen in lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).

<div>


> [!NOTE]  
> Sie können erst dann eine neue Einwahl Zugriffsnummer verwenden, wenn die Active Directory-Domänendienste (AD &nbsp; DS)-Replikation dieser Zugriffsnummer abgeschlossen ist. Die Replikation kann mehrere Stunden in Anspruch nehmen.



</div>

<div>


> [!NOTE]  
> Nach dem Erstellen von Zugriffsnummern für die Einwahl können Sie den Anzeigenamen für die Active Directory-Kontaktobjekte modifizieren, sodass Benutzer die richtige Zugriffsnummer einfacher identifizieren können. Verwenden Sie das Cmdlet " <STRONG>Satz-CsDialInConferencingAccessNumber</STRONG> ", um den Anzeigenamen zu ändern. Active Directory-Objekte sollten nicht manuell geändert werden. Details zum Ändern einer Zugriffsnummer finden Sie unter Dokumentation zur lync Server-Verwaltungsshell für das Cmdlet " <STRONG>Satz-CsDialInConferencingAccessNumber</STRONG> ".



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

[Erstellen oder Ändern einer Einwahlnummer für Einwahlkonferenzen in Lync Server 2013](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Anforderungen für Einwahlkonferenzen in lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  


[Konfigurieren von Wählplänen für Einwahlkonferenzen in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

