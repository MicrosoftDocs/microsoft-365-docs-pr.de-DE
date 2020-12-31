---
title: Hinzufügen von Datenquellen ohne Freiheitsentzug zu einem erweiterten eDiscovery-Fall
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
description: Sie können einem erweiterten eDiscovery-Fall Datenquellen ohne Freiheitsentzug hinzufügen und die Datenquelle aufbewahren. Datenquellen ohne Freiheitsentzug werden neu indiziert, sodass alle Inhalte, die als teilweise indiziert markiert wurden, neu verarbeitet werden, damit Sie vollständig und schnell durchsuchbar sind.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740352"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>Hinzufügen von Datenquellen ohne Freiheitsentzug zu einem erweiterten eDiscovery-Fall

In erweiterten eDiscovery-Fällen erfüllt es nicht immer Ihre Anforderungen, um eine Microsoft 365-Datenquelle mit einer Depotbank in dem Fall zuzuordnen. Möglicherweise müssen Sie diese Daten aber dennoch einem Fall zuordnen, damit Sie Sie durchsuchen, zu einem Überprüfungs Satzes hinzufügen und analysieren und überprüfen können. Das Feature in Advanced eDiscovery wird als *nicht-Freiheits Zeichen-Datenquellen* bezeichnet und ermöglicht es Ihnen, einem Fall Daten hinzuzufügen, ohne ihn einer Depotbank zuordnen zu müssen. Sie wendet auch die gleiche erweiterte eDiscovery-Funktionalität auf nicht-Freiheitsentzug-Daten an, die für mit der Depotbank verbundene Daten verfügbar sind. Zwei der nützlichsten Dinge, die Sie auf Daten ohne Freiheitsentzug anwenden können, sind das aufbewahren und das verarbeiten mit der [erweiterten Indizierung](indexing-custodian-data.md).

## <a name="add-a-non-custodial-data-source"></a>Hinzufügen einer Datenquelle ohne Freiheitsentzug

Führen Sie die folgenden Schritte aus, um Datenquellen ohne Freiheitsentzug in einem erweiterten eDiscovery-Fall hinzuzufügen und zu verwalten.

1. Klicken Sie auf der Seite für die **Erweiterte eDiscovery** -Homepage auf den Fall, dem Sie die Daten hinzufügen möchten.

2. Klicken Sie auf die Registerkarte **Datenquellen** , und klicken Sie dann auf Daten **Quelle** Hinzufügen von  >  **Datenspeicherorten**.

3. Wählen Sie auf der Seite Neues Flyout für **Datenspeicherorte ohne Freiheits** Zeichen die Datenquellen aus, die Sie der Anfrage hinzufügen möchten. Sie können mehrere Postfächer und Websites hinzufügen, indem Sie die **SharePoint** -oder **Exchange** -Abschnitte erweitern und dann auf **Bearbeiten** klicken.

   ![Hinzufügen von SharePoint-Websites und Exchange-Postfächern zu Datenquellen ohne Freiheitsentzug](../media/NonCustodialDataSources1.png)

   - **SharePoint** – klicken Sie auf **Bearbeiten** , um Websites hinzuzufügen. Wählen Sie eine Website in der Liste aus, oder suchen Sie nach einer Website, indem Sie die URL der Website in die Suchleiste eingeben. Wählen Sie die Websites aus, die Sie als nicht-Depotbank-Datenquellen hinzufügen möchten, und klicken Sie auf **Hinzufügen**.

   - **Exchange** – klicken Sie auf **Bearbeiten** , um Postfächer hinzuzufügen. Geben Sie einen Namen oder einen Alias (mindestens drei Zeichen) für Postfächer oder Verteilergruppen in das Suchfeld ein. Wählen Sie die Postfächer aus, die Sie als nicht-Depotbank-Datenquellen hinzufügen möchten, und klicken Sie auf **Hinzufügen**.

   > [!NOTE]
   > Sie können die **SharePoint** -und **Exchange** -Abschnitte zum Hinzufügen von Websites und Postfächern verwenden, die einem Team oder einer Gruppe "jammern" als Datenquellen ohne Freiheitsentzug zugeordnet sind. Sie müssen das Postfach und die Website, die einem Team oder einer Gruppe von jammern zugeordnet sind, separat hinzufügen.

