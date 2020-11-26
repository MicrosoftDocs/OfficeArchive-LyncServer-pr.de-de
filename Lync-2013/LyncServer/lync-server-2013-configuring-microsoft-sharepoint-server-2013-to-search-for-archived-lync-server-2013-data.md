---
title: 'Lync Server 2013: Konfigurieren von Microsoft SharePoint Server 2013 für die Suche nach archivierten lync Server 2013-Daten'
description: 'Lync Server 2013: Konfigurieren von Microsoft SharePoint Server 2013 für die Suche nach archivierten lync Server 2013-Daten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeabe49bb4f4e71bac7017497f3aadd9799bf515
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49432905"
---
# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a><span data-ttu-id="bec1a-103">Konfigurieren von Microsoft SharePoint Server 2013 zum Suchen nach archivierten Microsoft lync Server 2013-Daten</span><span class="sxs-lookup"><span data-stu-id="bec1a-103">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="bec1a-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="bec1a-104">

<span> </span></span></span>

<span data-ttu-id="bec1a-105">_**Letztes Änderungsdatum des Themas:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="bec1a-105">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="bec1a-106">Einer der Hauptvorteile für das Speichern von Instant Messaging-und Webkonferenz Protokollen in Microsoft Exchange Server 2013 anstelle von Microsoft lync Server 2013 besteht darin, dass Administratoren mithilfe eines einzigen Tools nach archivierten Exchange-Daten und/oder archivierten lync Server-Daten suchen können.</span><span class="sxs-lookup"><span data-stu-id="bec1a-106">One of the major advantages to storing instant messaging and Web conferencing transcripts in Microsoft Exchange Server 2013 instead of Microsoft Lync Server 2013 is the fact that storing data in the same location enables administrators to use a single tool to search for archived Exchange data and/or archived Lync Server data.</span></span> <span data-ttu-id="bec1a-107">Da alle Daten an derselben Stelle (Exchange) gespeichert sind, können alle Tools, die nach archivierten Exchange-Daten suchen können, auch nach archivierten lync Server-Daten suchen.</span><span class="sxs-lookup"><span data-stu-id="bec1a-107">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Lync Server data.</span></span>

<span data-ttu-id="bec1a-108">Ein Tool, mit dem Sie nach archivierten Daten einfach suchen können, ist Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bec1a-108">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="bec1a-109">Wenn Sie SharePoint zum Suchen nach lync Server-Daten verwenden möchten, müssen Sie zunächst alle Schritte ausführen, die bei der Konfiguration der Exchange-Archivierung in lync Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="bec1a-109">If you would like to use SharePoint to search for Lync Server data, you must first complete all the steps involved in configuring Exchange archiving in Lync Server.</span></span> <span data-ttu-id="bec1a-110">Nachdem Exchange 2013 und lync Server 2013 erfolgreich integriert wurden, müssen Sie die verwaltete API für Exchange-Webdienste, Version 2,0, auf Ihrem SharePoint-Server installieren. Das Setup-Programm für diese API kann aus dem Microsoft-Download Center () heruntergeladen werden [https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305) .</span><span class="sxs-lookup"><span data-stu-id="bec1a-110">After Exchange 2013 and Lync Server 2013 have been successfully integrated you must then install the Exchange Web Services Managed API Version 2.0 on your SharePoint Server; the setup program for that API can be downloaded from the Microsoft Downloads Center ([https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305)).</span></span> <span data-ttu-id="bec1a-111">Die heruntergeladene Datei (EWSManagedAPI.msi) kann in einem beliebigen Ordner auf Ihrem SharePoint-Server gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="bec1a-111">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>

<span data-ttu-id="bec1a-112">Wenn die Datei vollständig heruntergeladen ist, führen Sie auf dem SharePoint-Server folgendes Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="bec1a-112">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>

1.  <span data-ttu-id="bec1a-113">Öffnen Sie ein Befehlsfenster. Klicken Sie dazu auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bec1a-113">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>

2.  <span data-ttu-id="bec1a-114">Verwenden Sie im Befehlsfenster den Befehl **cd**, um das aktuelle Verzeichnis in den Ordner zu ändern, in dem die Datei „EWSManagedAPI.msi“ gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="bec1a-114">In the command window, use the **cd** command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="bec1a-115">Wenn Sie beispielsweise die Datei in C: Downloads gespeichert haben, \\ Geben Sie den folgenden Befehl im Befehlsfenster ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="bec1a-115">For example, if you have saved the file to C:\\Downloads type the following command in the command window and then press ENTER:</span></span>
    
        cd C:\Downloads

