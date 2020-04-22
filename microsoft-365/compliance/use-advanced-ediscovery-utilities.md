---
title: Verwenden von Advanced eDiscovery-Hilfsprogrammen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 'Erfahren Sie mehr über die Dienstprogramme in Advanced eDiscovery, einschließlich Fallprotokoll, klare Daten, Prozessfehler, Änderung der Relevanz und Transparenz Analyse.  '
ms.openlocfilehash: d4495920110916fdd5b07201d50080605ba177b1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633390"
---
# <a name="use-advanced-ediscovery-classic-utilities"></a>Verwenden von Advanced eDiscovery (Classic)-Hilfsprogrammen

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Die Dienstprogramme, die in Advanced eDiscovery angezeigt und verfügbar sind, hängen von Kontext und Benutzerrollen ab.
  
## <a name="case-log"></a>Fallprotokoll

Das Fallprotokoll enthält eine ausführliche Liste der Anwendungs Verarbeitungsaktivitäten, die für die Nachverfolgung, Problembehandlung und für die Behandlung von Fehlern und Warnungen verwendet werden können. Das Protokoll kann auf dem Host oder Server lokal erstellt und gespeichert oder direkt an eine e-Mail-Adresse gesendet werden.
  
Die Protokolldatei kann auch auf den Clientcomputer heruntergeladen werden. Die Client Download Option ist je nach Konfiguration und Benutzerrolle möglicherweise aktiviert oder deaktiviert.
  
1. Klicken Sie in der Menüleiste auf das **Zahnrad** Symbol. 
    
2. Wählen Sie auf der Registerkarte **Einstellungen und Dienstprogramme \> ** die Option ** \> Case Log Setup**aus.
    
3. Wählen Sie die **Protokollebene** wie folgt aus: 
    
  - **Standard**: enthält die grundlegenden Protokolldaten. Diese Option ist normalerweise für die Überwachung erforderlich und sollte verwendet werden, sofern nichts anderes empfohlen wird.
    
  - **Minimal**: wird für sehr große Fälle verwendet und gibt nur die neuesten Daten zurück.
    
4. Klicken Sie auf **Ausführungs Fallprotokoll**. Das Protokoll wird generiert, und path wird angezeigt. Die Informationen zum Vorgangsfortschritt für den aktuellen und letzten Vorgang werden im Aufgabenstatus Bereich angezeigt.
    
## <a name="clear-data"></a>Löschen von Daten

Wenn das Löschen oder erneute Initialisieren von Falldaten erforderlich ist, muss die Datenbankinstanz initialisiert werden. Mit dem Dienstprogramm "Daten löschen" werden alle angegebenen Einträge aus der falldatenbank, den Textdateien, dem Fallordner und den akkumulierten Ergebnissen gelöscht. Die Funktion kann nur von einem Administrator ausgeführt werden.
  
> [!IMPORTANT]
> Diese Aktion ist nicht umkehrbar und löscht alle vom Experten durchgeführten Relevanz-Tagging und-Analysen. Speichern Sie bei Bedarf eine Sicherung der Daten. Verwenden Sie diese Option mit größter Sorgfalt. Das Löschen von gekennzeichneten und bewerteten Dateien kann sich auf die Relevanz der Ergebnisse auswirken. 
  
1. Klicken Sie in der Menüleiste auf das **Zahnrad** Symbol. 
    
2. Wählen Sie auf der Registerkarte **Einstellungen und Dienstprogramme \> ** die Option ** \> Daten Einrichtung löschen**aus.
    
3. Wählen Sie eine Option aus, damit die Informationen initialisiert werden:
    
  - **Relevanz**: Löscht alle relevanten arbeiten, einschließlich der Definition von Lasten und der Zuordnung von zu Lasten gemachten Dateien. Alle Beispiele und Markierungen werden gelöscht.
    
  - **Nahe Duplikate und e-Mail-Threads**: Löscht alle Analyseinformationen von nahe Duplikaten und e-Mail-Threads.
    
  - **Designs**: löscht Designs-bezogene Daten.
    
  - **Export Historie**: Löscht Verlaufsinformationen von Export Batches.
    
