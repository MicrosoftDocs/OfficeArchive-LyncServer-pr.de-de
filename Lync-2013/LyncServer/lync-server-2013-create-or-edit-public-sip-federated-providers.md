---
title: 'Lync Server 2013: Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern'
description: 'Lync Server 2013: Erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0ef5850b5e8016e0bd90512db45c2917c16a104
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431876"
---
# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a><span data-ttu-id="ddbb6-103">Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ddbb6-103">Create or edit public SIP federated providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="ddbb6-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="ddbb6-104">

<span> </span></span></span>

<span data-ttu-id="ddbb6-105">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ddbb6-105">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ddbb6-106">Mit der öffentlichen Instant Messaging-Konnektivität (im) können Benutzer in Ihrer Organisation Chatnachrichten verwenden, um mit Benutzern von Chat Diensten zu kommunizieren, die von öffentlichen Chat Dienstanbietern, einschließlich Windows Live Messenger, Yahoo und AOL, bereitgestellt werden \! .</span><span class="sxs-lookup"><span data-stu-id="ddbb6-106">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live Messenger, Yahoo\!, and AOL.</span></span>

<span data-ttu-id="ddbb6-107">Lync Server 2013 verfügt über öffentliche Anbieter Konfigurationen für Amerika Online, Windows Live und Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="ddbb6-107">Lync Server 2013 has public provider configurations for America Online, Windows Live and Yahoo\!</span></span> <span data-ttu-id="ddbb6-108">Sofortnachrichten.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-108">instant messaging.</span></span> <span data-ttu-id="ddbb6-109">Jeder öffentliche Anbieter ist mit dem vollqualifizierten Domänennamen für den Edge-Server des Anbieters konfiguriert, und die Standard Überprüfungsstufe **ermöglicht Benutzern, nur mit Personen in der Kontaktliste zu kommunizieren, die diesen Anbieter verwenden**.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-109">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="ddbb6-110">Als Standardeinstellung ist keiner der öffentlichen Anbieter aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-110">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="ddbb6-111">Sie sollten den Lizenzvertrag und die Bereitstellungs Arbeit abschließen, bevor Sie die öffentlichen Anbieter aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-111">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="ddbb6-112">Sie können den Anbieter aktivieren, bevor Sie die Lizenzierung und Bereitstellungs Arbeit abschließen.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-112">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="ddbb6-113">Die Benutzer können erst dann mit Kontakten an diesen Anbietern kommunizieren, wenn die Voraussetzungen für die Arbeit erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-113">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="ddbb6-114">Details zur Lizenzierung und Bereitstellung öffentlicher Anbieter finden Sie unter Konfigurieren von [Richtlinien zum Steuern des Zugriffs öffentlicher Benutzer in lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ddbb6-114">For details on licensing and provisioning of public providers, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="ddbb6-115">Gehen Sie wie folgt vor, um öffentliche Anbieter zu erstellen oder zu bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="ddbb6-115">Use the following procedure to create or edit Public providers:</span></span>

<div>

## <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="ddbb6-116">So erstellen oder bearbeiten Sie öffentliche Anbieter</span><span class="sxs-lookup"><span data-stu-id="ddbb6-116">To create or edit public providers</span></span>

1.  <span data-ttu-id="ddbb6-117">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-117">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ddbb6-118">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ddbb6-119">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ddbb6-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ddbb6-120">Klicken Sie in der linken Navigationsleiste auf **Föderation und externer Zugriff**, und klicken Sie dann auf **SIP-Verbund Anbieter**.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-120">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="ddbb6-121">Wenn Sie einen neuen öffentlichen Anbieter erstellen müssen, klicken Sie auf **neu** , und klicken Sie dann auf **öffentlicher Anbieter**.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-121">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="ddbb6-122">Wenn Sie einen Eintrag aus der Liste der öffentlichen Anbieter bearbeiten möchten, wählen Sie einen öffentlichen Anbieter aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-122">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="ddbb6-123">Auf der Seite **SIP-Verbund Anbieter bearbeiten** können Sie die folgenden Einstellungen eingeben oder bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="ddbb6-123">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="ddbb6-124">**Aktivieren der Kommunikation mit diesem Anbieter**   Wenn Sie diese Einstellung aktivieren, wird im mit den Benutzern dieses Anbieters aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-124">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="ddbb6-125">**Anbietername:**   Eine erforderliche Eigenschaft, geben Sie den Namen des Anbieters ein, wie er in der Liste der SIP-Verbund Anbieter wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-125">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="ddbb6-126">**Access Edge Service (FQDN):**   Eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Access-Edgedienst des Anbieters ein, den Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-126">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="ddbb6-127">Diese Informationen werden als Standardelement bereitgestellt und sollten nur geändert werden, wenn der öffentliche Anbieter eine Änderung an dem FQDN des Access Edge-Diensts beim öffentlichen Anbieter vornimmt.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-127">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="ddbb6-128">**Standard Überprüfungsstufe:**   Die Standardeinstellung **ermöglicht Benutzern die Kommunikation mit Personen in Ihrer Kontaktliste, die diesen Anbieter verwenden** , beschränkt die Kommunikation auf Kontakte, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-128">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="ddbb6-129">**Wenn Sie Benutzern erlauben, mit allen Personen zu kommunizieren, die diesen Anbieter verwenden, wird** die Einschränkung entfernt, die Sie erhalten haben und eine Kontakt Einladung akzeptieren müssen.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-129">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="ddbb6-130">Diese Einstellung beschränkt nicht, wer Sie aus dem Netzwerk des öffentlichen Anbieters kontaktieren kann.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-130">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="ddbb6-131">Wenn Sie die Konfiguration der Einstellungen abgeschlossen haben, klicken **Sie zum Speichern auf übernehmen** , oder klicken Sie auf **Abbrechen** , um die Änderungen zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="ddbb6-131">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ddbb6-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddbb6-132">See Also</span></span>


[<span data-ttu-id="ddbb6-133">Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ddbb6-133">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="ddbb6-134">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ddbb6-134">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

<span data-ttu-id="ddbb6-135"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="ddbb6-135"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

