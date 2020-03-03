---
title: Microsoft-Sicherheitsbewertung
description: Beschreibt Microsoft Secure Score im Microsoft 365 Security Center, wie Details berechnet werden und welche Sicherheitsadministratoren erwarten können.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, sicheres Ergebnis, Sicherheitscenter, Verbesserungs Aktionen
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
ms.openlocfilehash: b19c48161d5d0f43c2beb207dd0ee2db8bfb1470
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372023"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

Microsoft Secure Score ist ein Maß für die Sicherheitslage einer Organisation mit einer höheren Zahl, die mehr Verbesserungs Aktionen anzeigt. Wenn Sie die Sicherheits Bewertungsempfehlungen befolgen, können Sie Ihre Organisation vor Bedrohungen schützen. Von einem zentralisierten Dashboard im Microsoft 365 Security Center aus können Organisationen die Sicherheit Ihrer Microsoft 365-Identitäten, Daten, apps, Geräte und Infrastruktur überwachen und daran arbeiten.

Secure Score hilft Organisationen:

* Bericht über den aktuellen Status der Sicherheitsposition der Organisation.
* Verbessern Sie Ihre Sicherheitsposition durch Bereitstellen von Auffindbarkeit, Sichtbarkeit, Anleitung und Steuerung.  
* Vergleichen Sie mit Benchmarks, und legen Sie Key Performance Indicators (KPIs) fest.

Organisationen erhalten Zugriff auf robuste Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, den Vergleich mit ähnlichen Organisationen und vieles mehr. Die Bewertung kann auch reflektieren, wenn von Drittanbieterlösungen Empfohlene Aktionen behandelt wurden.

