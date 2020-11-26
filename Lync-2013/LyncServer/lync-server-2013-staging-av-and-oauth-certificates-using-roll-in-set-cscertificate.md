---
title: Staging von AV-und OAuth-Zertifikaten mithilfe von-Rolle in Set-CsCertificate
description: Staging von AV-und OAuth-Zertifikaten mithilfe von-Rolle in der Gruppe-CsCertificate.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3732c4adb4327cc1e4111307ab2d72ed080cf221
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49423781"
---
# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a><span data-ttu-id="2fa6c-103">Staging von AV-und OAuth-Zertifikaten in lync Server 2013 mithilfe von-Rolle in Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="2fa6c-103">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="2fa6c-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="2fa6c-104">

<span> </span></span></span>

<span data-ttu-id="2fa6c-105">_**Letztes Änderungsdatum des Themas:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="2fa6c-105">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="2fa6c-106">Audio/Video (a/V)-Kommunikation ist eine wichtige Komponente von Microsoft lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-106">Audio/Video (A/V) communications is a key component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="2fa6c-107">Features wie Anwendungsfreigabe und Audio-und Videokonferenzen basieren auf den Zertifikaten, die dem a/v-Edgedienst, insbesondere dem a/v-Authentifizierungsdienst, zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-107">Features such as application sharing and audio and video conferencing rely on the certificates assigned to the A/V Edge service, specifically the A/V Authentication service.</span></span>

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P><span data-ttu-id="2fa6c-108">Dieses neue Feature ist für den A/V-Edgedienst und das <EM>OAuthTokenIssuer</EM> -Zertifikat konzipiert.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-108">This new feature is designed to work for the A/V Edge service and the <EM>OAuthTokenIssuer</EM> certificate.</span></span> <span data-ttu-id="2fa6c-109">Andere Zertifikattypen können zusammen mit dem a/v-Edgedienst und dem OAuth-Zertifikattyp bereitgestellt werden, profitieren aber nicht vom Koexistenzsystem, das vom a/v-Edgedienst-Zertifikat bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-109">Other certificate types can be provisioned along with the A/V Edge service and OAuth certificate type, but will not benefit from the coexistence behavior that the A/V Edge service certificate will.</span></span></P>
> <LI>
> <P><span data-ttu-id="2fa6c-110">Die in der lync Server-Verwaltungsshell verwendeten PowerShell-Cmdlets für die Verwaltung von Microsoft lync Server 2013-Zertifikaten bezieht sich auf das A/V-Edgedienst Zertifikat als <EM>AudioVideoAuthentication</EM> -Zertifikattyp und das OAuthServer-Zertifikat als Typ <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-110">The Lync Server Management Shell PowerShell cmdlets used to manage Microsoft Lync Server 2013 certificates refers to the A/V Edge service certificate as the <EM>AudioVideoAuthentication</EM> certificate type and the OAuthServer certificate as type <EM>OAuthTokenIssuer</EM>.</span></span> <span data-ttu-id="2fa6c-111">Im restlichen Thema – und zur eindeutigen Identifizierung der Zertifikate – wird mit demselben ID-Typ, <EM>AudioVideoAuthentication</EM> und <EM>OAuthTokenIssuer</EM>, auf sie verwiesen.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-111">For the rest of this topic and to uniquely identify the certificates, they will be referred to by the same identifier type, <EM>AudioVideoAuthentication</EM> and <EM>OAuthTokenIssuer</EM>.</span></span></P></LI></OL>



</div>

