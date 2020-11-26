---
title: 'Lync Server 2013: Löschen einer Archivierungskonfiguration'
description: 'Lync Server 2013: Löschen einer Archivierungskonfiguration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bb267c119b49c9bbf06f365c3bdf2cbab459628
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49430378"
---
# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a><span data-ttu-id="03de0-103">Löschen einer Archivierungskonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03de0-103">Deleting an Archiving configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="03de0-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="03de0-104">

<span> </span></span></span>

<span data-ttu-id="03de0-105">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="03de0-105">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="03de0-106">Sie können eine Websitekonfiguration oder Poolkonfiguration löschen.</span><span class="sxs-lookup"><span data-stu-id="03de0-106">You can delete a site configuration or pool configuration.</span></span> <span data-ttu-id="03de0-107">Die globale Konfiguration kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="03de0-107">The global configuration cannot be removed.</span></span> <span data-ttu-id="03de0-108">Wenn Sie die globale Konfiguration löschen, wird sie automatisch auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="03de0-108">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="03de0-109">Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="03de0-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a><span data-ttu-id="03de0-110">So löschen Sie eine Website-oder Poolkonfiguration für die Archivierung</span><span class="sxs-lookup"><span data-stu-id="03de0-110">To delete a site or pool configuration for archiving</span></span>

1.  <span data-ttu-id="03de0-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="03de0-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03de0-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="03de0-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="03de0-113">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="03de0-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="03de0-114">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="03de0-114">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="03de0-115">Klicken Sie in der Liste der Archivierungskonfigurationen auf die zu löschende Standort- oder Poolkonfiguration, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="03de0-115">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="03de0-116">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="03de0-116">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="03de0-117">Entfernen von Archivierungs Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="03de0-117">Removing Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="03de0-118">Die Archivierungs Konfigurationseinstellungen können mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsArchivingConfiguration** gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="03de0-118">Archiving configuration settings can be deleted by using Windows PowerShell and the **Remove-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="03de0-119">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="03de0-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="03de0-120">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="03de0-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a><span data-ttu-id="03de0-121">So entfernen Sie eine bestimmte Sammlung von Archivierungs Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="03de0-121">To remove a specified collection of archiving configuration settings</span></span>

  - <span data-ttu-id="03de0-122">Mit dem folgenden Befehl werden die auf die Redmond-Website angewendeten Archivierungs Konfigurationseinstellungen entfernt:</span><span class="sxs-lookup"><span data-stu-id="03de0-122">The following command removes the archiving configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="03de0-123">So entfernen Sie alle auf den Website Bereich angewendeten Archivierungs Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="03de0-123">To remove all the archiving configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="03de0-124">Mit diesem Befehl werden alle auf den Dienstbereich angewendeten Archivierungs Konfigurationseinstellungen entfernt:</span><span class="sxs-lookup"><span data-stu-id="03de0-124">This command removes all the archiving configuration settings applied to the service scope:</span></span>
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a><span data-ttu-id="03de0-125">So entfernen Sie Archivierungs Konfigurationseinstellungen auf Grundlage eines angegebenen Eigenschaftswerts</span><span class="sxs-lookup"><span data-stu-id="03de0-125">To remove archiving configuration settings based on a specified property value</span></span>

  - <span data-ttu-id="03de0-126">Mit diesem Befehl werden alle Archivierungs Konfigurationseinstellungen entfernt, bei denen die Exchange-Archivierung deaktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="03de0-126">This command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

<span data-ttu-id="03de0-127">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="03de0-127">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="03de0-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03de0-128">See Also</span></span>


[<span data-ttu-id="03de0-129">Funktionsweise der Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03de0-129">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="03de0-130">Verwalten der Archivierung interner und externer Kommunikation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03de0-130">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

<span data-ttu-id="03de0-131"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="03de0-131"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

