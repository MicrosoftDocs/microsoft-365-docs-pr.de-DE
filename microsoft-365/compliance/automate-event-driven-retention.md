---
title: Automatisieren der ereignisgesteuerten Aufbewahrung
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: In diesem Thema wird erläutert, wie Sie Geschäftsprozessabläufe über Ereignisse mithilfe der Microsoft 365-REST-API einrichten können, um die Aufbewahrung zu automatisieren.
ms.openlocfilehash: 0b2507497bfd90b892e95934a03f795045c9bac2
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43105652"
---
# <a name="automate-event-based-retention"></a>Automatisieren der ereignisbasierten Aufbewahrung

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Die explosionsartige Zunahme von Inhalten in Unternehmen und wie erreicht werden kann, dass diese keine Rolle mehr spielt, ist eine ernste Angelegenheit. Um auch weiterhin den Herausforderungen im Zusammenhang mit der Einhaltung gesetzlicher und geschäftlicher Bestimmungen gerecht zu werden, müssen Organisationen in der Lage sein, wichtige Informationen aufzubewahren und zu schützen und schnell herauszufinden, was relevant ist. Die Aufbewahrung ausschließlich wichtiger, relevanter Informationen ist der Schlüssel zum Erfolg einer Organisation.

Um dieser Anforderung gerecht zu werden, können Unternehmen die Aufbewahrungslösungen im Office 365 Security & Compliance Center nutzen. Aufbewahrung kann mithilfe von [Aufbewahrungsbezeichnungen](labels.md) ausgelöst werden. Eine Aufbewahrungsbezeichnung kann als [Grundlage für den Aufbewahrungszeitraum für ein bestimmtes Ereignis](event-driven-retention.md) dienen. In der Regel basiert der Aufbewahrungszeitraum auf einem bekannten Datum, z. B. dem Erstellungsdatum oder dem Datum der letzten Änderung der Inhalte. Unternehmen müssen jedoch auch Inhalte aufgrund des Eintretens eines Ereignisses entfernen, zum Beispiel 7 Jahre nach dem Austritt eines Mitarbeiters aus dem Unternehmen.

Um ein ordnungsgemäßes Entfernen der Inhalte sicherzustellen, ist es zwingend erforderlich zu wissen, wann ein Ereignis eintritt. Da die Inhaltsmenge rasant zunimmt, wird es immer schwieriger, Inhalte zeitnah und ordnungsgemäß aufzubewahren und zu entfernen.

Die ereignisbasierte Aufbewahrung stellt eine Lösung für dieses Problem dar. In diesem Thema wird erläutert, wie Sie Geschäftsprozessabläufe über Ereignisse mithilfe der Microsoft 365-REST-API einrichten können, um die Aufbewahrung zu automatisieren.

## <a name="about-event-based-retention"></a>Grundlegendes zur ereignisbasierten Aufbewahrung

Es gibt kleine, mittelständige und Großunternehmen. Die Anzahl der Geschäftsdokumente, Rechtsdokumente, Mitarbeiterdateien, Verträgen und Produktdokumenten, die täglich erstellt und verwaltet werden, nimmt dramatisch zu.

Zum Beispiel werden täglich Dutzende Mitarbeiter eingestellt, und es verlassen auch Dutzende Mitarbeiter die Unternehmen. Die Personalabteilung erstellt, aktualisiert oder löscht weiterhin mitarbeiterbezogene Dokumente gemäß den Geschäftsanforderungen. Dieser Prozess unterliegt verschiedenen Aufbewahrungsrichtlinien, die für das Unternehmen festgelegt sind:

- **Der Aufbewahrungszeitraum für die Inhalte kann ein bekanntes Datum sein,** z. B. das Datum, an dem der Inhalt erstellt, zuletzt geändert oder mit einer Bezeichnung versehen wurde. Beispiel: Dokumente werden möglicherweise sieben Jahre lang ab Erstellung aufbewahrt und anschließend gelöscht.

- **Der Aufbewahrungszeitraum für den Inhalt kann auch ein unbekanntes Datum sein**. Mit Aufbewahrungsbezeichnungen können Sie zum Beispiel als Basis für den Aufbewahrungszeitraum ein bestimmtes Ereignis festlegen, zum Beispiel den Austritt eines Mitarbeiters aus dem Unternehmen.

