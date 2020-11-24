---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren von Push-Benachrichtigungen für iPhones'
description: 'Lync Server 2013: Aktivieren oder Deaktivieren von Push-Benachrichtigungen für iPhones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49733719
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07a9c5ec442c3628455797b987d8b2f22677e70e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394702"
---
# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a>Aktivieren oder Deaktivieren von Push-Benachrichtigungen für iPhones in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Push-Benachrichtigungen in Form von Signalen, Symbolen oder Benachrichtigungen können auch dann an ein iPhone gesendet werden, wenn die Mobile Anwendung inaktiv ist. Push-Benachrichtigungen benachrichtigt einen Benutzer über Ereignisse wie eine neue oder verpasste Chat Einladung und Voicemail. Sie können Push-Benachrichtigungen für iPhone aktivieren oder deaktivieren, indem Sie entweder die lync Server 2013-Systemsteuerung oder die lync Server 2013-Verwaltungsshell verwenden.

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a>So aktivieren Sie Push-Benachrichtigungen für iPhone mithilfe der lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Schaltfläche Navigations **Benachrichtigungskonfiguration** .

4.  Klicken Sie auf der Seite **Konfiguration der Push-Benachrichtigung** auf die Website, die Sie bearbeiten möchten, klicken Sie auf das Menü **Bearbeiten** , und klicken Sie dann auf **Details anzeigen**.

5.  Klicken Sie auf das Kontrollkästchen **Apple-Push-Benachrichtigungen aktivieren** .

6.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a>So deaktivieren Sie Push-Benachrichtigungen für iPhone mithilfe der lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Schaltfläche Navigations **Benachrichtigungskonfiguration** .

4.  Klicken Sie auf der Seite **Konfiguration der Push-Benachrichtigung** auf die Website, die Sie bearbeiten möchten, klicken Sie auf das Menü **Bearbeiten** , und klicken Sie dann auf **Details anzeigen**.

5.  Deaktivieren Sie das Kontrollkästchen **Apple-Push-Benachrichtigungen aktivieren** .

6.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren von Push-Benachrichtigungen auf dem iPhone mithilfe von Windows PowerShell-Cmdlets

Push-Benachrichtigungen an Apple iPhone können mithilfe des Cmdlets " **CsPushNotificationConfiguration** " aktiviert oder deaktiviert werden. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-push-notifications-for-iphone"></a>So aktivieren Sie Push-Benachrichtigungen für iPhone

  - So aktivieren Sie die Push-Benachrichtigungen für iPhone legen Sie den Wert der EnableApplePushNotificationService-Eigenschaft auf true ($true) fest. Beispiel:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a>So deaktivieren Sie Push-Benachrichtigungen für iPhone

  - So deaktivieren Sie Push-Benachrichtigungen für iPhone legen Sie den Wert der EnableApplePushNotificationService-Eigenschaft auf false ($false) fest. Beispiel:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) ".

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von Pushbenachrichtigungen in Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

