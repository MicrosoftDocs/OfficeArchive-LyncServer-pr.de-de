---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs'
description: 'Lync Server 2013: Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d69f35baa16086b0c4e93a2a015474f87e08b736
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394198"
---
# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="184a7-103">Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="184a7-103">Configure policies to control federated user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="184a7-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="184a7-104">

<span> </span></span></span>

<span data-ttu-id="184a7-105">_**Letztes Änderungsdatum des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="184a7-105">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="184a7-106">Wenn Sie Richtlinien für die Unterstützung der Kommunikation mit Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von Verbunddomänen.</span><span class="sxs-lookup"><span data-stu-id="184a7-106">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="184a7-107">Sie können eine oder mehrere Richtlinien für den externen Benutzer Zugriff konfigurieren, um zu steuern, ob Benutzer von Verbunddomänen mit ihren lync Server 2013-Benutzern zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="184a7-107">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="184a7-108">Zum Steuern des Zugriffs von Verbundbenutzern können Sie Richtlinien auf globaler, Website-und Benutzerebene konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="184a7-108">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="184a7-109">Lync Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="184a7-109">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="184a7-110">Die Priorität der lync Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss).</span><span class="sxs-lookup"><span data-stu-id="184a7-110">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="184a7-111">Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="184a7-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="184a7-112">Sie können Richtlinien zum Steuern des Zugriffs von Verbundbenutzern konfigurieren, auch wenn Sie den Verbund für Ihre Organisation nicht aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="184a7-112">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="184a7-113">Die von Ihnen konfigurierten Richtlinien gelten jedoch nur, wenn der Verbund für Ihre Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="184a7-113">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="184a7-114">Details zum Aktivieren von Föderation finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="184a7-114">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="184a7-115">Wenn Sie eine Benutzerrichtlinie zum Steuern des Zugriffs von Verbundbenutzern angeben, gilt die Richtlinie zudem nur für Benutzer, die für lync Server 2013 aktiviert und für die Verwendung der Richtlinie konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="184a7-115">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="184a7-116">So konfigurieren Sie eine Richtlinie zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="184a7-116">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="184a7-117">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="184a7-117">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="184a7-118">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="184a7-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="184a7-119">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="184a7-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="184a7-120">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="184a7-120">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="184a7-121">Führen Sie auf der Seite " **externe Zugriffsrichtlinie** " eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="184a7-121">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="184a7-122">Klicken Sie zum Konfigurieren der globalen Richtlinie zur Unterstützung des Zugriffs von Verbundbenutzern auf die globale Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="184a7-122">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="184a7-123">Klicken Sie zum Erstellen einer neuen Website Richtlinie auf **neu**, und klicken Sie dann auf **Website Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="184a7-123">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="184a7-124">Klicken Sie unter **Website auswählen** auf die entsprechende Website in der Liste, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="184a7-124">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="184a7-125">Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="184a7-125">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="184a7-126">Erstellen Sie in der **neuen Richtlinie für den externen Zugriff** im Feld **Name** einen eindeutigen Namen, der angibt, was die Benutzerrichtlinie umfasst (beispielsweise **EnableFederatedUsers** für eine Benutzerrichtlinie, die die Kommunikation für Verbunddomänen Benutzer aktiviert).</span><span class="sxs-lookup"><span data-stu-id="184a7-126">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="184a7-127">Wenn Sie eine vorhandene Richtlinie ändern möchten, klicken Sie auf die entsprechende in der Tabelle aufgelistete Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="184a7-127">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="184a7-128">Optional Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen für die Richtlinie unter **Beschreibung** an.</span><span class="sxs-lookup"><span data-stu-id="184a7-128">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="184a7-129">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="184a7-129">Do one of the following:</span></span>
    
      - <span data-ttu-id="184a7-130">Wenn Sie den Verbundbenutzer Zugriff für die Richtlinie aktivieren möchten, aktivieren Sie das Kontrollkästchen **Kommunikation mit verbundenen Benutzern aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="184a7-130">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="184a7-131">Wenn Sie den Verbundbenutzer Zugriff für die Richtlinie deaktivieren möchten, deaktivieren Sie das Kontrollkästchen **Kommunikation mit verbundenen Benutzern aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="184a7-131">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="184a7-132">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="184a7-132">Click **Commit**.</span></span>

