---
title: Erstellen oder Ändern einer Sammlung von Konfigurationseinstellungen für Geräte Updates
description: Erstellen oder ändern Sie eine Sammlung von Konfigurationseinstellungen für Geräte Updates.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 593a1a0cb0f68254748ee48440cda18c78989780
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394379"
---
# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Erstellen oder Ändern einer Sammlung von Konfigurationseinstellungen für Geräte Updates in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Konfigurationseinstellungen für Geräte Updates können (nur im Website Bereich) mithilfe von Windows PowerShell und dem Cmdlet **New-CsDeviceUpdateConfiguration** erstellt und mithilfe des Cmdlets " **Satz-CsDeviceUpdateConfiguration** " geändert werden. Diese Cmdlets können entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]
> Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a>So erstellen Sie Konfigurationseinstellungen für Geräte Updates, die die Standardwerte verwenden

  - Mit diesem Befehl wird ein neuer Satz von Geräteupdate-Konfigurationseinstellungen für die Website "Redmond" erstellt:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    Da im vorhergehenden Befehl keine anderen Parameter als der Parameter für die obligatorische Identität angegeben wurden, werden in der neuen Sammlung der Konfigurationseinstellungen die Standardwerte für alle zugehörigen Eigenschaften verwendet.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a>So ändern Sie einen einzelnen Eigenschaftswert beim Erstellen von Geräteupdate-Konfigurationseinstellungen

  - Um Einstellungen zu erstellen, die andere Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und Parameterwert ein. Wenn Sie beispielsweise eine Sammlung von Konfigurationseinstellungen für Geräte Updates erstellen möchten, die standardmäßig alle 21 Tage alte Protokolldateien löscht, verwenden Sie einen Befehl wie den folgenden:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a>So ändern Sie beim Erstellen von Geräteupdate-Konfigurationseinstellungen mehrere Eigenschaftswerte

  - Mehrere Eigenschaftswerte können geändert werden, indem Sie mehrere Parameter angeben. Mit diesem Befehl wird beispielsweise das Protokoll Bereinigungsintervall auf 21 Tage und das Protokoll leer Intervall auf 30 Minuten festgelegt:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

Details zum Ändern vorhandener Geräte Konfigurationseinstellungen finden Sie im Hilfethema zum Cmdlet " [setCsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) ". Details zum Erstellen von Sammlungen von Konfigurationseinstellungen finden Sie im Hilfethema zum Cmdlet [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

