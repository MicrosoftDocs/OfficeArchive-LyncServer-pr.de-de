---
title: 'Lync Server 2013: Konfigurieren der Föderation mit lync Online'
description: 'Lync Server 2013: Konfigurieren Sie den Verbund mit lync online.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3372a76b5ff7ad9dde5a00fd562b74877bd679a
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49434032"
---
# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>Konfigurieren des Verbunds von lync Server 2013 mit lync Online

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-08-15_

Führen Sie die Schritte in diesem Abschnitt aus, um die Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype for Business Online zu konfigurieren.

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Konfigurieren Ihres lokalen Edge-Diensts für den Verbund mit Skype for Business Online

Mithilfe der Föderation können Benutzer in Ihrer lokalen Bereitstellung mit Microsoft 365-oder Office 365-Benutzern in Ihrer Organisation kommunizieren. Führen Sie die folgenden Cmdlets aus, um den Verbund zu konfigurieren:

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Konfigurieren Ihres Skype for Business Online-Mandanten für einen freigegebenen SIP-Adressraum

Eine SIP-Adresse (Session Initiation Protocol) ist ein eindeutiger Bezeichner für jeden Benutzer in einem Netzwerk, ähnlich wie eine Telefonnummer oder eine E-Mail-Adresse. Bevor Sie versuchen, lync-Benutzer von lokal in Skype for Business Online zu verschieben, müssen Sie Ihre Microsoft 365-oder Office 365-Organisation so konfigurieren, dass der SIP-Adressraum (Shared Session Initiation Protocol) für Ihre lokale Bereitstellung freigegeben wird. Wenn dies nicht konfiguriert ist, wird möglicherweise die folgende Fehlermeldung angezeigt:

Move-CsUser: HostedMigration fault: Error=(510), Description=(Der Mandant dieses Benutzers ist nicht für den freigegebenen SIP-Adressbereich aktiviert.)

Um einen freigegebenen SIP-Adressraum zu konfigurieren, richten Sie eine Remote-PowerShell-Sitzung mit Skype for Business Online ein, und führen Sie dann das folgende Cmdlet aus:
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
Zum Einrichten einer PowerShell-Remotesitzung mit Skype for Business Online müssen Sie zunächst das Skype for Business Online-Modul für Windows PowerShell installieren, das Sie hier abrufen können: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) .

Nach der Installation des Moduls können Sie mit den folgenden Cmdlets eine Remotesitzung einrichten:

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

Weitere Informationen zum Einrichten einer PowerShell-Remotesitzung mit Skype for Business Online finden Sie unter [Herstellen einer Verbindung mit Skype for Business Online mithilfe von Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

Weitere Informationen zur Verwendung des PowerShell-Moduls für Skype for Business Online finden Sie unter [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Neu – CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
