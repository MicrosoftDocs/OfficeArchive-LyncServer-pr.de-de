---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für AutoErmittlung'
description: 'Lync Server 2013: Konfigurieren der Unterstützung für AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23991f2f9467035f4ba461ff1b6a84fa8ed1a11d
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49432611"
---
# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>Konfigurieren der Unterstützung für die AutoErmittlung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-21_

Der **AutoErmittlungsdienst** für lync Server-Webdienste erschien zunächst im kumulativen Update für lync Server 2010: November 2011. Dieses Update wurde von der ersten Version von lync Mobile-Clients begleitet. Der AutoErmittlungsdienst hat die Mobilitätsdienste, den so genannten MCX-Dienst, verfügbar gemacht.

Der AutoErmittlungsdienst fungiert als einzelner Standort für alle Clients, um Informationen zu den verfügbaren Diensten und Features anzufordern und zu erfahren, wie Sie sich an die Mitarbeiter wenden können – entweder durch einen vollqualifizierten Domänennamen oder einen webuniform Resource Locator-Verweis. Die AutoErmittlung macht eine Reihe von Features verfügbar, und jeder Client stellt Anforderungen basierend auf den Features, die der Client verwenden kann, zur Verfügung. Beispielsweise wird ein lync 2013-Desktop Client autodiscvoer verwenden, um die externen Webdienste zu ermitteln, verwendet aber nicht die Mobilitätsdienste (MCX). Damit Ihre Clients die für Sie verfügbaren Features richtig definieren und aktivieren können, sollten die Szenarien definiert werden, die es einem Client ermöglichen, Auto Ermittlungs Einträge effektiv zu finden und zu verwenden. Zur Verwendung von autodoscover erfordert Ihre Bereitstellung, dass ein Reverse Proxy die lync Server-Webdienste veröffentlicht, dass DNS-Einträge für das Auflösen von DNS-Abfragen für den lync Server-AutoErmittlungsdienst und lync Server-Webdienste konfiguriert sind und dass die Zertifikatdienste für Ihr spezifisches Szenario ordnungsgemäß konfiguriert sind.

<div>


> [!TIP]  
> Technische Informationen dazu, welche Elemente in der Auto Ermittlungsanforderung/-Antwort ausgeführt werden, finden Sie unter <A href="lync-server-2013-understanding-autodiscover.md">Grundlegendes zu AutoErmittlung in lync Server 2013</A>.



</div>

Die folgenden Informationen und Tabellen definieren pro Szenario, welche Konfigurationen (sofern vorhanden) Sie implementieren müssen, um die vollständige und effektive Verwendung des AutoErmittlungsdiensts bereitzustellen. Die Informationen in den folgenden Themen sind spezifisch für Microsoft lync Server 2013. Wenn Sie nach Anleitungen zum Planen der Mobilität für lync Server 2010 suchen, lesen Sie [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113) . Informationen zum Bereitstellen von Mobility für lync Server 2010 finden Sie unter [https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren von DNS für die AutoErmittlung in lync Server 2013](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Konfigurieren von Zertifikaten für die AutoErmittlung in lync Server 2013](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Konfigurieren eines Reverse-Proxys für die AutoErmittlung in lync Server 2013](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [Konfigurieren der AutoErmittlung in lync Server 2013 für hybridbereitstellungen](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

