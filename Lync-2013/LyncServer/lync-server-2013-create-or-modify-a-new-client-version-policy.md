---
title: 'Lync Server 2013: Erstellen oder Ändern einer neuen clientversionsrichtlinie'
description: 'Lync Server 2013: Erstellen oder Ändern einer neuen clientversionsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4d100e21591a27646784161614ff6c248dc6ae6
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394635"
---
# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>Erstellen oder Ändern einer neuen clientversionsrichtlinie in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Sie können clientversionsrichtlinien verwenden, um die Versionen der Clients anzugeben, die in Ihrer Umgebung unterstützt werden. Die Verwendung der Client Versionsverwaltung kann dazu beitragen, die Kosten für die Unterstützung mehrerer Clientversionen zu senken. Darüber hinaus kann die Benutzeroberfläche insgesamt verbessert werden, da die verfügbaren Features durch die frühere Version des Clients limitiert werden können, wenn frühere und spätere Versionen von Clients interagieren. Sie können clientversionsrichtlinien über die lync Server 2013-Systemsteuerung oder die lync Server 2013-Verwaltungsshell erstellen oder ändern.

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>So erstellen oder ändern Sie clientversionsrichtlinien mithilfe der lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**.
    
    <div>
    

    > [!NOTE]  
    > Die Registerkarte <STRONG>Client Versionsrichtlinie</STRONG> ist standardmäßig aktiviert.

    
    </div>

4.  Führen Sie auf der Seite **Client Versionsrichtlinie** eine der folgenden Aktionen aus:
    
      - Wenn Sie eine clientversionsrichtlinie erstellen möchten, klicken Sie auf **neu**, wählen Sie **Website Richtlinie**, **Pool Richtlinie** oder **Benutzerrichtlinie** aus, und klicken Sie dann auf **OK**.
    
      - Wenn Sie die globale Richtlinie oder eine andere vorhandene clientversionsrichtlinie ändern möchten, wählen Sie die Richtlinie aus, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Erstellen oder ändern Sie auf der Seite **Richtlinie zum Bearbeiten der Client Version** Regeln, wie unter [erstellen oder Ändern einer neuen clientversionsrichtlinien Regel in lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)beschrieben.

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>Erstellen oder Ändern von Client Versionsrichtlinien mithilfe von Windows PowerShell-Cmdlets

Sie können clientversionsrichtlinien mithilfe des Cmdlets **New-CsClientVersionPolicy** erstellen und mithilfe des Cmdlets " **Satz-CsClientVersionPolicy** " ändern. Diese Cmdlets können entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>So erstellen Sie eine neue Richtlinie für Clientversionen mit Website Bereich

  - Mit dem folgenden Befehl wird eine neue clientversionsrichtlinie erstellt, die auf die Redmond-Website angewendet wurde. Da keine zusätzlichen Parameter angegeben werden, werden in der neuen Richtlinie die Standardeinstellungen für Clientversionen verwendet.
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>So erstellen Sie eine neue Richtlinie für benutzerspezifische Clientversionen

  - Verwenden Sie zum Erstellen einer benutzerbezogenen Richtlinie einen Befehl wie den folgenden:
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) und dem Cmdlet " [Satz-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>