<span data-ttu-id="2fa6c-112">Der a/v-Authentifizierungsdienst ist für das Ausgeben von Token verantwortlich, die von Clients und anderen a/v-Consumern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-112">The A/V Authentication service is responsible for issuing tokens that are used by clients and other A/V consumers.</span></span> <span data-ttu-id="2fa6c-113">Die Token werden aus Attributen auf dem Zertifikat generiert, und wenn das Zertifikat abläuft, führt dies zu einem Verbindungsabbruch und einer Anforderung, erneut mit einem neuen Token zu verbinden, das vom neuen Zertifikat generiert wird.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-113">The tokens are generated from attributes on the certificate, and when the certificate expires, loss of connection and requirement to rejoin with a new token generated by the new certificate will result.</span></span> <span data-ttu-id="2fa6c-114">Ein neues Feature in lync Server 2013 wird dieses Problem lindern – die Möglichkeit, ein neues Zertifikat im Vorfeld des alten zu inszenieren, das abläuft und es ermöglicht, dass beide Zertifikate während eines bestimmten Zeitraums weiterhin funktionieren.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-114">A new feature in Lync Server 2013 will alleviate this problem – the ability to stage a new certificate in advance of the old one expiring and allowing both certificates to continue to function for a period of time.</span></span> <span data-ttu-id="2fa6c-115">Dieses Feature verwendet aktualisierte Funktionen im Set-CsCertificate-Cmdlet der lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-115">This feature uses updated functionality in the Set-CsCertificate Lync Server Management Shell cmdlet.</span></span> <span data-ttu-id="2fa6c-116">Mit dem neuen Parameter – Rolle, mit dem vorhandenen Parameter – EffectiveDate, wird das neue AudioVideoAuthentication-Zertifikat im Zertifikatspeicher platziert.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-116">The new parameter –Roll, with the existing parameter –EffectiveDate, will place the new AudioVideoAuthentication certificate in the certificate store.</span></span> <span data-ttu-id="2fa6c-117">Das ältere AudioVideoAuthentication-Zertifikat bleibt für ausgestellte Token weiterhin gültig.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-117">The older AudioVideoAuthentication certificate will still remain for issued tokens to be validated against.</span></span> <span data-ttu-id="2fa6c-118">Beginnend mit dem Setzen des neuen AudioVideoAuthentication-Zertifikats wird die folgende Reihe von Ereignissen auftreten:</span><span class="sxs-lookup"><span data-stu-id="2fa6c-118">Beginning with putting the new AudioVideoAuthentication certificate in place, the following series of events will occur:</span></span>

<div>


> [!TIP]
> <span data-ttu-id="2fa6c-119">Mithilfe der lync Server-Verwaltungsshell-Cmdlets für die Verwaltung von Zertifikaten können Sie für jeden Zweck auf dem Edgeserver getrennte und unterschiedliche Zertifikate anfordern.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-119">Using the Lync Server Management Shell cmdlets for managing certificates, you can request separate and distinct certificates for each purpose on the Edge Server.</span></span> <span data-ttu-id="2fa6c-120">Die Verwendung des Zertifikat-Assistenten im lync Server-Bereitstellungs-Assistenten unterstützt Sie beim Erstellen von Zertifikaten, ist in der Regel aber der <STRONG>Standardtyp</STRONG> , mit dem alle Zertifikat Verwendungen für den Edgeserver auf einem einzigen Zertifikat kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-120">Using the Certificate Wizard in the Lync Server Deployment Wizard assists you in creating certificates, but is typically of the <STRONG>default</STRONG> type which couples all certificate uses for the Edge Server onto a single certificate.</span></span> <span data-ttu-id="2fa6c-121">Die empfohlene Vorgehensweise bei Verwendung der Funktion für rollende Zertifikate besteht darin, das AudioVideoAuthentication-Zertifikat von den anderen Zertifikatzwecken zu lösen.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-121">The recommended practice if you are going to use the rolling certificate feature is to decouple the AudioVideoAuthentication certificate from the other certificate purposes.</span></span> <span data-ttu-id="2fa6c-122">Sie können ein Zertifikat vom Typ „Standard“ bereitstellen, doch nur der AudioVideoAuthentication-Teil des kombinierten Zertifikats profitiert von dem Staging.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-122">You can provision and stage a certificate of the Default type, but only the AudioVideoAuthentication portion of the combined certificate will benefit from the staging.</span></span> <span data-ttu-id="2fa6c-123">Ein Benutzer, der an (beispielsweise) einer Sofortnachrichtenunterhaltung teilhat, wenn das Zertifikat abläuft, muss sich abmelden und wieder anmelden, um das neue Zertifikat zu verwenden, das dem Access Edge-Dienst zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-123">A user involved in (for example) an instant messaging conversation when the certificate expires will need to log out and log back in to make use of the new certificate associated with the Access Edge service.</span></span> <span data-ttu-id="2fa6c-124">Ein ähnliches Verhalten tritt für einen Benutzer ein, der mit dem Webkonferenz-Edgedienst an einer Webkonferenz teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-124">Similar behavior will occur for a user involved in a Web conference using the Web Conferencing Edge service.</span></span> <span data-ttu-id="2fa6c-125">Das OAuthTokenIssuer-Zertifikat ist ein bestimmter Typ, der auf allen Servern freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-125">The OAuthTokenIssuer certificate is a specific type that is shared across all servers.</span></span> <span data-ttu-id="2fa6c-126">Sie erstellen und verwalten das Zertifikat an einer zentralen Stelle, und das Zertifikat wird im zentralen Verwaltungsspeicher für alle anderen Server gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-126">You create and manage the certificate in one place and the certificate is stored in the Central Management store for all other servers.</span></span>



