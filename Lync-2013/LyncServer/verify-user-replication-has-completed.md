---
title: Überprüfen, ob die Benutzerreplikation abgeschlossen wurde
description: Überprüfen Sie, ob die Benutzerreplikation abgeschlossen ist.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bca44fcce811c29b1633bd4d3a39f832851885
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49446072"
---
# <a name="verify-user-replication-has-completed"></a>Überprüfen, ob die Benutzerreplikation abgeschlossen wurde

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Bei der Ausführung des Cmdlets **Move-CsUser** tritt möglicherweise ein Fehler auf, da die Benutzerinformationen zwischen den Active Directory-Domänendiensten (AD DS) und den lync Server 2013-Datenbanken nicht synchronisiert sind, weil die anfängliche Replikation unvollständig ist. Die Zeit, die für den erfolgreichen Abschluss der ersten Synchronisierung des lync Server 2013-Benutzerreplikationsdiensts benötigt wird, hängt von der Anzahl der Domänencontroller ab, die in der Active Directory-Gesamtstruktur gehostet werden, die den lync Server 2013-Pool hostet. Der erst Synchronisierungsvorgang des lync Server 2013-Benutzerreplikationsdiensts erfolgt, wenn der lync Server 2013-Front-End-Server zum ersten Mal gestartet wird. Danach basiert die Synchronisierung auf dem Intervall des Benutzerreplikationsdiensts. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation abgeschlossen ist, bevor Sie das Cmdlet **Move-CsUser** ausführen.

<div>

## <a name="to-verify-user-replication-has-completed"></a>So überprüfen Sie, ob die Benutzerreplikation abgeschlossen ist

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Klicken Sie auf das **Startmenü** , und klicken Sie dann auf **Ausführen**.

3.  Geben Sie **eventvwr.exe** ein, und klicken Sie dann auf **OK**.

4.  Klicken Sie in der Ereignisanzeige auf **Anwendungen und Dienstprotokolle** , um Sie zu erweitern, und wählen Sie dann lync Server aus.

5.  Klicken Sie im Bereich **Aktionen** auf **Aktuelles Protokoll filtern**.

6.  Klicken Sie in der Liste **Ereignisquellen** auf **ls-Benutzer Replikations** Dienst.

7.  **\<All Event IDs\>** Geben Sie **30024** ein, und klicken Sie dann auf **OK**.

8.  Suchen Sie in der Liste Gefilterte Ereignisse auf der Registerkarte **Allgemein** nach einem Eintrag, der besagt, dass die Benutzerreplikation erfolgreich abgeschlossen wurde.

</div>

</div>

<span> </span>

</div>

</div>

</div>

