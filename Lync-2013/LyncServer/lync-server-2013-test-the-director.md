---
title: 'Lync Server 2013: Testen des Directors'
description: 'Lync Server 2013: Testen des Directors'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f4cec23be01add5c02cc960cfe68c9256da07d8
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49441217"
---
# <a name="test-the-director-in-lync-server-2013"></a>Testen des Directors in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Zu diesem Zeitpunkt haben Sie einen Director-oder Director-Pool konfiguriert, aber Ihre DNS-SRV-Einträge (Domain Name System) verweisen weiterhin auf Clients, um sich mit einem Pool oder einem Standard Edition-Server anzumelden. Bevor Sie den DNS-Eintrag ändern, damit lync 2013-Clients sich automatisch mithilfe des Directors anmelden, testen Sie einen Client, indem Sie ihn manuell auf den Director verweisen.

<div>

## <a name="to-test-the-deployment"></a>So testen Sie die Bereitstellung

1.  Melden Sie sich bei dem Computer an, auf dem Sie die lync Server-Systemsteuerung mit einem Domänenkonto installiert haben, das Teil der **CSAdministrator** -Gruppe ist.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie im Navigationsbereich auf **Topologie**, und bestätigen Sie in der Spalte **Status** , dass ein grüner Server mit einem Pfeil (also ![Serversymbol mit grünem Pfeil](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server Symbol mit grünem Pfeil")) für Ihren Director-oder Director-Pool vorhanden ist.

4.  Verbinden Sie zwei Clientcomputer, auf denen der lync Server 2013-Client installiert ist, und melden Sie sich mit einem anderen Benutzerkonto an, das für lync Server 2013 auf jedem Computer aktiviert ist.

5.  Klicken Sie auf einem der Clientcomputer auf das Menü **Optionen** , wählen Sie die Gruppe **persönliche** Einstellungen aus, klicken Sie auf **erweitert**, klicken Sie auf **manuelle Konfiguration**, und legen Sie dann den **internen Server Namen oder die IP-Adresse** auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des neuen Director-oder Director-Pools.

6.  Melden Sie sich bei beiden Clients an, und stellen Sie sicher, dass sich der Client, der sich mit dem Director anmeldet, erfolgreich anmelden kann, den Anwesenheitsstatus des anderen Benutzers anzeigen und Sofortnachrichten austauschen können.

</div>

</div>

<span> </span>

</div>

</div>

</div>

