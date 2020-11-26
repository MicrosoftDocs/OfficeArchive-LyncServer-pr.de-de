---
title: 'Lync Server 2013: Erstellen oder Ändern einer Mobilitätsrichtlinie'
description: 'Lync Server 2013: Erstellen oder Ändern einer Mobilitätsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcf593c568a8ecf1bd6791641affc4076672b250
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431799"
---
# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Erstellen oder Ändern einer Mobilitätsrichtlinie in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Sie können mobilitätsrichtlinien erstellen oder ändern, um mobilen Benutzern die Verwendung unterstützter mobiler Geräte für lync-Funktionen wie Instant Messaging (im), Anwesenheitsinformationen und Kontakte zu ermöglichen. Sie können mobilitätsrichtlinien in der lync Server 2013-Systemsteuerung oder in der lync Server 2013-Verwaltungsshell erstellen oder ändern.

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>So erstellen Sie eine Mobilitätsrichtlinie mit der lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Mobilitätsrichtlinie** .

4.  Klicken Sie auf der Seite **Mobilitätsrichtlinie** auf **neu**, und führen Sie eine der folgenden Aktionen aus:
    
    1.  Wenn Sie eine Website Mobilitätsrichtlinie erstellen möchten, klicken Sie auf **Website Richtlinie**, klicken Sie auf eine Website, klicken Sie auf **OK**, überprüfen Sie die Standardeinstellungen, und nehmen Sie bei Bedarf alle gewünschten Änderungen vor.
    
    2.  Wenn Sie eine Benutzer Mobilitätsrichtlinie erstellen möchten, klicken Sie auf **Benutzerrichtlinie**, geben Sie einen Namen ein, überprüfen Sie die Standardeinstellungen, und nehmen Sie bei Bedarf Änderungen vor.

5.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>So ändern Sie eine Mobilitätsrichtlinie mit der lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Mobilitätsrichtlinie** .

4.  Klicken Sie auf der Seite **Mobilitätsrichtlinie** auf eine der vorhandenen mobilitätsrichtlinien.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Bearbeiten Sie alle Einstellungen.

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Erstellen von Richtlinien für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets

Mit Windows PowerShell und dem Cmdlet **New-CsMobilityPolicy** können Sie mobilitätsrichtlinien (im Bereich "Website" oder "pro Benutzer") erstellen. Darüber hinaus können Sie das Cmdlet " **Satz-CsMobilityPolicy** " verwenden, um Ihre vorhandenen Richtlinien einschließlich der globalen Richtlinie zu ändern. Diese Cmdlets können entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>So erstellen Sie eine Mobilitätsrichtlinie im Website Bereich

  - Mit diesem Befehl wird eine neue Mobilitätsrichtlinie für die Website "Redmond" erstellt:
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Da im vorhergehenden Befehl keine Parameter (mit Ausnahme des Parameters zur obligatorischen Identität) angegeben wurden, verwenden die Richtlinien die Standardwerte für alle zugehörigen Eigenschaften.

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>So erstellen Sie eine Mobilitätsrichtlinie für einzelne Benutzer

  - Wenn Sie eine Mobilitätsrichtlinie für den Benutzerbereich erstellen möchten, geben Sie eine eindeutige Identität für die Richtlinie an:
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>So ändern Sie einen einzelnen Eigenschaftswert beim Erstellen einer Mobilitätsrichtlinie

  - Zum Erstellen von Richtlinien, die unterschiedliche Eigenschaftswerte verwenden, schließen Sie den entsprechenden Parameter-und Parameterwert ein. Mit diesem Befehl wird beispielsweise eine Mobilitätsrichtlinie erstellt, die den Anruf über die Arbeit deaktiviert:
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>So ändern Sie beim Erstellen einer Mobilitätsrichtlinie mehrere Eigenschaftswerte

  - Mehrere Eigenschaftswerte können geändert werden, indem Sie mehrere Parameter angeben. Mit diesem Befehl wird beispielsweise eine Richtlinie erstellt, die sowohl Mobilität als auch Anruf über die Arbeit deaktiviert:
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

Ausführliche Informationen finden Sie im Hilfethema zu den Cmdlets [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) und [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) .

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren der Mobilitätsrichtlinie in Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

