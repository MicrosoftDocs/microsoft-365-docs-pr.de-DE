---
title: Verwenden Des Relevanzmoduls zum Analysieren von Daten in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Erfahren Sie, wie das Relevanzmodul Daten in Nachweisen mit einer Beschreibung des Relevanzworkflows und der Schulungsschritte in Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286061"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a>Verwenden Des Relevanzmoduls zum Analysieren von Daten in Advanced eDiscovery

In Advanced eDiscovery umfasst das Relevanzmodul die Relevanzschulung und die Überprüfung von Dateien im Zusammenhang mit einem Fall. Um den Relevanzworkflow zu verwenden, wechseln Sie zu Überprüfungssatz in einem Überprüfungssatz verwalten, und klicken Sie auf Relevanz anzeigen. Es gibt einige Schritte, die Sie ausführen müssen, bevor Sie den Workflow starten können:

- Prozess: Jeder dem Überprüfungssatz hinzugefügte Lastensatz wird hier als "Container" gezeigt. Sie müssen diese Dokumente verarbeiten, bevor Sie sie dem Relevanzmodul hinzufügen können. Hier können Sie sie auch als Seed markieren oder für ein bestimmtes Problem vorab markieren.

- Relevanz hinzufügen: Unter Relevanzlasten können Sie Dokumente hinzufügen, die zu Relevanz verarbeitet wurden, um sie für \> Schulungen verfügbar zu machen.

Der Relevanzworkflow wird wie folgt angezeigt und beschrieben:
  
