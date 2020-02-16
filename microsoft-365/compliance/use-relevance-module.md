---
title: Verwenden des Moduls "Relevanz" zum Analysieren von Daten in Evidence
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 0b6c42f594ef10c868051d81b0a7ea4b7ff84e00
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080612"
---
# <a name="use-the-relevance-module-to-analyze-data-in-evidence"></a>Verwenden des Moduls "Relevanz" zum Analysieren von Daten in Evidence

In Data Investigations (Preview) enthält das Modul Relevanz die Relevanz Schulung und Überprüfung von Dateien im Zusammenhang mit einer Untersuchung. Der Relevanz-Workflow wird wie folgt dargestellt und beschrieben:
  
![Relevanz-Workflow](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **Zyklen der Bewertung und Nachverfolgung**:
    
  - **Bewertung**: ermöglicht eine frühe Bewertung basierend auf einer zufälligen Stichprobe von Dateien und verwendet diese Bewertung, um Entscheidungen zu treffen, um die Leistung des vorhersagbaren Codierungsprozesses zu bestimmen. 
    
  - **Track**: berechnen und Anzeigen von vorläufigen Ergebnissen der Bewertung bei gleichzeitiger Überwachung der statistischen Gültigkeit des Prozesses. 
    
- **Trainingszyklen und Nachverfolgung**
    
  - **Tag**: Data Investigations (Preview) erlernt Relevanz-Kriterien für jedes Problem, basierend auf der iterativen Überprüfung und Markierung der einzelnen Dateien durch den Experten.
    
  - **Track**: berechnen und Anzeigen von Zwischenergebnissen der Relevanz-Schulung bei gleichzeitiger Überwachung der statistischen Gültigkeit des Prozesses. 
    
- **Batch Berechnung**: die akkumulierten und gelernten Relevanz-Kriterien werden auf die gesamte Dateisammlung angewendet, und für jede Datei wird ein Relevanz-Score generiert.
    
- **Entscheidung**: die Ergebnisse der Analyse, die auf den gesamten Fall angewendet werden, werden nach der Batch Berechnung angezeigt, und es werden Daten angezeigt, mit denen die Dokument Überprüfungs Entscheidungen getroffen werden.
    
- **Test**: Ergebnisse können getestet werden, um die Gültigkeit und Effektivität der Verarbeitung von Daten Untersuchungen (Preview) zu überprüfen.

- **Suche**: Wenn Sie den Relevanz-Workflow abgeschlossen haben, können Sie die Ausgabe wie etwa das Quantil eines Dokuments für Ihr Problem verwenden, wenn Sie eine Abfrage innerhalb Ihres Arbeitssatzes ausführen.
    
## <a name="guidelines-for-relevance-training-and-review"></a>Richtlinien für die Relevanz-Schulung und-Prüfung

Im folgenden finden Sie eine Übersicht über Richtlinien für die Relevanz-Schulung und-Überprüfung:
  
- **Fehler und Inkonsistenzen**: Wenn Markierungsfehler während des Trainings vorgenommen werden, kehren Sie zu vorherigen Datei Beispielen zurück, um Sie zu korrigieren. Wenn zu viele Fehler zu korrigieren sind oder eine neue Perspektive für den Fall oder das Problem vorliegt, sollten die Relevanz-Kriterien vom Administrator neu definiert werden, und die Relevanz-Schulung wurde neu gestartet.
    
- **Tagging und Schulung**: 
    
  - Dateien sollten nur auf der Grundlage von Inhalt gekennzeichnet werden. Metadaten wie Depot, Datum oder Dateipfad werden nicht als solche betrachtet. 
    
  - Berücksichtigen Sie keine Datumsbereichs Angaben im Text beim Markieren von Dateien.
    
  - Berücksichtigen Sie beim Markieren von Dateien keine eingebetteten grafischen Bilder.
     
  - Auf Relevanz angewendeter Text ignorieren wird im angezeigten Dateiinhalt in der Textansicht relevant entfernt. Wenn die Werte für Ignore Text nach dem bereits begonnenen Relevanz Training definiert wurden, wird der neue ignorierte Text auf Beispieldateien angewendet, die an dem Ort erstellt wurden, an dem er definiert wurde. Das Feature Text ignorieren sollte vorsichtig verwendet werden, da die Leistung der Dateianalyse durch die Verwendung reduziert werden kann.
    
  - Verwenden Sie die Option " **Tagging überspringen** " nur, wenn dies erforderlich ist. Daten Untersuchungen (Vorschau) werden nicht basierend auf übersprungenen Dateien trainiert. Wenn es schwierig ist, festzustellen, ob eine Datei relevant ist, ist es besser, nach Möglichkeit als relevant (n) oder nicht relevant (Nr) zu markieren, anstatt **Skip**auszuwählen. Wenn Daten Untersuchungen (Preview) das Training auswerten, kann man dann sehen, wie gut diese Dateitypen verarbeitet wurden.
    
  - Selbst Dateien mit einer sehr kleinen Menge extrahierten Texts sollten im Training als R/Nr und nicht als "Skip" markiert werden, wenn möglich. 
    
  - Tagging kann sich auf die Klassifizierung auswirken, solange die Datei lesbar ist und als R/Nr gekennzeichnet werden kann.
    
  - Die Dateisequenz Nummer in der Liste der angezeigten Beispieldateien auf der Registerkarte **Tag** ermöglicht es dem Benutzer, zur ursprünglichen angezeigten Reihenfolge der Dateien zurückzukehren. 
    
  - Sie können zu einem beliebigen Beispiel zurückkehren und die Kennzeichnung der Bewertungs-und Schulungs Mappen-Dateien ändern. Die Änderungen werden angewendet, wenn das nächste Beispiel erstellt wird.
    
  - Gescannte Excel-Dateien im PDF-Format sollten beim Markieren von Dateien identisch mit systemeigenen Excel-Dateien behandelt werden.
    
  - Wenn Sie in Bezug auf die Relevanz der Kennzeichnung einer Datei Zweifel haben, wenden Sie sich an einen Experten. Falsche Kennzeichnung während des Relevanz-Trainings kann zu einem späteren Zeitpunkt des Prozesses zu einem Zeitverlust führen und kann sich auch negativ auf die Qualität der Gesamtergebnisse auswirken.
    
  - Schlüsselwörter, die in Stichwortlisten definiert wurden, werden in Farben angezeigt, damit der Benutzer relevante Dateien beim Tagging identifizieren kann.
    
- **Batch Berechnung**: Dateien, die vom Experten als R/Nr markiert wurden, erhalten eine Punktzahl von 0 oder 100. Dies gilt für Tagging, das vor der Batch Berechnung erstellt wurde. Wenn der Experte das Problem nach der Batch Berechnung in den Leerlauf umgeschaltet und das Problem fortgesetzt hat, werden die neu markierten Ergebnisse nicht 100/0, sondern die ursprüngliche Punktzahl sein.
    
- **Probleme und Samplingmodus**: Probleme werden normalerweise deaktiviert, wenn die Arbeit an Ihnen abgeschlossen ist (Relevanz-Training wird stabilisiert und Batch Berechnung wurde durchgeführt), wenn die Probleme abgebrochen werden oder wenn ein anderer Benutzer an den Problemen arbeitet.
    
## <a name="steps-in-relevance-training"></a>Schritte zur Relevanz-Schulung

Auf der Registerkarte **relevanzstatus \> ** werden mit den folgenden nächsten Schritten Empfehlungen zur Vorgehensweise bei der Verarbeitung von Daten Untersuchungen bereitgestellt. Die Auswirkungen werden im folgenden beschrieben, wenn jeder der folgenden Schritte im Relevanz-Schulungsprozess empfohlen wird. 
  
- Tagging/Continue Tagging: Dateiüberprüfung und Relevanz-Tagging, die von einem Experten für jede Datei und jedes Problem in einem Beispiel ausgeführt werden.
    
  - Implikation: ein vorhandenes Beispiel muss markiert werden.
    
- Assessment/Continue Assessment: ermöglicht frühzeitiges Überprüfen der Fall Ausgabe Relevanz und eine vorläufige Ansicht der Relevanz der für den aktuellen Fall importierten Datei Auffüllung.
    
  - Implikation: Es ist eine weitere Bewertung erforderlich oder empfehlenswert.
    
- Schulung/Fortsetzung der Schulung: Prozess, in dem Daten Untersuchungen von dem Experten erlernt werden, der die Dateibeispiele kennzeichnen kann, und die Fähigkeit erlangt, relevante Kriterien für jedes Problem im Kontext jedes Einzelfalls zu identifizieren.
    
  - Implikation: das Problem erfordert mehr Schulung; Das nächste Beispiel sollte erstellt und markiert werden. 
    
- Batch Berechnung: relevanzprozess, bei dem Daten Untersuchungen das erworbene Wissen während der Schulungsphase erwerben und auf die gesamte Datei Auffüllung anwenden. Alle Dateien in der entsprechenden Dateigruppe werden auf Relevanz ausgewertet und einem Relevanz-Score zugeordnet.
    
  - Implikation: das Problem wurde stabilisiert, und die Batch Berechnung kann ausgeführt werden.
    
- Catch-up: Relevanz gibt an, wann ein Experte ein Beispiel für Dateien prüft und kennzeichnet, die aus einer zusätzlichen Datei Auslastung während eines Szenarios mit Rollen Lasten ausgewählt wurden.
    
  - Implikation: eine neue Last wurde hinzugefügt, und Nachholbedarf ist erforderlich, um die Arbeit fortzusetzen.
    
- Tag Inkonsistenzen: Prozess identifiziert über einen Algorithmus für Daten Untersuchungen Inkonsistenzen im Datei Kennzeichnungs Prozess, die sich möglicherweise negativ auf die Analyse auswirken.
    
  - Implikation: das nächste Beispiel enthält Dateien, die in vorherigen Beispielen markiert wurden, und ihre Kennzeichnung muss erneut ausgeführt werden.
    
- Update Klassifizierung: ermöglicht dem Benutzer das Anwenden von Markierungen oder Seeding Änderungen.
    
  - Implikation: das Tagging und das Seeding können geändert werden, ohne dass ein weiteres Relevanz-Beispiel manuell ausgeführt werden muss.
    
- In der Warteschleife: der Relevanz-Schulungsprozess ist abgeschlossen.
    
  - Implikation: an dieser Position ist keine Relevanz-Schulung erforderlich.
    
Obwohl Daten Untersuchungen Sie durch den Prozess führen, mit empfohlenen nächsten Schritten in verschiedenen Phasen, können Sie auch zwischen Registerkarten und Seiten navigieren und Entscheidungen treffen, um Situationen zu beheben, die für den jeweiligen Fall, das Problem oder Dokument Überprüfungsprozess. 
  
Es ist möglich, Daten Untersuchungen im nächsten Schritt zur Verarbeitung von Optionen zu akzeptieren oder außer Kraft zu setzen. Wenn Sie einen anderen Schritt als den empfohlenen nächsten Schritt durchführen möchten, klicken Sie auf den **nächsten Schritt** , der in der erweiterten Problemanzeige im Dialogfeld aufgeführt ist, klicken Sie neben dem nächsten Schritt auf die Schaltfläche **ändern** , und wählen Sie eine andere Option für nächsten Schritt aus. 
  
> [!NOTE]
> Einige Optionen bleiben nach dem entsperren möglicherweise deaktiviert, da Sie für die Verwendung zu diesem Zeitpunkt im Prozess nicht unterstützt werden. 
  
## <a name="more-information"></a>Weitere Informationen

[Grundlegendes zur Relevanz der Bewertung](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging und Bewertung](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Tagging und Relevanz Training](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Analyse der nach Verfolgungs Relevanz](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Entscheidung basierend auf den Ergebnissen](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testen der Relevanz-Analyse](test-relevance-analysis-in-advanced-ediscovery.md)

[Abfragen der Daten in Evidence](evidence-query.md)
