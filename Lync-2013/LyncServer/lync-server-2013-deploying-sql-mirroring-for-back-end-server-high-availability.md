---
title: Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern
description: Bereitstellen der SQL-Spiegelung für den Back-End-Server mit höherer Verfügbarkeit.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a2ab2d598249c12231668a888b442f830c5d65f
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49393995"
---
# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="33281-103">Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33281-103">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="33281-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="33281-104">

<span> </span></span></span>

<span data-ttu-id="33281-105">_**Letztes Änderungsdatum des Themas:** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="33281-105">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="33281-106">Damit eine SQL-Spiegelung bereitgestellt werden kann, müssen Ihre Server mindestens SQL Server 2008 R2 ausführen.</span><span class="sxs-lookup"><span data-stu-id="33281-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="33281-107">Diese Version muss auf allen beteiligten Servern (primärer Server, Spiegel und Zeuge) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="33281-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="33281-108">Ausführliche Informationen finden Sie unter [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921) .</span><span class="sxs-lookup"><span data-stu-id="33281-108">For details, see [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="33281-109">Im Allgemeinen müssen folgende Voraussetzungen erfüllt sein, um eine SQL-Spiegelung zwischen zwei Back-End-Servern mit einem Zeugen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="33281-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="33281-110">Die Version von SQL Server, die auf dem primären Server ausgeführt wird, muss die SQL-Spiegelung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="33281-110">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="33281-111">Prinzipal, Spiegel und Zeuge (sofern bereitgestellt) müssen dieselbe Version von SQL Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="33281-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="33281-p102">Prinzipal und Spiegel müssen dieselbe Version von SQL Server verwenden. Der Zeuge darf eine andere Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="33281-p102">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="33281-114">Informationen zu SQL-bewährten Methoden in Bezug auf die Unterstützung von SQL-Versionen für eine Zeugenrolle finden Sie unter "Daten Bank Spiegelungs Zeuge" in der MSDN Library unter [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345) .</span><span class="sxs-lookup"><span data-stu-id="33281-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="33281-115">Sie verwenden den Topologie-Generator zum Bereitstellen der SQL-Spiegelung.</span><span class="sxs-lookup"><span data-stu-id="33281-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="33281-116">Sie wählen eine Option im Topologie-Generator aus, um die Datenbanken zu spiegeln, und der Topologie-Generator richtet die Spiegelung (einschließlich der Einrichtung eines Zeugen bei Bedarf) ein, wenn Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="33281-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="33281-117">Beachten Sie, dass Sie den Zeugen zum selben Zeitpunkt wie den Spiegel einrichten oder entfernen müssen.</span><span class="sxs-lookup"><span data-stu-id="33281-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="33281-118">Es gibt keinen separaten Befehl, mit dem Sie nur einen Zeugen bereitstellen oder entfernen können.</span><span class="sxs-lookup"><span data-stu-id="33281-118">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="33281-119">Wenn Sie eine Serverspiegelung konfigurieren möchten, müssen Sie zuerst die SQL-Datenbankberechtigungen korrekt einrichten.</span><span class="sxs-lookup"><span data-stu-id="33281-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="33281-120">Ausführliche Informationen finden Sie unter "Einrichten von Anmeldekonten für Datenbankspiegelung oder AlwaysOn-Verfügbarkeitsgruppen (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454) .</span><span class="sxs-lookup"><span data-stu-id="33281-120">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="33281-p105">Bei der SQL-Spiegelung ist der Datenbankwiederherstellungsmodus immer auf **Vollständig** festgelegt, d. h. Sie müssen die Größe des Transaktionsprotokolls genau überwachen und Transaktionsprotokolle regelmäßig sichern, um zu verhindern, dass der Speicherplatz auf den Back-End-Servern zur Neige geht. Die Häufigkeit der Transaktionsprotokollsicherungen ist abhängig von der Wachstumsrate des Protokolls. Letztere richtet sich wiederum nach den Datenbanktransaktionen, die durch Benutzeraktivitäten im Front-End-Pool entstehen. Es wird empfohlen, dass Sie das zu erwartende Wachstum des Transaktionsprotokolls für Ihre Lync-Bereitstellungsarbeitsauslastung ermitteln und eine entsprechende Planung vornehmen. In den folgenden Artikeln finden Sie zusätzliche Informationen zur SQL-Sicherung und Protokollverwaltung:</span><span class="sxs-lookup"><span data-stu-id="33281-p105">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="33281-125">Daten Bank Wiederherstellungsmodelle: "Wiederherstellungsmodelle (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="33281-125">Database recovery models: "Recovery Models (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="33281-126">Übersicht über Backup: "Übersicht über Sicherungen (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="33281-126">Backup overview: "Backup Overview (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="33281-127">Backup-Transaktionsprotokoll: "Sichern eines Transaktionsprotokolls (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="33281-127">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="33281-128">Bei der SQL-Spiegelung können Sie die Topologie für die Spiegelung entweder beim Erstellen der Pools oder erst nach dem Erstellen der Pools konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="33281-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="33281-129">Die Verwendung des Topologie-Generators oder von Cmdlets zum Einrichten und Entfernen der SQL-Spiegelung wird nur unterstützt, wenn die Server für primär-, Spiegel-und Zeugen (falls erwünscht) zur gleichen Domäne gehören.</span><span class="sxs-lookup"><span data-stu-id="33281-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="33281-130">Wenn Sie die SQL-Spiegelung für Server einrichten möchten, die sich in unterschiedlichen Domänen befinden, erhalten Sie weitere Informationen in der Dokumentation zu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="33281-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="33281-131">Bei jeder Änderung an einer Spiegelungsbeziehung einer Back-End-Datenbank müssen Sie alle Front-End-Server im Pool neu starten. </span><span class="sxs-lookup"><span data-stu-id="33281-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="33281-132">Wenn Sie eine Änderung der Spiegelung vornehmen möchten (beispielsweise die Position einer Spiegelung ändern), müssen Sie den Topologie-Generator verwenden, um diese drei Schritte auszuführen:</span><span class="sxs-lookup"><span data-stu-id="33281-132">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="33281-133">Entfernen Sie die Spiegelung vom alten Spiegelserver.</span><span class="sxs-lookup"><span data-stu-id="33281-133">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="33281-134">Fügen Sie dem neuen Spiegelserver die Spiegelung hinzu.</span><span class="sxs-lookup"><span data-stu-id="33281-134">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="33281-135">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="33281-135">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="33281-136">Sie müssen eine Dateifreigabe erstellen, in die die Spiegeldateien geschrieben werden, und der Dienst, unter dem SQL Server und SQL Agent ausgeführt werden, benötigt Lese-/Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="33281-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="33281-137">Wenn der SQL Server-Dienst unter dem Kontext des Netzwerkdiensts ausgeführt wird, können Sie &lt; &gt; &lt; den Freigabeberechtigungen Domänen&#92;sqlservername &gt; $ sowohl der Prinzipal-als auch der Spiegelungs-SQL-Server hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="33281-137">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="33281-138">Das $-Zeichen ist wichtig, um anzugeben, dass es sich um ein Computerkonto handelt.</span><span class="sxs-lookup"><span data-stu-id="33281-138">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="33281-139">So konfigurieren Sie die SQL-Spiegelung beim Erstellen eines Pools im Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="33281-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="33281-140">Klicken Sie auf der Seite **SQL-Speicher definieren** neben dem Feld **SQL-Speicher** auf **Neu**. </span><span class="sxs-lookup"><span data-stu-id="33281-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="33281-141">Geben Sie auf der Seite **Neuen SQL-Speicher definieren** den primären Speicher ein, wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die SQL-Spiegelportnummer an (Standardwert 5022), und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="33281-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="33281-142">Wählen Sie auf der Seite **SQL-Speicher definieren** die Option **SQL-Speicherspiegelung aktivieren** aus. </span><span class="sxs-lookup"><span data-stu-id="33281-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="33281-p108">Geben Sie auf der Seite **Neuen SQL-Speicher definieren** den SQL-Speicher an, der als Spiegel verwendet werden soll. Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die Portnummer an (Standardwert 5022), und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="33281-p108">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="33281-145">Wenn Sie einen Zeugen für diesen Spiegel verwenden möchten, führen Sie folgende Schritte aus: </span><span class="sxs-lookup"><span data-stu-id="33281-145">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="33281-146">Wählen Sie **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** aus. </span><span class="sxs-lookup"><span data-stu-id="33281-146">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="33281-147">Wählen Sie auf der Seite **SQL-Speicher definieren** die Option **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** aus, und geben Sie den SQL-Speicher an, der als Zeuge verwendet werden soll. </span><span class="sxs-lookup"><span data-stu-id="33281-147">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="33281-148">Geben Sie die Portnummer an (Standardwert 7022), und klicken Sie auf **OK**. </span><span class="sxs-lookup"><span data-stu-id="33281-148">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="33281-149">Nachdem Sie die Definition des Front-End-Pools und aller anderen Rollen in Ihrer Topologie abgeschlossen haben, verwenden Sie den Topology Builder zum Veröffentlichen der Topologie.</span><span class="sxs-lookup"><span data-stu-id="33281-149">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="33281-150">Wenn die Topologie veröffentlicht wird und der Front-End-Pool, in dem der zentrale Verwaltungsspeicher gehostet wird, die SQL-Spiegelung aktiviert hat, wird eine Option zum Erstellen von primären und Spiegel-SQL Store-Datenbanken angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33281-150">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="33281-151">Klicken Sie auf **Einstellungen**, und geben Sie den Pfad ein, den Sie als Dateifreigabe für die Spiegelungssicherung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="33281-151">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="33281-p110">Klicken Sie auf **OK** und anschließend auf **Weiter**, um die Datenbanken zu erstellen und die Topologie zu veröffentlichen. Die Spiegel- und die Zeugeninstanz (sofern angegeben) werden bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="33281-p110">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="33281-154">Mithilfe des Topologie-Generators können Sie die Eigenschaften eines bereits vorhandenen Pools bearbeiten, um die SQL-Spiegelung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="33281-154">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="33281-155">So fügen Sie eine SQL-Spiegelung zu einem vorhandenen Front-End-Pool im Topologie-Generator hinzu</span><span class="sxs-lookup"><span data-stu-id="33281-155">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="33281-156">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="33281-156">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="33281-157">Wählen Sie **SQL-Speicherspiegelung aktivieren** aus, und klicken Sie dann neben **Spiegelungs-SQL-Speicher** auf **Neu**. </span><span class="sxs-lookup"><span data-stu-id="33281-157">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="33281-158">Geben Sie den SQL-Speicher an, der als Spiegel verwendet werden soll. </span><span class="sxs-lookup"><span data-stu-id="33281-158">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="33281-159">Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die Portnummer für die SQL-Spiegelung an (Standardwert 5022), und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="33281-159">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="33281-160">Wenn Sie einen Zeugen konfigurieren möchten, wählen Sie **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** aus, und klicken Sie dann auf **Neu**. </span><span class="sxs-lookup"><span data-stu-id="33281-160">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="33281-161">Geben Sie den SQL-Speicher an, der als Zeuge verwendet werden soll. </span><span class="sxs-lookup"><span data-stu-id="33281-161">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="33281-162">Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die Portnummer für die SQL-Spiegelung an (Standardwert 7022), und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="33281-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="33281-163">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="33281-163">Click **OK**.</span></span>

9.  <span data-ttu-id="33281-p111">Veröffentlichen Sie die Topologie. Dabei werden Sie zur Installation der Datenbank aufgefordert. </span><span class="sxs-lookup"><span data-stu-id="33281-p111">Publish the topology. When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="33281-p112">Während der Topologieveröffentlichung werden Sie aufgefordert, einen Dateifreigabepfad zu definieren. Die SQL-Server, die an der Spiegelung teilnehmen, benötigen Lese-/Schreibzugriff auf diese Dateifreigabe, damit der Spiegel eingerichtet werden kann.</span><span class="sxs-lookup"><span data-stu-id="33281-p112">During the topology publishing process, you will be asked to define a file share path. The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="33281-168">Sie müssen nun erst die Datenbank installieren, bevor Sie mit dem nächsten Schritt fortfahren können.</span><span class="sxs-lookup"><span data-stu-id="33281-168">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="33281-169">Bei der Einrichtung einer SQL-Spiegelung sollten Sie die folgenden Aspekte berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="33281-169">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="33281-170">Wenn bereits ein Spiegelungsendpunkt vorhanden ist, wird dieser mit den definierten Ports erneut verwendet. Die von Ihnen in der Topologie angegebenen Ports werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="33281-170">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="33281-p113">Alle bereits anderen Anwendungen auf demselben Server zugewiesenen Ports, einschließlich der Ports für andere SQL-Instanzen, sollten nicht für die jeweils installierten SQL-Instanzen verwendet werden. Das bedeutet, wenn mehrere SQL-Instanzen auf demselben Server installiert sind, dürfen diese Instanzen nicht denselben Port für die Spiegelung verwenden. Ausführliche Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="33281-p113">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
      - <span data-ttu-id="33281-174">"Geben Sie eine Server-Netzwerkadresse (Datenbankspiegelung)" in der MSDN Library unter [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="33281-174">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="33281-175">"Der Endpunkt der Datenbankspiegelung (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="33281-175">"The Database Mirroring Endpoint (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="33281-176">Verwenden von Cmdlets der lync Server-Verwaltungsshell zum Einrichten der SQL-Spiegelung</span><span class="sxs-lookup"><span data-stu-id="33281-176">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="33281-177">Die einfachste Möglichkeit zum Einrichten der Spiegelung ist die Verwendung des Topologie-Generators, Sie können dies aber auch mithilfe von Cmdlets vornehmen.</span><span class="sxs-lookup"><span data-stu-id="33281-177">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="33281-178">Öffnen Sie ein lync Server-Verwaltungsshell-Fenster, und führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="33281-178">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="33281-179">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="33281-179">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="33281-180">Folgendes wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="33281-180">You will see the following:</span></span>
    
        Database Name:rtcxds 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcshared 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcab 
                Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
                 Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsconfig 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:cpsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:xds 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:lis 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$
        [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

2.  <span data-ttu-id="33281-181">Überprüfen Sie die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="33281-181">Verify the following:</span></span>
    
      - <span data-ttu-id="33281-182">Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im primären SQL Server E04-OCS. Los \_ a. lsipt. local RTC aktiviert ist \\ .</span><span class="sxs-lookup"><span data-stu-id="33281-182">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="33281-183">Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im Mirror SQL Server K16-OCS. Los \_ a. lsipt. local RTC aktiviert ist \\ .</span><span class="sxs-lookup"><span data-stu-id="33281-183">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="33281-184">Auf Port 7022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im Zeugen SQL Server AB14-LCT. Los \_ a. lsipt. local RTC aktiviert ist \\ .</span><span class="sxs-lookup"><span data-stu-id="33281-184">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="33281-185">Konten, auf denen die SQL-Server auf allen Primär-und Spiegelservern ausgeführt werden, verfügen über Lese-/Schreibzugriff auf die Dateifreigabe \\ \\ E04-OCS- \\ csdatabackup</span><span class="sxs-lookup"><span data-stu-id="33281-185">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="33281-p114">Stellen Sie sicher, dass der Windows-Verwaltungsinstrumentationsanbieter (Windows Management Instrumentation, WMI) auf allen diesen Servern ausgeführt wird. Das Cmdlet verwendet diesen Anbieter, um die Kontoinformationen für die SQL Server-Dienste zu ermitteln, die auf allen primären, Spiegel- und Zeugenservern ausgeführt werden. </span><span class="sxs-lookup"><span data-stu-id="33281-p114">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="33281-188">Stellen Sie sicher, dass das Konto, unter dem dieses Cmdlet ausgeführt wird, für alle Spiegelserver über die Berechtigung zum Erstellen von Ordnern für die Daten- und Protokolldateien verfügt. </span><span class="sxs-lookup"><span data-stu-id="33281-188">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="33281-p115">Beachten Sie, dass das Benutzerkonto, unter dem die SQL-Instanz ausgeführt wird, über die Lese-/Schreibberechtigung für die Dateifreigabe verfügt. Wenn sich die Dateifreigabe auf einem anderen Server befindet und die SQL-Instanz unter einem lokalen Systemkonto ausgeführt wird, müssen Sie dem Server, auf dem die SQL-Instanz gehostet wird, Dateifreigabeberechtigungen erteilen.</span><span class="sxs-lookup"><span data-stu-id="33281-p115">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="33281-191">Geben Sie „A“ ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="33281-191">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="33281-192">Die Spiegelung wird konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="33281-192">The mirroring will be configured.</span></span>

<span data-ttu-id="33281-193">**Install-CsMirrorDatabase** installiert die Spiegelung und konfiguriert die Spiegelung für alle Datenbanken, die im primären SQL Store vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="33281-193">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="33281-194">Wenn Sie die Spiegelung nur für bestimmte Datenbanken konfigurieren möchten, können Sie die Option – DatabaseType verwenden, oder wenn Sie die Spiegelung für alle Datenbanken mit Ausnahme einiger weniger konfigurieren möchten, können Sie die Option-ExcludeDatabaseList zusammen mit einer durch Trennzeichen getrennten Liste der auszuschließenden Datenbanknamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="33281-194">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="33281-195">Wenn Sie beispielsweise die folgende Option an **Install-CsMirrorDatabase** anfügen, werden alle Datenbanken außer „rtcab“ und „rtcxds“ gespiegelt.</span><span class="sxs-lookup"><span data-stu-id="33281-195">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="33281-196">Wenn Sie beispielsweise die folgende Option an **Install-CsMirrorDatabase** anfügen, werden nur die Datenbanken „rtcab“, „rtcshared“ und „rtcxds“ gespiegelt.</span><span class="sxs-lookup"><span data-stu-id="33281-196">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="33281-197">Entfernen oder Ändern der SQL-Spiegelung</span><span class="sxs-lookup"><span data-stu-id="33281-197">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="33281-p117">Wenn Sie die SQL-Spiegelung eines Pools im Topologie-Generator entfernen möchten, müssen Sie zuerst mithilfe eines Cmdlets den Spiegel in SQL Server entfernen. Anschließend können Sie mithilfe des Topologie-Generators den Spiegel aus der Topologie entfernen. Verwenden Sie das folgende Cmdlet, um den Spiegel in SQL Server zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="33281-p117">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="33281-201">Geben Sie beispielsweise Folgendes ein, um die Spiegelung zu entfernen und die Datenbanken für die Benutzerdatenbanken zu verwerfen:</span><span class="sxs-lookup"><span data-stu-id="33281-201">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="33281-202">Die `-DropExistingDatabasesOnMirror` Option bewirkt, dass die betroffenen Datenbanken aus der Spiegelung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="33281-202">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="33281-203">Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="33281-203">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="33281-204">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="33281-204">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="33281-205">Deaktivieren Sie **SQL-Speicherspiegelung aktivieren**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="33281-205">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="33281-206">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="33281-206">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="33281-207">Entfernen eines Spiegelungszeugen</span><span class="sxs-lookup"><span data-stu-id="33281-207">Removing a Mirroring Witness</span></span>

<span data-ttu-id="33281-208">Verwenden Sie dieses Verfahren, wenn Sie den Zeugen aus einer Back-End-Server Spiegelungskonfiguration entfernen müssen.</span><span class="sxs-lookup"><span data-stu-id="33281-208">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="33281-209">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="33281-209">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="33281-210">Deaktivieren Sie **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren**, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="33281-210">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="33281-211">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="33281-211">Publish the topology.</span></span>
    
    <span data-ttu-id="33281-212">Nach der Veröffentlichung der Topologie wird in der Topologie-Builder eine Meldung angezeigt, die Folgendes enthält:</span><span class="sxs-lookup"><span data-stu-id="33281-212">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="33281-213">Führen Sie diesen Schritt jedoch nicht aus, und geben Sie nicht `Uninstall-CsMirrorDatabase` so ein, dass die gesamte Spiegelungskonfiguration deinstalliert wird.</span><span class="sxs-lookup"><span data-stu-id="33281-213">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="33281-214">Wenn Sie nur den Zeugen aus der SQL Server-Konfiguration entfernen möchten, folgen Sie den Anweisungen unter "Entfernen des Zeugen aus einer Datenbankspiegelungssitzung (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456) .</span><span class="sxs-lookup"><span data-stu-id="33281-214">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

<span data-ttu-id="33281-215"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="33281-215"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

