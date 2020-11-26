---
title: Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer
description: Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64a7d785a77701c6796488178a7cce10caf54f42
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427824"
---
# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="f90e0-103">Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f90e0-103">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="f90e0-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="f90e0-104">

<span> </span></span></span>

<span data-ttu-id="f90e0-105">_**Letztes Änderungsdatum des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="f90e0-105">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="f90e0-106">Damit Sie Best Practices Analyzer erfolgreich ausführen können, muss das Benutzerkonto, das Sie für die Anmeldung verwenden, ein Mitglied der Gruppe Administratoren auf dem lokalen Computer sein.</span><span class="sxs-lookup"><span data-stu-id="f90e0-106">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer.</span></span> <span data-ttu-id="f90e0-107">Darüber hinaus muss das Benutzerkonto ein Mitglied der folgenden Gruppen sein, um die Umgebung zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="f90e0-107">Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="f90e0-108">**Domänenadministratoren**   Zum Auflisten von Informationen zu Active Directory-Domänendiensten und zum Aufrufen der WMI-Anbieter (Windows Management Instrumentation) auf Domänencontrollern und globalen Katalogservern.</span><span class="sxs-lookup"><span data-stu-id="f90e0-108">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="f90e0-109">**Administratoren**   Erforderlich für jeden lync Server 2013-internen Computer und jeden Edgeserver, um die WMI-Anbieter (Windows Management Instrumentation) anzurufen und auf die Registrierung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f90e0-109">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="f90e0-110">**RTCUniversalReadOnlyAdmins**   Vollständig oder delegiert lesen Sie nur die Administratorrechte von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f90e0-110">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="f90e0-111">**Exchange-Administrator "nur anzeigen**   "   Vollständiger oder Delegierter Exchange-Administrator mit nur Ansicht für die Microsoft Exchange-Organisation.</span><span class="sxs-lookup"><span data-stu-id="f90e0-111">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="f90e0-112">Wenn Ihr Benutzerkonto nicht über ausreichende Benutzerrechte verfügt, haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="f90e0-112">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="f90e0-113">Verwenden Sie an einer Eingabeaufforderung den Befehl **runas** , um das Tool unter einem Konto auszuführen, das über genügend Benutzerrechte verfügt.</span><span class="sxs-lookup"><span data-stu-id="f90e0-113">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="f90e0-114">Die Syntax lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f90e0-114">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="f90e0-115">Setzen Sie auf der Seite **mit Active Directory verbinden** die Anmeldeinformationen für die Konten, die Sie zum Ausführen von Best Practices Analyzer verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f90e0-115">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="f90e0-116">Klicken Sie auf **Erweiterte Anmeldeoptionen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f90e0-116">Click **Show advanced login options**.</span></span> <span data-ttu-id="f90e0-117">Sie können drei Konten eingeben: eine zum Herstellen einer Verbindung mit Active Directory-Domänendiensten, eine zum Herstellen einer Verbindung mit lync Server 2013-Edgeserver und eine für die Verbindung zu den Exchange-Servern.</span><span class="sxs-lookup"><span data-stu-id="f90e0-117">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="f90e0-118">Wenn Sie keines dieser Konten angeben, wird das Benutzerkonto verwendet, das Sie für die Anmeldung und die Ausführung von Best Practices Analyzer verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="f90e0-118">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

<span data-ttu-id="f90e0-119"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="f90e0-119"></div>

<span> </span>

</div>

</div>

</span></span></div>

