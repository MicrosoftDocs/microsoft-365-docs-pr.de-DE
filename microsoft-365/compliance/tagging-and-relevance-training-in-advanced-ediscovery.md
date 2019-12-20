---
title: Tagging und Relevanz Training in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
description: 'Erfahren Sie mehr über die Schritte zum Markieren und arbeiten Sie dann mit einem Schulungs Beispiel mit 40 Dateien während der Relevanz-Schulungsphase von Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: e214e8a8edba7472f93274f3a4f7a06a09e2a801
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802698"
---
# <a name="tagging-and-relevance-training-in-office-365-advanced-ediscovery"></a>Tagging und Relevanz Training in Office 365 Advanced eDiscovery

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In diesem Thema wird das Verfahren zum Arbeiten mit dem Modul "Advanced eDiscovery Relevanz Training" beschrieben. 
  
Nachdem die Bewertung in Advanced eDiscovery abgeschlossen wurde und Sie die Relevanz-Schulungsphase eingeben, wird ein Schulungs Beispiel mit 40-Dateien in die Tag-Registerkarte für die Markierung von Tags gebracht. 
  
## <a name="performing-relevance-training"></a>Durchführen von Relevanz-Schulungen

1. Auf der Registerkarte **relevanztag \> ** wird der Bereich Tagging standardmäßig im linken Bereich angezeigt, und die Beispieldateien werden jeweils einzeln für die Markierung angezeigt. 
    
    ![Bereich "Relevanz-Tag"](media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    Auf der Registerkarte **Tag** wird der Anzeigename der Datei angezeigt. Hierbei kann es sich um den Pfad, den e-Mail-Betreff, den Titel oder den benutzerdefinierten Namen handeln. Die ID, der Dateipfad oder der Textpfad können kopiert werden, indem Sie mit der rechten Maustaste auf den Pfad der Datei klicken. 
    
    Die Kennzeichnung der **Tags** -Registerkarten Statistik zeigt die Datei Beispiel Nummer (oben im linken Bereich), die Nummer der aktuell angezeigten Datei aus den Gesamtdateien im Beispiel (unten im rechten Bereich) und die aktuelle Gesamtzahl der getaggten Dateien im Beispiel (unten im linken Bereich) an, die sich beim Markieren von Dateien ändert. Dies gilt für alle durchgeführten Relevanz-Markierungen, sei es bei der Bewertung, Schulung, Aufholjagd oder Test. 
    
    Symbole, die das vorhanden sein von Kommentaren, Tags und Familiendateien angeben, werden in der Datei Ansicht in einer Leiste oberhalb der Datei angezeigt.
    
2. Ermitteln Sie die Relevanz der Datei für das Fall Problem, und markieren Sie die Datei mit den Symbolschaltflächen für die Markierungsoption oder mit den Tastenkombinationen, wie in der folgenden Tabelle dargestellt:

|**Tagging-Option**|**Beschreibung**|**Tastenkombination**|**Für mehrere Probleme – Tastenkombination für Massen Tags**|
|-----|-----|-----|-----|
|R  <br/> |Relevanten  <br/> |Z  <br/> |UMSCHALT + Z  <br/> |
|Nr  <br/> |Nicht relevant  <br/> |X  <br/> |UMSCHALT + X  <br/> |
|Überspringen  <br/> |Überspringen  <br/> |C  <br/> |UMSCHALT + A  <br/> |
   
  - Wenn mehrere Probleme für eine Datei vorhanden sind, wird die Auswahl nach der Kennzeichnung eines Problems zum nächsten Problem (sofern vorhanden) verschoben. 
    
  - Schlüsselwörter, die vom Administrator oder Fall-Manager beim Hervorheben von Stichwörtern definiert \> wurden (Relevanz-Setup markierte Schlüsselwörter), werden (in bestimmten Farben) angezeigt, um relevante Dateien beim Tagging zu identifizieren. Wenn ein Schlüsselwort doppelt unterstrichen ist, kann auf dieses geklickt werden, um einen QuickInfo mit der Beschreibung des Schlüsselwortes anzuzeigen. 
    
    Klicken Sie optional auf der Registerkarte **Tag** auf **Tag-Einstellungen** , um die folgenden Optionen festzulegen: 
    
    ![Relevanz-Tag-Einstellungen](media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
  - **Massentag**: Verwenden Sie diese Option, um mehrere Probleme für eine Datei zuzuweisen, indem Sie **alle** auswählen, um das Tag für die ausgewählte Datei für alle Probleme (Überschreibt bereits markierte Probleme) festzulegen, oder indem Sie **den Rest** auswählen, um das Tag auf die verbleibenden nicht markierten Probleme anzuwenden. Die ausgewählte Option bleibt für alle Fälle dieses Benutzers gültig, bis Sie von diesem Benutzer geändert wird (Einstellung ist pro Benutzer für alle Fälle des Benutzers). 
    
  - **Auto-Tag**: Aktivieren Sie dieses Kontrollkästchen, um andere Probleme für eine Datei nach einem einzelnen relevanten Tagging als nicht relevant festzulegen.
    
  - **Auto Advance**: Aktivieren Sie dieses Kontrollkästchen, um die angezeigte Dateiauswahl in die nächste Datei zu verlagern, wenn Sie das letzte oder nur unmarkierte Problem markieren. 
    
    Übersprungene Dateien werden nicht für Relevanz Training und Relevanz Scoring Zwecke berücksichtigt.
    
3. Freitextkommentare, die einer Datei zugeordnet sind, können über die Option **Kommentar** in der Dropdownliste im linken Bereich angezeigt und bearbeitet werden. (optional) 
    
4. Richtlinien für die Markierung können angezeigt werden, indem Sie in der Dropdownliste Linker Bereich die Option **Markierungs Richtlinien** auswählen. 
    
5. Nachdem Sie die Markierung aller Dateien in der Liste abgeschlossen haben und die Ergebnisse berechnen können, klicken Sie auf **berechnen**. Die Registerkarte **Track** wird angezeigt. 
    
## <a name="working-with-the-sample-files-list"></a>Arbeiten mit der Liste "Beispieldateien"

In der Liste mit den Beispieldateien können Sie eine Liste der Dateien in einem Schulungs Beispiel anzeigen und verschiedene Aktionen für eine oder mehrere Dateien durchführen. Auf der Registerkarte " **Relevanz** \> - **Tag** " wird im linken Bereich " **Sample Files** " eine Liste der Beispieldateien zur Verarbeitung mit den Prozessen "Assessment", "Training", "Catch-up" und "Inkonsistenzen" angezeigt. 
  
1. Wählen Sie auf der Registerkarte **Relevanz \> -Tag** die Beispieldateien in der Dropdownliste Linker Bereich aus. Die Beispieldateien werden im linken Bereich aufgelistet. 
    
    ![Liste mit Relevanz-Tag-Beispieldateien](media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. Wählen Sie eine bestimmte Stichprobe oder Dateinummer aus, indem Sie die entsprechende Nummer in den Feldern **Sample** oder **File** eingeben oder auswählen. 
    
  -   - In der linken Spalte der Liste angezeigter Dateien auf der Registerkarte **Tag** wird eine Dateisequenz Nummer aufgeführt. Durch Klicken auf die Kopfzeile kehrt die ursprüngliche Reihenfolge der Dateien in die ursprüngliche Reihenfolge zurück. 
    
  - Durch Klicken auf eine Datei Zeile wird der Inhalt im rechten Bereich angezeigt.
    
  - Navigieren zwischen Dateien im aktuellen Beispiel mithilfe der untergeordneten Menüleistenoptionen. Darüber hinaus stehen Navigationstasten Kombinationen zur Verfügung:
    
    So navigieren Sie zur ersten Datei im Beispiel: UMSCHALT + STRG +\<
    
    So navigieren Sie zur vorherigen Datei im Beispiel: UMSCHALT +\<
    
    So navigieren Sie zur nächsten Datei im Beispiel: UMSCHALT +\>
    
    So navigieren Sie zur letzten Datei im Beispiel: UMSCHALT + STRG +\>
    
## <a name="see-also"></a>Siehe auch

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Grundlegendes zur Relevanz der Bewertung](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging und Bewertung](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Analyse der nach Verfolgungs Relevanz](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Entscheidung basierend auf den Ergebnissen](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testen der Relevanz-Analyse](test-relevance-analysis-in-advanced-ediscovery.md)

