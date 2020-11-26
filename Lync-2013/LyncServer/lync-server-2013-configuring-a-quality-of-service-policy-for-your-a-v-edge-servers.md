---
title: Konfigurieren einer Quality of Service-Richtlinie für Ihre a/V-Edgeserver
description: Konfigurieren einer Quality of Service-Richtlinie für Ihre a/V-Edgeserver
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ec1f012260aa32df984925a86882a3201e07db0
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433507"
---
# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="bc288-103">Konfigurieren einer Quality of Service-Richtlinie für Ihre a/V-Edgeserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc288-103">Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="bc288-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="bc288-104">

<span> </span></span></span>

<span data-ttu-id="bc288-105">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="bc288-105">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="bc288-106">Zusätzlich zum Erstellen von QoS-Richtlinien für Ihre Konferenz-, Anwendungs-und Vermittlungsserver müssen Sie auch Audio-und Video Richtlinien für die interne Seite Ihrer A/V-Edgeserver erstellen.</span><span class="sxs-lookup"><span data-stu-id="bc288-106">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="bc288-107">Die auf Ihren Edgeserver verwendeten Richtlinien unterscheiden sich jedoch von den Richtlinien, die auf Ihren Konferenz-, Anwendungs-und Vermittlungsservern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bc288-107">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="bc288-108">Für Konferenz-, Anwendungs-und Vermittlungsserver haben Sie einen Quellportbereich angegeben. bei Edge-Servern müssen Sie einen Ziel Portbereich angeben.</span><span class="sxs-lookup"><span data-stu-id="bc288-108">For the Conferencing, Application, and Mediation servers you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="bc288-109">Aus diesem Grund können Sie die QoS-Richtlinien für Konferenz-, Anwendungs-und Vermittlungsserver nicht einfach auf Ihre Edge-Server anwenden: Diese Richtlinien funktionieren einfach nicht.</span><span class="sxs-lookup"><span data-stu-id="bc288-109">Because of that you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="bc288-110">Stattdessen müssen Sie neue Richtlinien erstellen und diese Richtlinien nur auf Ihre Edgeserver anwenden.</span><span class="sxs-lookup"><span data-stu-id="bc288-110">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="bc288-111">Im folgenden Verfahren wird das Verfahren zum Erstellen von Active Directory-Gruppenrichtlinienobjekten beschrieben, die zum Verwalten von Quality of Service auf Edge-Servern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="bc288-111">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="bc288-112">Natürlich ist es möglich, dass Ihre Edgeserver eigenständige Server sind, die keine Active Directory-Konten haben.</span><span class="sxs-lookup"><span data-stu-id="bc288-112">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="bc288-113">Wenn dies der Fall ist, können Sie anstelle der Active Directory-Gruppenrichtlinie lokale Gruppenrichtlinien verwenden: der einzige Unterschied besteht darin, dass Sie diese lokalen Richtlinien mit dem Editor für lokale Gruppenrichtlinien erstellen müssen, und Sie müssen einzeln denselben Satz von Richtlinien auf jedem Edgeserver erstellen.</span><span class="sxs-lookup"><span data-stu-id="bc288-113">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="bc288-114">Gehen Sie wie folgt vor, um den Editor für lokale Gruppenrichtlinien auf einem Edgeserver zu starten:</span><span class="sxs-lookup"><span data-stu-id="bc288-114">To start the Local Group Policy Editor on an Edge server do the following:</span></span>

1.  <span data-ttu-id="bc288-115">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bc288-115">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="bc288-116">Geben Sie im Dialogfeld **Ausführen** den Text **gpedit. msc** ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="bc288-116">In the **Run** dialog box, type **gpedit.msc** and then press ENTER.</span></span>

<span data-ttu-id="bc288-117">Wenn Sie Active Directory-basierte Richtlinien erstellen, sollten Sie sich an einem Computer anmelden, auf dem die Gruppenrichtlinienverwaltung installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="bc288-117">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="bc288-118">Öffnen Sie in diesem Fall die Gruppenrichtlinienverwaltung (Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**), und führen Sie dann die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bc288-118">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following steps:</span></span>

1.  <span data-ttu-id="bc288-119">Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bc288-119">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="bc288-120">Wenn sich beispielsweise alle lync Server-Computer in einer Organisationseinheit mit dem Namen lync Server befinden, sollte die neue Richtlinie in der lync Server-Organisationseinheit erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="bc288-120">For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="bc288-121">Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt in dieser Domäne erstellen, und verknüpfen Sie es hier**.</span><span class="sxs-lookup"><span data-stu-id="bc288-121">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="bc288-122">Geben Sie im Dialogfeld **neues GPO** im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein (beispielsweise **lync Server-Audio**), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc288-122">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="bc288-123">Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bc288-123">Right-click the newly-created policy and then click **Edit**.</span></span>

