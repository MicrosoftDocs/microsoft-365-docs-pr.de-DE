---
title: Microsoft Secure Score
description: Beschreibt Microsoft-Sicherheitsbewertung im Microsoft 365 Security Center, erläutert die Berechnung von Details und was Sicherheitsadministratoren erwarten dürfen.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitsbewertung, Security Center, Verbesserungsmaßnahmen
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: ea91fc29a0fa768113ff3ca8d8129a0ee56ab5f5
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633993"
---
# <a name="microsoft-secure-score"></a>Microsoft-Sicherheitsbewertung

Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden. Wenn Sie den Empfehlungen der Sicherheitsbewertung folgen, können Sie Ihre Organisation vor Bedrohungen schützen. Über ein zentrales Dashboard im Microsoft 365 Security Center können Organisationen die Sicherheit ihrer Microsoft 365-Identitäten, Daten, Apps, Geräte und Infrastruktur überwachen und daran arbeiten.

Secure Score hilft Organisationen auf diese Arten:

* Berichtet über den aktuellen Sicherheitsstatus der Organisation.
* Verbessert den Sicherheitsstatus durch Auffindbarkeit, Transparenz, Anleitung und Kontrolle.  
* Ermöglicht Vergleiche mit Benchmarks und erstellt KPIs (Key Performance Indicators).

Organisationen erhalten Zugriff auf zuverlässige Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, einen Vergleich mit ähnlichen Organisationen und vieles mehr. Die Bewertung zeigt auch, wenn Lösungen von Drittanbietern empfohlene Maßnahmen behandelt haben.

