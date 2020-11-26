---
title: 'Lync Server 2013: Anpassen der XSLT-Definitionsdatei'
description: 'Lync Server 2013: Anpassen der XSLT-Definitionsdatei'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing the XSLT definition file
ms:assetid: f18dd78c-3598-4f38-b496-96b750c6e518
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679898(v=OCS.15)
ms:contentKeyID: 49557733
ms.date: 09/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b248b44c9257fa9f30cc99a3773abf71ddbd8651
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431330"
---
# <a name="customizing-the-xslt-definition-file-in-lync-server-2013"></a><span data-ttu-id="8f17c-103">Anpassen der XSLT-Definitionsdatei in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f17c-103">Customizing the XSLT definition file in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="8f17c-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="8f17c-104">

<span> </span></span></span>

<span data-ttu-id="8f17c-105">_**Letztes Änderungsdatum des Themas:** 2014-09-11_</span><span class="sxs-lookup"><span data-stu-id="8f17c-105">_**Topic Last Modified:** 2014-09-11_</span></span>

<span data-ttu-id="8f17c-106">Der Kompatibilitätsdienst zeichnet Daten auf, die sich auf die einzelnen lync Server 2013-, persistent Chat Server-Unterhaltungen beziehen, einschließlich, wenn ein Teilnehmer:</span><span class="sxs-lookup"><span data-stu-id="8f17c-106">The Compliance service records and archives data related to each Lync Server 2013, Persistent Chat Server conversation, including when a participant:</span></span>

  - <span data-ttu-id="8f17c-107">Beitritt zu einem beständigen Chatroom</span><span class="sxs-lookup"><span data-stu-id="8f17c-107">Joins a Persistent Chat room</span></span>

  - <span data-ttu-id="8f17c-108">Einen Chatroom verlässt</span><span class="sxs-lookup"><span data-stu-id="8f17c-108">Leaves a chat room</span></span>

  - <span data-ttu-id="8f17c-109">Eine Nachricht veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="8f17c-109">Posts a message</span></span>

  - <span data-ttu-id="8f17c-110">Den Chatverlauf anzeigt</span><span class="sxs-lookup"><span data-stu-id="8f17c-110">Views chat history</span></span>

  - <span data-ttu-id="8f17c-111">Eine Datei hochlädt</span><span class="sxs-lookup"><span data-stu-id="8f17c-111">Uploads a file</span></span>

  - <span data-ttu-id="8f17c-112">Eine Datei herunterlädt</span><span class="sxs-lookup"><span data-stu-id="8f17c-112">Downloads a file</span></span>

<span data-ttu-id="8f17c-113">Die Daten werden als XML bereitgestellt, die Sie mithilfe einer XSLT-Definitionsdatei in das Format umwandeln können, das für Ihre Organisation am besten geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="8f17c-113">The data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file.</span></span> <span data-ttu-id="8f17c-114">In diesem Thema wird die vom Konformitätsdienst erstellte XML-Datei beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f17c-114">This topic describes the XML file that the Compliance service creates.</span></span> <span data-ttu-id="8f17c-115">Zudem werden Beispiele für XSLT-Definitions- und Ausgabedateien bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="8f17c-115">It also provides samples of XSLT definition and output files.</span></span>

<div>

## <a name="output-format"></a><span data-ttu-id="8f17c-116">Ausgabe Format</span><span class="sxs-lookup"><span data-stu-id="8f17c-116">Output Format</span></span>

<span data-ttu-id="8f17c-117">Die Ausgabe des Kompatibilitätsdiensts wird nach Unterhaltung (dem Conversation-Element) und dann nach Nachricht (dem Messages-Element) kategorisiert, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f17c-117">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample.</span></span>

    <?xml version="1.0" encoding="utf-8" ?> 
    <Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <Conversation>
        <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
        <!--FirstMessage goes here --!>
        <Messages> 
          <!—Messages go here--!>
        </Messages>
        <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
        <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
      </Conversation>
    </Conversations>

