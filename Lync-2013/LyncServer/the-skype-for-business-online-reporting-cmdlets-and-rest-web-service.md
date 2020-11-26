---
title: Die Skype for Business Online-Bericht Erstellungs-Cmdlets und der übrige Web Service
description: Die Skype for Business Online-Berichterstattungs-Cmdlets und der restliche Webdienst.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2160e0910d42f811ec8b03fa50450d5f73c59b1
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49423407"
---
# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>Die Skype for Business Online-Bericht Erstellungs-Cmdlets und der übrige Web Service

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-09-05_

In Verbindung mit den Berichterstellungsfeatures bietet Skype for Business Online Zugriff auf fünf Windows PowerShell-Cmdlets, die dazu beitragen, diese Berichte zu generieren, und Sie können auch von Administratoren verwendet werden, um angepasste Berichtsdaten zurückzugeben. Skype for Business Online enthält auch den anderen (Repräsentations Status Transfer), der von Entwicklern zum Abrufen von benutzerdefinierten Bericht Erstellungsinformationen verwendet werden kann.

Zu den für Administratoren verfügbaren Berichterstattungs-Cmdlets gehören:

  - Get-CsActiveUserReport, das Informationen über die Anzahl aktiver Benutzer enthält (also Benutzer, die sich bei Skype for Business Online angemeldet haben und an mindestens einer Konferenz oder Peer-to-Peer-Kommunikationssitzung teilgenommen haben).

  - Get-CsAVConferenceTimeReport bietet Informationen über die Zeitdauer (in Minuten), die Benutzer in Audio-und Videokonferenzen verbracht haben.

  - Get-CsConferenceReport, das Informationen über die Anzahl und die Art der Konferenzen enthält, an denen Benutzer teilgenommen haben.

  - Get-CsP2PAVTimeReport bietet Informationen über die Zeitdauer (in Minuten), die Benutzer in Peer-to-Peer-Sitzungen mit Audio und/oder Video verbracht haben.

  - Get-CsP2PSessionReport, das Informationen über die Anzahl und den Typ der Peer-to-Peer-Sitzungen enthält, an denen Benutzer teilgenommen haben.

Die meisten Administratoren verwenden die im Microsoft 365 Admin Center verfügbaren Berichte: Diese Berichte werden nicht nur automatisch generiert, sondern auch eine grafische Darstellung der Daten bereitgestellt, die häufig einfacher zu interpretieren sind als die von den Berichterstattungs-Cmdlets zurückgegebenen unformatierten Zahlenwerte. Administratoren, die mit Windows PowerShell vertraut sind, können jedoch mithilfe der Berichterstattungs-Cmdlets Daten zurückgeben, die in den lync Online-Berichten nicht ohne weiteres verfügbar sind. Beispielsweise geben die Berichterstattungs-Cmdlets Informationen zur Sitzungsdauer zurück (die Zeitdauer in Minuten, zu der jede Sitzung dauerte). Die einzelnen Sitzungs dauern sind mithilfe der lync Online-Berichte nicht verfügbar. In der täglichen Ansicht werden in den lync Online-berichten ebenfalls Informationen nur für die vorhergehenden 14 Tage angezeigt. Wenn Sie die Tagesergebnisse für einen anderen Tag überprüfen möchten (beispielsweise ein Datum vor vier Monaten), können Sie dies mithilfe der Berichterstattungs-Cmdlets tun.

Administratoren sind möglicherweise auch an dem Artikel [mit Excel zum Abrufen von Office 365-Berichtsdaten](https://msdn.microsoft.com/library/dn781442.aspx)interessiert, in dem erläutert wird, wie Sie das Feature "OData-Datenabfrage" in Microsoft Excel verwenden, um einen benutzerdefinierten Office 365-Bericht zu erstellen. Benutzerdefinierte Berichte bieten Ihnen die Möglichkeit, zu diktieren, welche Daten (und wie viele Daten) vom Office 365-Berichterstattungsdienst zurückgegeben werden. Benutzerdefinierte Berichte ermöglichen Ihnen auch, wie Sie angeben, wie die Daten sortiert und gruppiert werden sollen, und bieten Zugriff auf Informationen, die nicht im Admin Center angezeigt werden.

Administratoren mit einem Entwicklungshintergrund können mithilfe des RESTful-Webdiensts Informationen abrufen, die nicht im Skype for Business Online Admin Center angezeigt werden. Der restliche Dienst ist mit dem SOAP-Dienst vergleichbar, da jede Technologie eine Möglichkeit bietet, XML-Daten zwischen einem Client und einem Server zu übertragen. Der Service für den Ruhezustand hat jedoch mindestens zwei Vorteile gegenüber dem SOAP-Dienst. Zum einen führt Ruhe XML-Datenübertragungen mit einem standardisierten Format aus, das als Atom-Syndication-Format bezeichnet wird. Im Gegensatz dazu wird SOAP beim Übertragen von Daten mit einem nicht standardmäßigen Format verwendet. Darüber hinaus ist "Ruhe" in der Lage, Daten über Netzwerke zu übertragen, die andere HTTP-Verben als "abrufen" und "Posten" blockieren.

<div>

## <a name="see-also"></a>Siehe auch


[Lync Online-Berichterstellung](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))  


[Der Office 365-Berichterstellungsdienst](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[Kennenlernen des Office 365-Berichts-Webdiensts](https://msdn.microsoft.com/library/office/jj984321.aspx)  
[Die Exchange Online-Berichterstattungs-Cmdlets](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)  
[Verwenden von Excel zum Abrufen von Office 365-Berichtsdaten](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

