---
title: Überlegungen zum Managementplan der Geschäftskontinuität für Großunternehmen
author: chrfox
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Aspekte, die bei der Entwicklung eines Cloud-bewussten Geschäftskontinuitätsplans berücksichtigt werden müssen.
ms.openlocfilehash: 4a133c65f6a5a2de44e871995886a01c2ce8e9a9
ms.sourcegitcommit: 7690c8bfdea6e6d245cfa7c5b09b913b092cde0a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "37122335"
---
# <a name="developing-your-continuity-plan"></a>Entwickeln Ihres Kontinuitätsplans

Unter diesem Thema finden Sie Anleitungen zum Entwickeln eines Geschäftskontinuitätsplans, der Microsoft 365-Abhängigkeiten berücksichtigt. Hier empfehlen wir Methoden, wie Sie Ihre Geschäftsfunktionen analysieren und bestimmen, welche von Microsoft 365-Diensten abhängig sind. Sie führen diese Analyse mit der Erwartungshaltung aus, dass es Dienstausfälle geben wird und Sie sich darauf vorbereiten müssen.

Im Allgemeinen umfasst die Planung der Geschäftskontinuität vier Aspekte: Bewertung, Planung, Funktionsüberprüfung sowie Kommunikation und Koordination.

## <a name="assesment"></a>Bewertung
Zuerst müssen Sie die Geschäftsfunktionen in Ihrer Organisation und die Dienste und Prozesse ermitteln, die Sie unterstützen. Dies umfasst das Abschließen einer Analyse geschäftlicher Auswirkungen, bei der jede Geschäftsfunktion nach ihrer Wichtigkeit bewertet wird, und Sie ermitteln die Prozesse und Dienste, von denen jede abhängig ist. Hier ist eine Beispieltabelle, auf die Sie für die ersten Schritte bei Ihrer Bewertung zurückgreifen können.

**Beispiel für die Bewertung geschäftlicher Auswirkungen (Business Impact Assessment, BIA)**

Dies ist ein BIA-Dokument für `name of the service, system, process, or function`

|BIA-Felder|Beschreibung|
|---------|---------|
|BIA-Typ|`is it a business process or technology, service or system?`|
|BIA-Name|`name of the service/system/function/process`|
|Dienstbeschreibung|`give a full description of the service, process, or function`|
|Unternehmensfunktion|`some examples: customer services; legal; marketing; risk management, security, sales, information technology, production, manufacturing`|
|Geschäftsjahr|`the current fiscal year, re-evaluate these on a regular basis`|
|Kritikalität|`develop your own classifications, but here are some examples: mission critical, important, deferrable`|
|Geschäftsbereich|`name of the business unit that owns this business function`|
|Prozess (Dienst, Funktion)|`the name of the process, service, or feature`|
|Leiter der Unternehmensgruppe|`the name and contact information of the senior leader of the business group that owns this business process`|
|Besitzt die Technologie ein eingeführtes **internes** SLA oder OLA?|`please explain in as much detail as possible`|
|Besitzt die Technologie ein eingeführtes **externes** SLA oder OLA?|`please explain in as much detail as possible`|
|Besitzt die Technologie ein bekanntes leitendes Mandat, das ein bestimmtes SLA für Prozesse steuert? Wenn ja, geben Sie eine ausführliche Erklärung.|`details here`|
|Wird durch den Verlust oder die Kompromittierung der mit diesen Diensten verbundenen Daten ein großes Ereignis ausgelöst? Wenn ja, geben Sie eine ausführliche Erklärung.|`details here`|
|Gibt es für den Dienst eine vorhandene Problemumgehung oder Alternative für einige oder alle seine wichtigen Funktionen und Features? Wenn ja, geben Sie eine ausführliche Erklärung.|`details here`|
|Verarbeitet, speichert oder überträgt der Dienst Kundendaten (PII)? Wenn ja, geben Sie eine ausführliche Erklärung.|`details here`|
|BIA-Status|`develop your own status classification, here are some examples: planned, started, in-progress, complete, on-hold, expired`|
|Abschlussdatum|`the date this BIA was completed`|
|BIA-Vermittler|`name of the person or group who is responsible for developing and maintaining this BIA`|
|BIA-Genehmigung|`name of the person or group who is the executive sponsor of this BIA and who has responsibility for approving it.`|
|Mitwirkende|`optional list of the people who helped develop this BIA and their contact information`|
|BIA-Genehmigungsspeicherort|`indicate where the executive approval is located, or attach proof to this document`|