<span data-ttu-id="8f17c-118">Ein Unterhaltungselement enthält vier Elemente („Channel“, „FirstMessage“, „StartTimeUTC“ und „EndTimeUTC“).</span><span class="sxs-lookup"><span data-stu-id="8f17c-118">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC).</span></span> <span data-ttu-id="8f17c-119">Das Element „Channel“ enthält den Uniform Resource Identifier (URI) des Chatrooms und das Element „FirstMessage“ beschreibt das erste Element im Nachrichtenelement.</span><span class="sxs-lookup"><span data-stu-id="8f17c-119">The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element.</span></span> <span data-ttu-id="8f17c-120">Die StartTimeUTC-und EndTimeUTC-Elemente stellen die Start-und Endzeit für die Konversation bereit, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f17c-120">The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample.</span></span>

    <<FirstMessage type="JOIN" content="" id="0">
          <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
          <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    </FirstMessage>

<span data-ttu-id="8f17c-121">Ein Nachrichtenelement enthält zwei Elemente („Sender“ und „DateTimeUTC“) und drei Attribute („Type“, „Content“ und „ID“).</span><span class="sxs-lookup"><span data-stu-id="8f17c-121">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID).</span></span> <span data-ttu-id="8f17c-122">Das Sender-Element stellt den Benutzer dar, der die Nachricht sendet, und das DateTimeUTC-Element stellt dar, wenn ein Ereignis eintritt, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f17c-122">The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample.</span></span>

    <Message type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
    </Message>

<span data-ttu-id="8f17c-123">In der folgenden Tabelle werden die Nachrichtenattribute „Type“, „Content“ und „ID“ beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f17c-123">The following table describes the message attributes Type, Content, and ID.</span></span>

### <a name="messages-element-attributes"></a><span data-ttu-id="8f17c-124">Nachrichtenelementattribute</span><span class="sxs-lookup"><span data-stu-id="8f17c-124">Messages Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f17c-125">Attribut</span><span class="sxs-lookup"><span data-stu-id="8f17c-125">Attribute</span></span></th>
<th><span data-ttu-id="8f17c-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f17c-126">Description</span></span></th>
<th><span data-ttu-id="8f17c-127">Optional/erforderlich</span><span class="sxs-lookup"><span data-stu-id="8f17c-127">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f17c-128">Typ</span><span class="sxs-lookup"><span data-stu-id="8f17c-128">Type</span></span></p></td>
<td><p><span data-ttu-id="8f17c-p104">Gibt den Nachrichtentyp an. Die Nachrichtentypen werden in der Tabelle „Nachrichtenelemente – Nachrichtentypen“ beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f17c-p104">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span></p></td>
<td><p><span data-ttu-id="8f17c-131">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="8f17c-131">Required</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f17c-132">Content</span><span class="sxs-lookup"><span data-stu-id="8f17c-132">Content</span></span></p></td>
<td><p><span data-ttu-id="8f17c-p105">Enthält den Inhalt der Nachricht. Nachrichten vom Typ „Join“ oder „Part“ verwenden dieses Attribut nicht.</span><span class="sxs-lookup"><span data-stu-id="8f17c-p105">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span></p></td>
<td><p><span data-ttu-id="8f17c-135">Optional</span><span class="sxs-lookup"><span data-stu-id="8f17c-135">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f17c-136">ID</span><span class="sxs-lookup"><span data-stu-id="8f17c-136">ID</span></span></p></td>
<td><p><span data-ttu-id="8f17c-p106">Gibt die eindeutige ID des Inhalts an. Dieses Attribut wird nur mit Nachrichten vom Typ „Chat“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="8f17c-p106">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span></p></td>
<td><p><span data-ttu-id="8f17c-139">Optional</span><span class="sxs-lookup"><span data-stu-id="8f17c-139">Optional</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8f17c-p107">Jedes „Sender“-Element enthält fünf Attribute: „user name“, „ID“, „email“, „internal“ und „URI“. Diese Attribute sind in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f17c-p107">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

