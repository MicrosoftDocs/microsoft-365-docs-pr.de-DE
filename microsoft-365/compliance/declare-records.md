---
title: Datensätzen mithilfe von Aufbewahrungsbezeichnungen deklarieren
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Datensätze mithilfe von Aufbewahrungsbezeichnungen deklarieren.
ms.openlocfilehash: c8024cf08be2259ffa8b6747bebf4943e11e4d60
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695252"
---
# <a name="declare-records-by-using-retention-labels"></a>Datensätzen mithilfe von Aufbewahrungsbezeichnungen deklarieren

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Verwenden Sie [Aufbewahrungsbezeichnungen](retention.md#retention-labels), um Inhalte als Datensätze zu kennzeichnen. Sie können diese Bezeichnungen entweder veröffentlichen, damit Benutzer und Administratoren sie manuell auf Inhalte anwenden können, oder diese Bezeichnungen automatisch auf Inhalte anwenden, die Sie als Datensatz markieren möchten.

## <a name="configuring-retention-labels-to-declare-records"></a>Aufbewahrungsetiketten zum Deklarieren von Datensätzen konfigurieren

Wenn Sie eine [Aufbewahrungsbezeichnung](retention.md#retention-labels)erstellen, wählen Sie die Option aus, um den Inhalt als Datensatz zu markieren.

>[!NOTE] 
> Die Option zum Markieren des Inhalts als Datensatz ist nicht verfügbar, wenn Sie Aufbewahrungsbezeichnungen aus **Information Governance** im Microsoft 365 Compliance Center erstellen oder konfigurieren. Verwenden Sie stattdessen **Datensatzverwaltung**.

1. Gehen Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com) zu **Datensatzverwaltung** \> **Ablageplan**. Wählen Sie von der Seite **Dateiplan** **Eine Bezeichnung erstellen**.

2. Wählen Sie auf der Seite **Bezeichnungseinstellungen** im Assistenten die Option zum Klassifizieren von Inhalten als Datensatz aus.
    
   ![Aktivieren Sie das Kontrollkästchen „Bezeichnung zum Klassifizieren von Inhalt als „Datensatz“ verwenden“](../media/recordversioning6.png)

3. Wenden Sie die Aufbewahrungsbezeichnung nach Bedarf auf SharePoint- oder OneDrive-Dokumente und Exchange-E-Mails an. Für Anweisungen:
    
    - [Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)
    
    - [Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a>Anwenden der konfigurierten Aufbewahrungsbezeichnung auf Inhalte

Wenn Aufbewahrungsbezeichnungen, die Inhalte als Datensatz markieren, Benutzern zur Verfügung gestellt werden, um sie in Apps anzuwenden:

- Bei Exchange kann jeder Benutzer mit Schreibzugriff auf das Postfach diese Bezeichnung anwenden. 
- Bei SharePoint und OneDrive kann jeder Benutzer in der Standardgruppe "Mitglieder" (Berechtigungsstufe "Beitrag") diese Bezeichnung anwenden.

Beispiel für ein Dokument, das mithilfe einer Aufbewahrungsbezeichnung als Datensatz markiert wurde:

![Detailbereich für ein als Datensatz markiertes Dokument](../media/recordversioning7.png)

## <a name="next-steps"></a>Weitere Schritte

Wenn Sie Dokumente aktualisieren müssen, bei denen es sich um Datensätze handelt, lesen Sie [Versionsverwaltung zur Aktualisierung von Datensätzen verwenden, die in Microsoft Office SharePoint Online oder OneDrive gespeichert sind](record-versioning.md).

Mehr zur Löschung von Datensätzen finden Sie unter [Löschung von Inhalten](disposition.md).
