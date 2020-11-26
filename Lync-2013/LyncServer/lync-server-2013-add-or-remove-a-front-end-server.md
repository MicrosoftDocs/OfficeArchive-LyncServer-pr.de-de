---
title: 'Lync Server 2013: Hinzufügen oder Entfernen eines Front-End-Servers'
description: 'Lync Server 2013: Hinzufügen oder Entfernen eines Front-End-Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 297bbf42dbba3d4f9926fd5ab9e0d7ed79349dc4
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49439275"
---
# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Add or remove a Front End Server in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-01-21_

Wenn Sie einen Front-End-Server zu einem Pool hinzufügen oder einen Front-End-Server aus einem Pool entfernen, müssen Sie den Pool erneut starten. Gehen Sie beim Hinzufügen oder Entfernen eines Front-End-Servers wie folgt vor, um eine Unterbrechung des Diensts für Benutzer zu verhindern.

<div>


> [!NOTE]  
> Wenn Sie neue Server zum Pool hinzufügen, aktualisieren Sie Ihre neuen Poolserver, sodass diese im Hinblick auf das kumulative Update auf demselben Stand sind wie die bereits bestehenden Server in dem Pool.



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>So können Sie Front-End-Server hinzufügen oder entfernen

1.  Wenn Sie alle Front-End-Server entfernen, beenden Sie zunächst neue Verbindungen mit diesen Servern. Dazu können Sie das folgende Cmdlet verwenden:
    
        Stop-CsWindowsServices -Graceful

2.  Wenn die entfernten Server keine aktuellen Sitzungen haben, beenden Sie die lync Server-Dienste.

3.  Öffnen Sie den Topologie-Generator, und fügen Sie die erforderlichen Server hinzu, oder entfernen Sie Sie.

4.  Veröffentlichen Sie die Topologie.

5.  Wenn der Pool von zwei Front-End-Servern auf mehr als zwei oder von mehr als zwei Servern auf genau zwei hinausgegangen ist, müssen Sie das folgende Cmdlet eingeben:
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    Wenn der Pool über drei oder mehr Server verfügt, müssen mindestens drei dieser Server ausgeführt werden, wenn Sie dieses Cmdlet eingeben.

6.  Starten Sie alle Front-End-Server im Pool einzeln neu.

</div>

</div>

<span> </span>

</div>

</div>

</div>

