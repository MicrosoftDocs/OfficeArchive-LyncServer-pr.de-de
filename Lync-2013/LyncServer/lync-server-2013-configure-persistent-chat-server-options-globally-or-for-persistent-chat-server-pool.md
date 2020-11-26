---
title: 'Lync Server 2013: Konfigurieren von Optionen für den Server für beständigen Chat auf globaler oder Poolebene'
description: 'Lync Server 2013: Konfigurieren Sie die Serveroptionen für beständigen Chats Global oder für den Serverpool für beständigen Chat.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0e26fc8719f9aa5f153a7962df70ee7237b980
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433822"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="095ca-103">Konfigurieren von Optionen für den Server für beständigen Chat auf globaler oder Poolebene in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="095ca-103">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="095ca-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="095ca-104">

<span> </span></span></span>

<span data-ttu-id="095ca-105">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="095ca-105">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="095ca-106">In der lync Server 2013-Systemsteuerung können Sie auf der Seite " **beständiger** Chat" den Abschnitt " **beständiger Chat** " verwenden, um die Einstellungen für beständigen Chat Global zu konfigurieren, wenn Sie für alle beständigen Chat Server Pools gelten, oder für einen bestimmten beständigen Chat Serverpool.</span><span class="sxs-lookup"><span data-stu-id="095ca-106">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="095ca-107">Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um der Topologie Unterstützung für beständigen Chat Server hinzuzufügen und dann die Topologie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="095ca-107">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="095ca-108">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigem Chat Server zu Ihrer Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="095ca-108">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="095ca-109">So konfigurieren Sie beständige Chat Optionen Global</span><span class="sxs-lookup"><span data-stu-id="095ca-109">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="095ca-110">Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="095ca-110">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="095ca-111">Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="095ca-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="095ca-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="095ca-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="095ca-113">Sie können auch Windows PowerShell-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="095ca-113">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="095ca-114">Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des beständigen Chat Servers mithilfe von Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="095ca-114">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="095ca-115">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="095ca-115">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="095ca-116">Klicken Sie auf der Seite **persistent Chat Configuration** auf **neu,** und klicken Sie dann auf **Websitekonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="095ca-116">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="095ca-117">Wählen Sie diese Option aus, wenn die Konfiguration auf alle beständigen Chat Server Pools angewendet werden soll, die auf der Website bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="095ca-117">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="095ca-118">Klicken Sie auf <STRONG>Poolkonfiguration</STRONG> , wenn die Konfiguration auf einen bestimmten beständigen Chat Server Pool angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="095ca-118">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="095ca-119">Wählen Sie unter **Website auswählen** die Website aus, die für die Websitekonfiguration des beständigen Chat Servers konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="095ca-119">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="095ca-120">Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="095ca-120">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="095ca-p105">Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortname bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="095ca-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="095ca-p106">Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert und Administratoren können den Chatverlauf pro Kategorie deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="095ca-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="095ca-126">Der beständige Chat Server speichert diese Nachrichten im Arbeitsspeicher, wenn Sie also diese Zahl erhöhen, werden weitere Nachrichten zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="095ca-126">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="095ca-127">Sie können jederzeit auf Verlaufs Inhalte zugreifen, indem Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="095ca-127">You can always access historical content by search.</span></span> <span data-ttu-id="095ca-128">Die Standardnummer bestimmt einfach die maximale Anzahl von Nachrichten, die Sie beim Herstellen einer Verbindung mit einem Chatroom anfänglich sehen.</span><span class="sxs-lookup"><span data-stu-id="095ca-128">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="095ca-p108">Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).</span><span class="sxs-lookup"><span data-stu-id="095ca-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="095ca-132">Diese Einstellung wird auf dem Server erzwungen, da benutzerdefinierte Anwendungen oder vorherige Gruppen-Chat-Clients, die Office Communications Server 2007 R2 &nbsp; -Gruppen-Chat Server oder lync Server 2010 verwenden, Gruppen-Chat Dateien in einem Raum bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="095ca-132">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="095ca-133">Wenn Sie über eine reine lync 2013-Bereitstellung oder einen lync 2013-Client verfügen, ist der lync 2013-Client nicht in der Lage, Dateien in einem beständigen Chat Server-Chatroom zu Posten.</span><span class="sxs-lookup"><span data-stu-id="095ca-133">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="095ca-134">Wählen Sie in der **Teilnehmer Aktualisierungs Grenze** das Limit für Teilnehmer Updates aus.</span><span class="sxs-lookup"><span data-stu-id="095ca-134">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="095ca-135">Der beständige Chat Server sendet Dienstplan Informationen (die mit einem Chatroom verbunden sind) an alle Teilnehmer, bis die Anzahl der verbundenen Nutzer diese Nummer erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="095ca-135">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="095ca-136">Standardmäßig ist die Nummer 75.</span><span class="sxs-lookup"><span data-stu-id="095ca-136">By default, the number is 75.</span></span> <span data-ttu-id="095ca-137">Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum an, über die der beständige Chat Server keine Dienstplan Updates mehr an verbundene Clients sendet, die im Chatroom anwesend sind.</span><span class="sxs-lookup"><span data-stu-id="095ca-137">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="095ca-p111">(Optional.) Wählen Sie unter **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte benutzerdefinierte Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und lediglich die Standardeinstellung verwenden möchten, können Sie diese Option leer lassen. Nach dem Festlegen der URL wird diese sowohl als interne als auch als externe Raumverwaltungs-URL angewendet.</span><span class="sxs-lookup"><span data-stu-id="095ca-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="095ca-142">Wenn Sie Ihre Raum Erstellungs Erfahrung anpassen und ihren spezifischen geschäftsworkflow einbeziehen möchten, können Sie eine benutzerdefinierte Raum Verwaltungslösung erstellen, indem Sie den beständigen Chat Server Software Development Kit (SDK) verwenden, ihn an einer beliebigen Stelle hosten und die URL hier platzieren.</span><span class="sxs-lookup"><span data-stu-id="095ca-142">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="095ca-143">Diese URL wird an den Client gesendet, sodass ein Benutzer, der versucht, einen Raum anzuzeigen oder zu erstellen, an Ihre benutzerdefinierte Raum Verwaltungslösung weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="095ca-143">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="095ca-144">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="095ca-144">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="095ca-145">So konfigurieren Sie beständige Chat-Optionen für einen bestimmten beständigen Chat-Server Pool</span><span class="sxs-lookup"><span data-stu-id="095ca-145">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="095ca-146">Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="095ca-146">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="095ca-147">Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="095ca-147">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="095ca-148">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="095ca-148">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="095ca-149">Sie können auch Windows PowerShell-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="095ca-149">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="095ca-150">Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des beständigen Chat Servers mithilfe von Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="095ca-150">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="095ca-151">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="095ca-151">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="095ca-152">Klicken Sie auf der Seite **Konfiguration für beständigen Chat** auf **Neu** und dann auf **Poolkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="095ca-152">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="095ca-153">Wählen Sie in **Dienst auswählen** den Dienst aus, der dem Server Pool für beständigen Chat zugeordnet ist und konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="095ca-153">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="095ca-154">Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="095ca-154">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="095ca-p115">Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortpoolname bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="095ca-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="095ca-p116">Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert und Administratoren können den Chatverlauf pro Kategorie deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="095ca-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="095ca-160">Der beständige Chat Server speichert diese Nachrichten im Arbeitsspeicher, wenn Sie also diese Zahl erhöhen, werden weitere Nachrichten zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="095ca-160">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="095ca-161">Sie können jederzeit auf Verlaufs Inhalte zugreifen, indem Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="095ca-161">You can always access historical content by search.</span></span> <span data-ttu-id="095ca-162">Die Standardnummer bestimmt einfach die maximale Anzahl von Nachrichten, die Sie beim Herstellen einer Verbindung mit einem Chatroom anfänglich sehen.</span><span class="sxs-lookup"><span data-stu-id="095ca-162">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="095ca-p118">Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).</span><span class="sxs-lookup"><span data-stu-id="095ca-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="095ca-166">Diese Einstellung wird auf dem Server erzwungen, da benutzerdefinierte Anwendungen oder vorherige Gruppen-Chat-Clients (Office Communications Server 2007 R2 &nbsp; -Gruppen-Chat Server oder lync Server 2010, Gruppen-Chat) Dateien in einem Raum bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="095ca-166">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="095ca-167">Wenn Sie über eine reine lync 2013-Bereitstellung oder einen lync 2013-Client verfügen, ist der lync 2013-Client nicht in der Lage, Dateien in einem beständigen Chat Server-Chatroom zu Posten.</span><span class="sxs-lookup"><span data-stu-id="095ca-167">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="095ca-168">Wählen Sie in der **Teilnehmer Aktualisierungs Grenze** das Limit für Teilnehmer Updates aus.</span><span class="sxs-lookup"><span data-stu-id="095ca-168">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="095ca-169">Der beständige Chat Server sendet Dienstplan Informationen (die mit einem Chatroom verbunden sind) an alle Teilnehmer, bis die Anzahl der verbundenen Nutzer diese Nummer erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="095ca-169">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="095ca-170">Standardmäßig ist die Nummer 75.</span><span class="sxs-lookup"><span data-stu-id="095ca-170">By default, the number is 75.</span></span> <span data-ttu-id="095ca-171">Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum an, über die der beständige Chat Server keine Dienstplan Updates mehr an verbundene Clients sendet, die im Chatroom anwesend sind.</span><span class="sxs-lookup"><span data-stu-id="095ca-171">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="095ca-p121">Wählen Sie unter **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte Bereitstellung der Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und lediglich die Standardeinstellung verwenden möchten, können Sie diese Option leer lassen.</span><span class="sxs-lookup"><span data-stu-id="095ca-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="095ca-175">Wenn Sie Ihre Raum Erstellungs Erfahrung anpassen und ihren spezifischen geschäftsworkflow einbeziehen möchten, können Sie eine benutzerdefinierte Raum Verwaltungslösung erstellen, indem Sie den beständigen Chat Server Software Development Kit (SDK) verwenden, ihn an einer beliebigen Stelle hosten und die URL hier platzieren.</span><span class="sxs-lookup"><span data-stu-id="095ca-175">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="095ca-176">Diese URL wird an den Client gesendet, damit ein Benutzer, der versucht, einen Raum anzuzeigen/zu erstellen, an Ihre benutzerdefinierte Raum Verwaltungslösung weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="095ca-176">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="095ca-177">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="095ca-177">Click **Commit**.</span></span>

<span data-ttu-id="095ca-178"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="095ca-178"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

