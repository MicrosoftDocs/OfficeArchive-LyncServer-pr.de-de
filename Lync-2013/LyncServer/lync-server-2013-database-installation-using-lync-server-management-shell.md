---
title: 'Lync Server 2013: Installieren von Datenbanken mithilfe der Lync Server-Verwaltungsshell'
description: 'Lync Server 2013: Datenbankinstallation mithilfe der lync Server-Verwaltungsshell.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d572984c94d280723b12c5343a92ddfaa12d4f0
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431253"
---
# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="52cfb-103">Installieren von Datenbanken mithilfe der Lync Server-Verwaltungsshell in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52cfb-103">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="52cfb-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="52cfb-104">

<span> </span></span></span>

<span data-ttu-id="52cfb-105">_**Letztes Änderungsdatum des Themas:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="52cfb-105">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="52cfb-106">Die Trennung von Rollen und Zuständigkeiten zwischen Serveradministratoren und SQL Server-Administratoren kann zu Verzögerungen bei der Implementierung führen.</span><span class="sxs-lookup"><span data-stu-id="52cfb-106">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="52cfb-107">Lync Server 2013 verwendet rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC), um diese Probleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="52cfb-107">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="52cfb-108">In einigen Fällen muss der SQL Server-Administrator die Installation von Datenbanken auf dem SQL Server-basierten Server außerhalb von RBAC verwalten.</span><span class="sxs-lookup"><span data-stu-id="52cfb-108">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="52cfb-109">Die lync Server 2013-Verwaltungsshell bietet dem SQL Server-Administrator die Möglichkeit, Windows PowerShell-Cmdlets auszuführen, die zum Konfigurieren der Datenbanken mit den korrekten Daten und Protokolldateien entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="52cfb-109">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="52cfb-110">Ausführliche Informationen finden Sie unter [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52cfb-110">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="52cfb-111">Im folgenden Verfahren wird davon ausgegangen, dass mindestens die lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012-Verwaltungsobjekte, CLR-Typen für Microsoft SQL Server 2012 und Microsoft SQL Server 2012 ADOMD.NET installiert sind.</span><span class="sxs-lookup"><span data-stu-id="52cfb-111">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="52cfb-112">Die OCSCore.msi befindet sich auf dem Installationsmedium im \Setup\AMD64\Setup-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="52cfb-112">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="52cfb-113">Die restlichen Komponenten befinden sich in \setup\amd64.</span><span class="sxs-lookup"><span data-stu-id="52cfb-113">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="52cfb-114">Darüber hinaus wurde die Active Directory-Vorbereitung für lync Server 2013 erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="52cfb-114">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="52cfb-115">" **Installieren-CsDatabase** " ist das Windows PowerShell-Cmdlet, mit dem Sie die Datenbanken installieren.</span><span class="sxs-lookup"><span data-stu-id="52cfb-115">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="52cfb-116">Das Cmdlet " **install-CsDatabase** " verfügt über eine große Anzahl von Parametern, von denen nur einige hier besprochen werden.</span><span class="sxs-lookup"><span data-stu-id="52cfb-116">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="52cfb-117">Details zu den möglichen Parametern finden Sie in der Dokumentation zur lync Server 2013-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="52cfb-117">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="52cfb-118">Um die Leistung und mögliche Timeoutprobleme zu vermeiden, sollten Sie immer vollqualifizierte Domänennamen (FQDNs) verwenden, wenn Sie auf SQL Server-basierte Server verweisen.</span><span class="sxs-lookup"><span data-stu-id="52cfb-118">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="52cfb-119">Vermeiden Sie die Verwendung von Host Namen bezogenen verweisen.</span><span class="sxs-lookup"><span data-stu-id="52cfb-119">Avoid using host name-only references.</span></span> <span data-ttu-id="52cfb-120">Verwenden Sie beispielsweise sqlbe01.contoso.net, aber vermeiden Sie die Verwendung von sqlbe01.</span><span class="sxs-lookup"><span data-stu-id="52cfb-120">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="52cfb-121">Für die Installation von Datenbanken verwendet **install-CsDatabase** drei primäre Methoden zum Platzieren der Datenbanken auf dem vorbereiteten SQL Server-basierten Server:</span><span class="sxs-lookup"><span data-stu-id="52cfb-121">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="52cfb-122">Führen Sie **install-CsDatabase** ohne DatabasePaths oder UseDefaultSqlPath aus.</span><span class="sxs-lookup"><span data-stu-id="52cfb-122">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="52cfb-123">Das Cmdlet verwendet einen integrierten Algorithmus, um die beste Platzierung für das Protokoll und die Datendateien zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="52cfb-123">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="52cfb-124">Der Algorithmus funktioniert nur für eigenständige SQL Server-Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="52cfb-124">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="52cfb-125">Führen Sie **install-CsDatabase** mit dem DatabasePaths-Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="52cfb-125">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="52cfb-126">Der integrierte Algorithmus zum Optimieren von Protokoll-und Datendateispeicher Orten wird nicht verwendet, wenn der DatabasePaths-Parameter definiert ist.</span><span class="sxs-lookup"><span data-stu-id="52cfb-126">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="52cfb-127">Mithilfe dieses Parameters können Sie die Speicherorte definieren, an denen Protokoll-und Datendateien bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="52cfb-127">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="52cfb-128">Führen Sie **install-CsDatabase** mit UseDefaultSqlPaths aus.</span><span class="sxs-lookup"><span data-stu-id="52cfb-128">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="52cfb-129">Diese Option verwendet nicht den integrierten Algorithmus, um die Speicherorte für Protokolle und Datendateien zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="52cfb-129">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="52cfb-130">Protokoll-und Datendatei werden gemäß den vom SQL Server-Administrator gesetzten Standardeinstellungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="52cfb-130">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="52cfb-131">Diese Pfade werden in der Regel für die automatische Verwaltung von Protokoll-und Datendateien auf dem SQL Server im Voraus eingestellt und sind nicht mit dem Setup von lync Server 2013 verbunden.</span><span class="sxs-lookup"><span data-stu-id="52cfb-131">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="52cfb-132">Der DatabasePathMap-Parameter kann auch verwendet werden, um einen Speicherort für jede Datenbank und die zugehörige Protokolldatei explizit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="52cfb-132">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="52cfb-133">So verwenden Sie Windows PowerShell-Cmdlets zum Konfigurieren des SQL Server Central-Verwaltungsspeichers</span><span class="sxs-lookup"><span data-stu-id="52cfb-133">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="52cfb-134">Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server-basierten Server an.</span><span class="sxs-lookup"><span data-stu-id="52cfb-134">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="52cfb-135">Ausführliche Informationen finden Sie unter [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52cfb-135">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="52cfb-136">Öffnen Sie die lync Server 2013-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="52cfb-136">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="52cfb-137">Wenn Sie die Ausführungsrichtlinie für Windows PowerShell nicht angepasst haben, müssen Sie die Richtlinie so anpassen, dass Windows PowerShell-Skripts ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="52cfb-137">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="52cfb-138">Ausführliche Informationen finden Sie unter "Überprüfen der Ausführungsrichtlinie" unter [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093) .</span><span class="sxs-lookup"><span data-stu-id="52cfb-138">For details, see “Examining the Execution Policy” at [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="52cfb-139">Verwenden Sie das Cmdlet " **install-CsDatabase** ", um den zentralen Verwaltungsspeicher zu installieren.</span><span class="sxs-lookup"><span data-stu-id="52cfb-139">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="52cfb-140">Der Berichtsparameter ist optional, aber hilfreich, wenn Sie den Installationsvorgang dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="52cfb-140">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="52cfb-141">**Install-CsDatabase – DatabasePaths** kann bis zu sechs Pfadparameter verwenden, die jeweils die Pfade für die Laufwerke definieren, wie Sie in SQL Server-Daten und in der Protokolldatei Platzierung definiert sind.</span><span class="sxs-lookup"><span data-stu-id="52cfb-141">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="52cfb-142">Nach den logischen Regeln der Datenbankkonfiguration in lync Server 2013 werden Laufwerke in Buckets von zwei, vier oder sechs analysiert.</span><span class="sxs-lookup"><span data-stu-id="52cfb-142">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="52cfb-143">Je nach SQL Server-Konfiguration und Anzahl der Buckets werden zwei Pfade, vier Pfade oder sechs Pfade bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="52cfb-143">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="52cfb-144">Wenn Sie über drei Laufwerke verfügen, erhält das Protokoll Priorität, und danach werden die Datendateien verteilt.</span><span class="sxs-lookup"><span data-stu-id="52cfb-144">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="52cfb-145">Ein Beispiel für einen auf SQL Server basierenden Server, der mit sechs Laufwerken konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="52cfb-145">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="52cfb-146">Nach Abschluss der Datenbankinstallation können Sie die lync Server 2013-Verwaltungsshell schließen oder mit der Installation der im Topologie-Generator definierten lync Server 2013-Datenbanken fortfahren.</span><span class="sxs-lookup"><span data-stu-id="52cfb-146">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="52cfb-147">So verwenden Sie Windows PowerShell-Cmdlets zum Konfigurieren der konfigurierten SQL Server-Topologie für Datenbanken</span><span class="sxs-lookup"><span data-stu-id="52cfb-147">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="52cfb-148">Zum Installieren des Topologie-Generators, der für lync Server 2013 konfiguriert ist, muss der lync Server 2013-Administrator die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="52cfb-148">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="52cfb-149">Ausführliche Informationen finden Sie unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="52cfb-149">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="52cfb-150">Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server-basierten Server an.</span><span class="sxs-lookup"><span data-stu-id="52cfb-150">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="52cfb-151">Lesen Sie das Thema [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52cfb-151">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="52cfb-152">Um die SQL Server-basierten Datenbanken konfigurieren zu können, müssen Sie sicherstellen, dass das SQL Server-Administratorkonto, das zum Ausführen der hier beschriebenen Schritte verwendet wird, auch ein Mitglied der Gruppe Sysadmins (oder Äquivalent) auf dem Server ist, auf dem SQL Server ausgeführt wird, und die zentrale Verwaltungs Server Rolle innehat.</span><span class="sxs-lookup"><span data-stu-id="52cfb-152">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="52cfb-153">Dies ist besonders wichtig, um nach weiteren lync Server 2013-Pools zu suchen, die eine SQL Server-Datenbankinstallation oder-Konfiguration erfordern.</span><span class="sxs-lookup"><span data-stu-id="52cfb-153">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="52cfb-154">Wenn Sie beispielsweise einen zweiten Pool (pool02) bereitstellen, die zentrale Verwaltungs Server Rolle aber von pool01 gehalten wird.</span><span class="sxs-lookup"><span data-stu-id="52cfb-154">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="52cfb-155">Die SQL Server-Gruppe sysadmin (oder eine entsprechende) muss über Berechtigungen für beide SQL Server-basierten Datenbanken verfügen.</span><span class="sxs-lookup"><span data-stu-id="52cfb-155">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="52cfb-156">Öffnen Sie die lync Server 2013-Verwaltungsshell, wenn Sie noch nicht geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="52cfb-156">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="52cfb-157">Verwenden Sie das Cmdlet " **install-CsDatabase** ", um die konfigurierten Datenbanken des Topologie-Generators zu installieren.</span><span class="sxs-lookup"><span data-stu-id="52cfb-157">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="52cfb-158">Der Berichtsparameter ist optional, aber hilfreich, wenn Sie den Installationsvorgang dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="52cfb-158">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="52cfb-159">Wenn die Datenbankinstallation abgeschlossen ist, schließen Sie die lync Server 2013-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="52cfb-159">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="52cfb-160">So verwenden Sie Windows PowerShell-Cmdlets zum Konfigurieren der SQL Server-Topologie mithilfe des DatabasePathMap-Parameters</span><span class="sxs-lookup"><span data-stu-id="52cfb-160">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="52cfb-161">Zum Installieren von Datenbanken für lync Server 2013 muss der lync Server-Administrator die Pfade erstellen und die Datenbankendateien und Protokolldateien entsprechend einem vordefinierten Satz von Regeln bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="52cfb-161">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="52cfb-162">Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server-basierten Server an.</span><span class="sxs-lookup"><span data-stu-id="52cfb-162">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="52cfb-163">Lesen Sie das Thema [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52cfb-163">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="52cfb-164">Um die SQL Server-basierten Datenbanken konfigurieren zu können, müssen Sie sicherstellen, dass das SQL Server-Administratorkonto, das zum Ausführen der hier beschriebenen Schritte verwendet wird, auch ein Mitglied der Gruppe Sysadmins (oder Äquivalent) auf dem Server ist, auf dem SQL Server ausgeführt wird, und die zentrale Verwaltungs Server Rolle innehat.</span><span class="sxs-lookup"><span data-stu-id="52cfb-164">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="52cfb-165">Dies ist besonders wichtig, um nach weiteren lync Server-Pools zu suchen, die eine SQL Server-Datenbankinstallation oder-Konfiguration erfordern.</span><span class="sxs-lookup"><span data-stu-id="52cfb-165">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="52cfb-166">Wenn Sie beispielsweise einen zweiten Pool (pool02) bereitstellen, die zentrale Verwaltungs Server Rolle aber von pool01 gehalten wird.</span><span class="sxs-lookup"><span data-stu-id="52cfb-166">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="52cfb-167">Die SQL Server-Gruppe sysadmin (oder eine entsprechende) muss über Berechtigungen für beide SQL Server-basierten Datenbanken verfügen.</span><span class="sxs-lookup"><span data-stu-id="52cfb-167">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="52cfb-168">Öffnen Sie die lync Server-Verwaltungsshell, wenn Sie noch nicht geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="52cfb-168">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="52cfb-169">Verwenden Sie das Cmdlet **install-CsDatabase** mit dem DatabasePathMap-Parameter und einer PowerShell-Hashtabelle, um die konfigurierten Datenbanken des Topologie-Generators zu installieren.</span><span class="sxs-lookup"><span data-stu-id="52cfb-169">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="52cfb-170">Im Beispielcode können die für die Datenbanken definierten Pfade auf granulare Weise mithilfe des – DatabasePathMap-Parameters und einer definierten Hashtabelle wie folgt bestimmt werden (im Beispiel wird "c: \\ CSData" für alle Datenbankdateien (MDF) und "c: \\ CSLogFiles" für alle Protokolldateien (LDF) verwendet.</span><span class="sxs-lookup"><span data-stu-id="52cfb-170">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="52cfb-171">Der Ordner wird nach Bedarf von install-CsDatabase erstellt):</span><span class="sxs-lookup"><span data-stu-id="52cfb-171">Folder will be created as needed by Install-CsDatabase):</span></span>
    ```powershell
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
    "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
    "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
    }
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  <span data-ttu-id="52cfb-172">Da die Datenbank-und Protokolldateien explizit mit ihrem Speicherort auf dem Zieldatenbankserver benannt sind, können Sie bestimmte Speicherorte für die tatsächliche Datenbank und den Speicherort des jeweiligen Diensttyps definieren.</span><span class="sxs-lookup"><span data-stu-id="52cfb-172">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="52cfb-173">Im folgenden Beispiel werden Datenbanken für jeden bestimmten Diensttyp auf separaten Datenträgern und zugehörigen Protokolldateien auf einer anderen Festplatte platziert.</span><span class="sxs-lookup"><span data-stu-id="52cfb-173">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="52cfb-174">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="52cfb-174">For example:</span></span>
    
      - <span data-ttu-id="52cfb-175">Alle RTC-Datenbanken auf "D: \\ RTCDatabase"</span><span class="sxs-lookup"><span data-stu-id="52cfb-175">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="52cfb-176">Alle RTC-Protokolldateien auf "E: \\ RTCLogs"</span><span class="sxs-lookup"><span data-stu-id="52cfb-176">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="52cfb-177">Alle Anwendungsspeicher Datenbanken auf "F: \\ CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="52cfb-177">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="52cfb-178">Alle Anwendungsspeicher Protokolle auf "G: \\ CPSLogs"</span><span class="sxs-lookup"><span data-stu-id="52cfb-178">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="52cfb-179">Alle Antwortgruppen speichern Datenbanken auf "H: \\ RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="52cfb-179">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="52cfb-180">Alle Reaktionsgruppen Speicherprotokolle auf "I: \\ RGSLogs"</span><span class="sxs-lookup"><span data-stu-id="52cfb-180">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="52cfb-181">Alle Adressbuchspeicher Datenbanken auf "J: \\ ABSDatabases"</span><span class="sxs-lookup"><span data-stu-id="52cfb-181">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="52cfb-182">Alle Adressbuchspeicher-Protokolldateien in "K: \\ ABSLogs"</span><span class="sxs-lookup"><span data-stu-id="52cfb-182">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="52cfb-183">Alle Archivierungsspeicher Datenbanken auf "L: \\ ArchivingDatabases"</span><span class="sxs-lookup"><span data-stu-id="52cfb-183">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="52cfb-184">Alle Archivierungsspeicher Protokolle auf "M: \\ ArchivingLogs"</span><span class="sxs-lookup"><span data-stu-id="52cfb-184">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="52cfb-185">Alle Überwachungsspeicher Datenbanken auf "N: \\ MonitoringDatabases"</span><span class="sxs-lookup"><span data-stu-id="52cfb-185">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="52cfb-186">Alle Überwachungsspeicher-Protokolldateien auf "O: \\ MonitoringLogfiles"</span><span class="sxs-lookup"><span data-stu-id="52cfb-186">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
    <!-- end list -->
    
    ```powershell    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    <span data-ttu-id="52cfb-187">Mithilfe des-DatabasePathMap-Parameters können Sie eine beliebige Kombination aus logischem Laufwerksbuchstaben definieren, die die beste Lösung für Ihre Leistungs-und Platzierungs Anforderungen in SQL Server bietet.</span><span class="sxs-lookup"><span data-stu-id="52cfb-187">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="52cfb-188">Wenn Sie Ihre Datenbankdateien und Protokolldateien mithilfe der **DatabasePathMap** -Methode konfigurieren, müssen Sie bei Verwendung des Topologie-Generators eine geringfügige Änderung an Ihrem normalen Prozess vornehmen.</span><span class="sxs-lookup"><span data-stu-id="52cfb-188">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="52cfb-189">In der Regel definieren Sie Ihre Topologie-Auswahl, veröffentlichen die Topologie und wählen, wie die Datenbankauswahl bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="52cfb-189">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="52cfb-190">Wenn Sie **DatabasePathMap** verwendet haben, haben Sie bereits den dritten Teil des Topologie-Builder-Prozesses erfüllt.</span><span class="sxs-lookup"><span data-stu-id="52cfb-190">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="52cfb-191">Wenn Sie vor dem Ausführen des Topologie-Generators einen vollständig konfigurierten Datenbankserver besitzen, würden Sie weiterhin alle Serverrollen und-Optionen definieren, aber die Option zum Erstellen der Datenbanken deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="52cfb-191">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

<span data-ttu-id="52cfb-192"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="52cfb-192"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

