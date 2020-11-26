---
title: 'Lync Server 2013: Erstellen oder Ändern eines interaktiven Workflows'
description: 'Lync Server 2013: Erstellen oder Ändern eines interaktiven Workflows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 470a073322c48c351dbfdfb24ce376731b3e7512
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431694"
---
# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a>Erstellen oder Ändern eines interaktiven Workflows in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-09-11_

Führen Sie eines der folgenden Verfahren aus, um einen interaktiven Workflow zu erstellen oder zu ändern.

<div>


> [!NOTE]  
> Sie können die lync Server-Verwaltungsshell oder das Reaktionsgruppen-Konfigurations Tool verwenden, um interaktive Workflows zu erstellen und zu ändern. Sie können über die lync Server-Systemsteuerung auf das Tool für die Reaktionsgruppen Konfiguration zugreifen, oder indem Sie die Webseite direkt in einem Webbrowser öffnen, indem Sie die folgende URL eingeben: <STRONG>https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>So verwenden Sie das Reaktionsgruppen-Konfigurations Tool zum Erstellen oder Ändern eines interaktiven Workflows

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Workflow**.

4.  Klicken Sie auf der Seite **Workflow** auf **Workflow erstellen oder bearbeiten**.

5.  Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den vollständigen Namen des **ApplicationServer**-Diensts ein, von dem der Workflow gehostet wird, den Sie erstellen oder ändern möchten. Klicken Sie in der nun angezeigten Liste der Dienst auf den gewünschten Dienst und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Das Tool für die Reaktionsgruppen Konfiguration wird geöffnet. Sie können das Tool für die Reaktionsgruppen Konfiguration auch direkt in einem Webbrowser öffnen, indem Sie die folgende URL eingeben: <STRONG>https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>.

    
    </div>

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Klicken Sie unterhalb von **Neuen Workflow erstellen** neben **Interaktiv** auf **Erstellen**.
    
      - Suchen Sie unter **Vorhandenen Workflow verwalten** nach dem Workflow, den Sie ändern möchten, und klicken Sie anschließend unter **Aktion** auf **Bearbeiten**.

7.  Falls Benutzer den Workflow noch nicht aufrufen sollen, müssen Sie das Kontrollkästchen **Workflow aktivieren** deaktivieren.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie einen verwalteten Workflow erstellen, müssen Sie <STRONG>Workflow aktivieren</STRONG> auswählen. Nachdem Sie den aktiven, verwalteten Workflow gespeichert haben, können Sie ihn ändern und deaktivieren.

    
    </div>

8.  Aktivieren Sie das Kontrollkästchen **Für Partnerverbund aktivieren**, um Partnerbenutzern Anrufe bei der Gruppe zu ermöglichen. Außerdem müssen Sie über eine Richtlinie für den externen Zugriff verfügen, die für die für den Verbund konfigurierte reaktionsgruppenanwendung gilt.
    
    <div>
    

    > [!NOTE]  
    > Die globale Richtlinie für den externen Zugriff gilt für die Antwortgruppen Anwendung. Sie können die globale Richtlinie für die Antwortgruppen Föderation mithilfe der lync Server-Systemsteuerung oder mithilfe des Cmdlets "CsExternalAccessPolicy" konfigurieren, um den EnableOutsideAccess <STRONG>-</STRONG> Parameter auf "true" festzulegen. Bedenken Sie, dass globale Richtlinieneinstellungen für alle Benutzer gelten, es sei denn, sie sind einer standort- oder benutzerspezifischen Richtlinie zugeordnet. Stellen Sie daher vor dem Ändern dieser Einstellung für Reaktionsgruppen sicher, dass die Partnerverbundeinstellung die Anforderungen Ihrer Organisation erfüllt. Details dazu, wie Richtlinien für Benutzer gelten, finden Sie unter <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Verwalten der Richtlinie für den externen Zugriff in lync Server 2013</A>. Details zur Föderations Einstellung finden Sie unter Dokumentation zu CsExternalAccessPolicy in der lync Server <STRONG>-</STRONG> Verwaltungsshell.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Benutzer, die in lync online gehostet werden, können keine Anrufe an Reaktionsgruppen tätigen, die in einer lokalen Bereitstellung gehostet werden. Dies gilt sowohl in hybridbereitstellungen als auch in Fällen, in denen eine lokale Bereitstellung mit einer lync Online-Bereitstellung verbunden ist.

    
    </div>

