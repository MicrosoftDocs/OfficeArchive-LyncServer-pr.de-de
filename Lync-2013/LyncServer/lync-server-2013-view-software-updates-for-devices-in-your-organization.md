---
title: 'Lync Server 2013: Anzeigen von Softwareupdates für Geräte in Ihrer Organisation'
description: 'Lync Server 2013: Anzeigen von Softwareupdates für Geräte in Ihrer Organisation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 833ab25315847b760271c63bbfca3ba8357e41c1
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394667"
---
# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>Anzeigen von Softwareupdates für Geräte in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Mit lync Server 2013 verwenden Sie den Geräte Update-Webdienst, um Softwareupdates für die Geräte Ihrer Organisation anzuzeigen und zu verwalten. Diese Updates sind in CAB-Dateien (Cabinet) von der Microsoft-Support Website unter verfügbar [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) . Führen Sie nach dem Herunterladen der CAB-Datei das Cmdlet " **Import-CSDeviceUpdate** " aus, um die geräteaktualisierungsregeln aus der CAB-Datei zu importieren. Details zum Cmdlet " **Import-CSDeviceUpdate** " finden Sie unter [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in der Dokumentation zur lync Server-Verwaltungsshell.

<div>


> [!TIP]  
> Bevor Sie ein neues Update für Ihre Organisation bereitstellen, stellen Sie sicher, dass es auf einem Testgerät ordnungsgemäß funktioniert.



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>So zeigen Sie Softwareupdates für UC-Geräte an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Laden Sie die CAB-Datei von der Microsoft-Support Website an [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) einen Speicherort auf einem lync Server 2013-Computer herunter (beispielsweise C: \\ Updates \\UCUpdates.cab).

3.  Importieren Sie die geräteaktualisierungsregeln aus der Datei C: \\ Updates \\UCUpdates.cab, indem Sie eines der folgenden Cmdlets ausführen:
    
      - Wenn sich die CAB-Datei auf demselben Computer befindet wie diejenige, die den zu aktualisierenden Dienst ausführt (Dienst: Redmond-websvc-2), führen Sie das folgende Cmdlet aus:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Wenn sich die CAB-Datei auf einem anderen Computer als derjenige befindet, der den zu aktualisierenden Dienst ausführt (Dienst: Redmond-websvc-3), führen Sie das folgende Cmdlet aus:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

5.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf **Geräteaktualisierung**.

6.  Klicken Sie auf der Seite **Device Update** auf ein Update in der Liste, und führen Sie dann eine der folgenden Aktionen aus:
    
      - **Abbrechen einer ausstehenden Aktualisierung** Wenn Sie verhindern möchten, dass das ausgewählte Update auf den Geräten Ihrer Organisation bereitgestellt wird, klicken Sie auf das Menü **Aktion** und dann auf **ausstehende Updates Abbrechen**.
    
      - **Genehmigen eines Updates** Wenn Sie zulassen möchten, dass das ausgewählte Update auf den Geräten Ihrer Organisation bereitgestellt wird, klicken Sie auf das Menü **Aktion** und dann auf **genehmigen**.
    
      - **Wiederherstellen eines Updates** Wenn Sie zulassen möchten, dass ein zuvor genehmigtes Update auf den Geräten Ihrer Organisation bereitgestellt wird, klicken Sie auf das Menü **Aktion** und dann auf **Wiederherstellen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

