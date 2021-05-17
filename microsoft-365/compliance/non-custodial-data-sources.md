---
title: Hinzufügen nicht verwahrter Datenquellen zu einem Advanced eDiscovery Fall
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
description: Sie können einem fall nicht verwahrten Datenquellen Advanced eDiscovery hinzufügen und die Datenquelle speichern. Nicht verwahrbare Datenquellen werden neu indiziert, sodass alle Inhalte, die als teilweise indiziert markiert wurden, erneut verarbeitet werden, um sie vollständig und schnell durchsuchbar zu machen.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740352"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>Hinzufügen nicht verwahrter Datenquellen zu einem Advanced eDiscovery Fall

In Advanced eDiscovery erfüllt es nicht immer Ihre Anforderungen, eine Microsoft 365 datenquelle einem Custodian in dem Fall zuzuordnen. Möglicherweise müssen Sie diese Daten jedoch einem Fall zuordnen, damit Sie sie durchsuchen, einem Überprüfungssatz hinzufügen und analysieren und überprüfen können. Das Feature in Advanced eDiscovery wird  als nicht verwahrte Datenquellen bezeichnet und ermöglicht es Ihnen, einem Fall Daten hinzuzufügen, ohne sie einem Verwahrer zuordnen zu müssen. Es wendet auch die Advanced eDiscovery auf nicht verwahrte Daten an, die für Daten verfügbar sind, die mit dem Custodian verknüpft sind. Zwei der nützlichsten Dinge, die Sie auf nicht verwahrbare Daten anwenden können, besteht in der Inhaftierung und Verarbeitung dieser Daten mithilfe der [erweiterten Indizierung.](indexing-custodian-data.md)

## <a name="add-a-non-custodial-data-source"></a>Hinzufügen einer nicht verwahrten Datenquelle

Führen Sie die folgenden Schritte aus, um nicht verwahrte Datenquellen in einem Fall hinzuzufügen und Advanced eDiscovery verwalten.

1. Klicken Sie **Advanced eDiscovery** Startseite auf den Fall, dem Sie die Daten hinzufügen möchten.

2. Klicken Sie **auf die** Registerkarte Datenquellen, und klicken Sie dann auf Datenquelle **hinzufügen**  >  **Speicherorte hinzufügen.**

3. Wählen Sie **auf** der Flyoutseite Neue nicht verwahrte Datenspeicherorte die Datenquellen aus, die Sie dem Fall hinzufügen möchten. Sie können mehrere Postfächer und Websites hinzufügen, indem Sie die SharePoint **oder** **Exchange** erweitern und dann auf **Bearbeiten klicken.**

   ![Hinzufügen SharePoint Websites und Exchange Postfächern als nicht verwahrte Datenquellen](../media/NonCustodialDataSources1.png)

   - **SharePoint** – Klicken **Sie auf Bearbeiten,** um Websites hinzuzufügen. Wählen Sie eine Website in der Liste aus, oder Sie können nach einer Website suchen, indem Sie die URL der Website in die Suchleiste eingeben. Wählen Sie die Websites aus, die Sie als datenquellenfrei hinzufügen möchten, und klicken Sie auf **Hinzufügen**.

   - **Exchange** - Klicken Sie **auf Bearbeiten,** um Postfächer hinzuzufügen. Geben Sie einen Namen oder Alias (mindestens drei Zeichen) in das Suchfeld für Postfächer oder Verteilergruppen ein. Wählen Sie die Postfächer aus, die Sie als nicht verwahrerische Datenquellen hinzufügen möchten, und klicken Sie auf **Hinzufügen**.

   > [!NOTE]
   > Sie können die Abschnitte **SharePoint** und **Exchange** verwenden, um Websites und Postfächer hinzuzufügen, die einem Team oder einer Yammer-Gruppe als nicht verwahrte Datenquellen zugeordnet sind. Sie müssen das Postfach und die Website, die einem Team oder einer Gruppe zugeordnet sind, Yammer hinzufügen.

4. Nachdem Sie nicht verwahrte Datenquellen hinzugefügt haben, haben Sie die Möglichkeit, diese Speicherorte in der Warteschleife zu platzieren oder nicht. Aktivieren oder deaktivieren Sie das **Kontrollkästchen Halten** neben der Datenquelle, um es in der Warteschleife zu platzieren.

5. Klicken **Sie** unten auf der Flyoutseite Neue nicht **verwahrte** Datenspeicherorte auf Hinzufügen, um dem Fall die Datenquellen hinzuzufügen.

   Jede nicht verwahrte Datenquelle, die Sie hinzugefügt haben, wird auf der Seite **Datenquellen** aufgeführt. Nicht verwahrte Datenquellen  werden durch den Datenspeicherortwert in der **Spalte Quelltyp** identifiziert.

   ![Nicht verwahrte Datenquellen auf der Registerkarte Datenquellen](../media/NonCustodialDataSources2.png)

Nachdem Sie dem Fall nicht verwahrte Datenquellen hinzugefügt haben, wird ein Auftrag mit  dem Namen *Reindexing non-custodial data* erstellt und auf der Registerkarte Aufträge des Falls angezeigt. Nachdem der Auftrag erstellt wurde, wird der erweiterte Indizierungsprozess in initiiert und die Datenquellen neu indiziert.

## <a name="manage-the-hold-for-non-custodial-data-sources"></a>Verwalten des Halteraums für nicht verwahrte Datenquellen

Nachdem Sie eine Nicht-Verwahrer-Datenquelle gespeichert haben, wird automatisch eine Halterichtlinie erstellt, die die nicht verwahrten Datenquellen für den Fall enthält. Wenn Sie andere nicht verwahrte Datenquellen in der Warteschleife platzieren, werden sie dieser Halterichtlinie hinzugefügt.

1. Öffnen Sie Advanced eDiscovery Fall, und wählen Sie die Registerkarte **Halten** aus.

2. Klicken **Sie auf \<GUID\> NCDSHold-**, wobei der GUID-Wert für den Fall eindeutig ist.

   Auf der Flyoutseite werden Informationen und Statistiken zu nicht verwahrten Datenquellen angezeigt.

   ![Die Flyoutseite für nicht verwahrte Datenquellen zeigt Statistiken an.](../media/NonCustodialDataSourcesHoldFlyout.png)

3. Klicken **Sie auf Halteraum** bearbeiten, um die nicht verwahrbaren Datenquellen zu sehen, die in der Warteschleife gespeichert sind, und führen Sie die folgenden Verwaltungsaufgaben aus:

   - Auf der **Seite Speicherorte** können Sie eine nicht verwahrte Datenquelle los, indem Sie sie aus dem Halteraum entfernen. Durch das Freigeben einer Datenquelle wird die nicht verwahrte Datenquelle nicht aus dem Fall entfernt. Es wird nur der Halteraum entfernt, der für die Datenquelle platziert wurde.

   - Auf der **Seite Abfrage** können Sie den Haltemodus bearbeiten, um einen abfragebasierten Haltemodus zu erstellen, der in diesem Fall auf alle nicht verwahrbaren Datenquellen angewendet wird.
