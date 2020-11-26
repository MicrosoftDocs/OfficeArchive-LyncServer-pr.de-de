---
title: 'Lync Server 2013: Entfernen der Kerberos-Authentifizierung aus einem Standort'
description: 'Lync Server 2013: Entfernen der Kerberos-Authentifizierung von einer Website.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a3d9100d07d37e98800cfce106bc75fcfaeaa59
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49436384"
---
# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="8e81a-103">Entfernen der Kerberos-Authentifizierung aus einem Standort in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e81a-103">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="8e81a-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="8e81a-104">

<span> </span></span></span>

<span data-ttu-id="8e81a-105">_**Letztes Änderungsdatum des Themas:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="8e81a-105">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="8e81a-106">Um dieses Verfahren erfolgreich abzuschließen, sollten Sie als Benutzer angemeldet sein, der Mitglied der RTCUniversalServerAdmins-Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="8e81a-106">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="8e81a-107">Wenn Sie die Kerberos-Authentifizierung von einer Website entfernen oder eine Website zurückziehen müssen, müssen Sie die Kerberos-Authentifizierungs Konto Zuweisung von der Website mithilfe des Cmdlets **Remove-CsKerberosAccountAssignment** entfernen.</span><span class="sxs-lookup"><span data-stu-id="8e81a-107">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="8e81a-108">Gehen Sie wie folgt vor, um die Kerberos-Authentifizierungs Kontozuordnung zu entfernen, wodurch die Zuordnung von allen Computern auf der Website entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="8e81a-108">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="8e81a-109">Wenn Sie das Kerberos-fähige Konto endgültig zurückziehen, sollten Sie Active Directory-Benutzer und-Computer verwenden, um es aus Active Directory-Domänendiensten zu löschen, nachdem Sie die Aufgabe entfernt haben.</span><span class="sxs-lookup"><span data-stu-id="8e81a-109">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="8e81a-110">Wenn Sie beabsichtigen, das Objekt in Zukunft zu verwenden, sollten Sie das Active Directory-Objekt behalten.</span><span class="sxs-lookup"><span data-stu-id="8e81a-110">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="8e81a-111">So entfernen Sie die Kerberos-Authentifizierung von einer Website</span><span class="sxs-lookup"><span data-stu-id="8e81a-111">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="8e81a-112">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe an einem Computer in der Domäne mit lync Server 2013 oder auf einem Computer an, auf dem die Verwaltungstools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="8e81a-112">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="8e81a-113">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="8e81a-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8e81a-114">Führen Sie in der Befehlszeile die beiden folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="8e81a-114">From the command line, run the following two commands:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="8e81a-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8e81a-115">For example:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8e81a-116">Nachdem Sie die Kerberos-Authentifizierung geändert haben, beispielsweise ein Konto hinzugefügt oder ein Konto entfernt haben, müssen Sie <STRONG>enable-CsTopology</STRONG> über die Eingabeaufforderung der lync Server-Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="8e81a-116">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    <span data-ttu-id="8e81a-117"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="8e81a-117"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

