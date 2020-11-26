---
title: 'Lync Server 2013: lync Server-Cmdlets nach Kategorie'
description: 'Lync Server 2013: lync Server-Cmdlets nach Kategorie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df562bd11d54c9ecda4fe3d6172ed1d8bd2627d6
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49426277"
---
# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="e8f83-103">Lync Server 2013-Cmdlets nach Kategorie</span><span class="sxs-lookup"><span data-stu-id="e8f83-103">Lync Server 2013 cmdlets by category</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="e8f83-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="e8f83-104">

<span> </span></span></span>

<span data-ttu-id="e8f83-105">_**Letztes Änderungsdatum des Themas:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="e8f83-105">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="e8f83-106">Microsoft lync Server 2013 wird mit fast 550-Cmdlets ausgeliefert, die speziell dazu entwickelt wurden, Administratoren die Verwaltung von lync Server über die Befehlszeile zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e8f83-106">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="e8f83-107">Sie greifen in der lync Server-Verwaltungsshell auf die Cmdlets zu.</span><span class="sxs-lookup"><span data-stu-id="e8f83-107">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="e8f83-108">Sie können die Hilfe zu einem Cmdlet direkt über die Befehlszeile abrufen, indem Sie einen Befehl wie den folgenden eingeben:</span><span class="sxs-lookup"><span data-stu-id="e8f83-108">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="e8f83-109">Der vorhergehende Befehl ruft alle für das Cmdlet **New-CsVoicePolicy** verfügbare Hilfe ab.</span><span class="sxs-lookup"><span data-stu-id="e8f83-109">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="e8f83-110">Ersetzen Sie den Verweis auf **New-CsVoicePolicy** durch den Namen des Cmdlets, für das Sie Hilfe abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="e8f83-110">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="e8f83-111">Wenn Sie eine vollständige Liste der für die Verwaltung von Microsoft lync Server 2013 verfügbaren Cmdlets abrufen möchten, geben Sie Folgendes an der Eingabeaufforderung der lync Server-Verwaltungsshell ein:</span><span class="sxs-lookup"><span data-stu-id="e8f83-111">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="e8f83-112">Wenn Sie sich nicht sicher sind, welche Cmdlets Sie benötigen, haben wir auch eine kategorisierte Liste mit Cmdlets und deren Hilfethemen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e8f83-112">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics.</span></span> <span data-ttu-id="e8f83-113">Sie werden feststellen, dass einige Cmdlets in mehr als einer Kategorie angezeigt werden, was beabsichtigt war, da Sie für mehrere Bereiche des Produkts gelten.</span><span class="sxs-lookup"><span data-stu-id="e8f83-113">You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product.</span></span> <span data-ttu-id="e8f83-114">Es folgt eine Liste der Kategorien:</span><span class="sxs-lookup"><span data-stu-id="e8f83-114">The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e8f83-115">Die Skype for Business-Cmdlet-Referenz wurde in docs.Microsoft.com verschoben.</span><span class="sxs-lookup"><span data-stu-id="e8f83-115">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="e8f83-116">Wenn Sie auf die Links unten klicken, gelangen Sie zur neuen docs.Microsoft.com-Seite.</span><span class="sxs-lookup"><span data-stu-id="e8f83-116">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="e8f83-117">Der Inhalt wird nun über GitHub freigegeben und steht für Community-Beiträge zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e8f83-117">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="e8f83-118">Möchten Sie einen Beitrag leisten?</span><span class="sxs-lookup"><span data-stu-id="e8f83-118">Interested in contributing?</span></span> <span data-ttu-id="e8f83-119">Schauen Sie sich die Readme-Datei im Repo hier an: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="e8f83-119">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e8f83-120">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e8f83-120">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8f83-121"><a href="lync-server-2013-user-management-cmdlets.md">Cmdlets für die Benutzerverwaltung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-121"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8f83-122"><a href="lync-server-2013-voice-application-cmdlets.md">Cmdlets für die Sprachanwendung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-122"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f83-123"><a href="lync-server-2013-client-management-cmdlets.md">Cmdlets für die Client Verwaltung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-123"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8f83-124"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Erweiterte Enterprise-VoIP-Cmdlets in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-124"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f83-125"><a href="lync-server-2013-im-and-presence-cmdlets.md">Cmdlets für Chats und Anwesenheitsinformationen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-125"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8f83-126"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Cmdlets für PSTN-Konnektivität in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-126"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f83-127"><a href="lync-server-2013-conferencing-cmdlets.md">Konferenz-Cmdlets in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-127"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8f83-128"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Cmdlets für Telefone und Geräte in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-128"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f83-129"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Cmdlets für Infrastruktur und Bereitstellung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-129"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8f83-130"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Cmdlets für Migration und Koexistenz in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-130"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f83-131"><a href="lync-server-2013-security-cmdlets.md">Sicherheits-Cmdlets in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-131"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8f83-132"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Konfigurations-Cmdlets der lync Server-Verwaltungsshell in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-132"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f83-133"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Cmdlets für Server Rollen und Dienste in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-133"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8f83-134"><a href="lync-server-2013-mobility-cmdlets.md">Mobilitäts-Cmdlets in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-134"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f83-135"><a href="lync-server-2013-application-management-cmdlets.md">Cmdlets für die Anwendungsverwaltung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-135"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8f83-136"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Server-Cmdlets für beständigen Chat in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-136"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f83-137"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Cmdlets für Föderations-und externen Zugriff in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-137"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8f83-138"><a href="lync-server-2013-centralized-logging-cmdlets.md">Cmdlets für die zentralisierte Protokollierung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-138"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f83-139"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise-VoIP-Cmdlets in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8f83-139"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e8f83-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8f83-140">See Also</span></span>


[<span data-ttu-id="e8f83-141">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="e8f83-141">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

<span data-ttu-id="e8f83-142"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="e8f83-142"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

