---
title: 'Lync Server 2013: Konfigurieren von Archivierungsoptionen auf globaler Ebene'
description: 'Lync Server 2013: Konfigurieren von Archivierungsoptionen auf globaler Ebene'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44b8939ec95d00afa2aa7632f4555bc6fef89834
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433339"
---
# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a>Konfigurieren von Archivierungsoptionen auf globaler Ebene in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

Wenn Sie Ihrer Topologie Archivierungsvorgänge hinzufügen und die Topologie veröffentlichen, erstellt lync Server eine globale Konfiguration für die Archivierung. Standardmäßig sind in der globalen Konfiguration keine Archivierungsoptionen aktiviert. Die globale Konfiguration bestimmt, welche Optionen für Ihre gesamte Bereitstellung aktiviert werden, außer Sie richten Standort- oder Poolkonfigurationen ein, die die globale Konfiguration außer Kraft setzen.

Ausführliche Informationen zur Funktionsweise von Archivierungs Konfigurationen, einschließlich der Hierarchie für Global-, Website-und Poolkonfigurationen, finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.

<div>


> [!NOTE]  
> Sie sollten alle geeigneten Optionen in den Archivierungs Konfigurationen angeben, bevor Sie die Archivierung aktivieren.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a>So konfigurieren Sie Archivierungsoptionen auf globaler Ebene

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server 2013-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server 2013-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Global**, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details einblenden**.

5.  Wählen Sie unter **Archivierungseinstellung bearbeiten – Global** in der Dropdownliste **Archivierungseinstellung** eine der folgenden Archivierungsoptionen aus:
    
      - **Archivierung deaktivieren**
    
      - **Chatsitzungen archivieren**
    
      - **Chat- und Webkonferenzsitzungen archivieren**

6.  Führen Sie außerdem auf der Seite **Archivierungseinstellung bearbeiten – Global** die folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
      - Wenn Sie Microsoft Exchange Server zum Speichern von Archivierungsdaten verwenden möchten, klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** .
    
      - Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:
        
          - Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
        
          - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.

7.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

