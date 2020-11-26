---
title: 'Lync Server 2013: Verwenden von Config.xml zum Ausführen von Installationsaufgaben'
description: 'Lync Server 2013: Verwenden von Config.xml, um Installationsaufgaben auszuführen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22fff14e21a120c3a0ee2cd6432fd1eba2bbee5f
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49438953"
---
# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a><span data-ttu-id="af25b-103">Verwenden von Config.xml zum Ausführen von Installationsaufgaben in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af25b-103">Using Config.xml to perform installation tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="af25b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="af25b-104">

<span> </span></span></span>

<span data-ttu-id="af25b-105">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="af25b-105">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="af25b-p101">Das Office-Anpassungstool (OAT) ist zwar das primäre Tool für die angepasste Installation, Administratoren können jedoch mit der Datei "Config.xml" zusätzliche, im OAT nicht verfügbare Installationsanweisungen angeben. Die folgenden Anpassungen können nur mithilfe der Datei Config.xml vorgenommen werden:</span><span class="sxs-lookup"><span data-stu-id="af25b-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

  - <span data-ttu-id="af25b-108">Angeben des Netzwerkinstallationspfads</span><span class="sxs-lookup"><span data-stu-id="af25b-108">Specify the path of the network installation point.</span></span>

  - <span data-ttu-id="af25b-109">Auswählen der zu installierenden Produkte</span><span class="sxs-lookup"><span data-stu-id="af25b-109">Select the products to install.</span></span>

  - <span data-ttu-id="af25b-110">Konfigurieren der Protokollierung und des Speicherorts der Setupanpassungsdatei und Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="af25b-110">Configure logging and the location of the Setup customization file and software updates.</span></span>

  - <span data-ttu-id="af25b-111">Angeben von Installationsoptionen, z. B. Benutzername</span><span class="sxs-lookup"><span data-stu-id="af25b-111">Specify installation options, such as user name.</span></span>

  - <span data-ttu-id="af25b-112">Kopieren der lokalen Installationsquelle (Local Installation Source, LIS) auf den Benutzercomputer ohne Installation von Office</span><span class="sxs-lookup"><span data-stu-id="af25b-112">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

  - <span data-ttu-id="af25b-113">Hinzufügen oder Entfernen von Sprachen in der Installation</span><span class="sxs-lookup"><span data-stu-id="af25b-113">Add or remove languages from the installation.</span></span>

<span data-ttu-id="af25b-114">Wir empfehlen, dass Sie die Config.xml-Datei verwenden, um die unbeaufsichtigte lync 2013-Installation zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="af25b-114">We recommend that you use the Config.xml file to configure Lync 2013 silent installation.</span></span>

<span data-ttu-id="af25b-115">Standardmäßig wird die Config.xml-Datei, die im Kernproduktordner gespeichert ist (beispielsweise \\ Product. WW) weist Setup an, dieses Produkt zu installieren.</span><span class="sxs-lookup"><span data-stu-id="af25b-115">By default, the Config.xml file that is stored in the core product folder (for example, \\product.WW) directs Setup to install that product.</span></span> <span data-ttu-id="af25b-116">Beispielsweise wird in der Config.xml-Datei im folgenden Ordner lync 2013 installiert:</span><span class="sxs-lookup"><span data-stu-id="af25b-116">For example, the Config.xml file in the following folder installs Lync 2013:</span></span>

  - <span data-ttu-id="af25b-117">\\\\Server \\ Freigabe \\ Lync15 \\ lync. WW \\Config.xml</span><span class="sxs-lookup"><span data-stu-id="af25b-117">\\\\server\\share\\Lync15\\Lync.WW \\Config.xml</span></span>

<span data-ttu-id="af25b-118">Die Config.xml Elemente, die am häufigsten für die lync 2013-Installation verwendet werden, sind in der folgenden Tabelle aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="af25b-118">The Config.xml elements most commonly used for Lync 2013 installation are listed in the following table.</span></span>

