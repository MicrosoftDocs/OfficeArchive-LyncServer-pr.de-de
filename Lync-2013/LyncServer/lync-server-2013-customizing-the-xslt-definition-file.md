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
# <a name="customizing-the-xslt-definition-file-in-lync-server-2013"></a>Anpassen der XSLT-Definitionsdatei in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-09-11_

Der Kompatibilitätsdienst zeichnet Daten auf, die sich auf die einzelnen lync Server 2013-, persistent Chat Server-Unterhaltungen beziehen, einschließlich, wenn ein Teilnehmer:

  - Beitritt zu einem beständigen Chatroom

  - Einen Chatroom verlässt

  - Eine Nachricht veröffentlicht

  - Den Chatverlauf anzeigt

  - Eine Datei hochlädt

  - Eine Datei herunterlädt

Die Daten werden als XML bereitgestellt, die Sie mithilfe einer XSLT-Definitionsdatei in das Format umwandeln können, das für Ihre Organisation am besten geeignet ist. In diesem Thema wird die vom Konformitätsdienst erstellte XML-Datei beschrieben. Zudem werden Beispiele für XSLT-Definitions- und Ausgabedateien bereitgestellt.

<div>

## <a name="output-format"></a>Ausgabe Format

Die Ausgabe des Kompatibilitätsdiensts wird nach Unterhaltung (dem Conversation-Element) und dann nach Nachricht (dem Messages-Element) kategorisiert, wie im folgenden Codebeispiel gezeigt.

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

Ein Unterhaltungselement enthält vier Elemente („Channel“, „FirstMessage“, „StartTimeUTC“ und „EndTimeUTC“). Das Element „Channel“ enthält den Uniform Resource Identifier (URI) des Chatrooms und das Element „FirstMessage“ beschreibt das erste Element im Nachrichtenelement. Die StartTimeUTC-und EndTimeUTC-Elemente stellen die Start-und Endzeit für die Konversation bereit, wie im folgenden Codebeispiel gezeigt.

    <<FirstMessage type="JOIN" content="" id="0">
          <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
          <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    </FirstMessage>

Ein Nachrichtenelement enthält zwei Elemente („Sender“ und „DateTimeUTC“) und drei Attribute („Type“, „Content“ und „ID“). Das Sender-Element stellt den Benutzer dar, der die Nachricht sendet, und das DateTimeUTC-Element stellt dar, wenn ein Ereignis eintritt, wie im folgenden Codebeispiel gezeigt.

    <Message type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
    </Message>

In der folgenden Tabelle werden die Nachrichtenattribute „Type“, „Content“ und „ID“ beschrieben.

### <a name="messages-element-attributes"></a>Nachrichtenelementattribute

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut</th>
<th>Beschreibung</th>
<th>Optional/erforderlich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Typ</p></td>
<td><p>Gibt den Nachrichtentyp an. Die Nachrichtentypen werden in der Tabelle „Nachrichtenelemente – Nachrichtentypen“ beschrieben.</p></td>
<td><p>Erforderlich</p></td>
</tr>
<tr class="even">
<td><p>Content</p></td>
<td><p>Enthält den Inhalt der Nachricht. Nachrichten vom Typ „Join“ oder „Part“ verwenden dieses Attribut nicht.</p></td>
<td><p>Optional</p></td>
</tr>
<tr class="odd">
<td><p>ID</p></td>
<td><p>Gibt die eindeutige ID des Inhalts an. Dieses Attribut wird nur mit Nachrichten vom Typ „Chat“ verwendet.</p></td>
<td><p>Optional</p></td>
</tr>
</tbody>
</table>


Jedes „Sender“-Element enthält fünf Attribute: „user name“, „ID“, „email“, „internal“ und „URI“. Diese Attribute sind in der folgenden Tabelle beschrieben.

