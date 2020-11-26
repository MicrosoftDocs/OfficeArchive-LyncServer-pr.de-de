---
title: 'Lync Server 2013: Konfigurieren von Sicherheitseinstellungen für lync Phone Edition'
description: 'Lync Server 2013: Konfigurieren von Sicherheitseinstellungen für lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82e6a6488db66a8497930ee6b2d1aec6fc8b0b2d
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433766"
---
# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="c6a12-103">Konfigurieren von Sicherheitseinstellungen für lync Phone Edition in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6a12-103">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="c6a12-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="c6a12-104">

<span> </span></span></span>

<span data-ttu-id="c6a12-105">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c6a12-105">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c6a12-106">Verbessern Sie die Sicherheit von Geräten, auf denen lync Phone Edition ausgeführt wird, über Ihre SIP-Sicherheitseinstellung und die Einstellungen für die Telefonsperre.</span><span class="sxs-lookup"><span data-stu-id="c6a12-106">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="c6a12-107">So konfigurieren Sie die Sicherheitseinstellungen für lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="c6a12-107">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="c6a12-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="c6a12-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c6a12-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c6a12-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c6a12-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c6a12-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c6a12-111">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf **Gerätekonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c6a12-111">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="c6a12-112">Doppelklicken Sie auf der Seite **Device Configuration** in der Liste der Gerätekonfigurationen auf die Konfiguration, für die Sie die Sicherheitseinstellungen ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c6a12-112">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="c6a12-113">Geben Sie unter **Gerätekonfiguration bearbeiten** in **SIP-Sicherheit** die SIP-Sicherheitsstufe an.</span><span class="sxs-lookup"><span data-stu-id="c6a12-113">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level.</span></span> <span data-ttu-id="c6a12-114">Die Standardstufe ist **hoch**, was wir empfehlen.</span><span class="sxs-lookup"><span data-stu-id="c6a12-114">The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="c6a12-115">Aktivieren oder deaktivieren Sie unter **Gerätekonfiguration bearbeiten** unter **Telefonsperre** das Kontrollkästchen **Gerätesperre erzwingen** (standardmäßig aktiviert), und geben Sie die minimale PIN-Länge (standardmäßig 6 Zeichen) und einen Timeoutzeitraum (standardmäßig 10 Minuten) an.</span><span class="sxs-lookup"><span data-stu-id="c6a12-115">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default).</span></span> <span data-ttu-id="c6a12-116">Wir empfehlen, diese Standardeinstellungen zu verwenden oder die PIN-Länge zu erhöhen und/oder den Timeoutzeitraum zu verringern.</span><span class="sxs-lookup"><span data-stu-id="c6a12-116">We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6a12-117">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-enforce-phone-locking.md">erzwingen der Telefon Sperrung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c6a12-117">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c6a12-118">Konfigurieren von Sicherheitseinstellungen für lync Phone Edition-Telefone mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c6a12-118">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c6a12-119">Sicherheitseinstellungen können mithilfe der lync Server-Verwaltungsshell und des Cmdlets **Get-CsUCPhoneConfiguration** verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="c6a12-119">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="c6a12-120">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c6a12-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c6a12-121">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="c6a12-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="c6a12-122">So ändern Sie den SIP-Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="c6a12-122">To modify the SIP security mode</span></span>

  - <span data-ttu-id="c6a12-123">Dieser Befehl legt den SIPSecurityMode für die globale Sammlung von UC-Telefoneinstellungen auf Mittel fest.</span><span class="sxs-lookup"><span data-stu-id="c6a12-123">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium.</span></span> <span data-ttu-id="c6a12-124">SIP-Sicherheit kann auch auf "Low" oder "hoch" (der Standardwert) festgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="c6a12-124">SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="c6a12-125">So ändern Sie die minimale PIN-Länge</span><span class="sxs-lookup"><span data-stu-id="c6a12-125">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="c6a12-126">In diesem Beispiel werden alle UC-Telefoneinstellungen so geändert, dass eine minimale PIN-Länge von 7 Ziffern erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c6a12-126">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="c6a12-127">Ausführliche Informationen finden Sie unter [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="c6a12-127">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6a12-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6a12-128">See Also</span></span>


[<span data-ttu-id="c6a12-129">Verwalten der lync Server 2013-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c6a12-129">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="c6a12-130">Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6a12-130">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

<span data-ttu-id="c6a12-131"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="c6a12-131"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

