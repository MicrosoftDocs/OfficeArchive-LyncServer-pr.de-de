---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
description: Konfigurieren von vertrauenswürdigen Anwendungsservern.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39f439ea3e5996e0a3464540069024b70c415e3d
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394434"
---
# <a name="configure-trusted-application-servers"></a>Konfigurieren von vertrauenswürdigen Anwendungsservern

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-11_

Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie den Pool für den nächsten Hop als lync Server 2013-Pool einrichten. In einer gemischten Umgebung werden sowohl der Legacy lync Server 2010-Pool als auch der lync Server 2013-Pool in der Dropdownliste angezeigt. Das Auswählen des Legacy Pools wird nicht unterstützt.

**Auswählen von lync Server 2013 als nächster Hop beim Erstellen eines vertrauenswürdigen Anwendungsservers**

1.  Öffnen Sie den Topologie-Generator.

2.  Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver** , und klicken Sie auf **neuer vertrauenswürdiger Anwendungs Pool**.

3.  Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, und wählen Sie aus, ob es sich um einen Einzelserver oder um einen Server mit mehreren Servern handelt.

4.  Klicken Sie auf **Weiter**.

5.  Wählen Sie auf der Seite **Nächster Hop auswählen** in der Liste den lync Server 2013-Front-End-Pool aus.

6.  Klicken Sie auf **Fertig stellen**.

7.  Wählen Sie den obersten Knoten **lync Server** aus, und wählen Sie im Menü **Aktion** die Option **veröffentlichen** aus.
    
    Überprüfen Sie, ob der **Vertrauenswürdige Anwendungs Pool** erfolgreich erstellt wurde und dem richtigen Front-End-Pool zugeordnet ist.

</div>

<span> </span>

</div>

</div>

</div>

