---
title: 'Lync Server 2013: Konfigurieren von Unified Messaging in Microsoft Exchange'
description: 'Lync Server 2013: Konfigurieren von Unified Messaging in Microsoft Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8db43bbe50061a1a044bdd34b637ba86f626ca85
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49395239"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Konfigurieren von Unified Messaging in Microsoft Exchange für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

In diesem Thema wird beschrieben, wie Sie Exchange Unified Messaging (um) auf einem Microsoft Exchange-Server für die Verwendung mit Enterprise-VoIP konfigurieren.

<div>


> [!NOTE]  
> Die Cmdlet-Beispiele in diesem Thema enthalten Syntax für die Exchange 2007-Version der Exchange-Verwaltungsshell. Wenn Sie Exchange 2010 oder Exchange 2013 ausführen, lesen Sie die entsprechende Dokumentation, auf die verwiesen wird.



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>So konfigurieren Sie einen Server mit Exchange Server um

1.  Erstellen Sie einen SIP-Wählplan (Uniform Resource Identifier) für jedes Ihrer Enterprise-VoIP-Standortprofile. Wenn Sie die Exchange-Verwaltungskonsole verwenden möchten, erstellen Sie einen neuen Wählplan, wobei die Sicherheitseinstellung **gesichert (bevorzugt)** ist.
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie den Wert für die Sicherheitseinstellung auf <STRONG>SIP secured</STRONG> festgelegt haben, um die Verschlüsselung für den SIP-Datenverkehr zu erzwingen, wie zuvor empfohlen, beachten Sie, dass diese Sicherheitseinstellung für einen Wählplan unzureichend ist, wenn der Front-End-Pool so konfiguriert ist, dass eine Verschlüsselung erforderlich ist, was bedeutet, dass der Pool für SIP-und RTP-Datenverkehr verschlüsselt Wenn die Sicherheitseinstellungen für Wählplan und Pool nicht kompatibel sind, schlagen alle Anrufe an Exchange um aus dem Front-End-Pool fehl, was zu einem Fehler führt, der besagt, dass Sie über eine "inkompatible Sicherheitseinstellung" verfügen.

    
    </div>
    
    Wenn Sie die Exchange-Verwaltungsshell verwenden, geben Sie Folgendes ein:
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    Ausführliche Informationen finden Sie hier:
    
      - Informationen zu Office Communications Server 2007 finden Sie unter "Erstellen eines SIP-URI-Wählplans für Unified Messaging" unter [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) und "neu-UMDialplan: Exchange 2007-Hilfe" unter [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) .
    
      - Informationen zu Exchange 2010 finden Sie unter "Erstellen eines um-Wählplans" [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) und unter "neu-UMDialplan: Exchange 2010-Hilfe" unter [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) .
    
      - Informationen zu Exchange 2013 finden Sie unter "Unified Messaging" unter [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .
    
    <div>
    

    > [!NOTE]  
    > Ob Sie eine Sicherheitsstufe von <STRONG>SIPSecured</STRONG> oder <STRONG>gesichert</STRONG> auswählen, hängt davon ab, ob SRTP (Secure Real-Time Transport Protocol) für die Medienverschlüsselung aktiviert oder deaktiviert ist. Bei der lync Server 2010-Integration in Exchange um sollte dies der Verschlüsselungsstufe in der lync Server Media-Konfiguration entsprechen. Die lync Server Media-Konfiguration kann angezeigt werden, indem Sie das Cmdlet " <STRONG>Get-CsMediaConfiguration</STRONG> " ausführen. Ausführliche Informationen finden Sie unter Get-CsMediaConfiguration in der Dokumentation zur lync Server-Verwaltungsshell.<BR>Details zum Auswählen der geeigneten VoIP-Sicherheitseinstellung finden Sie unter <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Bereitstellungsprozess für die Integration von lokalen Unified Messaging und lync Server 2013</A>.

    
    </div>

2.  Führen Sie das folgende Cmdlet aus, um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für die einzelnen um-Wähleinstellungen zu erhalten:
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Ausführliche Informationen finden Sie hier:
    
      - Informationen zu Exchange 2007 finden Sie unter "Get-UMDialplan: Exchange 2007-Hilfe" unter [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) .
    
      - Informationen zu Exchange 2010 finden Sie unter "Get-UMDialplan: Exchange 2010-Hilfe" unter [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) .
    
      - Informationen zu Exchange 2013 finden Sie unter "Unified Messaging" unter [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .

3.  Notieren Sie den Namen des Wähl Plans für jeden um-Wählplan. Je nach ihrer Version von Exchange Server müssen Sie möglicherweise den FQDN für jeden Wählplan später als Namen für den entsprechenden lync Server-Wählplan für den Wählplan verwenden, damit die Wähl Plan Namen übereinstimmen.
    
    <div>
    

    > [!NOTE]  
    > Namen von lync Server-Wählplänen müssen nur dann mit um-Wähl Plan Namen übereinstimmen, wenn der um-Wählplan unter einer <EM>früheren</EM> Exchange-Version als Exchange 2010 SP1 ausgeführt wird.

    
    </div>

4.  Fügen Sie den Wählplan dem Server mit Exchange um wie folgt hinzu:
    
      - Wenn Sie die Exchange-Verwaltungskonsole verwenden, können Sie den Wählplan über das Eigenschaftenfenster für den Server hinzufügen. Spezifische Anweisungen finden Sie in der Exchange Server-Produktdokumentation.
        
        Informationen zu Exchange 2007 finden Sie unter "Hinzufügen eines Unified Messaging-Servers zu einem Wählplan" unter [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) .
        
        Informationen zu Exchange 2010 finden Sie unter "anzeigen oder Konfigurieren der Eigenschaften eines um-Servers" unter [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) .
        
        Informationen zu Exchange 2013 finden Sie unter "Unified Messaging" unter [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .
    
      - Wenn Sie die Exchange-Verwaltungsshell verwenden, führen Sie für jeden Ihrer Exchange um-Server die folgenden Aktionen aus:
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > Bevor Sie den folgenden Schritt ausführen, stellen Sie sicher, dass alle Enterprise-VoIP-Benutzer mit einem Exchange Server-Postfach konfiguriert wurden.<BR>Informationen zu Exchange 2007 finden Sie in der TechNet-Bibliothek Exchange Server 2007 unter <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> .<BR>Informationen zu Exchange 2010 finden Sie in der TechNet-Bibliothek Exchange Server 2010 unter <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> .<BR>Wenn Sie eine Postfachrichtlinie für jeden Wählplan angeben, den Sie in Schritt 1 erstellt haben, wählen Sie entweder die Standardrichtlinie oder eine aus, die Sie erstellt haben.

    
    </div>

5.  Navigieren Sie zu \<Exchange installation directory\> \\ Skripts, und geben Sie Folgendes ein, wenn Exchange in einer einzelnen Gesamtstruktur bereitgestellt wird:
    ```console
    exchucutil.ps1
    ```
    Wenn Exchange in mehreren Gesamtstrukturen bereitgestellt wird, geben Sie Folgendes ein:
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    wobei Gesamtstruktur-FQDN die Gesamtstruktur angibt, in der lync Server bereitgestellt wird.
    
    Wenn Sie über einen oder mehrere um-Wählpläne verfügen, die mehreren IP-Gateways zugeordnet sind, fahren Sie mit Schritt 6 fort. Wenn Ihre Wählpläne jeweils nur einem einzigen IP-Gateway zugeordnet sind, überspringen Sie Schritt 6.
    
    <div>
    

    > [!IMPORTANT]  
    > Stellen Sie sicher, dass der <STRONG>lync Server-Front-End-</STRONG> Dienst (rtcsrv.exe) <EM>nach</EM> der Ausführung von exchucutil.ps1 neu gestartet wird. Andernfalls erkennt lync Server keine Unified Messaging-Funktion in der Topologie.

    
    </div>

6.  Deaktivieren Sie entweder über die Exchange-Verwaltungsshell oder die Exchange-Verwaltungskonsole ausgehende Anrufe für alle IP-Gateways, die mit den einzelnen Wählplänen verknüpft sind.
    
    <div>
    

    > [!NOTE]  
    > Dieser Schritt ist erforderlich, um sicherzustellen, dass ausgehende Anrufe des Servers, auf dem Exchange Server Unified Messaging ausgeführt wird, für externe Benutzer (beispielsweise wie bei Szenarien mit Wiedergabe auf dem Smartphone) die Unternehmensfirewall zuverlässig durchlaufen.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie das um-IP-Gateway auswählen, über das ausgehende Anrufe zugelassen werden sollen, wählen Sie diejenige aus, die wahrscheinlich den meisten Datenverkehr verarbeitet. Lassen Sie ausgehenden Datenverkehr nicht über ein IP-Gateway zu, das eine Verbindung mit einem Pool von lync Server Directors herstellt. Vermeiden Sie auch Pools in einem anderen zentralen Standort oder einer Zweigstelle. Sie können eine der folgenden Methoden verwenden, um ausgehende Anrufe zu blockieren, indem Sie ein IP-Gateway durchlaufen:

    
    </div>
    
      - Wenn Sie die Exchange-Verwaltungsshell verwenden, deaktivieren Sie die einzelnen IP-Gateways, indem Sie den folgenden Befehl ausführen:
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        Informationen zu Exchange 2007 finden Sie unter "einrichten-UMIPGateway: Exchange 2007-Hilfe" unter [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) .
        
        Informationen zu Exchange 2010 finden Sie unter "einrichten-UMIPGateway: Exchange 2010-Hilfe" unter [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) .
    
      - Wenn Sie die Exchange-Verwaltungskonsole verwenden, deaktivieren Sie das Kontrollkästchen **ausgehende Anrufe über dieses IP-Gateway zulassen** .
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Ihr um-SIP-URI-Wählplan nur einem einzigen IP-Gateway zugeordnet ist, dürfen Sie ausgehende Anrufe über dieses Gateway nicht unterbinden.

    
    </div>

7.  Erstellen Sie für jeden lync Server-Wählplan eine automatische UM-Telefonzentrale.
    
    <div>
    

    > [!IMPORTANT]  
    > Schließen Sie keine Leerzeichen in den Namen der automatischen Telefonzentrale ein.

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    Ausführliche Informationen finden Sie hier:
    
      - Informationen zu Exchange 2007 finden Sie unter "New-UMAutoAttendant: Exchange 2007 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) .
    
      - Informationen zu Exchange 2010 finden Sie unter "New-UMAutoAttendant: Exchange 2010 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) .
    
    Der folgende Schritt sollte für jeden Benutzer ausgeführt werden, nachdem Sie lync Server-Benutzer für Enterprise-VoIP aktiviert haben und deren SIP-URIs kennen.

8.  Ordnen Sie Exchange um-Benutzern (die jeweils mit einem Exchange-e-Mail-Feld konfiguriert werden sollten) mit dem um-Wählplan zu, und erstellen Sie einen SIP-URI für jeden Benutzer.
    
    <div>
    

    > [!NOTE]  
    > Die <STRONG>SIPResourceIdentifier</STRONG> im folgenden Beispiel muss die SIP-Adresse des lync Server-Benutzers sein.

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    Ausführliche Informationen finden Sie hier:
    
      - Informationen zu Exchange 2007 finden Sie unter "Enable-UMMailbox: Exchange 2007 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) .
    
      - Informationen zu Exchange 2010 finden Sie unter "Enable-UMMailbox: Exchange 2010 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

