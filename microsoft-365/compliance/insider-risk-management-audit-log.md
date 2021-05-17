---
title: Überwachungsprotokoll für insider risk management
description: Erfahren Sie mehr über das Insider-Risikomanagement-Überwachungsprotokoll in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: bda9633ab37fd21fd66b3a8a53d4dd522e48ced1
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "50820273"
---
# <a name="insider-risk-management-audit-log"></a>Überwachungsprotokoll für insider risk management

Das Überwachungsprotokoll des Insider-Risikomanagements ermöglicht Es Ihnen, über die Aktionen auf dem Laufenden zu bleiben, die für Insider-Risikomanagement-Features ergriffen wurden. Dieses Protokoll ermöglicht eine unabhängige Überprüfung der Aktionen von Benutzern, die einer oder mehreren Rollengruppen des Insiderrisikomanagements zugewiesen sind. Das Überwachungsprotokoll für insider risk management wird in Ihrer Organisation automatisch aktiviert und kann nicht deaktiviert werden.

![Überwachungsprotokoll für insider risk management](../media/insider-risk-audit-log.png)

Das Überwachungsprotokoll wird automatisch und sofort aktualisiert, wenn überwachte Aktivitäten auftreten, und das Protokoll behält Informationen über die Aktivität für 180 Tage (ca. sechs Monate) bei. Nach 180 Tagen werden die Daten für die Aktivität endgültig aus dem Protokoll gelöscht.

Zu den Bereichen, die in der Aktivitätsüberwachung enthalten sind, gehören:

- Richtlinien
- Fälle
- Warnungen
- Einstellungen
- Benutzer
- Benachrichtigungsvorlagen

Zum Anzeigen und Exportieren von Daten aus dem Überwachungsprotokoll müssen Benutzer den Rollengruppen *Insider Risk Management* oder Insider Risk Management Auditor *zugewiesen* werden. Weitere Informationen zu Rollengruppen für das Insiderrisikomanagement finden Sie unter Erste Schritte mit insider risk [management Schritt 1: Aktivieren von Berechtigungen](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management).

>[!NOTE]
>Das Überwachungsprotokoll des Insider-Risikomanagements ist nicht dem überwachungsprotokoll Microsoft 365 zugeordnet, sondern es handelt sich um unabhängige Überwachungssysteme, die Informationen zu separaten Aktivitäten erfassen. Das Deaktivieren Microsoft 365 Überwachung wirkt sich nicht auf die Aktivitätsüberwachung innerhalb des Insider-Risikomanagements aus.

## <a name="view-activity-in-the-insider-risk-audit-log"></a>Anzeigen von Aktivitäten im Überwachungsprotokoll für Insiderrisiken

Um feature activity monitored for insider risk management zu sehen, navigieren Sie zu, und wählen Sie den Link **Insider Risk Audit Log** im oberen rechten Bereich der Registerkarte Insider Risk Management aus. Standardmäßig werden die folgenden Informationen für Insider-Risikomanagementaktivitäten angezeigt:

- **Aktivität:** Eine Beschreibung der Aktivitäten, die innerhalb der Insider-Risikomanagement-Lösung von einem Benutzer ergriffen werden.
- **Kategorie:** Der Bereich oder das Element, in dem die Aktivität ausgeführt wurde. Beispielsweise werden Richtlinien als *Kategorie* angezeigt, wenn Richtlinienänderungsaktivitäten ausgeführt wurden.
- **Aktivitäten, die von:** Der Benutzername des Benutzers, der die Aktivität ausgeführt hat.
- **Datum:** Datum und Uhrzeit der Aktivität. Datum und Uhrzeit sind das lokale Datum und die Uhrzeit für Ihre Organisation.

Wenn Sie weitere Informationen zu einer protokollierten Aktivität erhalten, wählen Sie die Aktivität aus, um den Aktivitätsdetailsebereich anzuzeigen. Dieser Bereich enthält zusätzliche Informationen zur Aktivität.

## <a name="columns-and-filtering"></a>Spalten und Filtern

Damit Prüfer die protokollierten Aktivitäten leichter überprüfen können, wird die Filterung im **Überwachungsprotokoll für Insiderrisiken unterstützt.** Für die grundlegende Filterung stehen Warteschlangenspalten zur Verfügung, die der Ansicht hinzugefügt werden können, um unterschiedliche Pivots für die Dateien und Nachrichten zur Verfügung zu stellen. Sie können Aktivitäten nach **Kategorie, Datumsbereich** und Aktivität filtern, **die von Feldern ausgeführt** werden.