4. Klicken Sie auf **Daten löschen**. Die Case-Daten werden gelöscht. Die Informationen zum Vorgangsfortschritt für den aktuellen und letzten Vorgang werden im **Aufgabenstatus** Bereich angezeigt. 
    
## <a name="modify-relevance"></a>Relevanz ändern

In diesem Abschnitt wird beschrieben, wie ein Relevanz-Beispiel übersprungen oder zurückgesetzt wird.
  
1. Klicken Sie in der Menüleiste auf das **Zahnrad** Symbol. 
    
2. Wählen Sie auf der Registerkarte **Einstellungen und Dienstprogramme \> ** die Option **Relevanz ändern**aus.
    
3. Wählen Sie eine der folgenden Optionen aus: 
    
  - **Aktuelles Beispiel überspringen-für aktuellen Benutzer**: Dadurch werden alle nicht markierten Dateien im Open Case-Beispiel des Benutzers, der das Dienstprogramm ausführt, als **Skip**markiert. Für Dateien, die als **Skip**markiert sind, wird die Relevanz-Verarbeitung nicht ausgeführt.
    
  - **Aktuelles Beispiel überspringen – alle geöffneten Beispiele**: Dadurch werden alle nicht markierten Dateien in allen geöffneten Beispielen für alle Benutzer als **Skip**markiert. Diese Option wird nicht empfohlen, wenn Benutzer derzeit Beispiele kennzeichnen.
    
  - **Rollback für das letzte Beispiel**: das letzte abgeschlossene Schulungs Beispiel für Relevanz wird rückgängig gemacht, unabhängig davon, ob es vor oder nach dem Prozess "Calculate" liegt. Rollback eines catch-up-Beispiels ist nicht zulässig.
    
4. Klicken **Sie auf Ausführen** . 
    
## <a name="transparency-analysis"></a>Transparenz Analyse

Das Dienstprogramm zur Transparenz Analyse ermöglicht eine detaillierte Ansicht der Dateien und ihres zugewiesenen Relevanz-Ergebnisses. Der Bericht kann als Plausibilitätsüberprüfung verwendet werden oder um die Relevanz einer Datei zu vergleichen, die von einem menschlichen Prüfer im Vergleich zur von Advanced eDiscovery zugewiesenen Relevanz definiert wurde. 
  
Zusätzlich zu den Relevanz-Werten berechnet und weist Advanced eDiscovery Stich Wort Gewichte zu, die den Keyword-Kontext Beachtung finden. Das gleiche Wort in einer Datei kann je nach Kontext und Ort unterschiedliche Gewichtungen zugewiesen werden. Jedes Keyword wird mit einer zunehmenden Skala von Farbintensitäten markiert, die von gelb bis dunkel Orange und unterschiedliche Grauschattierungen reichen. Die Farbcodierung wird verwendet, um den relativen positiven oder negativen Beitrag des Wortes zur Relevanz-Bewertung visuell anzugeben. 
  
In einem Szenario mit mehreren Problemfällen kann für jedes Problem ein Bericht über die Transparenz Analyse generiert werden.
  
1. Klicken Sie in der Menüleiste auf das **Zahnrad** Symbol. 
    
2. Wählen Sie auf der Registerkarte **Einstellungen und Dienstprogramme \> ** die Option ** \> Transparenz Analyse einrichten**aus.
    
3. Geben Sie in * * Datei-ID * * die Datei-ID der zu verarbeitenden Datei ein.
    
4. Wählen Sie in der Liste **Problem** das relevante Problem aus. 
    
5. Klicken Sie auf **Transparenz Analyse**. Nach Abschluss des Berichts wird der Bericht über die Transparenz der Datei angezeigt, der zeigt, wie die markierten Schlüsselwortfarben mit dem Gesamtergebnis der Relevanz korrelieren.
    
## <a name="see-also"></a>Siehe auch

[Advanced eDiscovery (Classic)](office-365-advanced-ediscovery.md)
  
[Definieren von Fall-und Mandanten Einstellungen](define-case-and-tenant-settings-in-advanced-ediscovery.md)