Mit dem Ereignis wird der Anfang des Aufbewahrungszeitraums ausgelöst. Für alle Inhalte mit einer Bezeichnung, die für diese Art des Ereignisses angewendet wurde, werden die Aufbewahrungsmaßnahmen der Bezeichnung erzwungen. Dies wird auch als ereignisbasierte Aufbewahrung bezeichnet. Weitere Informationen hierzu finden Sie unter [Übersicht über die ereignisgesteuerte Aufbewahrung](event-driven-retention.md).

## <a name="set-up-event-based-retention"></a>Einrichten der ereignisbasierten Aufbewahrung

Dieser Abschnitt beinhaltet die für die Aufbewahrung von Inhalten erforderlichen Schritte.

### <a name="identify-roles"></a>Identifizieren von Rollen

Identifizieren Sie die verschiedenen Rollen in einem Unternehmen, die Aufgaben für die Datensatzverwaltung ausführen und für eine effektive und effiziente Aufbewahrung von Geschäftsdokumenten verantwortlich sind.

  | **Persona**| **Rolle**|
  | - | - |
  | Admin | Erstellt Ereignistypen für die Aufbewahrung, Aufbewahrungsbezeichnungen und Repositorys für die Aufbewahrung in SharePoint. |
  | Datensatzverwalter                                  | Stellt Details zur Einhaltung von Aufbewahrungsrichtlinien und Aufbewahrungszeitplänen bereit.   |
  | Systemadministrator (Unternehmen)                          | Richtet externe Systeme für die Verwendung mit Microsoft 365 ein, und verwaltet diese.                       |
  | Information-Worker                               | Verwaltet den Lebenszyklus der Geschäftsabläufe (HR, Finanzen, IT usw.).                 |

### <a name="set-up-the-security--compliance-center"></a>Einrichten des Security & Compliance Center
  
1. Der Compliance-Administrator erstellt einen Ereignistyp &ndash;, zum Beispiel Ende der Beschäftigung, Vertragsablauf oder Ende der Produktherstellung. (Eine schrittweise Anleitung finden Sie unter [Ereignisgesteuerte Aufbewahrung](event-driven-retention.md)).
    
2. Der Compliance-Administrator erstellt eine Aufbewahrungsbezeichnung auf der Grundlage eines Ereignisses und weist die Bezeichnung einem Ereignistyp zu.
    
    Es gibt vier Arten von Auslösern für Aufbewahrungsbezeichnungen:
            
    1. Erstellungsdatum
                
    2. Zuletzt geändert
                
    3. Datum der Bezeichnung (Zeitpunkt, zu dem die Inhalte mit der Bezeichnung versehen wurden)
                
    4. Ereignis-basiert
    
3. Der Compliance-Administrator veröffentlicht die Aufbewahrungsbezeichnung.

### <a name="set-up-sharepoint"></a>Einrichten von SharePoint
   
Der Compliance-Administrator geht wie folgt vor, um ein Repository für Datensätze zu erstellen:

1. Er erstellt eine SharePoint-Website.