9.  Aktivieren Sie das Kontrollkästchen **Agentanonymität aktivieren**, um bei Anrufen die Identität der Agents zu verbergen.
    
    <div>
    

    > [!NOTE]  
    > Anonyme Anrufe können nicht mit Chats oder Video gestartet werden. Agent oder Anrufer können jedoch im Verlauf des Anrufs Chats und Video aktivieren. Ein anonymer Agent kann Anrufe halten, weiterleiten (sowohl blind als auch nach Rücksprache) sowie Anrufe parken und fortsetzen. Anonyme Anrufe bieten keine Unterstützung für Konferenzen, Anwendungs- und Desktopfreigabe, Dateiübertragung, Whiteboardverwendung und Datenzusammenarbeit sowie Anrufaufzeichnung. Agents, die das Lync VDI-Plugin verwenden, können eingehende Anrufe anonym empfangen, jedoch keine ausgehenden anonymen Anrufe tätigen.

    
    </div>

10. Geben Sie im Feld **Adresse der Gruppe eingeben, die die Anrufe entgegennimmt** den primären SIP-URI (Uniform Resource Identifier) der Gruppe ein, die die Anrufe beim Workflow erhalten soll.

11. Geben Sie im Feld **Anzeigename** den Namen ein, der für den Workflow angezeigt werden soll (z. B. „Vertrieb-IVR-Reaktionsgruppe“).
    
    <div>
    

    > [!NOTE]  
    > Fügen Sie die Zeichen " &lt; " oder " &gt; " nicht in den Anzeigenamen ein. Die folgenden Anzeigenamen sind reserviert und dürfen nicht verwendet werden: „RGS-Anwesenheitsmonitor“ oder „Ankündigungsdienst“.

    
    </div>

12. Geben Sie unter **Telefonnummer** den Anschluss-URI für die Reaktionsgruppe ein (z. B. +14255550165).

13. Geben Sie im Feld **Anzeigenummer** die Nummer ein, wie sie für die Reaktionsgruppe angezeigt werden soll (z. B. +1 (425) 555-0165).

14. Optional Geben Sie in **Beschreibung** eine Beschreibung für den Workflow ein, der auf der Visitenkarte im lync-Client angezeigt werden soll.

15. Wählen Sie unter **Workflowtyp** die Option **Verwaltet** aus, wenn dieser Workflow von einem Reaktionsgruppenmanager verwaltet wird. Gehen Sie wie folgt vor, um dem Workflow Antwortgruppen-Manager zuzuweisen:
    
    1.  Geben Sie den SIP-URI eines Managers für diesen Workflow ein und klicken Sie auf **Hinzufügen**.
    
    2.  Geben Sie den SIP-URI zusätzlicher Manager für den Workflow ein und klicken Sie auf **Hinzufügen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Jedem Benutzer, der als Manager einer Reaktionsgruppe bestimmt wurde, muss die Rolle „CsResponseGroupManager“ zugewiesen sein. Falls Benutzern diese Rolle nicht zugewiesen ist, können sie keine Reaktionsgruppen verwalten.

    
    </div>

16. Klicken Sie unter **Schritt 2: Sprache auswählen** auf die Sprache, die für die Spracherkennung und die Text-zu-Sprache-Funktion verwendet werden soll.

17. Aktivieren Sie zum Konfigurieren einer Willkommensnachricht unter **Schritt 3: Willkommensnachricht konfigurieren** das Kontrollkästchen **Willkommensnachricht wiedergeben** und führen Sie eine der folgenden Aktionen aus:
    
      - Um die Willkommensnachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben Sie die Willkommensnachricht in das Textfeld ein.
        
        <div>
        

        > [!NOTE]  
        > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

        
        </div>
    
      - Um eine aufgezeichnete WAV- oder WMA-Datei für die Willkommensnachricht zu verwenden, klicken Sie auf **Aufzeichnung auswählen**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Audiodatei und klicken Sie dann auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.
        
        <div>
        

        > [!NOTE]  
        > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu unterstützten Dateiformaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technische Anforderungen für die Reaktionsgruppe in lync Server 2013</A>.

        
        </div>

