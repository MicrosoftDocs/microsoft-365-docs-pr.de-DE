---
title: Anmerkungen zur Version für Advanced eDiscovery
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
description: Dieser Artikel enthält die Versionshinweise zu Advanced eDiscovery, einschließlich bekannter Probleme, behobener Probleme und neuer Features.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 45a4647856fef0186840ec5465bb9250e5d78de4
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034619"
---
# <a name="release-notes-for-advanced-ediscovery"></a>Anmerkungen zur Version für Advanced eDiscovery

Das Public Preview-Programm für Advanced eDiscovery ist die Möglichkeit, frühzeitig Zugriff auf die bevorstehenden Funktionen und Updates zu erhalten. Um frühzeitig Zugriff auf die neuesten Funktionen zu erhalten, erstellen und verwenden Sie einfach einen erweiterten eDiscovery-Fall im Security & Compliance Center. Weitere Informationen finden Sie unter [Create a New Case](create-new-ediscovery-case.md).

## <a name="known-issues"></a>Bekannte Probleme

**Microsoft Forms**

- Die Daten, die einem Formular entsprechen, das vor dem 31. Januar 2019 erstellt wurde, können nicht durchsucht werden, wenn das Such Tool in Advanced eDiscovery zum Durchsuchen von Depot Postfächern verwendet wird. Formulare, die nach diesem Datum erstellt wurden, stehen für die Suche zur Verfügung.

- Ein von einem Benutzer erstelltes Formular kann weiterhin Antworten erhalten, auch wenn der Benutzer, der das Formular erstellt hat, gelöscht wird. Die entsprechenden Daten für diese Antworten (die nach dem Löschen des Depot Postfachs aufgetreten sind) sind jedoch nicht durchsuchbar, wenn Sie das Such Tool in Advanced eDiscovery zum Durchsuchen von Depot Postfächern verwenden.
 
**Microsoft Sway**

- Wenn ein Benutzer ein Sway unmittelbar vor dem Löschen des Benutzerkontos für den Besitzer dieses Sways bearbeitet, sind diese Änderungen möglicherweise nicht durchsuchbar, wenn das Such Tool in Advanced eDiscovery zum Durchsuchen von Depot Postfächern verwendet wird. Sway Blocks ändert sich in ein Sway, sobald ein Signal empfangen wird, dass das Konto gelöscht wurde. Es gibt jedoch eine kleine Chance, dass ein Sway bearbeitet werden kann, bevor dieses Signal empfangen wird.

## <a name="issues-fixed-in-this-release"></a>In dieser Version behobene Probleme

- DCR: Ausnahmebehandlung für nicht indizierte Elemente und verwaiste Elemente
- DCR: Benachrichtigungen halten
- DCR: Verwalter in eDiscovery

## <a name="whats-new"></a>Neuerungen

- Neu **gestaltete Navigation im Security & Compliance Center** – Advanced eDiscovery hat ein neues Aussehen und Verhalten. Verwenden Sie Advanced eDiscovery, um einen größeren Teil Ihres Fall Workflows zu verwalten.

- **Case Management** – zusätzliche Unterstützung für neue Falltypen. Sie können auch Ihre aktuellen und bevorzugten Fälle auswählen und speichern. Verfolgen und Überwachen von Aktivitäten innerhalb und über mehrere Fälle mithilfe neuer Dashboards.

- **Depotverwaltung** – hinzufügen und Entfernen von Benutzern als Datenverwalter in einem Fall.

- **Exchange-, OneDrive-und** Microsoft Teams-Integration – fügen Sie einem Fall automatisch das aktuelle Postfach des Benutzers, das OneDrive für Unternehmen-Konto und die Microsoft Teams-Websites hinzu. 

- **Depotbank Communications** – senden und Verwalten von Benachrichtigungen über rechtliche Aufbewahrungsdaten im Namen Ihrer Organisation.

- **Depot Portal** – neues Portal für depotverwalter für den Zugriff auf Ihre aktiven Aufbewahrungs Benachrichtigungen.

- **Deep Indexing** – erneutes durchforsten von teilweise indizierten Elementen bei Bedarf.

- **Fehler** Korrektur – beheben oder Herunterladen von Verarbeitungsfehlern; Dies umfasst die Korrektur Unterstützung für große Dateitypen, kennwortgeschützte Dateien und vieles mehr. 

- **Verbesserungen bei der Suche** – erstellen Sie eine Suche, indem Sie Verwalter und/oder Standorte identifizieren.

- **Überprüfen von Sätzen** – verwalten, nachverfolgen und Überwachen von statischen Dokumentensätzen.

- **Review** – verwenden Sie eine systemeigene, Text-und Near-Native-Ansicht, um Dokumente zu überprüfen, die Ihrem Überprüfungs hinzugefügt wurden.

- **Redact, Tags und Anmerkungen** – Redact Text, wendet Tags an und macht bei der Überprüfung von Dokumenten Anmerkungen.
  
- **Analyse-powered Review**– nutzen Sie die erweiterte eDiscovery-Analyse, um Ergebnisse innerhalb eines Überprüfungs Satzes zu suchen, zu suchen und zu cullieren.

- **Jobs** – Status der lang dauernden Prozesse nachverfolgen.

- **Neue Überwachungsaktivitäten** – verfolgen und Anzeigen neuer Überwachungsaktivitäten für erweiterte eDiscovery.
