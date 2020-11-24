---
title: Cmdlets in Skype for Business Online, die keinen Bereich oder keine Identität verwenden
description: Cmdlets in Skype for Business Online, die keinen Bereich oder keine Identität verwenden.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7d893c4cf9203c8657dfbdfd7fb2bf46dbdfe4e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394246"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>Cmdlets in Skype for Business Online, die keinen Bereich oder keine Identität verwenden

 


Die beim Ändern der zulässigen Listen und blockierten Listen verwendeten Cmdlets (Listen, die ermitteln, mit welchen externen Organisationen ihre Benutzer kommunizieren dürfen) verwenden weder einen Bereich noch eine Identität. In der Tat hat das Cmdlet **New-CsEdgeAllowAllKnownDomains** keinerlei Parameter. Bei den Cmdlets, die weder einen Bereich noch eine Identität verwenden, handelt es sich um folgende:

  - [New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))

  - [New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))

  - [New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))

Beachten Sie, dass Sie mit dem Cmdlet **New-CsEdgeAllowList** und dem Cmdlet **New-CsEdgeDomainPattern** den Parameter Domain angeben müssen. Beispiel:

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>Siehe auch


[Identitäten, Bereiche und Mandanten in Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Lync Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

