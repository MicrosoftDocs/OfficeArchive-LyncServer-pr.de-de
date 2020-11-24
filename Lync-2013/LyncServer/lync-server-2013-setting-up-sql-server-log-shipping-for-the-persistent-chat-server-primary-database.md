---
title: 'Lync Server 2013: Einrichten des SQL Server-Protokollversands für die primäre Datenbank des Servers für beständigen Chat'
description: 'Lync Server 2013: Einrichten des SQL Server-Protokollversands für die primäre Datenbank des beständigen Chat Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72b7e68bd0cb7b9f544b86a15204d3e832692ec1
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394954"
---
# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="bfd39-103">Einrichten des SQL Server-Protokollversands für die primäre Datenbank des Servers für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfd39-103">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="bfd39-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="bfd39-104">

<span> </span></span></span>

<span data-ttu-id="bfd39-105">_**Letztes Änderungsdatum des Themas:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="bfd39-105">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="bfd39-106">Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der sekundären Protokollversand-Datenbankinstanz des beständigen Chat Servers her, und stellen Sie sicher, dass der SQL Server-Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bfd39-106">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="bfd39-107">Führen Sie die folgenden Schritte aus, indem Sie SQL Server Management Studio verwenden, das mit der primären Datenbankinstanz für beständigen Chat verbunden ist:</span><span class="sxs-lookup"><span data-stu-id="bfd39-107">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="bfd39-108">Stellen Sie sicher, dass der SQL Server-Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bfd39-108">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="bfd39-109">Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bfd39-109">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="bfd39-110">Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.</span><span class="sxs-lookup"><span data-stu-id="bfd39-110">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="bfd39-111">Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="bfd39-111">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="bfd39-112">Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="bfd39-112">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="bfd39-113">Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zur Freigabe ein, die Sie für den Ordner mit den Transaktionsprotokollsicherungen erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="bfd39-113">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="bfd39-114">Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Sicherungsordner im **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie einen lokalen Pfad zu dem Ordner ein (Beispiel: c: \\ Sicherung)** .</span><span class="sxs-lookup"><span data-stu-id="bfd39-114">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="bfd39-115">(Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="bfd39-115">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bfd39-116">Wenn das SQL Server-Dienstkonto auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie den Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad zu diesem Ordner angeben.</span><span class="sxs-lookup"><span data-stu-id="bfd39-116">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="bfd39-117">Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.</span><span class="sxs-lookup"><span data-stu-id="bfd39-117">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="bfd39-118">Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an.</span><span class="sxs-lookup"><span data-stu-id="bfd39-118">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="bfd39-119">Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Planen**, und passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="bfd39-119">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="bfd39-120">Wählen Sie unter **Komprimierung** die Option **Standardservereinstellung verwenden** aus und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfd39-120">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="bfd39-121">Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bfd39-121">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="bfd39-122">Klicken Sie auf **verbinden** , und stellen Sie eine Verbindung mit der Instanz von SQL Server her, die Sie als sekundären Server konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="bfd39-122">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="bfd39-123">Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="bfd39-123">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="bfd39-124">Aktivieren Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option **Ja, eine vollständige Sicherung der primären Datenbank generieren und diese Sicherung in der sekundären Datenbank wiederherstellen (und die sekundäre Datenbank erstellen, falls diese nicht vorhanden ist)**.</span><span class="sxs-lookup"><span data-stu-id="bfd39-124">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="bfd39-p103">Geben Sie auf der Registerkarte **Dateien kopieren** im Feld **Zielordner für kopierte Dateien** den Pfad zum Ordner ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen. Dieser Ordner befindet sich oft auf dem sekundären Server.</span><span class="sxs-lookup"><span data-stu-id="bfd39-p103">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="bfd39-127">Beachten Sie den im Feld **Zeitplan** unter **Kopierauftrag** aufgeführten Kopierzeitplan.</span><span class="sxs-lookup"><span data-stu-id="bfd39-127">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="bfd39-128">Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Planen**, und passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="bfd39-128">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="bfd39-129">Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.</span><span class="sxs-lookup"><span data-stu-id="bfd39-129">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="bfd39-130">Wählen Sie auf der Registerkarte **Wiederherstellen** unter **Datenbankstatus beim Wiederherstellen von Sicherungen** die Option **Kein Wiederherstellungsmodus** aus.</span><span class="sxs-lookup"><span data-stu-id="bfd39-130">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="bfd39-131">Wählen Sie unter **Wiederherstellen von Sicherungen verzögern um mindestens:** die Option **0 Minuten** aus.</span><span class="sxs-lookup"><span data-stu-id="bfd39-131">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="bfd39-132">Wählen Sie unter **Warnen, wenn keine Wiederherstellung erfolgt in** einen Warnschwellenwert aus.</span><span class="sxs-lookup"><span data-stu-id="bfd39-132">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="bfd39-133">Sehen Sie sich den im Feld **Zeitplan** unter **Wiederherstellungsauftrag** aufgeführten Wiederherstellungszeitplan an.</span><span class="sxs-lookup"><span data-stu-id="bfd39-133">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="bfd39-134">Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan**, passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfd39-134">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="bfd39-135">Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.</span><span class="sxs-lookup"><span data-stu-id="bfd39-135">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="bfd39-136">Klicken Sie im Dialogfeld **Datenbankeigenschaften** auf **OK**, um den Konfigurationsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="bfd39-136">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

<span data-ttu-id="bfd39-137"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="bfd39-137"></div>

<span> </span>

</div>

</div>

</span></span></div>

