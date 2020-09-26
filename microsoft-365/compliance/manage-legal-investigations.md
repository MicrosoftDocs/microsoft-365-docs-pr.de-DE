---
title: Verwalten von rechtlichen Untersuchungen in Microsoft 365
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-apr2020
description: Verwenden Sie eDiscovery-Fälle im Security & Compliance Center in Office 365, um die rechtliche Untersuchung Ihres Unternehmens zu verwalten.
ms.openlocfilehash: edc9835cdbefa611af4c0906be5d3e1d0404c635
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285651"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Verwalten von rechtlichen Untersuchungen in Microsoft 365

Organisationen haben viele Gründe, auf einen Rechtsstreit mit bestimmten Führungskräften oder anderen Mitarbeitern in Ihrer Organisation zu reagieren. Dies kann dazu führen, dass weitere Ermittlungs spezifische Informationen in e-Mails, Dokumenten, Chats und anderen Inhaltsspeicherorten, die von Personen in ihren täglichen Arbeitsaufgaben verwendet werden, schnell gefunden und aufbewahrt werden. Sie können diese und viele andere ähnliche Aktivitäten mithilfe der eDiscovery Case-Tools im Security and Compliance Center ausführen.
  
**Möchten Sie wissen, wie Microsoft die eDiscovery-Untersuchungen verwaltet?** Hier ist ein [Technisches Whitepaper](https://go.microsoft.com/fwlink/?linkid=852161) , das Sie herunterladen können, das erläutert, wie wir die gleichen Such-und Untersuchungs Tools zur Verwaltung unseres internen eDiscovery-Workflows verwenden.
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Verwalten von rechtlichen Untersuchungen mit eDiscovery-Fällen

mit eDiscovery-Fällen können Sie steuern, wer eDiscovery-Fälle in Ihrer Organisation erstellen, auf Sie zugreifen und diese verwalten kann. Verwenden Sie Fälle, um Mitglieder hinzuzufügen und zu steuern, welche Arten von Aktionen Sie durchführen können, Aufbewahrungsmöglichkeiten für inhaltsspeicherorte, die für einen Rechtsfall relevant sind, und mithilfe des Inhalts Such Tools die Speicherorte für Inhalte zu durchsuchen, die möglicherweise auf Ihren Fall reagieren. Anschließend können Sie diese Ergebnisse auch zur weiteren Untersuchung durch externe Bearbeiter exportieren und herunterladen.
  
- [Verwalten des eDiscovery-Workflows](ediscovery-cases.md) durch Erstellen und Verwenden von eDiscovery-Fällen für jede rechtliche Untersuchung, die Ihre Organisation durchführen muss 
    
- [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md) zum Steuern der Benutzer, die eDiscovery-Fälle in Ihrer Organisation erstellen und verwalten können 
    
- [Einrichten von Compliance-Grenzen](tagging-and-assessment-in-advanced-ediscovery.md) zum Steuern der Benutzerinhalts Speicherorte, die eDiscovery-Manager durchsuchen können 
    
- [Suchen nach Inhalten](search-for-content.md) in Ihrer Organisation 
    
### <a name="use-scripts-for-advanced-scenarios"></a>Verwenden von Skripts für erweiterte Szenarien

Wie im vorherigen Abschnitt, in dem Skripts für Inhalts Suchszenarien aufgeführt sind, haben wir auch einige PowerShell-Skripts für Sicherheits & Compliance Center erstellt, die Sie bei der Verwaltung von eDiscovery-Fällen unterstützen.
  
- [Erstellen eines eDiscovery Hold-Berichts](create-a-report-on-holds-in-ediscovery-cases.md) mit Informationen zu allen mit eDiscovery-Fällen in Ihrer Organisation verknüpften Haltestatus 
    
- [Hinzufügen von Postfächern und OneDrive-Speicherorten](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) für eine Liste von Benutzern zu einem eDiscovery-Haltestatus 
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Verwalten von rechtlichen Untersuchungen mit der erweiterten eDiscovery-Lösung in Microsoft 365

Die Advanced eDiscovery-Lösung in Microsoft 365 basiert auf den vorhandenen eDiscovery- und Analysefunktionen in Office 365. Diese neue Lösung mit dem Namen *Advanced eDiscovery* bietet einen End-to-End-Workflow zum Beibehalten, Sammeln, Überprüfen, Analysieren und Exportieren von Inhalten, die auf die internen und externen Ermittlungen Ihrer Organisation abgestimmt sind. Außerdem können Rechtsteams den gesamten Benachrichtigungs-Workflow einsehen, der für juristische Zwecke aufbewahrt wurde, und so mit den an einem Fall beteiligten Verwahrern kommunizieren.

Advanced eDiscovery erfordert ein E5-Abonnement für Ihre Microsoft 365-oder Office 365-Organisation. Weitere Informationen zur Lizenzierung finden Sie unter [Erste Schritte mit Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

Im folgenden finden Sie eine kurze Übersicht über den integrierten Workflow in Advanced eDiscovery. Weitere Informationen finden Sie unter [Explore the Advanced eDiscovery Workflow](get-started-with-advanced-ediscovery.md#explore-the-advanced-ediscovery-workflow).

- [Erstellen einer Anfrage](create-new-ediscovery-case.md) für erste Schritte

- [Verwalten Sie Verwalter](managing-custodians.md) , indem Sie Sie zu einem Fall hinzufügen und den Inhalten in Ihrem Postfach, OneDrive-Konto und Microsoft Teams, in denen Sie Mitglieder sind, Rechtliche Aufbewahrungspflicht erteilen.

- [Verwalten der Kommunikation](managing-custodian-communications.md) mit Depotbanken durch Automatisierung des Benachrichtigungsprozesses für rechtliche Aufbewahrungen

- [Indizieren von Depotdaten](processing-data-for-case.md) und Beheben von Indizierungs Fehlern, damit Sie effektiv Daten für ihre Untersuchungen erfassen können

- [Sammeln von Daten](collecting-data-for-ediscovery.md) für einen Fall und Hinzufügen des [Add-Ins zu einer Überprüfungsgruppe](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) zur weiteren Untersuchung

- [Anzeigen ](view-documents-in-review-set.md) von Dokumenten, [Abfrage](review-set-search.md) Daten und [Tag](tagging-documents.md) -Elementen in einem Überprüfungs Satzes

- [Analysieren von Case-Daten](analyzing-data-in-review-set.md) mit erweiterten Analysetools

- [Exportieren von Falldaten](exporting-data-ediscover20.md) zur Überprüfung durch externe Berater

- [Verwalten von Aufträgen mit langer Ausführungszeit](managing-jobs-ediscovery20.md) in Advanced eDiscovery