18. Klicken Sie unter **Schritt 4: Geschäftszeiten angeben** im Feld **Ihre Zeitzone** auf die Zeitzone des Workflows.
    
    <div>
    

    > [!NOTE]  
    > Dies ist die Zeitzone, in der sich die Anrufer und Agents des Workflows befinden. Die Angabe wird verwendet, um die Öffnungszeiten zu berechnen. Wenn der Workflow z. B. für die mitteleuropäische Zeit konfiguriert wurde und der Workflow um 7:00 Uhr öffnen und um 11:00 Uhr schließen soll, werden die Zeiten 7:00 Uhr MEZ und 23:00 Uhr MEZ verwendet. (Die Zeiten müssen im 24-Stunden-Format eingegeben werden.)

    
    </div>

19. Sie haben folgende Möglichkeiten, um die gewünschten Geschäftszeiten anzugeben:
    
      - Wenn Sie einen vordefinierten Zeitplan für die Geschäftszeiten verwenden möchten, klicken Sie auf **Vordefinierten Zeitplan verwenden** und wählen Sie den gewünschten Zeitplan in der Dropdownliste aus.
        
        <div>
        

        > [!NOTE]  
        > Sie müssen mindestens einen vordefinierten Zeitplan erstellt haben, um diese Option auswählen zu können. Sie erstellen vordefinierte Zeitpläne mit dem <STRONG>New-CSRgsHoursOfBusiness</STRONG>-Cmdlet. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-optional-define-response-group-business-hours.md">(optional) definieren von Reaktionsgruppen-Geschäftszeiten in lync Server 2013</A>. Wenn Sie einen vordefinierten Zeitplan verwenden, werden die Werte für <STRONG>Tag</STRONG>, <STRONG>Öffnen</STRONG> und <STRONG>Schließen</STRONG>, automatisch mit den Tagen und Stunden ausgefüllt, an denen die Reaktionsgruppe verfügbar ist.

        
        </div>
    
      - Klicken Sie auf **Benutzerdefinierten Zeitplan verwenden**, um einen benutzerdefinierten Zeitplan zu erstellen, der nur für diesen Workflow gilt.

20. Wenn Sie einen benutzerdefinierten Zeitplan für diesen Workflow erstellen, aktivieren Sie die Kontrollkästchen für die Wochentage, an denen die Reaktionsgruppe verfügbar ist.

21. Beim Erstellen eines benutzerdefinierten Zeitplans geben Sie über die Werte für **Öffnen** und **Schließen** den Zeitraum ein, in dem die Reaktionsgruppe verfügbar ist.
    
    <div>
    

    > [!NOTE]  
    > Die Werte für <STRONG>Öffnen</STRONG> und <STRONG>Schließen</STRONG> müssen im 24-Stunden-Format angegeben werden. Wenn Ihr Büro z. B. von 9 Uhr bis 17 Uhr geöffnet und mittags geschlossen ist, können Sie die Geschäftszeiten als <STRONG>Öffnen</STRONG> 9:00, <STRONG>Schließen</STRONG> 12:00, <STRONG>Öffnen</STRONG> 13:00 und <STRONG>Schließen</STRONG> 17:00 angeben.

    
    </div>

22. Wenn Sie eine Nachricht wiedergeben möchten, wenn das Büro geschlossen ist, aktivieren Sie das Kontrollkästchen **Nachricht wiedergeben, wenn die Reaktionsgruppe nicht geöffnet ist** und geben Sie die Nachricht ein, indem Sie eine der folgenden Aktionen ausführen:
    
      - Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben Sie die Nachricht in das Textfeld ein.
        
        <div>
        

        > [!NOTE]  
        > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

        
        </div>
    
      - Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Aufzeichnung auswählen**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.
        
        <div>
        

        > [!NOTE]  
        > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu unterstützten Dateiformaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technische Anforderungen für die Reaktionsgruppe in lync Server 2013</A>.

        
        </div>

23. Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):
    
      - Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.
    
      - Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben Sie die Voicemailadresse ein. Das Format für die Voicemail-Adresse lautet \<username\> @ \<domainname\> (beispielsweise Bob@contoso.com).
    
      - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben Sie die Adresse eines Benutzers ein. Das Format für die Benutzeradresse lautet \<username\> @ \<domainname\> .
    
      - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben Sie die Telefonnummer ein. Das Format für die Telefonnummer lautet \<number\> @ \<domainname\> (beispielsweise + 14255550121@contoso.com). Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.

