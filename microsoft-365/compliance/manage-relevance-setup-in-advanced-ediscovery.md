---
title: Verwalten der Einrichtung von Relevanz in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
description: Lesen Sie die Empfehlungen zum Einrichten des Relevanztrainings in Office 365 Advanced eDiscovery, um Dateien nach ihrer Relevanz zu beurteilen und Analyseergebnisse zu generieren.
ms.openlocfilehash: 49c7614eb1fec4e61fb374fb637093fd6e860619
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557885"
---
# <a name="manage-relevance-setup-in-advanced-ediscovery-classic"></a>Verwalten der Einrichtung von Relevanz in Advanced eDiscovery (Classic)

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 Bei der Relevanztechnologie von Advanced eDiscovery wird eine Software unter Anleitung von Experten zum Bewerten von Dateien nach ihrer Relevanz eingesetzt. Das Relevanzmodul in Advanced eDiscovery kann für eine frühzeitige Falleinschätzung, zum Sortieren und zur Überprüfung von Dateibeispielen verwendet werden. 
  
 Advanced eDiscovery umfasst die Komponenten für das Relevanztraining und das Markieren von Dateien, die für einen Fall relevant sind. Advanced eDiscovery lernt anhand der trainierten Beispiele relevanter und nicht relevanter Dateien, um Relevanzbewertungen für jede Datei bereitzustellen, und generiert Analyseergebnisse, die während und nach dem Dateiüberprüfungsprozess verwendet werden können. 
  
## <a name="guidelines-for-setting-up-relevance-training"></a>Richtlinien zum Einrichten des Relevanztrainings

 Wählen Sie in Advanced eDiscovery im Fenster **Fälle** einen Fall aus, und klicken Sie auf **Zum Fall wechseln**. Klicken Sie auf **Relevanz** \> **Einrichten von Relevanz**. Befolgen Sie die folgenden empfohlenen Richtlinien zum Einrichten von Relevanz. 
  
- **Markieren**: Die Effektivität des iterativen Relevanztrainingsprozesses ist von der Fähigkeit des Experten abhängig, die Dateibeispiele präzise und konsistent zu markieren.
    
- **Fallprobleme**: 
    
  - Verwenden Sie im gesamten Relevanztrainingsprozess für jedes Problem denselben Experten. Das gleichzeitige Markieren desselben Problems durch mehrere Experten ist nicht zulässig.
    
  - Ermitteln Sie, ob jede Gruppe von Dateien nur für ein bestimmtes Problem relevant ist. 
    
  - Wenn ein Problem zu allgemein definiert ist, werden in Advanced eDiscovery möglicherweise zu viele Dateien gefunden, die eigentlich nicht relevant sind. Wenn ein Problem zu eng definiert ist, dauert der Relevanztrainingsprozess möglicherweise länger. 
    
  - Bei jedem Zyklus des Relevanztrainings befasst sich Advanced eDiscovery mit einem einzigen aktiven Problem, und es werden Zwischenergebnisse angezeigt.
    
  - In einem Szenario mit mehreren Problemen können mithilfe des Samplingmodus die Probleme ausgewählt werden, die in die Verarbeitung aufgenommen werden sollen. Probleme, die als „deaktiviert“ definiert sind, werden erst verarbeitet, wenn ihr Samplingmodus geändert wird. Ein Problem kann nur für einen Experten „im Leerlauf“ oder „aktiviert“ sein.
    
  -  Advanced eDiscovery kann zum Generieren von Kandidatberechtigungsdateien verwendet werden. Richten Sie ein separates Problem für Berechtigungen ein. Wenn möglich, trainieren und sortieren Sie erst im Hinblick auf Relevanz. Trainieren Sie dann im Hinblick auf die Berechtigung nur für den sortierten Satz (laden Sie den sortierten Satz als separaten Fall erneut). 
    
  - Die Batchberechnung kann nur ausgeführt werden, wenn keine offenen Beispiele vorhanden sind (beim Klicken auf „Batchberechnung“ wird eine Liste von Benutzern mit offenen Beispielen angezeigt). Um Beispiele von anderen Benutzern zu schließen (dies sollte nur durchgeführt werden, wenn diese Benutzer diese Beispiele nicht markieren), kann ein Administrator das Dienstprogramm „Relevanz ändern“ mit der Option des Beispiels für alle Benutzer verwenden.
    
- **Metadaten**: Advanced eDiscovery konzentriert sich auf Inhalte. Es werden keine Metadaten als Teil der Relevanzkriterien berücksichtigt. 
    
- **Relevanzgrad**: Wenn der Relevanzgrad für ein Problem nach der Bewertung unter 3 % liegt, sollte das Seeding des Relevanztrainings mit bekannten relevanten und nicht relevanten Dateien ausgeführt werden.
    
- **Dateigröße**: Große Dateien (über 5.242.880 Zeichen extrahierter Text) werden im Relevanztool ignoriert. Die Dateien sind nicht am Relevanztrainingsprozess beteiligt und erhalten nach der Batchberechnung keine Relevanzbewertung. Dateien über 5 MB können in dem Bewertungssatz aufgenommen werden.
    
## <a name="setting-up-case-issues"></a>Einrichten von Fallproblemen

Die in diesem Abschnitt beschriebenen Parameter sind in Advanced eDiscovery unter **Relevanz** \> **Einrichten von Relevanz** verfügbar. 
  
- Probleme müssen einem Benutzer zugewiesen werden, der die Dateien trainiert.
    
- Importierte Dateien müssen dann der verarbeiteten Last hinzugefügt werden.
    
- Definieren und organisieren Sie Probleme sorgfältig, da sich dies auf die Ergebnisse des Relevanztrainings auswirken kann.
    
Nachdem die Parameter festgelegt wurden, kann der Prüfer/Experte mit dem Training der Dateien auf der Registerkarte **Relevanz** beginnen. 
  
## <a name="see-also"></a>Siehe auch

[Advanced eDiscovery (Classic)](office-365-advanced-ediscovery.md)
  
[Definieren von Problemen und Zuweisen von Benutzern](define-issues-and-assign-users.md)
  
[Einrichten von Lasten zum Hinzufügen importierter Dateien](set-up-loads-to-add-imported-files.md)
  
[Definieren hervorgehobener Schlüsselwörter und erweiterte Optionen](define-highlighted-keywords-and-advanced-options.md)

