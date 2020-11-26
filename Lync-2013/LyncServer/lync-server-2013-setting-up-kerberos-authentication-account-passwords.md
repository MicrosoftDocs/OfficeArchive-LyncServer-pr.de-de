---
title: 'Lync Server 2013: Einrichten von Kennwörtern für ein Kerberos-Authentifizierungskonto'
description: 'Lync Server 2013: Einrichten von Kennwörtern für Kerberos-Authentifizierungs Konten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614b1411f9454c39843f4e69cabbfc3b02986e51
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49423971"
---
# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="e2f96-103">Einrichten von Kennwörtern für ein Kerberos-Authentifizierungskonto in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2f96-103">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="e2f96-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="e2f96-104">

<span> </span></span></span>

<span data-ttu-id="e2f96-105">_**Letztes Änderungsdatum des Themas:** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="e2f96-105">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="e2f96-106">Nachdem Sie das Computerobjekt für das Kerberos-Authentifizierungs Konto erstellt haben, können Sie das Kennwort für das Konto einrichten.</span><span class="sxs-lookup"><span data-stu-id="e2f96-106">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="e2f96-107">Sie führen das Windows PowerShell-Cmdlet aus, um das Kerberos-Kontokennwort auf einem Server festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e2f96-107">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="e2f96-108">Sie können das Kennwort für das für die Kerberos-Authentifizierung erstellte Objekt festlegen.</span><span class="sxs-lookup"><span data-stu-id="e2f96-108">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="e2f96-109">Das Kennwort kann auf einen bekannten Wert eingestellt werden, ist aber standardmäßig ein zufälliges Kennwort.</span><span class="sxs-lookup"><span data-stu-id="e2f96-109">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="e2f96-110">Das Kennwort steht für alle Kerberos-Authentifizierungsquellen, die das Konto verwenden, zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e2f96-110">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="e2f96-111">Sie verwenden Windows PowerShell-Cmdlets zum Einrichten und Verwalten von Kennwörtern für Kerberos-Konten.</span><span class="sxs-lookup"><span data-stu-id="e2f96-111">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e2f96-112">Das Kerberos-Kontoobjekt ist ein Computerobjekt, verwendet aber den Benutzerkonto-Parameter für Vorgänge in den Windows PowerShell-Cmdlets, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e2f96-112">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="e2f96-113">Beachten Sie, dass es sich nicht um einen Fehler handelt, sondern um das beabsichtigte Verhalten des Cmdlets, wenn es mit dem Erstellen und Verwalten von Kerberos-Konten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e2f96-113">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e2f96-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e2f96-114">In This Section</span></span>

  - [<span data-ttu-id="e2f96-115">Festlegen eines Kennworts für das Kerberos-Authentifizierungskonto auf einem Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2f96-115">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="e2f96-116">Synchronisieren eines Kennworts für das Kerberos-Authentifizierungskonto mit IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2f96-116">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

<span data-ttu-id="e2f96-117"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="e2f96-117"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