<span data-ttu-id="184a7-133">Zum Aktivieren des Zugriffs auf den Verbundbenutzer müssen Sie auch die Unterstützung für den Verbund in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="184a7-133">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="184a7-134">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="184a7-134">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="184a7-135">Wenn es sich um eine Benutzerrichtlinie handelt, müssen Sie die Richtlinie auch auf Benutzer anwenden, die in der Lage sein sollen, mit Verbundbenutzern zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="184a7-135">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="184a7-136">Ausführliche Informationen finden Sie unter [Zuweisen einer externen Benutzerzugriffs Richtlinie zu einem lync-aktivierten Benutzer in lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span><span class="sxs-lookup"><span data-stu-id="184a7-136">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="184a7-137">So konfigurieren Sie eine vorhandene Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="184a7-137">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="184a7-138">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="184a7-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="184a7-139">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="184a7-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="184a7-140">Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="184a7-140">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="184a7-141">Ein Beispielbefehl, der die globale Richtlinie für den Verbundbenutzer Zugriff auf Enabled, XMPP-Domänenzugriff auf aktiviert, Remote Benutzer Zugriff auf aktiviert, Zugriff durch öffentliche Anbieter auf aktiviert und die Möglichkeit zur Verwendung von Audio und Video für öffentliche Anbieter, die es unterstützen, festlegen soll:</span><span class="sxs-lookup"><span data-stu-id="184a7-141">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="184a7-142">Der Parameter "EnablePublicCloudAudioVideoAccess" hat in der lync Server-Systemsteuerung keine entsprechende Auswahl.</span><span class="sxs-lookup"><span data-stu-id="184a7-142">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="184a7-143">So erstellen Sie eine neue Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="184a7-143">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="184a7-144">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="184a7-144">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="184a7-145">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="184a7-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="184a7-146">Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="184a7-146">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="184a7-147">Ein Beispiel für das Erstellen einer neuen Website Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="184a7-147">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="184a7-148">So löschen oder setzen Sie eine Richtlinie mithilfe von Windows PowerShell zurück, um den Zugriff durch Benutzer von Verbunddomänen zu unterstützen</span><span class="sxs-lookup"><span data-stu-id="184a7-148">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="184a7-149">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="184a7-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="184a7-150">Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="184a7-150">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="184a7-151">Ein Beispiel für das Zurücksetzen der globalen Richtlinie (für die globale Richtlinie kann nur die Einstellung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="184a7-151">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="184a7-152">Die Richtlinie kann nicht gelöscht werden):</span><span class="sxs-lookup"><span data-stu-id="184a7-152">The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="184a7-153">Um eine Website Richtlinie zu entfernen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="184a7-153">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="184a7-154">Löscht die Website Richtlinie Redmond.</span><span class="sxs-lookup"><span data-stu-id="184a7-154">Deletes the site policy Redmond.</span></span> <span data-ttu-id="184a7-155">Zum Löschen einer Benutzerrichtlinie mit dem Namen UserEAPPolicy geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="184a7-155">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="184a7-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="184a7-156">See Also</span></span>


[<span data-ttu-id="184a7-157">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="184a7-157">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="184a7-158">Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="184a7-158">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="184a7-159">Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="184a7-159">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="184a7-160">Verwalten von SIP-Partnerverbundanbietern für eine Organisation in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="184a7-160">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="184a7-161">Satz-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="184a7-161">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="184a7-162">Neu – CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="184a7-162">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="184a7-163">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="184a7-163">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="184a7-164">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="184a7-164">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="184a7-165">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="184a7-165">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

<span data-ttu-id="184a7-166"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="184a7-166"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

