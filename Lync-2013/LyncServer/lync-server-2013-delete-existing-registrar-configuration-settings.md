---
title: 'Lync Server 2013: Löschen vorhandener Registrierungs Konfigurationseinstellungen'
description: 'Lync Server 2013: Löschen vorhandener Registrierungs Konfigurationseinstellungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b625b97724edf0ecf8928ec31d89a6166230c4c7
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49430455"
---
# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="13a14-103">Löschen vorhandener Registrierungs Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13a14-103">Delete existing Registrar configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="13a14-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="13a14-104">

<span> </span></span></span>

<span data-ttu-id="13a14-105">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="13a14-105">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="13a14-106">Führen Sie die folgenden Schritte aus, um eine Registrierungsstelle zu löschen.</span><span class="sxs-lookup"><span data-stu-id="13a14-106">Follow these steps to delete a Registrar.</span></span>

<div>

## <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="13a14-107">So löschen Sie Registrierungsstellenkonfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="13a14-107">To delete Registrar configuration settings</span></span>

1.  <span data-ttu-id="13a14-108">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="13a14-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="13a14-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="13a14-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="13a14-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="13a14-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="13a14-111">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierungsstelle**.</span><span class="sxs-lookup"><span data-stu-id="13a14-111">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="13a14-112">Geben Sie auf der Seite **Registrierungsstelle** in das Suchfeld den vollständigen oder teilweisen Namen der Registrierungsstelle ein, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="13a14-112">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>

5.  <span data-ttu-id="13a14-113">Klicken Sie in der Liste auf die gewünschte Registrierungsstelle, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="13a14-113">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="13a14-114">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="13a14-114">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="13a14-115">Entfernen von Registrierungsstellen-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="13a14-115">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="13a14-116">Sie können die Konfigurationseinstellungen der Registrierungsstelle mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsProxyConfiguration** löschen.</span><span class="sxs-lookup"><span data-stu-id="13a14-116">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="13a14-117">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="13a14-117">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="13a14-118">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="13a14-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="13a14-119">So entfernen Sie eine bestimmte Gruppe mit Registrierungsstellensicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="13a14-119">To remove a specific set of Registrar security settings</span></span>

  - <span data-ttu-id="13a14-120">Mithilfe des folgenden Befehls werden die auf den Edgeserver „atl-edge-011.litwareinc.com“ angewendeten Sicherheitseinstellungen für die Registrierungsstelle entfernt:</span><span class="sxs-lookup"><span data-stu-id="13a14-120">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="13a14-121">So entfernen Sie alle Sicherheitseinstellungen für die Registrierungsstelle, die auf den Standortbereich angewendet werden</span><span class="sxs-lookup"><span data-stu-id="13a14-121">To remove all of the Registrar security settings applied to the site scope</span></span>

  - <span data-ttu-id="13a14-122">Mithilfe des folgenden Befehls werden alle auf den Registrierungsstellendienst angewendeten Sicherheitseinstellungen für die Registrierungsstelle entfernt:</span><span class="sxs-lookup"><span data-stu-id="13a14-122">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="13a14-123">So entfernen Sie alle Sicherheitseinstellungen für die Registrierungsstelle, die die NTLM-Authentifizierung zulassen</span><span class="sxs-lookup"><span data-stu-id="13a14-123">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

  - <span data-ttu-id="13a14-124">Mithilfe des folgenden Befehls werden alle Sicherheitseinstellungen für die Registrierungsstelle gelöscht, die die Verwendung von NTLM für die Clientauthentifizierung zulassen:</span><span class="sxs-lookup"><span data-stu-id="13a14-124">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

<span data-ttu-id="13a14-125">Ausführliche Informationen finden Sie unter [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span><span class="sxs-lookup"><span data-stu-id="13a14-125">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span></span>

<span data-ttu-id="13a14-126"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="13a14-126"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