</div>

<span data-ttu-id="2fa6c-p106">Zusätzliche Informationen werden benötigt, um die Optionen und Anforderungen bei der Verwendung des Set-CsCertificate-Cmdlets zum Bereitstellen von Zertifikaten vor dem Ablauf des aktuellen Zertifikats nachvollziehen zu können. Der Parameter „–Roll“ ist wichtig, dient jedoch nur einem Zweck. Wenn Sie ihn als Parameter festlegen, informieren Sie damit „Set-CsCertificate“, dass Sie Informationen zum betroffenen durch „–Type“ definierten Zertifikat (z. B. AudioVideoAuthentication und OAuthTokenIssuer) bereitstellen werden, wenn es am durch „–EffectiveDate“ definierten Zeitpunkt gültig wird.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-p106">Additional detail is needed to fully understand your options and requirements when using the Set-CsCertificate cmdlet and using it to stage certificates prior to the current certificate expiring. The –Roll parameter is important, but essentially single purpose. If you define it as a parameter, you are telling Set-CsCertificate that you will be providing information about the certificate that will be affected defined by –Type (for example AudioVideoAuthentication and OAuthTokenIssuer), when the certificate will become effective defined by –EffectiveDate.</span></span>

<span data-ttu-id="2fa6c-130">**-Rolle:** Der-Rolle-Parameter ist erforderlich und weist Abhängigkeiten auf, die zusammen mit ihm bereitgestellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-130">**-Roll:** The –Roll parameter is required and has dependencies that must be supplied along with it.</span></span> <span data-ttu-id="2fa6c-131">Parameter, die zum Festlegen der betroffenen Zertifikate und ihrer Anwendungsweise erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="2fa6c-131">Required parameters to fully define which certificates will be affected and how they will be applied:</span></span>

<span data-ttu-id="2fa6c-132">**-EffectiveDate:** Der Parameter – EffectiveDate definiert, wann das neue Zertifikat mit dem aktuellen Zertifikat gemeinsam aktiv wird.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-132">**-EffectiveDate:** The parameter –EffectiveDate defines when the new certificate will become co-active with the current certificate.</span></span> <span data-ttu-id="2fa6c-133">Die – EffectiveDate kann in der Nähe der Ablaufzeit des aktuellen Zertifikats liegen, oder es kann einen längeren Zeitraum dauern.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-133">The –EffectiveDate can be close to the expiry time of the current certificate, or it can be a longer period of time.</span></span> <span data-ttu-id="2fa6c-134">Ein Empfohlenes Mindest-EffectiveDate für das AudioVideoAuthentication-Zertifikat wäre 8 Stunden, was die standardmäßige Token-Lebensdauer für AV-Edgedienst-Token ist, die mit dem AudioVideoAuthentication-Zertifikat ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-134">A recommended minimum –EffectiveDate for the AudioVideoAuthentication certificate would be 8 hours, which is the default token lifetime for AV Edge service tokens issued using the AudioVideoAuthentication certificate.</span></span>

