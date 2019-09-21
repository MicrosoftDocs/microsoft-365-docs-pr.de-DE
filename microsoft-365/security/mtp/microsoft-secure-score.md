---
title: Microsoft-Sicherheitsbewertung
description: Beschreibt Microsoft Secure Score im Microsoft 365 Security Center, wie Details berechnet werden und welche Sicherheitsadministratoren davon erwarten können.
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
ms.openlocfilehash: 17d2decc7374d9022c68cbe2f2d58da959f44a7d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082759"
---
# <a name="microsoft-secure-score"></a>Microsoft-Sicherheitsbewertung

>[!IMPORTANT]
>Einige Informationen beziehen sich auf vorversions Produkte, die möglicherweise wesentlich geändert werden, bevor Sie kommerziell veröffentlicht werden. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Mit Microsoft-Sicherheitsbewertung im Microsoft 365 Security Center können Sie einen besseren Überblick und mehr Kontrolle über den Sicherheitsstatus Ihres Unternehmens erhalten. Von einem zentralen Dashboard aus können Sie die Sicherheit Ihrer Microsoft 365 Identitäten, Daten, Anwendungen, Geräte und Infrastrukturen überwachen und verbessern.

Microsoft-Sicherheitsbewertung bietet Ihnen robuste Visualisierungen, die Integration mit anderen Microsoft-Produkten, den Vergleich Ihrer Ergebnisse mit anderen Unternehmen, die Filterung nach Kategorien und vieles mehr. Mit dem Tool können Sie Maßnahmen zur Verbesserung der Sicherheit in Ihrer Organisation durchführen und die Entwicklung Ihrer Bewertung verfolgen. Die Bewertung zeigt auch, wenn Lösungen von Drittanbietern empfohlene Verbesserungsmaßnahmen behandelt haben.  

## <a name="how-it-works"></a>Funktionsweise

Sie erhalten Punkte zum Konfigurieren empfohlener Sicherheitsfeatures, zum Ausführen sicherheitsbezogener Aufgaben (beispielsweise zum Anzeigen von Berichten) oder zur Adressierung der Verbesserungs Aktion mit einer Anwendung oder Software eines Drittanbieters. Einige Aktionen werden für einer teilweisen Vervollständigung bewertet, wie z.B. die Aktivierung der Mehrstufige Authentifizierung (MFA) für Ihre Benutzer. Sicherheit sollte immer mit Benutzerfreundlichkeit in Einklang gebracht werden, und nicht jede Empfehlung wird für Ihre Umgebung funktionieren.

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Um Microsoft Secure Score anzeigen zu können, müssen Sie in Azure Active Directory eine der folgenden Rollen zugewiesen sein:

* Globaler Administrator
* Sicherheitsadministrator
* Sicherheits Leser

## <a name="rich-experiences--additional-security-recommendations"></a>Umfangreiche Erfahrungen #a0 Zusätzliche Sicherheitsempfehlungen

In Microsoft Secure Score wurden Empfehlungen aus Azure AD, InTune und Cloud App Security mit Empfehlungen von Azure Security Center und Microsoft Defender ATP in Kürze hinzugefügt. Außerdem haben wir noch weitere Office 365 Sicherheitsempfehlungen hinzugefügt. Dank zusätzlicher Einblicke und größerer Transparenz in einer breiteren Palette von Microsoft-Produkten und-Diensten können Sie sich sicher fühlen, dass Sie die Verwaltung über die Sicherheitsintegrität Ihrer Organisation berichten. Sie können Ihre Partitur auch mithilfe der [Microsoft Graph-API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta)abrufen.

Um Ihnen die Informationen zu erleichtern, die Sie schneller benötigen, sind Microsoft-Empfehlungen in Gruppen gegliedert:

