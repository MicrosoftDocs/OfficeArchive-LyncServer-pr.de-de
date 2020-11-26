---
title: Anfordern und Konfigurieren eines Zertifikats für den HTTP-Reverseproxy
description: Anfordern und Konfigurieren eines Zertifikats für den Reverse http-Proxy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdeaa080e3ccb6a9895e18a6ac02084e99a1e33e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49442747"
---
# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="ccd82-103">Anfordern und Konfigurieren eines Zertifikats für den HTTP-Reverseproxy in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccd82-103">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="ccd82-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="ccd82-104">

<span> </span></span></span>

<span data-ttu-id="ccd82-105">_**Letztes Änderungsdatum des Themas:** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="ccd82-105">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="ccd82-106">Sie müssen das Zertifikat der Stammzertifizierungsstelle auf dem Server mit Microsoft Forefront Threat Management Gateway 2010 oder IIS arr für die Zertifizierungsstellen-Infrastruktur installieren, die die Serverzertifikate für die internen Server mit Microsoft lync Server 2013 ausgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="ccd82-106">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="ccd82-107">Sie müssen auch ein öffentliches Webserverzertifikat auf dem Reverse Proxy Server installieren.</span><span class="sxs-lookup"><span data-stu-id="ccd82-107">You also must install a public web server certificate on your reverse proxy server.</span></span> <span data-ttu-id="ccd82-108">Die alternativen Namen dieses Zertifikats sollten die veröffentlichten externen vollqualifizierten Domänennamen (FQDNs) der einzelnen Pools enthalten, die für Remotezugriff aktivierte Benutzer sind, und die externen FQDNs aller Directors-oder Director-Pools, die innerhalb dieser Edge-Infrastruktur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ccd82-108">This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure.</span></span> <span data-ttu-id="ccd82-109">Der Alternative Name des Antragstellers muss auch die einfache URL der Besprechung, die einfache URL für Einwahl und, wenn Sie Mobile Anwendungen bereitstellen und die automatische Ermittlung verwenden möchten, die URL des externen AutoErmittlungsdiensts enthalten, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ccd82-109">The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="ccd82-110">Wert</span><span class="sxs-lookup"><span data-stu-id="ccd82-110">Value</span></span></th>
<th><span data-ttu-id="ccd82-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ccd82-111">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccd82-112">Name des Antragstellers</span><span class="sxs-lookup"><span data-stu-id="ccd82-112">Subject name</span></span></p></td>
<td><p><span data-ttu-id="ccd82-113">Pool-FQDN</span><span class="sxs-lookup"><span data-stu-id="ccd82-113">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="ccd82-114">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccd82-114">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd82-115">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="ccd82-115">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="ccd82-116">Pool-FQDN</span><span class="sxs-lookup"><span data-stu-id="ccd82-116">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="ccd82-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccd82-117">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="ccd82-118">Der Name des Antragstellers muss auch im alternativen Betreff vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="ccd82-118">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd82-119">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="ccd82-119">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="ccd82-120">Optionale Director-Webdienste (wenn Director bereitgestellt wird)</span><span class="sxs-lookup"><span data-stu-id="ccd82-120">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="ccd82-121">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccd82-121">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd82-122">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="ccd82-122">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="ccd82-123">Einfache URL für Besprechungen</span><span class="sxs-lookup"><span data-stu-id="ccd82-123">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="ccd82-124">Alle einfachen URLs der Besprechung müssen dem alternativen Betreff Namen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ccd82-124">All meeting simple URLs must be in the subject alternative name.</span></span> <span data-ttu-id="ccd82-125">Für jede SIP-Domäne muss mindestens eine einfache URL für die aktive Besprechung vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="ccd82-125">Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="ccd82-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccd82-126">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd82-127">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="ccd82-127">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="ccd82-128">Einfache URLs vom Typ „Dialin“</span><span class="sxs-lookup"><span data-stu-id="ccd82-128">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="ccd82-129">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccd82-129">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccd82-130">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="ccd82-130">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="ccd82-131">Office Web Apps-Server</span><span class="sxs-lookup"><span data-stu-id="ccd82-131">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="ccd82-132">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccd82-132">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccd82-133">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="ccd82-133">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="ccd82-134">URL des externen AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="ccd82-134">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="ccd82-135">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ccd82-135">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="ccd82-136">Wenn Sie auch Microsoft Exchange Server verwenden, müssen Sie auch Reverse-Proxy Regeln für die Exchange-Auto Ermittlungs-und Webdienste-URLs konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ccd82-136">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="ccd82-137">Wenn Ihre interne Bereitstellung aus mehr als einem Standard Edition-Server oder Front-End-Pool besteht, müssen Sie Webveröffentlichungsregeln für jeden FQDN der externen Webfarm konfigurieren, und Sie benötigen entweder ein Zertifikat und einen Weblistener für jede Person, oder Sie müssen ein Zertifikat abrufen, dessen Subjekt alternativer Name die von allen Pools verwendeten Namen enthält, und Sie einem Weblistener zuweisen , und teilen Sie Sie unter mehreren Webveröffentlichungsregeln.</span><span class="sxs-lookup"><span data-stu-id="ccd82-137">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="ccd82-138">Erstellen einer Zertifikatanforderung</span><span class="sxs-lookup"><span data-stu-id="ccd82-138">Create a Certificate Request</span></span>

