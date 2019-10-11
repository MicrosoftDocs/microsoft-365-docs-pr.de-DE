---
title: Microsoft-Sicherheitsbewertung
description: Beschreibt Microsoft Secure Score im Microsoft 365 Security Center, wie Details berechnet werden und welche Sicherheitsadministratoren erwarten können.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, sicheres Ergebnis, Sicherheitscenter, Verbesserungs Aktionen
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: b337f020702b60ceeb02043e9b66d5614f58c228
ms.sourcegitcommit: 27a7a373ca77375fdab0690a899135fad16c3cf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435559"
---
# <a name="microsoft-secure-score"></a>Microsoft-Sicherheitsbewertung

Microsoft Secure Score ist ein Maß für die Sicherheitslage einer Organisation mit einer höheren Zahl, die mehr Verbesserungs Aktionen anzeigt. Von einem zentralisierten Dashboard im Microsoft 365 Security Center aus können Organisationen die Sicherheit Ihrer Microsoft 365-Identitäten, Daten, apps, Geräte und Infrastruktur überwachen und daran arbeiten.

Mit Secure Score können Organisationen Folgendes tun:  

* Bericht über den aktuellen Status der Sicherheitsposition der Organisation.
* Verbessern Sie Ihre Sicherheitsposition durch Bereitstellen von Auffindbarkeit, Sichtbarkeit, Anleitung und Steuerung.  
* Vergleichen Sie mit Benchmarks, und legen Sie Key Performance Indicators (KPIs) fest.

Mit Secure Score erhalten Organisationen Zugriff auf robuste Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, den Vergleich mit ähnlichen Organisationen und vieles mehr. Die Bewertung kann auch reflektieren, wenn von Drittanbieterlösungen Empfohlene Aktionen behandelt wurden.

Darüber hinaus können Sie über die [Microsoft Graph-API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta)auf Ihre Empfehlungen und Gäste zugreifen.

## <a name="how-it-works"></a>Funktionsweise

Sie erhalten Punkte zum Konfigurieren empfohlener Sicherheitsfeatures, zum Ausführen sicherheitsbezogener Aufgaben (beispielsweise zum Anzeigen von Berichten) oder zur Adressierung der Verbesserungs Aktion mit einer Anwendung oder Software eines Drittanbieters. Einige Verbesserungs Aktionen geben nur dann Punkte, wenn Sie vollständig abgeschlossen sind, und einige geben partielle Punkte an, wenn Sie für einige Geräte oder Benutzer abgeschlossen werden. Sicherheit sollte immer mit Benutzerfreundlichkeit abgeglichen werden, und nicht jede Empfehlung kann für Ihre Umgebung funktionieren.

Ihre Punktzahl wird in Echtzeit aktualisiert, um die Informationen widerzuspiegeln, die auf den Seiten Visualisierungen und Verbesserungs Aktionen angezeigt werden. Secure Score synchronisiert auch täglich, um Systemdaten zu ihren erreichten Punkten für jede Aktion zu erhalten.

### <a name="how-improvement-actions-are-scored"></a>So werden Verbesserungs Aktionen bewertet

Die meisten werden auf binäre Weise bewertet – Wenn Sie die Verbesserungs Aktion implementieren, wie das Erstellen einer neuen Richtlinie oder das Aktivieren einer bestimmten Einstellung, erhalten Sie 100% der Punkte. Bei anderen Verbesserungs Aktionen werden Punkte als Prozentsatz der Gesamtkonfiguration angegeben. Wenn die Verbesserungs Aktion beispielsweise besagt, dass Sie 30 Punkte erhalten, indem Sie alle Ihre Benutzer mit mehrstufiger Authentifizierung schützen und nur 5 von 100 gesamt Benutzern geschützt sind, erhalten Sie einen Teil der Punktzahl von rund 2 Punkten (5 Protected/100 Total * 30 MAX pts = 2 Pkt.  Teilergebnis).

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Um über die Berechtigung zum Zugriff auf Microsoft Secure Score verfügen zu können, muss in Azure Active Directory eine der folgenden Rollen zugewiesen sein.

### <a name="read-and-write-roles"></a>Lesen und Schreiben von Rollen

Mit Lese-und Schreibzugriff können Sie Änderungen vornehmen und direkt mit Secure Score interagieren. Sie können auch anderen Benutzern schreibgeschützten Zugriff zuweisen.

* CompanyAdministrator
* SecurityAdministrator
* ExchangeAdmin
* SharePointAdmin

### <a name="read-only-roles"></a>Schreibgeschützte Rollen

Mit schreibgeschütztem Zugriff können Sie den Status oder die Notizen für eine Verbesserungs Aktion nicht bearbeiten, Bewertungs Zonen bearbeiten oder benutzerdefinierte Vergleiche bearbeiten.

* HelpdeskAdmin
* UserAccountAdmin
* ServiceSupportAdmin
* SecurityReader
* SecurityOperator
* GlobalReader

### <a name="graph-api"></a>Graph-API

Für den Zugriff auf die Graph-API benötigen Sie zusätzlich zu einer Rolle einen der folgenden Bereiche:

