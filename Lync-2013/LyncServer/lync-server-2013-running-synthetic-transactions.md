---
title: 'Lync Server 2013: Ausführen synthetischer Transaktionen'
description: 'Lync Server 2013: Ausführen synthetischer Transaktionen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b0c26024f361dac196319eaf849c1847033cc9
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49442180"
---
# <a name="running-synthetic-transactions-in-lync-server-2013"></a>Ausführen synthetischer Transaktionen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-08-18_

Synthetische Transaktionen werden in der Regel auf zwei Arten durchgeführt. Sie können die CsHealthMonitoringConfiguration-Cmdlets verwenden, um Testbenutzer für die einzelnen registrierungspools einzurichten. Bei diesen Testbenutzern handelt es sich um ein paar Benutzer, die für die Verwendung mit synthetischen Transaktionen vorkonfiguriert wurden. (In der Regel handelt es sich hierbei um Testkonten und nicht um Konten, die tatsächlichen Benutzern gehören.) Bei Testbenutzern, die für einen Pool konfiguriert sind, können Sie eine synthetische Transaktion für diesen Pool ausführen, ohne die Identitäten (und die Anmeldeinformationen für) der am Test beteiligten Benutzerkonten angeben zu müssen.

Oder Sie können eine synthetische Transaktion unter Verwendung tatsächlicher Benutzerkonten ausführen. Wenn beispielsweise zwei Benutzer keine Chatnachrichten austauschen können, können Sie eine synthetische Transaktion unter Verwendung dieser beiden Benutzerkonten (anstelle eines Paars von Testkonten) ausführen und dann versuchen, das Problem zu diagnostizieren und zu beheben. Wenn Sie sich entscheiden, eine synthetische Transaktion mit tatsächlichen Benutzerkonten durchzuführen, müssen Sie die Anmeldenamen und Kennwörter für jeden Benutzer angeben.

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von Watcher-Knotentest Benutzern und Konfigurationseinstellungen in lync Server 2013](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Spezielle Einrichtungsanweisungen für synthetische Transaktionen in lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

