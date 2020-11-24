---
title: Veröffentlichen von Office Web Apps Server mithilfe eines Reverseproxyservers
description: Veröffentlichen von Office Web Apps Server mit einem Reverse-Proxy Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 888399e315d90624ba41e23e173fa33813a92b43
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394554"
---
# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="f1f2e-103">Veröffentlichen von Office Web Apps Server in lync Server 2013 mit einem Reverse Proxy Server</span><span class="sxs-lookup"><span data-stu-id="f1f2e-103">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="f1f2e-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="f1f2e-104">

<span> </span></span></span>

<span data-ttu-id="f1f2e-105">_**Letztes Änderungsdatum des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="f1f2e-105">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="f1f2e-106">Wenn Sie externe Benutzer (also Benutzer, die sich außerhalb der Firewall Ihrer Organisation anmelden) für den Zugriff auf Office Web Apps Server PowerPoint-Präsentationen verwenden möchten, müssen Sie Office Web Apps Server und einen Reverse Proxy Server wie Microsoft Forefront Threat Management Gateway verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-106">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="f1f2e-107">Das bedeutet auch, dass Sie eine Website Veröffentlichungsregel erstellen und konfigurieren müssen. Mithilfe dieser Regel wird sichergestellt, dass Benutzer eine Verbindung mit dem Server herstellen können.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-107">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="f1f2e-108">Wenn Sie keinen Zugriff auf externe Benutzer bereitstellen müssen, müssen Sie keine Veröffentlichungsregel für Websites konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-108">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="f1f2e-109">Führen Sie die folgenden Schritte aus, um eine Website Veröffentlichungsregel im Forefront Threat Management-Gateway zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f1f2e-109">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="f1f2e-110">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Forefront TMG**, und klicken Sie dann auf **Forefront TMG-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-110">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="f1f2e-111">Klicken Sie in Forefront TMG mit der rechten Maustaste auf **Firewall-Richtlinie**, zeigen Sie auf **neu**, und klicken Sie dann auf **Website Veröffentlichungsregel**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-111">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="f1f2e-112">Geben Sie im Assistenten für neue Webveröffentlichungsregel auf der Seite **Willkommen bei der neuen Webveröffentlichungsregel-Assistent** einen Namen für die neue Regel in das Feld **Name der Webveröffentlichungs** Regel ein (beispielsweise **Office Web Apps-Server Regel**), und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-112">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="f1f2e-113">Wählen Sie auf der Seite **Regelaktion angeben** die Option **zulassen** aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-113">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="f1f2e-114">Wählen Sie auf der Seite **Veröffentlichungs** **eine einzelne Website oder ein Lastenausgleichsmodul veröffentlichen** aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-114">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="f1f2e-115">Wählen Sie auf der Seite **Server Verbindungssicherheit** die Option SSL verwenden aus, um **eine Verbindung mit dem veröffentlichten Webserver oder der Serverfarm herzustellen** , und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-115">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="f1f2e-116">Geben Sie auf der Seite **interne Veröffentlichungs Details** den FQDN Ihres Office Web Apps-Servers (beispielsweise **officewebapps01.contoso.com**) in das Feld **interner Websitename** ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-116">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**.</span></span> <span data-ttu-id="f1f2e-117">Der Name, der im Feld **interner Websitename** eingegeben wurde, muss im Feld Betreff oder im Feld Subject Alternative Name des Zertifikats angezeigt werden, das Sie Office Web Apps Server zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-117">The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="f1f2e-118">Geben Sie auf der Seite **interne Veröffentlichungs Details** **/ \* *_ in das Feld _* Path (optional)** ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-118">On the **Internal Publishing Details** page, type **/\**_ in the _\* Path (optional)*\* box and then click **Next**.</span></span> <span data-ttu-id="f1f2e-119">Mit der/- \* Syntax wird sichergestellt, dass alle Ordner und Unterordner der Website veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-119">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="f1f2e-120">Wählen Sie auf der Seite Details für den **öffentlichen Namen** diesen Domänennamen aus der Dropdownliste **Accept Request for** **(Typ below)** aus, und geben Sie dann im Feld öffentlicher Name den vollqualifizierten für Ihren Office Web Apps-Server ein.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-120">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="f1f2e-121">Dieser Name sollte der Name sein, der für den Zugriff auf Ihre Website verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-121">This name should be the name used to access your website.</span></span> <span data-ttu-id="f1f2e-122">Wenn Sie beispielsweise über die URL auf Ihre Website zugreifen, http://officewebapps01.contoso.com sollten Sie **officewebapps01.contoso.com** in das Feld **Öffentlicher Name** eingeben.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-122">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="f1f2e-123">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-123">Click **Next**.</span></span>

