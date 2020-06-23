---
title: Microsoft-Sicherheitsbewertung (neu)
description: Beschreibt die Microsoft-Sicherheitsbewertung im Microsoft 365 Security Center, erläutert die Berechnung von Details und was Sicherheitsadministratoren von der Verwendung der Funktion erwarten dürfen.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitsbewertung, Security Center, Verbesserungsmaßnahmen
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: dbc8d1e8dae1845412b1fb3ad86b831b08a4a518
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327144"
---
# <a name="microsoft-secure-score-new"></a>Microsoft-Sicherheitsbewertung (neu)

>[!IMPORTANT]
>Diese neue Iteration von Microsoft-Sicherheitsbewertung ersetzt die vorherige Iteration in den nächsten Monaten durch neue Designelemente und Funktionen.
>
>Wenn neben „Verlauf“ keine Registerkarte **Metriken und Trends** angezeigt wird, befinden Sie sich in der vorherigen Iteration. [Wechseln Sie zur Microsoft-Sicherheitsbewertung (vorherige Iteration)](microsoft-secure-score.md)

Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden. Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).

Wenn Sie den Empfehlungen der Sicherheitsbewertung folgen, können Sie Ihre Organisation vor Bedrohungen schützen. Über ein zentrales Dashboard im Microsoft 365 Security Center können Organisationen die Sicherheit ihrer Microsoft 365-Identitäten, Daten, Apps, Geräte und Infrastruktur überwachen und daran arbeiten.

Sicherheitsbewertung hilft Organisationen auf diese Arten:  

* Berichtet über den aktuellen Sicherheitsstatus der Organisation.
* Verbessert den Sicherheitsstatus durch Auffindbarkeit, Transparenz, Anleitung und Kontrolle.  
* Ermöglicht Vergleiche mit Benchmarks und erstellt KPIs (Key Performance Indicators).

Organisationen erhalten Zugriff auf zuverlässige Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, einen Vergleich mit ähnlichen Organisationen und vieles mehr. Die Bewertung zeigt auch, wenn Lösungen von Drittanbietern empfohlene Maßnahmen behandelt haben.

