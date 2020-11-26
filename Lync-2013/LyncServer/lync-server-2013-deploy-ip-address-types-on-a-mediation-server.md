---
title: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver'
description: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daa3be8d1ef12629dc185f98b95d2db0e565cf18
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49430234"
---
# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a><span data-ttu-id="d63da-103">Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d63da-103">Deploy IP address types on a Mediation Server for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="d63da-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="d63da-104">

<span> </span></span></span>

<span data-ttu-id="d63da-105">_**Letztes Änderungsdatum des Themas:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="d63da-105">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="d63da-106">Führen Sie mithilfe des Topologie-Generators die Schritte im folgenden Verfahren aus, um IP-Adresstypen auf einem Vermittlungs Server bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d63da-106">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="d63da-107">So stellen Sie IP-Adresstypen auf einem Vermittlungsserver bereit</span><span class="sxs-lookup"><span data-stu-id="d63da-107">To deploy IP address types on a Mediation Server</span></span>

  - <span data-ttu-id="d63da-108">Klicken Sie im Topologie-Generator unter **Vermittlungs Pools** mit der rechten Maustaste auf den Server in einem Pool, und wählen Sie dann **Eigenschaften bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="d63da-108">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="d63da-109">(Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)</span><span class="sxs-lookup"><span data-stu-id="d63da-109">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

  - <span data-ttu-id="d63da-p102">Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** den IP-Adressentyp, den Sie konfigurieren möchten. Wählen Sie für eine Dualstapel-Konfiguration wie in der folgenden Abbildung zu sehen **IPv4 aktivieren** und **IPv6 aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="d63da-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="d63da-112">**Das Dialogfeld „Eigenschaften bearbeiten“ für den Vermittlungsserverpool**</span><span class="sxs-lookup"><span data-stu-id="d63da-112">**Edit Properties dialog box for the Mediation Server pool**</span></span>
    
    <span data-ttu-id="d63da-113">![Seite "Allgemeine Eigenschaften" von lync Server mit FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Seite "Allgemeine Eigenschaften" von lync Server mit FQDN")</span><span class="sxs-lookup"><span data-stu-id="d63da-113">![Lync Server general properties page with FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server general properties page with FQDN")</span></span>
    
      - <span data-ttu-id="d63da-p103">**Alle konfigurierten IP-Adressen verwenden**. Wählen Sie diese Option, wenn Sie zulassen möchten, dass eine beliebige auf dem Computer festgelegte IP-Adresse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d63da-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d63da-116">Diese Option wird für IP Version 6-Konfigurationen (IPv6) empfohlen.</span><span class="sxs-lookup"><span data-stu-id="d63da-116">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="d63da-p104">**Dienstverwendung auf ausgewählte IP-Adressen begrenzen**. Wählen Sie diese Option, um eine spezifische Adresse zur Verwendung auf dem neuen Server anzugeben. Wenn Sie diese Option auswählen, müssen Sie einen Wert für „Primäre IP-Adresse“ angeben.</span><span class="sxs-lookup"><span data-stu-id="d63da-p104">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>
    
      - <span data-ttu-id="d63da-p105">**Primäre IP-Adresse**. Geben Sie eine IP-Adresse an, die der Server für sämtliche Kommunikationsvorgänge mit Ausnahme der PSTN (Public Switched Telephone Network, Telefonfestnetz)-Kommunikation verwendet. Die eingegebene IP-Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d63da-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="d63da-123">**PSTN-IP-Adresse**.</span><span class="sxs-lookup"><span data-stu-id="d63da-123">**PSTN IP address**.</span></span> <span data-ttu-id="d63da-124">Definieren Sie eine PSTN-IP-Adresse, wenn ein Vermittlungs Server eigenständig ist.</span><span class="sxs-lookup"><span data-stu-id="d63da-124">Define a PSTN IP address when a Mediation Server is standalone.</span></span> <span data-ttu-id="d63da-125">Diese Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d63da-125">This address must match the format of the selected address type.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d63da-126">Die Installation zusätzlicher Netzwerkschnittstellenkarten (NIC) s zur Unterstützung der Konfiguration der PSTN-IP-Adresse für lync Server 2013 wird in den Serverrollen für festgestellten Vermittlungsserver nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d63da-126">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="d63da-127">Weitere Informationen zu unterstützten NIC-Konfigurationen für lync Server 2013 finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Server Hardwareplattformen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d63da-127">For more information about supported NIC configurations for Lync Server 2013, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>

        
        <span data-ttu-id="d63da-128"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="d63da-128"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

