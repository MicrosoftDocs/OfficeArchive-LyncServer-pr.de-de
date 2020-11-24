---
title: Cmdlets in Skype for Business Online, die den Mandanten Parameter verwenden
description: Cmdlets in Skype for Business Online, die den Mandanten Parameter verwenden.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff2b8053dd855a854fa26699770d3dafaa0dcbd7
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394135"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>Cmdlets in Skype for Business Online, die den Mandanten Parameter verwenden

 


Wenn Sie die Einstellungen Ihres öffentlichen Anbieters ändern, müssen Sie immer eine Mandanten Identität angeben. Dies gilt auch, wenn Sie nur einen einzigen Mandanten haben. Mit diesem Befehl wird beispielsweise Windows Live als einziger öffentlicher Anbieter festgelegt, mit dem Ihre Benutzer kommunizieren können:

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

Glücklicherweise müssen Sie die Mandanten-ID (beispielsweise bf19b7db-6960-41e5-A139-2aa373474354) nicht jedes Mal eingeben, wenn Sie eines dieser Cmdlets ausführen. Stattdessen können Sie die Mandanten-ID abrufen, indem Sie das Cmdlet " [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) " ausführen, die Mandanten-ID in einer Variablen speichern und diese Variable dann verwenden, wenn Sie eines der anderen Cmdlets aufrufen. Beispiel:

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

Sie können dies auch in einem einzigen Befehl durchführen, indem Sie die Mandanten-ID abrufen und diesen Wert dann an das Set-CsTenantPublicProvider-Cmdlet weiterleiten:

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

Sie müssen die Mandanten-ID nicht angeben, wenn Sie das Cmdlet **Get-CsTenant** aufrufen. Dieser Befehl gibt Informationen zu Ihrem Mandanten zurück:

    Get-CsTenant

Die folgenden Cmdlets akzeptieren eine Mandanten Identität. In diesen Fällen ist der Parameter jedoch optional und muss nicht eingegeben werden, wenn das Cmdlet aufgerufen wird. Stattdessen wird Windows PowerShell die Mandanten Identität basierend auf dem Skype for Business Online-Mandanten, mit dem Sie zurzeit verbunden sind, effektiv eingeben:

  - [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))

  - [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))

  - [Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

Beispielsweise kann das Cmdlet " **Get-CsTenantFederationConfiguration** " mit diesem Befehl aufgerufen werden:

    Get-CsTenantFederationConfiguration

Obwohl dies nicht erforderlich ist, können Sie den Mandanten Parameter einbeziehen, wenn Sie Get-CsTenantFederationConfiguration aufrufen:

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>Siehe auch


[Identitäten, Bereiche und Mandanten in Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Lync Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