3.  <span data-ttu-id="bec1a-116">Zum Installieren der API geben Sie den folgenden Befehl ein und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="bec1a-116">To install the API, type the following command then press ENTER:</span></span>
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  <span data-ttu-id="bec1a-117">Wenn die API installiert ist, setzen Sie IIS zurück, indem Sie folgenden Befehl eingeben und die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="bec1a-117">After the API has been installed, reset IIS by typing the following command and pressing ENTER:</span></span>
    
        iisreset

<span data-ttu-id="bec1a-118">Nachdem Exchange-Webdienste installiert wurden, müssen Sie die Server-zu-Server-Authentifizierung zwischen SharePoint Server 2013 und Exchange 2013 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bec1a-118">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="bec1a-119">Öffnen Sie dazu zunächst die SharePoint 2013-Verwaltungsshell, und führen Sie den folgenden Befehlssatz aus:</span><span class="sxs-lookup"><span data-stu-id="bec1a-119">To do this, first open the SharePoint 2013 Management Shell and run the following set of command:</span></span>

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> <span data-ttu-id="bec1a-120">Achten Sie darauf, den URI für Ihren AutoErmittlungsdienst zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bec1a-120">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="bec1a-121">Verwenden Sie den Beispiel-URI nicht https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 .</span><span class="sxs-lookup"><span data-stu-id="bec1a-121">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span>



</div>

<span data-ttu-id="bec1a-122">Nachdem Sie den Token-Aussteller erstellt und den Tokendienst konfiguriert haben, führen Sie diese Befehle aus, und stellen Sie sicher, dass Sie die URL Ihrer SharePoint-Website für die Beispiel-URL ersetzen. http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="bec1a-122">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

<span data-ttu-id="bec1a-123">Wenn Sie die Server-zu-Server-Authentifizierung für Exchange 2013 konfigurieren möchten, öffnen Sie die Exchange-Verwaltungsshell, und führen Sie einen ähnlichen Befehl aus (vorausgesetzt, Exchange wurde auf Laufwerk C: installiert und verwendet den Standardordnerpfad):</span><span class="sxs-lookup"><span data-stu-id="bec1a-123">To configure server-to-server authentication for Exchange 2013, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

<span data-ttu-id="bec1a-124">Nachdem Sie die Partneranwendung konfiguriert haben, empfiehlt es sich, Internet Informationsdienste (IIS) auf allen Exchange-Post Fach-und Clientzugriffsservern zu beenden und neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="bec1a-124">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="bec1a-125">Sie können IIS neu starten, indem Sie einen ähnlichen Befehl verwenden, mit dem der Dienst auf dem Computer "ATL-Exchange-001" neu gestartet wird:</span><span class="sxs-lookup"><span data-stu-id="bec1a-125">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="bec1a-126">Dieser Befehl kann in der Exchange-Verwaltungsshell oder in einem anderen Befehlsfenster ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bec1a-126">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>

<span data-ttu-id="bec1a-127">Führen Sie als nächstes einen Befehl aus, der dem folgenden ähnelt, wodurch der angegebene Benutzer (in diesem Beispiel kenmyer) das Recht hat, eine Ermittlung in Exchange durchzuführen:</span><span class="sxs-lookup"><span data-stu-id="bec1a-127">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

<span data-ttu-id="bec1a-128">Nachdem die Server-zu-Server-Authentifizierung zwischen Exchange und SharePoint hergestellt wurde, besteht der nächste Schritt darin, eine eDiscovery-Website in SharePoint zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bec1a-128">After server-to-server authentication has been established between Exchange and SharePoint your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="bec1a-129">Dies kann durch Ausführen von Befehlen ähnlich wie in der SharePoint-Verwaltungsshell erfolgen:</span><span class="sxs-lookup"><span data-stu-id="bec1a-129">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> <span data-ttu-id="bec1a-130">„eDiscovery“ steht für „electronic Discovery“ (elektronische Ermittlung) und bezeichnet in der Regel das Durchsuchen von elektronischen Archiven nach Elementen, die in einem Gerichtsverfahren als Beweismittel zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="bec1a-130">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span>



</div>

<span data-ttu-id="bec1a-131">Wenn die neue Website fertig ist, besteht der nächste Schritt darin, Exchange 2013 so zu konfigurieren, dass Sie als ergebnisquelle für SharePoint fungiert.</span><span class="sxs-lookup"><span data-stu-id="bec1a-131">When the new site is ready, the next step is to configure Exchange 2013 to act as a result source for SharePoint.</span></span> <span data-ttu-id="bec1a-132">Sie können dies tun, indem Sie das folgende Verfahren auf der Seite SharePoint 2013-zentral Administration ausführen:</span><span class="sxs-lookup"><span data-stu-id="bec1a-132">You can do that by completing the following procedure from the SharePoint 2013 Central Administration page:</span></span>

