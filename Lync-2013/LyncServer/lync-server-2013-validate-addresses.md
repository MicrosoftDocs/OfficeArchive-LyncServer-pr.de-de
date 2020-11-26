---
title: 'Lync Server 2013: Adressen überprüfen'
description: 'Lync Server 2013: Überprüfen von Adressen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcbb8789912b3bcbcfb60dd79807f06c2957c1f6
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49446318"
---
# <a name="validate-addresses-in-lync-server-2013"></a>Überprüfen von Adressen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Bevor Sie die Standortdatenbank veröffentlichen, müssen Sie neue Speicherorte für den Master Street Address Guide (MSAG) überprüfen, der von Ihrem SIP-Stamm oder dem öffentlichen Telefonnetz (PSTN) E9-1-1 Service Provider verwaltet wird.

Ausführliche Informationen zu SIP Trunk E9-1-1 Serviceanbietern finden Sie unter [Auswählen eines E9-1-1-Dienstanbieters für lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).

Details zur Überprüfung von Adressen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - **Get-CsLisServiceProvider**

  - **Satz-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>So überprüfen Sie Adressen in der Standortdatenbank auf Gültigkeit

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie die folgenden Cmdlets zum Konfigurieren der Verbindung mit dem Anbieter für die Notrufunterstützung aus.
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  Führen das folgende Cmdlet zum Überprüfen der Gültigkeit von Adressen in der Standortdatenbank aus.
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    Einzelne Adressen können Sie auch mit dem Cmdlet **Test-CsLisCivicAddress** validieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

