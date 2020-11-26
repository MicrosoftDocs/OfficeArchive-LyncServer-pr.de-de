---
title: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Edgeserver'
description: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Edgeserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7798ca2f7b38865a2b4ea373546dd4e7203f5b8e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49430199"
---
# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a>Bereitstellen von IP-Adresstypen auf einem Edgeserver für Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-14_

Führen Sie mithilfe des Topologie-Generators die Schritte im folgenden Verfahren aus, um IP-Adresstypen auf einem Edgeserver bereitzustellen.

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a>So stellen Sie IP-Adresstypen auf dem Edgeserver bereit

1.  Klicken Sie im Topologie-Generator unter **Edge-Pools** mit der rechten Maustaste auf den Server in einem Pool, und wählen Sie dann **Eigenschaften bearbeiten** aus. (Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)

2.  Wählen Sie im Fenster **Eigenschaften bearbeiten** die IP-Adresskonfiguration, die Sie unterstützen möchten. In den folgenden Abbildungen wird eine Dualstapelkonfiguration für die interne und die externe Schnittstelle dargestellt.
    
    **Interne Dualstapelschnittstelle für Edge Server**
    
    ![Seite "Allgemeine Eigenschaften von lync Server"](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Seite "Allgemeine Eigenschaften von lync Server"")
    
    **Externe Dualstapelschnittstelle für Edge Server**
    
    ![Lync Server-nächster Hop/externe Konfigurationsseite](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server-nächster Hop/externe Konfigurationsseite")

3.  Für jeden Adresstyp, den Sie auswählen, müssen Sie die geeigneten internen und externen Adressen auswählen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

