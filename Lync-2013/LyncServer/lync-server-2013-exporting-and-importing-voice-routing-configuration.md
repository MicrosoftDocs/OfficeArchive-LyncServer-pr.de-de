---
title: 'Lync Server 2013: Exportieren und Importieren einer VoIP-Routingkonfiguration'
description: 'Lync Server 2013: Exportieren und Importieren der sprach Routingkonfiguration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a94a9c02672debae9f5b30e3a1a96856050d6ab1
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428356"
---
# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="748f1-103">Exportieren und Importieren einer VoIP-Routingkonfiguration in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="748f1-103">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="748f1-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="748f1-104">

<span> </span></span></span>

<span data-ttu-id="748f1-105">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="748f1-105">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="748f1-106">Wenn Sie Ihre sprach Routingkonfiguration speichern möchten, ohne Sie zu veröffentlichen, führen Sie die folgenden Schritte aus, um die Konfigurations Export-und-Importbefehle in lync Server Control Panel zu verwenden, um eine Momentaufnahme Ihrer VoIP-Routingkonfiguration zu speichern und abzurufen.</span><span class="sxs-lookup"><span data-stu-id="748f1-106">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="748f1-107">Wenn Sie eine sprach Routing-Konfigurationsdatei (. vcfg) importieren, aber Änderungen an der sprach Routingkonfiguration auf dem Server in der Zwischenzeit vorgenommen wurden, zeigen die Seiten in der Gruppe **VoIP-Routing** in der lync Server-Systemsteuerung an, dass nicht festgeschriebene Änderungen an der sprach Weiterleitung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="748f1-107">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="748f1-108">Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.</span><span class="sxs-lookup"><span data-stu-id="748f1-108">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="748f1-109">Wenn Sie Änderungen an den Einstellungen auf einer beliebigen Seite innerhalb der <STRONG>VoIP-Routing</STRONG> Gruppe vorgenommen haben, werden die Änderungen in der exportierten sprach Konfigurationsdatei (vcfg) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="748f1-109">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="748f1-110">So können Sie während mehrerer lync Server Control Panel-Sitzungen Änderungen an der sprach Routingkonfiguration vornehmen, bevor Sie die Änderungen veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="748f1-110">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="748f1-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="748f1-111">In This Section</span></span>

  - [<span data-ttu-id="748f1-112">Exportieren einer sprach Routen-Konfigurationsdatei in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="748f1-112">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="748f1-113">Importieren einer VoIP-Routenkonfigurationsdatei in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="748f1-113">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="748f1-114">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="748f1-114">Related Sections</span></span>

<span data-ttu-id="748f1-115"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="748f1-115"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

