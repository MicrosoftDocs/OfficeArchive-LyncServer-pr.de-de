---
title: Migrieren des Adressbuchs
description: Migrieren des Adressbuchs
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad6acd8cca58aa4e09e21b9b45cbdddec527b5f8
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49438610"
---
# <a name="migrate-address-book"></a><span data-ttu-id="38b15-103">Migrieren des Adressbuchs</span><span class="sxs-lookup"><span data-stu-id="38b15-103">Migrate Address Book</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="38b15-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="38b15-104">

<span> </span></span></span>

<span data-ttu-id="38b15-105">_**Letztes Änderungsdatum des Themas:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="38b15-105">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="38b15-106">Im Allgemeinen wird das lync Server 2010-Adressbuch zusammen mit der restlichen Topologie migriert.</span><span class="sxs-lookup"><span data-stu-id="38b15-106">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="38b15-107">Möglicherweise müssen Sie jedoch einige Schritte nach der Migration durchführen, wenn Sie die folgenden Schritte in ihrer lync Server 2010-Umgebung angepasst haben:</span><span class="sxs-lookup"><span data-stu-id="38b15-107">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="38b15-108">Legen Sie die WMI-Eigenschaft **PartitionbyOU** auf Gruppen Adressbucheinträge nach Organisationseinheit (Organizational Unit, OU).</span><span class="sxs-lookup"><span data-stu-id="38b15-108">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="38b15-109">Benutzerdefinierte Adressbuch-Normalisierungsregeln.</span><span class="sxs-lookup"><span data-stu-id="38b15-109">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="38b15-110">Der Standardwert für den **UseNormalizationRules** -Parameter wurde auf "false" geändert.</span><span class="sxs-lookup"><span data-stu-id="38b15-110">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="38b15-111">**Gruppierte Adressbucheinträge**</span><span class="sxs-lookup"><span data-stu-id="38b15-111">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="38b15-112">Wenn Sie die **PartitionbyOU** -WMI-Eigenschaft auf "true" festlegen, um Adressbücher für jede OU zu erstellen, müssen Sie das Active Directory-Attribut " **Attribut msRTCSIP-Gruppierung** " für Benutzer und Kontakte festlegen, wenn Sie die Gruppierung von Adressbucheinträgen fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="38b15-112">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span></span> <span data-ttu-id="38b15-113">Möglicherweise möchten Sie Adressbucheinträge gruppieren, um den Umfang der Adressbuchsuche zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="38b15-113">You might want to group address book entries to limit the scope of Address Book searches.</span></span> <span data-ttu-id="38b15-114">Wenn Sie das **Attribut msRTCSIP-GROUPING-** Attribut verwenden möchten, schreiben Sie ein Skript zum Auffüllen des Attributs, und weisen Sie allen Benutzern, die Sie gruppieren möchten, denselben Wert zu.</span><span class="sxs-lookup"><span data-stu-id="38b15-114">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span></span> <span data-ttu-id="38b15-115">Weisen Sie beispielsweise allen Benutzern in einer OU einen einzelnen Wert zu.</span><span class="sxs-lookup"><span data-stu-id="38b15-115">For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="38b15-116">**Regeln für die Normalisierung des Adressbuchs**</span><span class="sxs-lookup"><span data-stu-id="38b15-116">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="38b15-117">Wenn Sie in ihrer lync Server 2010-Umgebung Adressbuch-Normalisierungsregeln angepasst haben, müssen Sie die angepassten Regeln in Ihren Pilot Pool migrieren.</span><span class="sxs-lookup"><span data-stu-id="38b15-117">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="38b15-118">Wenn Sie die Regeln für die Adressbuch Normalisierung nicht angepasst haben, müssen Sie für den Adressbuchdienst nichts migrieren.</span><span class="sxs-lookup"><span data-stu-id="38b15-118">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="38b15-119">Die standardmäßigen Normalisierungsregeln für lync Server 2013 entsprechen den Standardregeln für lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="38b15-119">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="38b15-120">Führen Sie die Schritte weiter unten in diesem Abschnitt aus, um angepasste Normalisierungsregeln zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="38b15-120">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="38b15-121">Wenn in Ihrer Organisation die Remoteanrufsteuerung verwendet wird und Sie die Regeln für die Adressbuch Normalisierung angepasst haben, müssen Sie das in diesem Thema beschriebene Verfahren ausführen, bevor Sie die Remoteanrufsteuerung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="38b15-121">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="38b15-122">Für das Verfahren ist die Mitgliedschaft in der RTCUniversalServerAdmins-Gruppe oder entsprechende Rechte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="38b15-122">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="38b15-123">**UseNormalizationRules auf "false" festgelegt**</span><span class="sxs-lookup"><span data-stu-id="38b15-123">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="38b15-124">Wenn Sie den Wert für **UseNormalizationRules** auf "false" festlegen, damit Benutzer Telefonnummern verwenden können, wie Sie in Active Directory-Domänendiensten definiert sind, ohne dass lync Server 2013 Normalisierungsregeln anwenden, müssen Sie die **UseNormalizationRules** -und **IgnoreGenericRules** -Parameter auf true festlegen.</span><span class="sxs-lookup"><span data-stu-id="38b15-124">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="38b15-125">Führen Sie die Schritte weiter unten in diesem Abschnitt aus, um diese Parameter auf "true" festzulegen.</span><span class="sxs-lookup"><span data-stu-id="38b15-125">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="38b15-126">So migrieren Sie Adressbuch angepasste Normalisierungsregeln</span><span class="sxs-lookup"><span data-stu-id="38b15-126">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="38b15-127">Suchen Sie die \_ Normalisierung der Firmentelefonnummer \_ \_ \_Rules.txt Datei im Stammverzeichnis des freigegebenen Adressbuch Ordners, und kopieren Sie Sie in den Stammordner des freigegebenen Adressbuch Ordners in Ihrem lync Server 2013-Pilot Pool.</span><span class="sxs-lookup"><span data-stu-id="38b15-127">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38b15-128">Das Beispiel für die Normalisierungsregeln für das Adressbuch wurde im Dateiverzeichnis der ABS-Webkomponente installiert.</span><span class="sxs-lookup"><span data-stu-id="38b15-128">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="38b15-129">Der Pfad ist <STRONG>$installedDriveLetter: \Programme\Microsoft lync Server 2013 \ Web Components\Address Adress Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="38b15-129">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="38b15-130">Diese Datei kann als &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; in das Stammverzeichnis des freigegebenen Ordners des Adressbuchs kopiert und umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="38b15-130">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="38b15-131">Beispielsweise ist das in <STRONG>$serverX</STRONG>freigegebene Adressbuch &nbsp; der Pfad ähnlich wie: <STRONG> \\ $serverX \LyncFileShare\2-Webservices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="38b15-131">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="38b15-132">Verwenden Sie einen Text-Editor wie Editor, um die Normalisierung der \_ Firmen \_ Telefonnummer \_ \_Rules.txt Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="38b15-132">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="38b15-133">Bestimmte Typen von Einträgen funktionieren in lync Server 2013 nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="38b15-133">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="38b15-134">Durchsuchen Sie die Datei nach den in diesem Schritt beschriebenen Arten von Einträgen, bearbeiten Sie Sie nach Bedarf, und speichern Sie die Änderungen im freigegebenen Ordner des Adressbuchs in Ihrem Pilot Pool.</span><span class="sxs-lookup"><span data-stu-id="38b15-134">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="38b15-135">Zeichenfolgen, die erforderliche leer-oder Interpunktionszeichen enthalten, führen zu Normalisierungsregeln, da diese Zeichen aus der Zeichenfolge entfernt werden, die für die Normalisierungsregeln eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="38b15-135">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="38b15-136">Wenn Zeichenfolgen vorhanden sind, die die erforderlichen Leerzeichen oder Interpunktionszeichen enthalten, müssen Sie die Zeichenfolgen ändern.</span><span class="sxs-lookup"><span data-stu-id="38b15-136">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="38b15-137">Die folgende Zeichenfolge würde beispielsweise dazu führen, dass die Normalisierungsregel fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="38b15-137">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="38b15-138">Die folgende Zeichenfolge würde nicht dazu führen, dass die Normalisierungsregel fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="38b15-138">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="38b15-139">So setzen Sie UseNormalizationRules und IgnoreGenericRules auf "true"</span><span class="sxs-lookup"><span data-stu-id="38b15-139">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="38b15-140">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="38b15-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="38b15-141">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="38b15-141">Do one of the following:</span></span>
    
      - <span data-ttu-id="38b15-142">Wenn Ihre Bereitstellung nur lync Server 2013 umfasst, führen Sie das folgende Cmdlet auf globaler Ebene aus, um die Werte für **UseNormalizationRules** und **IgnoreGenericRules** auf "true" zu ändern:</span><span class="sxs-lookup"><span data-stu-id="38b15-142">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="38b15-143">Wenn Ihre Bereitstellung eine Kombination aus lync Server 2013 und lync Server 2010 oder Office Communications Server 2007 R2 umfasst, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem lync Server 2013-Pool in der Topologie zu:</span><span class="sxs-lookup"><span data-stu-id="38b15-143">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="38b15-144">Warten Sie, bis die Replikation des zentralen Verwaltungsspeichers in allen Pools ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="38b15-144">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="38b15-145">Ändern Sie die Regeldatei für Telefon Normalisierungsregeln, "Unternehmens- \_ Telefon \_ Nummern \_ Normalisierung \_Rules.txt", damit Ihre Bereitstellung den Inhalt löscht.</span><span class="sxs-lookup"><span data-stu-id="38b15-145">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="38b15-146">Die Datei befindet sich auf der Dateifreigabe der einzelnen lync Server 2013-Pools.</span><span class="sxs-lookup"><span data-stu-id="38b15-146">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="38b15-147">Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit dem Namen "Firmen \_ Telefonnummer- \_ \_ normalisierungs \_Rules.txt".</span><span class="sxs-lookup"><span data-stu-id="38b15-147">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="38b15-148">Warten Sie einige Minuten, bis alle Front-End-Pools die neuen Dateien gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="38b15-148">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="38b15-149">Führen Sie das folgende Cmdlet für jeden lync Server 2013-Pool in Ihrer Bereitstellung aus:</span><span class="sxs-lookup"><span data-stu-id="38b15-149">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

<span data-ttu-id="38b15-150"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="38b15-150"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

