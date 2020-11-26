---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer'
description: 'Lync Server 2013: Konfigurieren von Richtlinien zum Steuern des Remotebenutzerzugriffs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6408747cfbbc5e7dff8fd198c0de162f49fc5ff2
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433773"
---
# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="2fe68-103">Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fe68-103">Configure policies to control remote user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="2fe68-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="2fe68-104">

<span> </span></span></span>

<span data-ttu-id="2fe68-105">_**Letztes Änderungsdatum des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="2fe68-105">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="2fe68-106">Sie konfigurieren eine oder mehrere Richtlinien für den externen Benutzer Zugriff, um zu steuern, ob Remotebenutzer mit internen lync Server-Benutzern zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="2fe68-106">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="2fe68-107">Wenn Sie den Zugriff durch Remotebenutzer steuern möchten, können Sie Richtlinien auf globaler, Website-und Benutzerebene konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2fe68-107">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="2fe68-108">Website Richtlinien überschreiben die globale Richtlinie, und Benutzerrichtlinien überschreiben Website-und globale Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="2fe68-108">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="2fe68-109">Details zu den Richtlinientypen, die Sie konfigurieren können, finden Sie unter [Verwalten des Föderations-und des externen Zugriffs auf lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="2fe68-109">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="2fe68-110">Lync Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2fe68-110">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="2fe68-111">Die Priorität der lync Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss).</span><span class="sxs-lookup"><span data-stu-id="2fe68-111">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="2fe68-112">Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="2fe68-112">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2fe68-113">Sie können Richtlinien konfigurieren, um den Remotebenutzerzugriff zu steuern, auch wenn Sie den Remotebenutzerzugriff für Ihre Organisation nicht aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="2fe68-113">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="2fe68-114">Die von Ihnen konfigurierten Richtlinien gelten jedoch nur, wenn der Remotebenutzerzugriff für Ihre Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2fe68-114">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="2fe68-115">Ausführliche Informationen zum Aktivieren des Remotebenutzerzugriffs finden Sie unter <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2fe68-115">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="2fe68-116">Wenn Sie außerdem eine Benutzerrichtlinie zum Steuern des Remotebenutzerzugriffs angeben, gilt die Richtlinie nur für Benutzer, die für lync Server aktiviert und für die Verwendung der Richtlinie konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="2fe68-116">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="2fe68-117">Details zum Angeben von Benutzern, die sich bei lync Server von Remotestandorten aus anmelden können, finden Sie unter <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Zuweisen einer Richtlinie für den externen Benutzer Zugriff zu einem lync-aktivierten Benutzer in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2fe68-117">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="2fe68-118">Gehen Sie wie folgt vor, um jede Richtlinie für den externen Zugriff zu konfigurieren, die Sie zum Steuern des Remotebenutzerzugriffs verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="2fe68-118">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2fe68-119">In diesem Verfahren wird beschrieben, wie Sie eine Richtlinie nur für die Kommunikation mit Remotebenutzern konfigurieren, aber jede Richtlinie, die Sie für die Unterstützung des Remotebenutzerzugriffs konfigurieren, kann auch den Zugriff durch den Verbundbenutzer und den Zugriff auf öffentliche Benutzer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2fe68-119">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="2fe68-120">Details zum Konfigurieren von Richtlinien für die Unterstützung von Verbundbenutzern finden Sie unter <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zum Steuern des Zugriffs auf den Verbundbenutzer in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2fe68-120">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="2fe68-121">Details zum Konfigurieren von Richtlinien für die Unterstützung öffentlicher Benutzer finden Sie unter <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2fe68-121">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="2fe68-122">So konfigurieren Sie eine Richtlinie für den externen Zugriff zur Unterstützung des Remotebenutzerzugriffs</span><span class="sxs-lookup"><span data-stu-id="2fe68-122">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="2fe68-123">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="2fe68-123">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2fe68-124">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2fe68-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2fe68-125">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2fe68-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2fe68-126">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="2fe68-126">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="2fe68-127">Führen Sie auf der Seite " **externe Zugriffsrichtlinie** " eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="2fe68-127">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="2fe68-128">Wenn Sie die globale Richtlinie für die Unterstützung des Remotebenutzerzugriffs konfigurieren möchten, klicken Sie auf die globale Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="2fe68-128">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="2fe68-129">Klicken Sie zum Erstellen einer neuen Website Richtlinie auf **neu**, und klicken Sie dann auf **Website Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="2fe68-129">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="2fe68-130">Klicken Sie unter **Website auswählen** auf die entsprechende Website in der Liste, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fe68-130">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="2fe68-131">Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="2fe68-131">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="2fe68-132">Erstellen Sie in der **neuen Richtlinie für den externen Zugriff** im Feld **Name** einen eindeutigen Namen, der angibt, was die Benutzerrichtlinie umfasst (beispielsweise **EnableRemoteUsers** für eine Benutzerrichtlinie, die die Kommunikation für Remotebenutzer aktiviert).</span><span class="sxs-lookup"><span data-stu-id="2fe68-132">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="2fe68-133">Wenn Sie eine vorhandene Richtlinie ändern möchten, klicken Sie auf die entsprechende in der Tabelle aufgelistete Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="2fe68-133">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2fe68-134">Optional Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen für die Richtlinie unter **Beschreibung** an.</span><span class="sxs-lookup"><span data-stu-id="2fe68-134">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="2fe68-135">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2fe68-135">Do one of the following:</span></span>
    
      - <span data-ttu-id="2fe68-136">Aktivieren Sie das Kontrollkästchen **Kommunikation mit Remotebenutzern aktivieren** , um den Remotebenutzerzugriff für die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2fe68-136">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="2fe68-137">Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Remotebenutzern aktivieren** , um den Remotebenutzerzugriff für die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2fe68-137">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="2fe68-138">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2fe68-138">Click **Commit**.</span></span>

<span data-ttu-id="2fe68-139">Wenn Sie den Zugriff durch Remotebenutzer aktivieren möchten, müssen Sie auch die Unterstützung für den Zugriff durch Remotebenutzer in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2fe68-139">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="2fe68-140">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2fe68-140">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="2fe68-141">Wenn es sich um eine Benutzerrichtlinie handelt, müssen Sie die Richtlinie auch auf Benutzer anwenden, die eine Remoteverbindung herstellen können sollen.</span><span class="sxs-lookup"><span data-stu-id="2fe68-141">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="2fe68-142">Ausführliche Informationen finden Sie unter [Zuweisen einer externen Benutzerzugriffs Richtlinie zu einem lync-aktivierten Benutzer in lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2fe68-142">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="2fe68-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="2fe68-143"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

