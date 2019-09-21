---
title: Option Text ignorieren festlegen für Analyse in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: 'Erfahren Sie, wie Sie die Regel definieren, um bestimmten Text zu ignorieren, wenn Sie die Analyse-und Prozessmodule in Office 365 Advanced eDiscovery verwenden.  '
ms.openlocfilehash: 70d9879f1cb6b3def06ff978fc2f7fa8f20a92f0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082173"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a>Option Text ignorieren festlegen für Analyse in Office 365 Advanced eDiscovery

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Das Feature Text ignorieren kann auf alle oder alle der folgenden erweiterten eDiscovery-Module angewendet werden: analysieren (nahe Duplikate, e-Mail-Threads, Designs) und Relevanz. Der ignorierte Text wird nicht in den für Relevanz angezeigten Dateien angezeigt, und die Analyse/Berechnungen verwerfen den ignorierten Text.
  
Wenn das Feature Text ignorieren zuvor für Module definiert wurde, die bereits ausgeführt wurden, wird die Einstellung Text ignorieren jetzt vor der Änderung geschützt. Die Funktion Text ignorieren für das Modul Relevanz kann jedoch jederzeit noch geändert werden.
  
## <a name="how-ignore-text-filters-are-applied"></a>Wie ignorieren von Text Filtern angewendet wird

Mehrere Text Filter ignorieren werden in der Reihenfolge angewendet, in der Sie eingegeben wurden. Um die Reihenfolge zu ändern, in der Sie angewendet werden, müssen Sie gelöscht und in der gewünschten Reihenfolge erneut eingegeben werden.
  
Wenn es sich beispielsweise um den Textinhalt handelt: "Dave Bob Alice Carol Eve", im folgenden finden Sie Beispiele für Ignore-Texteinträge und die Ergebnisse:
  
||||
|:-----|:-----|:-----|
|**Text Einträge ignorieren** <br/> |**==\>** <br/> |**Ergebnisse** <br/> |
|"Alice", "Bob Carol"  <br/> |==\>  <br/> |"Dave Eve"  <br/> |
|"Alice", "Bob Alice Carol"  <br/> |==\>  <br/> |"Dave Bob Carol Eve"  <br/> |
   
Der zweite Ignore-Texteintrag ist nicht implementiert, da die Zeichenfolge nicht als solches gefunden wird, nachdem der erste Text ignoriert wurde.
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a>Verwenden regulärer Ausdrücke beim Definieren von Text ignorieren

Reguläre Ausdrücke werden für die Verwendung beim Definieren von Ignore-Text unterstützt. Im folgenden finden Sie Beispiele für Syntax und Verwendung von regulären Ausdrücken:
  
- So entfernen Sie Text von Anfang bis zum Ende einer Zeile (ignorieren):
    
     `Begin(.*)$`
    
    wobei "BEGIN" das erste Vorkommen dieser Zeichenfolge in der Linie ist.
    
    Beispielsweise für den folgenden Text:
    
    **"Dies ist der erste Satz und die erste Textreihe.**
    
    **Dies ist der zweite Satz und die zweite Reihe "**
    
    der reguläre Ausdruck zuerst (.\*) $ führt zu:
    
    **"Dies ist**
    
    **Dies ist der zweite Satz und die zweite Reihe "**
    
- So entfernen Sie Haftungsausschlüsse und rechtliche Anweisungen, die am Ende der e-Mail-Threads automatisch eingefügt werden:
    
     `Begin(.|\s)*End`
    
    wobei "BEGIN" und "End" eindeutige Zeichenfolgen am Anfang und am Ende eines umgebrochenen Textabsatzes sind. 
    
    Beispielsweise werden im folgenden regulären Ausdruck Haftungsausschlüsse und rechtliche Anweisungen entfernt, die sich im e-Mail-Thread zwischen den Zeichenfolgen BEGIN und End befanden:
    
    **Diese Nachricht enthält vertrauliche Informationen (. | \s)\*wenn eine Überprüfung erforderlich ist, fordern Sie eine Hardcopy-Version an.**
    
- So entfernen Sie einen Haftungsausschluss (einschließlich Sonderzeichen): 
    
    Beispielsweise für den folgenden Text (mit dem Haftungsausschluss, der hier von x dargestellt wird): 
    
    **/\*\ Diese Nachricht enthält vertrauliche Informationen. xxxx xxxx**
    
    **xxxx xxxx xxxx xxxx xxxx xxxx xxxx**
    
    **xxxx xxxx wenn eine Überprüfung erforderlich ist, fordern Sie bitte eine Hardcopy-Version an. /\*\**
    
    der reguläre Ausdruck zum Entfernen des obigen Haftungsausschlusses sollte wie folgt aussehen: 
    
    **\/\\*\\Diese Nachricht enthält vertrauliche\.Informationen (. | \s)\* wenn eine Überprüfung erforderlich ist, fordern Sie eine Hardcopy\. -Version an.\/\\*\\**
    
- Regeln für reguläre Ausdrücke:
    
  - Alle Zeichen, die nicht Teil des Alphabets sind, mit Ausnahme von Leerzeichen, "_" und "-" muss vorangestellt werden\".
    
  - Das reguläre eExpression-Feld kann unbegrenzte Länge aufweisen.
    
> [!TIP]
> Eine Erklärung und ausführliche Syntax für reguläre Ausdrücke finden Sie unter: [Regular Expression Language-Quick Reference](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx). 
  
## <a name="define-ignore-text-rule"></a>Definieren von Ignore-Text Regel

1. Klicken Sie auf der Registerkarte **analysiere \> \> Analyseoptionen verwalten** im Abschnitt **Text ignorieren** auf **+** das Symbol, um eine Regel hinzuzufügen. 
    
2. Geben Sie im Dialogfeld **Text ignorieren hinzufügen** in das Feld **Name** einen Namen für die Regel Text ignorieren ein. 
    
    ![Ignorierten Text hinzufügen](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. Geben Sie **in das Textfeld** den zu ignorierenden Text ein. Das Textfeld erlaubt eine unbegrenzte Anzahl von Zeichen. 
    
    > [!TIP]
    > Klicken Sie wie im obigen Fenster gezeigt auf **Glühbirne,** um allgemeine Syntax Richtlinien für die Regel Text ignorieren anzuzeigen. 
  
4. Aktivieren Sie bei Bedarf das Kontrollkästchen **groß** -/Kleinschreibung. 
    
5. Wählen Sie in der Liste **übernehmen für** die erweiterten eDiscovery-Module aus, in denen die Definition angewendet werden soll. 
    
6. Wenn Sie einen Testlauf für Beispieltext ausführen möchten, geben Sie Beispieltext in das **Eingabe** Textfeld ein, und klicken Sie auf **Testen**. Die Ergebnisse werden im Textfeld **Ausgabe** angezeigt. 
    
7. Klicken Sie auf **OK** , um die Regel Text ignorieren zu speichern. Die definierte Regel Ignore Text wird angezeigt. 
    
    ![Ignorierten Textnamen festlegen](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a>Siehe auch

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Grundlegendes zur Dokument Ähnlichkeit](understand-document-similarity-in-advanced-ediscovery.md)
  
[Festlegen von Analyseoptionen](set-analyze-options-in-advanced-ediscovery.md)
  
[Einstellungen für die erweiterte Analyse Einstellung](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Anzeigen von Analyseergebnissen](view-analyze-results-in-advanced-ediscovery.md)

