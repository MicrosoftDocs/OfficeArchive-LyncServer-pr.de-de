---
title: 'Lync Server 2013: Konfigurieren von Microsoft Exchange Server 2013 Unified Messaging für lync Server 2013-Voicemail'
description: 'Lync Server 2013: Konfigurieren von Microsoft Exchange Server 2013 Unified Messaging für lync Server 2013-Voicemail.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57576981e419f96734e4bd2ed62a7d203f7b683c
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49432947"
---
# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a><span data-ttu-id="2e508-103">Konfigurieren von Microsoft Exchange Server 2013 Unified Messaging für Microsoft lync Server 2013-Voicemail</span><span class="sxs-lookup"><span data-stu-id="2e508-103">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="2e508-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="2e508-104">

<span> </span></span></span>

<span data-ttu-id="2e508-105">_**Letztes Änderungsdatum des Themas:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="2e508-105">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="2e508-106">Mit Microsoft lync Server 2013 können Sie Voicemail-Nachrichten in Microsoft Exchange Server 2013 speichern. Diese Sprachnachrichten werden dann als e-Mail-Nachrichten in den Posteingängen Ihrer Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e508-106">Microsoft Lync Server 2013 enables you to have voicemail messages stored in Microsoft Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> <span data-ttu-id="2e508-107">Diese Funktion wurde auch in den 2010-Editionen von lync Server und Exchange gefunden. der Vorgang zum Konfigurieren dieses "Unified Messaging" wurde in den 2013-Editionen jedoch dank der Einführung der um-Anruf-Router-Komponente vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="2e508-107">This capability was also found in the 2010 editions of Lync Server and Exchange; however, the process of configuring this "unified messaging" has been simplified in the 2013 editions thanks to the introduction of the UM Call Router component.</span></span> <span data-ttu-id="2e508-108">Diese Komponente ist auf dem Exchange 2013-Client Zugriffsserver installiert, und alle Anrufe an Exchange Unified Messaging (wie eine Sprachnachricht) werden zuerst über den Anruf Router weitergeleitet und dann an den entsprechenden Postfachserver umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="2e508-108">This component is installed on the Exchange 2013 Client Access server, and all calls to Exchange unified messaging (such as a voicemail) are first routed through the Call Router and then are redirected to the appropriate Mailbox server.</span></span>

<span data-ttu-id="2e508-109">Wenn Sie die Server-zu-Server-Authentifizierung bereits zwischen lync Server 2013 und Exchange 2013 konfiguriert haben, können Sie Unified Messaging einrichten.</span><span class="sxs-lookup"><span data-stu-id="2e508-109">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you are ready to setup unified messaging.</span></span> <span data-ttu-id="2e508-110">Dazu müssen Sie zuerst einen neuen Unified Messaging-Wählplan auf dem Exchange-Server erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2e508-110">To do so, you must first create and assign a new unified messaging dial plan on your Exchange server.</span></span> <span data-ttu-id="2e508-111">So konfigurieren diese beiden Befehle (die in der Exchange-Verwaltungsshell ausgeführt werden) einen neuen dreistelligen Wählplan für Exchange:</span><span class="sxs-lookup"><span data-stu-id="2e508-111">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="2e508-p103">Im ersten Befehl im Beispiel geben der Parameter „VoIPSecurity“ und der Parameterwert „Secured“ an, dass der Signalkanal mithilfe von TLS (Transport Layer Security) verschlüsselt wird. Der URI-Typ „SipName“ gibt an, dass Nachrichten unter Verwendung des SIP-Protokolls gesendet und empfangen werden, und der Wert „1“ für „CountryOrRegionCode“ gibt an, dass der Wählplan für die USA gilt.</span><span class="sxs-lookup"><span data-stu-id="2e508-p103">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>

