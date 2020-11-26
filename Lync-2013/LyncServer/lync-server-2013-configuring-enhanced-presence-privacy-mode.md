---
title: 'Lync Server 2013: Konfigurieren des Datenschutzmodus für erhöhte Anwesenheit'
description: 'Lync Server 2013: Konfigurieren des erweiterten Datenschutzmodus für Anwesenheitsinformationen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8eab347d233c23a9a4becf119dee673d3021dfa
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433171"
---
# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a><span data-ttu-id="05008-103">Konfigurieren des erweiterten Anwesenheitsdaten Schutzmodus in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05008-103">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="05008-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="05008-104">

<span> </span></span></span>

<span data-ttu-id="05008-105">_**Letztes Änderungsdatum des Themas:** 2014-12-08_</span><span class="sxs-lookup"><span data-stu-id="05008-105">_**Topic Last Modified:** 2014-12-08_</span></span>

<span data-ttu-id="05008-106">Mit dem erweiterten Anwesenheitsdaten Schutzmodus können Benutzer ihre Anwesenheitsinformationen so einschränken, dass Sie nur für die Kontakte sichtbar sind, die in ihrer lync 2013-Kontaktliste aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="05008-106">With enhanced presence privacy mode, users can restrict their presence information so that it is visible only to the contacts listed in their Lync 2013 Contacts list.</span></span> <span data-ttu-id="05008-107">Die Cmdlets **New-CsPrivacyConfiguration** und **CsPrivacyConfiguration** verfügen über einen EnablePrivacyMode-Parameter, der diese Option steuert.</span><span class="sxs-lookup"><span data-stu-id="05008-107">The **New-CsPrivacyConfiguration** and **Set-CsPrivacyConfiguration** cmdlets have an EnablePrivacyMode parameter controls this option.</span></span> <span data-ttu-id="05008-108">Wenn EnablePrivacyMode auf "true" festgelegt ist, wird die Option zum Einschränken der Anwesenheitsinformationen auf Kontakte in den lync 2013-Status Optionen zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="05008-108">When EnablePrivacyMode is set to True, the option to restrict presence information to contacts becomes available in the Lync 2013 Status options.</span></span> <span data-ttu-id="05008-109">Wenn EnablePrivacyMode auf "false" festgelegt ist, können Benutzer entweder immer zulassen, dass ihre Anwesenheitsinformationen angezeigt werden, oder alle zukünftigen Änderungen einhalten, die der Administrator am Datenschutzmodus vornimmt.</span><span class="sxs-lookup"><span data-stu-id="05008-109">When EnablePrivacyMode is set to False, users can choose either to always allow everyone to see their presence information or to adhere to any future changes the administrator makes to the privacy mode.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="05008-110">Die Privatsphäre-Einstellungen von lync 2013 und lync 2010 werden von früheren Versionen (Microsoft Office Communicator 2007 R2 oder Microsoft Office Communicator 2007) nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="05008-110">Lync 2013 and Lync 2010 privacy settings are not honored by previous versions (Microsoft Office Communicator 2007 R2 or Microsoft Office Communicator 2007).</span></span> <span data-ttu-id="05008-111">Wenn frühere Versionen von Office Communicator angemeldet werden können, kann ein lync 2013-Benutzerstatus, die Kontaktinformationen oder das Bild von einer Person angezeigt werden, die nicht autorisiert ist, Sie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="05008-111">If previous versions of Office Communicator are allowed to sign in, a Lync 2013 user’s status, contact information, or picture could be viewed by someone who has not been authorized to view it.</span></span> <span data-ttu-id="05008-112">Darüber hinaus werden die Privatsphäre-Einstellungen eines lync 2013-Benutzers zurückgesetzt, wenn er sich später mit der vorherigen Version von Communicator anmeldet.</span><span class="sxs-lookup"><span data-stu-id="05008-112">Additionally, a Lync 2013 user’s privacy settings are reset if he or she later signs in with previous version of Communicator.</span></span><BR><span data-ttu-id="05008-113">Aus diesen Gründen in einem Migrationsszenario, bevor Sie den erweiterten Anwesenheitsdaten Schutzmodus aktivieren:</span><span class="sxs-lookup"><span data-stu-id="05008-113">For these reasons, in a migration scenario, before you enable enhanced presence privacy mode:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="05008-114">Stellen Sie sicher, dass auf jedem Benutzer lync 2013 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="05008-114">Ensure that every user has Lync 2013 installed.</span></span></P>
> <LI>
> <P><span data-ttu-id="05008-115">Definieren Sie eine clientversionsrichtlinien Regel, um zu verhindern, dass frühere Versionen von Communicator angemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="05008-115">Define a client version policy rule to prevent previous versions of Communicator from signing in.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a><span data-ttu-id="05008-116">So aktivieren Sie den Datenschutzmodus für erhöhte Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="05008-116">To enable enhanced presence privacy mode</span></span>

1.  <span data-ttu-id="05008-117">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="05008-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="05008-118">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="05008-118">Run the following command:</span></span>
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    <span data-ttu-id="05008-119">Dieser Befehl aktiviert den Datenschutzmodus für alle Datenschutz-Konfigurationseinstellungen, die derzeit in der Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05008-119">This command enables privacy mode for all the privacy configuration settings currently in use in the organization.</span></span> <span data-ttu-id="05008-120">Weitere Informationen dazu, wie die Richtlinienkonfigurationen für den lync Server Enhanced Presence-Datenschutzmodus die Kontakt Anwesenheit für den lync 2013-Client verwalten, finden Sie im Microsoft Knowledge Base-Artikel [Aktivieren des lync Server Enhanced Presence-Datenschutzmodus aktualisiert den Anwesenheitsstatus einiger lync-Kontakte auf "nicht verfügbar"](https://support.microsoft.com/kb/3020057).</span><span class="sxs-lookup"><span data-stu-id="05008-120">For more information about how the Lync Server enhanced presence privacy mode policy configurations manages contact presence for the Lync 2013 client, see the Microsoft KB article [Enabling Lync Server enhanced presence privacy mode updates the presence status of some Lync contacts to "unavailable"](https://support.microsoft.com/kb/3020057).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="05008-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05008-121">See Also</span></span>


[<span data-ttu-id="05008-122">Get-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="05008-122">Get-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[<span data-ttu-id="05008-123">Neu – CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="05008-123">New-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[<span data-ttu-id="05008-124">Satz-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="05008-124">Set-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

<span data-ttu-id="05008-125"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="05008-125"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

