---
title: 'Lync Server 2013: Übersicht über die Vorbereitung der Active Directory-Domänendienste'
description: 'Lync Server 2013: Übersicht über die Vorbereitung der Active Directory-Domänendienste.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b22e11a73ad7a181e2eaf887b1b49b934d9db5
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49445162"
---
# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="62a6b-103">Übersicht über die Vorbereitung der Active Directory-Domänendienste in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62a6b-103">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="62a6b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="62a6b-104">

<span> </span></span></span>

<span data-ttu-id="62a6b-105">_**Letztes Änderungsdatum des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="62a6b-105">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="62a6b-106">Wenn Sie die Active Directory-Domänendienste für Ihre lync Server 2013-Bereitstellung vorbereiten möchten, müssen Sie drei Schritte in einer bestimmten Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="62a6b-106">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="62a6b-107">In der folgenden Tabelle werden die Schritte beschrieben, die zum Vorbereiten von AD DS für lync Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="62a6b-107">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="62a6b-108">Vorbereitungsschritte für Active Directory</span><span class="sxs-lookup"><span data-stu-id="62a6b-108">Active Directory Preparation Steps</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="62a6b-109">Schritt</span><span class="sxs-lookup"><span data-stu-id="62a6b-109">Step</span></span></th>
<th><span data-ttu-id="62a6b-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62a6b-110">Description</span></span></th>
<th><span data-ttu-id="62a6b-111">Wo ausführen</span><span class="sxs-lookup"><span data-stu-id="62a6b-111">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="62a6b-112"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Vorbereiten des Active Directory-Schemas in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="62a6b-112"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="62a6b-113">Erweitert das Active Directory-Schema durch Hinzufügen neuer Klassen und Attribute, die von lync Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62a6b-113">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="62a6b-114">Einmaliges ausführen für jede Gesamtstruktur in Ihrer Bereitstellung, in der lync Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="62a6b-114">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="62a6b-115">Für den Schemamaster in der Stammdomäne jeder Gesamtstruktur, in der lync Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="62a6b-115">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="62a6b-116">Sie müssen diesen Schritt nicht in der Stammdomäne ausführen, wenn Sie über Berechtigungen für den Schemamaster verfügen, aber Sie müssen Mitglied der Gruppe "Schemaadministratoren" in der Stammdomäne und ein Mitglied der Gruppe "Organisations-Admins" auf dem Schemamaster sein.</span><span class="sxs-lookup"><span data-stu-id="62a6b-116">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master.</span></span> <span data-ttu-id="62a6b-117">Führen Sie in einer Ressourcengesamtstruktur-Topologie diesen Schritt nur in der Ressourcengesamtstruktur und nicht in allen Benutzergesamtstrukturen aus.</span><span class="sxs-lookup"><span data-stu-id="62a6b-117">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="62a6b-118">Führen Sie in einer zentralen Gesamtstrukturtopologie diesen Schritt nur in der zentralen Gesamtstruktur und nicht in allen Benutzergesamtstrukturen aus.</span><span class="sxs-lookup"><span data-stu-id="62a6b-118">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="62a6b-119"><a href="lync-server-2013-preparing-the-forest.md">Vorbereiten der Gesamtstruktur für Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="62a6b-119"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="62a6b-120">Erstellt globale Einstellungen und universelle Gruppen, die von lync Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62a6b-120">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="62a6b-121">Einmaliges ausführen für jede Gesamtstruktur in Ihrer Bereitstellung, in der lync Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="62a6b-121">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="62a6b-122">In der Stammdomäne jeder Gesamtstruktur, in der lync Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="62a6b-122">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="62a6b-123">Damit Sie diesen Schritt ausführen können, müssen Sie Mitglied der Gruppe Organisations-Admins sein.</span><span class="sxs-lookup"><span data-stu-id="62a6b-123">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="62a6b-124">Führen Sie in einer Ressourcengesamtstruktur-Topologie diesen Schritt nur in der Ressourcengesamtstruktur und nicht in allen Benutzergesamtstrukturen aus.</span><span class="sxs-lookup"><span data-stu-id="62a6b-124">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="62a6b-125">Führen Sie in einer zentralen Gesamtstrukturtopologie diesen Schritt nur in der zentralen Gesamtstruktur und nicht in allen Benutzergesamtstrukturen aus.</span><span class="sxs-lookup"><span data-stu-id="62a6b-125">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="62a6b-126"><a href="lync-server-2013-preparing-domains.md">Vorbereiten von Domänen für Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="62a6b-126"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="62a6b-127">Fügt Berechtigungen für Objekte hinzu, die von Mitgliedern universeller Gruppen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="62a6b-127">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="62a6b-128">Einmal pro Benutzerdomäne oder Server Domäne ausführen.</span><span class="sxs-lookup"><span data-stu-id="62a6b-128">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="62a6b-129">Wenn Sie von lync Server 2010 zu lync Server 2013 migrieren, zeigt der Bereitstellungs-Assistent möglicherweise an, dass die Domänenvorbereitung bereits abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="62a6b-129">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="62a6b-130">Sie müssen die Domänenvorbereitung nicht erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="62a6b-130">You do not need to run domain preparation again.</span></span> <span data-ttu-id="62a6b-131">Es wurden keine Berechtigungen von lync Server 2010 zu lync Server 2013 geändert.</span><span class="sxs-lookup"><span data-stu-id="62a6b-131">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="62a6b-132">Auf einem Mitgliedsserver in jeder Domäne, in der lync Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="62a6b-132">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="62a6b-133">Damit Sie diesen Schritt ausführen können, müssen Sie Mitglied der Gruppe der Domänenadministratoren sein.</span><span class="sxs-lookup"><span data-stu-id="62a6b-133">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="62a6b-134">Lync Server 2013 speichert ähnlich wie lync Server 2010 einen Großteil der Konfigurationsinformationen im zentralen Verwaltungsspeicher statt in AD DS, wie dies bei Office Communications Server 2007 R2 der Fall war.</span><span class="sxs-lookup"><span data-stu-id="62a6b-134">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="62a6b-135">Die folgenden Informationen werden jedoch in AD DS gespeichert:</span><span class="sxs-lookup"><span data-stu-id="62a6b-135">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="62a6b-136">**Schema Erweiterungen**:</span><span class="sxs-lookup"><span data-stu-id="62a6b-136">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="62a6b-137">Benutzerobjekterweiterungen</span><span class="sxs-lookup"><span data-stu-id="62a6b-137">User object extensions</span></span>
    
      - <span data-ttu-id="62a6b-138">Erweiterungen für Office Communications Server 2007 R2-Klassen zum aufrecht erhalten der Abwärtskompatibilität</span><span class="sxs-lookup"><span data-stu-id="62a6b-138">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="62a6b-139">**Daten** (im erweiterten lync Server-Schema und in vorhandenen Schemaklassen gespeichert):</span><span class="sxs-lookup"><span data-stu-id="62a6b-139">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="62a6b-140">Benutzer SIP Uniform Resource Identifier (URI) und andere Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="62a6b-140">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="62a6b-141">Kontaktobjekte für Anwendungen wie Reaktionsgruppe und Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="62a6b-141">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="62a6b-142">Ein Zeiger auf den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="62a6b-142">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="62a6b-143">Kerberos-Authentifizierungs Konto (ein optionales Computerobjekt)</span><span class="sxs-lookup"><span data-stu-id="62a6b-143">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="62a6b-144">In lync Server 2013 delegieren Sie Setup und Verwaltung, indem Sie der universellen RTCUniversalServerAdmins-Gruppe Setup Berechtigungen erteilen, damit Mitglieder dieser Gruppe lync Server 2013 auf einem lokalen Server installieren und aktivieren können (nachdem der Server zur Topologie hinzugefügt, veröffentlicht und aktiviert wurde).</span><span class="sxs-lookup"><span data-stu-id="62a6b-144">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="62a6b-145">Die Delegierten Benutzer müssen lokale Administratoren auf dem Computer sein, auf dem Sie lync Server 2013 installieren und aktivieren, aber Sie müssen nicht Mitglieder der Gruppe der Domänenadministratoren sein.</span><span class="sxs-lookup"><span data-stu-id="62a6b-145">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="62a6b-146">Sie können auch Berechtigungen für Objekte in angegebenen Organisationseinheiten (Organizational Units, OUs) erteilen, damit Mitglieder der universellen Gruppen, die während der Gesamtstrukturvorbereitung erstellt wurden, auf diese Objekte zugreifen können, ohne Mitglieder der Gruppe der Domänenadministratoren zu sein.</span><span class="sxs-lookup"><span data-stu-id="62a6b-146">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="62a6b-147">Bei neuen Bereitstellungen von lync Server 2013 müssen die globalen Einstellungen im Container Konfiguration gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="62a6b-147">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="62a6b-148">Wenn Ihre Organisation ein Upgrade von einer früheren Version durchläuft und Sie weiterhin über globale Einstellungen im Systemcontainer verfügen, wird der Systemcontainer weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="62a6b-148">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="62a6b-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62a6b-149">See Also</span></span>


[<span data-ttu-id="62a6b-150">Vorbereiten des Active Directory-Schemas in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62a6b-150">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="62a6b-151">Active Directory-Schemaerweiterungen, -Klassen und -Attribute, die von Lync Server 2013 verwendet werden</span><span class="sxs-lookup"><span data-stu-id="62a6b-151">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="62a6b-152">Vorbereiten der Gesamtstruktur für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62a6b-152">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="62a6b-153">Vorbereiten von Domänen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62a6b-153">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

<span data-ttu-id="62a6b-154"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="62a6b-154"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

