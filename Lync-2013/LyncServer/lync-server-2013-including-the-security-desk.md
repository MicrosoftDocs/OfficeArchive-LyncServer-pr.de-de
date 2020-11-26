---
title: 'Lync Server 2013: einschließlich des Security Desks'
description: 'Lync Server 2013: einschließlich des Security Desks.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23a5b01dff5e3db8293944033f1f3b675bbc4d37
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427306"
---
# <a name="including-the-security-desk-in-lync-server-2013"></a><span data-ttu-id="afebd-103">Einschließen des Security Desks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afebd-103">Including the security desk in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="afebd-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="afebd-104">

<span> </span></span></span>

<span data-ttu-id="afebd-105">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="afebd-105">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="afebd-p101">In Ihrem Unternehmen soll möglicherweise das Sicherheitsdesk in die Konfiguration für Notrufe eingebunden werden. Um entscheiden zu können, wie das Sicherheitsdesk in Ihre E9-1-1-Bereitstellung integriert werden kann, müssen Sie die folgenden Fragen beantworten.</span><span class="sxs-lookup"><span data-stu-id="afebd-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>

  - <span data-ttu-id="afebd-108">**Soll das Sicherheitsdesk benachrichtigt werden, wenn ein Notruf abgesetzt wird?**</span><span class="sxs-lookup"><span data-stu-id="afebd-108">**Do you want the security desk to be notified when there is an emergency call?**</span></span>  
    <span data-ttu-id="afebd-109">Sie können die ortungsrichtlinie so konfigurieren, dass lync Server Sofortnachrichten (im) an die lync-SIP-Adressen eines oder mehrerer Sicherheitspersonal sendet.</span><span class="sxs-lookup"><span data-stu-id="afebd-109">You can configure the location policy so that Lync Server sends instant messaging (IM) alerts to the Lync SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="afebd-110">Diese Benachrichtigungen enthalten den Namen, die Nummer und den Standort der Person, die den Notruf durchführt, und erleichtert das Sicherheitspersonal bei der Unterstützung der Notfallsituation.</span><span class="sxs-lookup"><span data-stu-id="afebd-110">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>

<!-- end list -->

  - <span data-ttu-id="afebd-111">**Möchten Sie für Notrufe eine Konferenzschaltung mit dem Sicherheitsdesk einrichten?**</span><span class="sxs-lookup"><span data-stu-id="afebd-111">**Do you want to conference the security desk in on each emergency call?**</span></span>  
    <span data-ttu-id="afebd-p103">Sofern dies vom Anbieter für die Notrufunterstützung unterstützt wird, können Sie in der Ortungsrichtlinie eine Rückrufnummer für Notrufe einschließen. Diese Nummer wird vom Anbieter verwendet, um für Notrufe eine Konferenzschaltung mit dem Sicherheitspersonal einzurichten.</span><span class="sxs-lookup"><span data-stu-id="afebd-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="afebd-p104">Falls erforderlich, können Sie für jede Ortungsrichtlinie unterschiedliches Notrufpersonal konfigurieren. Auf diese Weise können Sie die Maßnahmen für unterschiedliche Unternehmensbereiche anpassen oder ein unterschiedliches Verhalten für Notrufe konfigurieren, die von innerhalb oder von außerhalb des Netzwerks erfolgen. Geben Sie die Mitarbeiter, die benachrichtigt werden sollen, mithilfe von Verteilergruppen an.</span><span class="sxs-lookup"><span data-stu-id="afebd-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span>



<span data-ttu-id="afebd-118"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="afebd-118"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