<span data-ttu-id="2fa6c-p109">Für das Bereitstellen der OAuthTokenIssuer-Zertifikate liegen verschiedene Anforderungen für die Vorlaufzeit vor, bevor das Zertifikat wirksam werden kann. Der Mindestwert des OAuthTokenIssuer-Zertifikats für die Vorlaufzeit sollte 24 Stunden vor der Ablaufzeit des aktuellen Zertifikats betragen. Die erweiterte Vorlaufzeit für die Koexistenz ist durch andere Serverrollen begründet, die von dem OAuthTokenIssuer-Zertifikat (beispielsweise Exchange Server) abhängen, das eine längere Aufbewahrungszeit für durch Zertifikate erstellte Authentifizierungs- und Verschlüsselungsschlüsselelemente besitzt.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-p109">When staging OAuthTokenIssuer certificates, there are different requirements for the lead time before the certificate can become effective. The minimum time that the OAuthTokenIssuer certificate should have for its lead time is 24 hours before the expiration time of the current certificate. The extended lead time for the coexistence is because of other server roles that are dependent on the OAuthTokenIssuer certificate (Exchange Server, for example) which has a longer retention time for certificate created authentication and encryption key materials.</span></span>

<span data-ttu-id="2fa6c-138">**-Fingerabdruck:** Der Fingerabdruck ist ein Attribut des Zertifikats, das für dieses Zertifikat eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-138">**-Thumbprint:** The thumbprint is an attribute on the certificate that is unique to that certificate.</span></span> <span data-ttu-id="2fa6c-139">Mit dem Parameter „–Thumbprint“ wird das Zertifikat ermittelt, das von den Aktionen des Cmdlets „Set-CsCertificate“ betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-139">The –Thumbprint parameter is used to identify the certificate that will be affected by the actions of the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="2fa6c-140">**-Geben Sie Folgendes ein:** Der Parameter – Type kann einen einzelnen Zertifikat Verwendungstyp oder eine durch trennzeichengetrennte Liste der Zertifikat Verwendungstypen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-140">**-Type:** The –Type parameter can accept a single certificate usage type or a comma separated list of certificate usage types.</span></span> <span data-ttu-id="2fa6c-141">Die Zertifikattypen geben für das Cmdlet und den Server an, worin der Zweck des Zertifikats besteht.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-141">The certificate types are those that identify to the cmdlet and to the server what the purpose of the certificate is.</span></span> <span data-ttu-id="2fa6c-142">Geben Sie beispielsweise AudioVideoAuthentication ein, um den A/V-Edgedienst und den AV-Authentifizierungsdienst zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-142">For example, type AudioVideoAuthentication is for use by the A/V Edge service and the AV Authentication service.</span></span> <span data-ttu-id="2fa6c-143">Wenn Sie verschiedene Zertifikattypen zum gleichen Zeitpunkt bereitstellen möchten, müssen Sie die längste effektive Mindestvorlaufzeit für die Zertifikate berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-143">If you decide to stage and provision certificates of a different type at the same time, you must consider the longest required minimum effective lead time for the certificates.</span></span> <span data-ttu-id="2fa6c-144">Sie müssen beispielsweise Zertifikate vom Typ „AudioVideoAuthentication“ und vom Typ „OAuthTokenIssuer“ bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-144">For example, you need to stage certificates of type AudioVideoAuthentication and OAuthTokenIssuer.</span></span> <span data-ttu-id="2fa6c-145">Als Mindestwert muss für „-EffectiveDate“ der höhere Wert der beiden Zertifikate festgelegt werden, in diesem Fall der Wert des Zertifikats „OAuthTokenIssuer“, dessen Mindestvorlaufzeit 24 Stunden beträgt.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-145">Your minimum –EffectiveDate must be the greater of the two certificates, in this case the OAuthTokenIssuer, which has a minimum lead time of 24 hours.</span></span> <span data-ttu-id="2fa6c-146">Wenn Sie das Zertifikat „AudioVideoAuthentication“ nicht mit einer Vorlaufzeit von 24 Stunden bereitstellen möchten, stellen Sie es separat mit einem Ihren Anforderungen entsprechenden Wert für „EffectiveDate“ bereit.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-146">If you do not want to stage the AudioVideoAuthentication certificate with a lead time of 24 hours, stage it separately with an EffectiveDate that is more to your requirements.</span></span>

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="2fa6c-147">So aktualisieren oder erneuern Sie ein a/V-Edgedienst-Zertifikat mit einem – Rollen-und-EffectiveDate-Parameter</span><span class="sxs-lookup"><span data-stu-id="2fa6c-147">To update or renew an A/V Edge service certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="2fa6c-148">Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-148">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="2fa6c-149">Fordern Sie ein Erneuerungs-oder neues AudioVideoAuthentication-Zertifikat mit exportier barem privaten Schlüssel für das vorhandene Zertifikat im a/V-Edgedienst an.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-149">Request a renewal or new AudioVideoAuthentication certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="2fa6c-150">Importieren Sie das neue AudioVideoAuthentication-Zertifikat auf den Edgeserver und alle anderen Edgeserver in Ihrem Pool (wenn Sie einen Pool bereitgestellt haben).</span><span class="sxs-lookup"><span data-stu-id="2fa6c-150">Import the new AudioVideoAuthentication certificate to the Edge Server and all other Edge Server in your pool (if you have a pool deployed).</span></span>

