---
title: 'Lync Server 2013: Zuweisen einer pro Benutzer gehosteten Voicemail-Richtlinie'
description: 'Lync Server 2013: Zuweisen einer pro Benutzer gehosteten Voicemail-Richtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49440521"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Zuweisen einer pro Benutzer gehosteten Voicemail-Richtlinie in lync Server 2013

 


Das Bereitstelleneiner oder mehrerer pro Benutzer gehosteter Voicemail-Richtlinien ist optional. Wenn Sie Richtlinien für einzelne Benutzer bereitstellen, müssen Sie diese explizit Benutzern, Gruppen oder Kontaktobjekten zuweisen.

Details zum Zuweisen oder Entfernen der Zuweisung von Richtlinien für gehostete Voicemail pro Benutzer finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>So weisen Sie eine pro Benutzer gehostete Voicemail-Richtlinie zu

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Grant-CsHostedVoicemailPolicy-Cmdlet aus, um die Richtlinie für pro Benutzer gehostete Voicemail einzelnen Benutzern, Gruppen und Kontaktobjekten zuzuweisen. Führen Sie beispielsweise den folgenden Befehl aus:
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    In diesem Beispiel wurde dem Benutzer Ken Myers die Richtlinie für die gehostete Voicemail-e-Mail zugewiesen.
    
    **Identity** gibt das zu ändernde Benutzerkonto an. Der Identity-Wert kann mit einem der folgenden Formate angegeben werden:
    
      - Die SIP-Adresse des Benutzers
    
      - Name des Active Directory-Benutzerprinzipals des Benutzers
    
      - Der Domänen \\ Anmeldename des Benutzers (beispielsweise contoso \\ kenmyer)
    
      - Die Active Directory-Domänendienste des Benutzers Display-Name (beispielsweise Ken Myers). Wenn Sie die Display-Name als Identitätswert verwenden, können Sie das \* Platzhalterzeichen Sternchen () verwenden. Die Identität " \* Smith" gibt beispielsweise alle Benutzer zurück, die eine Display-Name haben, die mit dem Zeichenfolgenwert "Smith" endet.
    

    > [!NOTE]  
    > Der Name des Active Directory-SAM-Kontos des Benutzers kann nicht als Identitätswert verwendet werden, da der Name des SAM-Kontos in der Gesamtstruktur nicht unbedingt eindeutig ist.


