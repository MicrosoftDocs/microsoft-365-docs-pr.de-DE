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
ROBOTS: NOINDEX, NOFOLLOW
description: Sie können einem erweiterten eDiscovery-Fall Datenquellen ohne Freiheitsentzug hinzufügen und die Datenquelle aufbewahren. Datenquellen ohne Freiheitsentzug werden erneut indiziert, sodass alle Inhalte, die als teilweise indiziert betrachtet wurden, erneut verarbeitet werden, damit Sie vollständig und schnell durchsuchbar sind.
ms.openlocfilehash: 618d39bfb7be6cd260c88cdf4c57501747f440f1
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695500"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>Hinzufügen von Datenquellen ohne Freiheitsentzug zu einem erweiterten eDiscovery-Fall

In erweiterten eDiscovery-Fällen erfüllt es nicht immer Ihre Anforderungen, um eine Microsoft 365-Datenquelle mit einer Depotbank in dem Fall zuzuordnen. Möglicherweise müssen Sie diese Daten jedoch dennoch einem Fall zuordnen, damit Sie Sie durchsuchen, Sie zu Überprüfungs Sätzen hinzufügen und überprüfen können. Mit dem neuen Feature " *nicht-Freiheits geschützte Datenquellen* " können Sie Daten zu einem Fall hinzufügen, ohne die Daten einer Depotbank zuordnen zu müssen. Sie wendet auch die gleiche erweiterte eDiscovery-Funktionalität auf nicht-Freiheitsentzug-Daten an, die für mit der Depotbank verbundene Daten verfügbar sind. Zwei der nützlichsten Funktionen, die Sie auf Daten ohne Freiheitsentzug anwenden können, sind das aufbewahren und das verarbeiten mit der [erweiterten Indizierung](indexing-custodian-data.md).

## <a name="add-a-non-custodial-data-source"></a>Hinzufügen einer Datenquelle ohne Freiheitsentzug

Führen Sie die folgenden Schritte aus, um Datenquellen ohne Freiheitsentzug in einem erweiterten eDiscovery-Fall hinzuzufügen und zu verwalten.

1. Klicken Sie auf der Seite für die **Erweiterte eDiscovery** -Homepage auf den Fall, dem Sie die Daten hinzufügen möchten.

2. Klicken Sie auf der Seite **Quellen** auf die Registerkarte **Datenspeicherorte** , und klicken Sie dann auf **Datenspeicherort hinzufügen**.

3. Klicken Sie auf **Datenspeicherort hinzufügen** , und wählen Sie die Datenquellen aus, die der Anfrage hinzugefügt werden sollen. Sie können mehrere Postfächer und Websites hinzufügen.

4. Fügen Sie auf der Seite **Speicherorte auswählen** des Assistenten Postfächer oder Websites (oder beides) als Datenquellen ohne Freiheitsentzug für den Fall hinzu.

5. Klicken Sie nach dem Hinzufügen der Datenquellen auf **weiter**.

6. Wählen Sie auf der Seite **Platz Haltestatus** die Datenquellen aus, die Sie speichern möchten, indem Sie das zugehörige Kontrollkästchen auswählen oder aufheben.

7. Überprüfen Sie die Aufbewahrungsoptionen, und klicken Sie dann auf **senden**.

   Jede Datenquelle ohne Freiheits Schutz, die Sie hinzugefügt haben, wird auf der Seite **Datenquellen** aufgeführt.

   Außerdem wird ein Auftrag mit dem Namen " *re-Indexing Non-Freiheitsentzug Data* " erstellt und auf der Registerkarte " **Aufträge** " der Groß-/Kleinschreibung angezeigt. Nachdem der Auftrag erstellt wurde, wird der erweiterte Indizierungsprozess in initiierten und den Datenquellen neu indiziert.

## <a name="managing-the-hold-on-non-custodial-data-sources"></a>Verwalten der Aufbewahrungszeit für Datenquellen ohne Freiheitsentzug

Nachdem Sie eine Datenquelle ohne Freiheitsentzug gespeichert haben, wird automatisch eine Aufbewahrungsrichtlinie erstellt, die alle Datenquellen ohne Freiheits Schutz für den Fall enthält. Wenn Sie zusätzliche Datenquellen ohne Freiheitsentzug speichern, werden Sie dieser Aufbewahrungsrichtlinie hinzugefügt.

1. Klicken Sie auf der **Start** Seite der Anfrage auf die Registerkarte halte **Status** .

2. Auf der Seite halte **Status** , und klicken Sie auf **NCDSHold- \<GUID\> **, wobei der GUID-Wert für den Fall eindeutig ist.

3. Klicken Sie auf der Flyout-Seite auf **Haltestatus bearbeiten** , um alle Datenquellen ohne Freiheitsentzug anzuzeigen, die in der Warteschleife gespeichert werden.

Sie können die folgende Verwaltungsaufgabe für Datenquellen ohne Freiheitsentzug ausführen:

- Sie können den Haltebereich bearbeiten, um einen abfragebasierten Haltebereich zu erstellen, der für alle Datenquellen ohne Freiheitsentzug in dem Fall verwendet wird.

- Sie können eine Datenquelle ohne Freiheitsentzug aus dem Haltestatus freigeben. Durch das Freigeben einer Datenquelle wird nicht die Datenquelle ohne Freiheitsentzug aus dem Fall entfernt. Es entfernt nur den Haltebereich, der in der Datenquelle eingefügt wurde.
