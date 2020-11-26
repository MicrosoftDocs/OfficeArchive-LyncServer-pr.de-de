---
title: 'Lync Server 2013: IIS-Konfiguration'
description: 'Lync Server 2013: IIS-Konfiguration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901aca7bf5ff8824b54e93754569a6ef5defc10e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427432"
---
# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="93bb2-103">IIS-Konfiguration in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93bb2-103">IIS configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="93bb2-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="93bb2-104">

<span> </span></span></span>

<span data-ttu-id="93bb2-105">_**Letztes Änderungsdatum des Themas:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="93bb2-105">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="93bb2-106">Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie am Server minimal als lokaler Administrator und Domänenbenutzer angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="93bb2-106">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="93bb2-107">Bevor Sie den Front-End-Server für lync Server 2013, Standard Edition oder den ersten Front-End-Server in einem Pool konfigurieren und installieren, installieren und konfigurieren Sie die Server Rolle und die Webdienste für Internet Informationsdienste (IIS).</span><span class="sxs-lookup"><span data-stu-id="93bb2-107">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="93bb2-108">Wenn Ihre Organisation erfordert, dass Sie IIS und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk finden, können Sie den Installationspfad für die lync Server 2013-Dateien im Dialogfeld "Setup" ändern, wenn Sie zunächst die lync Server 2013-Verwaltungstools installieren.</span><span class="sxs-lookup"><span data-stu-id="93bb2-108">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="93bb2-109">Sie installieren die Verwaltungstools, bevor Sie IIS installieren.</span><span class="sxs-lookup"><span data-stu-id="93bb2-109">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="93bb2-110">Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen lync Server 2013-Dateien auf diesem Laufwerk bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="93bb2-110">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="93bb2-111">Informationen zu dtails finden Sie unter <A href="lync-server-2013-install-lync-server-administrative-tools.md">Installieren von lync Server 2013-Verwaltungstools</A>.</span><span class="sxs-lookup"><span data-stu-id="93bb2-111">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="93bb2-112">Ausführliche Informationen dazu, wie Sie die INETPUB, die vom Windows Server-Manager bereitgestellt werden, bei der Installation von IIS verschieben, finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .</span><span class="sxs-lookup"><span data-stu-id="93bb2-112">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="93bb2-113">In der folgenden Tabelle sind die erforderlichen IIS 7,5-Rollendienste angegeben.</span><span class="sxs-lookup"><span data-stu-id="93bb2-113">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="93bb2-114">IIS 7,5-Rollendienste</span><span class="sxs-lookup"><span data-stu-id="93bb2-114">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93bb2-115">Rollen Überschrift</span><span class="sxs-lookup"><span data-stu-id="93bb2-115">Role Heading</span></span></th>
<th><span data-ttu-id="93bb2-116">Rollendienst</span><span class="sxs-lookup"><span data-stu-id="93bb2-116">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-117">Allgemeine HTTP-Features installiert</span><span class="sxs-lookup"><span data-stu-id="93bb2-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="93bb2-118">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="93bb2-118">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-119">Allgemeine HTTP-Features installiert</span><span class="sxs-lookup"><span data-stu-id="93bb2-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="93bb2-120">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="93bb2-120">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-121">Allgemeine HTTP-Features installiert</span><span class="sxs-lookup"><span data-stu-id="93bb2-121">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="93bb2-122">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="93bb2-122">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-123">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="93bb2-123">Application development</span></span></p></td>
<td><p><span data-ttu-id="93bb2-124">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="93bb2-124">ASP.NET</span></span></p>
<p><span data-ttu-id="93bb2-125">Windows Server 2012 erfordert auch ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="93bb2-125">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-126">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="93bb2-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="93bb2-127">.NET-Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="93bb2-127">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-128">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="93bb2-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="93bb2-129">ISAPI-Erweiterungen (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="93bb2-129">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-130">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="93bb2-130">Application development</span></span></p></td>
<td><p><span data-ttu-id="93bb2-131">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="93bb2-131">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-132">Status und Diagnose</span><span class="sxs-lookup"><span data-stu-id="93bb2-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="93bb2-133">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="93bb2-133">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-134">Status und Diagnose</span><span class="sxs-lookup"><span data-stu-id="93bb2-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="93bb2-135">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="93bb2-135">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-136">Status und Diagnose</span><span class="sxs-lookup"><span data-stu-id="93bb2-136">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="93bb2-137">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="93bb2-137">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-138">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="93bb2-138">Security</span></span></p></td>
<td><p><span data-ttu-id="93bb2-139">Anonyme Authentifizierung (standardmäßig installiert und aktiviert)</span><span class="sxs-lookup"><span data-stu-id="93bb2-139">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-140">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="93bb2-140">Security</span></span></p></td>
<td><p><span data-ttu-id="93bb2-141">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="93bb2-141">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-142">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="93bb2-142">Security</span></span></p></td>
<td><p><span data-ttu-id="93bb2-143">Authentifizierung der Client Zertifikatzuordnung</span><span class="sxs-lookup"><span data-stu-id="93bb2-143">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-144">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="93bb2-144">Security</span></span></p></td>
<td><p><span data-ttu-id="93bb2-145">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="93bb2-145">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-146">Leistung</span><span class="sxs-lookup"><span data-stu-id="93bb2-146">Performance</span></span></p></td>
<td><p><span data-ttu-id="93bb2-147">Komprimierung statischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="93bb2-147">Static content compression</span></span></p>
<p><span data-ttu-id="93bb2-148">Dynamische Inhaltskomprimierung</span><span class="sxs-lookup"><span data-stu-id="93bb2-148">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-149">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="93bb2-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="93bb2-150">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="93bb2-150">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-151">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="93bb2-151">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="93bb2-152">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="93bb2-152">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93bb2-153">Auf dem Windows Server 2008 R2 SP1 x64-Betriebssystem können Sie Windows PowerShell 2,0 verwenden.</span><span class="sxs-lookup"><span data-stu-id="93bb2-153">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="93bb2-154">Sie müssen zuerst das Server-Modul importieren und dann die IIS 7,5-Rollen-und-Rollendienste installieren.</span><span class="sxs-lookup"><span data-stu-id="93bb2-154">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="93bb2-155">Die anonyme Authentifizierung wird standardmäßig mit der IIS-Serverrolle installiert.</span><span class="sxs-lookup"><span data-stu-id="93bb2-155">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="93bb2-156">Sie können die anonyme Authentifizierung nach der Installation von IIS verwalten.</span><span class="sxs-lookup"><span data-stu-id="93bb2-156">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="93bb2-157">Ausführliche Informationen finden Sie unter "Aktivieren der anonymen Authentifizierung (IIS 7.0)" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> .</span><span class="sxs-lookup"><span data-stu-id="93bb2-157">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="93bb2-158">In der folgenden Tabelle sind die erforderlichen IIS 8,0-und IIS 8,5-Rollendienste für Windows Server 2012 und Windows Server 2012 R2 angegeben.</span><span class="sxs-lookup"><span data-stu-id="93bb2-158">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="93bb2-159">Für Windows Server 2012 und Windows Server 2012 R2 wurde das Add-WindowsFeature-Cmdlet durch das Install-WindowsFeature-Cmdlet ersetzt.</span><span class="sxs-lookup"><span data-stu-id="93bb2-159">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="93bb2-160">Ausführliche Informationen finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">install-Cmdlets</A>.</span><span class="sxs-lookup"><span data-stu-id="93bb2-160">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="93bb2-161">IIS 8,0 und IIS 8,5-Rollendienste</span><span class="sxs-lookup"><span data-stu-id="93bb2-161">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93bb2-162">Rollen Überschrift</span><span class="sxs-lookup"><span data-stu-id="93bb2-162">Role Heading</span></span></th>
<th><span data-ttu-id="93bb2-163">Rollendienst</span><span class="sxs-lookup"><span data-stu-id="93bb2-163">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-164">Webserver (IIS)</span><span class="sxs-lookup"><span data-stu-id="93bb2-164">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="93bb2-165">Web Server</span><span class="sxs-lookup"><span data-stu-id="93bb2-165">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-166">Allgemeine HTTP-Funktionen</span><span class="sxs-lookup"><span data-stu-id="93bb2-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="93bb2-167">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="93bb2-167">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-168">Allgemeine HTTP-Funktionen</span><span class="sxs-lookup"><span data-stu-id="93bb2-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="93bb2-169">Verzeichnissuche</span><span class="sxs-lookup"><span data-stu-id="93bb2-169">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-170">Allgemeine HTTP-Funktionen</span><span class="sxs-lookup"><span data-stu-id="93bb2-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="93bb2-171">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="93bb2-171">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-172">Allgemeine HTTP-Funktionen</span><span class="sxs-lookup"><span data-stu-id="93bb2-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="93bb2-173">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="93bb2-173">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-174">Allgemeine HTTP-Funktionen</span><span class="sxs-lookup"><span data-stu-id="93bb2-174">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="93bb2-175">HTTP-Umleitung</span><span class="sxs-lookup"><span data-stu-id="93bb2-175">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-176">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="93bb2-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="93bb2-177">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="93bb2-177">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-178">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="93bb2-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="93bb2-179">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="93bb2-179">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-180">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="93bb2-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="93bb2-181">Anforderungs Monitor</span><span class="sxs-lookup"><span data-stu-id="93bb2-181">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-182">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="93bb2-182">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="93bb2-183">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="93bb2-183">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-184">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="93bb2-184">Security</span></span></p></td>
<td><p><span data-ttu-id="93bb2-185">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="93bb2-185">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-186">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="93bb2-186">Security</span></span></p></td>
<td><p><span data-ttu-id="93bb2-187">Standardauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="93bb2-187">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-188">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="93bb2-188">Security</span></span></p></td>
<td><p><span data-ttu-id="93bb2-189">Clientzertifikatzuordnungs-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="93bb2-189">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-190">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="93bb2-190">Security</span></span></p></td>
<td><p><span data-ttu-id="93bb2-191">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="93bb2-191">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-192">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="93bb2-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="93bb2-193">.NET-Erweiterbarkeit 3,5</span><span class="sxs-lookup"><span data-stu-id="93bb2-193">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-194">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="93bb2-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="93bb2-195">.NET-Erweiterbarkeit 4,5</span><span class="sxs-lookup"><span data-stu-id="93bb2-195">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-196">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="93bb2-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="93bb2-197">ASP.NET 3,5</span><span class="sxs-lookup"><span data-stu-id="93bb2-197">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-198">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="93bb2-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="93bb2-199">ASP.NET 4,5</span><span class="sxs-lookup"><span data-stu-id="93bb2-199">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-200">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="93bb2-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="93bb2-201">ISAPI-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="93bb2-201">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-202">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="93bb2-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="93bb2-203">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="93bb2-203">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-204">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="93bb2-204">Application Development</span></span></p></td>
<td><p><span data-ttu-id="93bb2-205">Server seitige includes</span><span class="sxs-lookup"><span data-stu-id="93bb2-205">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-206">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="93bb2-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="93bb2-207">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="93bb2-207">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-208">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="93bb2-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="93bb2-209">IIS 6-Metabase-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="93bb2-209">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-210">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="93bb2-210">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="93bb2-211">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="93bb2-211">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-212">.NET 3,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="93bb2-212">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="93bb2-213">.NET 3,5-Framework</span><span class="sxs-lookup"><span data-stu-id="93bb2-213">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-214">.NET 4,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="93bb2-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="93bb2-215">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="93bb2-215">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-216">.NET 4,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="93bb2-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="93bb2-217">ASP.NET 4,5</span><span class="sxs-lookup"><span data-stu-id="93bb2-217">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-218">.NET 4,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="93bb2-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="93bb2-219">HTTP-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="93bb2-219">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-220">.NET 4,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="93bb2-220">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="93bb2-221">TCP-Port Freigabe</span><span class="sxs-lookup"><span data-stu-id="93bb2-221">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-222">Intelligenter Hintergrundübertragungsdienst</span><span class="sxs-lookup"><span data-stu-id="93bb2-222">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="93bb2-223">IIS-Server Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="93bb2-223">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-224">Freihand-und Handschriftdienste</span><span class="sxs-lookup"><span data-stu-id="93bb2-224">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="93bb2-225">Freihand-und Handschriftdienste</span><span class="sxs-lookup"><span data-stu-id="93bb2-225">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-226">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="93bb2-226">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="93bb2-227">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="93bb2-227">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-228">Benutzeroberflächen und Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="93bb2-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="93bb2-229">Grafische Verwaltungs Tools und-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="93bb2-229">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-230">Benutzeroberflächen und Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="93bb2-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="93bb2-231">Desktop Experience</span><span class="sxs-lookup"><span data-stu-id="93bb2-231">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-232">Benutzeroberflächen und Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="93bb2-232">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="93bb2-233">Grafische Server-Shell</span><span class="sxs-lookup"><span data-stu-id="93bb2-233">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-234">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="93bb2-234">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="93bb2-235">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="93bb2-235">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93bb2-236">Windows-Prozessaktivierungsdienst</span><span class="sxs-lookup"><span data-stu-id="93bb2-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="93bb2-237">Prozessmodell</span><span class="sxs-lookup"><span data-stu-id="93bb2-237">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93bb2-238">Windows-Prozessaktivierungsdienst</span><span class="sxs-lookup"><span data-stu-id="93bb2-238">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="93bb2-239">Konfigurations-APIs</span><span class="sxs-lookup"><span data-stu-id="93bb2-239">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93bb2-240">In Windows Server 2012 und Windows Server 2012 R2 können Sie Windows PowerShell 3,0 verwenden, um die IIS-Anforderungen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="93bb2-240">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="93bb2-241">Geben Sie im Server-Modul von Windows PowerShell 3,0 Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="93bb2-241">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="93bb2-242">Neu in Windows Server 2012 ist der-source-Parameter, der definiert, wo die Windows Server 2012-Quellmedien gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="93bb2-242">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="93bb2-243">Die Medien können als DVD-Laufwerk (beispielsweise D:\Sources\Sxs) oder als Netzwerkfreigabe definiert werden, in der die Mediendateien kopiert wurden (beispielsweise \\ fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="93bb2-243">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="93bb2-244">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93bb2-244">See Also</span></span>


[<span data-ttu-id="93bb2-245">IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93bb2-245">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

<span data-ttu-id="93bb2-246"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="93bb2-246"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

