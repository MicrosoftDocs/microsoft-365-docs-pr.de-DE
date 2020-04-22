---
title: Ausführen des Prozess Moduls in Advanced eDiscovery
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
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: 'Erfahren Sie mehr über die Richtlinien für die Vorbereitung von Fall Dateien von Daten für die Analyse mit Advanced eDiscovery.  '
ms.openlocfilehash: c0c0b8c3477f8c3fdbe0437659a88f14fbcad1cd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626461"
---
# <a name="run-the-process-module-in-advanced-ediscovery-classic"></a>Ausführen des Prozess Moduls in Advanced eDiscovery (klassisch)

Fall Dateien werden während des **Vorbereitungs** \> **Prozesses**in die erweiterte eDiscovery geladen. 
  
> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a>Richtlinien: Vorbereiten von Daten für erweiterte eDiscovery

- **Qualität**: identifizieren Sie eindeutig die für den Fall relevante Fall Datei Population.
    
- **Lädt**: Laden Sie die Dateien an einen Speicherort, auf den Advanced eDiscovery zugreifen kann.
    
- **Datei-ID**: ein eindeutiger Dateibezeichner in Advanced eDiscovery. Wenn kein Dateibezeichner importiert wird, generiert Advanced eDiscovery automatisch die ID. Wenn Sie die ID in einer nachfolgenden Prozesslast zuordnen und einen anderen Pfad zuordnen als bei der anfänglichen Prozesslast, ersetzt Advanced eDiscovery den Pfad (statt einen neuen Dateieintrag hinzuzufügen). Die ID kann als Referenz im Export Prozess verwendet werden. Der ID-Wert sollte nicht "-1" lauten.
    
- **MD5**: Diese Signatur wird verwendet, um zwischen Dateien zu unterscheiden (zwei Dateien werden nur dann als exakte Duplikate betrachtet, wenn Sie denselben MD5 haben). Standardmäßig berechnet Advanced eDiscovery die MD5-Datei. Wenn es sich bei den geladenen Dateien um Textdateien handelt, wird empfohlen, den ursprünglichen MD5-Wert zu laden und zuzuordnen, anstatt ihn in Advanced eDiscovery zu berechnen.
    
- **Dateityp und Name**:
    
  - Advanced eDiscovery kann Dateien verschiedener Formate verarbeiten und geladene systemeigene Dateien in ein Standardformat extrahieren, \*beispielsweise. TXT, HTML oder. XML. Die Verarbeitung von Textdateien ist schneller als systemeigene Dateien. Extrahierte Textdateien werden im Fallordner gespeichert.
    
  - Laden Sie keine Dateien, die nicht extrahiert werden können, wie Systemdateien oder Grafik Bilder. Diese Dateien können die Verarbeitung verzögern.
    
  - Stellen Sie sicher, dass die Dateinamen signifikant benannt sind und die Pfade korrekt sind.
    
- **Dateipfad**: Advanced eDiscovery kann Dateien mit Pfad Längen von bis zu 400 Zeichen laden.
    
- **Textextraktion**: beim Extrahieren von Text aus systemeigenen Dateien, zusätzlich zum normalen Text, werden auch die folgenden extrahiert: verborgener Text (Excel und. doc), ausgeblendete Spalten (Excel), Nachverfolgen von Änderungen (doc), referentennotizen (PPT), eingebettete Objekte (beispielsweise Excel-Objekte in a. ppt). Diese können im Text-Editor angezeigt werden.
    
- **Text ignorieren**: dieses optionale Feature wird nach dem Ausführen des Prozesses und vor der Analyse definiert. Ignore Text sollte mit Vorsicht verwendet werden, da seine Verwendung die Leistung der Dateianalyse verringern kann.
    
- **Mehrsprachiger Text**: Advanced eDiscovery verarbeitet derzeit keine mehrsprachigen Namen für Tags, Verwalter und Probleme.
    
- **Metadata**: bestimmen Sie, ob es Metadaten gibt, die Sie in der falldatenbank zur zukünftigen Referenz speichern möchten, beispielsweise den Datumsbereich, die Dateigröße, den Dateityp, den depotverwalter und den Betreff. Metadaten können geladen werden, nachdem Dateien bereits geladen wurden, ohne dass das Inventar erneut ausgeführt oder der Aufwand für die erneute Verarbeitung hinzugefügt wurde. 
    
  - Wenn die Dateien ursprünglich aus dem Pfad geladen wurden, ordnen Sie die Spalte path zu, wenn Sie später Metadaten importieren. Es ist möglich, auf die Datei anhand der ID zu referenzieren und einen anderen Pfad zuzuordnen. Dies ist ein nützliches Szenario, wenn sich die Dateipfade ändern.
    
  - Wenn die Dateien ursprünglich von der Datei-ID geladen wurden, ordnen Sie die ID-Spalte beim Laden von Metadaten zu. Wenn Sie auf die Datei durch path (anstelle von ID) verweisen, wird das erneute Laden von Dateien mit einer anderen ID bewirkt. Mit Advanced eDiscovery werden Kopien der Dateien erstellt, anstatt Metadaten der vorhandenen Dateien zu laden.
    
- **Familien**: Es ist nicht möglich, eine Familie ohne das übergeordnete Element (Familienoberhaupt) zu laden. 
    
- **Dateigröße**: Es gibt keine Beschränkung der Größe von Dateien, die auf Advanced eDiscovery geladen wurden. Für die Analyse (Analyse, Relevanz usw.) beträgt der Grenzwert 5.242.880 Zeichen extrahierten Texts. Größere Dateien werden ignoriert (beispielsweise relevant: Dateien nehmen nicht am Relevanz-Schulungsprozess Teil und erhalten nach der Stapel Berechnung kein Relevanz-Ergebnis).
    
- **Datei Menge**: Es gibt keine empfohlene Grenze für die Anzahl der Dateien, die in einem einzigen Fall behandelt werden können. Die Leistung hängt von den Ressourcen Ihres Systems ab. 
    
## <a name="filtering-files"></a>Filtern von Dateien

Eine benutzerdefinierte Bezeichnung kann mit einer Reihe von Dateien verknüpft werden, um Sie von Prozessen oder anderen Aufgaben auszuschließen. Jeder Prozess Sitzung ist eine Batch-ID zugeordnet. Obwohl die Batch-ID für den Experten in Relevanz nicht sichtbar ist, kann dies mithilfe eines Such Dienstprogramms erfolgen, indem ein Filter für den aktuellen Batch hinzugefügt und alle entsprechenden Dateien mit einer benutzerdefinierten Bezeichnung versehen werden. 
  
## <a name="see-also"></a>Siehe auch

[Advanced eDiscovery (Classic)](office-365-advanced-ediscovery.md)
  
[Ausführung des Prozess Moduls und Laden von Daten](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[Anzeigen der Ergebnisse des Prozess Moduls](view-process-module-results-in-advanced-ediscovery.md)

