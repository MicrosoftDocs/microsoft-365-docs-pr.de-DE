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
description: Verwenden Sie eDiscovery-Fälle im Security & Compliance Center in Office 365, um die rechtliche Untersuchung Ihrer Organisation zu verwalten.
ms.openlocfilehash: c052daab8de33e21cccc3c638ab4995a007f60fb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903459"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Verwalten von rechtlichen Untersuchungen in Microsoft 365

Organisationen haben viele Gründe, auf einen Rechtsstreit mit bestimmten Führungskräften oder anderen Mitarbeitern in Ihrer Organisation zu reagieren. Dies kann die schnelle Suche und Aufbewahrung weiterer untersuchungsspezifischer Informationen in E-Mails, Dokumenten, Chatunterhaltungen und anderen Inhaltsspeicherorten umfassen, die von Personen in ihren täglichen Arbeitsaufgaben verwendet werden. Sie können diese und viele andere ähnliche Aktivitäten mithilfe der eDiscovery-Falltools im Security and Compliance Center ausführen.
  
**Möchten Sie wissen, wie Microsoft seine eDiscovery-Untersuchungen verwaltet?** Hier ist ein technisches [Whitepaper,](https://go.microsoft.com/fwlink/?linkid=852161) das Sie herunterladen können, in dem erläutert wird, wie wir die gleichen Such- und Untersuchungstools verwenden, um unseren internen eDiscovery-Workflow zu verwalten.

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Verwalten rechtlicher Untersuchungen mit eDiscovery-Fällen

Mit eDiscovery-Fällen können Sie steuern, wer eDiscovery-Fälle in Ihrer Organisation erstellen, darauf zugreifen und diese verwalten kann. Verwenden Sie Fälle, um Mitglieder hinzuzufügen und zu steuern, welche Arten von Aktionen sie ausführen können, um inhaltsrelevante Speicherorte für einen Rechtsstreit zu halten und das Tool für die Inhaltssuche zu verwenden, um die Speicherorte im Halteraum nach Inhalten zu durchsuchen, die möglicherweise auf Ihren Fall reagieren. Anschließend können Sie diese Ergebnisse auch zur weiteren Untersuchung durch externe Prüfer exportieren und herunterladen.
  
- [Verwalten Sie Ihren eDiscovery-Workflow,](./get-started-core-ediscovery.md) indem Sie eDiscovery-Fälle für jede rechtliche Untersuchung erstellen und verwenden, die Von Ihrer Organisation durchgeführt werden muss.

- [Weisen Sie eDiscovery-Berechtigungen zu,](assign-ediscovery-permissions.md) um zu steuern, wer eDiscovery-Fälle in Ihrer Organisation erstellen und verwalten kann.

- [Richten Sie Compliancegrenzen ein,](set-up-compliance-boundaries.md) um die Speicherorte von Benutzerinhalten zu steuern, die eDiscovery-Manager durchsuchen können.

- [Suchen Sie nach Inhalten](search-for-content.md) in Ihrer Organisation.

### <a name="use-scripts-for-advanced-scenarios"></a>Verwenden von Skripts für erweiterte Szenarien

Wie im vorherigen Abschnitt, in dem Skripts für Inhaltssuchszenarien aufgeführt wurden, haben wir auch einige Security & Compliance Center PowerShell-Skripts erstellt, die Ihnen bei der Verwaltung von eDiscovery-Fällen helfen.
  
- [Erstellen Sie einen eDiscovery-Haltebericht,](create-a-report-on-holds-in-ediscovery-cases.md) der Informationen zu allen in eDiscovery-Fällen in Ihrer Organisation zugeordneten Halteinformationen enthält.

- [Fügen Sie Postfächer und OneDrive einer](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) Liste von Benutzern zu einem eDiscovery-Archiv hinzu.
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Verwalten rechtlicher Untersuchungen mit der Advanced eDiscovery Lösung in Microsoft 365

Die Advanced eDiscovery-Lösung in Microsoft 365 basiert auf den vorhandenen eDiscovery- und Analysefunktionen in Office 365. Diese neue Lösung mit dem Namen *Advanced eDiscovery* bietet einen End-to-End-Workflow zum Beibehalten, Sammeln, Überprüfen, Analysieren und Exportieren von Inhalten, die auf die internen und externen Ermittlungen Ihrer Organisation abgestimmt sind. Außerdem können Rechtsteams den gesamten Benachrichtigungs-Workflow einsehen, der für juristische Zwecke aufbewahrt wurde, und so mit den an einem Fall beteiligten Verwahrern kommunizieren.

Advanced eDiscovery erfordert ein E5-Abonnement für Microsoft 365 oder Office 365 Organisation. Weitere Informationen zur Lizenzierung finden Sie unter [Einrichten Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

Hier finden Sie eine kurze Übersicht über den integrierten Workflow in Advanced eDiscovery. Weitere Informationen finden Sie unter [Manage the Advanced eDiscovery workflow](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow).

- [Erstellen Sie einen Fall](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) für die ersten Schritte.

- [Verwalten Von](managing-custodians.md) Verwahrern, indem Sie sie zu einem Fall hinzufügen und inhalte in ihrem Postfach, OneDrive konto und Microsoft Teams, in dem sie Mitglieder sind, rechtlich in den Archiven halten.

- [Verwalten sie die](managing-custodian-communications.md) Kommunikation mit Custodians, indem Sie den Benachrichtigungsprozess für die gesetzliche Benachrichtigung automatisieren.

- [Indexieren Von Daten des Verwahrers](processing-data-for-case.md) und Beheben von Indizierungsfehlern, damit Sie effektiv Daten für Ihre Untersuchungen sammeln können.

- [Sammeln Sie Daten](collecting-data-for-ediscovery.md) für einen Fall, und fügen Sie [sie einem Überprüfungssatz zur](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) weiteren Untersuchung hinzu.

- [Anzeigen](view-documents-in-review-set.md) von Dokumenten, [Abfragedaten](review-set-search.md) und [Tagelementen](tagging-documents.md) in einem Überprüfungssatz.

- [Analysieren Sie Falldaten](analyzing-data-in-review-set.md) mit erweiterten Analysetools.

- [Exportieren von Falldaten zur](exporting-data-ediscover20.md) Überprüfung durch externe Berater.

- [Verwalten von Aufträgen mit](managing-jobs-ediscovery20.md) langer Laufzeit in Advanced eDiscovery.