4. Nachdem Sie Datenquellen ohne Freiheitsentzug hinzugefügt haben, haben Sie die Möglichkeit, diese Speicherorte in der Warteschleife zu platzieren oder nicht. Aktivieren oder deaktivieren Sie das Kontrollkästchen **halten** neben der Datenquelle, um es in die Warteschleife zu versetzen.

5. Klicken Sie unten auf der Flyout-Seite für **neue Datenspeicherorte ohne Freiheitsentzug** auf **Hinzufügen** , um die Datenquellen dem Fall hinzuzufügen.

   Jede Datenquelle ohne Freiheits Schutz, die Sie hinzugefügt haben, wird auf der Seite **Datenquellen** aufgeführt. Datenquellen ohne Freiheitsentzug werden durch den Wert **Datenspeicherort** in der Spalte **Quelltyp** identifiziert.

   ![Datenquellen ohne Freiheitsentzug auf der Registerkarte Datenquellen](../media/NonCustodialDataSources2.png)

Nachdem Sie dem Fall Datenquellen ohne Freiheitsentzug hinzugefügt haben, wird ein Auftrag mit dem Namen " *Neuindizieren von nicht-Freiheitsentzug-Daten* " erstellt und auf der Registerkarte " **Aufträge** " der Groß-/Kleinschreibung angezeigt. Nachdem der Auftrag erstellt wurde, wird der erweiterte Indizierungsprozess in initiiert und die Datenquellen neu indiziert.

## <a name="manage-the-hold-for-non-custodial-data-sources"></a>Verwalten der Aufbewahrungszeit für Datenquellen ohne Freiheitsentzug

Nachdem Sie eine Datenquelle ohne Freiheitsentzug gespeichert haben, wird automatisch eine Aufbewahrungsrichtlinie erstellt, die die Datenquellen ohne Freiheits Schutz für den Fall enthält. Wenn Sie andere Datenquellen ohne Freiheitsentzug in die Warteschleife setzen, werden Sie dieser Aufbewahrungsrichtlinie hinzugefügt.

1. Öffnen Sie den erweiterten eDiscovery-Fall, und wählen Sie die Registerkarte **halten** aus.

2. Klicken Sie auf **NCDSHold- \<GUID\>**, wobei der GUID-Wert für den Fall eindeutig ist.

   Auf der Flyout-Seite werden Informationen und Statistiken zu den nicht-Freiheits geschützten Datenquellen in der Warteschleife angezeigt.

   ![Die Flyout-Seite für Datenquellen ohne Freiheitsentzug zeigt Statistiken an](../media/NonCustodialDataSourcesHoldFlyout.png)

3. Klicken Sie auf Speicher **Bearbeiten** , um die Datenquellen ohne Freiheitsentzug anzuzeigen, die in der Warteschleife gespeichert sind, und führen Sie die folgenden Verwaltungsaufgaben aus:

   - Auf der Seite **Speicherorte** können Sie eine Datenquelle ohne Freiheitsentzug freigeben, indem Sie Sie aus dem Haltestatus entfernen. Durch das Freigeben einer Datenquelle wird nicht die Datenquelle ohne Freiheitsentzug aus dem Fall entfernt. Es entfernt nur den Haltebereich, der in der Datenquelle eingefügt wurde.

   - Auf der Seite **Abfrage** können Sie den Haltebereich bearbeiten, um einen abfragebasierten Haltebereich zu erstellen, der auf alle Tha-nicht-Freiheits Zeichen-Datenquellen in dem Fall angewendet wird.