<span data-ttu-id="ccd82-139">Sie erstellen eine Zertifikatanforderung auf dem Reverse-Proxy.</span><span class="sxs-lookup"><span data-stu-id="ccd82-139">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="ccd82-140">Wenn Sie eine Anforderung auf einem anderen Computer erstellen, müssen Sie das signierte Zertifikat mit dem privaten Schlüssel exportieren und dann auf den Reverseproxy importieren, nachdem Sie es von der öffentlichen Zertifizierungsstelle erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="ccd82-140">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ccd82-141">Eine Zertifikatanforderung oder eine Zertifikatsignaturanforderung (CSR) ist eine Anforderung an eine vertrauenswürdige öffentliche Zertifizierungsstelle, um den öffentlichen Schlüssel des anfordernden Computers zu überprüfen und zu signieren.</span><span class="sxs-lookup"><span data-stu-id="ccd82-141">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="ccd82-142">Wenn ein Zertifikat generiert wird, werden ein öffentlicher Schlüssel und ein privater Schlüssel erstellt.</span><span class="sxs-lookup"><span data-stu-id="ccd82-142">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="ccd82-143">Nur der öffentliche Schlüssel wird freigegeben und signiert.</span><span class="sxs-lookup"><span data-stu-id="ccd82-143">Only the public key is shared and signed.</span></span> <span data-ttu-id="ccd82-144">Wie der Name schon sagt, wird der öffentliche Schlüssel jeder öffentlichen Anforderung zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="ccd82-144">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="ccd82-145">Der öffentliche Schlüssel wird von Clients, Servern und anderen anfordernden Personen verwendet, die Informationen sicher austauschen und die Identität eines Computers überprüfen müssen.</span><span class="sxs-lookup"><span data-stu-id="ccd82-145">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="ccd82-146">Der private Schlüssel wird gesichert und nur von dem Computer verwendet, der das Schlüsselpaar zum Entschlüsseln von Nachrichten, die mit seinem öffentlichen Schlüssel verschlüsselt wurden, erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="ccd82-146">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="ccd82-147">Der private Schlüssel kann für andere Zwecke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ccd82-147">The private key can be used for other purposes.</span></span> <span data-ttu-id="ccd82-148">Für Reverse-Proxy-Zwecke ist die Datenverschlüsselung die hauptsächliche Verwendung.</span><span class="sxs-lookup"><span data-stu-id="ccd82-148">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="ccd82-149">In zweiter Linie ist die Zertifikatauthentifizierung auf der Zertifikatschlüssel Ebene eine andere Verwendung und ist nur auf die Überprüfung eingeschränkt, die ein Anforderer über den öffentlichen Schlüssel des Computers verfügt, oder dass der Computer, für den Sie über einen öffentlichen Schlüssel verfügen, tatsächlich der Computer ist, den er vorgibt.</span><span class="sxs-lookup"><span data-stu-id="ccd82-149">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="ccd82-150">Wenn Sie Ihre Edge-Server Zertifikate und ihre Reverse-Proxy Zertifikate gleichzeitig planen, sollten Sie feststellen, dass die beiden Zertifikatanforderungen sehr ähnlich sind.</span><span class="sxs-lookup"><span data-stu-id="ccd82-150">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="ccd82-151">Wenn Sie Ihr Edge-Server-Zertifikat konfigurieren und anfordern, kombinieren Sie den Edgeserver und die alternativen Namen des Reverse Proxy-Subjekts.</span><span class="sxs-lookup"><span data-stu-id="ccd82-151">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="ccd82-152">Sie können dasselbe Zertifikat für Ihren Reverseproxy verwenden, wenn Sie das Zertifikat und den privaten Schlüssel exportieren und die exportierte Datei in den Reverse-Proxy kopieren und dann das Zertifikat/Schlüsselpaar importieren und in den anstehenden Verfahren nach Bedarf zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ccd82-152">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="ccd82-153">Lesen Sie die Zertifikatanforderungen für den Edge &nbsp; -Server-<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan für Edge-Server-Zertifikate in lync Server 2013</A> und die <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Zusammenfassung des Reverse-Proxy Zertifikats – Reverse Proxy in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ccd82-153">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="ccd82-154">Stellen Sie sicher, dass Sie das Zertifikat mit einem exportierbaren privaten Schlüssel erstellen.</span><span class="sxs-lookup"><span data-stu-id="ccd82-154">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="ccd82-155">Das Erstellen des Zertifikats und der Zertifikatanforderung mit einem exportierbaren privaten Schlüssel ist für Pool-Edgeserver erforderlich, daher ist dies eine übliche Vorgehensweise, und der Zertifikat-Assistent im lync Server-Bereitstellungs-Assistenten für den Edgeserver ermöglicht es Ihnen, das exportierbare Kennzeichen <STRONG>privater Schlüssel machen</STRONG> zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ccd82-155">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="ccd82-156">Nachdem Sie die Zertifikatanforderung von der öffentlichen Zertifizierungsstelle zurück erhalten haben, werden Sie das Zertifikat und den privaten Schlüssel exportieren.</span><span class="sxs-lookup"><span data-stu-id="ccd82-156">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="ccd82-157">Informationen zum Erstellen und Exportieren Ihres Zertifikats mit einem privaten Schlüssel finden Sie im Abschnitt "So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool" im Thema <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Einrichten von Zertifikaten für die externe Edge-Schnittstelle für lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="ccd82-157">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="ccd82-158">Die Erweiterung des Zertifikats sollte vom Typ <STRONG>PFX</STRONG>sein.</span><span class="sxs-lookup"><span data-stu-id="ccd82-158">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="ccd82-159">Führen Sie die folgenden Schritte aus, um eine Zertifikatsignaturanforderung auf dem Computer zu generieren, auf dem das Zertifikat und der private Schlüssel zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="ccd82-159">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="ccd82-160">**Erstellen einer Zertifikatsignaturanforderung**</span><span class="sxs-lookup"><span data-stu-id="ccd82-160">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="ccd82-161">Öffnen Sie die Microsoft Management Console (MMC), fügen Sie das Zertifikat-Snap-in hinzu, wählen Sie **Computer** aus, und erweitern Sie dann **Personal**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-161">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="ccd82-162">Ausführliche Informationen zum Erstellen einer Certificates-Konsole in der Microsoft Management Console (MMC) finden Sie unter [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616) .</span><span class="sxs-lookup"><span data-stu-id="ccd82-162">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="ccd82-163">Klicken Sie mit der rechten Maustaste auf **Zertifikate**, klicken Sie auf **alle Aufgaben**, klicken Sie auf **Erweiterte Vorgänge**, klicken Sie auf **Benutzerdefinierte Anforderung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-163">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="ccd82-164">Klicken Sie auf der Seite **Zertifikatregistrierung** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-164">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="ccd82-165">Wählen Sie auf der Seite **Zertifikatregistrierungsrichtlinie auswählen** unter **Benutzerdefinierte Anforderung** die Option **ohne Registrierungsrichtlinie fortfahren** aus.</span><span class="sxs-lookup"><span data-stu-id="ccd82-165">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="ccd82-166">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-166">Click **Next**.</span></span>