* Bereich securityevents. Read. all (für schreibgeschützte Rolle)
* Bereich securityevents. ReadWrite. all (für Lese-und Schreibrolle)

## <a name="rich-experiences--security-recommendations"></a>Umfangreiche Erfahrungen #a0 Sicherheitsempfehlungen

In Microsoft Secure Score gibt es Empfehlungen aus Office 365, Azure AD, InTune und Cloud-App-Sicherheit mit Empfehlungen von Azure Security Center und Microsoft Defender Security Center in Kürze.

Um Ihnen die Informationen zu erleichtern, die Sie schneller benötigen, sind Microsoft-Empfehlungen in Gruppen gegliedert:

* Identität (Azure Ad Konten und Rollen)
* Daten (Office 365 Dokumente)
* Gerät (Microsoft Defender ATP-Geräte)
* App (e-Mail-und Cloud-Apps)
* Infrastruktur (Azure-Ressourcen)

Auf der Microsoft Secure Score-Übersichtsseite können Sie sehen, wie Punkte zwischen diesen Gruppen aufgeteilt werden und welche Punkte verfügbar sind. Auf der Übersichtsseite erhalten Sie außerdem eine Übersicht über die Gesamtpunktzahl, die Verlaufs Entwicklung ihrer sicheren Partitur mit Benchmark-Vergleichen sowie priorisierte Verbesserungs Aktionen, die zur Verbesserung der Bewertung durchgeführt werden können. Sie können diese Daten verwenden, um zu agieren und große Unterschiede in ihrer Sicherheitsposition zu treffen.  

![Secure Score Homepage](../media/secure-score/homepage-original.png)
*Abbildung 1: Übersicht über die Microsoft Secure Scores-Seite*

## <a name="take-action-to-improve-your-score"></a>Durchführen von Aktionen zur Verbesserung der Punktzahl

Auf der Registerkarte Verbesserungs Aktionen werden die Sicherheitsempfehlungen für mögliche Angriffs Oberflächen sowie deren Status (abgeschlossen, nicht abgeschlossen, durch Drittanbieter aufgelöst und ignoriert) aufgeführt. Sie können alle Verbesserungs Aktionen durchsuchen, Filtern und gruppieren.

### <a name="ranking"></a>Ranking

Die Rangfolge basiert auf der Anzahl der verbleibenden Punkte, die zum Erreichen der Implementierungs Schwierigkeit, der Benutzer Auswirkungen und der Komplexität übrig bleiben. Die am höchsten bewerteten Verbesserungs Aktionen weisen bei niedrigen Schwierigkeitsgraden, Benutzer Auswirkungen und Komplexität große verbleibende Punkte auf.

### <a name="actions"></a>Aktionen

Aktionen mit der Bezeichnung [nicht erzielt] werden von Microsoft Secure Score nicht nachverfolgt. Sie können dennoch Aktionen durchführen, aber Sie haben keinen Einfluss auf Ihre Punktzahl. Wenn eine Aktion in Zukunft von Microsoft Secure Score verfolgt wird und Sie Sie bereits abgeschlossen haben, wird die Änderung automatisch von ihrer sicheren Punktzahl reflektiert.

Wenn Sie eine bestimmte Verbesserungs Aktion auswählen, wird ein verfliegt angezeigt. Um die Aktion abzuschließen, haben Sie einige Optionen:

1. Wählen Sie **Ansichtseinstellungen** aus, um den Konfigurationsbildschirm zu wechseln und die Änderung vorzunehmen. Sie erhalten dann die Punkte, die die Aktion Wert ist, am oberen Rand des ausfliegens sichtbar. Es kann bis zu 24 Stunden dauern, bis Punkte aktualisiert werden.

2. Wählen Sie **durch Drittanbieter auflösen** aus, da die Verbesserungs Aktion bereits von einer Drittanbieteranwendung oder-Software behoben wurde. Sie erhalten die Punkte, die die Aktion Wert ist, sodass Ihre sichere Punktzahl Ihre gesamte Sicherheitsposition besser widerspiegelt. Wenn ein Drittanbieter das Steuerelement nicht mehr abdeckt, können Sie die Verbesserungs Aktion als nicht abgeschlossen markieren. Beachten Sie, dass Microsoft keine Sichtbarkeit hat, ob die Bewertungsanforderungen erfüllt sind, wenn die Verbesserungs Aktion als durch Drittanbieter aufgelöst gekennzeichnet ist.

3. Wählen Sie **ignorieren** aus, da Sie sich entschieden haben, das Risiko zu akzeptieren und die Verbesserungs Aktion nicht zu verabschieden. Nachdem Sie eine Verbesserungs Aktion ignoriert haben, wird die Gesamtzahl der sicheren Punkte reduziert, die Sie erzielen können. Sie können diese Aktion im Verlauf anzeigen oder jederzeit wieder rückgängig machen.

