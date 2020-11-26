---
title: 'Lync Server 2013: Erstellen einer Hosted Voicemail-Richtlinie auf Websiteebene'
description: 'Lync Server 2013: Erstellen einer Hosted Voicemail-Richtlinie auf Websiteebene'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cd578359a8d20562e8887b61b86d53332e6f8d8
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49432114"
---
# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Erstellen einer gehosteten Voicemail-Richtlinie auf Websiteebene in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-24_

Eine *Website* Richtlinie kann sich auf alle Benutzer auswirken, die sich auf der Website befinden, für die die Richtlinie definiert ist. Wenn ein Benutzer für den gehosteten Exchange um-Zugriff konfiguriert ist und keiner Richtlinie pro Benutzer zugewiesen wurde, gilt die Website Richtlinie. Wenn Sie keine Website Richtlinie bereitgestellt haben, gilt die globale Richtlinie.

Details zum Konfigurieren von Website Richtlinien finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - [Neu – CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Satz-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>So erstellen Sie eine von der Website gehostete Voicemail-Richtlinie

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das New-CsHostedVoicemailPolicy-Cmdlet aus, um die Richtlinie zu erstellen. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    In diesem Beispiel wird eine gehostete Voicemail-Richtlinie mit Website Bereich erstellt, und die folgenden Parameter werden festgelegt:
    
      - **Identity** gibt einen eindeutigen Bezeichner für die Richtlinie an, der den Bereich umfasst. Bei einer Richtlinie mit Website Bereich muss der Parameterwert Identity im Format angegeben werden `site:` *\<name\>* , beispielsweise `site:Redmond` .
    
      - **Ziel** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Exchange um-Diensts an. Dieser Parameter ist optional, aber wenn Sie versuchen, einen Benutzer für gehostete Voicemail zu aktivieren, und die zugewiesene Richtlinie des Benutzers keinen Zielwert hat, schlägt die Aktivierung fehl.
    
      - **Beschreibung** enthält optionale beschreibende Informationen zur Richtlinie.
    
      - **Organisation** gibt eine durch trennzeichengetrennte Liste der Exchange-Mandanten an, die lync Server 2013-Benutzer sind. Jeder Mandant muss als FQDN dieses Mandanten für den gehosteten Exchange um-Dienst angegeben werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

