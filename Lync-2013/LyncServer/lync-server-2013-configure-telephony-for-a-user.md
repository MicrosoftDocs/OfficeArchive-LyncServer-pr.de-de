---
title: 'Lync Server 2013: Konfigurieren der Telefonie für einen Benutzer'
description: 'Lync Server 2013: Konfigurieren der Telefonie für einen Benutzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b82cecb67ea11928d187bd2a4a00625fbca7b23e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433654"
---
# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a><span data-ttu-id="21d89-103">Konfigurieren der Telefonie für einen Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21d89-103">Configure telephony for a user in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="21d89-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="21d89-104">

<span> </span></span></span>

<span data-ttu-id="21d89-105">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="21d89-105">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="21d89-106">Telefonieeinstellungen sind einige der individuellen Einstellungen eines Benutzerkontos, das in der lync Server-Systemsteuerung für den Benutzer konfiguriert werden kann (das heißt, wenn der einzelne Benutzer für lync Server 2013 aktiviert wurde und die Organisation die Telefonie unterstützt).</span><span class="sxs-lookup"><span data-stu-id="21d89-106">Telephony settings are some of the individual settings of a user account that can be configured in Lync Server Control Panel for the user (that is, if the individual user has been enabled for Lync Server 2013 and the organization supports telephony).</span></span>

<span data-ttu-id="21d89-107">Zu den lync Server-Benutzer Telefonie-Optionen gehören die folgenden:</span><span class="sxs-lookup"><span data-stu-id="21d89-107">Lync Server user telephony options include the following:</span></span>

  - <span data-ttu-id="21d89-108">**Audio/Video deaktiviert**   Der Benutzer kann mit Audio und Video keine Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="21d89-108">**Audio/video disabled**   The user cannot make calls with audio and video.</span></span>

  - <span data-ttu-id="21d89-109">**Nur PC-zu-PC**   Der Benutzer kann nur PC-zu-PC-Audio-oder Videoanrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="21d89-109">**PC-to-PC only**   The user can make only PC-to-PC audio or video calls.</span></span>

  - <span data-ttu-id="21d89-110">**Enterprise-VoIP**   Der Benutzer kann die lync Server 2013-Infrastruktur verwenden, um alle eingehenden und ausgehenden Anrufe weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="21d89-110">**Enterprise Voice**   The user can use the Lync Server 2013 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="21d89-111">Der Benutzer kann auch PC-zu-PC-Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="21d89-111">The user can also make PC-to-PC calls.</span></span>

  - <span data-ttu-id="21d89-112">**Remote Anrufsteuerung**   Der Benutzer kann lync Server 2013 verwenden, um das Desktoptelefon zu steuern, und kann auch PC-zu-PC-Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="21d89-112">**Remote call control**   The user can use Lync Server 2013 to control the desktop phone, and can also make PC-to-PC calls.</span></span>

<span data-ttu-id="21d89-113">Details zum Konfigurieren der Telefonie für eine Organisation finden Sie unter [Konfigurieren der Telefonie für einen Benutzer in lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) und [Bereitstellen von Enterprise-VoIP in lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="21d89-113">For details about configuring telephony for an organization, see [Configure telephony for a user in Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) and [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a><span data-ttu-id="21d89-114">So konfigurieren Sie die Telefonie für ein bestimmtes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="21d89-114">To configure telephony for a specific user account</span></span>

1.  <span data-ttu-id="21d89-115">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="21d89-115">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="21d89-116">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="21d89-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="21d89-117">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="21d89-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="21d89-118">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="21d89-118">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="21d89-119">Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="21d89-119">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="21d89-120">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="21d89-120">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="21d89-121">Klicken Sie im Menü **Bearbeiten** auf **ändern**.</span><span class="sxs-lookup"><span data-stu-id="21d89-121">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="21d89-122">Führen Sie in **Telefonie** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="21d89-122">In **Telephony**, do the following:</span></span>
    
      - <span data-ttu-id="21d89-123">Wenn Sie Audio-und Videoanrufe für den Benutzer deaktivieren möchten, klicken Sie auf **Audio/Video deaktiviert**.</span><span class="sxs-lookup"><span data-stu-id="21d89-123">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
      - <span data-ttu-id="21d89-124">Wenn Sie die PC-zu-PC-Audiokommunikation für den Benutzer, aber nicht die Remoteanrufsteuerung oder Enterprise-VoIP aktivieren möchten, klicken Sie auf **nur PC-zu-** PC.</span><span class="sxs-lookup"><span data-stu-id="21d89-124">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="21d89-125">Geben Sie einen Wert für den **Leitungs-URI** für das Telefon an, das der Benutzer für die PC-zu-PC-Audiokommunikation verwendet.</span><span class="sxs-lookup"><span data-stu-id="21d89-125">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
      - <span data-ttu-id="21d89-126">Klicken Sie auf **Enterprise-VoIP**, um die Telefonanrufe des Benutzers mithilfe der lync Server 2010-Infrastruktur in Übereinstimmung mit der Service Richtlinienklasse zu leiten, einschließlich PC-zu-PC-Audiokommunikation.</span><span class="sxs-lookup"><span data-stu-id="21d89-126">To route the user's phone calls by using the Lync Server 2010 infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="21d89-127">Geben Sie in der **Zeile URI** die Telefonnummer für Enterprise-VoIP an.</span><span class="sxs-lookup"><span data-stu-id="21d89-127">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="21d89-128">Geben Sie in der Richtlinie für **Wähl Plan Richtlinien** und **VoIP** die entsprechenden Richtlinien für den Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="21d89-128">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="21d89-129">Wenn Sie die Normalisierungsregeln für die Übersetzung von Telefonnummern angeben möchten, die vom Benutzer im E. 164-Format gewählt wurden, wählen Sie das entsprechende Standortprofil in der **ortungsrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="21d89-129">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
      - <span data-ttu-id="21d89-130">Klicken Sie auf **Remoteanrufsteuerung**, um die Remoteanrufsteuerung zu aktivieren, mit der Benutzer Ihre Desktop-Telefonleitung von lync Server 2013 steuern können, um PC-zu-PC-Anrufe zu tätigen und PC-zu-Telefon-Anrufe zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="21d89-130">To enable remote call control, which enables users to control their desktop phone line from Lync Server 2013 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="21d89-131">Geben Sie in der **Zeile URI** die Telefonnummer für die Remoteanrufsteuerung ein.</span><span class="sxs-lookup"><span data-stu-id="21d89-131">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="21d89-132">Der Benutzer muss über ein Desktoptelefon und eine PBX-Verbindung (Private Branch Exchange) für das Anrufrouting verfügen.</span><span class="sxs-lookup"><span data-stu-id="21d89-132">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21d89-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21d89-133">See Also</span></span>


[<span data-ttu-id="21d89-134">Ändern von Benutzerkontoeigenschaften in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21d89-134">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="21d89-135"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="21d89-135"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