### <a name="sender-element-attributes"></a><span data-ttu-id="8f17c-142">„Sender“-Elementattribute</span><span class="sxs-lookup"><span data-stu-id="8f17c-142">Sender Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f17c-143">Attribut</span><span class="sxs-lookup"><span data-stu-id="8f17c-143">Attribute</span></span></th>
<th><span data-ttu-id="8f17c-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f17c-144">Description</span></span></th>
<th><span data-ttu-id="8f17c-145">Optional/erforderlich</span><span class="sxs-lookup"><span data-stu-id="8f17c-145">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f17c-146">Username</span><span class="sxs-lookup"><span data-stu-id="8f17c-146">Username</span></span></p></td>
<td><p><span data-ttu-id="8f17c-147">Der Name des Absenders.</span><span class="sxs-lookup"><span data-stu-id="8f17c-147">The name of the sender.</span></span></p></td>
<td><p><span data-ttu-id="8f17c-148">Optional</span><span class="sxs-lookup"><span data-stu-id="8f17c-148">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f17c-149">ID</span><span class="sxs-lookup"><span data-stu-id="8f17c-149">ID</span></span></p></td>
<td><p><span data-ttu-id="8f17c-150">Die eindeutige ID des Absenders.</span><span class="sxs-lookup"><span data-stu-id="8f17c-150">The sender’s unique ID.</span></span></p></td>
<td><p><span data-ttu-id="8f17c-151">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="8f17c-151">Required</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f17c-152">E-Mail</span><span class="sxs-lookup"><span data-stu-id="8f17c-152">Email</span></span></p></td>
<td><p><span data-ttu-id="8f17c-153">Die E-Mail-Adresse des Absenders</span><span class="sxs-lookup"><span data-stu-id="8f17c-153">The sender’s email address.</span></span></p></td>
<td><p><span data-ttu-id="8f17c-154">Optional</span><span class="sxs-lookup"><span data-stu-id="8f17c-154">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f17c-155">Intern</span><span class="sxs-lookup"><span data-stu-id="8f17c-155">Internal</span></span></p></td>
<td><p><span data-ttu-id="8f17c-p108">Gibt an, ob es sich um einen internen Benutzer oder einen Verbundbenutzer handelt. Bei Festlegung des Werts auf „true“ (wahr) ist der Benutzer intern.</span><span class="sxs-lookup"><span data-stu-id="8f17c-p108">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span></p></td>
<td><p><span data-ttu-id="8f17c-158">Optional</span><span class="sxs-lookup"><span data-stu-id="8f17c-158">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f17c-159">Uri</span><span class="sxs-lookup"><span data-stu-id="8f17c-159">Uri</span></span></p></td>
<td><p><span data-ttu-id="8f17c-160">Die SIP-URI des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="8f17c-160">The user’s SIP URI.</span></span></p></td>
<td><p><span data-ttu-id="8f17c-161">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="8f17c-161">Required</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8f17c-p109">In der folgenden Tabelle werden die Nachrichtentypen beschrieben, die das Nachrichtenelement enthalten kann. Sie enthält auch Beispiele für die Verwendung der einzelnen Elemente.</span><span class="sxs-lookup"><span data-stu-id="8f17c-p109">The following table describes the message types that the Messages element can contain. It also provides examples of how each element is used.</span></span>