1.  <span data-ttu-id="bec1a-133">Klicken Sie auf der Seite „Zentraladministration“ auf **Dienstanwendungen verwalten** und dann auf **Suchdienstanwendung**.</span><span class="sxs-lookup"><span data-stu-id="bec1a-133">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>

2.  <span data-ttu-id="bec1a-134">Klicken Sie auf der Seite „Suchdienstanwendung: Suchverwaltung“ auf **Ergebnisquellen** und dann auf **Neue Ergebnisquelle**.</span><span class="sxs-lookup"><span data-stu-id="bec1a-134">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>

3.  <span data-ttu-id="bec1a-135">Geben Sie im Bereich **Neue Ergebnisquelle** im Feld **Name** einen Namen für die neue Ergebnisquelle ein (z. B. **Microsoft Exchange**).</span><span class="sxs-lookup"><span data-stu-id="bec1a-135">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="bec1a-136">Wählen Sie **Exchange** als Ergebnis Quell **Protokoll** aus, und geben Sie dann im Feld **Exchange-Quell-URL** die URL des Webdienste-Quellcodes für Ihren Exchange-Server ein.</span><span class="sxs-lookup"><span data-stu-id="bec1a-136">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="bec1a-137">Die Quell-URL sollte in etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="bec1a-137">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  <span data-ttu-id="bec1a-138">Stellen Sie sicher, dass **AutoErmittlung verwenden** nicht ausgewählt ist, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bec1a-138">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>

<span data-ttu-id="bec1a-139">Erstellen Sie schließlich einen neuen eDiscovery-Fall und einen neuen eDiscovery-Satz, indem Sie das folgende Verfahren auf der SharePoint-Ermittlungs Website ausführen (beispielsweise https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="bec1a-139">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>

1.  <span data-ttu-id="bec1a-140">Klicken Sie auf der Seite **Websiteinhalte** auf Neuen Fall erstellen.</span><span class="sxs-lookup"><span data-stu-id="bec1a-140">On the Site Contents page click **Create a new case**.</span></span>

2.  <span data-ttu-id="bec1a-p110">Geben Sie auf der Seite „Websiteinhalte: Neue SharePoint-Website“ im Feld **Titel** den E-Mail-Alias des Benutzers (z. B. **kenmyer**) ein und geben Sie im Feld **Websiteadresse** dieselbe URL ein. Das Ergebnis ist eine ähnliche URL wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="bec1a-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  <span data-ttu-id="bec1a-143">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bec1a-143">Click **Create**.</span></span>

4.  <span data-ttu-id="bec1a-144">Wenn die Seite „eDiscovery-Satz“ angezeigt wird, klicken Sie unter **Identifizieren und beibehalten: eDiscovery-Sätze** auf **Neues Element**.</span><span class="sxs-lookup"><span data-stu-id="bec1a-144">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>

5.  <span data-ttu-id="bec1a-145">Geben Sie auf der Seite „Neu: eDiscovery-Satz“ im Feld **Name für eDiscovery-Satz** den E-Mail-Alias des Benutzers ein.</span><span class="sxs-lookup"><span data-stu-id="bec1a-145">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="bec1a-146">Geben Sie **eDiscovery lync \* *_ in das Feld _* Filter** ein, und klicken Sie dann auf **Hinzufügen & Quellen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="bec1a-146">Enter **eDiscovery Lync\**_ in the _\* Filter*\* box and then click **Add & Manage Sources**.</span></span>

6.  <span data-ttu-id="bec1a-p112">Geben Sie auf der Seite „Quellen hinzufügen und verwalten“ unter **Postfächer** im ersten Textfeld den E-Mail-Alias des Benutzers ein. Klicken Sie neben dem Textfeld auf das Symbol „Postfach überprüfen“, um sicherzustellen, dass SharePoint eine Verbindung mit dem angegebenen Postfach herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="bec1a-p112">On the Add & Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**. Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>

7.  <span data-ttu-id="bec1a-149">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bec1a-149">Click **OK**.</span></span>

8.  <span data-ttu-id="bec1a-150">Klicken Sie auf der Seite „eDiscovery-Satz“ auf **Speichern**, um den neuen eDiscovery-Satz zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bec1a-150">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>

<span data-ttu-id="bec1a-151">An diesem Punkt können Sie das angegebene Postfach (kenmyer) durchsuchen und/oder aktivieren, In-Place auf die gleiche Weise wie bei allen anderen SharePoint-Inhalten oder-Ergebnisquellen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="bec1a-151">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>

<span data-ttu-id="bec1a-152"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="bec1a-152"></div>

<span> </span>

</div>

</div>

</span></span></div>

