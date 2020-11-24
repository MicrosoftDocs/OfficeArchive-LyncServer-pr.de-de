---
title: 'Lync Server 2013: Aktivieren von Lync-Benutzern für die Remoteanrufsteuerung'
description: 'Lync Server 2013: Aktivieren von lync-Benutzern für die Remoteanrufsteuerung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84b76d0d899da8ca25f42b5bed450914890f4b27
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49395022"
---
# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="7213b-103">Aktivieren von Lync-Benutzern für die Remoteanrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7213b-103">Enable Lync users for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="7213b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="7213b-104">

<span> </span></span></span>

<span data-ttu-id="7213b-105">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7213b-105">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7213b-106">Sie können lync-Benutzer für die Remoteanrufsteuerung konfigurieren, indem Sie in-Band-Bereitstellungsrichtlinien verwenden, die Server basiert sind.</span><span class="sxs-lookup"><span data-stu-id="7213b-106">You can configure Lync users for remote call control by using in-band provisioning policies that are server-based.</span></span> <span data-ttu-id="7213b-107">Sie können in-Band-Bereitstellungseinstellungen mithilfe der lync Server-Systemsteuerung oder der Befehlszeilenschnittstelle der lync Server-Verwaltungsshell verwalten.</span><span class="sxs-lookup"><span data-stu-id="7213b-107">You can manage in-band provisioning settings by using Lync Server Control Panel or the Lync Server Management Shell command-line interface.</span></span> <span data-ttu-id="7213b-108">Diese Tools ersetzen das WMI-Snap-in (Windows Management Instrumentation), das zum Verwalten von Gruppenrichtlinieneinstellungen in früheren Versionen verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="7213b-108">These tools replace the Windows Management Instrumentation (WMI) snap-in that was used to manage Group Policy settings in earlier releases.</span></span>

<span data-ttu-id="7213b-109">Wenn Sie es vorziehen, Benutzern die Konfiguration eigener Einstellungen für die Remoteanrufsteuerung in lync zu ermöglichen, können Sie die Einstellungen für die Remoteanrufsteuerung für Benutzer auf dem Server konfigurieren, ohne den URI und die **URI** -Werte für den **Leitungsserver** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7213b-109">If you prefer to let users to configure their own remote call control settings in Lync, you can configure remote call control settings for users on the server without specifying **Line Server URI** and **Line URI** values.</span></span> <span data-ttu-id="7213b-110">Stellen Sie sicher, dass Sie Ihren Benutzern die entsprechenden URI- **und URI-Werte für** den **Leitungs Server** mitteilen, und geben Sie Ihren Benutzern die Anweisungen zum Konfigurieren dieser Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="7213b-110">Be sure that you communicate the appropriate **Line Server URI** and **Line URI** values to your users, and provide your users with the instructions to configure these settings.</span></span> <span data-ttu-id="7213b-111">Das Verfahren zum manuellen Konfigurieren der Remoteanrufsteuerung in lync Server finden Sie unter "Festlegen von Telefonoptionen und-Nummern" <https://go.microsoft.com/fwlink/p/?linkid=210132> in der lync-Client Dokumentation auf der Microsoft Office-Website.</span><span class="sxs-lookup"><span data-stu-id="7213b-111">For the procedure to manually configure remote call control in Lync Server, see "Set Phones options and numbers" at <https://go.microsoft.com/fwlink/p/?linkid=210132> in the Lync client documentation on the Microsoft Office website.</span></span>

<span data-ttu-id="7213b-112">Wenn Sie über eine vorhandene Communications Server 2007 R2-oder Communications Server 2007-Bereitstellung verfügen, verwenden Communicator 2007 R2-und Communicator 2007-Clients weiterhin Gruppenrichtlinien während der parallelen Migration.</span><span class="sxs-lookup"><span data-stu-id="7213b-112">If you have an existing Communications Server 2007 R2 or Communications Server 2007 deployment, Communicator 2007 R2 and Communicator 2007 clients will continue to use Group Policy during side-by-side migration.</span></span> <span data-ttu-id="7213b-113">Wenn die Richtlinieneinstellungen jedoch auf lync-Clients übertragen werden sollen, müssen Sie die entsprechenden Einstellungen für lync Server-in-Band-Bereitstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7213b-113">However, if you want policy settings to carry over to Lync clients, you need to configure the equivalent Lync Server in-band provisioning settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7213b-114">Um einen Benutzer für die Remoteanrufsteuerung zu aktivieren, müssen Sie den Benutzer mit einem Leitungs-URI und einem Leitungs Server-URI versorgen.</span><span class="sxs-lookup"><span data-stu-id="7213b-114">To enable a user for remote call control, you need to provide the user with both a Line URI and a Line Server URI.</span></span> <span data-ttu-id="7213b-115">Wie unter <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Bereitstellungsaufgaben für die Remoteanrufsteuerung in lync Server 2013</A>beschrieben, müssen Sie sicherstellen, dass Sie die Syntax verwenden, die für das Gateway für diese Einstellungen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7213b-115">As described in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Deployment tasks for remote call control in Lync Server 2013</A>, you need to be sure to use the syntax that is required by the gateway for these settings.</span></span><BR><span data-ttu-id="7213b-116">Stellen Sie sicher, dass die Domäne im Linien Server-URI mit der Zieldomäne identisch ist, die Sie im MatchUri-Parameter angegeben haben, als Sie die statische Route zum Gateway konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="7213b-116">Be sure that the domain in the Line Server URI is the same as the destination domain that you specified in the MatchUri parameter when you configured the static route to the gateway.</span></span><BR><span data-ttu-id="7213b-117">Der Zeile-URI gibt die Telefonnummer an, die dem Benutzer im E. 164-Format mit dem Präfix "Tel:" zugewiesen wurde (beispielsweise Tel: + 14255550150).</span><span class="sxs-lookup"><span data-stu-id="7213b-117">The Line URI specifies the phone number assigned to the user in E.164 format, with the "TEL:" prefix (for example, tel:+14255550150).</span></span> <span data-ttu-id="7213b-118">Wenn Sie eine Durchwahlnummer konfigurieren möchten, lautet das Format Tel: + 14255550150; ext = 111.</span><span class="sxs-lookup"><span data-stu-id="7213b-118">If you want to configure an extension number, then the format is tel:+14255550150;ext=111.</span></span> <span data-ttu-id="7213b-119">Wenn Sie zuvor den URI des Benutzers konfiguriert haben und sich der Wert nicht geändert hat, müssen Sie den URI nicht angeben, wenn Sie den Benutzer für die Remoteanrufsteuerung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7213b-119">If you previously configured the user’s Line URI and the value has not changed, you do not need to specify the Line URI when you enable the user for remote call control.</span></span>



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a><span data-ttu-id="7213b-120">So aktivieren Sie die Remoteanrufsteuerung für lync-fähige Benutzer mithilfe der Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="7213b-120">To enable remote call control for Lync-enabled users by using Management Shell</span></span>

