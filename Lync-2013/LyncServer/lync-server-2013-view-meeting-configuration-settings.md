---
title: 'Lync Server 2013: Anzeigen von Einstellungen für die besprechungskonfiguration'
description: 'Lync Server 2013: Anzeigen der Einstellungen für die besprechungskonfiguration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190b9d331a8cd0a08e17c482dbc3b0bc27590003
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49446976"
---
# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="62a18-103">Anzeigen von Einstellungen für die besprechungskonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62a18-103">View meeting configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="62a18-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="62a18-104">

<span> </span></span></span>

<span data-ttu-id="62a18-105">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="62a18-105">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="62a18-106">In der lync Server 2013-Systemsteuerung verwenden Sie die Einstellung für die besprechungskonfiguration, um zu steuern, wie Besprechungen in Ihrer Bereitstellung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="62a18-106">In Lync Server 2013 Control Panel, you use meeting configuration setting to control how meetings are implemented in your deployment.</span></span> <span data-ttu-id="62a18-107">Dies umfasst die folgenden Besprechungs Konfigurationen:</span><span class="sxs-lookup"><span data-stu-id="62a18-107">This includes the following meeting configurations:</span></span>

  - <span data-ttu-id="62a18-108">Eine globale Konfiguration, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="62a18-108">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="62a18-109">Optionale Konfigurationen auf Websiteebene und auf Benutzerebene, die Sie erstellen und verwenden können, um anzugeben, wie Besprechungen für bestimmte Websites oder Benutzer implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="62a18-109">Optional site-level and user-level configurations that you can create and use to specify how meetings are implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-meeting-configuration-settings"></a><span data-ttu-id="62a18-110">So zeigen Sie die Einstellungen für die besprechungskonfiguration an</span><span class="sxs-lookup"><span data-stu-id="62a18-110">To view meeting configuration settings</span></span>

1.  <span data-ttu-id="62a18-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="62a18-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62a18-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="62a18-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="62a18-113">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="62a18-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="62a18-114">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** , und klicken Sie dann auf **besprechungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="62a18-114">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="62a18-115">Klicken Sie auf der Seite **Besprechungskonfiguration** auf die Besprechungskonfiguration, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="62a18-115">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>

5.  <span data-ttu-id="62a18-116">Wählen Sie im **Filter Datei bearbeiten** die Option **Details anzeigen aus.**</span><span class="sxs-lookup"><span data-stu-id="62a18-116">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="62a18-117">Aktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="62a18-117">check box.</span></span>
    
    <span data-ttu-id="62a18-118">**Bearbeiten der besprechungskonfiguration \<policy\> –** Öffnet die Anzeige der Einstellungen für die ausgewählte Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="62a18-118">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="62a18-119">Details zum Konfigurieren der Einstellungen finden Sie unter [erstellen oder Ändern einer Sammlung von Einstellungen für die besprechungskonfiguration in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="62a18-119">For details about configuring the settings, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span>

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="62a18-120">Anzeigen von Informationen zur besprechungskonfiguration mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="62a18-120">Viewing Meeting Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="62a18-121">Die Einstellungen für die besprechungskonfiguration können mithilfe von Windows PowerShell und dem Cmdlet Get-CsMeetingConfiguration angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="62a18-121">Meeting configuration settings can be viewed by using Windows PowerShell and the Get-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="62a18-122">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="62a18-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="62a18-123">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="62a18-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-meeting-configuration-information"></a><span data-ttu-id="62a18-124">So zeigen Sie die Informationen zur besprechungskonfiguration an</span><span class="sxs-lookup"><span data-stu-id="62a18-124">To view meeting configuration information</span></span>

  - <span data-ttu-id="62a18-125">Wenn Sie Informationen zu allen Besprechungs Konfigurationseinstellungen anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="62a18-125">To view information about all your meeting configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsMeetingConfiguration
    
    <span data-ttu-id="62a18-126">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="62a18-126">That will return information similar to this:</span></span>
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

<span data-ttu-id="62a18-127">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="62a18-127">For more information, see the help topic for the [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet.</span></span>

<span data-ttu-id="62a18-128"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="62a18-128"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

