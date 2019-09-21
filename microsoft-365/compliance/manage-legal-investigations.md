---
title: Verwalten von rechtlichen Untersuchungen in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
description: 'Verwenden Sie eDiscovery-Fälle im Security #a0 Compliance Center in Office 365, um die rechtliche Untersuchung Ihres Unternehmens zu verwalten. Wenn Sie über ein E5-Abonnement verfügen, können Sie die Falldaten weiter analysieren, indem Sie die Funktionen Textanalyse, Maschinelles Lernen und Vorhersage Codierung von Advanced eDiscovery verwenden.'
ms.openlocfilehash: c6b5b3048039a8c92d120d2b9f46d6d22d9ccee0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081594"
---
# <a name="manage-legal-investigations-in-office-365"></a>Verwalten von rechtlichen Untersuchungen in Office 365

Organisationen haben viele Gründe, auf einen Rechtsstreit mit bestimmten Führungskräften oder anderen Mitarbeitern in Ihrer Organisation zu reagieren. Dies kann dazu führen, dass in e-Mails, Dokumenten, Chats und anderen Inhaltsspeicherorten, die von Personen in ihren täglichen Arbeitsaufgaben verwendet werden, weitere unter Such spezifische Informationen gefunden und aufbewahrt werden. Sie können diese und viele andere ähnliche Aktivitäten mithilfe der eDiscovery Case-Tools im Security #a0 Compliance Center ausführen.
  
