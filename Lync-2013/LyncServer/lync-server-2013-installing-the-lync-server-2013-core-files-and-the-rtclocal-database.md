---
title: Installieren der lync Server 2013-Core-Dateien und der RTCLocal-Datenbank
description: Installieren der lync Server 2013-Core-Dateien und der RTCLocal-Datenbank
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68964f8b80f6377afd859d113783d61e33afbebd
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49426998"
---
# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="7ace2-103">Installieren der lync Server 2013-Core-Dateien und der RTCLocal-Datenbank</span><span class="sxs-lookup"><span data-stu-id="7ace2-103">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="7ace2-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="7ace2-104">

<span> </span></span></span>

<span data-ttu-id="7ace2-105">_**Letztes Änderungsdatum des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="7ace2-105">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="7ace2-106">Führen Sie die folgenden Schritte aus, um die Core-Dateien von lync Server 2013 auf einem Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="7ace2-106">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="7ace2-107">Die RTCLocal-Datenbank wird automatisch installiert, wenn Sie die Core-Dateien installieren.</span><span class="sxs-lookup"><span data-stu-id="7ace2-107">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="7ace2-108">Beachten Sie, dass Sie SQL Server nicht auf den Watcher-Knoten installieren müssen.</span><span class="sxs-lookup"><span data-stu-id="7ace2-108">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="7ace2-109">Stattdessen wird SQL Server Express automatisch für Sie installiert.</span><span class="sxs-lookup"><span data-stu-id="7ace2-109">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="7ace2-110">So installieren Sie die lync Server 2013-Core-Dateien und die RTCLocal-Datenbank:</span><span class="sxs-lookup"><span data-stu-id="7ace2-110">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="7ace2-111">Klicken Sie auf dem Watcher-Knoten Computer auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7ace2-111">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="7ace2-112">Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE, und verwenden Sie den entsprechenden Pfad zu ihren lync Server-Setupdateien:</span><span class="sxs-lookup"><span data-stu-id="7ace2-112">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="7ace2-113">Um zu überprüfen, ob die zentralen lync Server-Komponenten erfolgreich installiert wurden, klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="7ace2-113">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="7ace2-114">Geben Sie in der lync Server 2013-Verwaltungsshell den folgenden Windows PowerShell-Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="7ace2-114">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="7ace2-115">Wenn Sie diesen Befehl zum ersten Mal ausführen, werden keine Daten zurückgegeben, da Sie noch keine Watcher-Knoten Computer konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="7ace2-115">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="7ace2-116">Solange der Befehl ausgeführt wird, ohne einen Fehler zurückzugeben, können Sie davon ausgehen, dass das lync Server-Setup erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="7ace2-116">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="7ace2-117">Wenn sich Ihr Watcher-Knoten Computer in Ihrem Umkreisnetzwerk befindet, können Sie den folgenden Befehl ausführen, um die Installation von lync Server 2013 zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="7ace2-117">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="7ace2-118">Je nach der Anzahl der für die Verwendung in Ihrer Organisation konfigurierten Richtlinien für die persönliche Identifikationsnummer (PIN) erhalten Sie Informationen ähnlich wie die folgenden:</span><span class="sxs-lookup"><span data-stu-id="7ace2-118">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="7ace2-119">Wenn Sie Informationen zu Ihren PIN-Richtlinien sehen, bedeutet dies, dass Sie die Kernkomponenten erfolgreich installiert haben.</span><span class="sxs-lookup"><span data-stu-id="7ace2-119">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

<span data-ttu-id="7ace2-120"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="7ace2-120"></div>

<span> </span>

</div>

</div>

</span></span></div>

