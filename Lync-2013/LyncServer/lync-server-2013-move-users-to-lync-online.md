---
title: 'Lync Server 2013: Verschieben von Benutzern nach lync Online'
description: 'Lync Server 2013: Verschieben von Benutzern nach lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 501eda3a76cec3226831c0af3631317377cd82cb
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425276"
---
# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Verschieben von Benutzern nach lync Online in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-29_

Bevor Sie mit der Migration von Benutzern zu lync Online beginnen, sollten Sie die Benutzerdaten sichern, die den zu verschiebenden Konten zugeordnet sind. Nicht alle Benutzerdaten werden mit dem Benutzerkonto verschoben. Informationen finden Sie unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Daten](lync-server-2013-backup-and-restoration-requirements-data.md).

<div>

## <a name="migrate-user-settings-to-lync-online"></a>Migrieren von Benutzereinstellungen zu lync Online

Benutzereinstellungen werden zusammen mit dem Benutzerkonto verschoben. Einige lokale Einstellungen werden jedoch nicht mit dem Benutzerkonto verschoben.

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>Verschieben von Pilot Benutzern nach lync Online

Bevor Sie beginnen, Benutzer nach lync online zu verschieben, möchten Sie möglicherweise einige Pilotbenutzer verschieben, um zu bestätigen, dass Ihre Umgebung ordnungsgemäß konfiguriert ist. Sie können dann überprüfen, ob die lync-Features und-Dienste wie erwartet funktionieren, bevor Sie versuchen, weitere Benutzer zu verschieben.

Wenn Sie einen lokalen Benutzer in ihren lync Online-Mandanten verschieben möchten, führen Sie die folgenden Cmdlets in der lync Server-Verwaltungsshell aus, wobei Sie die Administratoranmeldeinformationen für Ihre Microsoft 365-oder Office 365-Organisation verwenden. Ersetzen Sie „benutzername@contoso.com“ mit den Informationen des zu verschiebenden Benutzers.

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

Das Format der für den **HostedMigrationOverrideUrl** -Parameter angegebenen URL muss die URL des Pools sein, in dem der gehostete Migrationsdienst ausgeführt wird, im folgenden Format: https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc.

Sie können die URL für den gehosteten Migrationsdienst ermitteln, indem Sie die URL für die lync Online-Systemsteuerung für Ihr Microsoft 365-oder Office 365-organisationskonto anzeigen.

**So ermitteln Sie die URL des gehosteten Migrations Diensts für Ihre Organisation**

1.  Melden Sie sich als Administrator bei Ihrer Microsoft 365-oder Office 365-Organisation an.

2.  Öffnen Sie das **lync Admin Center**.

3.  Wenn das **lync Admin Center** angezeigt wird, wählen Sie die URL in der Adressleiste bis zu **lync.com** aus, und kopieren Sie Sie. Eine Beispiel-URL sieht ähnlich wie die folgende aus:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Ersetzen Sie **webdir** in der URL durch **admin**, womit Sie folgendes Ergebnis erhalten:
    
    `https://admin0a.online.lync.com`

5.  Fügen Sie dann folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.
    
    Die daraus resultierende URL, die dem Wert der **HostedMigrationOverrideUrl** entspricht, sollte wie folgt aussehen:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a>Verschieben von Benutzern nach lync Online

Sie können mehrere Benutzer verschieben, indem Sie das Cmdlet " [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) " mit dem-Filter-Parameter verwenden, um die Benutzer mit einer bestimmten Eigenschaft auszuwählen, die den Benutzerkonten zugewiesen ist, wie etwa RegistrarPool. Sie können die zurückgegebenen Benutzer dann an das Cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) übergeben, wie im folgenden Beispiel gezeigt.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

Sie können auch den Parameter „-OU“ verwenden, um alle Benutzer in der angegebenen Organisationseinheit (Organizational Unit, OU) abzurufen, wie im folgenden Beispiel dargestellt.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Überprüfen der lync Online-Benutzereinstellungen und-Features

Mit folgenden Methoden können Sie überprüfen, ob ein Benutzer erfolgreich verschoben wurde:

  - Anzeigen des Status des Benutzers in der lync Online-Systemsteuerung. Für lokale und Onlinebenutzer werden unterschiedliche visuelle Indikatoren verwendet.

  - Führen Sie das folgende Cmdlet aus:
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

