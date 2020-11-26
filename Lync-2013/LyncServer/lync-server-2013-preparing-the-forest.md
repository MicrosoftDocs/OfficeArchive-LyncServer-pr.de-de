---
title: 'Lync Server 2013: Vorbereiten der Gesamtstruktur'
description: 'Lync Server 2013: Vorbereiten der Gesamtstruktur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 275d861ebfe7e0350e7baf120b6e6f2bae6a26ad
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49424109"
---
# <a name="preparing-the-forest-for-lync-server-2013"></a>Vorbereiten der Gesamtstruktur für Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Die Gesamtstrukturvorbereitung erstellt Active Directory-globale Einstellungen und-Objekte sowie universelle Active Directory-Gruppen für die Verwendung durch lync Server 2013 und gewährt geeignete Zugriffsberechtigungen für die Active Directory-Objekte. Eine Beschreibung der universellen Gruppen und der globalen Einstellungen und Objekte, die von der Gesamtstrukturvorbereitung erstellt wurden, finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in lync Server 2013 vorgenommen](lync-server-2013-changes-made-by-forest-preparation.md)wurden.

Die Gesamtstrukturvorbereitung erstellt auch Objekte, die Eigenschaftensätze und Anzeigebezeichner enthalten, die von lync Server 2013 verwendet werden, und speichert Sie im Konfigurationscontainer.

<div>


> [!IMPORTANT]  
> Stellen Sie sicher, dass die Schema Vorbereitungs Änderungen auf alle Domänencontroller repliziert wurden, bevor Sie das Verfahren für die Gesamtstrukturvorbereitung durchführen. Wenn die Replikation nicht abgeschlossen ist, tritt ein Fehler auf.



</div>

Wenn Sie eine neue lync Server-Bereitstellung durchführen, müssen Sie die globalen Einstellungen im Container Konfiguration speichern. Wenn Sie ein Upgrade von einer früheren Version durchführen und die globalen Einstellungen weiterhin im Systemcontainer speichern, können Sie den Systemcontainer weiterhin verwenden.

Sie müssen ein Mitglied der Gruppe "Organisations-Admins" oder "Domänen-Admins" für die Gesamtstruktur-Stammdomäne sein, um dieses Verfahren ausführen zu können.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Ausführen der Gesamtstrukturvorbereitung für Lync Server 2013](lync-server-2013-running-forest-preparation.md)

  - [Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