<span data-ttu-id="bc288-124">Von hier aus ist der Prozess identisch, unabhängig davon, ob Sie eine Active Directory-Richtlinie oder eine lokale Richtlinie erstellen:</span><span class="sxs-lookup"><span data-stu-id="bc288-124">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="bc288-125">Erweitern Sie im Gruppenrichtlinien-Verwaltungs-Editor oder im Editor für lokale Gruppenrichtlinien **Computer Konfiguration**, erweitern Sie **Richtlinien**, erweitern Sie **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bc288-125">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="bc288-126">Geben Sie im Dialogfeld **richtlinienbasierte QoS** auf der Seite öffnen in das Feld **Name** einen Namen für die neue Richtlinie (beispielsweise **lync Server-Audio**) ein.</span><span class="sxs-lookup"><span data-stu-id="bc288-126">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="bc288-127">Wählen Sie **DSCP-Wert angeben** aus, und legen Sie den Wert auf **46** fest.</span><span class="sxs-lookup"><span data-stu-id="bc288-127">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="bc288-128">Geben Sie die **ausgehende Drosselungs Rate** nicht ausgewählt ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="bc288-128">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="bc288-129">Stellen Sie auf der nächsten Seite sicher, dass **alle Anwendungen** ausgewählt ist, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="bc288-129">On the next page, make sure that **All applications** is selected and then click **Next**.</span></span> <span data-ttu-id="bc288-130">Mit dieser Einstellung wird das Netzwerk angewiesen, nach allen Paketen mit einer DSCP-Kennzeichnung von 46 zu suchen, nicht nur von Paketen, die von einer bestimmten Anwendung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="bc288-130">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="bc288-131">Stellen Sie auf der dritten Seite sicher, dass sowohl **eine Quell-IP-Adresse** als auch **eine beliebige Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="bc288-131">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="bc288-132">Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, auf welchem Computer (IP-Adresse) diese Pakete gesendet werden und auf welchem Computer (IP-Adresse) diese Pakete empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="bc288-132">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="bc288-133">Wählen Sie auf Seite 4 **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet werden soll** .</span><span class="sxs-lookup"><span data-stu-id="bc288-133">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="bc288-134">TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von lync Server und seinen Clientanwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bc288-134">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

6.  <span data-ttu-id="bc288-135">Wählen Sie unter der Überschrift **die Zielportnummer** aus, und wählen Sie **aus diesem Ziel Port oder-Bereich aus**.</span><span class="sxs-lookup"><span data-stu-id="bc288-135">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="bc288-136">Geben Sie im Feld Begleittext den Portbereich ein, der für Audioübertragungen reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="bc288-136">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="bc288-137">Wenn Sie beispielsweise Ports 49152 über Ports 57500 für den Audioverkehr reserviert haben, geben Sie den Portbereich mit folgendem Format ein: **49152:57500**.</span><span class="sxs-lookup"><span data-stu-id="bc288-137">For example, if you reserved ports 49152 through ports 57500 for audio traffic then enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="bc288-138">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="bc288-138">Click **Finish**.</span></span>

