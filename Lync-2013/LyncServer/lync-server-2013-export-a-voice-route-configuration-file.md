---
title: 'Lync Server 2013: Exportieren einer sprach Routen-Konfigurationsdatei'
description: 'Lync Server 2013: Exportieren einer sprach Routen-Konfigurationsdatei'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bf342e11be41015df3cfd76f6a875381cb8b64
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428370"
---
# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a>Exportieren einer sprach Routen-Konfigurationsdatei in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Wenn Sie Ihre sprach Routingkonfiguration speichern möchten, ohne Sie zu veröffentlichen, führen Sie die folgenden Schritte aus, um die Konfigurations Export-und-Importbefehle in lync Server Control Panel zu verwenden, um eine Momentaufnahme Ihrer VoIP-Routingkonfiguration zu speichern und abzurufen. Wenn Sie eine sprach Routing-Konfigurationsdatei (. vcfg) importieren, aber Änderungen an der sprach Routingkonfiguration auf dem Server in der Zwischenzeit vorgenommen wurden, zeigen die Seiten in der Gruppe **VoIP-Routing** in der lync Server-Systemsteuerung an, dass nicht festgeschriebene Änderungen an der sprach Weiterleitung vorhanden sind. Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.

Wenn Sie Änderungen an den Einstellungen auf einer beliebigen Seite innerhalb der Gruppe vorgenommen haben, werden die Änderungen in der exportierten sprach Konfigurationsdatei (vcfg) gespeichert. So können Sie während mehrerer Sitzungen Änderungen an der sprach Routingkonfiguration vornehmen, bevor Sie die Änderungen veröffentlichen.

<div>

## <a name="to-export-a-voice-routing-configuration"></a>So exportieren Sie eine VoIP-Routingkonfiguration

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.

4.  Klicken Sie im Menü **Aktionen** auf **Konfiguration exportieren**.

5.  Geben Sie einen Speicherort und Dateinamen an und klicken Sie auf **Speichern**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Importieren einer VoIP-Routenkonfigurationsdatei in Lync Server 2013](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

