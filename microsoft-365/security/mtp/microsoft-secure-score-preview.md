---
title: Microsoft Secure Score (Vorschau)
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
ms.openlocfilehash: 5ce06f582966f7209d4b539f9de41e8045b98519
ms.sourcegitcommit: af7950d9674f0eab3aee03f9afccff9ca2f4709a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40970923"
---
# <a name="microsoft-secure-score-preview"></a>Microsoft Secure Score (Vorschau)

>[!IMPORTANT]
>Einige Informationen beziehen sich auf vorversions Produkte, die möglicherweise wesentlich geändert werden, bevor Sie kommerziell veröffentlicht werden. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft Secure Score ist ein Maß für die Sicherheitslage einer Organisation mit einer höheren Zahl, die mehr Verbesserungs Aktionen anzeigt. Wenn Sie die Sicherheits Bewertungsempfehlungen befolgen, können Sie Ihre Organisation vor Bedrohungen schützen. Von einem zentralisierten Dashboard im Microsoft 365 Security Center aus können Organisationen die Sicherheit Ihrer Microsoft 365-Identitäten, Daten, apps, Geräte und Infrastruktur überwachen und daran arbeiten.

Secure Score hilft Organisationen:  

* Bericht über den aktuellen Status der Sicherheitsposition der Organisation.
* Verbessern Sie Ihre Sicherheitsposition durch Bereitstellen von Auffindbarkeit, Sichtbarkeit, Anleitung und Steuerung.  
* Vergleichen Sie mit Benchmarks, und legen Sie Key Performance Indicators (KPIs) fest.

Organisationen erhalten Zugriff auf robuste Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, den Vergleich mit ähnlichen Organisationen und vieles mehr. Die Bewertung kann auch reflektieren, wenn von Drittanbieterlösungen Empfohlene Aktionen behandelt wurden.