11. <span data-ttu-id="f1f2e-124">Klicken Sie auf der Seite **Weblistener auswählen** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-124">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="f1f2e-125">Geben Sie im Assistenten für neue Weblistener-Definition einen Namen für den neuen Weblistener (beispielsweise **SSL**) in das Feld **Weblistener-Name** ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-125">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="f1f2e-126">Wählen Sie auf der Seite **Client Verbindungssicherheit** die Option **SSL-gesicherte Verbindungen mit Clients anfordern** aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-126">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="f1f2e-127">Wählen Sie auf der Seite **Weblistener-IP-Adressen** die Option **extern** aus, wählen Sie **intern** aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-127">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="f1f2e-128">Wählen Sie auf der Seite **Listener SSL-Zertifikate** die Option **einzelnes Zertifikat für diesen Weblistener verwenden** aus, und klicken Sie dann auf **Zertifikat auswählen**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-128">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="f1f2e-129">Wählen Sie im Dialogfeld **Zertifikat auswählen** das für diesen Weblistener zu verwendende Zertifikat aus, und klicken Sie dann auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-129">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="f1f2e-130">Klicken Sie auf der Seite **Listener SSL-Zertifikate** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-130">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="f1f2e-131">Wählen Sie auf der Seite **Authentifizierungseinstellungen** in der Dropdown **Liste Wählen Sie aus, wie Clients Anmeldeinformationen für Forefront TMG bereitstellen** die Option **keine Authentifizierung** aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-131">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="f1f2e-132">Klicken Sie auf der Seite **Einstellungen für einmaliges Anmelden** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-132">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="f1f2e-133">Überprüfen Sie auf der Seite zum **abschließen des neuen Weblistener-Assistenten** die Zusammenfassung der von Ihnen vorgenommenen Konfigurationsoptionen.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-133">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made.</span></span> <span data-ttu-id="f1f2e-134">Wenn Sie fertig sind, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-134">When ready, click **Finish**.</span></span>

21. <span data-ttu-id="f1f2e-135">Klicken Sie auf der Seite **Weblistener auswählen** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-135">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="f1f2e-136">Wählen Sie auf der Seite **Authentifizierungsdelegierung** die Option **keine Delegierung aus, aber der Client kann sich direkt** über die **Option wählen Sie die Methode aus, die von Forefront TMG für die Authentifizierung bei der veröffentlichten Web Server** -Dropdownliste verwendet wird, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-136">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="f1f2e-137">Überprüfen Sie auf der Seite **Benutzersätze** , ob die entsprechenden Benutzersätze aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-137">On the **User Sets** page, confirm that the appropriate user sets are listed.</span></span> <span data-ttu-id="f1f2e-138">Standardmäßig ist dies der Benutzersatz **alle Benutzer** .</span><span class="sxs-lookup"><span data-stu-id="f1f2e-138">By default, this is the **All Users** user set.</span></span> <span data-ttu-id="f1f2e-139">Klicken Sie auf **Hinzufügen** , um andere Benutzergruppen hinzuzufügen, die Sie möglicherweise definiert haben.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-139">Click **Add** to add other user sets you may have defined.</span></span> <span data-ttu-id="f1f2e-140">Wenn Sie fertig sind, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-140">When complete, click **Next**.</span></span>

24. <span data-ttu-id="f1f2e-141">Klicken Sie auf der Seite zum **Abschließen der neuen Webveröffentlichungsregel** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-141">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="f1f2e-142">Beachten Sie, dass das Klicken auf " **Fertig stellen** " nicht bedeutet, dass Sie den Vorgang abgeschlossen haben. Das bedeutet, dass dies nicht automatisch angewendet wird und die neue Regel aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-142">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule.</span></span> <span data-ttu-id="f1f2e-143">Stattdessen müssen Sie auf die Schaltfläche "über **nehmen** " klicken, die auf der Forefront TMG-Benutzeroberfläche angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-143">Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface.</span></span> <span data-ttu-id="f1f2e-144">Wenn Sie auf über **nehmen** klicken, wird das Dialogfeld **Beschreibung der Konfigurationsänderung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-144">When you click **Apply** the **Configuration Change Description** dialog box will appear.</span></span> <span data-ttu-id="f1f2e-145">Klicken Sie in diesem Dialogfeld auf über **nehmen** , um die neue Veröffentlichungsregel zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-145">Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="f1f2e-146">Nachdem die neue Regel angewendet wurde, müssen Sie einige kleinere Änderungen an der Regel vornehmen, um sicherzustellen, dass die Benutzer die neuen PowerPoint-Präsentationsfunktionen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-146">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="f1f2e-147">Verwenden Sie dazu das folgende Verfahren:</span><span class="sxs-lookup"><span data-stu-id="f1f2e-147">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="f1f2e-148">Klicken Sie in Forefront TMG mit der rechten Maustaste auf den Namen der neuen Veröffentlichungsregel, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-148">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="f1f2e-149">Wählen Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **an** die Option **Weiterleiten des ursprünglichen Hostheaders statt des eigentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-149">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="f1f2e-150">Klicken Sie auf der Registerkarte **Datenverkehr** auf **Filtern** , und klicken Sie dann auf **http konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-150">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="f1f2e-151">Deaktivieren Sie im Dialogfeld **http-Richtlinie für Regel konfigurieren** das Kontrollkästchen **Normalisierung über** prüfen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-151">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="f1f2e-152">Klicken Sie im Dialogfeld **Eigenschaften** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-152">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="f1f2e-153">Klicken Sie in Forefront TMG auf über **nehmen** , um die Änderungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-153">In Forefront TMG, click **Apply** to enable the changes.</span></span> <span data-ttu-id="f1f2e-154">Wenn das Dialogfeld **Beschreibung der Konfigurationsänderung** angezeigt wird, klicken Sie auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-154">When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="f1f2e-155">Nach Abschluss der Installation können Sie Ihren Office Web Apps-Server mit den Verfahren im Thema über [Prüfen der Konfiguration von Office Web Apps Server in lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)testen.</span><span class="sxs-lookup"><span data-stu-id="f1f2e-155">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

<span data-ttu-id="f1f2e-156"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="f1f2e-156"></div>

<span> </span>

</div>

</div>

</span></span></div>

