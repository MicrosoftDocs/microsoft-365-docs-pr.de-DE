---
title: Verwalten rechtlicher Untersuchungen in Microsoft 365
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
description: Verwenden Sie eDiscovery-Fälle im Security & Compliance Center in Office 365, um die rechtliche Untersuchung Ihrer Organisation zu verwalten.
ms.openlocfilehash: 7a02bd47f93a85e643694efea4dcc140847916e0
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840704"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Verwalten rechtlicher Untersuchungen in Microsoft 365

Organisationen haben viele Gründe, auf einen Rechtsfall zu reagieren, an dem bestimmte Führungskräfte oder andere Mitarbeiter in Ihrer Organisation beteiligt sind. Dies kann eine schnelle Suche und Aufbewahrung für weitere untersuchungsspezifische Informationen in E-Mails, Dokumenten, Chatunterhaltungen und anderen Inhaltsspeicherorten sein, die von Personen in ihren täglichen Aufgaben verwendet werden. Sie können diese und viele andere ähnliche Aktivitäten mithilfe der eDiscovery-Falltools im Security and Compliance Center ausführen.
  
**Möchten Sie wissen, wie Microsoft seine eDiscovery-Untersuchungen verwaltet?** Hier ist ein [technisches](https://go.microsoft.com/fwlink/?linkid=852161) Whitepaper, das Sie herunterladen können und in dem erläutert wird, wie wir die gleichen Such- und Untersuchungstools verwenden, um unseren internen eDiscovery-Workflow zu verwalten.

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Verwalten rechtlicher Untersuchungen mit eDiscovery-Fällen

Mit eDiscovery-Fällen können Sie steuern, wer eDiscovery-Fälle in Ihrer Organisation erstellen, darauf zugreifen und verwalten kann. Verwenden Sie Fälle, um Mitglieder hinzuzufügen und zu steuern, welche Arten von Aktionen sie ausführen können, platzieren Sie die für einen Rechtsfall relevanten Speicherorte in einem Haltefeld, und verwenden Sie das Tool für die Inhaltssuche, um die Halteorte nach Inhalten zu durchsuchen, die möglicherweise auf Ihren Fall reagieren. Anschließend können Sie diese Ergebnisse auch zur weiteren Untersuchung durch externe Prüfer exportieren und herunterladen.
  
- [Verwalten Sie Ihren eDiscovery-Workflow,](ediscovery-cases.md) indem Sie eDiscovery-Fälle für jede rechtliche Untersuchung erstellen und verwenden, die Ihre Organisation unternehmen muss.

- [Weisen Sie eDiscovery-Berechtigungen zu,](assign-ediscovery-permissions.md) um zu steuern, wer eDiscovery-Fälle in Ihrer Organisation erstellen und verwalten kann.

- [Richten Sie Compliancegrenzen ein,](set-up-compliance-boundaries.md) um die Speicherorte für Benutzerinhalte zu steuern, die eDiscovery-Manager durchsuchen können.

- [Suchen Sie nach Inhalten](search-for-content.md) in Ihrer Organisation.

### <a name="use-scripts-for-advanced-scenarios"></a>Verwenden von Skripts für erweiterte Szenarien

Wie im vorherigen Abschnitt, in dem Skripts für Inhaltssuchszenarien aufgeführt sind, haben wir auch einige Security & Compliance Center -PowerShell-Skripts erstellt, die Sie bei der Verwaltung von eDiscovery-Fällen unterstützen.
  
- [Erstellen Sie einen eDiscovery-Haltebericht,](create-a-report-on-holds-in-ediscovery-cases.md) der Informationen zu allen In-EDiscovery-Fällen in Ihrer Organisation zugeordneten Halte halte enthält.

- [Hinzufügen von Postfächern und #A0](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) für eine Liste von Benutzern zu einem eDiscovery-Archiv.
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Verwalten rechtlicher Untersuchungen mit der Advanced eDiscovery-Lösung in Microsoft 365

Die Advanced eDiscovery-Lösung in Microsoft 365 basiert auf den vorhandenen eDiscovery- und Analysefunktionen in Office 365. Diese neue Lösung mit dem Namen *Advanced eDiscovery* bietet einen End-to-End-Workflow zum Beibehalten, Sammeln, Überprüfen, Analysieren und Exportieren von Inhalten, die auf die internen und externen Ermittlungen Ihrer Organisation abgestimmt sind. Außerdem können Rechtsteams den gesamten Benachrichtigungs-Workflow einsehen, der für juristische Zwecke aufbewahrt wurde, und so mit den an einem Fall beteiligten Verwahrern kommunizieren.

Advanced eDiscovery erfordert ein E5-Abonnement für Ihre Microsoft 365- oder Office 365-Organisation. Weitere Informationen zur Lizenzierung finden Sie unter ["Einrichten von Advanced eDiscovery".](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)

Hier finden Sie eine kurze Übersicht über den integrierten Workflow in Advanced eDiscovery. Weitere Informationen finden Sie unter [Verwalten des Advanced eDiscovery-Workflows.](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)

- [Erstellen Sie einen Fall](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) für die ersten Schritte.

- [Verwalten Sie](managing-custodians.md) Verwahrer, indem Sie sie zu einem Fall hinzufügen und inhalte in ihrem Postfach, ihrem #A0 und Microsoft Teams, in dem sie Mitglied sind, gesetzlich archivieren.

- [Verwalten Sie die](managing-custodian-communications.md) Kommunikation mit Verwahrern, indem Sie den Benachrichtigungsprozess für die gesetzliche Gesetzliche Benachrichtigung automatisieren.

- [Indizieren Von Verwahrerdaten](processing-data-for-case.md) und Beheben von Indizierungsfehlern, damit Sie effektiv Daten für Ihre Untersuchungen sammeln können.

- [Sammeln sie Daten](collecting-data-for-ediscovery.md) für einen Fall, und fügen Sie sie [einem Überprüfungssatz zur](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) weiteren Untersuchung hinzu.

- [Anzeigen](view-documents-in-review-set.md) von Dokumenten, [Abfragedaten](review-set-search.md) und [Tagelementen](tagging-documents.md) in einem Überprüfungssatz.

- [Analysieren Sie Falldaten](analyzing-data-in-review-set.md) mit erweiterten Analysetools.

- [Exportieren Sie Falldaten](exporting-data-ediscover20.md) zur Überprüfung durch externe Rechtsberater.

- [Verwalten lang dauernder Aufträge](managing-jobs-ediscovery20.md) in Advanced eDiscovery.