Darüber hinaus können Sie über die [Microsoft Graph-API](https://www.microsoft.com/security/partnerships/graph-security-api)auf Ihre Empfehlungen und Bewertungen zugreifen. Erfahren Sie mehr über den [Ressourcentyp Sicherheitsbewertung](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Funktionsweise

Sie erhalten Punkte für die Konfiguration empfohlener Sicherheitsfunktionen, die Ausführung sicherheitsrelevanter Aufgaben oder die Behandlung von Verbesserungsmaßnahmen mit einer Drittanbieteranwendung oder -software oder einer alternativen Korrektur. Einige Verbesserungsmaßnahmen geben nur Punkte, wenn sie vollständig abgeschlossen sind, und einige geben schon Punkte, auch wenn sie nur für einige Geräte oder Benutzer abgeschlossen sind. Wenn Sie eine der Verbesserungsmaßnahmen nicht ausführen können oder möchten, können Sie sich entschließen, das Risiko bzw. das Restrisiko zu übernehmen.

Wir zeigen Ihnen die vollständige Palette möglicher Verbesserungen – unabhängig von der Lizenz –, damit Sie bewährte Methoden für die Sicherheit verstehen und Ihre Punktzahl verbessern können. Sicherheitsbewertung stellt Ihren absoluten Sicherheitsstatus dar, der unverändert bleibt, unabhängig von den Lizenzen Ihrer Organisation. Bitte bedenken Sie: Sicherheit sollte mit Benutzerfreundlichkeit in Einklang gebracht werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung.

Ihre Bewertung wird in Echtzeit aktualisiert, um die Informationen auf den Seiten Visualisierung und Verbesserungsmaßnahmen darzustellen. Sicherheitsbewertung wird auch täglich synchronisiert, um Systemdaten zu Ihren erreichten Punkten für jede Aktion zu erhalten.

### <a name="how-improvement-actions-are-scored"></a>Wie Verbesserungsmaßnahmen bewertet werden

Jede Verbesserungsmaßnahme hat einen Wert von höchstens 10 Punkten. Die meisten werden auf binäre Art bewertet – wenn Sie die Verbesserungsmaßnahme umsetzen, wie z. B. eine neue Richtlinie erstellen oder eine bestimmte Einstellung aktivieren –, erhalten Sie die volle Punktzahl. Bei anderen Verbesserungsmaßnahmen werden Punkte als Prozentsatz der Gesamtkonfiguration gegeben. Wenn Sie beispielsweise für die Verbesserungsmaßnahme 30 Punkte erhalten, wenn Sie alle Ihre Benutzer mit einer mehrstufigen Authentifizierung schützen, aber nur 5 von insgesamt 100 Benutzern geschützt sind, dann erhalten Sie eine Teilpunktzahl von ca. 2 Punkten (5 geschützt/100 insgesamt * 30 Maximalpunktzahl = 2 Punkte Teilpunktzahl).

### <a name="products-included-in-secure-score"></a>Produkte in Sicherheitsbewertung

Derzeit gibt es Empfehlungen für Microsoft 365 (einschließlich Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP und Cloud App Security. Empfehlungen für andere Sicherheitsprodukte werden in Kürze verfügbar sein. Die Empfehlungen umfassen nicht alle Angriffsflächen, die jedem Produkt zugeordnet sind, sind aber ein guter Ausgangsbasis. Sie können die Verbesserungsmaßnahmen auch als „über Drittanbieter abgedeckt“ oder „ durch alternative Korrektur abgedeckt“ markieren.

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Um die Zugriffsberechtigung auf die Microsoft-Sicherheitsbewertung zu erhalten, müssen Sie eine der folgenden Rollen in Azure Active Directory besitzen.

### <a name="read-and-write-roles"></a>Rollen "Lesen und Schreiben"

Mit Lese- und Schreibzugriff können Sie Änderungen vornehmen und mit Sicherheitsbewertung direkt interagieren. Sie können anderen Benutzern auch schreibgeschützten Zugriff zuweisen.

* Globaler Administrator
* Sicherheitsadministrator
* Exchange-Administrator
* SharePoint-Administrator
* Kontoadministrator

### <a name="read-only-roles"></a>Schreibgeschützte Rollen

Bei schreibgeschütztem Zugriff können Sie den Status oder die Notizen für eine Verbesserungsmaßnahme nicht bearbeiten, sowie keine Ergebniszonen oder benutzerdefinierte Vergleiche bearbeiten.

* Helpdesk-Administrator
* Benutzeradministrator
* Service-Administrator
* Benutzer mit Leseberechtigung für Sicherheitsfunktionen
* Sicherheitsoperator
* Globaler Leser

### <a name="graph-api"></a>Graph-API

Für den Zugriff auf die Graph-API benötigen Sie, zusätzlich zu einer Rolle, einen der folgenden Bereiche:

* SecurityEvents.Read.All (für schreibgeschützte Rollen)
* SecurityEvents.ReadWrite.All (für „Lesen und Schreiben“-Rollen)

## <a name="gain-visibility-into-your-security-posture"></a>Erhalten Sie Einblicke in Ihren Sicherheitsstatus

Damit Sie die benötigten Informationen schneller finden können, sind die Microsoft Verbesserungsmaßnahmen in Gruppen aufgeteilt:

* Identität (Azure AD-Konten & -Rollen)
* Daten (Microsoft Information Protection)
* Gerät (Microsoft Defender ATP)
* App (E-Mail-und Cloud-Apps, einschließlich Office 365 und Microsoft Cloud App Security)
* Infrastruktur (bisher keine Verbesserungsmaßnahmen)

>[!NOTE]
>In der letzten Version von Microsoft-Sicherheitsbewertung wurde ein verbessertes Bewertungsmodell veröffentlicht, das zu einer vorübergehenden Inkompatibilität der Microsoft-Sicherheitsbewertung mit der Identitätssicherheitsbewertung und der Graph-API geführt hatte. [Details anzeigen](microsoft-secure-score-new.md#incompatibility-with-identity-secure-score-and-graph-api)

Auf der Übersicht der Microsoft-Sicherheitsbewertung können Sie sehen, wie die Punkte zwischen diesen Gruppen aufgeteilt werden und welche Punkte verfügbar sind. Auf der Übersichtsseite können Sie auch einen Überblick über die Gesamtpunktzahl, den historischen Trend Ihres Sicherheitsbewertung mit Benchmark-Vergleichen sowie priorisierte Verbesserungsmaßnahmen zur Verbesserung ihrer Punktzahl erhalten.

![Startseite der Sicherheitsbewertung](../../media/secure-score/secure-score-homepage-new.png)


## <a name="take-action-to-improve-your-score"></a>Ergreifen Sie Maßnahmen, um Ihre Punktzahl zu verbessern

Auf der Registerkarte **Verbesserungsmaßnahmen** werden die Sicherheitsempfehlungen, die mögliche Angriffsflächen behandeln, zusammen mit deren Status („Zu behandeln“, „Geplant“, „Risiko akzeptiert“, „Von Drittanbieter behoben“, „Durch alternative Korrektur behoben“ und „Erledigt“) aufgelistet. Sie können alle Verbesserungsmaßnahmen durchsuchen, filtern und gruppieren.  

### <a name="ranking"></a>Rangfolge

Die Bewertung basiert auf der Anzahl der noch zu erreichenden Punkte, der Implementierungsschwierigkeit, der Auswirkungen auf die Benutzer und der Komplexität. Die am höchsten bewerteten Verbesserungen bieten viele Punkte mit geringem Schwierigkeitsgrad, Auswirkungen auf Benutzer, sowie Komplexität.

### <a name="view-improvement-action-details"></a>Anzeigen von Details zu Verbesserungsmaßnahmen

Wenn Sie eine bestimmte Verbesserungsmaßnahme auswählen, wird ein vollständiges Seiten-Flyout angezeigt.  

![Beispiel für Verbesserungsmaßnahmen-Flyout](../../media/secure-score/secure-score-improvement-action-details.png)
*Abbildung 2: Beispiel für Verbesserungsmaßnahmen-Flyout*

Zum Ausführen der Maßnahme stehen Ihnen verschiedene Optionen zur Verfügung:

* Wählen Sie **Verwalten** aus, um in den Konfigurationsbildschirm zu wechseln und die Änderung vorzunehmen. Dann erhalten Sie die Punkte, die die Maßnahme wert ist und wie sie im Flyout angezeigt werden. Es dauert in der Regel bis zu 24 Stunden, bis Punkte aktualisiert werden.

* Wählen Sie **Teilen** aus, um den direkten Link zu der Verbesserungsmaßnahme zu kopieren, oder wählen Sie die Plattform für das Teilen des Links aus, z. B. E-Mail, Microsoft Teams, Microsoft Planner oder ServiceNow. Wenn Sie ServiceNow auswählen, können Sie ein Änderungsticket erstellen, das in ServiceNow und auf der Startseite des Microsoft 365 Security Center angezeigt wird. Weitere Informationen hierzu finden Sie unter [Microsoft 365 Security Center und ServiceNow-Integration](tickets.md).

### <a name="choose-an-improvement-action-status"></a>Auswählen eines Verbesserungsmaßnahmenstatus

Wählen Sie beliebige Status aus, und zeichnen Sie Notizen auf, die für die Verbesserungsmaßnahme spezifisch sind. Sie können die folgenden Status auswählen:

* **Zu behandeln**: Sie erkennen an, dass die Verbesserungsmaßnahme notwendig ist, und planen deren Durchführung zu einem späteren Zeitpunkt. Dieser Zustand gilt auch für Maßnahmen, die als teilweise, aber noch nicht vollständig erledigt erkannt wurden.
* **Geplant**: Es gibt konkrete Pläne, die Verbesserungsmaßnahme auszuführen.
* **Risiko akzeptiert**: Sicherheit sollte immer mit Benutzerfreundlichkeit in Einklang stehen, und nicht jede Empfehlung wird für Ihre Umgebung funktionieren. Wenn dies der Fall ist, können Sie sich entschließen, das Risiko bzw. das Restrisiko zu übernehmen und die Verbesserungsmaßnahme nicht zu ergreifen. Sie erhalten keine Punkte, aber die Maßnahme wird in der Liste der Verbesserungsmaßnahmen nicht mehr angezeigt. Sie können diese Aktion jederzeit im Verlauf anzeigen oder rückgängig machen.
* **Von Drittanbieter behoben** und **Durch alternative Korrektur behoben**:Die Verbesserungsmaßnahme wurde bereits von einer Drittanbieteranwendung oder -software oder einem internen Tool vorgenommen. Sie erhalten die Punkte, die die Maßnahme wert ist, damit Ihre Bewertung Ihren Sicherheitsstatus im Ganzen besser widerspiegelt. Wenn ein Drittanbieter- oder internes Toll diese Maßnahme nicht mehr abdeckt, können Sie einen anderen Status auswählen. Bitte beachten Sie, dass Microsoft keinen Einblick in die Vollständigkeit der Implementierung besitzt, wenn die Verbesserungsmaßnahme mit einem dieser Status gekennzeichnet ist.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Verbesserungsmaßnahmen für Bedrohungs- und Sicherheitsrisikoverwaltung

Für Verbesserungsmaßnahmen in der Kategorie „Gerät“ können Sie keinen Status auswählen. Stattdessen werden Sie zu der zugeordneten [Sicherheitsempfehlung des Bedrohungs- und Sicherheitsrisikomanagements (TVM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) im [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) geleitet, um Maßnahmen zu ergreifen. Die Ausnahme, die Sie auswählen, und die Begründung, die Sie schreiben, sind spezifisch für dieses Portal und finden sich nicht im Microsoft-Sicherheitsbewertungsportal.

#### <a name="completed-improvement-actions"></a>Erledigte Verbesserungsmaßnahmen

Verbesserungsmaßnahmen haben den Status „Erledigt“, sobald alle möglichen Punkte der Verbesserungsmaßnahme erzielt wurden. Erledigte Verbesserungsmaßnahmen werden durch Microsoft-Daten bestätigt, und Sie können den Status nicht ändern.

### <a name="assess-information-and-review-user-impact"></a>Bewerten von Informationen und Überprüfen der Auswirkungen auf Benutzer

Im Abschnitt **Auf einen Blick** erfahren Sie die Kategorie, Angriffe, vor denen Sie geschützt werden können, sowie das Produkt.

Die **Benutzerauswirkungen** zeigen, was bei den Benutzern geschieht, wenn die Verbesserungsmaßnahme vorgenommen wird, und unter **Betroffene Benutzer** wird angezeigt, wer diese Erfahrungen machen wird.

### <a name="implement-the-improvement-action"></a>Implementieren der Verbesserungsmaßnahmen

Im Abschnitt **Implementierung** werden alle Voraussetzungen, schrittweise die nächsten Schritte zum Durchführen der Verbesserungsmaßnahme, der aktuelle Implementierungsstatus der Verbesserungsmaßnahme sowie alle „Weitere Informationen“-Links angezeigt.

Voraussetzungen sind alle Lizenzen, die Sie besitzen müssen, oder Aktionen, die ausgeführt werden müssen, bevor die Verbesserungsmaßnahme vorgenommen wird. Vergewissern Sie sich, dass Ihre Lizenz genügend Plätze abdeckt, um die Verbesserungsmaßnahme vornehmen zu können, und dass diese Lizenzen auf die erforderlichen Benutzer angewendet werden.  

## <a name="track-your-score-history-and-meet-goals"></a>Nachverfolgen Ihres Bewertungsverlaufs und Erfüllen von Zielen

Auf der Registerkarte **Verlauf** können Sie einen Graph der Bewertung Ihrer Organisation anzeigen. Unterhalb des Diagramms finden Sie eine Liste aller Maßnahmen, die im ausgewählten Zeitraum ausgeführt wurden, und deren Attributen, wie etwa die Kategorie und die resultierenden Punkte. Sie können einen Datumsbereich anpassen und nach Kategorie filtern.

Auf der Registerkarte **Metriken und Trends** finden Sie mehrere Graphen und Diagramme, die Ihnen einen besseren Einblick in Trends und festgelegte Ziele ermöglichen. Sie können den Datumsbereich für die gesamte Seite der Visualisierungen festlegen. Die Visualisierungen umfassen:

* **Ihre Sicherheitsbewertungszone**: Angepasst, basierend auf den Zielen und Definitionen Ihrer Organisation für die Bewertungsbereiche „Gut“, „OK“ und „Schlecht“.
* **Verschlechterungstrend**: Eine Zeitachse mit Punkten, die sich aufgrund von Änderungen an der Konfiguration, am Benutzer oder am Gerät verschlechtert haben.  
* **Vergleichstrend**: Wie die Sicherheitsbewertung Ihrer Organisation im Vergleich mit anderen im zeitlichen Verlauf abschneidet. Diese Ansicht kann Linien enthalten, die den Bewertungsdurchschnitt von Organisationen mit ähnlicher Anzahl von Plätzen darstellt, sowie eine benutzerdefinierte Vergleichsansicht, die Sie festlegen können.
* **Risikoakzeptanztrend**: Zeitachse mit Verbesserungsmaßnahmen, die mit „Risiko akzeptiert“ gekennzeichnet sind.
* **Änderungen an der Bewertung**: Die Anzahl der erzielten Punkte, verschlechterter Punkte sowie der sich anschließenden Bewertungsänderung im angegebenen Datumsbereich.

## <a name="risk-awareness"></a>Risikobewusstsein

Die Microsoft-Sicherheitsbewertung ist eine numerische Zusammenfassung Ihres Sicherheitsstatus, die auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsrelevanten Maßstäben basiert. Hierbei handelt es sich nicht um eine absolute Messung, wie wahrscheinlich eine Sicherheitsverletzung Ihres System oder Ihrer Daten ist. Vielmehr stellt Sie das Ausmaß dar, in dem Sie Sicherheitskontrollen in Ihrer Microsoft-Umgebung eingeführt haben, die das Risiko einer Sicherheitsverletzung ausgleichen können. Kein Onlinedienst ist vollkommen immun gegen Sicherheitsverstöße, und Sicherheitsbewertung sollte in keiner Weise als Garantie gegen Sicherheitsverstöße interpretiert werden.

## <a name="whats-new"></a>Was sind die Neuerungen? 

Damit die Microsoft-Sicherheitsbewertung zu einem besseren Ansprechpartner für Ihren Sicherheitsstatus wird, haben wir einige Änderungen vorgenommen. Wenn Sie mehr über geplante Änderungen wissen möchten, lesen Sie [Bald in der Microsoft-Sicherheitsbewertung verfügbar](microsoft-secure-score-whats-coming.md).

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Inkompatibilität mit der Identitätssicherheitsbewertung und der Graph-API

In der letzten Version von Microsoft-Sicherheitsbewertung wurde ein verbessertes Bewertungsmodell veröffentlicht. Diese Änderungen ermöglichen eine flexiblere und präzisere Ansicht Ihres Sicherheitsstatus. Diese Updates haben jedoch zu einer vorübergehenden Inkompatibilität der Microsoft-Sicherheitsbewertung mit der Identitätssicherheitsbewertung und der Graph-API geführt.

Im Laufe der Zeit werden die Identitätssicherheitsbewertung und die Graph-API das neue Bewertungsmodell übernehmen. Bis dahin werden Kunden Unterschiede bei den von der Microsoft-Sicherheitsbewertung, der Identitätssicherheitsbewertung und der Graph-API gemeldeten Bewertungen feststellen. Wir entschuldigen uns für alle Unannehmlichkeiten, die hierdurch verursacht werden, und arbeiten an der Sicherstellung, dass diese Erfahrungen zukünftig kompatibler sein werden.

### <a name="updated-improvement-actions"></a>Aktualisierte Verbesserungsmaßnahmen

- Azure Active Directory-Verbesserungsmaßnahmen hinzugefügt
- Azure Advanced Threat Protection-Verbesserungsmaßnahmen hinzugefügt
- Unterstützung der Sicherheitsempfehlungen von Microsoft Defender ATP [Threat & Vulnerability Management (TVM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Alle von TVM bereitgestellten Sicherheitsempfehlungen, die freigegeben wurden, sind nun verfügbar.

### <a name="updated-interface-and-functionality"></a>Benutzeroberfläche und Funktionalität aktualisiert

* Völlig neue Metriken und Trend-Ansichten für CISO und Lead Level-Diskussionen
* Neue Möglichkeiten zum Nachverfolgen und Benchmarken Ihrer Bewertung
* Bessere Nachverfolgung und besseres Verständnis von Bewertungsverschlechterungen
* Filtern, Taggen, Suchen und Gruppieren von Verbesserungsmaßnahmen
* Verwalten Sie Ihre zukünftigen Ziele mithilfe von Score-Projektionen und geplanten Maßnahmen
* Und mehr!

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, informieren Sie uns mit einem Beitrag in der Community für [Sicherheit, Datenschutz und Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy). Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.