4.  <span data-ttu-id="2fa6c-151">Konfigurieren Sie das importierte Zertifikat mit dem Cmdlet „Set-CsCertificate“ und verwenden Sie den Parameter „–Roll“ mit dem Parameter „–EffectiveDate“.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-151">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter.</span></span> <span data-ttu-id="2fa6c-152">Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokenlebensdauer (standardmäßig acht Stunden) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-152">The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus token lifetime (by default eight hours).</span></span> <span data-ttu-id="2fa6c-153">Dadurch erhalten wir eine Uhrzeit, zu der das Zertifikat auf "aktiv" festgesetzt werden muss, und ist das-EffectiveDate \<string\> : "7/22/2012 6:00:00 am".</span><span class="sxs-lookup"><span data-stu-id="2fa6c-153">This gives us a time that the certificate must be set to active, and is the –EffectiveDate \<string\>: “7/22/2012 6:00:00 AM”.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="2fa6c-154">Bei einem Edge-Pool müssen alle AudioVideoAuthentication-Zertifikate bereitgestellt und durch das Datum und die Uhrzeit bereitgestellt werden, die durch den – EffectiveDate-Parameter des ersten bereitgestellten Zertifikats definiert sind, um mögliche A/V-KOMMUNIKATIONSUNTERBRECHUNGEN zu vermeiden, weil das ältere Zertifikat abläuft, bevor alle Client-und Consumer-Token mithilfe des neuen Zertifikats erneuert wurden.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-154">For an Edge pool, you must have all AudioVideoAuthentication certificates deployed and provisioned by the date and time defined by the –EffectiveDate parameter of the first certificate deployed to avoid possible A/V communications disruption due to the older certificate expiring before all client and consumer tokens have been renewed using the new certificate.</span></span>

    
    </div>
    
    <span data-ttu-id="2fa6c-155">Der Befehl „Set-CsCertificate“ mit den Parametern „–Roll“ und „–EffectiveTime“:</span><span class="sxs-lookup"><span data-stu-id="2fa6c-155">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="2fa6c-156">Ein Set-CsCertificate-Beispielbefehl:</span><span class="sxs-lookup"><span data-stu-id="2fa6c-156">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="2fa6c-p113">Das Gültigkeitsdatum muss so formatiert werden, dass es den Regions- und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-p113">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="2fa6c-159">Mit einer optischen Zeitachse können Sie den Vorgang besser verstehen, der von „Set-CsCertificate“, „-Roll“ und „–EffectiveDate“ zum Bereitstellen eines neuen Zertifikats für die Ausstellung neuer AudioVideoAuthentication-Token verwendet wird, während weiterhin mit einem vorhandenen Zertifikat das von Benutzern verwendete AudioVideoAuthentication-Zertifikat validiert wird.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-159">To further understand the process that Set-CsCertificate, -Roll, and –EffectiveDate use to stage a new certificate for issuing new AudioVideoAuthentication tokens while still using an existing certificate to validate AudioVideoAuthentication that are in use by consumers, a visual timeline is an effective means of understanding the process.</span></span>