### <a name="configxml-elements"></a><span data-ttu-id="af25b-119">Config.xml-Elemente</span><span class="sxs-lookup"><span data-stu-id="af25b-119">Config.xml elements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af25b-120">Element</span><span class="sxs-lookup"><span data-stu-id="af25b-120">Element</span></span></th>
<th><span data-ttu-id="af25b-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af25b-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af25b-122">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="af25b-122">Configuration</span></span></p></td>
<td><p><span data-ttu-id="af25b-123">Element der obersten Ebene (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="af25b-123">Top-level element (required).</span></span> <span data-ttu-id="af25b-124">Enthält das Product-Attribut, beispielsweise: product = lync</span><span class="sxs-lookup"><span data-stu-id="af25b-124">Contains the Product attribute, for example: Product=Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af25b-125">OptionState</span><span class="sxs-lookup"><span data-stu-id="af25b-125">OptionState</span></span></p></td>
<td><p><span data-ttu-id="af25b-126">Gibt an, wie bestimmte Produktfeatures während der Installation behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="af25b-126">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="af25b-127">Verwenden Sie die folgenden Attribute, um die Installation von Business Connectivity Services zu verhindern, die freigegebene Komponenten umfasst, die Outlook 2010 stören:</span><span class="sxs-lookup"><span data-stu-id="af25b-127">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2010:</span></span></p>
<ul>
<li><p><span data-ttu-id="af25b-128">ID = &quot; LOBiMain&quot;</span><span class="sxs-lookup"><span data-stu-id="af25b-128">Id=&quot;LOBiMain&quot;</span></span></p></li>
<li><p><span data-ttu-id="af25b-129">Zustand = &quot; abwesend&quot;</span><span class="sxs-lookup"><span data-stu-id="af25b-129">State=&quot;Absent&quot;</span></span></p></li>
<li><p><span data-ttu-id="af25b-130">Kinder = &quot; Kraft&quot;</span><span class="sxs-lookup"><span data-stu-id="af25b-130">Children=&quot;Force&quot;</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af25b-131">Anzeige</span><span class="sxs-lookup"><span data-stu-id="af25b-131">Display</span></span></p></td>
<td><p><span data-ttu-id="af25b-p105">Die Ebene der Benutzeroberfläche, die dem Benutzer angezeigt wird. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="af25b-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="af25b-134">CompletionNotice = &quot; Ja &quot;  |  &quot; Nein &quot; (Standard)</span><span class="sxs-lookup"><span data-stu-id="af25b-134">CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
<li><p><span data-ttu-id="af25b-135">AcceptEULA = &quot; Ja &quot;  |  &quot; Nein &quot; (Standard)</span><span class="sxs-lookup"><span data-stu-id="af25b-135">AcceptEula=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af25b-136">Protokollierung</span><span class="sxs-lookup"><span data-stu-id="af25b-136">Logging</span></span></p></td>
<td><p><span data-ttu-id="af25b-p106">Optionen für den vom Setup ausgeführten Protokollierungstyp. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="af25b-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="af25b-139">Type = &quot; Off &quot;  |  &quot; Standard &quot; (Standard) | &quot; Ausführliche&quot;</span><span class="sxs-lookup"><span data-stu-id="af25b-139">Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</span></span></p></li>
<li><p><span data-ttu-id="af25b-140">Template=”filename.txt” (Name der Protokolldatei)</span><span class="sxs-lookup"><span data-stu-id="af25b-140">Template=”filename.txt” (the name of the log file)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af25b-141">Einstellung</span><span class="sxs-lookup"><span data-stu-id="af25b-141">Setting</span></span></p></td>
<td><p><span data-ttu-id="af25b-p107">Gibt Werte für Windows Installer-Eigenschaften an. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="af25b-p107">Specifies values for Windows Installer properties. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="af25b-144">Festlegen von ID = &quot; Name &quot; (der Name der Windows Installer-Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="af25b-144">Setting Id=&quot;name&quot; (the name of the Windows Installer property)</span></span></p></li>
<li><p><span data-ttu-id="af25b-145">Value = &quot; Wert &quot; (der Wert, der der Eigenschaft zugewiesen werden soll)</span><span class="sxs-lookup"><span data-stu-id="af25b-145">Value=&quot;value&quot; (the value to assign to the property)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af25b-146">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="af25b-146">DistributionPoint</span></span></p></td>
<td><p><span data-ttu-id="af25b-p108">Der vollqualifizierte Pfad des Netzwerkinstallationspfads, von dem die Installation ausgeführt werden soll. Enthält das Standortattribut:</span><span class="sxs-lookup"><span data-stu-id="af25b-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="af25b-149">Location=”path”</span><span class="sxs-lookup"><span data-stu-id="af25b-149">Location=”path”</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="af25b-150">Das folgende Beispiel zeigt eine Config.xml-Datei für eine typische unbeaufsichtigte Installation von lync 2013.</span><span class="sxs-lookup"><span data-stu-id="af25b-150">The following example shows a Config.xml file for a typical silent installation of Lync 2013.</span></span>

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

<span data-ttu-id="af25b-151">Detaillierte Informationen zur Verwendung der Config.xml-Datei zum Ausführen von Office-Installations-und-Wartungsaufgaben finden Sie unter <https://go.microsoft.com/fwlink/p/?linkid=267514> .</span><span class="sxs-lookup"><span data-stu-id="af25b-151">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at <https://go.microsoft.com/fwlink/p/?linkid=267514>.</span></span>

<div>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="af25b-152">So passen Sie die Datei "Config.xml" an</span><span class="sxs-lookup"><span data-stu-id="af25b-152">To customize the Config.xml file</span></span>

1.  <span data-ttu-id="af25b-153">Öffnen Sie die Datei "Config.xml" in einem Text-Editor wie Editor.</span><span class="sxs-lookup"><span data-stu-id="af25b-153">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2.  <span data-ttu-id="af25b-154">Suchen Sie die Zeilen, die die zu ändernden Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="af25b-154">Locate the lines that contain the elements you want to change.</span></span>

3.  <span data-ttu-id="af25b-155">Ändern Sie den Elementeintrag mit den gewünschten Optionen für eine automatische Installation.</span><span class="sxs-lookup"><span data-stu-id="af25b-155">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="af25b-156">Stellen Sie sicher, dass Sie die Kommentartrennzeichen "" entfernen \<\!--" and "--\> .</span><span class="sxs-lookup"><span data-stu-id="af25b-156">Make sure that you remove the comment delimiters, "\<\!--" and "--\>".</span></span> <span data-ttu-id="af25b-157">Verwenden Sie z. B. die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="af25b-157">For example, use the following syntax:</span></span>
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  <span data-ttu-id="af25b-158">Speichern Sie die Datei Config.xml.</span><span class="sxs-lookup"><span data-stu-id="af25b-158">Save the Config.xml file.</span></span>

<span data-ttu-id="af25b-159"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="af25b-159"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