24. Aktivieren Sie unter **Schritt 5: Feiertage angeben** die Kontrollkästchen für einen oder mehrere Feiertagssätze, mit denen die Tage definiert werden, an denen die Reaktionsgruppe aufgrund eines Feiertags nicht verfügbar ist.
    
    <div>
    

    > [!NOTE]  
    > Sie müssen Feiertage und Feiertagssätze definieren, bevor Sie den Workflow konfigurieren. Verwenden Sie zum Definieren von Feiertagen und Feiertagssätzen die Cmdlets <STRONG>New-CsRgsHoliday</STRONG> und <STRONG>New-CsRgsHolidaySet</STRONG>. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(optional) definieren von Reaktionsgruppen Feiertagssätzen in lync Server 2013</A>.

    
    </div>

25. Wenn Sie an Feiertagen eine Nachricht wiedergeben möchten, aktivieren Sie das Kontrollkästchen **An Feiertagen eine Nachricht wiedergegeben** und geben Sie die Nachricht ein, indem Sie eine der folgenden Aktionen ausführen:
    
      - Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben Sie die Nachricht in das Textfeld ein.
        
        <div>
        

        > [!NOTE]  
        > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

        
        </div>
    
      - Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Aufzeichnung auswählen**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.
        
        <div>
        

        > [!NOTE]  
        > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu unterstützten audiodateidateien finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technische Anforderungen für die Reaktionsgruppe in lync Server 2013</A>.

        
        </div>

26. Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):
    
      - Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.
    
      - Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben Sie die Voicemailadresse ein. Das Format für die Voicemail-Adresse lautet \<username\> @ \<domainname\> (beispielsweise Bob@contoso.com).
    
      - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben Sie die Adresse eines Benutzers ein. Das Format für die Benutzeradresse lautet \<username\> @ \<domainname\> .
    
      - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben Sie die Telefonnummer ein. Das Format für die Telefonnummer lautet \<number\> @ \<domainname\> (beispielsweise + 14255550121@contoso.com). Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.

27. Wählen Sie unter **Schritt 6: Wartemusik konfigurieren** aus, was Anrufer beim Warten auf einen Agent hören sollen, indem Sie einen der folgenden Schritte ausführen:
    
      - Klicken Sie auf **Standard verwenden**, um die Standardwartemusik zu verwenden.
    
      - Klicken Sie auf **Musikdatei auswählen**, um eine aufgezeichnete Audiodatei als Wartemusik zu verwenden. Klicken Sie auf den Link **Musikdatei**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.
        
        <div>
        

        > [!NOTE]  
        > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu unterstützten Dateiformaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technische Anforderungen für die Reaktionsgruppe in lync Server 2013</A>.

        
        </div>

28. Geben Sie in **Schritt 7: Interaktive Sprachantwort (IVR) konfigurieren** unter **Der Benutzer hört den folgenden Text bzw. die folgende aufgezeichnete Nachricht** die Frage ein, die dem Anrufer gestellt wird. Führen Sie hierzu die folgenden Aktionen aus:
    
      - Um die Frage im Textformat einzugeben, klicken Sie auf **Text-zu-Sprache verwenden** und geben Sie die Frage in das Textfeld ein.
        
        <div>
        

        > [!NOTE]  
        > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > Das Symbol „#“ wird vom Text-zu-Sprache-Modul als das Wort „Nummer“ übersetzt. Wenn Sie auf die Taste # verweisen möchten, sollten Sie bei der Eingabe anstelle des Symbols den Tastennamen verwenden. Beispiel: „Wenn Sie mit unserem Vertrieb verbunden werden möchten, drücken Sie die Rautetaste.“

        
        </div>
    
      - Um eine aufgezeichnete Audiodatei mit der Frage zu verwenden, klicken Sie auf **Aufzeichnung auswählen** und dann auf den Link **Aufzeichnung**, um die Datei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Audiodatei und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden und geben Sie dann optional die Frage in das Textfeld ein (auf diese Weise kann die Frage und die Antwort des Anrufers an den zuständigen Agent weitergeleitet werden).
        
        <div>
        

        > [!NOTE]  
        > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu unterstützten Dateiformaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technische Anforderungen für die Reaktionsgruppe in lync Server 2013</A>.

        
        </div>

