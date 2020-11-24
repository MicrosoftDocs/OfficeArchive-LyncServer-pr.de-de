---
title: 'Lync Server 2013: Update-CsAddressBook für die Verwaltung von Adressbüchern'
description: 'Lync Server 2013: Update-CsAddressBook für die Verwaltung von Adressbüchern.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4adc7f94e2f31f64f6517b8cdf9bbcb0649f6c8b
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394846"
---
# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a>Update-CsAddressBook für die Verwaltung von Adressbüchern in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Wer dieses Cmdlet ausführen kann: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Update-CsAddressBook-Cmdlet lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller rollenbasierten zugriffssteuerungsrollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

Das Update-CsAddressBook-Cmdlet ersetzt den Befehl **abserver.exe – syncNow** von Office Communications Server. Der Zweck des Cmdlets besteht darin, eine Synchronisierung sofort zu initiieren, anstatt auf die geplante Zeit zu warten. Mit dem ersten Beispielbefehl werden alle Adressbücher in der Organisation aktualisiert. Der zweite aktualisiert nur das Adressbuch, das dem definierten Server zugeordnet ist.

<div>


> [!NOTE]  
> In lync Server 2013 wird der lync Server-Benutzerreplikationsdienst die Änderungen aus Active Directory aufnehmen und die lync Server-Benutzerdatenbank basierend auf einem konfigurierten Intervall aktualisieren. Der lync Server-Benutzerreplikationsdienst gibt die Änderungen auch schnell an die RTCab-Datenbank weiter, ohne dass der Administrator Update-CSAddressBook ausführen muss. Administratoren müssen nur Update-CSAddressBook ausführen, wenn der Download der Adressbuchdatei aktiviert ist.



</div>

Beispiel:

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a>Siehe auch


[Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