Verwenden Sie zum Hinzufügen oder Entfernen von Spaltenüberschriften für die Aktivitätswarteschlange das **Steuerelement** Spalten anpassen, und wählen Sie aus den Spaltenoptionen aus. Diese Spalten werden allgemeinen Bedingungen im Überwachungsprotokoll für **Insiderrisiken** nützt und weiter unten in diesem Artikel aufgeführt.

## <a name="audit-log-export"></a>Export des Überwachungsprotokolls

Benutzer, die den Rollengruppen *Insider Risk Management* oder Insider Risk Management *Auditor* zugewiesen sind, können alle Aktivitäten im Überwachungsprotokoll in eine .csv-Datei (durch Kommas getrennte Werte) exportieren, indem sie **auf** der Seite Insider risk **audit log** exportieren auswählen. Je nach Aktivität sind einige Felder für eine Aktivität möglicherweise nicht auf die Aktivität anwendbar, und diese Felder werden in der exportierten Datei als leer angezeigt.

Die Datei enthält Aktivitätsinformationen für die folgenden Felder:

- **Aktivitäten, die von:** Der Benutzername des Benutzers, der einen Elementwert ändert. Die hier aufgeführten Benutzer wurden einer oder mehreren der folgenden Rollengruppen für insider risk [management](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)zugewiesen: *Insider Risk Management*, Insider Risk Management *Admins*, *Insider Risk Management Analysts*, *Insider Risk Management Investigators*. Jede Rollengruppe verfügt über unterschiedliche Berechtigungsstufen für die Verwaltung von Insiderrisikofeatures.
- **Aktivität:** Die Für ein Element übernommene Aktivität. Die Werte *werden angezeigt, gelöscht, hinzugefügt, bearbeitete Richtlinie, Fall, Benutzer, Warnung* *und Einstellungen.*
- **Hinzugefügt:** Objekte, die während der Aktivität hinzugefügt wurden, z. B. Benutzer, Dateitypen oder Domänen.
- **Warnungsvolumen:** Die In Den Insider-Risikomanagementeinstellungen definierte Warnungsstufe.
- **Betrag**: Die aktuell ausgewählten benutzerdefinierten Indikatorbeträge für eine Richtlinie.
- **Objekt-ID:** Die Ressourcen-ID des physischen Prioritätsvermögens, für das die Aktivität ausgeführt wurde.
- **Kategorie:** Die Kategorie des geänderten Elements. Werte sind *Richtlinien, Fälle, Benutzer, Warnungen, Einstellungen und* *Benachrichtigungsvorlagen.*
- **Datum:** Datum und Uhrzeit, die im lokalen Datum und der Uhrzeit Ihrer Organisation aufgeführt sind.
- **Beschreibung**: Die Beschreibungseingabe des Benutzers für das Objekt, an dem gehandelt wird (z. B. eine Richtlinie oder eine Benutzergruppe mit Priorität).
- **DLP-Richtlinie:** Die Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP), die ausgewählt wurde, um die Aufnahme in eine Insider-Risikomanagementrichtlinie auszulösen.
- **Indikator**: Der Indikator in den Insiderrisikoeinstellungen, für die die Aktivität ausgeführt wurde (z. B. Hinzufügen oder Entfernen eines Indikators).
- **Hinweisvorlage**: Die Benachrichtigungsvorlage, für die die Aktivität ausgeführt wurde.
- **Anzahl der Tage**: Das in Insiderrisikoeinstellungen definierte Richtlinienaktivierungsfenster.
- **Anzahl der Dateien:** Der in den Einstellungen für das Insiderrisikomanagement definierte Dateivolumengrenzwert.
- **Richtlinienvorlage:** Die Richtlinienvorlage, für die die Indikatoren verwendet wurden, gehört dazu.
- **Vorheriger Betrag**: Die zuvor ausgewählten benutzerdefinierten Indikatorbeträge für eine Richtlinie.
- **Benutzergruppe "Priorität":** Die Prioritätsbenutzergruppe, für die die Aktivität ausgeführt wurde.
- **Entfernt:** Objekte, die während der Aktivität entfernt wurden, z. B. Benutzer, Dateitypen oder Domänen.
- **Sender**: Das Absenderfeld der Benachrichtigungsvorlage, für die die Aktivität ausgeführt wurde.
- **Zielrichtlinie:** Die Richtlinie, für die die Aktivität ausgeführt wurde (z. B. Hinzufügen eines Benutzers oder Entfernen eines Benutzers).
- **Nachrichtentext der Vorlage:** Der Nachrichtentext der Benachrichtigungsvorlage, für die die Aktivität ausgeführt wurde.
- **Vorlagenbeschriftung**: Das Betrefffeld der Benachrichtigungsvorlage, für die die Aktivität ausgeführt wurde.
- **Benutzer:** Benutzer, für den die Aktivität ausgeführt wurde.
