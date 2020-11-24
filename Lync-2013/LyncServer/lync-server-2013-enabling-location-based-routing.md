---
title: 'Lync Server 2013: aktivieren Location-Based Routings'
description: 'Lync Server 2013: aktivieren Location-Based Routings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7844af5792468cd5645b6b42c857c63b943c2df1
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394718"
---
# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Aktivieren von Location-Based-Routing in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-04-26_

Nachdem Enterprise-VoIP bereitgestellt und netzwerkregionen,-Websites und-Subnetze definiert sind, können Sie Location-Based Routing aktivieren. Location-Based Routing muss für die folgenden Enterprise-VoIP-Elemente aktiviert sein:

  - Netzwerk Websites

  - Trunk-Konfigurationen

  - VoIP-Richtlinien

  - Routing Konfiguration

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>Aktivieren Location-Based Routings auf Netzwerk Websites

Nachdem Sie Enterprise-VoIP und konfigurierte Netzwerk Websites bereitgestellt haben, können Sie Location-Based Routing konfigurieren. Zuerst erstellen Sie eine VoIP-Routing Richtlinie, um die Netzwerk Website mit den entsprechenden PSTN-Nutzungen zu verknüpfen. Stellen Sie beim Zuweisen von PSTN-Nutzungen zu einer VoIP-Routing Richtlinie sicher, dass nur PSTN-Nutzungen verwendet werden, die VoIP-Routen zugeordnet sind, die ein lokales PSTN-Gateway für die Website oder ein PSTN-Gateway verwenden, das sich in einem Bereich befindet, in dem Location-Based Routing Einschränkungen nicht erforderlich sind. Verwenden Sie den lync Server Windows PowerShell-Befehl, die CsVoiceRoutingPolicy-oder lync Server-Systemsteuerung, um VoIP-Routing Richtlinien zu erstellen.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Weitere Informationen finden Sie unter [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).

In diesem Beispiel veranschaulichen die folgenden Tabellen-und Windows PowerShell-Befehle zwei VoIP-Routing Richtlinien und die zugehörigen PSTN-Nutzungen, die in diesem Szenario definiert sind. Nur Einstellungen, die für Location-Based Routing spezifisch sind, werden in der Tabelle zu Illustrationszwecken berücksichtigt.

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>VoIP-Routing Richtlinie 1</th>
<th>VoIP-Routing Richtlinie 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VoIP-Richtlinienkennung</p></td>
<td><p>Delhi-VoIP-Routing Richtlinie</p></td>
<td><p>Hyderabad-VoIP-Routing Richtlinie</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Nutzungen</p></td>
<td><p>Nutzung von Delhi, Nutzung von Telefonanlagen, Telefonanlagen Hyd</p></td>
<td><p>Hyderabad-Nutzung, Nutzung von Telefonanlagen Hyd, Telefonanlagen Nutzung</p></td>
</tr>
</tbody>
</table>

  

Konfigurieren Sie als nächstes Location-Based Routing für die entsprechenden Netzwerk Websites, und ordnen Sie Ihre VoIP-Routing Richtlinien zu. Verwenden Sie den Windows PowerShell-Befehl von lync Server, New-CsNetworkSite, um Location-Based Routing zu aktivieren und Ihren Netzwerk Websites VoIP-Routing Richtlinien zuzuordnen, die Routing Einschränkungen erzwingen müssen.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

In diesem Beispiel wird in der folgenden Tabelle Location-Based Routing für zwei verschiedene Netzwerkstandorte, Delhi und Hyderabad, veranschaulicht, die in diesem Szenario mithilfe der lync Server Windows PowerShell definiert sind. Nur Einstellungen, die für Location-Based Routing spezifisch sind, werden in der Tabelle zu Illustrationszwecken berücksichtigt.

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Website 1 (Delhi)</th>
<th>Website 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Websitename</p></td>
<td><p>Website 1 (Delhi)</p></td>
<td><p>Website 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>Wahr</p></td>
<td><p>Wahr</p></td>
</tr>
<tr class="odd">
<td><p>VoIP-Routing Richtlinie</p></td>
<td><p>Delhi-VoIP-Routing Richtlinie</p></td>
<td><p>Hyderabad-VoIP-Routing Richtlinie</p></td>
</tr>
<tr class="even">
<td><p>Subnetze</p></td>
<td><p>Subnetz 1 (Delhi)</p></td>
<td><p>Subnetz 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>Aktivieren von Location-Based Routing zu Trunks