<span data-ttu-id="2e508-114">Im zweiten Befehl gibt der an den Parameter „ConfiguredInCountryOrRegionGroups“ übergebene Parameterwert die länderinternen Gruppen an, die mit diesem Wählplan verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="2e508-114">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="2e508-115">Der Parameterwert "Anywhere; \* , \* \* " legt Folgendes fest:</span><span class="sxs-lookup"><span data-stu-id="2e508-115">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>

  - <span data-ttu-id="2e508-116">Gruppenname („Anywhere“)</span><span class="sxs-lookup"><span data-stu-id="2e508-116">Group name ("Anywhere")</span></span>

  - <span data-ttu-id="2e508-117">AllowedNumberString ( \* , ein Platzhalterzeichen, das angibt, dass eine beliebige Zahlen Zeichenfolge zulässig ist)</span><span class="sxs-lookup"><span data-stu-id="2e508-117">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>

  - <span data-ttu-id="2e508-118">DialNumberString ( \* , ein Platzhalterzeichen, das angibt, dass eine gewählte Nummer zulässig ist)</span><span class="sxs-lookup"><span data-stu-id="2e508-118">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>

  - <span data-ttu-id="2e508-119">Textcomment ( \* ein Platzhalterzeichen, das angibt, dass ein beliebiger Textbefehl zulässig ist)</span><span class="sxs-lookup"><span data-stu-id="2e508-119">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2e508-120">Die Erstellung eines neuen Wählplans sorgt zusätzlich für die Erstellung einer standardmäßigen Postfachrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="2e508-120">Creating a new dial plan will also create a Default Mailbox Policy.</span></span>



</div>

<span data-ttu-id="2e508-121">Nachdem Sie den neuen Wählplan erstellt und konfiguriert haben, müssen Sie den neuen Wählplan dem Unified Messaging-Server hinzufügen und dann den Startmodus dieses Servers ändern. insbesondere müssen Sie den Startmodus auf "Dual" einstellen.</span><span class="sxs-lookup"><span data-stu-id="2e508-121">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="2e508-122">Sie können diese beiden Aufgaben in der Exchange-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="2e508-122">You can perform both of these tasks from within the Exchange Management Shell:</span></span>

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

<span data-ttu-id="2e508-123">Nachdem der Unified Messaging-Server konfiguriert wurde, sollten Sie als nächstes das Enable-ExchangeCertificate-Cmdlet ausführen, um sicherzustellen, dass Ihr Exchange-Zertifikat auf den Unified Messaging-Dienst angewendet wird:</span><span class="sxs-lookup"><span data-stu-id="2e508-123">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

<span data-ttu-id="2e508-p106">Nachdem das Zertifikat ordnungsgemäß zugewiesen wurde, müssen Sie den MsExchangeUM-Dienst auf dem Unified Messaging-Server beenden und neu starten. Dieser Dienst muss jedes Mal beendet und neu gestartet werden, wenn der Startmodus geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="2e508-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>

<span data-ttu-id="2e508-126">Wenn die Konfiguration des UM-Servers abgeschlossen ist, können Sie den UM-Anrufrouter konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="2e508-126">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

<span data-ttu-id="2e508-127">Da der Startmodus geändert wurde, müssen Sie den MsExchangeUMCR-Dienst auf dem Computer mit dem UM-Anrufrouter beenden und neu starten.</span><span class="sxs-lookup"><span data-stu-id="2e508-127">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>

<span data-ttu-id="2e508-p107">Erstellen Sie zum Abschließen der Unified Messaging-Einrichtung eine UM-Postfachrichtlinie und aktivieren Sie dann mit dieser Richtlinie Benutzer für Unified Messaging. Sie können eine Postfachrichtlinie mit folgendem Befehl erstellen:</span><span class="sxs-lookup"><span data-stu-id="2e508-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="2e508-130">Sie können Unified Messaging für einen Benutzer mit einem Befehl wie dem folgenden aktivieren:</span><span class="sxs-lookup"><span data-stu-id="2e508-130">And you can enable a user for unified messaging by using a command similar to this:</span></span>

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

<span data-ttu-id="2e508-p108">Im vorherigen Befehl steht der Parameter „Extensions“ für die Durchwahlnummer des Benutzers. In diesem Beispiel besitzt der Benutzer die Durchwahl 100.</span><span class="sxs-lookup"><span data-stu-id="2e508-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>

<span data-ttu-id="2e508-133">Nach dem Aktivieren des Postfachs sollte der Benutzer „kenmyer@litwareinc.com“ Exchange Unified Messaging verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2e508-133">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="2e508-134">Sie können überprüfen, ob der Benutzer eine Verbindung mit Exchange um herstellen kann, indem Sie das Cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) in der lync Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="2e508-134">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet from within the Lync Server Management Shell:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="2e508-135">Wenn ein zweiter Benutzer vorhanden ist, für den Unified Messaging aktiviert wurde, können Sie mit dem Cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) sicherstellen, dass dieser zweite Benutzer eine Voicemailnachricht für den ersten Benutzer hinterlassen kann.</span><span class="sxs-lookup"><span data-stu-id="2e508-135">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

<span data-ttu-id="2e508-136"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="2e508-136"></div>

<span> </span>

</div>

</div>

</span></span></div>

