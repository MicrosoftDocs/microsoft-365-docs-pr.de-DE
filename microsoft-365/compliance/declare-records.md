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
ms.openlocfilehash: 841c5197addff704016e344ba7ae44355c872f72
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817101"
---
# <a name="declare-records-by-using-retention-labels"></a>Datensätzen mithilfe von Aufbewahrungsbezeichnungen deklarieren

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Um Dokumente und E-Mails als Datensatz zu deklarieren, verwenden Sie [Aufbewahrungsbezeichnungen](retention.md#retention-labels), die Elemente als Datensatz markieren. Sie können diese Bezeichnungen entweder veröffentlichen, damit Benutzer und Administratoren sie manuell auf Inhalte anwenden können, oder diese Bezeichnungen automatisch auf Inhalte anwenden, die Sie als Datensatz markieren möchten.

## <a name="configuring-retention-labels-to-declare-records"></a>Aufbewahrungsetiketten zum Deklarieren von Datensätzen konfigurieren

Wenn Sie eine Aufbewahrungsbezeichnung erstellen oder konfigurieren, wählen Sie die Option aus, um Elemente als Datensatz zu markieren.

>[!NOTE] 
> Die Option zum Markieren des Inhalts als Datensatz ist nicht verfügbar, wenn Sie Aufbewahrungsbezeichnungen aus **Information Governance** im Microsoft 365 Compliance Center erstellen oder konfigurieren. Verwenden Sie stattdessen **Datensatzverwaltung**.

So erstellen Sie eine neue Aufbewahrungsbezeichnung, die den Inhalt als Datensatz kennzeichnet:

1. Gehen Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com) zu **Datensatzverwaltung** \> **Ablageplan**. Wählen Sie von der Seite **Dateiplan** **Eine Bezeichnung erstellen**.

2. Wählen Sie im Assistenten auf der Seite **Aufbewahrungseinstellungen definieren** die Option, Elemente als Datensätze festzulegen:
    
   ![Wählen Sie die Aufbewahrungseinstellung aus, um Elemente als Datensatz zu markieren](../media/recordversioning6.png)

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

Eine Liste von Szenarios, die von der Datensatzverwaltung unterstützt werden, finden Sie unter [Häufige Szenarios für die Datensatzverwaltung](get-started-with-records-management.md#common-scenarios-for-records-management).
