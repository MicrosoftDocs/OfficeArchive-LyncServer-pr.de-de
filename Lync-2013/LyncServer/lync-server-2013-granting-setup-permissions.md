---
title: 'Lync Server 2013: Gewähren von Setupberechtigungen'
description: 'Lync Server 2013: Erteilen von Setup Berechtigungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5523494219d07907caeefc1bd139c41856effa54
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427900"
---
# <a name="granting-setup-permissions-in-lync-server-2013"></a>Gewähren von Setupberechtigungen in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-08-27_

Sie können das Cmdlet **Grant-CsSetupPermission** verwenden, um der RTCUniversalServerAdmins-Gruppe für eine angegebene Active Directory-Organisationseinheit (OU) Lese-, Schreib-, ReadSPN-und WriteSPN-Berechtigungen hinzuzufügen. Anschließend können Mitglieder der RTCUniversalServerAdmins-Gruppe in dieser OU Server mit lync Server 2013 in der angegebenen Domäne installieren, ohne Mitglieder der Gruppe der Domänenadministratoren zu sein.

Verwenden Sie das Cmdlet **Test-CsSetupPermission** , um die Berechtigungen zu überprüfen, die Sie mithilfe des Cmdlets **Grant-CsSetupPermission** eingerichtet haben.

Sie können das Cmdlet **REVOKE-CsSetupPermission** verwenden, um Berechtigungen zu entfernen, die Sie mit dem Cmdlet **Grant-CsSetupPermission** erteilt haben.

<div>

## <a name="to-grant-setup-permissions"></a>So erteilen Sie Setup Berechtigungen

1.  Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie Setup Berechtigungen erteilen möchten. Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Sie können den ComputerOu-Parameter als relativ zum Standardnamenskontext der angegebenen Domäne (beispielsweise CN = Computers) angeben. Sie können diesen Parameter auch als vollständigen Distinguished Name (DN) angeben (beispielsweise "CN = Computers, DC = contoso, DC = com"). In diesem Fall müssen Sie eine OU-DN angeben, die mit der von Ihnen angegebenen Domäne konsistent ist.
    
    Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.

</div>

<div>

## <a name="to-verify-setup-permissions"></a>So überprüfen Sie die Setup Berechtigungen

1.  Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie die mit dem Cmdlet **Grant-CsSetupPermission** gewährten Setup Berechtigungen überprüfen möchten. Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    Sie können den ComputerOu-Parameter als relativ zum Standardnamenskontext der angegebenen Domäne (beispielsweise CN = Computers) angeben. Sie können diesen Parameter auch als vollständigen Distinguished Name (DN) angeben (beispielsweise "CN = Computers, DC = contoso, DC = com"). In diesem Fall müssen Sie eine OU-DN angeben, die mit der von Ihnen angegebenen Domäne konsistent ist.
    
    Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>So widerrufen Sie die Setup Berechtigungen

1.  Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie die vom Cmdlet **Grant-CsSetupPermission** gewährten Setup Berechtigungen widerrufen möchten. Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Sie können den ComputerOu-Parameter als relativ zum Standardnamenskontext der angegebenen Domäne (beispielsweise CN = Computers) angeben. Sie können diesen Parameter auch als vollständigen Distinguished Name (DN) angeben (beispielsweise "CN = Computers, DC = contoso, DC = com"). In diesem Fall müssen Sie eine OU-DN angeben, die mit der von Ihnen angegebenen Domäne konsistent ist.
    
    Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.

</div>

</div>

<span> </span>

</div>

</div>

</div>

