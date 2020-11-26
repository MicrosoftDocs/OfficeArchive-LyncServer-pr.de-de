---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs'
description: 'Lync Server 2013: Konfigurieren von Richtlinien zum Steuern des Zugriffs durch öffentliche Benutzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d44437cc288d1515784af8c635f4b28902c4fa1
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433787"
---
# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="7cd27-103">Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cd27-103">Configure policies to control public user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="7cd27-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="7cd27-104">

<span> </span></span></span>

<span data-ttu-id="7cd27-105">_**Letztes Änderungsdatum des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="7cd27-105">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="7cd27-106">Mit der öffentlichen Instant Messaging-Konnektivität (im) können Benutzer in Ihrer Organisation Chatnachrichten verwenden, um mit Benutzern der Chat Dienste zu kommunizieren, die von öffentlichen Chat Dienstanbietern bereitgestellt werden, einschließlich des Windows Live-Netzwerks von Internet Diensten, Yahoo \! und AOL.</span><span class="sxs-lookup"><span data-stu-id="7cd27-106">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="7cd27-107">Sie konfigurieren eine oder mehrere Richtlinien für den externen Benutzer Zugriff, um zu steuern, ob öffentliche Benutzer mit internen lync Server-Benutzern zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="7cd27-107">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="7cd27-108">Die öffentliche Instant Messaging-Konnektivität ist ein hinzugefügtes Feature, das auf der Konfiguration Ihrer Bereitstellung und der Benutzer basiert.</span><span class="sxs-lookup"><span data-stu-id="7cd27-108">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="7cd27-109">Sie hängt auch von der Bereitstellung des Diensts beim öffentlichen Chat Dienstanbieter ab.</span><span class="sxs-lookup"><span data-stu-id="7cd27-109">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="7cd27-110">Informationen dazu, wie Sie Ihre Bereitstellung für die Verwendung der öffentlichen Anbieter bereitstellen können, finden Sie im Leitfaden zu den öffentlichen im-Konnektivität für Microsoft lync Server, Office Communications Server und Live Communications Server. [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="7cd27-110">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="7cd27-111">Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7cd27-111">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="7cd27-112">Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden</span><span class="sxs-lookup"><span data-stu-id="7cd27-112">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="7cd27-113">Messenger, bis der Dienst das Datum beendet hat.</span><span class="sxs-lookup"><span data-stu-id="7cd27-113">Messenger until the service shut down date.</span></span> <span data-ttu-id="7cd27-114">Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="7cd27-114">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="7cd27-115">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="7cd27-115">has been announced.</span></span> <span data-ttu-id="7cd27-116">Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7cd27-116">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="7cd27-117">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7cd27-117">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="7cd27-118">Messenger.</span><span class="sxs-lookup"><span data-stu-id="7cd27-118">Messenger.</span></span> <span data-ttu-id="7cd27-119">Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</span><span class="sxs-lookup"><span data-stu-id="7cd27-119">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="7cd27-120">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="7cd27-120">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="7cd27-121">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7cd27-121">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="7cd27-122">Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="7cd27-122">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="7cd27-123">Verwenden Sie den folgenden Link, um auf die Bereitstellung der Microsoft lync Server Public im Connectivity-Bereitstellungswebsite zuzugreifen: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="7cd27-123">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="7cd27-124">Wenn Sie den Zugriff durch öffentliche Benutzer steuern möchten, können Sie Richtlinien auf globaler, Website-und Benutzerebene konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7cd27-124">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="7cd27-125">Details zu den Richtlinientypen, die Sie konfigurieren können, finden Sie unter [Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in der Bereitstellungsdokumentation oder in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7cd27-125">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="7cd27-126">Lync Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="7cd27-126">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="7cd27-127">Die Priorität der lync Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss).</span><span class="sxs-lookup"><span data-stu-id="7cd27-127">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="7cd27-128">Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="7cd27-128">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="7cd27-129">Im Fall von Chat-Einladungen hängt die Antwort von der Client Software ab.</span><span class="sxs-lookup"><span data-stu-id="7cd27-129">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="7cd27-130">Die Anforderung wird akzeptiert, es sei denn, externe Absender werden explizit durch eine vom Benutzer konfigurierte Regel blockiert (also die Einstellungen in den Client- **Allow** -und- **Block** Listen).</span><span class="sxs-lookup"><span data-stu-id="7cd27-130">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="7cd27-131">Darüber hinaus können Chat-Einladungen blockiert werden, wenn ein Benutzer wählt, Alle Chatnachrichten von Benutzern zu blockieren, die nicht in der **Zulassungs** Liste aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="7cd27-131">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7cd27-132">Sie können Richtlinien zum Steuern des Zugriffs durch öffentliche Benutzer konfigurieren, auch wenn Sie die Föderation für Ihre Organisation nicht aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="7cd27-132">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="7cd27-133">Die von Ihnen konfigurierten Richtlinien gelten jedoch nur, wenn der Verbund für Ihre Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7cd27-133">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="7cd27-134">Details zum Aktivieren von Föderation finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7cd27-134">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="7cd27-135">Wenn Sie außerdem eine Benutzerrichtlinie zum Steuern des Zugriffs durch öffentliche Benutzer angeben, gilt die Richtlinie nur für Benutzer, die für lync Server aktiviert und für die Verwendung der Richtlinie konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="7cd27-135">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="7cd27-136">Details zum Angeben von öffentlichen Benutzern, die sich bei lync Server anmelden können, finden Sie unter <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Zuweisen einer Richtlinie für den externen Benutzer Zugriff zu einem lync-aktivierten Benutzer in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7cd27-136">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="7cd27-137">Gehen Sie wie folgt vor, um eine Richtlinie zum unterstützen des Zugriffs durch Benutzer eines oder mehrerer öffentlicher Chat Anbieter zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7cd27-137">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="7cd27-138">So konfigurieren Sie eine Richtlinie für den externen Zugriff zur Unterstützung des Zugriffs durch öffentliche Benutzer</span><span class="sxs-lookup"><span data-stu-id="7cd27-138">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="7cd27-139">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7cd27-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7cd27-140">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7cd27-140">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7cd27-141">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7cd27-141">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7cd27-142">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="7cd27-142">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="7cd27-143">Führen Sie auf der Seite " **externe Zugriffsrichtlinie** " eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="7cd27-143">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="7cd27-144">Wenn Sie die globale Richtlinie für die Unterstützung des Zugriffs durch öffentliche Benutzer konfigurieren möchten, klicken Sie auf die globale Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7cd27-144">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="7cd27-145">Klicken Sie zum Erstellen einer neuen Website Richtlinie auf **neu**, und klicken Sie dann auf **Website Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="7cd27-145">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="7cd27-146">Klicken Sie unter **Website auswählen** auf die entsprechende Website in der Liste, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7cd27-146">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="7cd27-147">Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="7cd27-147">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="7cd27-148">Erstellen Sie in der **neuen Richtlinie für den externen Zugriff** im Feld **Name** einen eindeutigen Namen, der angibt, was die Benutzerrichtlinie umfasst (beispielsweise **EnablePublicUsers** für eine Benutzerrichtlinie, die die Kommunikation für öffentliche Benutzer aktiviert).</span><span class="sxs-lookup"><span data-stu-id="7cd27-148">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="7cd27-149">Wenn Sie eine vorhandene Richtlinie ändern möchten, klicken Sie auf die entsprechende in der Tabelle aufgelistete Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7cd27-149">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7cd27-150">Optional Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen für die Richtlinie unter **Beschreibung** an.</span><span class="sxs-lookup"><span data-stu-id="7cd27-150">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="7cd27-151">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7cd27-151">Do one of the following:</span></span>
    
      - <span data-ttu-id="7cd27-152">Aktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren** , um den Zugriff öffentlicher Benutzer für die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7cd27-152">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="7cd27-153">Deaktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren** , um den Zugriff öffentlicher Benutzer für die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7cd27-153">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="7cd27-154">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7cd27-154">Click **Commit**.</span></span>

<span data-ttu-id="7cd27-155">Wenn Sie den Zugriff durch öffentliche Benutzer aktivieren möchten, müssen Sie auch die Unterstützung für den Verbund in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7cd27-155">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="7cd27-156">Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7cd27-156">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="7cd27-157">Wenn es sich um eine Benutzerrichtlinie handelt, müssen Sie die Richtlinie auch auf öffentliche Benutzer anwenden, die in der Lage sein sollen, mit öffentlichen Benutzern zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7cd27-157">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="7cd27-158">Ausführliche Informationen finden Sie unter [Zuweisen von Richtlinien für einzelne Benutzer in lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7cd27-158">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7cd27-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cd27-159">See Also</span></span>


[<span data-ttu-id="7cd27-160">Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cd27-160">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="7cd27-161">Verwalten von SIP-Partnerverbundanbietern für eine Organisation in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cd27-161">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

<span data-ttu-id="7cd27-162"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="7cd27-162"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