<span data-ttu-id="bc288-139">Nachdem Sie die QoS-Richtlinie für den Audioverkehr erstellt haben, sollten Sie eine zweite Richtlinie für den Videoverkehr erstellen.</span><span class="sxs-lookup"><span data-stu-id="bc288-139">After you have created the QoS policy for audio traffic you should create a second policy for video traffic.</span></span> <span data-ttu-id="bc288-140">Wenn Sie eine Richtlinie für Video erstellen möchten, führen Sie die gleichen grundlegenden Verfahren aus, die Sie beim Erstellen der audiorichtlinie befolgt haben, indem Sie diese Substitutionen vornehmen:</span><span class="sxs-lookup"><span data-stu-id="bc288-140">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="bc288-141">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **lync Server-Video**).</span><span class="sxs-lookup"><span data-stu-id="bc288-141">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="bc288-142">Setzen Sie den DSCP-Wert auf **34** statt auf 46.</span><span class="sxs-lookup"><span data-stu-id="bc288-142">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="bc288-143">(Beachten Sie, dass Sie keinen DSCP-Wert von 34 verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="bc288-143">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="bc288-144">Die einzige Voraussetzung ist, dass Sie einen anderen DSCP-Wert für Video verwenden, als Sie für Audio verwendet haben.)</span><span class="sxs-lookup"><span data-stu-id="bc288-144">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="bc288-145">Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="bc288-145">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="bc288-146">Wenn Sie beispielsweise Ports 57501 bis 65535 für Video reserviert haben, setzen Sie den Portbereich auf Folgendes: **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="bc288-146">For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="bc288-147">Dies sollte wiederum als Ziel Portbereich konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="bc288-147">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="bc288-148">Wenn Sie sich entscheiden, eine Richtlinie für die Verwaltung des Anwendungsfreigabe Datenverkehrs zu erstellen, müssen Sie eine dritte Richtlinie erstellen, indem Sie die folgenden Ersetzungen vornehmen:</span><span class="sxs-lookup"><span data-stu-id="bc288-148">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="bc288-149">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise die **lync Server-Anwendungsfreigabe**).</span><span class="sxs-lookup"><span data-stu-id="bc288-149">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="bc288-150">Setzen Sie den DSCP-Wert auf **24** anstatt auf 46.</span><span class="sxs-lookup"><span data-stu-id="bc288-150">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="bc288-151">(Sie müssen wiederum keinen DSCP-Wert von 24 verwenden.</span><span class="sxs-lookup"><span data-stu-id="bc288-151">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="bc288-152">Die einzige Voraussetzung ist, dass Sie einen anderen DSCP-Wert für die Anwendungsfreigabe verwenden, als Sie für Audio oder Video verwendet haben.)</span><span class="sxs-lookup"><span data-stu-id="bc288-152">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="bc288-153">Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="bc288-153">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="bc288-154">Wenn Sie beispielsweise Ports 40803 bis 49151 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich auf this: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="bc288-154">For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="bc288-155">Die neu erstellten Richtlinien werden erst wirksam, nachdem die Gruppenrichtlinien auf Ihren Edge-Servern aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="bc288-155">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="bc288-156">Die Gruppenrichtlinien werden zwar automatisch regelmäßig aktualisiert, aber Sie können die sofortige Aktualisierung erzwingen. Dazu führen Sie auf allen Computern, auf denen die Gruppenrichtlinien aktualisiert werden sollen, den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bc288-156">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="bc288-157">Dieser Befehl kann auf dem lync-Server oder in einem beliebigen Befehlsfenster, das unter Administratoranmeldeinformationen ausgeführt wird, ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bc288-157">This command can be run from within the Lync Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="bc288-158">Um ein Befehlsfenster mit Administratoranmeldeinformationen auszuführen, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bc288-158">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="bc288-159">Beachten Sie, dass Sie den Edge-Server möglicherweise auch nach dem Ausführen von Gpudate.exe neu starten müssen.</span><span class="sxs-lookup"><span data-stu-id="bc288-159">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="bc288-160">Wenn Sie sicherstellen möchten, dass Netzwerkpakete mit dem entsprechenden DSCP-Wert gekennzeichnet sind, sollten Sie auch einen neuen Registrierungseintrag auf jedem Computer erstellen, indem Sie das folgende Verfahren ausführen:</span><span class="sxs-lookup"><span data-stu-id="bc288-160">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="bc288-161">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bc288-161">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="bc288-162">Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit** ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="bc288-162">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="bc288-163">Erweitern Sie im Registrierungs-Editor **HKEY \_ lokaler \_ Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="bc288-163">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="bc288-164">Klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Taste**.</span><span class="sxs-lookup"><span data-stu-id="bc288-164">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="bc288-165">Nachdem der neue Registrierungsschlüssel erstellt wurde, geben Sie **QoS** ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="bc288-165">After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="bc288-166">Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**.</span><span class="sxs-lookup"><span data-stu-id="bc288-166">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="bc288-167">Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden** ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="bc288-167">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="bc288-168">Doppelklicken Sie auf **keine Verwendung von NLA**.</span><span class="sxs-lookup"><span data-stu-id="bc288-168">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="bc288-169">Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten den Wert** **1** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc288-169">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="bc288-170">Schließen Sie den Registrierungs-Editor, und starten Sie den Computer neu.</span><span class="sxs-lookup"><span data-stu-id="bc288-170">Close the Registry Editor and then reboot your computer.</span></span>

<span data-ttu-id="bc288-171"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="bc288-171"></div>

<span> </span>

</div>

</div>

</span></span></div>