29. Geben Sie unter **Antwort 1** wie folgt die erste mögliche Antwort auf die Frage ein:
    
    <div>
    

    > [!IMPORTANT]  
    > Verwenden Sie in Sprachantworten keine Anführungszeichen („“). Bei Verwendung von Anführungszeichen funktioniert die interaktive Sprachantwort nicht ordnungsgemäß.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Sie können auswählen, ob Anrufer per Sprache, Tasteneingabe oder beidem antworten können.

    
    </div>
    
      - Wenn Sie zulassen möchten, dass Anrufer per Sprache antworten, geben Sie die Antwort in das Feld **Sprachantwort eingeben** ein.
    
      - Wenn Sie zulassen möchten, dass Anrufer per Tasteneingabe antworten, klicken Sie im Feld **Ziffer** auf die entsprechende Ziffer.

30. Geben Sie wie folgt an, ob der Anrufer an eine Warteschleife weitergeleitet wird oder ob eine weitere Frage gestellt werden soll:
    
      - Um den Anrufer an eine Warteschleife weiterzuleiten, klicken Sie auf **An eine Warteschleife senden** und klicken Sie unter **Warteschleife auswählen** auf die Warteschleife, die Sie verwenden möchten.
    
      - Wenn eine weitere Frage gestellt werden soll, klicken Sie auf **Eine weitere Frage stellen**, klicken Sie dann auf **Text-zu-Sprache verwenden** und geben Sie die Frage ein oder klicken Sie auf **Aufzeichnung auswählen**. Verwenden Sie die Einstellungen in diesem Abschnitt, um bis zu vier mögliche Antworten auf die zusätzliche Frage sowie die Warteschleife für jede Antwort anzugeben. Um eine dritte oder vierte mögliche Antwort anzugeben, aktivieren Sie das Kontrollkästchen **Antwort 3** oder das Kontrollkästchen **Antwort 4**.

31. Geben Sie bis zu drei weitere mögliche Antworten auf die ursprüngliche Frage ein, indem Sie die Schritte 28 und 29 wiederholen, um mögliche Antworten und die Aktion für jede Antwort anzugeben. Um eine dritte oder vierte mögliche Antwort anzugeben, aktivieren Sie das Kontrollkästchen **Antwort 3** oder das Kontrollkästchen **Antwort 4**.

32. Klicken Sie auf **Bereitstellen**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a>So verwenden Sie Windows PowerShell zum Erstellen oder Ändern eines interaktiven Workflows

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Rufen Sie den Dienstnamen für den Reaktionsgruppendienst ab und weisen Sie ihn einer Variablen zu. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  Ein interaktiver Workflow erfordert mindestens zwei Warteschlangen und mindestens zwei Agentgruppen. Erstellen Sie zunächst die Agentgruppen. Führen Sie folgenden Befehl aus:
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  Erstellen Sie die Warteschlangen. Führen Sie folgenden Befehl aus:
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  Erstellen Sie die erste Reaktionsgruppen-Eingabeaufforderung. Führen Sie folgenden Befehl aus:
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  Erstellen Sie anschließend die Aktion, die nach der Eingabeaufforderung ausgeführt werden soll. Führen Sie folgenden Befehl aus:
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  Erstellen Sie die erste Reaktionsgruppenantwort. Führen Sie folgenden Befehl aus:
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  Erstellen Sie nun die zweite Eingabeaufforderung, die zweite Anrufaktion und die zweite Antwort. Erstellen Sie zunächst die Eingabeaufforderung. Führen Sie folgenden Befehl aus:
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. Erstellen Sie die zweite Anrufaktion. Führen Sie folgenden Befehl aus:
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. Erstellen Sie die zweite Reaktionsgruppenantwort. Führen Sie folgenden Befehl aus:
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. Erstellen Sie die Eingabeaufforderung der obersten Ebene. Führen Sie folgenden Befehl aus:
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. Erstellen Sie die Frage der obersten Ebene. Führen Sie folgenden Befehl aus:
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. Erstellen Sie nun den Workflow. Führen Sie folgenden Befehl aus:
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > Allen Benutzern, die als Manager einer Reaktionsgruppe bestimmt wurden, muss die Rolle „CsResponseGroupManager“ zugewiesen sein. Falls Benutzern diese Rolle nicht zugewiesen ist, können sie keine Reaktionsgruppen verwalten.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