Bevor eine trunk-Konfiguration für Location-Based Routing aktiviert werden kann, müssen Sie für jeden trunk oder jede Netzwerk Website eine trunk-Konfiguration erstellen. Verwenden Sie den Windows PowerShell-Befehl von lync Server, New-CsTrunkConfiguration, um eine trunk-Konfiguration zu erstellen. Wenn mehrere Trunks einem bestimmten System (also Gateway oder PBX) zugeordnet sind, muss jede trunk-Konfiguration so geändert werden, dass Location-Based Routing Einschränkungen aktiviert werden.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Weitere Informationen finden Sie unter [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

In diesem Beispiel veranschaulichen die folgenden Windows PowerShell-Befehle das Erstellen einer trunk-Konfiguration für jeden trunk in der Bereitstellung, die in diesem Szenario definiert ist.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

Nachdem eine trunk-Konfiguration pro trunk konfiguriert wurde, können Sie den lync Server Windows PowerShell-Befehl, CsTrunkConfiguration, verwenden, um Location-Based Routing an Ihre Trunks zu aktivieren, die Routing Einschränkungen erzwingen müssen. Aktivieren Sie Location-Based Routing an Trunks, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie die Netzwerk Website zu, auf der sich das Gateway befindet.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Weitere Informationen finden Sie unter [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

In diesem Beispiel ist Location-Based Routing für jeden trunk aktiviert, der PSTN-Gateways in Delhi und Hyderabad zugeordnet ist:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

Aktivieren Sie Location-Based Routing für Trunks, die keine Anrufe an das PSTN weiterleiten. Sie müssen den trunk jedoch weiterhin der Netzwerk Website zuordnen, auf der sich das System befindet, da Location-Based Routing Einschränkungen für PSTN-Anrufe, die über diesen Trunk verbunden sind, erzwungen werden müssen. In diesem Beispiel ist Location-Based Routing für jeden trunk, der PBX-Systemen in Delhi und Hyderabad zugeordnet ist, nicht aktiviert:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Endpunkte, die mit Systemen verbunden sind, die keine Anrufe an das PSTN (also eine Telefonanlage) weiterleiten, weisen ähnliche Einschränkungen wie lync-Endpunkte von Benutzern auf, die für Location-Based Routing aktiviert sind. Dies bedeutet, dass diese Benutzer unabhängig vom Standort des Benutzers Anrufe an und von lync-Benutzern tätigen und empfangen können. Sie können auch Anrufe von und zu anderen Systemen tätigen, die keine Anrufe an das PSTN-Netzwerk (also einen mit einer anderen Telefonanlage verbundenen Endpunkt) weiterleiten, und zwar unabhängig von der Netzwerk Website, der das System zugeordnet ist. Alle eingehenden Anrufe, ausgehenden Anrufe, Anruf Übertragungen und Anrufweiterleitung, die PSTN-Endpunkte betreffen, unterliegen Location-Based Routing-Erzwingung. Bei solchen anrufen müssen nur PSTN-Gateways verwendet werden, die für solche Systeme als lokal definiert sind.

In der folgenden Tabelle wird die trunk-Konfiguration von vier Trunks auf zwei verschiedenen Netzwerkstandorten veranschaulicht: zwei mit PSTN-Gateways verbunden und zwei mit PBX-Systemen verbunden.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>EnableLocationRestriction</th>
<th>NetworkSiteID</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PstnGateway: trunk 1 del-GW</p></td>
<td><p>Wahr</p></td>
<td><p>Website 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: trunk 2 Hyd-GW</p></td>
<td><p>Wahr</p></td>
<td><p>Website 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway: trunk 3 del-PBX</p></td>
<td><p>Falsch</p></td>
<td><p>Website 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: trunk 4 Hyd-PBX</p></td>
<td><p>Falsch</p></td>
<td><p>Website 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>Aktivieren von Location-Based Routing zu VoIP-Richtlinien

Wenn Sie Location-Based Routing für bestimmte Benutzer erzwingen möchten, konfigurieren Sie die VoIP-Richtlinie dieser Benutzer, um die PSTN-Maut Umgehung zu verhindern. Verwenden Sie den Windows PowerShell-Befehl von lync Server, New-CsVoicePolicy, zum Erstellen einer neuen VoIP-Richtlinie oder eines CsVoicePolicy, wenn Sie eine vorhandene Richtlinie verwenden, um Location-Based Routing zu aktivieren, indem Sie die PSTN-Maut Umgehung verhindern.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Weitere Informationen finden Sie unter [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).

In diesem Beispiel veranschaulichen die folgenden Tabellen-und Windows PowerShell-Befehle die Verhinderung von PSTN-Maut Umgehung für die in diesem Szenario definierten VoIP-Richtlinien in Delhi und Hyderabad. Nur Einstellungen, die für Location-Based Routing spezifisch sind, werden in der Tabelle zu Illustrationszwecken berücksichtigt.

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>VoIP-Richtlinie 1</th>
<th>VoIP-Richtlinie 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VoIP-Richtlinienkennung</p></td>
<td><p>VoIP-Richtlinie für Delhi</p></td>
<td><p>Hyderabad-VoIP-Richtlinie</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Nutzungen</p></td>
<td><p>Nutzung von Delhi, Nutzung von Telefonanlagen, Telefonanlagen Hyd</p></td>
<td><p>Hyderabad-Nutzung, Nutzung von Telefonanlagen Hyd, Telefonanlagen Nutzung</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>Wahr</p></td>
<td><p>Wahr</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>Aktivieren des Location-Based-Routings in der Routingkonfiguration

Schließlich können Sie Location-Based Routing an Ihre Routingkonfiguration Global aktivieren. Verwenden Sie den Windows PowerShell-Befehl von lync Server, New-CsRoutingConfiguration, um Location-Based Routing zu aktivieren.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Weitere Informationen finden Sie unter [Satz-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).

<div>


> [!NOTE]  
> während Location-Based-Routing über eine globale Konfiguration aktiviert werden muss, wird die anzuwendende Regel nur für die Websites, Benutzer und Trunks erzwungen, für die Sie konfiguriert wurde, wie in dieser Dokumentation angegeben.



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von standortbasiertem Routing in Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

