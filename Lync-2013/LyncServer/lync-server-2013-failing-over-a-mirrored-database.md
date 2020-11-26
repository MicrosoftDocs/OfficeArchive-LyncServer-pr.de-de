---
title: 'Lync Server 2013: Ausführen eines Failovers für eine gespiegelte Datenbank'
description: 'Lync Server 2013: Failover einer gespiegelten Datenbank'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc7c401157c79762f674721ca717296c0fe502db
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428293"
---
# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Ausführen eines Failovers für eine gespiegelte Datenbank in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-03-14_

Wenn Sie Ihre Back-End-Datenbank so konfiguriert haben, dass die synchronisierte Spiegelung mit einem Zeugen verwendet wird, ist das Failover automatisch. Wenn Sie die synchronisierte Spiegelung ohne Zeugen konfiguriert haben, können Sie die folgenden Verfahren zum Failover und Failback der Datenbank verwenden. Sie können diese Verfahren auch zum manuellen Failover und Failback Ihrer Datenbanken verwenden, selbst wenn Sie einen Zeugen konfiguriert haben.

<div>

## <a name="to-fail-over-your-back-end-database"></a>So führen Sie einen Failover für Ihre Back-End-Datenbank aus

1.  Bevor Sie einen Failover durchführen, können Sie ermitteln, welche Back-End-Datenbank der Prinzipal ist und welche die Spiegelung ist, indem Sie das folgende Cmdlet eingeben:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  Wenn der zentrale Verwaltungsspeicher in diesem Pool gehostet wird, geben Sie das folgende Cmdlet ein, um zu ermitteln, welches der Prinzipal ist und welches die Spiegelung für den zentralen Verwaltungsspeicher ist:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  Durchführen des Failovers der Benutzerdatenbank:
    
      - Wenn der primäre Fehler aufgetreten ist und Sie einen Failover zur Spiegelung durchführen, geben Sie Folgendes ein:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - Wenn der Spiegel Fehler aufgetreten ist und Sie das primäre Failover durchführen, geben Sie Folgendes ein:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  Wenn der Pool den zentralen Verwaltungs Server hostet, führen Sie das Failover des zentralen Verwaltungsspeichers durch.
    
      - Wenn der primäre Fehler aufgetreten ist und Sie einen Failover zur Spiegelung durchführen, geben Sie Folgendes ein:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - Wenn der Spiegel Fehler aufgetreten ist und Sie das primäre Failover durchführen, geben Sie Folgendes ein:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