<span data-ttu-id="2fa6c-160">Im folgenden Beispiel wird vom Administrator festgelegt, dass das A/V-Edgedienst-Zertifikat um 2:00:00 Uhr am 07/22/2012 abläuft.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-160">In the following example, the administrator determines that the A/V Edge service certificate is due to expire at 2:00:00 PM on 07/22/2012.</span></span> <span data-ttu-id="2fa6c-161">Er fordert und empfängt ein neues Zertifikat und importiert es auf jeden Edgeserver in seinem Pool.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-161">He requests and receives a new certificate and imports it to each Edge Server in his pool.</span></span> <span data-ttu-id="2fa6c-162">Um 2 Uhr auf 07/22/2012 beginnt er mit der Ausführung von Get-CsCertificate mit – Rolle,-Fingerabdruck, der der Fingerabdruck Zeichenfolge des neuen Zertifikats entspricht, und – Effektivzeit, die auf 07/22/2012 6:00:00 Uhr eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-162">At 2 AM on 07/22/2012, he begins running Get-CsCertificate with –Roll, -Thumbprint equal to the thumbprint string of the new certificate, and –EffectiveTime set to 07/22/2012 6:00:00 AM.</span></span> <span data-ttu-id="2fa6c-163">Er führt diesen Befehl auf jedem Edgeserver aus.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-163">He runs this command on each Edge Server.</span></span>

<span data-ttu-id="2fa6c-164">![Verwenden des Rollen-und des EffectiveDate-Parameters](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Verwenden des Rollen-und des EffectiveDate-Parameters")</span><span class="sxs-lookup"><span data-stu-id="2fa6c-164">![Using the Roll and the EffectiveDate parameters.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Using the Roll and the EffectiveDate parameters.")</span></span>

