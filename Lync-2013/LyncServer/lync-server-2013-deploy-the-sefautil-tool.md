---
title: 'Lync Server 2013: Bereitstellen des SEFAUtil-Tools'
description: 'Lync Server 2013: Bereitstellen des SEFAUtil-Tools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 311f14f33dff30b388836a7f02483c4afe5da1b1
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49430154"
---
# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="8ac71-103">Deploy the SEFAUtil tool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ac71-103">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="8ac71-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="8ac71-104">

<span> </span></span></span>

<span data-ttu-id="8ac71-105">_**Letztes Änderungsdatum des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="8ac71-105">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="8ac71-106">Zum Bereitstellen und Verwalten der Gruppenanruf Abholung müssen Sie das SEFAUtil Resource Kit-Tool verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ac71-106">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="8ac71-107">Das Tool ist Teil der lync Server 2013 Resource Kit-Tools.</span><span class="sxs-lookup"><span data-stu-id="8ac71-107">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="8ac71-108">Bevor Sie SEFAUtil installieren können, müssen Sie über einen vertrauenswürdigen Anwendungspool in Ihrer Topologie verfügen, SEFAUtil als vertrauenswürdige Anwendung angeben und die Topologie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8ac71-108">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8ac71-109">Das Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK muss auf jedem Computer installiert sein, auf dem Sie das SEFAUtil-Tool ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="8ac71-109">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="8ac71-110">Sie können die SEFAUtil in einem beliebigen Front-End-Pool in Ihrer Bereitstellung ausführen.</span><span class="sxs-lookup"><span data-stu-id="8ac71-110">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ac71-111">Weitere Informationen zum Ausführen von SEFAUtil finden Sie im TechNet-Blog Artikel "wie erhalte ich SEFAUtil?"</span><span class="sxs-lookup"><span data-stu-id="8ac71-111">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="8ac71-112">bei <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A> .</span><span class="sxs-lookup"><span data-stu-id="8ac71-112">at <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="8ac71-113">So stellen Sie das SEFAUtil-Tool bereit</span><span class="sxs-lookup"><span data-stu-id="8ac71-113">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="8ac71-114">Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8ac71-114">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8ac71-115">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="8ac71-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8ac71-116">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem vertrauenswürdigen Anwendungspool gehört.</span><span class="sxs-lookup"><span data-stu-id="8ac71-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="8ac71-117">Falls erforderlich, definieren Sie einen vertrauenswürdigen Anwendungspool für den Front-End-Pool, in dem Sie SEFAUtil ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="8ac71-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="8ac71-118">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8ac71-118">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="8ac71-p104">Definieren Sie das SEFAUtil-Tool als eine vertrauenswürdige Anwendung. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8ac71-p104">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ac71-121">Sie können ggf. einen anderen Port verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ac71-121">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="8ac71-p105">Aktivieren Sie die Topologie mit Ihren Änderungen. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8ac71-p105">Enable the topology with your changes. At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="8ac71-124">Installieren Sie die lync Server 2013 Resource Kit-Tools auf einem Front-End-Server, der sich in dem vertrauenswürdigen Anwendungspool befindet, den Sie in Schritt 3 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="8ac71-124">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="8ac71-125">Gehen Sie wie folgt vor, um sicherzustellen, dass Ihr SEFAUtil-Tool korrekt ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="8ac71-125">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="8ac71-126">Führen Sie das Tool an der Windows-Eingabeaufforderung mit Administratorberechtigungen aus, um die Anrufweiterleistungseinstellungen eines Benutzers in Ihrer Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8ac71-126">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8ac71-127">Das Tool befindet sich unter \Programme\Microsoft lync Server 2013 \ reskit.</span><span class="sxs-lookup"><span data-stu-id="8ac71-127">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="8ac71-p106">Zeigen Sie die Anrufweiterleitungseinstellungen eines Benutzers an. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8ac71-p106">Display the call forwarding settings of a user. At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="8ac71-130">Die Anrufweiterleitungseinstellungen für den Benutzer werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ac71-130">The call forwarding settings for the user will be displayed.</span></span>

<span data-ttu-id="8ac71-131"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="8ac71-131"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

