---
title: 'Lync Server 2013: Erstellen neuer Webdienst-Konfigurationseinstellungen'
description: 'Lync Server 2013: Erstellen neuer Webdienst-Konfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc66b0c8f394260fbe30e444f800640c774b6bcf
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431890"
---
# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="a6f14-103">Erstellen neuer Webdienst-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-103">Create new Web Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="a6f14-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="a6f14-104">

<span> </span></span></span>

<span data-ttu-id="a6f14-105">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a6f14-105">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a6f14-106">Sie können die **Webdienst** Seite verwenden, um die Authentifizierungsmethoden für den Zugriff auf lync Server 2013-Verwandte Webserver und Webdienste zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a6f14-106">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="a6f14-107">Führen Sie die folgenden Schritte aus, um eine neue Webdienstrichtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a6f14-107">Follow these steps to create a new Web Service policy.</span></span>

<div>

## <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="a6f14-108">So erstellen Sie neue Webdienst-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="a6f14-108">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="a6f14-109">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="a6f14-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="a6f14-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a6f14-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a6f14-111">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a6f14-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a6f14-112">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.</span><span class="sxs-lookup"><span data-stu-id="a6f14-112">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="a6f14-113">Klicken Sie auf der Seite **Webdienst** auf **Neu** und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a6f14-113">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="a6f14-p102">Zum Konfigurieren des Webdiensts für einen Standort klicken Sie auf **Standortkonfiguration**. Klicken Sie in **Standort auswählen** auf den Standort, auf den die Webdienstrichtlinie angewendet werden soll, und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6f14-p102">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
      - <span data-ttu-id="a6f14-p103">Zum Konfigurieren des Webdiensts für einen Pool klicken Sie auf **Poolkonfiguration**. Klicken Sie in **Dienst auswählen** auf den Dienst, auf den die Webdienstrichtlinie angewendet werden soll, und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6f14-p103">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span>

5.  <span data-ttu-id="a6f14-118">Wählen Sie im Abschnitt **Neue Webdiensteinstellung** unter **Integrierte Windows-Authentifizierung** die Option **Aushandeln**, **Integrierte Windows-Authentifizierung** oder **Keine** aus.</span><span class="sxs-lookup"><span data-stu-id="a6f14-118">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="a6f14-119">Wählen Sie je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung eine oder mehrere der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a6f14-119">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="a6f14-120">**PIN-Authentifizierung aktivieren**: Clients werden über eine PIN authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="a6f14-120">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="a6f14-121">**Zertifikatauthentifizierung aktivieren**: Die Server im Pool stellen Zertifikate an Clients aus.</span><span class="sxs-lookup"><span data-stu-id="a6f14-121">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="a6f14-122">**Download einer Zertifikatkette aktivieren**: Server können die Zertifikatkette für das jeweilige Zertifikat herunterladen.</span><span class="sxs-lookup"><span data-stu-id="a6f14-122">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="a6f14-123">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a6f14-123">Click **Commit**.</span></span>

<span data-ttu-id="a6f14-124"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="a6f14-124"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