* Identität (Schutzstatus ihrer Azure Ad Konten und Rollen)
* Daten (Schutzstatus Ihrer Office 365 Dokumente)
* Gerät (Schutzstatus Ihrer Geräte; Microsoft Defender-ATP-Verbesserungs Aktionen in Kürze verfügbar
* App (Schutzstatus Ihrer e-Mail-und Cloud-Apps)
* Infrastruktur (Schutzzustand ihrer Azure-Ressourcen; demnächst verfügbar)

Auf der Microsoft Secure Score-Übersichtsseite können Sie sehen, wie Punkte zwischen diesen Gruppen aufgeteilt werden und welche Punkte verfügbar sind. Auf der Übersichtsseite erhalten Sie außerdem eine Übersicht über die Gesamtpunktzahl, die Verlaufs Entwicklung ihrer sicheren Partitur mit Benchmark-Vergleichen sowie priorisierte Verbesserungs Aktionen, die zur Verbesserung der Bewertung durchgeführt werden können. Sie können diese Daten verwenden, um zu agieren und große Unterschiede in ihrer Sicherheitsposition zu treffen.  

![M365-](../media/secure-score/homepage-original.png)
Start*Seite Abbildung 1: Microsoft Secure Score –* Übersichtsseite

## <a name="take-action-to-improve-your-score"></a>Durchführen von Aktionen zur Verbesserung der Punktzahl

Auf der Registerkarte Verbesserungs Aktionen werden alle Sicherheitsempfehlungen für Ihren Mandanten zusammen mit dem Status (abgeschlossen, nicht abgeschlossen, durch Drittanbieter aufgelöst und ignoriert) aufgelistet. Sie können alle Steuerelemente durchsuchen, Filtern und gruppieren.  Die Rangfolge basiert auf der Bewertung von Microsoft sowohl des Sicherheits Werts als auch der Bemühen um Vollständigkeit.

Aktionen mit der Bezeichnung [nicht erzielt] werden von Microsoft Secure Score nicht nachverfolgt. Sie können dennoch Aktionen durchführen, aber Sie haben keinen Einfluss auf Ihre Punktzahl. Wenn eine Aktion in Zukunft von Microsoft Secure Score verfolgt wird und Sie Sie bereits abgeschlossen haben, wird die Änderung automatisch von ihrer sicheren Punktzahl reflektiert.

Wenn Sie auf eine Verbesserungs Aktion klicken, wird ein verfliegt angezeigt. Um die Aktion abzuschließen, haben Sie einige Optionen:

1. Wählen Sie **Ansichtseinstellungen** aus, um den Konfigurationsbildschirm zu wechseln und die Änderung vorzunehmen. Sie erhalten dann die Punkte, die die Aktion Wert ist, am oberen Rand des ausfliegens sichtbar. Es kann bis zu 24 Stunden dauern, bis Punkte aktualisiert werden.

2. Wählen Sie **durch Drittanbieter auflösen** aus, da die Verbesserungs Aktion bereits von einer Drittanbieteranwendung oder-Software behoben wurde. Sie erhalten die Punkte, die die Aktion Wert ist, sodass Ihre sichere Punktzahl Ihre gesamte Sicherheitsposition besser widerspiegelt. Wenn ein Drittanbieter das Steuerelement nicht mehr abdeckt, können Sie die Verbesserungs Aktion als nicht abgeschlossen markieren. Bitte beachten Sie, dass Microsoft keine Sichtbarkeit hat, ob die Bewertungsanforderungen erfüllt sind, wenn die Verbesserungs Aktion als durch Drittanbieter aufgelöst gekennzeichnet ist.

3. Wählen Sie **ignorieren** aus, da Sie sich entschieden haben, das Risiko zu akzeptieren und die Verbesserungs Aktion nicht zu verabschieden. Nachdem Sie eine Verbesserungs Aktion ignoriert haben, wird die Gesamtzahl der sicheren Punkte reduziert, die Sie erzielen können. Sie können diese Aktion im Verlauf anzeigen oder jederzeit wieder rückgängig machen.

4. Wählen Sie **überprüfen** aus, da für die Verbesserungs Aktion regelmäßig ein Teil Ihrer Umgebung überprüft werden muss, um Punkte zu erhalten und zu erhalten. Beispielsweise sollten Post Fach Weiterleitungsregeln wöchentlich überprüft werden, um sicherzustellen, dass die Daten nicht von Ihrem Netzwerk extrahiert werden. Sie müssen keine Änderungen vornehmen, es muss jedoch eine Aktion ausgeführt werden. Wenn Sie die Regeln regelmäßig überprüfen, werden Sie die Punkte erhalten. Wenn dies nicht der Fall ist, wird das Ergebnis reduziert.

![M365-Homepage](../media/secure-score/secure-score1x450.png) ![M365-Homepage](../media/secure-score/secure-score2x450.png)

*Abbildungen 2 #a0 3: Flyouts zur Verbesserungs Aktion*

## <a name="monitor-improvements-over-time"></a>Überwachen von Verbesserungen

Auf der Registerkarte **Verlauf** können Sie ein Diagramm der Bewertung Ihrer Organisation im Laufe der Zeit anzeigen. Diese Ansicht umfasst den globalen Durchschnitt, den Branchendurchschnitt und eine ähnliche Anzahl von Arbeitsplätzen sowie alle Aktionen, die im ausgewählten Zeitbereich durchgeführt wurden. Sie können auch einen Datumsbereich anpassen und nach Kategorie filtern.

Das Ergebnis wird einmal pro Tag berechnet (um 1:00 Uhr PST). Wenn Sie eine Änderung an einer gemessenen Aktion vornehmen, wird das Ergebnis automatisch am nächsten Tag aktualisiert. Es ist auch wichtig zu beachten, dass einige andere Portale Teile der Microsoft Secure Score (wie Microsoft Defender Security Center) anzeigen. Wenn Sie eine Verbesserungs Aktion durchführen und die Bewertung in diesen Portalen erhöht wird, kann es bis zu 24 Stunden dauern, bis das aktualisierte Ergebnis im Microsoft 365 Security Center angezeigt wird.  

## <a name="how-improvement-actions-are-scored"></a>So werden Verbesserungs Aktionen bewertet

Die meisten werden in binärer Weise bewertet – Sie erhalten 100% der Punkte, wenn Sie die Verbesserungs Aktion implementieren, wie das Erstellen einer neuen Richtlinie oder das Aktivieren einer bestimmten Einstellung. Bei anderen Verbesserungs Aktionen werden Punkte als Prozentsatz der Gesamtkonfiguration angegeben. Wenn beispielsweise die Verbesserungs Aktion besagt, dass Sie 30 Punkte erhalten, wenn Sie alle Ihre Benutzer mit mehrstufiger Authentifizierung schützen und nur 5 von 100 gesamt Benutzern geschützt sind, erhalten Sie ein Teilergebnis von rund 2 Punkten (5 Protected/100 Total * 30 MAX pts = 2  PTS-Teilergebnis).

## <a name="risk-awareness"></a>Risikobewusstsein

Microsoft Secure Score ist eine numerische Zusammenfassung Ihrer Sicherheitsposition basierend auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsbezogenen Messungen. Es ist keine absolute Maßeinheit dafür, wie wahrscheinlich ein System oder Daten verletzt werden. Sie stellt vielmehr das Ausmaß dar, in dem Sie Sicherheitssteuerelemente in Ihrer Microsoft-Umgebung übernommen haben, wodurch das Risiko eines Sicherheits übertretungs ausgeglichen werden kann. Kein Onlinedienst ist vollständig gegen Sicherheitsverletzungen geschützt, und die sichere Bewertung sollte nicht als Garantie gegen Sicherheitsverletzungen in irgendeiner Weise interpretiert werden.

## <a name="we-want-to-hear-from-you"></a>Wir möchten von Ihnen hören

Wenn Sie Probleme haben, lassen Sie es uns bitte wissen, indem Sie in der [Sicherheits-, Datenschutz-#a0 Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) -Community veröffentlichen. Wir überwachen die Community und helfen Ihnen dabei.