Darüber hinaus können Sie über die [Microsoft Graph-API](https://www.microsoft.com/security/partnerships/graph-security-api)auf Ihre Empfehlungen und Gäste zugreifen. Erfahren Sie mehr über den [Ressourcentyp Secure Score](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Funktionsweise

Sie erhalten Punkte zum Konfigurieren empfohlener Sicherheitsfeatures, zum Ausführen sicherheitsbezogener Aufgaben oder zum Beheben der Verbesserungs Aktion mit einer Drittanbieteranwendung oder-Software. Einige Verbesserungs Aktionen geben nur dann Punkte, wenn Sie vollständig abgeschlossen sind, und einige geben partielle Punkte an, wenn Sie für einige Geräte oder Benutzer abgeschlossen werden. Wenn Sie eine der Verbesserungs Aktionen nicht oder nicht durchführen möchten, können Sie das Risiko oder das verbleibende Risiko akzeptieren.

Wir zeigen Ihnen den vollständigen Überblick über mögliche Verbesserungen, unabhängig von der Lizenz, sodass Sie bewährte Methoden für die Sicherheit verstehen und Ihre Punktzahl verbessern können. Ihre absolute Sicherheitsposition wird durch Secure Score dargestellt, was unabhängig von den Produktlizenzen, die Ihre Organisation besitzt, gleich bleibt. Beachten Sie, dass die Sicherheit mit der Benutzerfreundlichkeit ausgeglichen werden sollte, und nicht jede Empfehlung kann für Ihre Umgebung funktionieren.

Ihre Punktzahl wird in Echtzeit aktualisiert, um die Informationen widerzuspiegeln, die auf den Seiten Visualisierungen und Verbesserungs Aktionen angezeigt werden. Secure Score synchronisiert auch täglich, um Systemdaten zu ihren erreichten Punkten für jede Aktion zu erhalten.

### <a name="how-improvement-actions-are-scored"></a>So werden Verbesserungs Aktionen bewertet

Jede Verbesserungs Aktion ist auf 10 Punkte oder niedriger Wert. Die meisten werden auf binäre Weise bewertet – Wenn Sie die Verbesserungs Aktion implementieren, wie Sie eine neue Richtlinie erstellen oder eine bestimmte Einstellung aktivieren, erhalten Sie 100% der Punkte. Bei anderen Verbesserungs Aktionen werden Punkte als Prozentsatz der Gesamtkonfiguration angegeben. Wenn die Verbesserungs Aktion beispielsweise besagt, dass Sie 30 Punkte erhalten, indem Sie alle Ihre Benutzer mit mehrstufiger Authentifizierung schützen und nur 5 von 100 gesamt Benutzern geschützt sind, erhalten Sie einen Teil der Punktzahl von etwa 2 Punkten (5 Protected/100 Total * 30 MAX pts = 2 PTS Partial Score).

### <a name="products-included-in-secure-score"></a>Produkte im Lieferumfang von Secure Score

Derzeit gibt es Empfehlungen für Office 365 (einschließlich SharePoint Online, Exchange Online, OneDrive für Unternehmen, Microsoft Information Protection und mehr), Azure AD, InTune, Microsoft Defender ATP und Cloud-App-Sicherheit. Empfehlungen für andere Sicherheitsprodukte finden Sie in Kürze. Die Empfehlungen decken nicht alle Angriffsflächen ab, die jedem Produkt zugeordnet sind, sind jedoch ein guter Ausgangswert. Sie können auch die Verbesserungs Aktionen als von einem Drittanbieter abgedeckt markieren.

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
* Sicherheitsleseberechtigter
* Sicherheitsoperator
* Globaler Leser

### <a name="graph-api"></a>Graph-API

Für den Zugriff auf die Graph-API benötigen Sie zusätzlich zu einer Rolle einen der folgenden Bereiche:

* Bereich securityevents. Read. all (für schreibgeschützte Rollen)
* Bereich securityevents. ReadWrite. all (für Lese-und Schreibrollen)

## <a name="gain-visibility-into-your-security-posture"></a>Verschaffen Sie sich eine Sichtbarkeit in ihrer Sicherheitsposition

Um Ihnen die Informationen zu erleichtern, die Sie schneller benötigen, sind Microsoft-Verbesserungs Aktionen in Gruppen gegliedert:

* Identität (Azure Ad Konten #a0 Rollen, wobei Azure ATP in Kürze verfügbar ist)
* Data (Microsoft Information Protection)
* Gerät (Microsoft Defender ATP-Geräte)
* App (e-Mail-und Cloud-apps, einschließlich Office 365 und Microsoft Cloud-App-Sicherheit)
* Infrastruktur (Azure-Ressourcen)

Auf der Microsoft Secure Score-Übersichtsseite können Sie sehen, wie Punkte zwischen diesen Gruppen aufgeteilt werden und welche Punkte verfügbar sind. Auf der Übersichtsseite erhalten Sie außerdem eine Übersicht über die Gesamtpunktzahl, die Verlaufs Entwicklung ihrer sicheren Partitur mit Benchmark-Vergleichen sowie priorisierte Verbesserungs Aktionen, die zur Verbesserung der Bewertung durchgeführt werden können.

![Secure Score Homepage](../media/secure-score/secure-score-homepage.png)
*Abbildung 1: Übersicht über die Microsoft Secure Scores-Seite*

## <a name="take-action-to-improve-your-score"></a>Durchführen von Aktionen zur Verbesserung der Punktzahl

Auf der Registerkarte Verbesserungs Aktionen werden die Sicherheitsempfehlungen für mögliche Angriffs Oberflächen sowie deren Status (abgeschlossen, geplant, Risiko akzeptiert, Drittanbieter und Adresse) aufgeführt. Sie können alle Verbesserungs Aktionen durchsuchen, Filtern und gruppieren.  

### <a name="ranking"></a>Ranking

Die Rangfolge basiert auf der Anzahl der verbleibenden Punkte, die zum Erreichen der Implementierungs Schwierigkeit, der Benutzer Auswirkungen und der Komplexität übrig bleiben. Die am höchsten bewerteten Verbesserungs Aktionen weisen eine große Anzahl von Punkten auf, die mit geringer Schwierigkeit, Benutzer Auswirkungen und Komplexität verbleiben.

### <a name="actions"></a>Aktionen

Wenn Sie eine bestimmte Verbesserungs Aktion auswählen, wird ein ganzseitiges Flyout angezeigt.  

![Verbesserungs Aktion-](../media/secure-score/secure-score-improvement-action.png)
Flyout-Beispiel*Abbildung 2: Beispiel für ein Verbesserungs Aktion-Flyout*

Um die Aktion abzuschließen, haben Sie einige Optionen:

* Wählen Sie **Verwalten** aus, um den Konfigurationsbildschirm zu wechseln und die Änderung vorzunehmen. Sie erhalten dann die Punkte, die die Aktion Wert ist, sichtbar in der ausfliegen. Die Aktualisierung der Punkte dauert im Allgemeinen ungefähr 24 Stunden.

* Wählen Sie **Freigeben** aus, um den direkten Link zur Verbesserungs Aktion zu kopieren, oder wählen Sie die Plattform aus, um den Link wie e-Mail, Microsoft Teams, Microsoft Planner oder ServiceNow freizugeben. Wenn Sie ServiceNow auswählen, können Sie ein Änderungs Ticket erstellen, das in ServiceNow und im Microsoft 365 Security Center Home angezeigt wird. Weitere Informationen finden Sie unter [Microsoft 365 Security Center und ServiceNow-Integration](tickets.md).

* Wählen Sie **Status und Notizen bearbeiten** aus, um manuelle Status oder Notizen für die Verbesserungs Aktionen zu bearbeiten. Sie können nach den Status in der Registerkarte Verbesserungs Aktionen filtern oder gruppieren. Die folgenden Statuen können ausgewählt werden:

    * **To Address** – Sie erkennen, dass die Verbesserungs Aktion erforderlich ist, und planen, diese zu einem späteren Zeitpunkt zu beheben. Dieser Status gilt auch für Aktionen, die als partiell erkannt, jedoch nicht vollständig abgeschlossen werden.
    * **Geplant** – es sind konkrete Pläne vorhanden, um die Verbesserungs Aktion abzuschließen.
    * **Risiko akzeptiert** : Sicherheit sollte immer mit Benutzerfreundlichkeit abgeglichen werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung. Wenn dies der Fall ist, können Sie das Risiko oder das verbleibende Risiko akzeptieren und die Verbesserungs Aktion nicht verabschieden. Sie erhalten keine Punkte, aber die Aktion wird in der Liste der Verbesserungs Aktionen nicht mehr angezeigt. Sie können diese Aktion im Verlauf anzeigen oder jederzeit wieder rückgängig machen.
    * **Durch Drittanbieter beheben** – die Verbesserungs Aktion wurde bereits von einer Drittanbieteranwendung oder-Software behoben. Sie erhalten die Punkte, die die Aktion Wert ist, sodass Ihre Punktzahl besser Ihre gesamte Sicherheitsposition widerspiegelt. Wenn ein Drittanbieter das Steuerelement nicht mehr abdeckt, können Sie einen anderen Status auswählen. Bitte beachten Sie, dass Microsoft keine Sichtbarkeit in die Vollständigkeit der Implementierung hat, wenn die Verbesserungs Aktion als aufgelöst durch einen Drittanbieter gekennzeichnet ist.

### <a name="prerequisites"></a>Voraussetzungen

In den Voraussetzungen im Abschnitt Implementierung werden alle Lizenzen aufgeführt, die abgerufen werden müssen, oder Aktionen, die ausgeführt werden müssen, bevor die Verbesserungs Aktion behandelt wird. Stellen Sie sicher, dass Sie über genügend Sitze in Ihrer Lizenz verfügen, um die Verbesserungs Aktion abzuschließen, und dass diese Lizenzen auf die erforderlichen Benutzer angewendet werden.  

## <a name="track-your-score-history-and-meet-goals"></a>Verfolgen des Ergebnis Verlaufs und erreichen der Ziele

Auf der Registerkarte **Verlauf** können Sie ein Diagramm der Bewertung Ihrer Organisation über einen Zeitraum anzeigen. unter dem Graphen befindet sich eine Liste aller Aktionen, die im ausgewählten Zeitbereich und deren Attributen durchgeführt werden, beispielsweise Ergebnis Punkte und Kategorie. Sie können einen Datumsbereich anpassen und nach Kategorie filtern.

Auf der Registerkarte **Metriken #a0 Trends** gibt es mehrere Diagramme und Diagramme, die Ihnen mehr Einblick in Trends geben und Ziele festlegen. Sie können den Datumsbereich für die gesamte Visualisierungs Seite festlegen. Die Visualisierungen umfassen Folgendes:

* **Ihre Secure Score Zone** – angepasst basierend auf den Zielen und Definitionen Ihrer Organisation für gute, ordnungsgemäße und ungültige Bewertungsbereiche.
* **Regressions Trend** – eine Zeitskala mit Punkten, die aufgrund von Konfigurations-, Benutzer-oder Geräteänderungen zurückgegangen sind.  
* **Vergleichs Trend** : wie das sichere Ergebnis Ihrer Organisation im Laufe der Zeit mit anderen verglichen wird. Diese Ansicht kann Zeilen enthalten, die den Notendurchschnitt von Organisationen mit ähnlicher Anzahl von sitzen und eine benutzerdefinierte Vergleichsansicht darstellen, die Sie festlegen können.
* **Trend zur Risikoakzeptanz** – Zeitskala der Verbesserungs Aktionen, die als "Risiko akzeptiert" gekennzeichnet sind.
* **Ergebnisänderungen** : Anzahl der erreichten Punkte, zurückgegebene Punkte oder neue hinzugefügte Aktionen zusammen mit der nachfolgenden Ergebnis Änderung im angegebenen Datumsbereich.

## <a name="risk-awareness"></a>Risikobewusstsein

Microsoft Secure Score ist eine numerische Zusammenfassung Ihrer Sicherheitsposition basierend auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsbezogenen Messungen. Es ist keine absolute Maßeinheit dafür, wie wahrscheinlich ein System oder Daten verletzt werden. Sie stellt vielmehr das Ausmaß dar, in dem Sie Sicherheitssteuerelemente in Ihrer Microsoft-Umgebung übernommen haben, wodurch das Risiko eines Sicherheits übertretungs ausgeglichen werden kann. Kein Onlinedienst ist vollständig gegen Sicherheitsverletzungen geschützt, und die sichere Bewertung sollte nicht als Garantie gegen Sicherheitsverletzungen in irgendeiner Weise interpretiert werden.

## <a name="whats-new"></a>Was ist neu? 

Um Microsoft Secure Score zu einem besseren Vertreter ihrer Sicherheitsposition zu machen und die Benutzerfreundlichkeit zu verbessern, haben wir einige Änderungen vorgenommen. Ihre Punktzahl und die maximal mögliche Punktzahl haben sich geändert. Dies impliziert jedoch keine Änderung ihrer Sicherheitsposition.

### <a name="updated-interface-and-functionality"></a>Aktualisierte Benutzeroberfläche und Funktionalität

* Alle neuen Metriken und Trends-Ansichten für ciso-und Lead-Level-Diskussionen
* Neue Möglichkeiten zum Nachverfolgen und benchmarken Ihrer Partitur
* Bessere Nachverfolgung und Verständnis für Ergebnis Regressionen
* Filtern, markieren, suchen und Gruppieren von Verbesserungs Aktionen
* Verwalten Ihrer zukünftigen Ziele mithilfe von Bewertungs Projektionen und geplanten Aktionen
* Und vieles mehr!

### <a name="removed-not-scored-and-review-improvement-actions"></a>Verbesserungs Aktionen "nicht bewertet" und "überprüfen" entfernt

Eines der Prinzipien von Secure Score ist, dass die Bewertung standardisiert und leicht zu beziehen ist. Durch Verbesserungs Aktionen, die nicht messbar oder handlungsbereit sind, wurde eine Verwechslung verursacht. Ein sicheres Ergebnis von Microsoft ist nur dann sinnvoll, wenn jede Empfehlung einen klaren Effekt auf die Bewertung haben kann. Nicht bewertete Verbesserungs Aktionen sind nicht messbar, und Überprüfungs Verbesserungs Aktionen werden nicht auf den gleichen Standard wie andere Verbesserungs Aktionen gemessen.

Aus diesen Gründen wurden alle Verbesserungs Aktionen vorübergehend entfernt, die nicht bewertet oder eine Überarbeitungs Kadenz erforderlich waren. Ihrerseits ist keine Aktion erforderlich.

### <a name="simplification-of-the-point-system"></a>Vereinfachung des Punktesystems

Um Punkte über mehrere Erfahrungen hinweg zu standardisieren, wurden alle Aktionspunkte für eine sichere Ergebnisverbesserung auf 10 oder mehr Punkte aktualisiert. Es ist erforderlich, dass die gesamte Breite Verschnaufpause von Sicherheitskontrollen konsistenter ist, die wir heute haben, und diejenigen, die wir in Zukunft hinzufügen werden. Dies ist zwar eine wesentliche Änderung, und es wird eine Verringerung der Gesamtzahl der Punkte angezeigt, aber ihre Sicherheitsposition wird nicht geändert.

## <a name="we-want-to-hear-from-you"></a>Wir möchten von Ihnen hören

Wenn Sie Probleme haben, lassen Sie es uns bitte wissen, indem Sie in der [Sicherheits-, Datenschutz-#a0 Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) -Community veröffentlichen. Wir überwachen die Community und helfen Ihnen dabei.
