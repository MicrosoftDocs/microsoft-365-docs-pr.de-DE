---
title: Anmerkungen zur Version für Daten Untersuchungen (Preview) in Microsoft 365
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
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
description: In diesem Artikel finden Sie Versionshinweise, die Änderungen und neue Features für das Tool zur Datenermittlung (Preview) in Microsoft 365 enthalten.
ms.openlocfilehash: 2a46236d000c62c4ab73f8a47e9c9f661fb17a61
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285411"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a>Anmerkungen zur Version für Daten Untersuchungen (Preview) in Microsoft 365

Sie können das Tool für neue Daten Untersuchungen (Preview) in Microsoft 365 verwenden, um datenbezogene Vorfälle zu selektieren, zu untersuchen und zu beheben, beispielsweise einen Vorfall mit Datenüberlauf oder eine interne Untersuchung. Die öffentliche Vorschau der Daten Untersuchungen bietet Ihnen frühzeitigen Zugriff auf die bevorstehenden Funktionen und Updates. Wenn Sie frühzeitig Zugriff auf die neuesten Funktionen erhalten möchten, erstellen Sie eine neue Untersuchung in Data Investigations (Preview) im Security & Compliance Center. Weitere Informationen finden Sie unter [manage a Data Spilling Incident in Microsoft 365](manage-data-spillage-incidents.md).

## <a name="whats-new"></a>Neuerungen 

- Unter **suchungen** – Sie können Suchvorgänge und Vorfälle gruppieren, indem Sie eine Untersuchung erstellen. Verwalten der Benutzer, die auf die Untersuchung zugreifen können, indem Sie Mitglieder hinzufügen oder entfernen.  Sie können auch Ihre bevorzugten Untersuchungen markieren und kennzeichnen. Verfolgen und Überwachen von Aktivitäten innerhalb und zwischen Untersuchungen mithilfe neuer Dashboards. Nachdem Sie Ihre Untersuchung abgeschlossen haben, können Sie Sie schließen oder löschen.

- **Personen von Interesse** – Wenn Sie Benutzer zu Untersuchungen als interessante Personen hinzufügen, können Sie die Websites Ihres Postfachs, OneDrive für Unternehmen Kontos und Microsoft Teams anzeigen. Sie können Sie verwenden, um Ihre investigativen Inhalts suchen zu bereichern. Um eine Person von Interesse weiter zu untersuchen, können Sie auch Überwachungsdatensätze im Zusammenhang mit ihren Aktivitäten in Microsoft 365 und anderen Microsoft-Diensten anzeigen.

- **Suchen – erstellen** einer organisationsweiten Suche mithilfe verschiedener Suchbedingungen. Wenn Sie Benutzer oder Websites kennen, die Sie durchsuchen möchten, können Sie dies tun, indem Sie diese Benutzer als interessante Personen hinzufügen oder Website Standorte im Assistenten zum Erstellen von Such Standorten angeben. 

- **Evidence** – Erstellen eines neuen Beweissatzes und Hinzufügen von Suchergebnissen, die Sie überprüfen möchten. Sie können einzelne Dokumente überprüfen, mit Anmerkungen versehen, um Ermittlungs Notizen zu hinterlassen, und Ergebnisse exportieren, um in eine andere Umgebung zu gelangen. 

- **Review** – verwenden Sie eine systemeigene, Text-und Near-Native-Ansicht, um die einem Vorfall hinzugefügten Dokumente zu überprüfen. Sie können auch Analysen auf Dokumente anwenden, um Elemente durch Duplikate, e-Mail-Threads und Designs zu gruppieren, die Ihnen bei der Überprüfung des Vorfalls behilflich sein können. 

- **Redact, Tags und Anmerkungen** – Redact Text, wendet Tags an und macht bei der Überprüfung von Dokumenten Anmerkungen.
  
- **Erweiterte Indizierung** – wenn es teilweise indizierte Elemente gibt, werden Sie neu indiziert bei Bedarf sodass alle Daten für die Suche zur Verfügung stehen.

- **Fehler** Korrektur – beheben oder Herunterladen von Verarbeitungsfehlern. Dies umfasst eine Korrektur Unterstützung für große Dateitypen, kennwortgeschützte Dateien und andere Probleme im Zusammenhang mit Indizierungs Fehlern. 

- **Jobs** – Status der lang dauernden Prozesse nachverfolgen.

- **Hartes Löschen von Postfachelementen** -in dringenden Situationen müssen Sie möglicherweise ungültige Elemente dauerhaft löschen. Dazu können Sie den Befehl **New-ComplianceSearchAction-Purge-purgetype HardDelete** in Security & Compliance Center PowerShell ausführen, um Elemente dauerhaft aus Postfächern zu entfernen. Weitere Informationen finden Sie unter [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction).
