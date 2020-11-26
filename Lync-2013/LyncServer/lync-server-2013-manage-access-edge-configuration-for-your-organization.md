---
title: 'Lync Server 2013: Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation'
description: 'Lync Server 2013: Verwalten der Access-Edge-Konfiguration für Ihre Organisation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2161385f9c03f025bcf6f5e599b7e0276f6d592c
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49426137"
---
# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Diese Dokumentation ist vorläufig und kann geändert werden. Leere Themen sind als Platzhalter enthalten.

Nachdem Sie einen oder mehrere Edgeserver bereitgestellt haben, müssen Sie die Typen des externen Domänen-oder Anbieter Zugriffs, den Remotebenutzerzugriff und den anonymen Benutzer Zugriff auf Konferenzen über die Edgeserver aktivieren, die für Ihre Organisation unterstützt werden.

Zu diesen Optionen gehören die folgenden Zugriffsarten, die über die Seite " **Zugriffs-Edge-Konfiguration** " konfiguriert werden können:

  - **Aktivieren von Verbund-und öffentlichen Chat Verbindungen**   Aktivieren Sie diese Option, wenn Sie den Benutzer Zugriff auf Partnerdomänen für Föderationen unterstützen möchten. Diese Einstellung gilt für SIP-Föderations-und XMPP-Föderationen, die für globale, Website-oder benutzerbereiche auf der Seite " **externe Zugriffsrichtlinie** " konfiguriert sind. Damit die Verbund Einstellungen angewendet werden, müssen Sie die Verbundunterstützung auf beiden Seiten konfigurieren.
    
    Es gibt zwei Optionen, die optionale Einstellungen für die Erkennung von Verbundpartnern sind, und ob Archivierungs verzichte (Benachrichtigung an verbundene Kontakte, mit denen Sie kommunizieren, dass Ihre Bereitstellung für die Archivierung aktiviert ist und dass die Kommunikationsdetails archiviert werden) an Kontakte gesendet werden.
    
      - **Aktivieren der Partnerdomänen Ermittlung**   Wenn Sie diese Option auswählen, wird die automatische Ermittlung von Domänen ermöglicht, mit denen Sie eine Föderation durch schließen können. Lync Server 2013 verwendet DNS-Einträge (Domain Name System), um zu versuchen, Domänen zu finden, die nicht in der Liste der zulässigen Domänen aufgeführt sind, den eingehenden Datenverkehr von ermittelten Partner Partnern automatisch auswerten und diesen Datenverkehr basierend auf der Vertrauensebene, dem Umfang des Datenverkehrs und den Administratoreinstellungen einschränken oder blockieren Wenn Sie diese Option nicht auswählen, wird der Verbundbenutzer Zugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste zugelassene Domänen aufnehmen. Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass einzelne Domänen blockiert oder zulässig sein sollen, einschließlich der Beschränkung des Zugriffs auf bestimmte Server, auf denen der Access-Edgedienst in der Verbunddomäne ausgeführt wird. Ausführliche Informationen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).
    
      - **Senden einer Archivierungs Klausel an verbundene Partner**   Wenn Sie diese Option aktivieren, können Sie eine Nachricht zur Archivierungs Haftung an verbundene Partner senden, die Ihnen mitteilt, dass Kommunikationsdetails aufgezeichnet werden. Wenn Sie die externe Kommunikation mit Verbundpartner Domänen archivieren, sollten Sie die Benachrichtigung über Archivierungs Verzicht aktivieren, um die Partner zu warnen, dass Ihre Nachrichten und Kommunikationsdetails von Ihrer Bereitstellung archiviert werden. Details zur Archivierung finden Sie unter [Definieren Ihrer Anforderungen für die Archivierung in lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).

  - **Aktivieren des Remotebenutzerzugriffs**   Aktivieren Sie diese Option, wenn Sie möchten, dass Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, wie Telecommuter und Benutzer, die unterwegs sind, eine Verbindung mit lync Server herstellen können. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

  - **Aktivieren von anonymen Benutzern für den Zugriff auf Konferenzen**   Aktivieren Sie diese Option, wenn interne Benutzer externe anonyme Benutzer zu Konferenzen einladen möchten, die Sie organisieren. Wenn Sie diese Einstellung aktivieren, können anonyme Benutzer nur für Konferenzen zugelassen werden. Informationen zum Konfigurieren der Konferenzumgebung und der Optionen, die definieren, wie und was Ihre Benutzer mit Konferenzen und für die Einbeziehung anonymer Benutzer tun können, finden Sie unter Details unter [erstellen oder Ändern von Konferenzbenutzer Oberflächen für eine Website oder Benutzer](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) und [Konferenzrichtlinien Einstellungsreferenz für lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>


> [!NOTE]  
> Neben der Unterstützung für den Zugriff durch externe Benutzer können Sie auch Richtlinien konfigurieren, um die Verwendung des Remotebenutzerzugriffs in Ihrer Organisation zu steuern, bevor Benutzer Zugriff auf externe Benutzer erhalten. Details zum Erstellen, konfigurieren und Anwenden von Richtlinien für den Zugriff durch externe Benutzer finden Sie unter Verwalten von Richtlinien für den <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">externen Zugriff in lync Server 2013</A>.



</div>

**Anzeigen von Informationen zur Access-Edge-Konfiguration mithilfe von Windows PowerShell-Cmdlets**

  - Informationen zur Access-Edge-Konfiguration können mithilfe von Windows PowerShell und dem Cmdlet **Get-csaccessedgeconfiguration nicht angeben** angezeigt werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .
    
    Wenn Sie Informationen zu allen Einstellungen für die Zugriffs-Edge-Konfiguration anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsAccessEdgeConfiguration
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer in Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