<span data-ttu-id="2fa6c-165">Wenn die effektive Zeit erreicht ist (7/22/2012 6:00:00 Uhr), werden alle neuen Token vom neuen Zertifikat ausgestellt.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-165">When the effective time is reached (7/22/2012 6:00:00 AM), all new tokens are issued by the new certificate.</span></span> <span data-ttu-id="2fa6c-166">Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-166">When validating tokens, tokens will first be validated against the new certificate.</span></span> <span data-ttu-id="2fa6c-167">Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-167">If the validation fails, the old certificate is tried.</span></span> <span data-ttu-id="2fa6c-168">Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-168">The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate.</span></span> <span data-ttu-id="2fa6c-169">Nachdem das alte Zertifikat abgelaufen ist (7/22/2012 2:00:00 Uhr), werden Token nur vom neuen Zertifikat überprüft.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-169">Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate.</span></span> <span data-ttu-id="2fa6c-170">Das alte Zertifikat kann mithilfe des Cmdlets „Remove-CsCertificate“ mit dem Parameter „–Previous“ sicher entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-170">The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="2fa6c-171">So aktualisieren oder erneuern Sie ein OAuthTokenIssuer-Zertifikat mit einem – Rollen-und-EffectiveDate-Parameter</span><span class="sxs-lookup"><span data-stu-id="2fa6c-171">To update or renew an OAuthTokenIssuer certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="2fa6c-172">Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-172">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="2fa6c-173">Fordern Sie ein Erneuerungs-oder neues OAuthTokenIssuer-Zertifikat mit exportier barem privaten Schlüssel für das vorhandene Zertifikat im a/V-Edgedienst an.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-173">Request a renewal or new OAuthTokenIssuer certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="2fa6c-174">Importieren Sie das neue OAuthTokenIssuer-Zertifikat in einen Front-End-Server in Ihrem Pool (wenn Sie einen Pool bereitgestellt haben).</span><span class="sxs-lookup"><span data-stu-id="2fa6c-174">Import the new OAuthTokenIssuer certificate to a Front End Server in your pool (if you have a pool deployed).</span></span> <span data-ttu-id="2fa6c-175">Das OAuthTokenIssuer-Zertifikat wird global repliziert und muss auf den Servern in Ihrer Bereitstellung aktualisiert und erneuert werden.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-175">The OAuthTokenIssuer certificate is replicated globally and only needs to be updated and renewed at any server in your deployment.</span></span> <span data-ttu-id="2fa6c-176">Als Beispiel wird der Front-End-Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-176">The Front End Server is used as an example.</span></span>

4.  <span data-ttu-id="2fa6c-p117">Konfigurieren Sie das importierte Zertifikat mit dem Cmdlet „Set-CsCertificate“ und verwenden Sie den Parameter „–Roll“ mit dem Parameter „–EffectiveDate“. Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus mindestens 24 Stunden festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-p117">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter. The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus a minimum of 24 hours.</span></span>
    
    <span data-ttu-id="2fa6c-179">Der Befehl „Set-CsCertificate“ mit den Parametern „–Roll“ und „–EffectiveTime“:</span><span class="sxs-lookup"><span data-stu-id="2fa6c-179">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="2fa6c-180">Ein Set-CsCertificate-Beispielbefehl:</span><span class="sxs-lookup"><span data-stu-id="2fa6c-180">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="2fa6c-p118">Das Gültigkeitsdatum muss so formatiert werden, dass es den Regions- und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-p118">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="2fa6c-183">Wenn die effektive Zeit erreicht ist (7/21/2012 1:00:00 Uhr), werden alle neuen Token vom neuen Zertifikat ausgestellt.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-183">When the effective time is reached (7/21/2012 1:00:00 AM), all new tokens are issued by the new certificate.</span></span> <span data-ttu-id="2fa6c-184">Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-184">When validating tokens, tokens will first be validated against the new certificate.</span></span> <span data-ttu-id="2fa6c-185">Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-185">If the validation fails, the old certificate is tried.</span></span> <span data-ttu-id="2fa6c-186">Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-186">The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate.</span></span> <span data-ttu-id="2fa6c-187">Nachdem das alte Zertifikat abgelaufen ist (7/22/2012 2:00:00 Uhr), werden Token nur vom neuen Zertifikat überprüft.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-187">Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate.</span></span> <span data-ttu-id="2fa6c-188">Das alte Zertifikat kann mithilfe des Cmdlets „Remove-CsCertificate“ mit dem Parameter „–Previous“ sicher entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-188">The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2fa6c-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fa6c-189">See Also</span></span>


[<span data-ttu-id="2fa6c-190">Planen von Edgeserver-Zertifikaten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fa6c-190">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="2fa6c-191">Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fa6c-191">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[<span data-ttu-id="2fa6c-192">Einrichten von Edgezertifikaten für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fa6c-192">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
<span data-ttu-id="2fa6c-193">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fa6c-193">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span></span>  
<span data-ttu-id="2fa6c-194">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fa6c-194">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span></span>  
  

<span data-ttu-id="2fa6c-195"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="2fa6c-195"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