![Relevanzworkflow](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **Bewertungs- und Nachverfolgungszyklen:**
    
  - **Bewertung**: Ermöglicht eine frühzeitige Bewertung basierend auf einer zufälligen Stichprobe von Dateien und verwendet diese Bewertung, um Entscheidungen anzuwenden, um die Leistung des Vorhersagecodierungsprozesses zu bestimmen. 
    
  - **Track**: Berechnen und Anzeigen von Zwischenergebnissen der Bewertung während der Überwachung der statistischen Gültigkeit des Prozesses. 
    
- **Zyklen von Schulungen und Nachverfolgung**
    
  - **Tag**: Advanced eDiscovery die relevanzspezifischen Kriterien für jedes Problem basierend auf der iterativen Überprüfung und Kennzeichnung einzelner Dateien durch den Experten.
    
  - **Track**: Berechnen und Anzeigen von Zwischenergebnissen der Relevanzschulung während der Überwachung der statistischen Gültigkeit des Prozesses. 
    
- **Batchberechnung:** Die kumulierten und gelernten Relevanzkriterien werden auf die gesamte Dateisammlung angewendet, und für jede Datei wird eine Relevanzpunktzahl generiert.
    
- **Entscheidung**: Die Ergebnisse der Analyse, die auf den gesamten Fall angewendet wurde, werden nach der Batchberechnung angezeigt, und Daten, die zum Treffen von Entscheidungen zur Dokumentüberprüfung verwendet werden, werden angezeigt.
    
- **Test:** Die Ergebnisse können getestet werden, um die Gültigkeit und Effektivität der Advanced eDiscovery zu überprüfen.

- **Suche**: Sobald der Relevanzworkflow abgeschlossen ist, können Sie die Ausgabe wie z. B. das Lesen von Perzentil eines Dokuments für Ihr Problem verwenden, wenn Sie eine Abfrage in Ihrem Überprüfungssatz ausführen.
    
## <a name="guidelines-for-relevance-training-and-review"></a>Richtlinien für Relevanzschulungen und -überprüfungen

Im Folgenden finden Sie eine Übersicht über Richtlinien für Relevanzschulungen und -überprüfungen:
  
- **Fehler und Inkonsistenzen:** Wenn während der Schulung Taggingfehler auftreten, kehren Sie zu vorherigen Dateibeispielen zurück, um sie zu korrigieren. Wenn zu viele Fehler zu korrigieren sind oder eine neue Perspektive für den Fall oder das Problem vor liegt, sollten die Relevanzkriterien vom Administrator neu definiert und die Relevanzschulung neu gestartet werden.
    
- **Tagging und Schulungen**: 
    
  - Dateien sollten nur basierend auf Inhalten markiert werden. Berücksichtigen Sie keine Metadaten, z. B. Custodian, Datum oder Dateipfad. 
    
  - Berücksichtigen Sie beim Markieren von Dateien keine Datumsbereichsangaben im Text.
    
  - Berücksichtigen Sie beim Markieren von Dateien keine eingebetteten grafischen Bilder.
     
  - Auf Relevanz angewendeter Text ignorieren wird im angezeigten Dateiinhalt in der Textansicht in Relevanz entfernt. Wenn die Werte für Text ignorieren definiert wurden, nachdem die Relevanzschulung bereits gestartet wurde, wird der neue ignorierte Text auf Beispieldateien angewendet, die an dem Punkt erstellt wurden, an dem er definiert wurde. Das Feature Text ignorieren sollte vorsichtig verwendet werden, da seine Verwendung die Leistung der Dateianalyse beeinträchtigen kann.
    
  - Verwenden Sie **die Option Tagging** überspringen nur bei Bedarf. Advanced eDiscovery wird nicht basierend auf übersprungenen Dateien trainiert. Wenn es schwierig ist, festzustellen, ob eine Datei relevant ist, ist es bei der Bewertung besser, wenn möglich als Relevant (R) oder Nicht relevant (NR) zu kennzeichnen, anstatt Skip zu **wählen.** Wenn Advanced eDiscovery Die Schulung ausgewertet wird, wird dann deutlich, wie gut diese Dateitypen verarbeitet wurden.
    
  - Selbst Dateien mit einer sehr geringen Menge extrahierten Textes sollten in Schulungen als R/NR gekennzeichnet werden, und nicht nach Möglichkeit als "Überspringen". 
    
  - Tagging kann sich auf den Klassifizierungstyp auswirken, solange die Datei lesbar ist und als R/NR gekennzeichnet werden kann.
    
  - Die Dateisequenznummer in der Liste der angezeigten Beispieldateien auf der Registerkarte **Tag** ermöglicht es dem Benutzer, zur ursprünglich angezeigten Reihenfolge der Dateien zurückzukehren. 
    
  - Sie können zu einem beliebigen Beispiel wechseln und die Markierung der Bewertungs- und Schulungssetdateien ändern. Die Änderungen werden beim Erstellen des nächsten Beispiels angewendet.
    
  - Gescannte Excel dateien im PDF-Format sollten beim Markieren von Dateien wie systemeigene Excel behandelt werden.
    
  - Wenn Sie zweifeln hinsichtlich der Relevanztagging einer Datei, wenden Sie sich an einen Experten. Falsche Markierungen während des Relevanztrainings können zu einem späteren Zeitpunkt im Prozess zu Zeit verloren gehen und sich auch negativ auf die Qualität der Gesamtergebnisse auswirken.
    
  - Schlüsselwörter, die in Stichwortlisten definiert wurden, werden in Farben angezeigt, um dem Benutzer zu helfen, relevante Dateien beim Markieren zu identifizieren.
    
- **Batchberechnung:** Dateien, die vom Experten als R/NR gekennzeichnet wurden, erhalten eine Bewertung von 0 oder 100. Dies gilt für Markierungen, die vor der Batchberechnung vorgenommen wurden. Wenn der Experte das Problem nach der Batchberechnung in Leerlauf umgestellt hat und dieses Problem weiterhin taggiert, sind die neu markierten Ergebnisse nicht 100/0, sondern die ursprüngliche Bewertung.
    
- **Probleme und Samplingmodus:** Probleme werden in der Regel deaktiviert, wenn die Arbeit an ihnen abgeschlossen ist (Relevanzschulungen werden stabilisiert und Batchberechnungen durchgeführt), wenn die Probleme abgebrochen werden oder wenn ein anderer Benutzer an den Problemen arbeitet.
    
## <a name="steps-in-relevance-training"></a>Schritte in Relevanzschulungen

Auf der **Registerkarte \> Relevanzspur** enthält Advanced eDiscovery Empfehlungen zum Fortfahren in der Verarbeitung mit den folgenden nächsten Schritten. Die Auswirkungen werden unten beschrieben, wenn jeder der folgenden Schritte im Relevanzschulungsprozess empfohlen wird. 
  
- Tagging/Continue-Tagging: Dateiüberprüfung und Relevanztagging, die von einem Experten für jede Datei und jedes Problem innerhalb eines Beispiels durchgeführt werden.
    
  - Implikationen: Ein vorhandenes Beispiel muss markiert werden.
    
- Bewertung/Fortsetzung der Bewertung: Ermöglicht eine frühzeitige Überprüfung der Relevanz des Fallproblems und eine vorläufige Ansicht der Relevanz der für den aktuellen Fall importierten Dateigesamtheit.
    
  - Implikationen: Es ist eine weitere Bewertung erforderlich oder empfohlen.
    
- Schulung/Weiterbildung: Prozess, bei dem Advanced eDiscovery von dem Experten lernt, der die Dateibeispiele tagt und die Möglichkeit erhält, Relevanzkriterien zu identifizieren, die für jedes Problem im Kontext jedes Falls relevant sind.
    
  - Implikationen: Das Problem benötigt mehr Schulungen; das nächste Beispiel sollte erstellt und markiert werden. 
    
- Batchberechnung: Relevanzprozess, bei dem Advanced eDiscovery das während der Schulung erworbene Wissen aufnimmt und auf die gesamte Dateigesamtheit angewendet wird. Alle Dateien in der relevanten Dateigruppe werden auf Relevanz geprüft und einer Relevanznote zugewiesen.
    
  - Implikationen: Das Problem hat sich stabilisiert, und die Batchberechnung kann durchgeführt werden.
    
- Nachholbedarf: Relevanz gibt an, wann ein Experte ein Beispiel von Dateien überprüft und tagt, die während eines Rolling Loads-Szenarios aus einer zusätzlichen Dateilast ausgewählt wurden.
    
  - Implikationen: Es wurde eine neue Last hinzugefügt, und die Nachholzeit ist erforderlich, um weiter zu arbeiten.
    
- Inkonsistenzen des Tags: Der Prozess identifiziert über einen Advanced eDiscovery-Algorithmus Inkonsistenzen im Dateitaggingprozess, die sich negativ auf die Analyse auswirken können.
    
  - Implikationen: Das nächste Beispiel enthält Dateien, die in vorherigen Beispielen markiert wurden, und deren Markierung muss rückgängig gemacht werden.
    
- Updateklassifikator: Ermöglicht dem Benutzer das Anwenden von Tagging- oder Seedingänderungen.
    
  - Implikationen: Markierungs- und Seedingänderungen können angewendet werden, ohne ein weiteres Relevanzbeispiel manuell ausführen zu müssen.
    
- In Warteschleife: Der Relevanzschulungsprozess ist abgeschlossen.
    
  - Implikationen: Derzeit ist keine Relevanzschulung erforderlich.
    
Obwohl Advanced eDiscovery Sie durch den Prozess führt, können Sie mit empfohlenen Nächsten Schritten in unterschiedlichen Phasen auch zwischen Registerkarten und Seiten navigieren und Entscheidungen treffen, um Situationen zu beheben, die für Ihren individuellen Fall-, Problem- oder Dokumentüberprüfungsprozess relevant sein können. 
  
Es ist möglich, die Auswahlmöglichkeiten für die Advanced eDiscovery nächsten Schritt zu akzeptieren oder außer Kraft zu setzen. Wenn Sie einen anderen Schritt als den empfohlenen  Nächsten Schritt ausführen möchten, klicken Sie  im Dialogfeld auf den nächsten Schritt, der in der erweiterten Problemanzeige aufgeführt ist, klicken Sie auf die Schaltfläche Ändern neben dem nächsten Schritt, und wählen Sie eine weitere Option Nächsten Schritt aus. 
  
> [!NOTE]
> Einige Optionen bleiben nach dem Entsperren möglicherweise deaktiviert, da sie zu diesem Zeitpunkt im Prozess nicht zur Verwendung unterstützt werden. 
  
## <a name="more-information"></a>Weitere Informationen

[Grundlegendes zur Bewertung in Relevanz](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging und Bewertung](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Tagging- und Relevanzschulungen](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Verfolgen der Relevanzanalyse](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Entscheidung basierend auf den Ergebnissen](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testen der Relevanzanalyse](test-relevance-analysis-in-advanced-ediscovery.md)

[Abfragen der Daten in einem Prüfdateisatz](review-set-search.md)