## <a name="planning"></a>Planung

Als Nächstes sehen Sie sich die Geschäftsprozesse an, um zu sehen, wo kaskadierende Abhängigkeitsbeziehungen bestehen. Auf der Grundlage des Ergebnisses priorisieren und bilden Sie Ausfallsicherheitsstrategien und Standardbetriebsverfahren, die Ihre Strategien unterstützen.

Sie können [Microsoft Service Map](https://docs.microsoft.com/de-DE/azure/azure-monitor/insights/service-map) verwenden, um Sie bei dieser Zuordnung zu unterstützen. Microsoft Service Map ermittelt automatisch Anwendungskomponenten auf Windows- und Linux-Systemen, ordnet alle TCP-Abhängigkeiten zu und ermittelt Verbindungen sowie Remotesysteme von Drittanbietern, von denen die App abhängig ist. Außerdem ordnet es Abhängigkeiten zu Bereichen Ihres Netzwerks zu, die herkömmlicherweise dunkel sind, z. B. Active Directory Domain Services.

Hier ist ein Beispiel für eine Abhängigkeitsanalyse (Dependency Analysis, DA), mit der Sie beginnen können. In Ihrer Abhängigkeitsanalyse (DA) bestimmen und überprüfen Sie die Prozessabhängigkeiten. Sorgen Sie dafür, dass Sie Personen, Lieferanten, Kunden, Partner und Einrichtungen einbeziehen. Die Daten aus dieser Analyse werden verwendet, um Lücken zwischen den Wiederherstellungsanforderungen eines Prozesses und den Wiederherstellungsfunktionen unterstützender Abhängigkeiten zu ermitteln.


|Feld|Beschreibung|
|---------|---------|
|Prozesstyp|         |
|Vermittler|         |
|abgeschlossen von|         |
|Abschlussdatum|         |
|Mitwirkende|         |
  
## <a name="capability-validation"></a>Funktionsüberprüfung

Sobald Sie Ihre Geschäftsprozesse inventarisiert und Beziehungen mit anderen Prozessen und Technologien verknüpft haben, müssen Sie Überprüfungsszenarien für alle Prozesse erstellen. Ermitteln Sie, wie Sie Ihre Kontinuitätspläne für Geschäftsprozesse grundsätzlich überprüfen. Sie werden wahrscheinlich feststellen, dass einige wichtiger als andere sind und Sie diese priorisieren möchten.
Vergessen Sie nicht, dass die regelmäßige Schulung von Mitarbeitern in der Reaktion auf Sicherheitsvorfälle und in Kontinuitätsmaßnahmen nach der Einführung des Plans wichtig ist. Vorfallnachprüfungen sollten dazu verwendet werden, Ihre Ausfallsicherheitsstrategien durch Einbeziehen der Erkenntnisse aus jeder Prüfung und jedem Test zu verbessern.

## <a name="incident-coordination-and-communication"></a>Vorfallskoordinierung und -kommunikation

Während eines Dienstvorfalls sind normale Kommunikationskanäle möglicherweise beeinträchtigt oder heruntergestuft, daher sollten Sie vorab Alternativen bestimmen, damit Ihre Organisation während eines Vorfalls verbunden bleibt. Es ist von entscheidender Bedeutung, dass die Kommunikationskanäle eingerichtet, auf Sicherheit und Compliance überprüft, und die Benutzer vor einer Unterbrechung in der Verwendung geschult sind. Bei Ausfällen von einer bekannten Lage zu einem anderen bekannten Zustand überzugehen, ist Benutzern, die mitten in einer Krise ad hoc unbekannte Lösungen aufbringen, um einiges vorzuziehen.

Bei Microsoft hat jedes Kundendienstteam interne alternative Kommunikationskanäle eingerichtet, um uns bei der Koordinierung zu helfen, wenn unsere normalen Kommunikationskanäle nicht verfügbar sind. Dazu gehören Lösungen zur Telefonie- und Audiokonferenzsicherung, Yammer-Gruppen, Teams-Gruppen, interne Service Health Dashboards und interne Software für das Vorfallsmanagement.

Während der Analyse geschäftlicher Auswirkungen und der Abhängigkeitsanalyse gestalten Sie entscheidende Prozesse und die Technologien und Dienste, von denen sie abhängen. Achten Sie während dieser Planungsphase besonders auf die Kommunikation und überlegen Sie sich Alternativen. Nun folgen einige Beispiele.

- Wenn E-Mail Ihre primäre Methode ist, Benutzer und Stakeholder auf dem Laufenden zu halten, und Ihr E-Mail-Dienst heruntergestuft wird oder nicht verfügbar ist, können Sie zur Sicherung einen anderen Dienst wie Microsoft Teams, Yammer oder einen anderen Drittanbieterdienst verwenden. Der entscheidende Punkt besteht darin, diese im Vorfeld einzurichten und Ihre Benutzer darin zu schulen, wohin sie sich wenden sollen. Ein Yammer-Thread wird nicht hilfreich sein, wenn niemand weiß, dass er existiert, oder ein Lesezeichen dafür erstellt hat.  
- Wenn sich Ihre internen Vorfallsmanagementprozesse bei der Koordinierung der Antworten auf Sprachkommunikation stützen, richten Sie eine alternative Telefonielösung zur Nutzung während einer Krise ein. Diese Lösung muss nicht in vollem Umfang mit Ihrem primären Dienst gleichwertig sein, sollte jedoch das Mindestmaß an Zusammenarbeit zur Koordinierung Ihrer Geschäftskontinuitäts- und Vorfallsmanagement-Teams bieten. Darüber hinaus kann das Auffordern von Benutzern, ihre Mobiltelefonnummern in Ihrer globalen Adressliste zu veröffentlichen, in Extremfällen eine zusätzliche Sicherung der Kommunikation darstellen.
- Sie können ein benutzerdefiniertes Service Health Dashboard oder eine andere derartige Website erstellen, die Statusaktualisierungen während eines Vorfalls bereitstellen kann. Die Schulung von Benutzern, wo Sie sich im Voraus informieren können, trägt dazu bei, unnötige Anrufe beim Helpdesk zu reduzieren und Ihrer Benutzerbasis Vertrauen einzuflößen, dass die Situation schnell und effizient gehandhabt wird. Verwenden Sie die Dienstkommunikations-API für O365, um diese in M365 einzubinden und die Transparenz weiter zu steigern.  
- Es ist von entscheidender Bedeutung, dass der Speicherort Ihrer Geschäftskontinuitätspläne und Standardbetriebsverfahren bekannt ist. Wir empfehlen, Online- und Offlinekopien wichtiger Dokumente zu pflegen, z. B. mit SharePoint Online oder OneDrive for Business, die für die automatische Synchronisierung lokaler Geräte konfiguriert sind. Bei Service- bzw. Netzwerkbetriebszentren und anderen ähnlichen Teams, die für die Wiederherstellung absolut maßgeblich sind, sollten Sie auch Hardcopys zur Verwendung im Notfall aufbewahren.

## <a name="know-your-external-points-of-integration"></a>Kennen Ihrer externen Integrationspunkte

Unabhängig vom Geschäftsmodell hat jedes Unternehmen Integrationspunkte mit seinen Kunden, Partnern und Lieferanten. Die Geschäftswert-Lieferkette basiert auf der Integration mit externen Entitäten. Um die Geschäftskontinuität im Fall einer Dienstunterbrechung zu verbessern, muss jeder Integrationspunkt berücksichtigt – und geschützt – werden.  
Während Sie Ihre Lieferkette analysieren, sollte die externe Kommunikation auf die gleiche Weise wie die interne Kommunikation betrachtet werden. Sind Ihre Kunden auf Ihre Exchange Online-Server als einzige Methode, sich an Sie zu wenden, angewiesen? Haben Sie alternative Kommunikationsmethoden eingerichtet und Ihre Lieferanten auf sie hingewiesen, falls die Betriebszeit beeinträchtigt wird? Hier ist eine Beispieltabelle als Vorschlag, wie Sie Ihre Gedanken ordnen können.

|Name der externen Entität|Szenario eines Vorfalls mit Auswirkung|Microsoft 365-Dienste integriert|Alternativen|
|---------|---------|---------|---------|
|`vendor name`|E-Mail-Fluss|Exchange Online ist das einzige Kommunikationsmittel bei Contoso|Einrichten externer Microsoft Teams-Kanäle oder einer Software von Drittanbietern für die Zusammenarbeit          |
|`service supplier name`|Chat|Microsoft Teams|Chat von Drittanbietern|
|`partner name`|VoIP|Microsoft Teams|mobiles oder öffentliches PSTN      |
|`supplier name`|Dateifreigabe|extern freigegebene SharePoint-Websites und OneDrive|Dateifreigabe von Drittanbietern         |
