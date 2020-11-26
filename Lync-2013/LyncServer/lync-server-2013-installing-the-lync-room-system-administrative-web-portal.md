---
title: 'Lync Server 2013: Installieren des lync Room System administrative Web Portals'
description: 'Lync Server 2013: Installieren des administrativen lync Room System-Webportals.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fba239346d75142bb4009c58e0ac67e8e1f3bcb
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427005"
---
# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="00513-103">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00513-103">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="00513-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="00513-104">

<span> </span></span></span>

<span data-ttu-id="00513-105">_**Letztes Änderungsdatum des Themas:** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="00513-105">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="00513-106">Sie können das administrative Webportal für Microsoft lync Room System aus dem Microsoft Download Center unter herunterladen [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044) .</span><span class="sxs-lookup"><span data-stu-id="00513-106">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="00513-107">Führen Sie die folgenden Schritte aus, um das lync Room System administrative Web Portal zu installieren.</span><span class="sxs-lookup"><span data-stu-id="00513-107">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="00513-108">Konfigurieren Sie den Port für vertrauenswürdige Anwendungen, indem Sie das folgende Cmdlet in der lync Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="00513-108">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="00513-109">Zum Installieren des Besprechungsraum-Portals laden Sie **LyncRoomAdminPortal.exe** herunter, und führen Sie es dann als Administrator aus.</span><span class="sxs-lookup"><span data-stu-id="00513-109">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="00513-110">Öffnen Sie die Datei Web.config aus folgendem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="00513-110">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="00513-111">% Program Files% \\ Microsoft lync Server 2013 \\ Webkomponenten \\ Besprechungsraum-Portal \\ int- \\ Handler</span><span class="sxs-lookup"><span data-stu-id="00513-111">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="00513-112">Ändern Sie in der Web.Config-Datei die PortalUserName in den in Schritt 2 erstellten Benutzernamen im Abschnitt "Konfigurieren von Voraussetzungen für das lync Room System Admin Portal" (der empfohlene Name im Schritt lautet LRSApp):</span><span class="sxs-lookup"><span data-stu-id="00513-112">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="00513-113">Da das LRS-Administrator Portal eine vertrauenswürdige Anwendung ist, müssen Sie das Kennwort nicht in der Portalkonfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="00513-113">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="00513-114">Wenn für diesen Benutzer nicht die lokale Registrierungsstelle, sondern eine andere Registrierungsstelle verwendet wird, müssen Sie diese für den Benutzer angeben, indem Sie folgende Zeile in die Datei Web.Config einfügen:</span><span class="sxs-lookup"><span data-stu-id="00513-114">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="00513-115">Wenn der verwendete Port nicht der Port 5061 ist, fügen Sie folgende Zeile in die Datei Web.Config ein: </span><span class="sxs-lookup"><span data-stu-id="00513-115">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="00513-116">Überprüfen der Installation des lync Room System administrative Web Portals</span><span class="sxs-lookup"><span data-stu-id="00513-116">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="00513-117">Gehen Sie wie folgt vor, um die Installation des lync Room System administrative Web Portals zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="00513-117">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="00513-118">Navigieren Sie auf einem Front-End-Server zur folgenden URL:</span><span class="sxs-lookup"><span data-stu-id="00513-118">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="00513-119"> https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="00513-119">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="00513-120">Sie sollten keine Fehler sehen (siehe folgende Abbildung):</span><span class="sxs-lookup"><span data-stu-id="00513-120">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="00513-121">![Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems")</span><span class="sxs-lookup"><span data-stu-id="00513-121">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="00513-122">Wenn Sie keine Fehler sehen, versuchen Sie, über einen anderen Computer in der Topologie auf die folgende URL zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="00513-122">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="00513-123"> https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="00513-123">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="00513-124">Wenn Sie auf die Seite zugreifen möchten, müssen Sie die DNS-Einträge hinzufügen, wie unter "erforderliche DNS-Einträge für die automatische Client Anmeldung" beschrieben ist [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056) .</span><span class="sxs-lookup"><span data-stu-id="00513-124">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

<span data-ttu-id="00513-125"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="00513-125"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

