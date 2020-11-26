---
title: Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung
description: Erstellen oder ändern Sie eine Normalisierungsregel, indem Sie eine Normalisierungsregel erstellen.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 824936359c070090ad4225a3ead6e8e46fe14785
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431751"
---
# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel in der lync Server-Systemsteuerung erstellen oder ändern möchten. Wenn Sie eine Normalisierungsregel manuell erstellen oder ändern möchten, finden Sie Informationen dazu unter [Manuelles Erstellen oder Ändern einer Normalisierungsregel in lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>So definieren Sie eine Regel mithilfe der Regel zum Erstellen einer Normalisierung

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Optional Führen Sie die Schritte unter [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md) bis Schritt 11 aus, oder [Ändern Sie einen Wählplan in lync Server 2013](lync-server-2013-modify-a-dial-plan.md) bis Schritt 10.

4.  Geben Sie unter **Neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten** im Feld **Name** einen beschreibenden Namen für das zu normalisierende Nummernmuster ein (beispielsweise **5DigitExtension**).

5.  (Optional) Geben Sie in **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise „Übersetzt 5-stellige Durchwahlnummern“).

6.  Geben Sie im Abschnitt **Normalisierungsregel erstellen** Werte in die folgenden Felder ein:
    
      - **Anfangsziffern** (Optional) Geben Sie die Anfangsziffern der gewählten Nummern ein, die Sie mit dem Muster abgleichen möchten. Geben Sie beispielsweise **425** ein, wenn das Muster für gewählte Nummern gelten soll, die mit 425 beginnen.
    
      - **Länge** Geben Sie die Anzahl von Ziffern im Vergleichsmuster ein und wählen Sie aus, ob mit dem Muster Nummern abgeglichen werden sollen, die exakt diese Länge, mindestens diese Länge oder eine beliebige Länge aufweisen.
    
      - **Zu entfernende Ziffern** (Optional) Geben Sie die Anzahl von Anfangsziffern ein, die aus gewählten Nummern entfernt werden sollen, die Sie mit dem Muster abgleichen möchten.
    
      - **Hinzuzufügende Ziffern** (Optional) Geben Sie Ziffern ein, die gewählten Nummern hinzugefügt werden, die Sie mit dem Muster abgleichen möchten.
    
    Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Vergleich** und **Übersetzungsregel** widergespiegelt. Wenn Sie beispielsweise **Anfangsziffern** leer lassen, den Wert **7** in das Feld **Länge** eingeben und **Genau** auswählen und den Wert **0** unter **Zu entfernende Ziffern** wählen, ergibt sich in **Muster für Vergleich** der folgende reguläre Ausdruck:
    
    **^ ( \\ d {7} ) $**

7.  Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein:
    
      - Ein Wert, der die Anzahl von Ziffern repräsentiert, die im Vergleichsmuster angegeben ist. Wenn das Übereinstimmungsmuster beispielsweise **^ ( \\ d {7} ) $** ist, stellt **$1** in der Übersetzungsregel siebenstellige Wähl Nummern dar.
    
      - (Optional) Geben Sie einen Wert in das Feld **Hinzuzufügende Ziffern** ein, um Ziffern anzugeben, die der übersetzten Nummer vorangestellt werden (z. B. **+1425**).
    
    Wenn Muster für die **Übereinstimmung** beispielsweise **^ ( \\ d {7} ) $** als Muster für gewählte Nummern und die **Übersetzungsregel** **+ 1425 $1** als Muster für E. 164-Telefonnummern enthält, normalisiert die Regel 5550100 auf + 14255550100.

8.  (Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl**.

9.  (Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.
    
    <div>
    

    > [!NOTE]
    > Sie können eine Normalisierungsregel speichern, die den Test nicht bestanden hat und sie später neu konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in lync Server 2013</A>.

    
    </div>

10. Klicken Sie auf **OK**, um die Normalisierungsregel zu speichern.

11. Klicken Sie auf **OK**, um die Wähleinstellungen zu speichern.

12. Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
    
    <div>
    

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Manuelles Erstellen oder Ändern einer Normalisierungsregel in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Ändern eines Wählplans in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Testen des VoIP-Routings in Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

