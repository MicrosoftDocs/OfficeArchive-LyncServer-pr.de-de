---
title: 'Lync Server 2013: Installieren von SQL Server Reporting Services'
description: 'Lync Server 2013: Installieren von SQL Server Reporting Services.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70da5e3845d18057b3362fa39953dee6cdc3d9f3
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427012"
---
# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="f2fb9-103">Installieren von SQL Server Reporting Services in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2fb9-103">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="f2fb9-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="f2fb9-104">

<span> </span></span></span>

<span data-ttu-id="f2fb9-105">_**Letztes Änderungsdatum des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="f2fb9-105">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="f2fb9-106">Wenn Sie beabsichtigen, Microsoft lync Server 2013-Überwachungsberichte zu verwenden (Weitere Informationen finden Sie im nächsten Abschnitt dieser Dokumentation), müssen Sie zuerst SQL Server Reporting Services installieren. Reporting Services kann zur gleichen Zeit installiert werden, wenn Sie Microsoft SQL Server oder nach der Installation von SQL Server installieren.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-106">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="f2fb9-107">Wenn Sie SQL Server nicht installiert haben, befolgen Sie die Anweisungen weiter oben in dieser Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-107">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="f2fb9-108">Stellen Sie bei der Installation von SQL Server sicher, dass Sie auf der Seite Featureauswahl die Option Reporting Services auswählen.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-108">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="f2fb9-109">, In dem SQL Server Reporting Services installiert wird.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-109">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="f2fb9-110">Wenn Sie bereits SQL Server installiert haben, aber SQL Server Reporting Services nicht installiert haben, können Sie dieses Feature hinzufügen, indem Sie die entsprechenden Anweisungen für SQL Server 2008 R2 oder SQL Server 2012 entsprechend befolgen.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-110">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="f2fb9-111">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Reporting Services erfolgreich installiert wurden:</span><span class="sxs-lookup"><span data-stu-id="f2fb9-111">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="f2fb9-112">Wenn Sie Microsoft SQL Server 2008 R2 ausführen, klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft SQL Server 2008 R2**, klicken Sie auf **Konfigurations Tools**, und klicken Sie dann auf **Reporting Services-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-112">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="f2fb9-113">Wenn Sie Microsoft SQL Server 2012 ausführen, klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft SQL Server 2012**, klicken Sie auf **Konfigurations Tools**, und klicken Sie dann auf **Reporting Services-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-113">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="f2fb9-114">Überprüfen Sie im Dialogfeld **Reporting Services-Konfigurationsverbindung** , ob der Name Ihres Servers im Feld **Servername** angezeigt wird und der Name der SQL Server-Instanz, die ihre Überwachungsdaten speichert, im Feld **Berichtsserverinstanz** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-114">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box.</span></span> <span data-ttu-id="f2fb9-115">Klicken Sie auf **verbinden**.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-115">Click **Connect**.</span></span>

<span data-ttu-id="f2fb9-116">Im Reporting Service-Konfigurations-Manager sollte der Bereich Berichtsserverstatus anzeigen, dass SQL Server Reporting Services installiert wurde und dass die Reporting Services aktuell ausgeführt werden: der Status des Berichtsservers sollte als **gestartet** angezeigt werden, und die Schaltfläche **Start** sollte abgeblendet und nicht verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-116">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="f2fb9-117">Wenn der Berichterstattungsdienst nicht ausgeführt wird, klicken Sie auf **Start** , um den Dienst zu starten.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-117">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="f2fb9-118">Wenn neben der Bezeichnung des Berichts Server-Datenbanknamens keine Datenbank aufgeführt ist, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="f2fb9-118">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="f2fb9-119">Klicken Sie im Reporting Services-Konfigurations-Manager auf **Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-119">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="f2fb9-120">Klicken Sie im Bereich Berichts Server-Datenbank auf **Datenbank ändern**.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-120">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="f2fb9-121">Wählen Sie im Konfigurations-Assistenten für Berichtsserver-Datenbank im Bereich "Aktion" die Option **neue Berichtsserver-Datenbank erstellen** aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-121">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="f2fb9-122">Überprüfen Sie im Konfigurations-Assistenten für die Berichts Server-Datenbank im Bereich Daten Bank Server, ob die in den Feldern **Server Name**, **Authentifizierungstyp** und **Benutzername** aufgeführten Informationen richtig sind.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-122">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct.</span></span> <span data-ttu-id="f2fb9-123">Klicken Sie auf **Verbindung testen** , um zu überprüfen, ob eine Verbindung mit dem Datenbankserver hergestellt werden kann, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-123">Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="f2fb9-124">Übernehmen Sie im Konfigurations-Assistenten für die Berichtsserver-Datenbank im Datenbankbereich die Standardwerte für **Datenbankname**, **Sprache** und **Berichtsservermodus** , und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-124">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="f2fb9-125">Überprüfen Sie im Assistenten für die Berichts Server-Datenbankkonfiguration im Bereich Anmeldeinformationen, ob die richtigen Informationen in der Dropdownliste **Authentifizierungstyp** und den Feldern **Benutzername** und **Kennwort** aufgeführt sind, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-125">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="f2fb9-126">Klicken Sie im Konfigurations-Assistenten für Berichts Server-Datenbank im Zusammenfassungsbereich auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-126">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="f2fb9-127">Klicken Sie im Konfigurations-Assistenten für Berichts Server-Datenbank im Bereich Status und fertig stellen auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-127">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="f2fb9-128">Wenn Sie überprüfen möchten, ob die Reporting Services-URLs konfiguriert wurden, klicken Sie auf **Webdienst-URL**.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-128">To verify that the Reporting Service URLs have been configured, click **Web Service URL**.</span></span> <span data-ttu-id="f2fb9-129">Es sollte eine oder mehrere URLs angezeigt werden, die unter der Überschrift **Berichts Server-Webdienst-URLs** aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-129">You should see one or more URLs listed under the heading **Report Server Web Service URLs**.</span></span> <span data-ttu-id="f2fb9-130">Klicken Sie auf jede dieser URLs, um zu überprüfen, ob Sie die Startseite für die lokale Installation von SQL Server Reporting Services erreichen können.</span><span class="sxs-lookup"><span data-stu-id="f2fb9-130">Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

<span data-ttu-id="f2fb9-131"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="f2fb9-131"></div>

<span> </span>

</div>

</div>

</span></span></div>