Darüber hinaus können Sie über die [Microsoft Graph-API](https://www.microsoft.com/security/partnerships/graph-security-api)auf Ihre Empfehlungen und Bewertungen zugreifen. Erfahren Sie mehr über den [Ressourcentyp Secure Score](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Funktionsweise

Sie erhalten Punkte für die Konfiguration empfohlener Sicherheitsfunktionen, die Ausführung sicherheitsrelevanter Aufgaben (z. B. das Anzeigen von Berichten) oder die Behandlung von Verbesserungsmaßnahmen mit einer Drittanbieteranwendung oder -software. Einige Verbesserungsmaßnahmen geben nur Punkte, wenn sie vollständig abgeschlossen sind, und einige geben schon Punkte, auch wenn sie nur für einige Geräte oder Benutzer abgeschlossen sind.

Wir zeigen Ihnen die vollständige Palette möglicher Verbesserungen – unabhängig von der Lizenz –, damit Sie bewährte Methoden für die Sicherheit verstehen und Ihre Punktzahl verbessern können. Secure Score stellt Ihren absoluten Sicherheitsstatus dar, der unverändert bleibt, unabhängig von den Lizenzen Ihrer Organisation. Bitte bedenken Sie: Sicherheit sollte mit Benutzerfreundlichkeit in Einklang gebracht werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung.

Ihre Bewertung wird in Echtzeit aktualisiert, um die Informationen auf den Seiten Visualisierung und Verbesserungsmaßnahmen darzustellen. Secure Score wird auch täglich synchronisiert, um Systemdaten zu Ihren erreichten Punkten für jede Aktion zu erhalten.

### <a name="how-improvement-actions-are-scored"></a>Wie Verbesserungsmaßnahmen bewertet werden

Die meisten werden auf binäre Art bewertet – wenn Sie die Verbesserungsmaßnahme umsetzen, wie z. B. eine neue Richtlinie erstellen oder eine bestimmte Einstellung aktivieren –, erhalten Sie die volle Punktzahl. Bei anderen Verbesserungsmaßnahmen werden Punkte als Prozentsatz der Gesamtkonfiguration gegeben. Wenn Sie beispielsweise für die Verbesserungsmaßnahme 30 Punkte erhalten, wenn Sie alle Ihre Benutzer mit einer mehrstufigen Authentifizierung schützen, aber nur 5 von insgesamt 100 Benutzern geschützt sind, dann erhalten Sie eine Teilpunktzahl von ca. 2 Punkten (5 geschützt/100 insgesamt * 30 Maximalpunktzahl = 2 Punkte Teilpunktzahl).

### <a name="products-included-in-secure-score"></a>Produkte in Secure Score

Derzeit gibt es Empfehlungen für Office 365 (einschließlich SharePoint Online, Exchange Online, OneDrive for Business, Microsoft Information Protection und mehr), Azure AD und Cloud App Security. Empfehlungen zu anderen Sicherheitsprodukten wie Azure ATP und Microsoft Defender ATP werden demnächst verfügbar sein. Die Empfehlungen umfassen nicht alle Angriffsflächen, die jedem Produkt zugeordnet sind, sind aber ein guter Ausgangsbasis. Sie können die Verbesserungsmaßnahmen auch als „abgedeckt durch Dritte“ markieren.

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Um die Zugriffsberechtigung auf die Microsoft-Sicherheitsbewertung zu erhalten, müssen Sie eine der folgenden Rollen in Azure Active Directory besitzen.

### <a name="read-and-write-roles"></a>Rollen "Lesen und Schreiben"

Mit Lese- und Schreibzugriff können Sie Änderungen vornehmen und mit Secure Score direkt interagieren. Sie können anderen Benutzern auch schreibgeschützten Zugriff zuweisen.

* Globaler Administrator
* Sicherheitsadministrator
* Exchange-Administrator
* SharePoint-Administrator

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

* SecurityEvents.Read.All (für die schreibgeschützte Rolle)
* SecurityEvents.ReadWrite.All (für die Rolle "Lesen und Schreiben")

## <a name="gain-visibility-into-your-security-posture"></a>Erhalten Sie Einblicke in Ihren Sicherheitsstatus

Damit Sie die benötigten Informationen schneller finden können, sind die Microsoft Verbesserungsmaßnahmen in Gruppen aufgeteilt:

* Identität (Azure AD-Konten & -Rollen)
* Daten (Microsoft Information Protection)
* Geräte (bisher keine Verbesserungsmaßnahmen)
* App (E-Mail-und Cloud-Apps, einschließlich Office 365 und Microsoft Cloud App Security)
* Infrastruktur (bisher keine Verbesserungsmaßnahmen)

Auf der Übersicht der Microsoft-Sicherheitsbewertung können Sie sehen, wie die Punkte zwischen diesen Gruppen aufgeteilt werden und welche Punkte verfügbar sind. Auf der Übersichtsseite können Sie auch einen Überblick über die Gesamtpunktzahl, den historischen Trend Ihres Secure Score mit Benchmark-Vergleichen sowie priorisierte Verbesserungsmaßnahmen zur Verbesserung ihrer Punktzahl erhalten.

![Secure Score-Startseite](../../media/secure-score/homepage-original.png)
*Abbildung 1: Übersichtsseite Microsoft-Sicherheitsbewertung*

## <a name="take-action-to-improve-your-score"></a>Ergreifen Sie Maßnahmen, um Ihre Punktzahl zu verbessern

Auf der Registerkarte "Verbesserungsmaßnahmen" werden die Sicherheitsempfehlungen, die mögliche Angriffsflächen behandeln, zusammen mit deren Status ("erledigt", "nicht abgeschlossen", "über Drittanbieter behoben" und "ignoriert") aufgelistet. Sie können alle Verbesserungsmaßnahmen durchsuchen, filtern und gruppieren.

### <a name="ranking"></a>Rangfolge

Die Bewertung basiert auf der Anzahl der noch zu erreichenden Punkte, der Implementierungsschwierigkeit, der Auswirkungen auf die Benutzer und der Komplexität. Die am höchsten bewerteten Verbesserungen bieten viele Punkte mit geringem Schwierigkeitsgrad, Auswirkungen auf Benutzer, sowie Komplexität.

### <a name="actions"></a>Maßnahmen

Maßnahmen, die mit [Nicht bewertet] gekennzeichnet sind, werden nicht von der Microsoft-Sicherheitsbewertung nachverfolgt. Sie können zwar diese Maßnahmen ergreifen, aber deren Vervollständigung wirkt sich nicht auf die Bewertung aus. Wenn eine Aktion zukünftig von der Microsoft-Sicherheitsbewertung  nachverfolgt wird und Sie sie bereits abgeschlossen haben, wird Ihr Secure Score automatisch angepasst.

Wenn Sie eine bestimmte Verbesserungsmaßnahme auswählen, wird ein Fly-out angezeigt. Zum Ausführen der Maßnahme stehen Ihnen verschiedene Optionen zur Verfügung:

1. Wählen Sie **Einstellungen anzeigen** aus, um in den Konfigurationsbildschirm zu wechseln und die Änderung vorzunehmen. Dann erhalten Sie die Punkte, die die Maßnahme wert ist und wie sie am oberen Rand des Fly-outs angezeigt werden. Es kann bis zu 24 Stunden dauern, bis Punkte aktualisiert werden.

2. Wählen Sie **Über Drittanbieter beheben** aus, weil die Verbesserungsmaßnahme bereits von einer Drittanbieteranwendung oder -Software vorgenommen wurde. Sie erhalten die Punkte, die die Maßnahme wert ist, damit Ihr Secure Score Ihren Sicherheitsstatus im Ganzen besser widerspiegelt. Wenn ein Drittanbieter das diese Maßnahme nicht mehr abdeckt, können Sie die Verbesserungsmaßnahme als "nicht erledigt" markieren. Bedenken Sie, dass Microsoft nicht einsehen kann, ob die Bewertungsanforderungen erfüllt wurden, wenn die Verbesserungsmaßnahme als "Über Drittanbieter behoben“ gekennzeichnet ist.

3. Wählen Sie **Ignorieren** aus, weil Sie sich entschieden haben, das Risiko zu übernehmen und die Verbesserungsmaßnahme nicht auszuführen. Wenn Sie eine Verbesserungsmaßnahme ignorieren, wird die Gesamtanzahl der Punkte, die Sie erzielen können, reduziert. Sie können diese Aktion jederzeit im Verlauf anzeigen oder rückgängig machen.

4. Wählen Sie **Überprüfen** aus, weil die Verbesserungsmaßnahme es erforderlich macht, einen Bereich Ihrer Umgebung regelmäßig zu überprüfen, um Punkte zu bekommen und zu behalten. Beispielsweise sollten Weiterleitungsregeln für Postfächer wöchentlich überprüft werden, um sicherzustellen, dass die Daten aus Ihrem Netzwerk extrahiert werden. Sie müssen keine Änderungen vornehmen, aber eine Aktion muss ausgeführt werden. Wenn Sie die Regeln regelmäßig überprüfen, erhalten Sie die Punkte. Wenn nicht, verschlechtert sich die Bewertung.

![Beispiel für Verbesserungsmaßnahmen Secure Score](../../media/secure-score/secure-score1x450.png) ![Beispiel für Verbesserungsmaßnahmen Secure Score – Überprüfung](../../media/secure-score/secure-score2x450.png)

*Abbildungen 2 & 3: Verbesserungsmaßnahmen Fly-outs*

## <a name="monitor-improvements-over-time"></a>Überwachen von Verbesserungen im Laufe der Zeit

Auf der Registerkarte **Verlauf** können Sie einen Graph der Bewertung Ihrer Organisation anzeigen. Unterhalb des Diagramms finden Sie eine Liste aller Maßnahmen, die im ausgewählten Zeitraum ausgeführt wurden, und deren Attributen, wie etwa die Kategorie und die resultierenden Punkte. Sie können einen Datumsbereich anpassen und nach Kategorie filtern.

## <a name="risk-awareness"></a>Risikobewusstsein

Die Microsoft-Sicherheitsbewertung ist eine numerische Zusammenfassung Ihres Sicherheitsstatus, die auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsrelevanten Maßstäben basiert. Hierbei handelt es sich nicht um eine absolute Messung, wie wahrscheinlich eine Sicherheitsverletzung Ihres System oder Ihrer Daten ist. Vielmehr stellt Sie das Ausmaß dar, in dem Sie Sicherheitskontrollen in Ihrer Microsoft-Umgebung eingeführt haben, die das Risiko einer Sicherheitsverletzung ausgleichen können. Kein Onlinedienst ist vollkommen immun gegen Sicherheitsverstöße, und Secure Score sollte in keiner Weise als Garantie gegen Sicherheitsverstöße interpretiert werden.

## <a name="whats-new"></a>Was sind die Neuerungen?

Damit die Microsoft-Sicherheitsbewertung zu einem besseren Ansprechpartner für Ihren Sicherheitsstatus wird, haben wir einige Änderungen vorgenommen.

Wenn Sie mehr über geplante Änderungen wissen möchten, lesen Sie [Bald in der Microsoft-Sicherheitsbewertung verfügbar](microsoft-secure-score-whats-coming.md)

### <a name="removed-not-scored-improvement-actions"></a>"Nicht bewertet"-Verbesserungsmaßnahmen entfernt

Einer der Grundsätze von Secure Score ist, dass die Bewertung standardisiert und einfach nachvollziehbar sein sollte. Verbesserungsmaßnahmen, die nicht messbar sind oder nicht durchgeführt werden können, führen zu Verwirrung. Die Microsoft-Sicherheitsbewertung ist nur sinnvoll, wenn jede Empfehlung einen eindeutigen Effekt auf die Bewertung haben kann. Nicht bewertete Verbesserungsmaßnahmen sind nicht messbar.  

Aus diesen Gründen wurden alle nicht bewerteten Verbesserungsmaßnahmen entfernt. Es ist keine Aktion Ihrerseits erforderlich.

### <a name="removed-device-improvement-actions"></a>Verbesserungsmaßnahmen für Geräte entfernte

Nach einer Auswertung der Kategorie Microsoft-Sicherheitsbewertung  – "Verbessungsmaßnahmen für Geräte" wurde beschlossen, dass diese Maßnahmen zurzeit den Richtlinienstatus und nicht den Konfigurationsstatus von Geräten bewerten. Da die Konfiguration direkt an den Sicherheitsstatus gebunden ist, wurde bei den vorhandenen Gerätemaßnahmen festgestellt, dass sie den Organisationsstatus nicht vollständig wiedergeben.  Wir werden die aktuellen Maßnahmen in der Kategorie "Gerät" entfernen, während wir an einer Reihe von Empfehlungen arbeiten, die die diagnostischen Daten direkt verwenden, um den Sicherheitsstatus der Geräte in vollem Umfang darzustellen.

Die folgenden Verbesserungsmaßnahmen wurden entfernt:

- Microsoft Intune Mobile Device Management (Verwaltung mobiler Geräte mit Intune) aktivieren
- Erstellen einer Microsoft Intune Compliance-Richtlinie für Android
- Erstellen einer Microsoft Intune Compliance-Richtlinie für Android for Work
- Erstellen einer Microsoft Intune App-Schutzrichtlinie für Android
- Erstellen einer Microsoft Intune App-Schutzrichtlinie für iOS
- Markieren von Geräten ohne Microsoft Intune Compliance-Richtlinie als "nicht kompatibel"
- Erstellen einer Microsoft Intune Compliance-Richtlinie für iOS
- Erstellen einer Microsoft Intune Compliance-Richtlinie für macOS
- Erstellen einer Microsoft Intune Compliance-Richtlinie für Windows
- Erstellen eines Microsoft Intune-Konfigurationsprofils für Android
- Erstellen eines Microsoft Intune-Konfigurationsprofils für Android for Work
- Erstellen eines Microsoft Intune-Konfigurationsprofils für macOS
- Erstellen eines Microsoft Intune-Konfigurationsprofils für iOS
- Erstellen eines Microsoft Intune-Konfigurationsprofils für Windows
- Erweiterte Jailbreak-Erkennung in Microsoft Intune aktivieren
- Erfordern, dass alle Geräte gepatcht sind und dass Antivirensoftware und Firewalls aktiviert sind
- Aktivieren der Windows Defender ATP-Integration in Microsoft Intune
- Erstellen einer Microsoft Intune Windows Information Protection-Richtlinie
- Erfordern, dass alle Geräte Erweiterte Sicherheitskonfigurationen haben
- Wöchentliches Überprüfung von blockierten Geräten

### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a>Verbesserungsmaßnahmen, die die Erwartungen für zuverlässige Messungen nicht erfüllen, wurden entfernt

Um sicherzustellen, dass die Microsoft-Sicherheitsbewertung aussagekräftig ist und jede Verbesserungsmaßnahme messbar und zuverlässig ist, entfernen wir die folgenden Verbesserungsmaßnahmen:

- Aktivieren der Aufzeichnung von Überwachungsdaten
- Entdeckung riskanter und nicht konformer Shadow IT-Anwendungen
- Überprüfen von Berechtigungen und Blockieren riskanter OAuth-Anwendungen
- Einrichten der Versionsverwaltung in SharePoint Online-Dokumentbibliotheken

### <a name="mfa-improvement-action-updates"></a>Aktualisierungen von MFA-Verbesserungsmaßnahmen

Um den Bedürfnissen von Unternehmen zu entsprechen, Sicherheit zu gewährleisten und gleichzeitig Richtlinien anzuwenden, die mit den Geschäftsabläufen harmonieren, hat die Microsoft-Sicherheitsbewertung drei Verbesserungsmaßnahmen zur mehrstufigen Authentifizierung entfernt und zwei hinzugefügt.

Entfernte Verbesserungsmaßnahmen:

- Registrieren von allen Benutzern für die Multi-Faktor-Authentifizierung
- Anfordern der MFA für alle Benutzer
- MFA für privilegierte Azure AD-Rollen anfordern

Hinzugefügte Verbesserungsmaßnahmen:

- Sicherstellen, dass alle Benutzer die mehrstufige Authentifizierung für sicheren Zugriff durchführen können
- MFA für Administratorrollen erzwingen

 Bei diesen neuen Verbesserungsmaßnahmen müssen die Benutzer oder Administratoren für die Multi-Faktor-Authentifizierung (MFA) in Ihrem Verzeichnis registriert werden, um die korrekten Richtlinien für Ihre organisatorischen Anforderungen zu etablieren. Das Hauptziel ist, flexibel zu sein und gleichzeitig sicherzustellen, dass alle Ihre Benutzer und Administratoren mit mehreren Faktoren oder mit risikobasierten Aufforderungen zur Identitätsüberprüfung authentifiziert werden können. Dies kann in der Art und Weise erfolgen, dass mehrere Richtlinien angewendet werden, die bereichsbezogene Entscheidungen treffen, oder dass Sicherheitsstandardwerte (ab 16. März) festgelegt werden, anhand derer Microsoft entscheiden kann, wann Benutzer für MFA herausgefordert werden.

### <a name="removed-review-improvement-actions"></a>"Überprüfen"-Verbesserungsmaßnahmen entfernt

Einer der Grundsätze von Secure Score ist, dass die Bewertung standardisiert und einfach nachvollziehbar sein sollte. Verbesserungsmaßnahmen, die nicht messbar sind oder nicht durchgeführt werden können, führen zu Verwirrung. Eine Microsoft-Sicherheitsbewertung ist nur sinnvoll, wenn jede Empfehlung einen eindeutigen Effekt auf die Bewertung haben kann. An "Überprüfen"-Verbesserungsmaßnahmen wird nicht der gleiche Standard wie an andere Verbesserungsmaßnahmen gelegt.  

Aus diesen Gründen wurden alle Verbesserungsmaßnahmen, bei denen ein Überprüfungsrhythmus erforderlich war, vorübergehend entfernt. Es ist keine Aktion Ihrerseits erforderlich.

### <a name="preview-features"></a>Vorschaufeatures

In der [Vorschauversion](microsoft-secure-score-preview.md) werden die folgenden Features enthalten sein:

* Völlig neue Metriken und Trend-Ansichten für CISO und Lead Level-Diskussionen
* Neue Möglichkeiten zum Nachverfolgen und Benchmarken Ihrer Bewertung
* Bessere Nachverfolgung und Überwachung von Score-Regressionen
* Filtern, Taggen, Suchen und Gruppieren von Verbesserungsmaßnahmen
* Verwalten Sie Ihre zukünftigen Ziele mithilfe von Score-Projektionen und geplanten Maßnahmen
* Vereinfachung des Punktesystems
* Und mehr!

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, informieren Sie uns mit einem Beitrag in der Community für [Sicherheit, Datenschutz und Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy). Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.