Darüber hinaus können Sie über die [Microsoft Graph-API](https://www.microsoft.com/security/partnerships/graph-security-api)auf Ihre Empfehlungen und Gäste zugreifen. Erfahren Sie mehr über den [Ressourcentyp Secure Score](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Funktionsweise

Sie erhalten Punkte zum Konfigurieren empfohlener Sicherheitsfeatures, zum Ausführen sicherheitsbezogener Aufgaben (beispielsweise zum Anzeigen von Berichten) oder zur Adressierung der Verbesserungs Aktion mit einer Anwendung oder Software eines Drittanbieters. Einige Verbesserungs Aktionen geben nur dann Punkte, wenn Sie vollständig abgeschlossen sind, und einige geben partielle Punkte an, wenn Sie für einige Geräte oder Benutzer abgeschlossen werden.

Wir zeigen Ihnen den vollständigen Überblick über mögliche Verbesserungen, unabhängig von der Lizenz, sodass Sie bewährte Methoden für die Sicherheit verstehen und Ihre Punktzahl verbessern können. Ihre absolute Sicherheitsposition wird durch Secure Score dargestellt, was unabhängig von den Produktlizenzen, die Ihre Organisation besitzt, gleich bleibt. Beachten Sie, dass die Sicherheit mit der Benutzerfreundlichkeit ausgeglichen werden sollte, und nicht jede Empfehlung kann für Ihre Umgebung funktionieren.

Ihre Punktzahl wird in Echtzeit aktualisiert, um die Informationen widerzuspiegeln, die auf den Seiten Visualisierungen und Verbesserungs Aktionen angezeigt werden. Secure Score synchronisiert auch täglich, um Systemdaten zu ihren erreichten Punkten für jede Aktion zu erhalten.

### <a name="how-improvement-actions-are-scored"></a>So werden Verbesserungs Aktionen bewertet

Die meisten werden auf binäre Weise bewertet – Wenn Sie die Verbesserungs Aktion implementieren, wie Sie eine neue Richtlinie erstellen oder eine bestimmte Einstellung aktivieren, erhalten Sie 100% der Punkte. Bei anderen Verbesserungs Aktionen werden Punkte als Prozentsatz der Gesamtkonfiguration angegeben. Wenn die Verbesserungs Aktion beispielsweise besagt, dass Sie 30 Punkte erhalten, indem Sie alle Ihre Benutzer mit mehrstufiger Authentifizierung schützen und nur 5 von 100 gesamt Benutzern geschützt sind, erhalten Sie einen Teil der Punktzahl von etwa 2 Punkten (5 Protected/100 Total * 30 MAX pts = 2 PTS Partial Score).

### <a name="products-included-in-secure-score"></a>Produkte im Lieferumfang von Secure Score

Derzeit gibt es Empfehlungen für Office 365 (einschließlich SharePoint Online, Exchange Online, OneDrive für Unternehmen, Microsoft Information Protection und mehr), Azure AD und Cloud-App-Sicherheit. Empfehlungen für andere Sicherheitsprodukte wie Azure ATP und Microsoft Defender ATP werden in Kürze verfügbar sein. Die Empfehlungen decken nicht alle Angriffsflächen ab, die jedem Produkt zugeordnet sind, sind jedoch ein guter Ausgangswert. Sie können auch die Verbesserungs Aktionen als von einem Drittanbieter abgedeckt markieren.

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Um über die Berechtigung zum Zugriff auf Microsoft Secure Score verfügen zu können, muss in Azure Active Directory eine der folgenden Rollen zugewiesen sein.

### <a name="read-and-write-roles"></a>Lesen und Schreiben von Rollen

Mit Lese-und Schreibzugriff können Sie Änderungen vornehmen und direkt mit Secure Score interagieren. Sie können auch anderen Benutzern schreibgeschützten Zugriff zuweisen.

* Globaler Administrator
* Sicherheitsadministrator
* Exchange-Administrator
* SharePoint-Administrator

### <a name="read-only-roles"></a>Schreibgeschützte Rollen

Mit schreibgeschütztem Zugriff können Sie den Status oder die Notizen für eine Verbesserungs Aktion nicht bearbeiten, Bewertungs Zonen bearbeiten oder benutzerdefinierte Vergleiche bearbeiten.

* Helpdesk-Administrator
* Benutzeradministrator
* Service-Administrator
* Benutzer mit Leseberechtigung für Sicherheitsfunktionen
* Sicherheitsoperator
* Globaler Leser

### <a name="graph-api"></a>Graph-API

Für den Zugriff auf die Graph-API benötigen Sie zusätzlich zu einer Rolle einen der folgenden Bereiche:

* Bereich securityevents. Read. all (für schreibgeschützte Rolle)
* Bereich securityevents. ReadWrite. all (für Lese-und Schreibrolle)

## <a name="gain-visibility-into-your-security-posture"></a>Verschaffen Sie sich eine Sichtbarkeit in ihrer Sicherheitsposition

Um Ihnen die Informationen zu erleichtern, die Sie schneller benötigen, sind Microsoft-Verbesserungs Aktionen in Gruppen gegliedert:

* Identität (Azure Ad Konten & Rollen, wobei Azure ATP in Kürze verfügbar ist)
* Data (Microsoft Information Protection)
* Device (Microsoft Defender ATP Devices, demnächst verfügbar)
* App (e-Mail-und Cloud-apps, einschließlich Office 365 und Microsoft Cloud-App-Sicherheit)
* Infrastruktur (Azure-Ressourcen)

Auf der Microsoft Secure Score-Übersichtsseite können Sie sehen, wie Punkte zwischen diesen Gruppen aufgeteilt werden und welche Punkte verfügbar sind. Auf der Übersichtsseite erhalten Sie außerdem eine Übersicht über die Gesamtpunktzahl, die Verlaufs Entwicklung ihrer sicheren Partitur mit Benchmark-Vergleichen sowie priorisierte Verbesserungs Aktionen, die zur Verbesserung der Bewertung durchgeführt werden können.

![Secure Score Homepage](../../media/secure-score/homepage-original.png)
*Abbildung 1: Übersicht über die Microsoft Secure Scores-Seite*

## <a name="take-action-to-improve-your-score"></a>Durchführen von Aktionen zur Verbesserung der Punktzahl

Auf der Registerkarte Verbesserungs Aktionen werden die Sicherheitsempfehlungen für mögliche Angriffs Oberflächen sowie deren Status (abgeschlossen, nicht abgeschlossen, durch Drittanbieter aufgelöst und ignoriert) aufgeführt. Sie können alle Verbesserungs Aktionen durchsuchen, Filtern und gruppieren.

### <a name="ranking"></a>Ranking

Die Rangfolge basiert auf der Anzahl der verbleibenden Punkte, die zum Erreichen der Implementierungs Schwierigkeit, der Benutzer Auswirkungen und der Komplexität übrig bleiben. Die am höchsten bewerteten Verbesserungs Aktionen weisen eine große Anzahl von Punkten auf, die mit geringer Schwierigkeit, Benutzer Auswirkungen und Komplexität verbleiben.

### <a name="actions"></a>Aktionen

Aktionen mit der Bezeichnung [nicht erzielt] werden von Microsoft Secure Score nicht nachverfolgt. Sie können dennoch Aktionen durchführen, aber Sie haben keinen Einfluss auf Ihre Punktzahl. Wenn eine Aktion in Zukunft von Microsoft Secure Score verfolgt wird und Sie Sie bereits abgeschlossen haben, wird die Änderung automatisch von ihrer sicheren Punktzahl reflektiert.

Wenn Sie eine bestimmte Verbesserungs Aktion auswählen, wird ein verfliegt angezeigt. Um die Aktion abzuschließen, haben Sie einige Optionen:

1. Wählen Sie **Ansichtseinstellungen** aus, um den Konfigurationsbildschirm zu wechseln und die Änderung vorzunehmen. Sie erhalten dann die Punkte, die die Aktion Wert ist, am oberen Rand des ausfliegens sichtbar. Es kann bis zu 24 Stunden dauern, bis Punkte aktualisiert werden.

2. Wählen Sie **durch Drittanbieter auflösen** aus, da die Verbesserungs Aktion bereits von einer Drittanbieteranwendung oder-Software behoben wurde. Sie erhalten die Punkte, die die Aktion Wert ist, sodass Ihre sichere Punktzahl Ihre gesamte Sicherheitsposition besser widerspiegelt. Wenn ein Drittanbieter das Steuerelement nicht mehr abdeckt, können Sie die Verbesserungs Aktion als nicht abgeschlossen markieren. Beachten Sie, dass Microsoft keine Sichtbarkeit hat, ob die Bewertungsanforderungen erfüllt sind, wenn die Verbesserungs Aktion als durch Drittanbieter aufgelöst gekennzeichnet ist.

3. Wählen Sie **ignorieren** aus, da Sie sich entschieden haben, das Risiko zu akzeptieren und die Verbesserungs Aktion nicht zu verabschieden. Nachdem Sie eine Verbesserungs Aktion ignoriert haben, wird die Gesamtzahl der sicheren Punkte reduziert, die Sie erzielen können. Sie können diese Aktion im Verlauf anzeigen oder jederzeit wieder rückgängig machen.

4. Wählen Sie **überprüfen** aus, da für die Verbesserungs Aktion regelmäßig ein Teil Ihrer Umgebung überprüft werden muss, um Punkte zu erhalten und zu erhalten. Beispielsweise sollten Post Fach Weiterleitungsregeln wöchentlich überprüft werden, um sicherzustellen, dass die Daten nicht von Ihrem Netzwerk extrahiert werden. Sie müssen keine Änderungen vornehmen, es muss jedoch eine Aktion ausgeführt werden. Wenn Sie die Regeln regelmäßig überprüfen, werden Sie die Punkte erhalten. Wenn dies nicht der Fall ist, wird das Ergebnis reduziert.

![Beispiel für sichere Ergebnis Verbesserungs Aktion](../../media/secure-score/secure-score1x450.png) ![Beispiel zur Verbesserung der Sicherheit Score-Überarbeitungs Aktion](../../media/secure-score/secure-score2x450.png)

*Abbildungen 2 & 3: Flyouts zur Verbesserungs Aktion*

## <a name="monitor-improvements-over-time"></a>Überwachen von Verbesserungen

Auf der Registerkarte **Verlauf** können Sie ein Diagramm der Bewertung Ihrer Organisation über einen Zeitraum anzeigen. unter dem Graphen befindet sich eine Liste aller Aktionen, die im ausgewählten Zeitbereich und deren Attributen durchgeführt werden, beispielsweise Ergebnis Punkte und Kategorie. Sie können einen Datumsbereich anpassen und nach Kategorie filtern.

## <a name="risk-awareness"></a>Risikobewusstsein

Microsoft Secure Score ist eine numerische Zusammenfassung Ihrer Sicherheitsposition basierend auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsbezogenen Messungen. Es ist keine absolute Maßeinheit dafür, wie wahrscheinlich ein System oder Daten verletzt werden. Sie stellt vielmehr das Ausmaß dar, in dem Sie Sicherheitssteuerelemente in Ihrer Microsoft-Umgebung übernommen haben, wodurch das Risiko eines Sicherheits übertretungs ausgeglichen werden kann. Kein Onlinedienst ist vollständig gegen Sicherheitsverletzungen geschützt, und die sichere Bewertung sollte nicht als Garantie gegen Sicherheitsverletzungen in irgendeiner Weise interpretiert werden.

## <a name="whats-new"></a>Was ist neu?

Um Microsoft Secure Score zu einem besseren Vertreter ihrer Sicherheitsposition zu machen, haben wir einige Änderungen vorgenommen.

Informationen zu geplanten Änderungen finden Sie unter [What es Coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)

### <a name="removed-not-scored-improvement-actions"></a>Verbesserungs Aktionen "nicht bewertet" entfernt

Eines der Prinzipien von Secure Score ist, dass die Bewertung standardisiert und leicht zu beziehen ist. Durch Verbesserungs Aktionen, die nicht messbar oder handlungsbereit sind, wurde eine Verwechslung verursacht. Microsoft Secure Score ist nur dann sinnvoll, wenn jede Empfehlung einen klaren Einfluss auf die Bewertung haben kann. Nicht bewertete Verbesserungs Aktionen sind nicht messbar.  

Aus diesen Gründen wurden alle nicht erzielten Verbesserungs Aktionen entfernt. Ihrerseits ist keine Aktion erforderlich.

### <a name="removed-device-improvement-actions"></a>Entfernte Geräte Verbesserungs Aktionen

Nach einer Evaluierung der Microsoft Secure Score-Gerätekategorie für Verbesserungs Aktionen wurde festgestellt, dass diese Aktionen derzeit den Richtlinienstatus und nicht den Konfigurationsstatus von Geräten bewerten. Da die Konfiguration direkt mit der Sicherheitsposition verbunden ist, wurden die vorhandenen Geräteaktionen bestimmt, um die organisatorische Haltung nicht vollständig darzustellen.  Wir werden die aktuellen Aktionen in der Gerätekategorie entfernen, wenn wir eine Reihe von Empfehlungen zur Verfügung stellen, mit denen Diagnosedaten direkt verwendet werden, um die Position der Gerätesicherheit in vollem Umfang darzustellen.

Die folgenden Verbesserungs Aktionen wurden entfernt:

- Aktivieren der Verwaltung von mobilen Geräten in Microsoft InTune
- Erstellen einer Microsoft InTune-Konformitätsrichtlinie für Android
- Erstellen einer Microsoft InTune-Konformitätsrichtlinie für Android for Work
- Erstellen einer Microsoft InTune-App-Schutzrichtlinie für Android
- Erstellen einer Microsoft InTune-App-Schutzrichtlinie für IOS
- Geräte markieren, für die keine Microsoft InTune-Konformitätsrichtlinie als nicht kompatibel zugewiesen ist
- Erstellen einer Microsoft InTune-Konformitätsrichtlinie für IOS
- Erstellen einer Microsoft InTune-Konformitätsrichtlinie für macOS
- Erstellen einer Microsoft InTune-Konformitätsrichtlinie für Windows
- Erstellen eines Microsoft InTune-Konfigurationsprofils für Android
- Erstellen eines Microsoft InTune-Konfigurationsprofils für Android for Work
- Erstellen eines Microsoft InTune-Konfigurationsprofils für macOS
- Erstellen eines Microsoft InTune-Konfigurationsprofils für IOS
- Erstellen eines Microsoft InTune-Konfigurationsprofils für Windows
- Aktivieren der verbesserten Jailbreak-Erkennung in Microsoft InTune
- Erfordern, dass alle Geräte gepatcht werden, Virenschutz und Firewalls aktiviert sind
- Aktivieren der Integration von Windows Defender ATP in Microsoft InTune
- Erstellen einer Microsoft InTune-Windows-Informationsschutz Richtlinie
- Erfordern von erweiterten Sicherheitskonfigurationen für alle Geräte
- Bericht überprüfen blockierter Geräte wöchentlich

### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a>Entfernen von Verbesserungs Aktionen, die die Erwartungen für eine zuverlässige Messung nicht erfüllen

Um sicherzustellen, dass die Microsoft Secure Score sinnvoll ist und dass jede Verbesserungs Aktion messbar und zuverlässig ist, haben wir die folgenden Verbesserungs Aktionen entfernt:

- Aktivieren der Aufzeichnung von Überwachungsdaten
- Ermitteln riskanter und nicht kompatibler Shadow-IT-Anwendungen
- Überprüfen von Berechtigungen & blockieren riskanter OAuth-Anwendungen, die mit Ihrer Umgebung verbunden sind
- Einrichten der Versionsverwaltung in SharePoint Online-Dokumentbibliotheken

### <a name="mfa-improvement-action-updates"></a>Aktualisierung der MFA-Verbesserungs Aktionen

Um den Anforderungen an Unternehmen Rechnung zu tragen, beim Anwenden von Richtlinien, die mit Ihrem Unternehmen zusammenarbeiten, die höchste Sicherheit zu gewährleisten, hat Microsoft Secure Score drei Verbesserungs Aktionen im Bereich der mehrstufigen Authentifizierung entfernt und zwei hinzugefügt.

Verbesserungs Aktionen wurden entfernt:

- Registrieren aller Benutzer für mehrstufige Authentifizierung
- MFA für alle Benutzer erforderlich
- MFA für Azure AD privilegierten Rollen erforderlich

Verbesserungs Aktionen wurden hinzugefügt:

- Sicherstellen, dass alle Benutzer mehrstufige Authentifizierung für sicheren Zugriff ausführen können
- MFA für Administratorrollen erforderlich

 Diese neuen Verbesserungs Aktionen erfordern das Registrieren Ihrer Benutzer oder Administratoren für mehrstufige Authentifizierung (MFA) in Ihrem Verzeichnis und das Festlegen der richtigen Richtlinien, die Ihren organisatorischen Anforderungen entsprechen. Das Hauptziel besteht in der Flexibilität bei gleichzeitiger Sicherstellung, dass alle Benutzer und Administratoren sich mit mehreren Faktoren oder mit risikobasierten Identitäts Überprüfungs Ansagen authentifizieren können. Dies kann die Form haben, dass mehrere Richtlinien mit bereichsbezogenen Entscheidungen angewendet werden oder Sicherheitsstandards (am 16. März) festgelegt werden, mit denen Microsoft entscheiden kann, wann die Benutzer für MFA herausgefordert werden sollen.

### <a name="removed-review-improvement-actions"></a>Verbesserungs Aktionen "überprüfen" entfernt

Eines der Prinzipien von Secure Score ist, dass die Bewertung standardisiert und leicht zu beziehen ist. Durch Verbesserungs Aktionen, die nicht messbar oder handlungsbereit sind, wurde eine Verwechslung verursacht. Ein sicheres Ergebnis von Microsoft ist nur dann sinnvoll, wenn jede Empfehlung einen klaren Effekt auf die Bewertung haben kann. Überarbeitungs Verbesserungs Aktionen werden nicht auf den gleichen Standard wie andere Verbesserungs Aktionen gemessen.  

Aus diesen Gründen wurden alle Verbesserungs Aktionen, die eine Überarbeitungs Kadenz erforderten, vorübergehend entfernt. Ihrerseits ist keine Aktion erforderlich.

### <a name="preview-features"></a>Vorschaufeatures

Die folgenden Features werden in der [Vorschauversion](microsoft-secure-score-preview.md)enthalten sein:

* Alle neuen Metriken und Trends-Ansichten für ciso-und Lead-Level-Diskussionen
* Neue Möglichkeiten zum Nachverfolgen und benchmarken Ihrer Partitur
* Bessere Nachverfolgung und Überwachung für Ergebnis Regressionen
* Filtern, markieren, suchen und Gruppieren von Verbesserungs Aktionen
* Verwalten Ihrer zukünftigen Ziele mithilfe von Bewertungs Projektionen und geplanten Aktionen
* Vereinfachung des Punktesystems
* Und vieles mehr!

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, lassen Sie es uns bitte wissen, indem Sie in der [Sicherheits-, Datenschutz-& Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) -Community veröffentlichen. Wir überwachen die Community und helfen Ihnen dabei.
