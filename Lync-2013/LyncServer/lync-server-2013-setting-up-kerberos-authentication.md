---
title: 'Lync Server 2013: Einrichten der Kerberos-Authentifizierung'
description: 'Lync Server 2013: Einrichten der Kerberos-Authentifizierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb461968bc073edbfe640f609257f3e84c192461
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49441718"
---
# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>Einrichten der Kerberos-Authentifizierung in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Lync Server 2013 unterstützt die NTLM-und Kerberos-Authentifizierung für Webdienste. Office Communications Server 2007 und Office Communications Server 2007 R2 verwendeten die standardmäßigen RTCComponentService und RTCService als Benutzerkonten, um die Webdienste-Anwendungspools auszuführen, wodurch ein Dienstprinzipalname (Service Principal Name, SPN) den Benutzerkonten zugewiesen und als Authentifizierungs Prinzipal fungieren kann. Lync Server verwendet Network Service zum Ausführen von Webdiensten, und Network Services kann keine SPNs zugewiesen werden.

Um das Problem zu lösen, dass keine Active Directory-Objekte für die SPNs enthalten sind, kann die lync Server-Systemsteuerung Computerkontoobjekte zu diesem Zweck verwenden. Die Computerkontoobjekte können die SPNs enthalten und unterliegen nicht dem Ablauf von Kennwörtern, was ein Problem bei der Verwendung von Benutzerkonten in früheren Versionen war.

Sie verwenden Windows PowerShell-Cmdlets, um die Computerobjekte so zu konfigurieren, dass die Kerberos-Authentifizierung bereitgestellt wird.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Voraussetzungen zur Aktivierung der Kerberos-Authentifizierung in Lync Server 2013](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Erstellen eines Kerberos-Authentifizierungskontos in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Zuweisen eines Kerberos-Authentifizierungskontos zu einem Standort in Lync Server 2013](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Einrichten von Kennwörtern für ein Kerberos-Authentifizierungskonto in Lync Server 2013](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [Hinzufügen der Kerberos-Authentifizierung zu weiteren Standorten in Lync Server 2013](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [Entfernen der Kerberos-Authentifizierung aus einem Standort in Lync Server 2013](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Test und Berichterstellung zu Status und Zuweisung der Kerberos-Authentifizierung in Lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

