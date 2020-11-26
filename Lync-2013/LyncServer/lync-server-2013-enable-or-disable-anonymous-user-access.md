---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer'
description: 'Lync Server 2013: Aktivieren oder Deaktivieren des Zugriffs auf anonyme Benutzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ca36cffc25cd31d057b00c22cb299c56cfd7b3c
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437560"
---
# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="1c7e5-103">Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c7e5-103">Enable or disable anonymous user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="1c7e5-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="1c7e5-104">

<span> </span></span></span>

<span data-ttu-id="1c7e5-105">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1c7e5-105">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1c7e5-106">Anonyme Benutzer sind Benutzer, die nicht über ein Benutzerkonto in den Active Directory-Domänendiensten Ihrer Organisation oder in einer unterstützten Föderationsdomäne verfügen, aber zur Remote Teilnahme an einer lokalen Konferenz eingeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-106">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="1c7e5-107">Durch das zulassen anonymer Teilnahme an Besprechungen können Sie anonyme Benutzer (also Benutzer, deren Identität nur über den Besprechungs-oder Konferenzschlüssel überprüft wird) aktivieren, um an Besprechungen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-107">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="1c7e5-108">Das Zulassen einer anonymen Teilnahme erfordert die Aktivierung für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-108">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="1c7e5-109">Wenn Sie den Zugriff von anonymen Benutzern später vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-109">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="1c7e5-110">Verwenden Sie das Verfahren in diesem Abschnitt, um den anonymen Benutzer Zugriff für Ihre Organisation zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-110">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c7e5-111">Indem Sie den anonymen Benutzer Zugriff für Ihre Organisation aktivieren, geben Sie nur an, dass die Server, auf denen der Access Edge-Dienst ausgeführt wird, den Zugriff durch anonyme Benutzer unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-111">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="1c7e5-112">Anonyme Benutzer können erst dann an Besprechungen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine konferenzrichtlinie konfiguriert und auf einen oder mehrere Benutzer oder Benutzergruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-112">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="1c7e5-113">Die einzigen Benutzer, die anonyme Benutzer zu Besprechungen einladen können, sind diejenigen Benutzer, denen eine konferenzrichtlinie zugewiesen ist, die für die Unterstützung anonymer Benutzer konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-113">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="1c7e5-114">Details zum Konfigurieren von Konferenzrichtlinien zur Unterstützung der Einladung anonymer Benutzer finden Sie unter <A href="lync-server-2013-conferencing-policies.md">Konferenzrichtlinien in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-114">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="1c7e5-115">So aktivieren oder deaktivieren Sie den anonymen Benutzer Zugriff für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="1c7e5-115">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="1c7e5-116">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-116">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1c7e5-117">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1c7e5-118">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1c7e5-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1c7e5-119">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Access-Edge-Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-119">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="1c7e5-120">Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-120">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1c7e5-121">Führen Sie in " **Access-Edge-Konfiguration bearbeiten**" eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="1c7e5-121">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="1c7e5-122">Aktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** , um den anonymen Benutzer Zugriff für Ihre Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-122">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="1c7e5-123">Wenn Sie den anonymen Benutzer Zugriff für Ihre Organisation deaktivieren möchten, deaktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="1c7e5-123">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="1c7e5-124">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1c7e5-125">Aktivieren oder Deaktivieren des Zugriffs auf anonyme Benutzer mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="1c7e5-125">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1c7e5-126">Sie können den anonymen Benutzer Zugriff mithilfe von Windows PowerShell und dem Cmdlet " **Satz-csaccessedgeconfiguration nicht angeben** " verwalten.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-126">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="1c7e5-127">Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-127">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1c7e5-128">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="1c7e5-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="1c7e5-129">So aktivieren Sie den anonymen Benutzer Zugriff</span><span class="sxs-lookup"><span data-stu-id="1c7e5-129">To enable anonymous user access</span></span>

  - <span data-ttu-id="1c7e5-130">Um den anonymen Benutzer Zugriff zu aktivieren, setzen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf true ($true):</span><span class="sxs-lookup"><span data-stu-id="1c7e5-130">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="1c7e5-131">So deaktivieren Sie den anonymen Benutzer Zugriff</span><span class="sxs-lookup"><span data-stu-id="1c7e5-131">To disable anonymous user access</span></span>

  - <span data-ttu-id="1c7e5-132">Um den anonymen Benutzer Zugriff zu deaktivieren, setzen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf false ($false):</span><span class="sxs-lookup"><span data-stu-id="1c7e5-132">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1c7e5-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c7e5-133">See Also</span></span>


[<span data-ttu-id="1c7e5-134">Referenz für konferenzrichtlinieneinstellungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c7e5-134">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

<span data-ttu-id="1c7e5-135"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="1c7e5-135"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

