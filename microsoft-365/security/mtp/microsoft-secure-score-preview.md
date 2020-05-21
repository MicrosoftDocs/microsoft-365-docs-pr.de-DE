---
title: Microsoft Secure Score (Vorschau)
description: Beschreibt Microsoft Secure Score im Microsoft 365 Security Center, wie Details berechnet werden und welche Sicherheitsadministratoren davon erwarten können.
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
ms.openlocfilehash: 4305d97d33439383989cf8c300522268727b1ae7
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327660"
---
# <a name="microsoft-secure-score-preview"></a>Microsoft Secure Score (Vorschau)

>[!IMPORTANT]
>Einige Informationen beziehen sich auf vorversions Produkte, die möglicherweise wesentlich geändert werden, bevor Sie kommerziell veröffentlicht werden. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden. Sie finden Sie https://security.microsoft.com/securescore im [Microsoft 365 Security Center](overview-security-center.md).

Wenn Sie den Empfehlungen der Sicherheitsbewertung folgen, können Sie Ihre Organisation vor Bedrohungen schützen. Über ein zentrales Dashboard im Microsoft 365 Security Center können Organisationen die Sicherheit ihrer Microsoft 365-Identitäten, Daten, Apps, Geräte und Infrastruktur überwachen und daran arbeiten.

Secure Score hilft Organisationen auf diese Arten:  

* Berichtet über den aktuellen Sicherheitsstatus der Organisation.
* Verbessert den Sicherheitsstatus durch Auffindbarkeit, Transparenz, Anleitung und Kontrolle.  
* Ermöglicht Vergleiche mit Benchmarks und erstellt KPIs (Key Performance Indicators).

Organisationen erhalten Zugriff auf zuverlässige Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, einen Vergleich mit ähnlichen Organisationen und vieles mehr. Die Bewertung zeigt auch, wenn Lösungen von Drittanbietern empfohlene Maßnahmen behandelt haben.

