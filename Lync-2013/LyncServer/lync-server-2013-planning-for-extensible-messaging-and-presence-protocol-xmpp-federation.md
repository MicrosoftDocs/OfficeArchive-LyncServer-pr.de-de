---
title: Planen des Extensible Messaging and Presence Protocol (XMPP)-Verbunds
description: Planen des Extensible Messaging and Presence Protocol (XMPP)-Verbunds
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 511273b69181334821f446bcc4424641367ecf51
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49424569"
---
# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="3ca44-103">Planen der erweiterbaren Messaging-und Anwesenheits Protokoll (XMPP)-Föderation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ca44-103">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="3ca44-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="3ca44-104">

<span> </span></span></span>

<span data-ttu-id="3ca44-105">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="3ca44-105">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="3ca44-106">In früheren Versionen von lync Server und Office Communications Server wurde ein Extensible Messaging and Presence Protocol (XMPP)-Gateway bereitgestellt, das als separate Server Rolle bereitgestellt werden kann, um die Föderation mit XMPP-Bereitstellungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3ca44-106">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="3ca44-107">In Microsoft lync Server 2013 kann die XMPP-Funktion als Feature bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3ca44-107">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="3ca44-108">Die XMPP-Funktionalität ist in zwei Teilen installiert: ein XMPP-Proxy, der auf dem Edgeserver ausgeführt wird, und das XMPP-Gateway, das auf den Front-End-Servern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3ca44-108">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="3ca44-109">Die Bereitstellung und Konfiguration von XMPP wird unter [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) , die Sie zur Unterstützung von xmpp in Ihrer Organisation planen, durch Definieren von Port-und Protokollregeln für Ihre Firewall, Konfiguration von Zertifikaten und Hinzufügen von DNS-Einträgen abgedeckt.</span><span class="sxs-lookup"><span data-stu-id="3ca44-109">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="3ca44-110">In den folgenden Themen in diesem Abschnitt werden die Informationen zusammengefasst, die Sie benötigen, um die XMPP-Föderation für Ihre Bereitstellung erfolgreich zu planen.</span><span class="sxs-lookup"><span data-stu-id="3ca44-110">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3ca44-p103">Die XMPP-Fähigkeit von Lync Server 2013 wird von Microsoft für den Instant-Messaging-Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich bei anderen XMPP-Systemen an den Drittanbieter, um zu überprüfen, ob dieser den Partnerverbund mit Lync Server 2013 unterstützt, und Empfehlungen bei Bereitstellung und Problembehandlung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3ca44-p103">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3ca44-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3ca44-113">In This Section</span></span>

  - [<span data-ttu-id="3ca44-114">Zertifikatzusammenfassung – Extensible Messaging and Presence Protocol (XMPP) Federation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ca44-114">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="3ca44-115">Port Zusammenfassung – Extensible Messaging and Presence Protocol (XMPP) Federation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ca44-115">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="3ca44-116">DNS Summary – Extensible Messaging and Presence Protocol (XMPP) Federation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ca44-116">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ca44-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ca44-117">See Also</span></span>


[<span data-ttu-id="3ca44-118">Einrichten eines XMPP-Partnerverbunds in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ca44-118">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="3ca44-119">Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ca44-119">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[<span data-ttu-id="3ca44-120">Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ca44-120">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
<span data-ttu-id="3ca44-121">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ca44-121">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>  
<span data-ttu-id="3ca44-122">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ca44-122">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>  
<span data-ttu-id="3ca44-123">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ca44-123">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>  
  

<span data-ttu-id="3ca44-124"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="3ca44-124"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