5.  <span data-ttu-id="ccd82-167">Klicken Sie auf der Seite **Benutzerdefinierte Anforderung** für **Vorlage** auf **Legacy Schlüssel (ohne Vorlage)**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-167">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="ccd82-168">Wenn Ihr Zertifikatanbieter nichts anderes anwendet, Belasse die Option **Standarderweiterungen** deaktivieren und die Auswahl des **Anforderungs Formats** in **PKCS \# 10**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-168">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="ccd82-169">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-169">Click **Next**.</span></span>

6.  <span data-ttu-id="ccd82-170">Klicken Sie auf der Seite **Zertifikatinformationen** auf **Details**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-170">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="ccd82-171">Geben Sie auf der Seite " **Zertifikateigenschaften** " auf der Registerkarte **Allgemein** im Feld **Anzeigename** einen Namen für dieses Zertifikat ein.</span><span class="sxs-lookup"><span data-stu-id="ccd82-171">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="ccd82-172">Geben Sie optional im Feld **Beschreibung** eine Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="ccd82-172">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="ccd82-173">Der Anzeige Name und die Beschreibung werden in der Regel vom Administrator verwendet, um zu ermitteln, was der Zertifikatszweck ist, beispielsweise den **Reverse Proxy-Listener für lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-173">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="ccd82-174">Wählen Sie die Registerkarte **Betreff** aus. Wählen Sie unter **Antragstellername** für den **Typ** den Eintrag **allgemeiner Name** für den Typ des Antragstellernamens aus.</span><span class="sxs-lookup"><span data-stu-id="ccd82-174">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="ccd82-175">Geben Sie für den **Wert** den Namen des Antragstellers ein, den Sie für den Reverse-Proxy verwenden möchten, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-175">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="ccd82-176">In dem Beispiel, das in der Tabelle in diesem Thema bereitgestellt wird, lautet der Name des Antragstellers Webext.contoso.com und wird in das Feld Wert für den Namen des Antragstellers eingegeben.</span><span class="sxs-lookup"><span data-stu-id="ccd82-176">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="ccd82-177">Wählen Sie auf der Registerkarte **Betreff** unter **alternativer Name** in der Dropdownliste für **Typ** die Option **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="ccd82-177">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="ccd82-178">Geben Sie für jeden definierten Betreff-alternativen Namen, den Sie für das Zertifikat benötigen, den vollqualifizierten Domänennamen ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-178">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="ccd82-179">In der Tabelle gibt es beispielsweise drei alternative Namen für Subjekte, Meet.contoso.com, dialin.contoso.com und lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ccd82-179">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="ccd82-180">Geben Sie im Feld **Wert** Meet.contoso.com ein, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-180">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="ccd82-181">Wiederholen Sie diesen Vorgang für jeden alternativen Betreff, den Sie definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="ccd82-181">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="ccd82-182">Klicken Sie auf der Seite **Zertifikateigenschaften** auf die Registerkarte **Erweiterungen** . Auf dieser Seite definieren Sie die kryptografischen Schlüssel Zwecke in der **Schlüsselverwendung** und die erweiterte Schlüsselverwendung in der **erweiterten Schlüsselverwendung (Anwendungsrichtlinien)**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-182">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="ccd82-183">Klicken Sie auf den Pfeil für die **Schlüsselverwendung** , um die **verfügbaren Optionen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ccd82-183">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="ccd82-184">Klicken Sie unter Verfügbare Optionen auf **digitale Signatur**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-184">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="ccd82-185">Klicken Sie auf **Schlüssel Verschlüsselung**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-185">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="ccd82-186">Aktivieren Sie das Kontrollkästchen, wenn das Kontrollkästchen für die **kritische Verwendung von Schlüsseln verwenden** deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ccd82-186">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="ccd82-187">Klicken Sie auf den Pfeil **Erweiterte Schlüsselverwendung (Anwendungsrichtlinien)** , um die **verfügbaren Optionen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ccd82-187">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="ccd82-188">Klicken Sie unter Verfügbare Optionen auf **Server Authentifizierung** und dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-188">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="ccd82-189">Klicken Sie auf **Client Authentifizierung** und dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-189">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="ccd82-190">Wenn das Kontrollkästchen für **die kritische Verwendung der erweiterten Schlüsselverwendung** aktiviert ist, deaktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="ccd82-190">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="ccd82-191">Im Gegensatz zum Kontrollkästchen "Schlüsselverwendung" (das überprüft werden muss) müssen Sie sicherstellen, dass das Kontrollkästchen Erweiterte Schlüsselverwendung nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ccd82-191">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="ccd82-192">Klicken Sie auf der Seite **Zertifikateigenschaften** auf die Registerkarte **privater Schlüssel** . Klicken Sie auf den Pfeil mit den **Schlüsseloptionen** .</span><span class="sxs-lookup"><span data-stu-id="ccd82-192">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="ccd82-193">Wählen Sie für **Schlüsselgröße** in der Dropdownliste **2048** aus.</span><span class="sxs-lookup"><span data-stu-id="ccd82-193">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="ccd82-194">Wenn Sie dieses Schlüsselpaar und CSR auf einem anderen Computer als dem umgekehrten Proxy generieren, für den dieses Zertifikat vorgesehen ist, wählen Sie exportierbarer **privater Schlüssel erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="ccd82-194">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" /><span data-ttu-id="ccd82-196">Sicherheitshinweis:</span><span class="sxs-lookup"><span data-stu-id="ccd82-196">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="ccd82-197">Wenn Sie in einer Farm mehr als einen Reverse Proxy haben, werden Sie in der Regel darauf hingewiesen, <strong>dass</strong> Sie das Zertifikat und den privaten Schlüssel auf jeden Computer in der Farm kopieren.</span><span class="sxs-lookup"><span data-stu-id="ccd82-197">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="ccd82-198">Wenn Sie einen exportierbaren privaten Schlüssel zulassen, müssen Sie mit dem Zertifikat und dem Computer, auf dem er erstellt wird, besonders vorsichtig vorgehen.</span><span class="sxs-lookup"><span data-stu-id="ccd82-198">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="ccd82-199">Wenn der private Schlüssel beeinträchtigt wird, wird das Zertifikat unbrauchbar, und der Computer oder Computer können dem externen Zugriff und anderen Sicherheitsrisiken ausgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ccd82-199">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="ccd82-200">Klicken Sie auf der Registerkarte **privater Schlüssel** auf den Pfeil des **Tasten Typs** .</span><span class="sxs-lookup"><span data-stu-id="ccd82-200">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="ccd82-201">Wählen Sie die Option **Exchange** aus.</span><span class="sxs-lookup"><span data-stu-id="ccd82-201">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="ccd82-202">Klicken Sie auf **OK** , um die von Ihnen festgelegten **Zertifikateigenschaften** zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ccd82-202">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="ccd82-203">Klicken Sie auf der Seite **Zertifikatregistrierung** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-203">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="ccd82-204">Auf der Seite **wo möchten Sie die Offlineanforderung speichern?** werden Sie aufgefordert, einen **Dateinamen** und ein **Datei Format** zum Speichern der Zertifikatsignaturanforderung einzugeben.</span><span class="sxs-lookup"><span data-stu-id="ccd82-204">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="ccd82-205">Geben Sie im Feld Dateiname den Pfad und den Datei **Namen** für die Anforderung ein, oder klicken Sie auf **Durchsuchen** , um einen Speicherort für die Datei auszuwählen, und geben Sie den Dateinamen für die Anforderung ein.</span><span class="sxs-lookup"><span data-stu-id="ccd82-205">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="ccd82-206">Klicken Sie im Feld **Dateiformat** entweder auf **Basis 64** oder **Binär**.</span><span class="sxs-lookup"><span data-stu-id="ccd82-206">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="ccd82-207">Wählen Sie **Basis 64** aus, es sei denn, Sie werden vom Hersteller anderweitig für Ihre Zertifikate angewiesen.</span><span class="sxs-lookup"><span data-stu-id="ccd82-207">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="ccd82-208">Suchen Sie die Anforderungsdatei, die Sie im vorherigen Schritt gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="ccd82-208">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="ccd82-209">An Ihre öffentliche Zertifizierungsstelle übermitteln.</span><span class="sxs-lookup"><span data-stu-id="ccd82-209">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="ccd82-210">Microsoft hat öffentliche Zertifizierungsstellen identifiziert, die den Anforderungen für Unified Communications-Zwecke entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ccd82-210">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="ccd82-211">Eine Liste wird im folgenden Knowledge Base-Artikel verwaltet.</span><span class="sxs-lookup"><span data-stu-id="ccd82-211">A list is maintained in the following knowledge base article.</span></span> <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    <span data-ttu-id="ccd82-212"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="ccd82-212"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