### <a name="sender-element-attributes"></a>„Sender“-Elementattribute

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut</th>
<th>Beschreibung</th>
<th>Optional/erforderlich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Username</p></td>
<td><p>Der Name des Absenders.</p></td>
<td><p>Optional</p></td>
</tr>
<tr class="even">
<td><p>ID</p></td>
<td><p>Die eindeutige ID des Absenders.</p></td>
<td><p>Erforderlich</p></td>
</tr>
<tr class="odd">
<td><p>E-Mail</p></td>
<td><p>Die E-Mail-Adresse des Absenders</p></td>
<td><p>Optional</p></td>
</tr>
<tr class="even">
<td><p>Intern</p></td>
<td><p>Gibt an, ob es sich um einen internen Benutzer oder einen Verbundbenutzer handelt. Bei Festlegung des Werts auf „true“ (wahr) ist der Benutzer intern.</p></td>
<td><p>Optional</p></td>
</tr>
<tr class="odd">
<td><p>Uri</p></td>
<td><p>Die SIP-URI des Benutzers.</p></td>
<td><p>Erforderlich</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Nachrichtentypen beschrieben, die das Nachrichtenelement enthalten kann. Sie enthält auch Beispiele für die Verwendung der einzelnen Elemente.

### <a name="message-element-message-types"></a>Nachrichtenelemente – Nachrichtentypen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nachrichtentyp</th>
<th>Beschreibung</th>
<th>Codebeispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Join</p></td>
<td><p>Ein Benutzer betritt einen Chatroom.</p></td>
<td><pre><code>&lt;Message type=&quot;JOIN&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206211842612&quot; string=&quot;2008-03-22T18:50:42.6127374Z&quot; long=&quot;633418086426127374&quot; /&gt; 
&lt;/Message</code></pre></td>
</tr>
<tr class="even">
<td><p>Part</p></td>
<td><p>Ein Benutzer verlässt einen Chatroom.</p></td>
<td><pre><code>&lt;Message type=&quot;PART&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt; Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212610602532&quot; string=&quot;2008-06-04T20:16:42.5324614Z&quot; long=&quot;633482074025324614&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p>Chat</p></td>
<td><p>Die E-Mail-Adresse des Absenders</p></td>
<td><pre><code>&lt;Message type=&quot;CHAT&quot; content=&quot;hello&quot; id=&quot;1&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351800522&quot; string=&quot;2008-03-12T19:56:40.522264Z&quot; long=&quot;633409486005222640&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p>Backchat</p></td>
<td><p>Ein Benutzer fordert Inhalte des Chatverlaufs an.</p></td>
<td><pre><code>&lt;Message type=&quot;BACKCHAT&quot; content=&quot;backchatcontent&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206034385284&quot; string=&quot;2008-03-20T17:33:05.2841594Z&quot; long=&quot;633416311852841594&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p>File upload</p></td>
<td><p>Ein Benutzer lädt eine Datei hoch.</p></td>
<td><pre><code>&lt;Message type=&quot;FILEUPLOAD&quot; content=&quot;0988239a-bb66-4616-90a4-b07771a2097c.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351828975&quot; string=&quot;2008-03-12T19:57:08.9755711Z&quot; long=&quot;633409486289755711&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p>File download</p></td>
<td><p>Ein Benutzer lädt eine Datei herunter.</p></td>
<td><pre><code>&lt;Message type=&quot;FILEDOWNLOAD&quot; content=&quot;006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;kazuto@litwareinc.com&quot; id=&quot;10&quot; email=&quot;&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212611141851&quot; string=&quot;2008-06-04T20:25:41.8518646Z&quot; long=&quot;633482079418518646&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>Standardmäßige, persistente Chat Ausgabe-XSD und Beispiel-XSL-Transformation

Das folgende Codebeispiel enthält die Standardausgabe des Kompatibilitätsservers.

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

Das folgende Codebeispiel enthält eine Beispiel-XSL-Transformation.

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

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

