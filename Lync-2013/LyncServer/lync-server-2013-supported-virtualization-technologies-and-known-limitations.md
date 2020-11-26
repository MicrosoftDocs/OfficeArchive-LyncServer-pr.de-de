---
title: 'Lync Server 2013: Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen'
description: 'Lync Server 2013: Unterstützte Virtualisierungs-Technologien und bekannte Einschränkungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 745fa535462d29342f4c0a58674ee6487db42a6f
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49423561"
---
# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2017-02-06_

Das lync VDI-Plug-in ermöglicht Audio-und Videoanrufe nach unterstützten Virtualisierungstechnologien. Dadurch wird die für Microsoft lync Server 2010 in der [Client-Virtualisierung in Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) -Whitepaper skizzierte Funktionalität erweitert. Gemäß Standardtelefonvorschriften ist auch Unterstützung für E911 enthalten. In den folgenden Abschnitten werden die Virtualisierungstechnologien beschrieben, die vom lync-VDI-Plug-in und den bekannten Funktionseinschränkungen unterstützt werden.

<div>

## <a name="support-for-virtualization-technologies"></a>Unterstützung für Virtualisierungstechnologien

Das lync-VDI-Plug-in unterstützt das vollständige Desktop-Remoting im Szenario des persönlichen virtuellen Desktops, aber nicht im Szenario der Remotedesktopsitzung. Diese Szenarien können wie folgt beschrieben werden:

  - **Unterstützt: Personalisierte virtuelle Desktops oder virtuelle Desktopinfrastruktur (Virtual Desktop Infrastructure, VDI).**   In diesem Szenario melden sich die einzelnen Benutzer bei einem anpassbaren virtuellen Desktop an und können Dateien auf dem Desktop speichern, die sitzungsübergreifend bestehen bleiben. Microsoft Remote Desktop Dienste, VMware Horizon View und Citrix XenDesktop sind Implementierungen, die für die Verwendung mit lync getestet wurden. Informationen zu herstellerspezifischen VDI-Umgebungen und Clienthardware, die von Microsoft getestet wurden, finden Sie unter [für Microsoft lync qualifizierte Infrastruktur](https://go.microsoft.com/fwlink/?linkid=313435).

  - **Nicht unterstützt: Remotedesktopsitzungen.**   In diesem Szenario meldet sich jeder Benutzer bei einer allgemeinen virtuellen Desktopsitzung an, die nicht angepasst werden kann. Zu den Beispielimplementierungen gehören Microsoft-Remotedesktopsitzungen (RDSH) und Citrix XenApp in Kombination mit Citrix Receiver.

Das lync-VDI-Plug-in unterstützt keine anderen Virtualisierungstechnologien wie Application Virtualization, was die Verwendung einer Anwendung ermöglicht, ohne dass die vollständige Anwendung lokal installiert werden muss. Zu den Beispielimplementierungen gehören Citrix XenApp und Microsoft Application Virtualization (App-V). Anwendungsstreaming, Anwendungsremoting und gemischte Virtualisierungsmodi (zum Beispiel Anwendungsremoting in vollem Desktopremoting) werden nicht unterstützt.

Um die Erweiterbarkeit zu ermöglichen, wurde das lync VDI-Plug-in für die Verwendung von plattformunabhängigen APIs mit dem Namen Dynamic Virtual Channels (DVCs) entwickelt. Informationen zu Szenarien, die nicht explizit von lync unterstützt werden, finden Sie unter Support-Statements des VDI-Lösungsanbieters.

</div>

<div>

## <a name="known-feature-limitations"></a>Bekannte Funktionseinschränkungen

Im folgenden sind bekannte Einschränkungen bei der Verwendung von lync 2013 in einer VDI-Umgebung bekannt:

  - Es gibt nur begrenzte Unterstützung für die Anonymisierungs Funktionen für Anruf Delegierungen und Reaktionsgruppen-Agents.

  - Folgende Features werden nicht unterstützt:
    
      - Integrierte Optimierungsseiten für Audio- und Videogeräte
    
      - Mehransicht für Video
    
      - Aufzeichnen von Konversationen
    
      - Remote Desktop Dienste (RDS).
    
      - Anonyme Teilnahme an Besprechungen (also an lync-Besprechungen, die von einer Organisation gehostet werden, die nicht mit Ihrer Organisation in Verbindung steht).
    
      - Verwenden des lync-VDI-Plug-ins zusammen mit einem lync Phone Edition-Gerät.
    
      - Anrufkontinuität im Fall eines Netzwerkausfalls
    
      - Features für benutzerdefinierte Klingeltöne und Wartemusik

  - Das lync-VDI-Plug-in wird in einer Microsoft 365-oder Office 365-Umgebung nicht unterstützt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

