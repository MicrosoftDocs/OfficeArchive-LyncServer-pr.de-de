---
title: 'Lync Server 2013: Active Directory-Unterstützung'
description: Active Directory-Unterstützung für lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 349862b2f541ef3033c9a725a6ff04c6a4e219f7
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49439408"
---
# <a name="active-directory-support-in-lync-server-2013"></a>Active Directory-Unterstützung in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-12-04_

Die lokalen Topologien für Active Directory-Domänendienste, die von lync Server 2013 unterstützt werden, sind wie folgt:

  - Einzelne Gesamtstruktur mit einzelner Domäne

  - Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen

  - Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces

  - Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur

  - Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur

<div>


> [!NOTE]  
> Lync Server 2013 unterstützt keine Single-Label-Domänen. Beispielsweise wird eine Gesamtstruktur mit einer Stammdomäne mit dem Namen " <STRONG>contoso. local</STRONG> " unterstützt, aber eine Stammdomäne mit einer einzelnen Bezeichnung, die " <STRONG>local</STRONG> " heißt, wird nicht unterstützt. Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 300684, "Informationen zum Konfigurieren von Windows für Domänen mit DNS-Namen mit einer Bezeichnung" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A> .



</div>

<div>


> [!NOTE]  
> Lync Server 2013 unterstützt keine Umbenennung von Domänen. Wenn Sie eine Domäne umbenennen müssen, in der lync Server bereitgestellt wird, müssen Sie zunächst lync Server deinstallieren, dann die Domäne umbenennen und dann lync Server erneut installieren.



</div>

Ausführliche Informationen zu unterstützten Topologien und Anforderungen für lokale Bereitstellungen finden Sie unter [Anforderungen für Active Directory-Domänendienste, Unterstützung und Topologien in lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in der Planungsdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