### <a name="message-element-message-types"></a><span data-ttu-id="8f17c-164">Nachrichtenelemente – Nachrichtentypen</span><span class="sxs-lookup"><span data-stu-id="8f17c-164">Message Element Message Types</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f17c-165">Nachrichtentyp</span><span class="sxs-lookup"><span data-stu-id="8f17c-165">Message Type</span></span></th>
<th><span data-ttu-id="8f17c-166">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f17c-166">Description</span></span></th>
<th><span data-ttu-id="8f17c-167">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="8f17c-167">Code example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f17c-168">Join</span><span class="sxs-lookup"><span data-stu-id="8f17c-168">Join</span></span></p></td>
<td><p><span data-ttu-id="8f17c-169">Ein Benutzer betritt einen Chatroom.</span><span class="sxs-lookup"><span data-stu-id="8f17c-169">A user joins a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;JOIN&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206211842612&quot; string=&quot;2008-03-22T18:50:42.6127374Z&quot; long=&quot;633418086426127374&quot; /&gt; 
&lt;/Message</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f17c-170">Part</span><span class="sxs-lookup"><span data-stu-id="8f17c-170">Part</span></span></p></td>
<td><p><span data-ttu-id="8f17c-171">Ein Benutzer verlässt einen Chatroom.</span><span class="sxs-lookup"><span data-stu-id="8f17c-171">A user leaves a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;PART&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt; Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212610602532&quot; string=&quot;2008-06-04T20:16:42.5324614Z&quot; long=&quot;633482074025324614&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f17c-172">Chat</span><span class="sxs-lookup"><span data-stu-id="8f17c-172">Chat</span></span></p></td>
<td><p><span data-ttu-id="8f17c-173">Die E-Mail-Adresse des Absenders</span><span class="sxs-lookup"><span data-stu-id="8f17c-173">The sender’s email address.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;CHAT&quot; content=&quot;hello&quot; id=&quot;1&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351800522&quot; string=&quot;2008-03-12T19:56:40.522264Z&quot; long=&quot;633409486005222640&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f17c-174">Backchat</span><span class="sxs-lookup"><span data-stu-id="8f17c-174">Backchat</span></span></p></td>
<td><p><span data-ttu-id="8f17c-175">Ein Benutzer fordert Inhalte des Chatverlaufs an.</span><span class="sxs-lookup"><span data-stu-id="8f17c-175">A user requests content from chat history.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;BACKCHAT&quot; content=&quot;backchatcontent&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206034385284&quot; string=&quot;2008-03-20T17:33:05.2841594Z&quot; long=&quot;633416311852841594&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f17c-176">File upload</span><span class="sxs-lookup"><span data-stu-id="8f17c-176">File upload</span></span></p></td>
<td><p><span data-ttu-id="8f17c-177">Ein Benutzer lädt eine Datei hoch.</span><span class="sxs-lookup"><span data-stu-id="8f17c-177">A user uploads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEUPLOAD&quot; content=&quot;0988239a-bb66-4616-90a4-b07771a2097c.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351828975&quot; string=&quot;2008-03-12T19:57:08.9755711Z&quot; long=&quot;633409486289755711&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f17c-178">File download</span><span class="sxs-lookup"><span data-stu-id="8f17c-178">File download</span></span></p></td>
<td><p><span data-ttu-id="8f17c-179">Ein Benutzer lädt eine Datei herunter.</span><span class="sxs-lookup"><span data-stu-id="8f17c-179">A user downloads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEDOWNLOAD&quot; content=&quot;006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;kazuto@litwareinc.com&quot; id=&quot;10&quot; email=&quot;&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212611141851&quot; string=&quot;2008-06-04T20:25:41.8518646Z&quot; long=&quot;633482079418518646&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="8f17c-180">Standardmäßige, persistente Chat Ausgabe-XSD und Beispiel-XSL-Transformation</span><span class="sxs-lookup"><span data-stu-id="8f17c-180">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="8f17c-181">Das folgende Codebeispiel enthält die Standardausgabe des Kompatibilitätsservers.</span><span class="sxs-lookup"><span data-stu-id="8f17c-181">The following code sample contains the default output from the Compliance Server.</span></span>

    <?xml version="1.0" encoding="utf-8"?>
    <xs:schema id="Conversations"  xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
       <xs:simpleType name="ComplianceMessageType">
          <xs:restriction base="xs:string">
            <xs:enumeration value="JOIN"/>
            <xs:enumeration value="PART"/>
            <xs:enumeration value="CHAT"/>
            <xs:enumeration value="BACKCHAT"/>
            <xs:enumeration value="FILEUPLOAD"/>
            <xs:enumeration value="FILEDOWNLOAD"/>
          </xs:restriction>
        </xs:simpleType>
      
      <xs:element name="Sender">
        <xs:complexType>
          <xs:attribute name="UserName" type="xs:string" />
          <xs:attribute name="id" type="xs:int" />
          <xs:attribute name="email" type="xs:string" use="optional" />
          <xs:attribute name="internal" type="xs:boolean" use="optional" >
            <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
          </xs:attribute>
          <xs:attribute name="uri" type="xs:anyURI" use="optional" />
        </xs:complexType>
      </xs:element>
      <xs:element name="DateTimeUTC">
        <xs:complexType>
          <xs:attribute name="since1970" type="xs:long" />
          <xs:attribute name="string" type="xs:string" />
          <xs:attribute name="long" type="xs:long" />
        </xs:complexType>
      </xs:element>
      <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
        <xs:complexType>
          <xs:choice minOccurs="0" maxOccurs="unbounded">
            <xs:element ref="Sender" />
            <xs:element ref="DateTimeUTC" />
            <xs:element name="Conversation">
              <xs:complexType>
                <xs:sequence>
                  <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                    <xs:complexType>
                      <xs:attribute name="uri" type="xs:anyURI" />
                      <xs:attribute name="name" type="xs:string" use="optional" />
                    </xs:complexType>
                  </xs:element>
                  <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                    <xs:complexType>
                      <xs:sequence>
                        <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                        <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                      </xs:sequence>
                      <xs:attribute name="type" type="ComplianceMessageType" />
                      <xs:attribute name="content" type="xs:string" />
                      <xs:attribute name="id" type="xs:int" />
                    </xs:complexType>
                  </xs:element>
                  <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                    <xs:complexType>
                      <xs:sequence>
                        <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                          <xs:complexType>
                            <xs:sequence>
                              <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                              <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                            </xs:sequence>
                            <xs:attribute name="type" type="ComplianceMessageType" />
                            <xs:attribute name="content" type="xs:string" />
                            <xs:attribute name="id" type="xs:int" />
                          </xs:complexType>
                        </xs:element>
                      </xs:sequence>
                    </xs:complexType>
                  </xs:element>
                  <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                    <xs:complexType>
                      <xs:attribute name="since1970" type="xs:long" />
                      <xs:attribute name="string" type="xs:string" />
                      <xs:attribute name="long" type="xs:long" />
                    </xs:complexType>
                  </xs:element>
                  <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                    <xs:complexType>
                      <xs:attribute name="since1970" type="xs:long" />
                      <xs:attribute name="string" type="xs:string" />
                      <xs:attribute name="long" type="xs:long" />
                    </xs:complexType>
                  </xs:element>
                </xs:sequence>
              </xs:complexType>
            </xs:element>
          </xs:choice>
        </xs:complexType>
      </xs:element>
    </xs:schema>