1.  <span data-ttu-id="7213b-121">Melden Sie sich bei einem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder als rollenbasierte zugriffssteuerungsrolle installiert ist, der Sie das Cmdlet " **Satz-CsUser** " zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="7213b-121">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or as a role-based access control role to which you have assigned the **Set-CsUser** cmdlet.</span></span>

2.  <span data-ttu-id="7213b-122">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="7213b-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7213b-123">Gehen Sie wie folgt vor, um das Cmdlet " **CsUser** " zum Konfigurieren der Remoteanrufsteuerung für einen vorhandenen lync-fähigen Benutzer zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="7213b-123">To use the **Set-CsUser** cmdlet to configure remote call control for an existing Lync-enabled user, do the following:</span></span>
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    <span data-ttu-id="7213b-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7213b-124">For example:</span></span>
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a><span data-ttu-id="7213b-125">So konfigurieren Sie Benutzer für die Remoteanrufsteuerung mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="7213b-125">To configure users for remote call control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7213b-126">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7213b-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7213b-127">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7213b-127">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7213b-128">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7213b-128">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7213b-129">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="7213b-129">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="7213b-130">Geben Sie im Feld **Benutzer suchen** alle (oder den ersten Teil) des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens, der SIP-Adresse oder des Uniform Resource Identifier (URI) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="7213b-130">In the **Search users** box, type all (or the first portion) of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="7213b-131">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="7213b-131">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="7213b-132">Klicken Sie im Menü **Bearbeiten** auf **ändern**.</span><span class="sxs-lookup"><span data-stu-id="7213b-132">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="7213b-133">Führen Sie in " **Telefonie**" eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="7213b-133">In **Telephony**, do one of the following:</span></span>
    
      - <span data-ttu-id="7213b-134">Klicken Sie auf **Remoteanrufsteuerung**, um die Remoteanrufsteuerung zu aktivieren, damit der Benutzer die Telefonanlage (Private Branch Exchange, PBX) von lync 2013 für PC-zu-PC-Audioanrufe und PC-zu-Telefon-Anrufe steuern kann.</span><span class="sxs-lookup"><span data-stu-id="7213b-134">To enable remote call control to enable the user to control their private branch exchange (PBX) phone from Lync 2013 to make PC-to-PC audio calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="7213b-135">Geben Sie in der **Zeile URI** die Telefonnummer des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="7213b-135">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="7213b-136">Geben Sie in der **Zeile Server-URI** den SIP-URI des SIP/CSTA-Gateways an.</span><span class="sxs-lookup"><span data-stu-id="7213b-136">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>
    
      - <span data-ttu-id="7213b-137">Um die Remoteanrufsteuerung zu aktivieren, aber PC-zu-PC-Audioanrufe zu deaktivieren und nur dem Benutzer die Steuerung seines PBX-Telefons von lync 2013 zu ermöglichen, um PC-zu-Telefon-Anrufe zu tätigen, klicken Sie **nur auf Remoteanrufsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="7213b-137">To enable remote call control, but disable PC-to-PC audio calls, and to enable only the user to control their PBX phone from Lync 2013 to make PC-to-phone calls, click **Remote call control only**.</span></span> <span data-ttu-id="7213b-138">Geben Sie in der **Zeile URI** die Telefonnummer des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="7213b-138">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="7213b-139">Geben Sie in der **Zeile Server-URI** den SIP-URI des SIP/CSTA-Gateways an.</span><span class="sxs-lookup"><span data-stu-id="7213b-139">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>

8.  <span data-ttu-id="7213b-140">Klicken Sie abschließend auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="7213b-140">When you are finished, click **Commit**.</span></span>

<span data-ttu-id="7213b-141"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="7213b-141"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

