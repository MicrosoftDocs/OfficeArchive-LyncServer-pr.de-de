---
title: 'Lync Server 2013: Konfigurieren von Zertifikaten auf dem Server, auf dem Microsoft Exchange Server Unified Messaging ausgeführt wird'
description: 'Lync Server 2013: Konfigurieren Sie Zertifikate auf dem Server, auf dem Microsoft Exchange Server Unified Messaging ausgeführt wird.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a7d1e0aec3ec36723ee68c0a1dcd7f60050f9ea
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49395155"
---
# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="b60ca-103">Konfigurieren von Zertifikaten auf dem Server, auf dem Microsoft Exchange Server Unified Messaging ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="b60ca-103">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="b60ca-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="b60ca-104">

<span> </span></span></span>

<span data-ttu-id="b60ca-105">_**Letztes Änderungsdatum des Themas:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="b60ca-105">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="b60ca-106">Wenn Sie Exchange Unified Messaging (um) bereitgestellt haben, wie unter [Planen der Integration von Exchange Unified Messaging in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in der Planning-Dokumentation beschrieben, und Sie Exchange um-Features für Enterprise-VoIP-Benutzer in Ihrer Organisation bereitstellen möchten, können Sie die folgenden Verfahren verwenden, um das Zertifikat auf dem Server mit Exchange um zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b60ca-106">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b60ca-107">Für interne Zertifikate müssen sowohl auf den Servern mit lync Server 2013 als auch auf den Servern, auf denen Microsoft Exchange ausgeführt wird, vertrauenswürdige Stammzertifizierungsstellen Zertifikate vorhanden sein, die gegenseitig vertrauenswürdig sind.</span><span class="sxs-lookup"><span data-stu-id="b60ca-107">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="b60ca-108">Die Zertifizierungsstelle (Certification Authority, ca) kann entweder dieselbe oder eine andere Zertifizierungsstelle sein, sofern die Server das Stammzertifikat der Zertifizierungsstelle im Zertifikatspeicher der vertrauenswürdigen Stammzertifizierungsstelle registriert haben.</span><span class="sxs-lookup"><span data-stu-id="b60ca-108">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="b60ca-109">Der Exchange-Server muss mit einem Server Zertifikat konfiguriert sein, um eine Verbindung mit lync Server 2013 herzustellen:</span><span class="sxs-lookup"><span data-stu-id="b60ca-109">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="b60ca-110">Laden Sie das Zertifizierungsstellenzertifikat für den Exchange-Server herunter.</span><span class="sxs-lookup"><span data-stu-id="b60ca-110">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="b60ca-111">Installieren Sie das Zertifizierungsstellenzertifikat für den Exchange-Server.</span><span class="sxs-lookup"><span data-stu-id="b60ca-111">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="b60ca-112">Überprüfen Sie, ob sich die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen des Exchange-Servers befindet.</span><span class="sxs-lookup"><span data-stu-id="b60ca-112">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="b60ca-113">Erstellen Sie eine Zertifikatanforderung für den Exchange-Server, und installieren Sie das Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="b60ca-113">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="b60ca-114">Weisen Sie das Zertifikat für den Exchange-Server zu.</span><span class="sxs-lookup"><span data-stu-id="b60ca-114">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="b60ca-115">So laden Sie das Zertifizierungsstellenzertifikat herunter</span><span class="sxs-lookup"><span data-stu-id="b60ca-115">To download the CA certificate</span></span>

1.  <span data-ttu-id="b60ca-116">Klicken Sie auf dem Server, auf dem Exchange um ausgeführt wird, auf **Start**, klicken Sie auf **Ausführen**, geben Sie **http:// \<name of your Issuing CA Server\> /certsrv** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-116">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="b60ca-117">Klicken Sie unter **Aufgabe auswählen** auf **Zertifizierungsstellenzertifikat, Zertifikatkette oder CRL Herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-117">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="b60ca-118">Wählen Sie unter **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer CRL** **die Option Encoding method to base 64** aus, und klicken Sie dann auf **CA-Zertifikat herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-118">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b60ca-119">Sie können in diesem Schritt auch die Codierungsregeln (Distinguished Encoding Rules, der) angeben.</span><span class="sxs-lookup"><span data-stu-id="b60ca-119">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="b60ca-120">Wenn Sie der Codierung auswählen, lautet der Dateityp im nächsten Schritt dieses Verfahrens und in Schritt 10 der <STRONG>Installation des Zertifizierungsstellenzertifikats</STRONG> P7B statt. cer.</span><span class="sxs-lookup"><span data-stu-id="b60ca-120">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="b60ca-121">Klicken Sie im Dialogfeld **Datei Download** auf **Speichern**, und speichern Sie die Datei auf der Festplatte auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="b60ca-121">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="b60ca-122">(Abhängig von der Codierung, die Sie im vorherigen Schritt ausgewählt haben, weist die Datei entweder eine CER-oder eine P7B-Dateierweiterung auf.)</span><span class="sxs-lookup"><span data-stu-id="b60ca-122">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="b60ca-123">So installieren Sie das Zertifizierungsstellenzertifikat</span><span class="sxs-lookup"><span data-stu-id="b60ca-123">To install the CA certificate</span></span>

1.  <span data-ttu-id="b60ca-124">Öffnen Sie auf dem Server, auf dem Exchange um ausgeführt wird, Microsoft Management Console (MMC), indem Sie auf **Start** klicken, auf **Ausführen** klicken, **MMC** in das Feld **Öffnen** eingeben und dann auf **OK** klicken.</span><span class="sxs-lookup"><span data-stu-id="b60ca-124">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="b60ca-125">Klicken Sie im Menü **Datei** auf **Snap-in hinzufügen/entfernen**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-125">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="b60ca-126">Klicken Sie im Feld **eigenständige Snap-Ins hinzufügen** auf **Zertifikate**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-126">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="b60ca-127">Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-127">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="b60ca-128">Überprüfen Sie im Dialogfeld **Computer auswählen** , ob das Kontrollkästchen **lokaler Computer: (Computer, auf dem diese Konsole ausgeführt wird)** aktiviert ist, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-128">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="b60ca-129">Klicken Sie auf **Schließen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-129">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="b60ca-130">Erweitern Sie in der Konsolenstruktur **Zertifikate (lokaler Computer)**, erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**, und klicken Sie dann auf **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-130">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="b60ca-131">Klicken Sie mit der rechten Maustaste auf **Zertifikate**, klicken Sie auf **alle Aufgaben**, und klicken Sie auf **importieren**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-131">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="b60ca-132">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-132">Click **Next**.</span></span>

10. <span data-ttu-id="b60ca-133">Klicken Sie auf **Durchsuchen** , um nach der Datei zu suchen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-133">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="b60ca-134">(Abhängig von der Codierung, die Sie in Schritt 3 **zum Herunterladen des CA-Zertifikats** ausgewählt haben, wird die Datei entweder eine CER-oder eine P7B-Dateierweiterung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b60ca-134">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="b60ca-135">Klicken Sie **im folgenden Store auf alle Zertifikate** speichern.</span><span class="sxs-lookup"><span data-stu-id="b60ca-135">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="b60ca-136">Klicken Sie auf **Durchsuchen**, und wählen Sie dann **Vertrauenswürdige Stammzertifizierungsstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="b60ca-136">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="b60ca-137">Klicken Sie auf **weiter** , um die Einstellungen zu überprüfen, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-137">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="b60ca-138">So überprüfen Sie, ob sich die Zertifizierungsstelle in der Liste vertrauenswürdiger Stammzertifizierungsstellen befindet</span><span class="sxs-lookup"><span data-stu-id="b60ca-138">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="b60ca-139">Erweitern Sie auf dem Server, auf dem Exchange um ausgeführt wird, in MMC **Zertifikate (lokaler Computer)**, erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**, und klicken Sie dann auf **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-139">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="b60ca-140">Überprüfen Sie im Detailbereich, ob sich Ihre Zertifizierungsstelle in der Liste der vertrauenswürdigen CAS befindet.</span><span class="sxs-lookup"><span data-stu-id="b60ca-140">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="b60ca-141">So konfigurieren Sie Exchange Server 2013 um mit lync Server</span><span class="sxs-lookup"><span data-stu-id="b60ca-141">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="b60ca-142">Ausführliche Informationen finden Sie unter "integrieren von Exchange 2013 um mit lync Server" in die Exchange Server [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) -Dokumentation unter.</span><span class="sxs-lookup"><span data-stu-id="b60ca-142">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="b60ca-143">So erstellen Sie eine Zertifikatanforderung und installieren das Zertifikat auf Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="b60ca-143">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="b60ca-144">Klicken Sie auf dem Server, auf dem Exchange um ausgeführt wird, auf **Start**, klicken Sie auf **Ausführen**, geben Sie **http:// \<**name of your Issuing CA Server**\> /certsrv** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-144">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<**name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="b60ca-145">Klicken Sie unter **Aufgabe auswählen** auf **Zertifikat anfordern**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-145">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="b60ca-146">Klicken Sie unter **Zertifikat anfordern** auf **Erweiterte Zertifikatanforderung**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-146">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="b60ca-147">Klicken Sie unter **Erweiterte Zertifikatanforderung** auf **erstellen, und senden Sie eine Anforderung an diese Zertifizierungsstelle**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-147">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="b60ca-148">Wählen Sie unter **Erweiterte Zertifikatanforderung** die Option **Webserver** oder eine andere Serverzertifikatvorlage aus, die für die Serverauthentifizierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="b60ca-148">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="b60ca-149">Geben Sie unter **identifizierende Informationen für die Offline Vorlage** im Feld **Name** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Exchange-Servers ein.</span><span class="sxs-lookup"><span data-stu-id="b60ca-149">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b60ca-150">Sie müssen den FQDN des Exchange-Servers eingeben, damit die Kommunikation funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b60ca-150">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="b60ca-151">Klicken Sie unter **Schlüsseloptionen** auf das Kontrollkästchen **Zertifikat im Zertifikatspeicher des lokalen Computers speichern** .</span><span class="sxs-lookup"><span data-stu-id="b60ca-151">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="b60ca-152">Klicken Sie unten auf der Webseite auf die Schaltfläche " **senden** ".</span><span class="sxs-lookup"><span data-stu-id="b60ca-152">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="b60ca-153">Klicken Sie in dem Dialogfeld, das zur Bestätigung aufgefordert wird, auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="b60ca-154">Klicken Sie auf der Seite Zertifikat ausgestellt unter **Zertifikat ausgestellt** auf **dieses Zertifikat installieren**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-154">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="b60ca-155">Klicken Sie in dem Dialogfeld, das zur Bestätigung aufgefordert wird, auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-155">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="b60ca-156">Überprüfen Sie, ob die Meldung "Ihr neues Zertifikat wurde erfolgreich installiert" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b60ca-156">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="b60ca-157">So erstellen Sie ein Zertifikat auf Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="b60ca-157">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="b60ca-158">Melden Sie sich mit den entsprechenden Benutzerrechten beim Server mit Exchange um an.</span><span class="sxs-lookup"><span data-stu-id="b60ca-158">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="b60ca-159">Ausführliche Informationen finden Sie unter "Client Zugriffsberechtigungen" unter [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) .</span><span class="sxs-lookup"><span data-stu-id="b60ca-159">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="b60ca-160">Die folgenden Verfahren zum Erstellen des Zertifikats finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="b60ca-160">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="b60ca-161">"Erstellen eines neuen Exchange-Zertifikats" unter [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="b60ca-161">"Create a New Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="b60ca-162">"Importieren eines Exchange-Zertifikats" unter [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="b60ca-162">"Import an Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b60ca-163">Für den Namen des Zertifikat <STRONG>Antragstellers</STRONG>müssen Sie den FQDN des Exchange-Servers eingeben, damit die Kommunikation funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b60ca-163">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="b60ca-164">So weisen Sie das Zertifikat auf Exchange Server 2007 (SP1) zu</span><span class="sxs-lookup"><span data-stu-id="b60ca-164">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="b60ca-165">Öffnen Sie auf dem Server, auf dem Exchange um ausgeführt wird, MMC.</span><span class="sxs-lookup"><span data-stu-id="b60ca-165">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="b60ca-166">Erweitern Sie in der Konsolenstruktur **Personal** , und klicken Sie dann auf **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="b60ca-166">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="b60ca-167">Überprüfen Sie im Detailbereich, ob persönliches Zertifikat angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b60ca-167">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="b60ca-168">Doppelklicken Sie auf das Zertifikat, um dessen Details zu lesen und sicherzustellen, dass es gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b60ca-168">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b60ca-169">Es kann einige Minuten dauern, bis das Zertifikat als gültig angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b60ca-169">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="b60ca-170">Starten Sie den Microsoft Exchange Unified Messaging-Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="b60ca-170">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b60ca-171">Der Server mit Exchange Server 2007 SP1 Unified Messaging ruft automatisch das richtige Zertifikat ab.</span><span class="sxs-lookup"><span data-stu-id="b60ca-171">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="b60ca-172">Öffnen Sie die Ereignisanzeige, und suchen Sie nach der Ereignis-ID 1112, die das Zertifikat angibt, das der Server mit Exchange Server 2007 SP1 Unified Messaging abgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="b60ca-172">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="b60ca-173">So weisen Sie das Zertifikat auf Exchange Server 2010 zu</span><span class="sxs-lookup"><span data-stu-id="b60ca-173">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="b60ca-174">Melden Sie sich mit den entsprechenden Benutzerrechten beim Server mit Exchange um an.</span><span class="sxs-lookup"><span data-stu-id="b60ca-174">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="b60ca-175">Ausführliche Informationen finden Sie unter "Client Zugriffsberechtigungen" unter [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) .</span><span class="sxs-lookup"><span data-stu-id="b60ca-175">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="b60ca-176">Eine Vorgehensweise zum Zuweisen des Zertifikats finden Sie unter "Zuweisen von Diensten zu einem Zertifikat" unter [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497) .</span><span class="sxs-lookup"><span data-stu-id="b60ca-176">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

<span data-ttu-id="b60ca-177"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="b60ca-177"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