<span data-ttu-id="8f17c-182">Das folgende Codebeispiel enthält eine Beispiel-XSL-Transformation.</span><span class="sxs-lookup"><span data-stu-id="8f17c-182">The following code sample contains a sample XSL transform.</span></span>

    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
       <xsl:output method="xml" encoding="UTF-8" indent="yes" />
    
       <xsl:template match="/">
          <FileDump>
             <xsl:apply-templates />
          </FileDump>
       </xsl:template>
    
       <xsl:template match="Conversation">
          <xsl:variable name="chanName" select="Channel/@name" />
          <Conversation Perspective="{$chanName}_group_channel">
             <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
             <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
             <xsl:apply-templates />
             <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
          </Conversation>
       </xsl:template>
    
       <xsl:template match="Message">
          <xsl:choose>
             <xsl:when test="@type='JOIN'">
                <ParticipantEntered>
                   <xsl:call-template name="DateTimeAndLogin" />
                   <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
                   <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
                   <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
                </ParticipantEntered>
             </xsl:when>
    
             <xsl:when test="@type='PART'">
                <ParticipantLeft>
                   <xsl:call-template name="DateTimeAndLogin" />
                   <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
                   <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
                   <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
                </ParticipantLeft>
             </xsl:when>
    
             <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
                <FileTransferStarted>
                   <xsl:call-template name="DateTimeAndLogin" />
                   <FileName><xsl:value-of select="@content" /></FileName>
                </FileTransferStarted>
                <FileTransferEnded>
                   <xsl:call-template name="DateTimeAndLogin" />
                   <FileName><xsl:value-of select="@content" /></FileName>
                   <Status>Completed</Status>
                </FileTransferEnded>
             </xsl:when>
    
             <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
                <Message>
                   <xsl:call-template name="DateTimeAndLogin" />
                   <Content><xsl:value-of select="@content" /></Content>
                </Message>
             </xsl:when>
    
             <xsl:otherwise />
          </xsl:choose>
       </xsl:template>
    
       <xsl:template name="DateTimeAndLogin">
          <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
          <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
       </xsl:template>
    </xsl:stylesheet>

<span data-ttu-id="8f17c-183"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="8f17c-183"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

