---
title: 'Lync Server 2013: Abrufen eines Standorts'
description: 'Lync Server 2013: Abrufen eines Speicherorts.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25aa907b5373cadd9eb8ffe9e32a7531afa01deb
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49439495"
---
# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="f4bd5-103">Abrufen eines Standorts in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4bd5-103">Acquiring a location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="f4bd5-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="f4bd5-104">

<span> </span></span></span>

<span data-ttu-id="f4bd5-105">_**Letztes Änderungsdatum des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="f4bd5-105">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="f4bd5-106">In einer lync Server 2013 E9-1-1-Bereitstellung erwirbt jeder intern verbundene lync-oder lync Phone Edition-Client aktiv seinen eigenen Standort.</span><span class="sxs-lookup"><span data-stu-id="f4bd5-106">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="f4bd5-107">Nach der SIP-Registrierung liefert der Client alle Netzwerk Verbindungsinformationen, die er über sich selbst weiß, in einer standortanforderung an den standortinformationsdienst, bei dem es sich um einen Webdienst handelt, der von einer replizierten SQL Server-Datenbank gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="f4bd5-107">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="f4bd5-108">Jeder zentrale Website Pool verfügt über einen standortinformationsdienst, der die Netzwerkinformationen verwendet, um seine Datensätze nach einem übereinstimmenden Speicherort abzufragen.</span><span class="sxs-lookup"><span data-stu-id="f4bd5-108">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="f4bd5-109">Wenn eine Übereinstimmung vorliegt, gibt der standortinformationsdienst einen Speicherort an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="f4bd5-109">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="f4bd5-110">Wenn keine Übereinstimmung vorliegt, wird der Benutzer möglicherweise zur manuellen Eingabe eines Standorts aufgefordert (abhängig von den Einstellungen in der Standortrichtlinie).</span><span class="sxs-lookup"><span data-stu-id="f4bd5-110">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="f4bd5-111">Die Standortdaten werden in einem standardisierten IETF-XML-Format (Internet Engineering Task Force), das als PIDF-LO (Presence Information Data Format Location Object) bezeichnet wird, zurück an den Client übertragen.</span><span class="sxs-lookup"><span data-stu-id="f4bd5-111">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="f4bd5-112">Der lync Server-Client enthält die PIDF-Lo-Daten als Teil eines Notrufs, und diese Daten werden vom Dienstanbieter E9-1-1 verwendet, um den entsprechenden PSAP zu ermitteln und den Anruf an diesen PSAP zusammen mit dem korrekten ESQK weiterzuleiten, wodurch der PSAP-Verteiler den Standort des Anrufers abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="f4bd5-112">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="f4bd5-113">Das folgende Diagramm zeigt, wie ein lync Server-Client einen Standort erwirbt (mit Ausnahme der Standort Methode eines Drittanbieters für Mac-Adressen auf dem Client):</span><span class="sxs-lookup"><span data-stu-id="f4bd5-113">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="f4bd5-114">![So erwirbt der Client ein Standort Diagramm](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "So erwirbt der Client ein Standort Diagramm")</span><span class="sxs-lookup"><span data-stu-id="f4bd5-114">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="f4bd5-115">Damit ein Client den Standort erwirbt, sind folgende Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="f4bd5-115">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="f4bd5-116">Der Administrator füllt die Datenbank des Standort Informationsdiensts mit dem Netzwerk Wiremap (Tabellen, in denen verschiedene Arten von Netzwerkadressen den entsprechenden Notfall Speicherorten zugeordnet werden (ERLs)).</span><span class="sxs-lookup"><span data-stu-id="f4bd5-116">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="f4bd5-p102">Wenn Sie einen SIP-Trunk E9-1-1-Dienstanbieter nutzen, überprüft der Administrator die Adressteile der Notfallstandorte gegen eine MSAG-Datenbank (Master Street Address Guide), die durch den E9-1-1-Dienstanbieter bereitgestellt wird. Wenn Sie ein ELIN-Gateway (Emergency Location Identification Number) nutzen, stellt der Administrator sicher, dass der PSTN-Anbieter die ELINs in die ALI-Datenbank hochlädt (Automatic Location Identification).</span><span class="sxs-lookup"><span data-stu-id="f4bd5-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="f4bd5-119">Bei der Registrierung oder bei jeder Netzwerkänderung sendet ein intern verbundener Client eine Standortanfrage, die die gefundenen Netzwerkadressen des Clients enthält, an den standortinformationsdienst.</span><span class="sxs-lookup"><span data-stu-id="f4bd5-119">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="f4bd5-120">Der standortinformationsdienst fragt seine veröffentlichten Datensätze nach einem Speicherort ab, und gibt, wenn eine Übereinstimmung gefunden wird, das Erl an den Client im PIDF-Lo-Format zurück.</span><span class="sxs-lookup"><span data-stu-id="f4bd5-120">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

<span data-ttu-id="f4bd5-121"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="f4bd5-121"></div>

<span> </span>

</div>

</div>

</span></span></div>