2. Er führt einen der folgenden Schritte aus:
        
    - Er erstellt eine SharePoint-Bibliothek: er legt eine ereignisbasierte Bezeichnung auf Bibliotheksebene fest. Weitere Informationen finden Sie unter [Anwenden einer Aufbewahrungsbezeichnung auf alle Inhalte in einer Bibliothek, einem Ordner oder einer Dokumentenmappe in SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
          
    - Richtet eine Dokumentenmappe in SharePoint ein. Weitere Informationen finden Sie unter [Einführung in Dokumentenmappen](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).
      
3. Weist jeder Dokumentenmappe eines Mitarbeiters eine Objekt-ID zu. Bei einer Objekt-ID handelt es sich um einen Produktnamen oder Code, der von der Organisation verwendet wird; die Mitarbeiternummer kann z. B. eine Objekt-ID sein. Durch Zuweisen der Objekt-ID zum Ordner erbt jedes Element in diesem Ordner automatisch dieselbe Objekt-ID. Dies bedeutet, dass der Aufbewahrungszeitraum aller Elemente durch das gleiche Ereignis ausgelöst werden kann.

## <a name="ways-to-trigger-event-based-retention"></a>Möglichkeiten zum Auslösen der ereignisbasierten Aufbewahrung

Es gibt zwei Möglichkeiten zum Auslösen der ereignisbasierten Aufbewahrung:

- **Verwenden der Benutzeroberfläche des Admin Centers** Dies ist ein Prozess, der verwendet werden kann, um weniger Inhalte gleichzeitig zu speichern, oder wenn Häufigkeit, mit der die Aufbewahrung ausgelöst wird, gering ist, z. B. monatlich oder jährlich. Weitere Informationen über diese Methode finden Sie unter [Übersicht über die ereignisgesteuerte Aufbewahrung](event-driven-retention.md). Allerdings kann diese Methode des Auslösens der Aufbewahrung zeitaufwändig und fehleranfällig sein, wodurch die Skalierbarkeit eingeschränkt wird. Daher kann eine automatisierte, nahtlose Lösung zum Auslösen der Aufbewahrung die Datensicherheit und Compliance verbessern.

- **Mithilfe einer Microsoft 365-REST-API**Dieser Prozess kann verwendet werden, wenn sehr viele Inhalte aufbewahrt werden und/oder die Aufbewahrung häufig ausgelöst wird, zum Beispiel täglich oder wöchentlich. Der Ablauf erkennt, wenn ein Ereignis in Ihrem Branchensystem eintritt, und erstellt automatisch ein zugehöriges Ereignis im Security & Compliance Center. Sie müssen keine Ereignisse in der Benutzeroberfläche manuell erstellen, wenn diese eintreten.

Es gibt zwei Optionen für die Verwendung der REST-API:

- **Microsoft Flow oder eine ähnliche Anwendung** kann verwendet werden, um das Ereignis automatisch auszulösen. Microsoft Flow ist ein Orchestrator zum Herstellen einer Verbindung zu anderen Systemen. Für die Verwendung von Microsoft Flow ist keine benutzerdefinierte Lösung erforderlich.

- **PowerShell oder ein HTTP-Client zum Aufrufen der REST-API** Sie können PowerShell (Version 6 oder höher) zum Aufrufen der Microsoft 365-REST-API verwenden, um Ereignisse zu erstellen. 

Bei einer Rest-API handelt es sich um einen Dienstendpunkt, der Gruppen von HTTP-Vorgängen (Methoden) unterstützt, die Zugriff zum Erstellen/Abrufen/Aktualisieren/Löschen der Dienstressourcen bieten. Weitere Informationen finden Sie unter [Komponenten einer REST-API-Anfrage/-Anfrage](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). In diesem Fall können mithilfe der Microsoft 365 Rest-API Ereignisse erstellt und mit POST- und GET-Operationen abgerufen werden.

## <a name="example-scenarios"></a>Beispielszenarien

Betrachten Sie die folgenden Szenarien.

### <a name="scenario-1-employees-leaving-the-organization"></a>Scenario 1: Mitarbeiter tritt aus dem Unternehmen aus 

Eine Organisation erstellt und speichert zahlreiche mitarbeiterbezogene Dokumente pro Mitarbeiter. Diese Dokumente werden während der Beschäftigungsdauer jedes Mitarbeiters verwaltet und aufbewahrt. Wenn der Mitarbeiter aber die Organisation verlässt oder das Beschäftigungsverhältnis beendet wird, ist die Organisation gemäß gesetzlicher und geschäftlicher Anforderungen verpflichtet, die Dokumente des Mitarbeiters für einen festgelegten Zeitraum aufzubewahren.

Wenn nun täglich mehrere Mitarbeiter aus dem Unternehmen austreten, muss das Unternehmen die Aufbewahrungszeit von Hunderten, wenn nicht Tausenden von Dokumenten pro Tag auslösen.

Darüber hinaus muss für jeden dieser Mitarbeiter die Aufbewahrungsfrist als Datum des Austritts aus dem Unternehmen + Anzahl der Tage, Monate oder Jahre je nach Art des Mitarbeiterdatensatzes berechnet werden. So kann beispielsweise die Vergütung des Mitarbeiters gegenüber den Leistungsanmeldungen desselben Arbeitnehmers eine unterschiedliche Aufbewahrung erfordern.

Das nachstehende Diagramm zeigt, dass mehrere Beschriftungen vorhanden sein können, die einem einzelnen Ereignis zugeordnet sind. Hier werden alle Dateien unter der Bezeichnung „Mitarbeitervergütung“ und alle Dateien unter der Bezeichnung „Leistungen“ mit einem einzelnen Ereignis verknüpft, und zwar, dass der Mitarbeiter das Unternehmen verlässt. Jede dieser unterschiedlichen Dateien weist unterschiedliche Aufbewahrungszeitpläne auf. Wenn ein Mitarbeiter das Unternehmen verlässt, haben diese Dateien innerhalb der einzelnen Bezeichnungen einen anderen Aufbewahrungszeitraum. Das Auslösen dieser unterschiedlichen Aufbewahrungszeitpläne für jeden Dateityp oder jede Bezeichnung für jeden Mitarbeiter ist eine große Herausforderung. Stellen Sie sich vor, dies für mehrere Mitarbeiter auszuführen.

![Diagramm zu Ereignistypen, Ereignissen und Bezeichnungen](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

Ein automatisierter Prozess zum Auslösen dieser unterschiedlicher Aufbewahrungszeiten für mehrere Mitarbeiter ist daher zeitsparend, fehlerfrei und äußerst effizient.

**Konfigurieren der automatisierten ereignisbasierten Aufbewahrung für dieses Szenario:**

![Diagramm zu Rollen und Aktionen für das Szenario, in dem Mitarbeiter aus dem Unternehmen austreten](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - Der Administrator erstellt in der Dokumentenmappe mehrere Mitarbeiterordner, zum Beispiel Jane Doe, John Smith.

  - Der Administrator fügt zu jedem Mitarbeiterordner mitarbeiterbezogene Dateien hinzu, zum Beispiel Leistungen, Lohn, Vergütung.

  - Der Administrator weist jedem Mitarbeiterordner eine Asset-ID zu. 

  - Der SCC-Administrator meldet sich beim Security & Compliance Center an.

  - SCC-Administrator erstellt mitarbeiterbezogene Ereignistypen wie „Beschäftigungsende“, „Einstellung des Mitarbeiters“.

  - SCC-Administrator erstellt Bezeichnung „Mitarbeiterbindung“.

  - Diese Bezeichnung wird veröffentlicht und manuell oder automatisch auf die Dateien des Mitarbeiters in SharePoint angewendet.

  - Ein HR-Managementsystem wie Workday kann regelmäßig mit Microsoft Flow verwendet werden, um die Dateien von Mitarbeitern zu verwalten.

  - Wenn ein Mitarbeiter aus dem Unternehmen ausgetreten ist, löst der Ablauf die Microsoft 365-REST-API für die ereignisbasierte Aufbewahrung aus, die den Aufbewahrungszeitraum für die Dateien eines bestimmten Mitarbeiters startet.

#### <a name="using-microsoft-flow"></a>Verwenden von Microsoft Flow

Schritt 1: Erstellen eines Ablaufs zum Erstellen einer Ereignisses mithilfe der Microsoft 365-REST-API

![Verwenden von Flow zum Erstellen eines Ereignisses](../media/automate-event-driven-retention-flow-1.png)

![Verwenden des Ablaufs zum Aufrufen der REST-API](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a>Erstellen eines Ereignisses

Beispielcode zum Aufrufen der REST-API

<table>
<thead>
<tr class="header">
<th>Methode</th>
<th>POST</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>URL</td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td>Header</td>
<td>Content-Type</td>
<td>application/atom+xml</td>
</tr>
<tr class="odd">
<td>Body</td>
<td><p>&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</p>
<p>&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</p>
<p>xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</p>
<p>xmlns='https://www.w3.org/2005/Atom'&gt;</p>
<p>&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</p>
<p>&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</p>
<p>&lt;content type='application/xml'&gt;</p>
<p>&lt;m:properties&gt;</p>
<p>&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</p>
<p>&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</p>
<p>&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</p>
<p>&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</p>
<p>&lt;/m:properties&gt;</p>
<p>&lt;/content&gt;</p>
<p>&lt;/entry&gt;</p></td>
<td></td>
</tr>
<tr class="even">
<td>Authentication</td>
<td>Basic</td>
<td></td>
</tr>
<tr class="odd">
<td>Username</td>
<td>“Complianceuser”</td>
<td></td>
</tr>
<tr class="even">
<td>Password</td>
<td>“Compliancepassword”</td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a>Verfügbare Parameter

<table>
<thead>
<tr class="header">
<th><strong>Parameter</strong></th>
<th><strong>Beschreibung</strong></th>
<th><strong>Hinweise</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>&lt;d:Name&gt;&lt;/d:Name&gt;</td>
<td>Geben Sie einen eindeutigen Namen für das Ereignis an.</td>
<td>Der Name darf nachfolgende Leerzeichen und die folgenden Zeichen nicht enthalten: % * \ &amp; &lt; &gt; | # ? , : ;</td>
</tr>
<tr class="even">
<td>&lt;d:EventType&gt;&lt;/d:EventType&gt;</td>
<td>Geben Sie den Namen des Ereignistyps (oder GUID) ein.</td>
<td>Beispiel: „Austritt eines Mitarbeiters“. Der Ereignistyp muss mit einer Aufbewahrungsbezeichnung verknüpft sein.</td>
</tr>
<tr class="odd">
<td>&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</td>
<td>Geben Sie „ComplianceAssetId:“ und die Mitarbeiter-ID ein.</td>
<td>Beispiel:&quot;ComplianceAssetId:12345&quot;</td>
</tr>
<tr class="even">
<td>&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</td>
<td>Datum und Uhrzeit des Ereignisses.</td>
<td><p>Format: jjjj-MM-ttTHH:mm:ssZ, Beispiel:</p>
<p>2018-12-01T00:00:00Z</p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a>Antwortcodes

| **Antwortcode** | **Beschreibung**       |
| ----------------- | --------------------- |
| 302               | Umleiten              |
| 201               | Erstellt               |
| 403               | Autorisierung fehlgeschlagen  |
| 401               | Authentifizierung fehlgeschlagen |

##### <a name="get-events-based-on-time-range"></a>Abrufen von Ereignissen basierend auf dem Zeitraum

<table>
<thead>
<tr class="header">
<th>Methode</th>
<th>GET</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>URL</td>
<td><ol start="4" type="1">
<li><p>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td>Header</td>
<td>Content-Type</td>
<td>application/atom+xml</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Authentication</td>
<td>Basic</td>
<td></td>
</tr>
<tr class="odd">
<td>Username</td>
<td>“Complianceuser”</td>
<td></td>
</tr>
<tr class="even">
<td>Password</td>
<td>“Compliancepassword”</td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a>Antwortcodes

| **Antwortcode** | **Beschreibung**                   |
| ----------------- | --------------------------------- |
| 200               | OK, eine Liste der Ereignisse in Atom + XML |
| 404               | Nicht gefunden                         |
| 302               | Umleiten                          |
| 401               | Autorisierung fehlgeschlagen              |
| 403               | Authentifizierung fehlgeschlagen             |

##### <a name="get-an-event-by-id"></a>Abrufen eines Ereignisses nach ID

| Methode         | GET   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| URL            | [https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\)) |                      |
| Header         | Content-Type                                                                                                                                                                                                                                                       | application/atom+xml |
| Authentication | Basic                                                                                                                                                                                                                                                              |                      |
| Username       | “Complianceuser”                                                                                                                                                                                                                                                   |                      |
| Password       | “Compliancepassword”                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a>Antwortcodes

| **Antwortcode** | **Beschreibung**                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | OK, der Antworttext enthält das Ereignis in Atom + XML |
| 404               | Nicht gefunden                                            |
| 302               | Umleiten                                             |
| 401               | Autorisierung fehlgeschlagen                                 |
| 403               | Authentifizierung fehlgeschlagen                                |

##### <a name="get-an-event-by-name"></a>Abrufen eines Ereignisses anhand des Namens

| Methode         | GET       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| URL            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| Header        | Content-Type                                                                                                                                 | application/atom+xml |
| Authentication | Basic                                                                                                                                        |                      |
| Username       | “Complianceuser”                                                                                                                             |                      |
| Password       | “Compliancepassword”                                                                                                                         |                      |

##### <a name="response-codes"></a>Antwortcodes

| **Antwortcode** | **Beschreibung**                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | OK, der Antworttext enthält das Ereignis in Atom + XML |
| 404               | Nicht gefunden                                            |
| 302               | Umleiten                                             |
| 401               | Autorisierung fehlgeschlagen                                 |
| 403               | Authentifizierung fehlgeschlagen                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a>Verwenden von PowerShell (Version 6 oder höher) oder eines beliebigen HTTP-Clients

Schritt 1: Stellen Sie eine Verbindung zu PowerShell her.

Schritt 2: Führen Sie das folgende Skript aus.

<table>
<tbody>
<tr class="odd">
<td><p>param([string]$baseUri)</p>
<p>$userName = &quot;UserName&quot;</p>
<p>$password = &quot;Password&quot;</p>
<p>$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</p>
<p>$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</p>
<p>$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</p>
<p>Write-Host &quot;Start to create an event with name: $EventName&quot;</p>
<p>$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</p>
<p>&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</p>
<p>xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</p>
<p>xmlns='https://www.w3.org/2005/Atom'&gt;</p>
<p>&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</p>
<p>&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</p>
<p>&lt;content type='application/xml'&gt;</p>
<p>&lt;m:properties&gt;</p>
<p>&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</p>
<p>&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</p>
<p>&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</p>
<p>&lt;/m:properties&gt;</p>
<p>&lt;/content&gt;</p>
<p>&lt;/entry&gt;&quot;</p>
<p>$event = $null</p>
<p>try</p>
<p>{</p>
<p>$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</p>
<p>}</p>
<p>catch</p>
<p>{</p>
<p>$response = $_.Exception.Response</p>
<p>if($response.StatusCode -eq &quot;Redirect&quot;)</p>
<p>{</p>
<p>$url = $response.Headers.Location</p>
<p>Write-Host &quot;redirected to $url&quot;</p>
<p>$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</p>
<p>}</p>
<p>}</p>
<p>$event | fl *</p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a>Überprüfen der Ausgabe bei beiden Optionen

Schritt 1: Wechseln Sie zum Security & Compliance Center.

Schritt 2: Klicken Sie unter **Informationskontrolle** auf **Ereignisse**.

Schritt 3: Überprüfen Sie, ob das Ereignis erstellt wurde.

Ebenso können die aufgeführten Optionen zum Automatisieren der ereignisbasierten Aufbewahrung auch für die folgenden Szenarien verwendet werden.

### <a name="scenario-2-contracts-expiring"></a>Szenario 2: Ablauf von Verträgen

Eine Organisation kann mehrere Datensätze für einen einzigen Vertrag mit Kunden, Lieferanten und Partnern haben. Diese Dokumente können sich in einer Dokumentbibliothek wie SharePoint befinden. Das Vertragsende bestimmt den Anfang des Aufbewahrungszeitraums der Dokumente, die dem Vertrag zugeordnet sind. So müssen z. B. alle Datensätze im Zusammenhang mit Verträgen fünf Jahre lang ab dem Zeitpunkt aufbewahrt werden, ab dem der Vertrag abläuft. Das Ereignis, das den Aufbewahrungszeitraum von fünf Jahren ausgelöst, ist der Ablauf des Vertrags.

Ein CRM-System kann mit Microsoft 365 verwendet werden und die Aufbewahrung für Vertragsdokumente auslösen.

**Konfigurieren der automatisierten ereignisbasierten Aufbewahrung für dieses Szenario:**

![Diagramm zu Rollen und Aufgaben für das Szenario zum Ablauf von Verträgen](../media/automate-event-driven-retention-contract-expiration.png)

  - Der Administrator erstellt eine SharePoint-Bibliothek mit verschiedenen Ordnern für jeden Vertragstyp.

  - Der Administrator fügt Vertragsdateien zu jedem Vertragsordner hinzu, zum Beispiel Lizenzverträge, Entwicklungsverträge.

  - Der Administrator weist jedem Vertragsordner eine Objekt-ID zu.

  - Der SCC-Administrator meldet sich beim Security & Compliance Center an.

  - Der SCC-Administrator erstellt vertragsbezogene Ereignisse wie „Erstellung des Vertrags“, „Ablauf des Vertrags“.

  - Der SCC-Administrator erstellt die Bezeichnung „Vertragsende“.

  - Diese Bezeichnung wird veröffentlicht und manuell oder automatisch auf die Vertragsdateien in SharePoint angewendet.

  - Ein Vertragsmanagementsystem kann mit Microsoft Flow oder einer ähnlichen Anwendung regelmäßig verwendet werden, um Vertragsdateien zu verwalten.

  - Wenn ein Vertrag abläuft, löst Microsoft Flow die Microsoft 365-REST-API für die ereignisbasierte Aufbewahrung aus, die den Aufbewahrungszeitraum für die Vertragsdateien startet.

### <a name="scenario-3-end-of-product-manufacturing"></a>Szenario 3: Ende der Produktherstellung

Ein Produktionsunternehmen, das verschiedene Produktlinien herstellt, erstellt viele Fertigungsspezifikationen und Preisgestaltungsdokumente. Wenn das Produkt nicht mehr hergestellt wird, müssen alle mit diesem Produkt verknüpften Spezifikationen und Dokumente über einen bestimmten Zeitraum ab Ende der Lebensdauer des Produkts aufbewahrt werden.

Ein ERP-System kann mit Microsoft 365 und Microsoft Flow verwendet werden, um die Aufbewahrung auszulösen.

**Konfigurieren der automatisierten ereignisbasierten Aufbewahrung für dieses Szenario:**

![Diagramm zu Rollen und Aufgaben für ein Produktlebenszyklusszenario](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - Der Administrator erstellt in der Dokumentenmappe Produktordner wie Produkt 1, Produkt 2 usw.

  - Der Administrator fügt jedem Produktordner Produktdateien hinzu, zum Beispiel Fertigungsspezifikationen, Produktpreisgestaltung, Produktlizenzierung.

  - Der Administrator weist jedem Produktordner eine Objekt-ID zu.

  - Der SCC-Administrator meldet sich beim Security & Compliance Center an.

  - Der SCC-Administrator erstellt produktbezogene Ereignistypen, zum Beispiel „Beginn der Produktherstellung“, „Ende der Produktherstellung“.

  - Der SCC-Administrator erstellt die Bezeichnung „Ende der Produktherstellung“.

  - Diese Bezeichnung wird veröffentlicht und manuell oder automatisch auf die Produktdateien in SharePoint angewendet.

  - ERP-Systeme können mit Microsoft Flow oder ähnlichen Anwendungen regelmäßig verwendet werden, um Produktdateien zu verwalten.

  - Wenn die Herstellung eines Produkts endet, löst Microsoft Flow die Microsoft 365-REST-API für die ereignisbasierte Aufbewahrung aus, die den Aufbewahrungszeitraum für die Produktdateien startet.

## <a name="appendix"></a>Anhang

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a>Verwenden der Redirect 302-Antwortergebnisse zum Aufrufen der REST-API

1. Rufen Sie einen POST-Aufbewahrungsereignisaufruf mithilfe der REST-API-URL auf <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (globale Administratorrechte sind erforderlich).

2. Überprüfen Sie den Antwortcode. Wenn dies 302 ist, rufen Sie die Umleitungs-URL aus der Location-Eigenschaft des Antwortheaders ab.

3. Rufen Sie den POST-Aufbewahrungsereignisaufruf erneut mithilfe der Umleitungs-URL auf.

## <a name="credits"></a>Mitwirkende

Dieses Thema wurde von überprüft von:

Antonio Maio<br/>MVP für Microsoft Office-Apps und -Dienste<br/> Antonio.Maio@Protiviti.com
