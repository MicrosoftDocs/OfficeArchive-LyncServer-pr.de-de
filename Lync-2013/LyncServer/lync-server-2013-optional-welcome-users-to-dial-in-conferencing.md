---
title: 'Lync Server 2013: (Optional) Einladen von Benutzern zu Einwahlkonferenzen'
description: 'Lync Server 2013: (optional) willkommene Benutzer für Einwahlkonferenzen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d33c7184a8cf22699b4ebe8d8ea8b4ef1c133a3
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49424842"
---
# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="ed851-103">(Optional) Einladen von Benutzern zu Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed851-103">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="ed851-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="ed851-104">

<span> </span></span></span>

<span data-ttu-id="ed851-105">_**Letztes Änderungsdatum des Themas:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="ed851-105">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="ed851-106">Nachdem Sie Einwahlkonferenzen konfiguriert und getestet haben, um sicherzustellen, dass Sie ordnungsgemäß funktioniert, sollten Sie anfängliche persönliche Identifikationsnummern (Pins) für Benutzer festlegen und die Benutzer über die Verfügbarkeit des Features informieren, einschließlich einführenden Anweisungen wie der anfänglichen PIN und dem Link zur Webseite für Einwahlkonferenzeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ed851-106">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="ed851-107">Dieser Schritt ist optional.</span><span class="sxs-lookup"><span data-stu-id="ed851-107">This step is optional.</span></span> <span data-ttu-id="ed851-108">In der Regel verwenden Sie das Cmdlet " **Satz-CsClientPin** ", um Pins zurückzusetzen, doch Sie können das Verfahren in diesem Thema zum ersten Mal verwenden, wenn Sie eine Willkommens-e-Mail mit den Informationen senden möchten.</span><span class="sxs-lookup"><span data-stu-id="ed851-108">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="ed851-109">Wenn Sie keine E-Mail senden möchten, können Sie stattdessen das Cmdlet **Set-CsClientPin** verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed851-109">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="ed851-110">Sie können mithilfe des Skripts **Set-CsPinSendCAWelcomeMail** eine PIN für einen einzelnen Benutzer einrichten und diesem Benutzer eine Begrüßungs-E-Mail senden.</span><span class="sxs-lookup"><span data-stu-id="ed851-110">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="ed851-111">Standardmäßig setzt das Skript eine PIN nicht zurück, wenn Sie bereits festgesetzt ist, aber Sie können den Parameter **Force** verwenden, um das Zurücksetzen einer PIN zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="ed851-111">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="ed851-112">Die E-Mail-Nachricht wird über SMTP (Simple Mail Transfer Protocol) gesendet.</span><span class="sxs-lookup"><span data-stu-id="ed851-112">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="ed851-113">Sie können ein Skript erstellen, mit dem das **Set-CsPinSendCAWelcomeMail**-Skript iterativ ausgeführt wird, um PINs für eine Benutzergruppe einzurichten und E-Mails an diese Gruppe zu senden.</span><span class="sxs-lookup"><span data-stu-id="ed851-113">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="ed851-114">Sie können die e-Mail-Vorlage (also die **CAWelcomeEmailTemplate.html** -Datei) ändern, um weitere Links zu Intranetseiten hinzuzufügen oder den e-Mail-Text zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ed851-114">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="ed851-115">So setzen Sie eine Initiale PIN und senden eine Willkommens-e-Mail</span><span class="sxs-lookup"><span data-stu-id="ed851-115">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="ed851-116">Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="ed851-116">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="ed851-117">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="ed851-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ed851-118">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="ed851-118">Run the following at the command prompt:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri <user identifier>
        -From <email address of sender> [-Subject <subject for email message>]
        [-UserEmailAddress <destination email address>]
        [-Cc <email address of recipients who receive copy of email>]
        [-Bcc <email address of recipients who receive blind copies>]
        [-TemplatePath <path for email template>]
        [-SmtpServer] <SMTP server name>]
        [-BodyAsPlainText] [-UseSsl]
        [-Pin <new numeric PIN>] [-Force] `
        [-Credential <SMTP server credentials used to send email with the specified From address>]
    
    <span data-ttu-id="ed851-119">**SmtpServer**   Standardmäßig verwendet das Skript den Wert der reservierten Umgebungsvariablen **$PSEmailServer** für diesen Parameter.</span><span class="sxs-lookup"><span data-stu-id="ed851-119">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="ed851-120">Wenn die Variable **$PSEmailServer** nicht gesetzt ist, müssen Sie diesen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="ed851-120">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="ed851-121">**Anmeldeinformationen**   Standardmäßig verwendet das Skript die Anmeldeinformationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ed851-121">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="ed851-122">Wenn der aktuelle Benutzer nicht zum Senden von E-Mails im Namen der angegebenen Absenderadresse berechtigt ist, müssen Sie diesen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="ed851-122">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="ed851-123">Als allgemeine Regel gilt: Wenn Sie nicht Ihre E-Mail-Adresse als Absenderadresse verwenden, geben Sie diesen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="ed851-123">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="ed851-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ed851-124">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="ed851-125">In diesem Beispiel wird eine neue PIN erstellt und dann eine Willkommens-e-Mail von Marco an Bob gesendet.</span><span class="sxs-lookup"><span data-stu-id="ed851-125">This example creates a new PIN and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="ed851-126">Hierbei wird der E-Mail-Text der Standardvorlage verwendet und die E-Mail-Nachricht wird im HTML-Format erstellt.</span><span class="sxs-lookup"><span data-stu-id="ed851-126">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="ed851-127">Das Standardthema lautet "Willkommen bei Dial in Conferencing".</span><span class="sxs-lookup"><span data-stu-id="ed851-127">The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="ed851-128">Ein weiteres Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ed851-128">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="ed851-129">In diesem Beispiel wird eine neue PIN mit dem Wert "383042650" für Bob erzwungen, obwohl Bob über eine vorhandene Pin verfügte und dann eine Willkommens-e-Mail von Marco an Bob sendet.</span><span class="sxs-lookup"><span data-stu-id="ed851-129">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="ed851-130">Da der Parameter „Credential“ angegeben ist, wird die Person, die den Befehl ausführt, zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ed851-130">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="ed851-131">Die e-Mail wird mithilfe des Secure Sockets Layer (SSL) gesendet.</span><span class="sxs-lookup"><span data-stu-id="ed851-131">The email is sent by using the Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="ed851-132"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="ed851-132"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