[Verwalten von rechtlichen Untersuchungen mit eDiscovery-Fällen](#manage-legal-investigations-with-ediscovery-cases)
  
[Analysieren von Case-Daten mit Office 365 Advanced eDiscovery](#analyze-case-data-using-office-365-advanced-ediscovery)
  
**Möchten Sie wissen, wie Microsoft die eDiscovery-Untersuchungen verwaltet?** Hier ist ein [Technisches Whitepaper](https://go.microsoft.com/fwlink/?linkid=852161) , das Sie herunterladen können, das erläutert, wie wir dieselben Office 365 Such-und Untersuchungs Tools zur Verwaltung unseres internen eDiscovery-Workflows verwenden.
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Verwalten von rechtlichen Untersuchungen mit eDiscovery-Fällen

mit eDiscovery-Fällen können Sie steuern, wer eDiscovery-Fälle in Ihrer Organisation erstellen, auf Sie zugreifen und diese verwalten kann. Verwenden Sie Fälle, um Mitglieder hinzuzufügen und zu steuern, welche Arten von Aktionen Sie durchführen können, Aufbewahrungsmöglichkeiten für inhaltsspeicherorte, die für einen Rechtsfall relevant sind, und mithilfe des Inhalts Such Tools die Speicherorte für Inhalte zu durchsuchen, die möglicherweise auf Ihren Fall reagieren. Anschließend können Sie diese Ergebnisse auch zur weiteren Untersuchung durch externe Bearbeiter exportieren und herunterladen. Wenn Ihre Office 365 Organisation über ein E5-Abonnement verfügt, können Sie auch Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten.
  
- [Verwalten des eDiscovery-Workflows](ediscovery-cases.md) durch Erstellen und Verwenden von eDiscovery-Fällen für jede rechtliche Untersuchung, die Ihre Organisation durchführen muss 
    
- [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md) zum Steuern der Benutzer, die eDiscovery-Fälle in Ihrer Organisation erstellen und verwalten können 
    
- [Einrichten von Compliance-Grenzen](tagging-and-assessment-in-advanced-ediscovery.md) zum Steuern der Benutzerinhalts Speicherorte, die eDiscovery-Manager durchsuchen können 
    
- [Suchen nach Inhalten](search-for-content.md) in Ihrer Organisation 
    
- [Vorbereiten der Fall Inhalte für Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md) , sodass Sie die Analyse mithilfe der leistungsstarken Analysetools von Advanced eDiscovery wie der optischen Zeichenerkennung, des e-Mail-Threads und der Vorhersage Codierung ausführen können 
    
### <a name="use-scripts-for-advanced-scenarios"></a>Verwenden von Skripts für erweiterte Szenarien

Wie im vorherigen Abschnitt, in dem Skripts für Inhalts Suchszenarien aufgeführt sind, haben wir auch einige PowerShell-Skripts für Sicherheits #a0 Compliance Center erstellt, die Sie bei der Verwaltung von eDiscovery-Fällen unterstützen.
  
- [Erstellen eines eDiscovery Hold-Berichts](create-a-report-on-holds-in-ediscovery-cases.md) mit Informationen zu allen mit eDiscovery-Fällen in Ihrer Organisation verknüpften Haltestatus 
    
- [Hinzufügen von Postfächern und OneDrive-Speicherorten](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) für eine Liste von Benutzern zu einem eDiscovery-Haltestatus 
  
## <a name="analyze-case-data-using-office-365-advanced-ediscovery"></a>Analysieren von Case-Daten mit Office 365 Advanced eDiscovery

Office 365 Advanced eDiscovery baut auf der in den vorherigen Abschnitten beschriebenen Inhaltssuche und eDiscovery-Funktionen auf. Nachdem Sie einen eDiscovery-Fall erstellt, die Aufbewahrungsorte gespeichert und Daten erfasst haben, die möglicherweise auf den Fall reagieren, können Sie die Daten anschließend mithilfe der Textanalyse, des maschinellen Lernens und der vorausschauenden Codierungsfunktionen von Advanced analysieren. eDiscovery. Dies kann dazu beitragen, dass Ihre Organisation Tausende von e-Mail-Nachrichten, Dokumenten und anderen Arten von Daten schnell verarbeitet, um nach diesen Elementen zu suchen, die für einen bestimmten Fall höchstwahrscheinlich relevant sind. Und wir haben die einheitliche Fallverwaltung und die erweiterte eDiscovery, damit Sie den gleichen Fall im Security #a0 Compliance Center nahtlos verwalten können.
  
> [!NOTE]
> Um die Daten eines Benutzers mithilfe von Advanced eDiscovery zu analysieren, muss dem Benutzer (dem Verwalter der Daten) eine Office 365 E5-Lizenz zugewiesen werden. Alternativ können Benutzern mit einer Office 365 E1-oder E3-Lizenz eine erweiterte eDiscovery-eigenständige Lizenz zugewiesen werden. Administratoren und Compliance Officer, die Fällen zugeordnet sind, und Verwenden von Advanced eDiscovery zum Analysieren von Daten benötigen keine E5-Lizenz. 
  
### <a name="get-started"></a>Erste Schritte

Am schnellsten können Sie mit Advanced eDiscovery beginnen, indem Sie einen Fall erstellen und Suchergebnisse im Security #a0 Compliance Center vorbereiten, diese Ergebnisse in Advanced eDiscovery laden und dann die Express Analyse ausführen, um die Falldaten zu analysieren und dann die Ergebnisse für externe Überprüfung.
  
- [Erhalten Sie einen schnellen Überblick](quick-setup-for-advanced-ediscovery.md) über den erweiterten eDiscovery-Workflow 
    
- [Einrichten von Benutzern und Fällen](set-up-users-and-cases-in-advanced-ediscovery.md) für Advanced eDiscovery durch Erstellen einer Anfrage, Zuweisen von eDiscovery-Berechtigungen und Hinzufügen von Fall Mitgliedern mithilfe des Security #a0 Compliance Centers 
    
- [Vorbereiten und Laden von Such Daten](prepare-data-for-advanced-ediscovery.md) in den Fall in Advanced eDiscovery 
    
- [Laden von nicht Office 365 Daten](import-non-office-365-data-into-advanced-ediscovery.md) in einen Fall zur Analyse in Advanced eDiscovery 
    
- [Verwenden Sie die Express Analyse](use-express-analysis-in-advanced-ediscovery.md) , um die Daten in einem Fall schnell zu analysieren und die Ergebnisse dann einfach zu exportieren. 
    
### <a name="analyze-data"></a>Analysieren von Daten

Nachdem Such Daten in den Fall in Advanced eDiscovery geladen wurden, verwenden Sie das ANALYZE-Modul, um mit der Analyse zu beginnen. Der erste Teil des Analyseprozesses besteht darin, Dateien in Gruppen eindeutiger Dateien, Duplikate und nahe Duplikate (auch bekannt als Dokument Ähnlichkeit) zu organisieren. Anschließend organisieren Sie die Daten erneut in hierarchisch strukturierte Gruppen von e-Mail-Threads und-Designs und legen optional Textfilter ignorieren fest, um bestimmten Text aus der Analyse auszuschließen. Anschließend führen Sie die Analyse aus und zeigen die Ergebnisse an.
  
- Informationen zur [Dokument Ähnlichkeit](understand-document-similarity-in-advanced-ediscovery.md) zur Vorbereitung auf die Analyse von Daten in Advanced eDiscovery 
    
- [Richten Sie die Optionen](set-analyze-options-in-advanced-ediscovery.md) für nahe Duplikate, Designs und e-Mail-Threading ein, und führen Sie dann das Modul analyze aus. 
    
- [Einrichten ignorieren von Text filtern](set-ignore-text-in-advanced-ediscovery.md) , um Text-und Textzeichenfolgen von der Analyse auszuschließen; Diese Filter ignorieren außerdem Text, wenn Sie die Relevanz-Analyse ausführen. 
    
- [Anzeigen der Ergebnisse](view-analyze-results-in-advanced-ediscovery.md) des Analyseprozesses 
    
- [Konfigurieren von erweiterten Einstellungen](set-analyze-advanced-settings-in-advanced-ediscovery.md) für den Analyseprozess 
    
### <a name="set-up-relevance-training"></a>Einrichten der Relevanzschulung

Mit Predictive Coding (genannt Relevanz) in Advanced eDiscovery können Sie das System auf das, was Sie suchen, einteilen, indem Sie Entscheidungen treffen (darüber, ob etwas relevant ist oder nicht), für eine kleine Gruppe von Dokumenten.
  
- [Hier erfahren Sie mehr über das Einrichten von Relevanz-Schulungen](manage-relevance-setup-in-advanced-ediscovery.md) , das Markieren von Dateien, die für einen Fall relevant sind, und das Definieren von Fall Problemen. 
    
- [Definieren von Fall Problemen](define-issues-and-assign-users.md) und Zuweisen jedes Problems zu einem Benutzer, der die Dateien trainieren wird 
    
- [Hinzufügen importierter Dateien zu aktueller oder neuer Last](set-up-loads-to-add-imported-files.md) , die dem Relevanz-Schulungsprogramm hinzugefügt werden; bei einer Last handelt es sich um einen neuen Batch mit Dateien, die einem Fall hinzugefügt und dann für die Relevanz-Schulung verwendet werden. 
    
- [Definieren Sie die hervorgehobenen Schlüsselwörter](define-highlighted-keywords-and-advanced-options.md) , die dem Relevanz-Training hinzugefügt werden können. auf diese Weise können Sie Dateien besser identifizieren, die für einen Fall relevant sind. 
    
### <a name="run-the-relevance-module"></a>Ausführen des Moduls "Relevanz"

Nachdem Sie das Training eingerichtet haben, können Sie das Modul "Relevanz" ausführen und die Effektivität der Schulungs Einstellungen bewerten. Dies führt zu einer Relevanz-Rangfolge, mit der Sie entscheiden können, ob Sie zusätzliche Schulungen durchführen müssen, oder ob Sie zum Starten von Tagging-Dateien bereit sind. relevant für Ihren Fall.
  
- [Erfahren Sie mehr über den Prozess der Relevanz](use-relevance-in-advanced-ediscovery.md) und den iterativen Prozess der Bewertung, Tagging, Nachverfolgung und Umschulung basierend auf Beispieldateien 
    
- [Erfahren Sie mehr über die Bewertung](assessment-in-relevance-in-advanced-ediscovery.md) , bei der ein mit dem Fall vertrauter Experte eine Reihe von Fall Dateien überprüft und die Effektivität des Relevanz-Trainings ermittelt. 
    
- [Bewerten Sie die Fall Dateien](tagging-and-assessment-in-advanced-ediscovery.md) , um die Effektivität ( *Reichtum* genannt) der Trainingseinstellungen zu berechnen, und markieren Sie dann Dateien als relevant oder nicht relevant für Ihren Fall. auf diese Weise können Sie ermitteln, ob das aktuelle Training ausreicht oder die Trainingseinstellungen anpassen. 
    
- [Ausführen des Relevanz-Trainings](tagging-and-relevance-training-in-advanced-ediscovery.md) nach Abschluss der Bewertung und Erneutes Markieren von Dateien als relevant oder nicht relevant für die Probleme, die Sie für den Fall definiert haben 
    
- [Verfolgen Sie den](track-relevance-analysis-in-advanced-ediscovery.md) Prozess zur Relevanz-Analyse, um festzustellen, ob die Relevanz-Schulung Ihr Bewertungs Ziel erreicht hat (als *stabiler Schulungsstatus* bezeichnet) oder ob mehr Schulungen erforderlich sind. Sie können auch die Relevanz der Ergebnisse für jedes Fall Problem anzeigen 
    
- [Entscheidungen basierend auf der Relevanz-Analyse treffen](decision-based-on-the-results-in-advanced-ediscovery.md) , um die Größe der sich ergebenden Fall Dateien zu bestimmen, die zur Überarbeitung exportiert werden können 
    
- [Testen Sie die Qualität der Relevanz-Analyse](test-relevance-analysis-in-advanced-ediscovery.md) , um die während des Relevanz-Prozesses getroffenen Culling-Entscheidungen zu validieren. 
    
### <a name="export-results"></a>Ergebnisse exportieren

Der letzte Schritt bei der Analyse von Falldaten in Advanced eDiscovery besteht darin, die Ergebnisse der Analyse für die externe Überprüfung zu exportieren.
  
- [Informationen zum Exportieren von Case-Daten](export-case-data-in-advanced-ediscovery.md)
    
- [Exportieren von Falldaten](export-results-in-advanced-ediscovery.md)
    
- [Anzeigen des Batchverlaufs und Exportieren vergangener Ergebnisse](view-batch-history-and-export-past-results.md)
    
- [Exportieren von Berichtsfeldern](export-report-fields-in-advanced-ediscovery.md)
    
### <a name="other-advanced-ediscovery-tools"></a>Weitere Erweiterte eDiscovery-Tools

Advanced eDiscovery bietet zusätzliche Tools und Funktionen jenseits der Analyse von Falldaten, der Relevanz-Analyse und des Exports von Daten.
  
- [Ausführen von erweiterten eDiscovery-Berichten](run-reports-in-advanced-ediscovery.md)
    
- [Definieren von Groß-/Kleinschreibung und Mandanten Einstellungen](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [Erweiterte eDiscovery-Dienstprogramme](use-advanced-ediscovery-utilities.md)