4. Wählen Sie **überprüfen** aus, da für die Verbesserungs Aktion regelmäßig ein Teil Ihrer Umgebung überprüft werden muss, um Punkte zu erhalten und zu erhalten. Beispielsweise sollten Post Fach Weiterleitungsregeln wöchentlich überprüft werden, um sicherzustellen, dass die Daten nicht von Ihrem Netzwerk extrahiert werden. Sie müssen keine Änderungen vornehmen, es muss jedoch eine Aktion ausgeführt werden. Wenn Sie die Regeln regelmäßig überprüfen, werden Sie die Punkte erhalten. Wenn dies nicht der Fall ist, wird das Ergebnis reduziert.

![Beispiel für sichere Ergebnis Verbesserungs Aktion](../media/secure-score/secure-score1x450.png) ![Beispiel zur Verbesserung der Sicherheit Score-Überarbeitungs Aktion](../media/secure-score/secure-score2x450.png)

*Abbildungen 2 #a0 3: Flyouts zur Verbesserungs Aktion*

## <a name="monitor-improvements-over-time"></a>Überwachen von Verbesserungen

Auf der Registerkarte **Verlauf** können Sie ein Diagramm der Bewertung Ihrer Organisation über einen Zeitraum anzeigen. unter dem Graphen befindet sich eine Liste aller Aktionen, die im ausgewählten Zeitbereich und deren Attributen durchgeführt werden, beispielsweise Ergebnis Punkte und Kategorie. Sie können einen Datumsbereich anpassen und nach Kategorie filtern.

## <a name="risk-awareness"></a>Risikobewusstsein

Microsoft Secure Score ist eine numerische Zusammenfassung Ihrer Sicherheitsposition basierend auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsbezogenen Messungen. Es ist keine absolute Maßeinheit dafür, wie wahrscheinlich ein System oder Daten verletzt werden. Sie stellt vielmehr das Ausmaß dar, in dem Sie Sicherheitssteuerelemente in Ihrer Microsoft-Umgebung übernommen haben, wodurch das Risiko eines Sicherheits übertretungs ausgeglichen werden kann. Kein Onlinedienst ist vollständig gegen Sicherheitsverletzungen geschützt, und die sichere Bewertung sollte nicht als Garantie gegen Sicherheitsverletzungen in irgendeiner Weise interpretiert werden.

## <a name="whats-coming"></a>Was kommt?

Um Microsoft Secure Score zu einem besseren Vertreter ihrer Sicherheitsposition zu machen und die Benutzerfreundlichkeit zu verbessern, werden wir in naher Zukunft einige Änderungen vornehmen. Ihre Punktzahl und die maximal mögliche Punktzahl ändern sich. Dies impliziert jedoch keine Änderung ihrer Sicherheitsposition.

### <a name="removing-not-scored-and-review-improvement-actions"></a>Entfernen von Verbesserungs Aktionen für "nicht bewertet" und "überprüfen"

Eines der Prinzipien von Secure Score ist, dass die Bewertung standardisiert und leicht zu beziehen ist. Durch Verbesserungs Aktionen, die nicht messbar oder handlungsbereit sind, wurde eine Verwechslung verursacht. Ein sicheres Ergebnis von Microsoft ist nur dann sinnvoll, wenn jede Empfehlung einen klaren Effekt auf die Bewertung haben kann. Nicht bewertete Verbesserungs Aktionen sind nicht messbar, und Überprüfungs Verbesserungs Aktionen werden nicht auf den gleichen Standard wie andere Verbesserungs Aktionen gemessen.  

Aus diesen Gründen werden alle Verbesserungs Aktionen, die nicht erzielt wurden oder die eine Überarbeitungs Kadenz erforderten, vorübergehend entfernt. Ihrerseits ist keine Aktion erforderlich.

### <a name="simplification-of-the-point-system"></a>Vereinfachung des Punktesystems

Um Punkte über mehrere Erfahrungen hinweg zu standardisieren, werden alle Aktionspunkte für eine sichere Punktzahl verbessert, sodass Sie 10 oder mehr Punkte Wert haben. Es ist erforderlich, dass die gesamte Breite Verschnaufpause von Sicherheitskontrollen konsistenter ist, die wir heute haben, und diejenigen, die wir in Zukunft hinzufügen werden. Dies ist zwar eine wesentliche Änderung, und es wird eine Verringerung der Gesamtzahl der Punkte angezeigt, aber ihre Sicherheitsposition wird nicht geändert.  

### <a name="preview-features"></a>Vorschau-Features

Die folgenden Features werden in der Vorschauversion enthalten sein:

* Alle neuen Metriken und Trends-Ansichten für ciso-und Lead-Level-Diskussionen
* Neue Möglichkeiten zum Nachverfolgen und benchmarken Ihrer Partitur
* Bessere Nachverfolgung und Überwachung für Ergebnis Regressionen
* Filtern, markieren, suchen und Gruppieren von Verbesserungs Aktionen
* Verwalten Ihrer zukünftigen Ziele mithilfe von Bewertungs Projektionen und geplanten Aktionen
* Und vieles mehr!

## <a name="we-want-to-hear-from-you"></a>Wir möchten von Ihnen hören

Wenn Sie Probleme haben, lassen Sie es uns bitte wissen, indem Sie in der [Sicherheits-, Datenschutz-#a0 Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) -Community veröffentlichen. Wir überwachen die Community und helfen Ihnen dabei.