Darüber hinaus können Sie über die [Microsoft Graph-API](https://www.microsoft.com/security/partnerships/graph-security-api)auf Ihre Empfehlungen und Bewertungen zugreifen. Erfahren Sie mehr über den [Ressourcentyp Secure Score](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Funktionsweise

Sie erhalten Punkte zum Konfigurieren empfohlener Sicherheitsfeatures, zum Ausführen sicherheitsbezogener Aufgaben oder zur Adressierung der Verbesserungs Aktion mit einer Drittanbieteranwendung oder-Software oder einer alternativen Schadensminimierung. Einige Verbesserungsmaßnahmen geben nur Punkte, wenn sie vollständig abgeschlossen sind, und einige geben schon Punkte, auch wenn sie nur für einige Geräte oder Benutzer abgeschlossen sind. Wenn Sie eine der Verbesserungs Aktionen nicht oder nicht durchführen möchten, können Sie das Risiko oder das verbleibende Risiko akzeptieren.

Wir zeigen Ihnen die vollständige Palette möglicher Verbesserungen – unabhängig von der Lizenz –, damit Sie bewährte Methoden für die Sicherheit verstehen und Ihre Punktzahl verbessern können. Secure Score stellt Ihren absoluten Sicherheitsstatus dar, der unverändert bleibt, unabhängig von den Lizenzen Ihrer Organisation. Bitte bedenken Sie: Sicherheit sollte mit Benutzerfreundlichkeit in Einklang gebracht werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung.

Ihre Bewertung wird in Echtzeit aktualisiert, um die Informationen auf den Seiten Visualisierung und Verbesserungsmaßnahmen darzustellen. Secure Score wird auch täglich synchronisiert, um Systemdaten zu Ihren erreichten Punkten für jede Aktion zu erhalten.

### <a name="how-improvement-actions-are-scored"></a>Wie Verbesserungsmaßnahmen bewertet werden

Jede Verbesserungs Aktion ist auf 10 Punkte oder niedriger Wert. Die meisten werden auf binäre Art bewertet – wenn Sie die Verbesserungsmaßnahme umsetzen, wie z. B. eine neue Richtlinie erstellen oder eine bestimmte Einstellung aktivieren –, erhalten Sie die volle Punktzahl. Bei anderen Verbesserungsmaßnahmen werden Punkte als Prozentsatz der Gesamtkonfiguration gegeben. Wenn Sie beispielsweise für die Verbesserungsmaßnahme 30 Punkte erhalten, wenn Sie alle Ihre Benutzer mit einer mehrstufigen Authentifizierung schützen, aber nur 5 von insgesamt 100 Benutzern geschützt sind, dann erhalten Sie eine Teilpunktzahl von ca. 2 Punkten (5 geschützt/100 insgesamt * 30 Maximalpunktzahl = 2 Punkte Teilpunktzahl).

### <a name="products-included-in-secure-score"></a>Produkte in Secure Score

Derzeit gibt es Empfehlungen für Microsoft 365 (einschließlich Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP und Cloud-App-Sicherheit. Empfehlungen für andere Sicherheitsprodukte finden Sie in Kürze. Die Empfehlungen umfassen nicht alle Angriffsflächen, die jedem Produkt zugeordnet sind, sind aber ein guter Ausgangsbasis. Sie können auch die Verbesserungs Aktionen als von einem Drittanbieter oder einer alternativen Schadensminderung abgedeckt kennzeichnen.

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Um die Zugriffsberechtigung auf die Microsoft-Sicherheitsbewertung zu erhalten, müssen Sie eine der folgenden Rollen in Azure Active Directory besitzen.

### <a name="read-and-write-roles"></a>Rollen "Lesen und Schreiben"

Mit Lese- und Schreibzugriff können Sie Änderungen vornehmen und mit Secure Score direkt interagieren. Sie können anderen Benutzern auch schreibgeschützten Zugriff zuweisen.

* Globaler Administrator
* Sicherheitsadministrator
* Exchange-Administrator
* SharePoint-Administrator
* Konto Administrator

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

* Bereich securityevents. Read. all (für schreibgeschützte Rollen)
* Bereich securityevents. ReadWrite. all (für Lese-und Schreibrollen)

## <a name="gain-visibility-into-your-security-posture"></a>Erhalten Sie Einblicke in Ihren Sicherheitsstatus

Damit Sie die benötigten Informationen schneller finden können, sind die Microsoft Verbesserungsmaßnahmen in Gruppen aufgeteilt:

* Identität (Azure AD-Konten & -Rollen)
* Daten (Microsoft Information Protection)
* Gerät (Microsoft Defender ATP)
* App (E-Mail-und Cloud-Apps, einschließlich Office 365 und Microsoft Cloud App Security)
* Infrastruktur (bisher keine Verbesserungsmaßnahmen)

>[!NOTE]
>In der letzten Version von Microsoft Secure Score wurde ein verbessertes Bewertungsmodell veröffentlicht, das Microsoft Secure Score vorübergehend inkompatibel mit Identity Secure Score und der Graph-API machte. [Details anzeigen](microsoft-secure-score-preview.md#incompatibility-with-identity-secure-score-and-graph-api)

Auf der Übersicht der Microsoft-Sicherheitsbewertung können Sie sehen, wie die Punkte zwischen diesen Gruppen aufgeteilt werden und welche Punkte verfügbar sind. Auf der Übersichtsseite können Sie auch einen Überblick über die Gesamtpunktzahl, den historischen Trend Ihres Secure Score mit Benchmark-Vergleichen sowie priorisierte Verbesserungsmaßnahmen zur Verbesserung ihrer Punktzahl erhalten.

![Secure Score-Startseite](../../media/secure-score/secure-score-homepage.png)
*Abbildung 1: Übersichtsseite Microsoft-Sicherheitsbewertung*

## <a name="take-action-to-improve-your-score"></a>Ergreifen Sie Maßnahmen, um Ihre Punktzahl zu verbessern

Auf der Registerkarte **Verbesserungs Aktionen** werden die Sicherheitsempfehlungen für mögliche Angriffsflächen sowie deren Status (Adresse, geplant, Risiko akzeptiert, durch Drittanbieter aufgelöst, durch alternative Schadensbegrenzende Maßnahmen behoben und abgeschlossen) aufgeführt. Sie können alle Verbesserungsmaßnahmen durchsuchen, filtern und gruppieren.  

### <a name="ranking"></a>Rangfolge

Die Bewertung basiert auf der Anzahl der noch zu erreichenden Punkte, der Implementierungsschwierigkeit, der Auswirkungen auf die Benutzer und der Komplexität. Die am höchsten bewerteten Verbesserungen bieten viele Punkte mit geringem Schwierigkeitsgrad, Auswirkungen auf Benutzer, sowie Komplexität.

### <a name="view-improvement-action-details"></a>Details zur Verbesserungs Aktion anzeigen

Wenn Sie eine bestimmte Verbesserungs Aktion auswählen, wird ein ganzseitiges Flyout angezeigt.  

![Verbesserungs Aktion-Flyout-Beispiel ](../../media/secure-score/secure-score-improvement-action-details.png)
 *Abbildung 2: Beispiel für ein Verbesserungs Aktion-Flyout*

Zum Ausführen der Maßnahme stehen Ihnen verschiedene Optionen zur Verfügung:

* Wählen Sie **Verwalten** aus, um den Konfigurationsbildschirm zu wechseln und die Änderung vorzunehmen. Sie erhalten dann die Punkte, die die Aktion Wert ist, sichtbar in der ausfliegen. Die Aktualisierung der Punkte dauert im Allgemeinen ungefähr 24 Stunden.

* Wählen Sie **Freigeben** aus, um den direkten Link zur Verbesserungs Aktion zu kopieren, oder wählen Sie die Plattform aus, um den Link wie e-Mail, Microsoft Teams, Microsoft Planner oder ServiceNow freizugeben. Wenn Sie ServiceNow auswählen, können Sie ein Änderungs Ticket erstellen, das in ServiceNow und im Microsoft 365 Security Center Home angezeigt wird. Weitere Informationen finden Sie unter [Microsoft 365 Security Center und ServiceNow-Integration](tickets.md).

### <a name="choose-an-improvement-action-status"></a>Auswählen eines Verbesserungs Aktionsstatus

Auswählen von Status und Aufzeichnen von Notizen, die für die Verbesserungs Aktion spezifisch sind. Die folgenden Statuen können ausgewählt werden:

* **To Address** – Sie erkennen, dass die Verbesserungs Aktion erforderlich ist, und planen, diese zu einem späteren Zeitpunkt zu beheben. Dieser Status gilt auch für Aktionen, die als partiell erkannt, jedoch nicht vollständig abgeschlossen werden.
* **Geplant** – es sind konkrete Pläne vorhanden, um die Verbesserungs Aktion abzuschließen.
* **Risiko akzeptiert** : Sicherheit sollte immer mit Benutzerfreundlichkeit abgeglichen werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung. Wenn dies der Fall ist, können Sie das Risiko oder das verbleibende Risiko akzeptieren und die Verbesserungs Aktion nicht verabschieden. Sie erhalten keine Punkte, aber die Aktion wird in der Liste der Verbesserungs Aktionen nicht mehr angezeigt. Sie können diese Aktion jederzeit im Verlauf anzeigen oder rückgängig machen.
* **Durch Drittanbieter aufgelöst** und **durch alternative Schadensbegrenzende Maßnahmen aufgelöst** – die Verbesserungs Aktion wurde bereits von einer Drittanbieteranwendung oder-Software oder einem internen Tool behandelt. Sie erhalten die Punkte, die die Aktion Wert ist, sodass Ihre Punktzahl besser Ihre gesamte Sicherheitsposition widerspiegelt. Wenn ein Drittanbieter oder ein internes Tool das Steuerelement nicht mehr abdeckt, können Sie einen anderen Status auswählen. Bitte beachten Sie, dass Microsoft keine Sichtbarkeit in die Vollständigkeit der Implementierung hat, wenn die Verbesserungs Aktion als einer dieser Status markiert ist.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Bedrohungs & Verbesserungs Aktionen bei der Sicherheitsrisikoverwaltung

Für Verbesserungs Aktionen in der Kategorie "Gerät" können Sie Status nicht auswählen. Stattdessen werden Sie zur entsprechenden [Threat & Vulnerability Management (TVM)-Sicherheitsempfehlung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) im [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) geleitet, um Maßnahmen zu ergreifen. Die von Ihnen ausgewählte Ausnahme und die Begründung, die Sie schreiben, werden speziell für dieses Portal verwendet und sind im Microsoft Secure Score-Portal nicht vorhanden.

#### <a name="completed-improvement-actions"></a>Abgeschlossene Verbesserungs Aktionen

Verbesserungs Aktionen haben den Status "abgeschlossen", nachdem alle möglichen Punkte für die Verbesserungs Aktion erreicht wurden. Abgeschlossene Verbesserungs Aktionen werden zwar von Microsoft-Daten bestätigt, und Sie können den Status nicht ändern.

### <a name="assess-information-and-review-user-impact"></a>Bewerten von Informationen und Überprüfen der Auswirkungen auf die Benutzer

Im Abschnitt " **im Überblick** " erfahren Sie mehr über die Kategorie, über Angriffe, die geschützt werden können, und das Produkt.

Die **Auswirkungen des Benutzers** zeigen, was die Benutzer erleben, wenn die Verbesserungs Aktion durchgesetzt wird und von **betroffenen Benutzern** gezeigt wird, wer Sie erleben wird.

### <a name="implement-the-improvement-action"></a>Implementieren der Verbesserungs Aktion

Im Abschnitt **Implementierung** werden alle Voraussetzungen aufgeführt, Schritt für Schritt werden die nächsten Schritte zum Abschließen der Verbesserungs Aktion, der aktuelle Implementierungsstatus der Verbesserungs Aktion sowie alle weiteren Links zu weiteren Informationen angezeigt.

Voraussetzungen sind alle Lizenzen, die abgerufen werden müssen, oder Aktionen, die ausgeführt werden müssen, bevor die Verbesserungs Aktion behandelt wird. Stellen Sie sicher, dass Sie über genügend Sitze in Ihrer Lizenz verfügen, um die Verbesserungs Aktion abzuschließen, und dass diese Lizenzen auf die erforderlichen Benutzer angewendet werden.  

## <a name="track-your-score-history-and-meet-goals"></a>Verfolgen des Ergebnis Verlaufs und erreichen der Ziele

Auf der Registerkarte **Verlauf** können Sie einen Graph der Bewertung Ihrer Organisation anzeigen. Unterhalb des Diagramms finden Sie eine Liste aller Maßnahmen, die im ausgewählten Zeitraum ausgeführt wurden, und deren Attributen, wie etwa die Kategorie und die resultierenden Punkte. Sie können einen Datumsbereich anpassen und nach Kategorie filtern.

Auf der Registerkarte **Metriken & Trends** gibt es mehrere Diagramme und Diagramme, die Ihnen mehr Einblick in Trends geben und Ziele festlegen. Sie können den Datumsbereich für die gesamte Visualisierungs Seite festlegen. Die Visualisierungen umfassen Folgendes:

* **Ihre Secure Score Zone** – angepasst basierend auf den Zielen und Definitionen Ihrer Organisation für gute, ordnungsgemäße und ungültige Bewertungsbereiche.
* **Regressions Trend** – eine Zeitskala mit Punkten, die aufgrund von Konfigurations-, Benutzer-oder Geräteänderungen zurückgegangen sind.  
* **Vergleichs Trend** : wie das sichere Ergebnis Ihrer Organisation im Laufe der Zeit mit anderen verglichen wird. Diese Ansicht kann Zeilen enthalten, die den Notendurchschnitt von Organisationen mit ähnlicher Anzahl von sitzen und eine benutzerdefinierte Vergleichsansicht darstellen, die Sie festlegen können.
* **Trend zur Risikoakzeptanz** – Zeitskala der Verbesserungs Aktionen, die als "Risiko akzeptiert" gekennzeichnet sind.
* **Ergebnisänderungen** : Anzahl der erreichten Punkte, zurückgegebene Punkte sowie die nachfolgende Ergebnis Änderung im angegebenen Datumsbereich.

## <a name="risk-awareness"></a>Risikobewusstsein

Microsoft Secure Score ist eine numerische Zusammenfassung Ihrer Sicherheitsposition basierend auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsbezogenen Messungen. Es ist keine absolute Maßeinheit dafür, wie wahrscheinlich ein System oder Daten verletzt werden. Vielmehr stellt Sie das Ausmaß dar, in dem Sie Sicherheitskontrollen in Ihrer Microsoft-Umgebung eingeführt haben, die das Risiko einer Sicherheitsverletzung ausgleichen können. Kein Onlinedienst ist vollkommen immun gegen Sicherheitsverstöße, und Secure Score sollte in keiner Weise als Garantie gegen Sicherheitsverstöße interpretiert werden.

## <a name="whats-new"></a>Was sind die Neuerungen? 

Um Microsoft Secure Score zu einem besseren Vertreter ihrer Sicherheitsposition zu machen, haben wir einige Änderungen vorgenommen. Informationen zu geplanten Änderungen finden Sie unter [What es Coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Inkompatibilität mit Identity Secure Score und Graph-API

In der letzten Version von Microsoft Secure Score wurde ein verbessertes Bewertungsmodell veröffentlicht. Diese Änderungen ermöglichen eine flexiblere und präzisere Darstellung Ihrer Sicherheitsposition. Diese Updates haben jedoch zur vorübergehenden Inkompatibilität von Microsoft Secure Score mit Identity Secure Score und der Graph-API geführt.

In der Zeit wird das neue Bewertungsmodell von Identity Secure Score und der Graph-API übernommen. Bis dahin werden Kunden Unterschiede in den von Microsoft Secure Score, Identity Secure Score und der Graph-API gemeldeten Bewertungen sehen. Wir entschuldigen uns für eventuelle Unannehmlichkeiten und arbeiten daran, dass diese Erfahrungen in Zukunft besser kompatibel sind.

### <a name="april-2020"></a>April 2020

#### <a name="added-azure-active-directory-improvement-action"></a>Azure Active Directory Improvement-Aktion hinzugefügt

- Nicht zulassen, dass Benutzer nicht verwalteten Anwendungen zustimmen (zurzeit in der veröffentlichten Version verfügbar)

#### <a name="added-azure-advanced-threat-protection-improvement-actions"></a>Verbesserungs Aktionen für erweiterte Azure Advanced Threat Protection hinzugefügt

- Druckerspoolerdienst auf Domänencontrollern deaktivieren
- Unsichere Kerberos-Delegierungen ändern, um einen Identitätswechsel zu verhindern
- Lokale Administratorkennwörter mit Microsoft LAPS schützen und verwalten
- Risiko des lateralen Bewegungspfads auf sensible Entitäten reduzieren
- Ruhende Konten aus sensiblen Gruppen entfernen
- Unsichere SID-Verlaufsattribute aus Entitäten entfernen
- Unsichere Kontoattribute auflösen
- Offenlegung von Anmeldeinformationen in Klartext verhindern
- Kommunikation über Legacy-Protokolle verhindern
- Verwendung schwacher Verschlüsselung verhindern

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a>Unterstützung der Sicherheitsempfehlungen von Microsoft Defender ATP Threat & Vulnerability Management (TVM)

Alle veröffentlichten Sicherheitsempfehlungen, die von TVM bereitgestellt werden, sind jetzt verfügbar.

### <a name="january---march-2020"></a>Januar-März 2020

#### <a name="updated-interface-and-functionality"></a>Aktualisierte Benutzeroberfläche und Funktionalität

* Völlig neue Metriken und Trend-Ansichten für CISO und Lead Level-Diskussionen
* Neue Möglichkeiten zum Nachverfolgen und Benchmarken Ihrer Bewertung
* Bessere Nachverfolgung und Verständnis für Ergebnis Regressionen
* Filtern, Taggen, Suchen und Gruppieren von Verbesserungsmaßnahmen
* Verwalten Sie Ihre zukünftigen Ziele mithilfe von Score-Projektionen und geplanten Maßnahmen
* Und mehr!

#### <a name="removed-not-scored-and-review-improvement-actions"></a>Verbesserungs Aktionen "nicht bewertet" und "überprüfen" entfernt

Einer der Grundsätze von Secure Score ist, dass die Bewertung standardisiert und einfach nachvollziehbar sein sollte. Verbesserungsmaßnahmen, die nicht messbar sind oder nicht durchgeführt werden können, führen zu Verwirrung. Eine Microsoft-Sicherheitsbewertung ist nur sinnvoll, wenn jede Empfehlung einen eindeutigen Effekt auf die Bewertung haben kann. Nicht bewertete Verbesserungs Aktionen sind nicht messbar, und Überprüfungs Verbesserungs Aktionen werden nicht auf den gleichen Standard wie andere Verbesserungs Aktionen gemessen.

Aus diesen Gründen wurden alle Verbesserungs Aktionen vorübergehend entfernt, die nicht bewertet oder eine Überarbeitungs Kadenz erforderlich waren. Es ist keine Aktion Ihrerseits erforderlich.

#### <a name="simplification-of-the-point-system"></a>Vereinfachung des Punktesystems

Um Punkte über mehrere Erfahrungen hinweg zu standardisieren, wurden alle Aktionspunkte für eine sichere Ergebnisverbesserung auf 10 oder mehr Punkte aktualisiert. Es ist erforderlich, dass die gesamte Breite Verschnaufpause von Sicherheitskontrollen konsistenter ist, die wir heute haben, und diejenigen, die wir in Zukunft hinzufügen werden. Dies ist zwar eine wesentliche Änderung, und es wird eine Verringerung der Gesamtzahl der Punkte angezeigt, aber ihre Sicherheitsposition wird nicht geändert.

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, informieren Sie uns mit einem Beitrag in der Community für [Sicherheit, Datenschutz und Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy). Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.
