---
title: Cmdlets in Skype for Business Online, die den globalen Bereich und den Transponder Bereich verwenden
description: Cmdlets in Skype for Business Online, die den globalen Bereich und den Transponder Bereich verwenden.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba89ebe7322159027c5de765117afd366cb3dc23
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394143"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Cmdlets in Skype for Business Online, die den globalen Bereich und den Transponder Bereich verwenden

 


In Skype for Business Online können Richtlinien entweder im *globalen Bereich* oder auf dem *Transponder Bereich* (oder *pro Benutzerbereich*) konfiguriert werden. Wenn Sie die **Get-CS-** Cmdlets verwenden, müssen Sie keinen Bereich oder keine Identität angeben. Wenn Sie eines dieser Cmdlets ohne Parameter aufrufen, werden alle relevanten Elemente zurückgegeben. Dieser Befehl gibt beispielsweise Informationen zu allen ihren Richtlinien für den externen Zugriff zurück:

    Get-CsExternalAccessPolicy

Sie müssen nur den Parameter Identity oder den Filter-Parameter einbeziehen, wenn Sie die zurückgegebenen Daten einschränken möchten. Wenn Sie beispielsweise nur die globale Richtlinie zurückgeben möchten, verwenden Sie diesen Befehl:

    Get-CsExternalAccessPolicy -Identity "global"

Verwenden Sie den folgenden Befehl, um eine benutzerspezifische Richtlinie mit der Identität "RedmondAccessPolicy" zurückzugeben:

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> Wenn Sie auf eine Richtlinie pro Benutzer verweisen, <STRONG>ist das Tagpräfix optional</STRONG> . Diese Syntax, die das Präfix enthält, ist ebenfalls gültig:<BR>Get-CsExternalAccessPolicy – Identity "Tag: RedmondAccessPolicy"



Verwenden Sie diesen Befehl, um alle Richtlinien mit Ausnahme der globalen Richtlinien (also alle pro-Benutzer-Richtlinien) zurückzugeben:

    Get-CsExternalAccessPolicy -Filter "tag:*"

Die folgenden Cmdlets arbeiten sowohl für den globalen Bereich als auch für den Bereich pro Benutzer (Tag):

  - [Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> Trotz des Namens sind die Wählpläne in der Regel Richtlinien. Der Begriff <EM>Wählplan</EM> wird anstelle von Wähl Richtlinien verwendet, um die Terminologie beizubehalten, die in früheren Versionen von lync Server verwendet wird.



## <a name="see-also"></a>Siehe auch


[Identitäten, Bereiche und Mandanten in Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Lync Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

