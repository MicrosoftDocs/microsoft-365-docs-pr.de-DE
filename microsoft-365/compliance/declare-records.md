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
ms.openlocfilehash: ba0587619609adba2d7746a45a3b24008a4a00be
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226995"
---
# <a name="declare-records-by-using-retention-labels"></a>Datensätzen mithilfe von Aufbewahrungsbezeichnungen deklarieren

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Um Dokumente und E-Mails als [Datensatz](records-management.md#records) zu deklarieren, verwenden Sie [Aufbewahrungsbezeichnungen](retention.md#retention-labels), die Elemente als **Datensatz** oder **regulatorischen Datensatz** markieren.

Wenn Sie nicht sicher sind, ob Sie einen Datensatz oder regulatorischen Datensatz verwenden sollen, lesen Sie [Vergleichen von Einschränkungen für die zulässigen und blockierten Aktionen](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked). Wenn Sie regulatorischen Datensatz verwenden müssen, müssen Sie zuerst einen PowerShell-Befehl ausführen, wie im nächsten Abschnitt beschrieben.

Danach können Sie diese Bezeichnungen entweder in einer Aufbewahrungsrichtlinie veröffentlichen (sodass Benutzer und Administratoren diese manuell auf Inhalte anwenden können) oder für Bezeichnungen, mit denen Elemente als Datensätze markiert werden. Wenden Sie diese Bezeichnungen automatisch auf Inhalte an, die Sie als Datensatz deklarieren möchten.

## <a name="how-to-display-the-option-to-mark-content-as-a-regulatory-record"></a>So zeigen Sie die Option zum Markieren von Inhalten als regulatorischen Datensatz an

> [!NOTE]
> Bei dem folgenden Verfahren handelt es sich um eine überwachbare Aktion, die Protokollierung **Option für die Festlegung von Auflagen für Aufbewahrungsbezeichnungen** im Abschnitt [Aufbewahrungsrichtlinie und Aufbewahrungsaktivitäten](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) des Überwachungsprotokolls.

Standardmäßig wird die Aufbewahrungsbezeichnungsoption zum Markieren von Inhalten als regulatorischer Datensatz im Aufbewahrungsbezeichnungs-Assistenten nicht angezeigt. Wenn Sie diese Option anzeigen möchten, müssen Sie zuerst einen PowerShell-Befehl ausführen:

1. [Herstellen einer Verbindung mit der Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

2. Führen Sie das folgende Cmdlet aus:

    ```powershell
    Set-RegulatoryComplianceUI -Enabled $true
    ````

    Es wird keine Bestätigung angezeigt, und die Einstellung wird sofort wirksam.

Wenn Sie es sich anders überlegen, können Sie sie erneut ausblenden, indem Sie dasselbe Cmdlet mit dem Wert **false** ausführen: `Set-RegulatoryComplianceUI -Enabled $false`

## <a name="configuring-retention-labels-to-declare-records"></a>Aufbewahrungsbezeichnugen zum Deklarieren von Datensätzen konfigurieren

Wenn Sie eine Aufbewahrungsbezeichnung aus der **Datensatzverwaltung**-Lösung im Microsoft 365 Compliance Center erstellen oder bearbeiten, haben Sie die Option zum Markieren von Elementen als Datensatz. Wenn Sie den PowerShell-Befehl aus dem vorherigen Abschnitt ausgeführt haben, können Sie alternativ Elemente als regulatorischen Datensatz festlegen.

Zum Beispiel:

![Konfigurieren einer Aufbewahrungsbezeichnung zum Markieren von Inhalten als Datensatz oder regulatorisch](../media/recordversioning6.png)

Wenden Sie die Aufbewahrungsbezeichnung nach Bedarf auf Microsoft Office SharePoint Online oder OneDrive-Dokumente und Exchange-E-Mails an.

Vollständige Anweisungen:

- [Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)

- [Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md) (wird bei regulatorischen Datensätzen nicht unterstützt)


## <a name="applying-the-configured-retention-label-to-content&quot;></a>Anwenden der konfigurierten Aufbewahrungsbezeichnung auf Inhalte

Wenn Aufbewahrungsbezeichnungen, die Inhalte als Datensatz oder regulatorischen Datensatz markieren, Benutzern zur Verfügung gestellt werden, um sie in Apps anzuwenden:

- Bei Exchange kann jeder Benutzer mit Schreibzugriff auf das Postfach diese Bezeichnung anwenden.
- Bei SharePoint und OneDrive kann jeder Benutzer in der Standardgruppe &quot;Mitglieder&quot; (Berechtigungsstufe &quot;Beitrag") diese Bezeichnung anwenden.

Beispiel für ein Dokument, das mithilfe einer Aufbewahrungsbezeichnung als Datensatz markiert wurde:

![Detailbereich für ein als Datensatz markiertes Dokument](../media/recordversioning7.png)

## <a name="searching-the-audit-log-for-labeled-items-that-were-declared-records"></a>Durchsuchen des Überwachungsprotokolls auf gekennzeichnete Elemente, die als Datensätze deklariert wurden.

Die Aktionen der Kennzeichnung, um Elemente als Datensätze zu deklarieren, werden im Überwachungsprotokoll festgeschrieben.

Für SharePoint-Elemente:
- Wählen Sie aus **Datei- und Seiten-Aktivitäten** die Option **Geänderte Aufbewahrungsbezeichnung für eine Datei** aus. Dieses Überwachungsereignis wird für Aufbewahrungsbezeichnungen angewendet, die Elemente als Datensätze oder regulatorische Datensätze markieren, oder die Standard-Aufbewahrungsbezeichnungen sind.

Für Exchange-Elemente:
- Wählen Sie aus den **Exchange-Postfachaktivitäten** die Option **Gekennzeichnete Nachricht als ein Datensatz**. Dieses Überwachungsereignis wird für Aufbewahrungsbezeichnungen angewendet, die Elemente als Datensätze oder regulatorische Datensätze markieren.

Weitere Informationen für die Suche nach diesen Ereignissen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).

## <a name="next-steps"></a>Weitere Schritte

Eine Liste von Szenarios, die von der Datensatzverwaltung unterstützt werden, finden Sie unter [Häufige Szenarios für die Datensatzverwaltung](get-started-with-records-management.md#common-scenarios-for-records-management).
