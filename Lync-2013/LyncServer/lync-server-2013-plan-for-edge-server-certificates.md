---
title: 'Lync Server 2013: Planen von Edgeserver-Zertifikaten'
description: 'Lync Server 2013: Planen von Edgeserver-Zertifikaten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22ec3743256fe3e4c55dba0f6357a85b1ad81cd0
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437136"
---
# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>Planen von Edgeserver-Zertifikaten in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-05_

Die Zertifikaterstellung für Edge wird in lync Server 2013 vereinfacht.

**Flussdiagramm für Zertifikate für Edgeserver**

![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")

Erstellen Sie ein einzelnes öffentliches Zertifikat, stellen Sie sicher, dass für das Zertifikat ein exportierbarer privater Schlüssel definiert ist, und weisen Sie ihn mithilfe des Zertifikat-Assistenten den folgenden Edge-Server-externen Schnittstellen zu:

<div>


> [!IMPORTANT]  
> Platzhalterzertifikate werden in lync Server nicht unterstützt, es sei denn, es wird verwendet, um die einfachen URLs über den Reverse-Proxy zusammenzufassen. Sie müssen für jeden SIP-Domänennamen, Webkonferenz-Edgedienst, A/V-Edgedienst und die von Ihrer Bereitstellung angebotene XMPP-Domäne eindeutige Subject Alternate Names (SANs) definieren.



</div>

<div>


> [!NOTE]  
> In lync Server 2013 eingeführt, erfordert das Staging von Audio/Video-Authentifizierungszertifikaten im Vorfeld der Ablaufzeit des aktuellen Zertifikats einige zusätzliche Planungsschritte. Anstelle eines Zertifikats mit mehreren Zwecken für die externe Edge-Schnittstelle benötigen Sie zwei Zertifikate, eine dem Access Edge-Dienst und dem Webkonferenz-Edgedienst zugewiesene Zertifikate sowie ein Zertifikat für den A/V-Edgedienst. Weitere Informationen finden Sie unter <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging von AV-und OAuth-Zertifikaten in lync Server 2013 using-Rolle in der Gruppe-CsCertificate</A>



</div>

<div>


> [!IMPORTANT]  
> Im Fall eines Pools von Edgeserver exportieren Sie das Zertifikat mit dem privaten Schlüssel zu jedem Edgeserver, und weisen Sie das Zertifikat jedem Edgeserver-Dienst zu. Führen Sie dasselbe für das interne Edgeserver-Zertifikat aus, exportieren Sie das Zertifikat mit dem privaten Schlüssel, und weisen Sie jeder internen Schnittstelleeine Zuordnung zu.



</div>

  - Stellen Sie sicher, dass für das Zertifikat ein exportierbarer privater Schlüssel zugewiesen ist.

  - Access-Edgedienst (als **SIP-Access-Edge extern** im Zertifikat-Assistenten bezeichnet)

  - Webkonferenz-Edgedienst (wird als **Webkonferenz Edge extern** im Zertifikat-Assistenten bezeichnet)

  - A/v-Authentifizierungsdienst (im Zertifikat-Assistenten als **extern** bezeichnet)

Erstellen Sie ein einzelnes internes Zertifikat mit exportier barem privaten Schlüssel, kopieren Sie es, und weisen Sie es jeder der Edge-Server-internen Schnittstellen zu:

  - Edgeserver (im Zertifikat-Assistenten als " **Edge-intern** " bezeichnet)

<div>


> [!IMPORTANT]  
> Es ist möglich, getrennte und unterschiedliche Zertifikate für jeden Edgeserver-Dienst zu verwenden. Ein guter Grund, getrennte Zertifikate zu wählen, ist, wenn Sie das neue Feature für das parallele Zertifikat für das A/V-Edgedienst Zertifikat verwenden möchten. Im Fall dieser Funktion empfiehlt es sich, das A/V-Edgedienst-Zertifikat vom Edgedienst für den Access-Edgedienst und dem Webkonferenz-Edgedienst zu entkoppeln. Wenn Sie sich entscheiden, für jeden Dienst separate Zertifikate anzufordern, zu erwerben und zuzuweisen, müssen Sie anfordern, dass der private Schlüssel für den a/v-Edgedienst exportierbar ist (Dies ist wiederum der a/v-Authentifizierungsdienst), und weisen Sie dem a/v-Edge-externen Interface auf jedem Edgeserver dasselbe Zertifikat zu.



</div>

<div>

## <a name="see-also"></a>Siehe auch


[Staging von AV-und OAuth-Zertifikaten in lync Server 2013 using-Rolle in der Gruppe-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[Änderungen in Lync Server 2013, die die Planung für Edgeserver betreffen](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

