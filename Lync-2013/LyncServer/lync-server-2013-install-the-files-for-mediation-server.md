---
title: 'Lync Server 2013: Installieren der Dateien für den Vermittlungsserver'
description: 'Lync Server 2013: Installieren Sie die Dateien für den Vermittlungsserver.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1fc20fb91328d116a4aee62b96b95aa3e270eb
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427145"
---
# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="c5d4e-103">Installieren der Dateien für den Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5d4e-103">Install the files for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="c5d4e-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="c5d4e-104">

<span> </span></span></span>

<span data-ttu-id="c5d4e-105">_**Letztes Änderungsdatum des Themas:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="c5d4e-105">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="c5d4e-106">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als lokaler Administrator beim Server angemeldet sein und ein Domänenbenutzerkonto verwenden, das mindestens Mitglied der Gruppe „RTCUniversalReadOnlyAdmins“ ist.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-106">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="c5d4e-107">Führen Sie die Schritte in diesem Thema aus, um den Bereitstellungs-Assistenten für lync Server 2013 auszuführen, um die Dateien für den Vermittlungsserver auf einem Computer zu installieren, den Sie einem Mediationsserver Pool hinzugefügt haben, als Sie den Pool mithilfe von Topologie-Generator definiert und veröffentlicht haben.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-107">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="c5d4e-108">Wenn Sie den Mediationsserver für Dateien installieren, können Sie auch das für jeden Computer in einem vermittlungsserverpool erforderliche Zertifikat installieren und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-108">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="c5d4e-109">Wenn Sie auf dieser Website bereits Vermittlungsserver bereitgestellt haben, die sich auf den Front-End-Pools oder dem Standard Edition-Server befinden, können Sie dieses Thema überspringen und stattdessen die [Konfiguration von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-109">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c5d4e-110">In diesem Thema wird davon ausgegangen, dass Sie bereits einen eigenständigen vermittlungsserverpool definiert und veröffentlicht haben, wie unter <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Definieren eines Vermittlungsservers im Topologie-Generator in lync Server 2013</A> und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben ist. und dass Sie überprüft haben, dass die Computer im Vermittlungs Server Pool die Voraussetzungen erfüllen, die unter <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software Voraussetzungen für Enterprise-VoIP in lync Server 2013</A> und <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Sicherheits-und Konfigurationsvoraussetzungen für Enterprise-VoIP in lync Server 2013</A>beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-110">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="c5d4e-111">So installieren Sie die Dateien für einen eigenständigen Vermittlungsserverpool</span><span class="sxs-lookup"><span data-stu-id="c5d4e-111">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="c5d4e-112">Klicken Sie auf dem Installationsmedium mit der rechten Maustaste auf \<installation media\> **\\ Setup \\ amd64 \\Setup.exe**, und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-112">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="c5d4e-113">Klicken Sie auf der Seite **Installationsspeicherort** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-113">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="c5d4e-p102">Klicken Sie auf der Seite **Endbenutzer-Lizenzvertrag** auf **Ich stimme zu** und klicken Sie anschließend auf **OK**. (Dieser Schritt ist erforderlich, um fortfahren zu können.)</span><span class="sxs-lookup"><span data-stu-id="c5d4e-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>

4.  <span data-ttu-id="c5d4e-116">Klicken Sie auf der Seite mit dem **Bereitstellungs-Assistenten von lync Server 2010** auf **lync Server System installieren oder aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-116">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="c5d4e-117">Klicken Sie neben **Schritt 1: Lokalen Konfigurationsspeicher installieren** auf **Ausführen** und folgen Sie den Anweisungen auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-117">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="c5d4e-118">Übernehmen Sie auf der Seite **Lokales Replikat des zentralen Verwaltungsspeichers konfigurieren** die Standardeinstellung **Direkt aus zentralem Verwaltungsspeicher abrufen** und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-118">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="c5d4e-119">Wenn der Taskstatus auf der Seite **Befehle ausführen** als **Abgeschlossen** angezeigt wird, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="c5d4e-120">Klicken Sie neben **Schritt 2: Einrichten oder Entfernen von lync Server-Komponenten** auf **Ausführen**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-120">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="c5d4e-121">Wenn der Taskstatus auf der Seite **Befehle ausführen** als **Abgeschlossen** angezeigt wird, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-121">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="c5d4e-p103">Klicken Sie neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Ausführen**. Folgen Sie den Anweisungen auf dem Bildschirm und übernehmen Sie die Standardeinstellungen. Da der Vermittlungsserver ein Zertifikat benötigt, müssen Sie **Schritt 3** zweimal ausführen: einmal zum Ausstellen und noch einmal zum Zuweisen des erforderlichen Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="c5d4e-125">Wenn das Zertifikat ordnungsgemäß ausgestellt und zugewiesen wurde, klicken Sie neben **Schritt 4: Dienste starten** auf **Ausführen** und folgen Sie den Anweisungen auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-125">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="c5d4e-126">Wenn **Schritt 4** erfolgreich abgeschlossen wurde, starten Sie den Server neu und melden Sie sich als Mitglied der Gruppe „Domänen-Admins“ an.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-126">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="c5d4e-127">Überprüfen Sie auf dem Computer, auf dem Sie die lync Server-Systemsteuerung ausführen, auf der Seite **Topologie** der lync Server-Systemsteuerung, dass der Dienststatus des Vermittlungsservers als grünes Häkchen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-127">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="c5d4e-128">Wenn ein rotes X angezeigt wird, wählen Sie den Vermittlungsserver aus.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-128">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="c5d4e-129">Klicken Sie im Menü **Aktion** auf **Alle Dienste starten**.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-129">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="c5d4e-130">Wenn Sie dem vermittlungsserverpool mehr als einen Computer hinzugefügt haben, führen Sie die Schritte in diesem Verfahren auf allen anderen Computern im vermittlungsserverpool aus.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-130">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="c5d4e-131">Wenn Sie keine Dateien für den Vermittlungsserver für andere Computer installieren müssen, führen Sie die Verfahren unter [Konfigurieren von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md) aus, um die Einstellungen für die trunk-Verbindung zwischen diesem vermittlungsserverpool (oder allen Vermittlungsservern an einem Standort) und seinem Peer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c5d4e-131">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5d4e-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5d4e-132">See Also</span></span>


[<span data-ttu-id="c5d4e-133">Anforderungen an Zertifikate für interne Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5d4e-133">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

<span data-ttu-id="c5d4e-134"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="c5d4e-134"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

