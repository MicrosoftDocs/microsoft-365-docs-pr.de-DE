---
title: Überwachungsprotokoll für Insider-Risikomanagement
description: Erfahren Sie mehr über das Überwachungsprotokoll des Insider-Risikomanagements in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Compliance
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
ms.openlocfilehash: b7eb225f04f531c3b6de71bf72df0f8062a8c93d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226503"
---
# <a name="insider-risk-management-audit-log"></a>Überwachungsprotokoll für Insider-Risikomanagement

Das Überwachungsprotokoll des Insider-Risikomanagements ermöglicht es Ihnen, über die Aktionen zu informieren, die mit Features des Insider-Risikomanagements durchgeführt wurden. Dieses Protokoll ermöglicht eine unabhängige Überprüfung der Aktionen von Benutzern, die einer oder mehreren Rollengruppen des Insider-Risikomanagements zugewiesen sind. Das Überwachungsprotokoll des Insider-Risikomanagements wird in Ihrer Organisation automatisch aktiviert und kann nicht deaktiviert werden.

![Überwachungsprotokoll für Insider-Risikomanagement](../media/insider-risk-audit-log.png)

Das Überwachungsprotokoll wird automatisch und sofort aktualisiert, wenn überwachte Aktivitäten auftreten, und das Protokoll speichert Informationen über die Aktivität 180 Tage lang (ca. sechs Monate). Nach 180 Tagen werden die Daten für die Aktivität dauerhaft aus dem Protokoll gelöscht.

Zu den Bereichen der Aktivitätsüberwachung gehören:

- Richtlinien
- Fällen
- Warnungen
- Einstellungen
- Benutzer
- Benachrichtigungsvorlagen

Um Daten aus dem Überwachungsprotokoll anzuzeigen und zu exportieren, müssen die Benutzer den Rollengruppen *"Insider-Risikomanagement"* oder *"Auditoren für Insider-Risikomanagement"* zugewiesen werden. Weitere Informationen zu Rollengruppen für das Insider-Risikomanagement finden Sie unter ["Erste Schritte mit Dem Insider-Risikomanagement Schritt 1: Aktivieren von Berechtigungen".](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)

> [!NOTE]
> Das Überwachungsprotokoll des Insider-Risikomanagements ist nicht mit dem Microsoft 365 Überwachungsprotokoll verknüpft, es handelt sich um unabhängige Überwachungssysteme und erfasst Informationen zu separaten Aktivitäten. Das Deaktivieren Microsoft 365 Überwachung wirkt sich nicht auf die Aktivitätsüberwachung innerhalb des Insider-Risikomanagements aus.

## <a name="view-activity-in-the-insider-risk-audit-log"></a>Anzeigen von Aktivitäten im Überwachungsprotokoll für Insider-Risiken

Navigieren Sie zum Anzeigen von Featureaktivitäten, die für das Insider-Risikomanagement überwacht werden, und wählen Sie den Link **"Überwachungsprotokoll für Insider-Risiken"** oben rechts auf jeder Registerkarte "Insider-Risikomanagement" aus. Standardmäßig werden die folgenden Informationen für Insider-Risikomanagementaktivitäten angezeigt:

- **Aktivität:** Eine Beschreibung der Aktivität, die ein Benutzer innerhalb der Insider-Risikomanagementlösung ausgeführt hat.
- **Kategorie:** Der Bereich oder das Element, in dem die Aktivität ausgeführt wurde. Beispielsweise werden *Richtlinien* als Kategorie angezeigt, wenn Richtlinienänderungsaktivitäten ausgeführt wurden.
- **Aktivität, die von:** Der Benutzername des Benutzers, der die Aktivität ausgeführt hat.
- **Datum:** Das Datum und die Uhrzeit, zu der die Aktivität ausgeführt wurde. Datum und Uhrzeit sind das lokale Datum und die lokale Uhrzeit für Ihre Organisation.

Um weitere Informationen zu einer protokollierten Aktivität zu erhalten, wählen Sie die Aktivität aus, um den Aktivitätsdetailsbereich anzuzeigen. Dieser Bereich enthält zusätzliche Informationen zu der Aktivität.

## <a name="columns-and-filtering"></a>Spalten und Filterung

Damit Prüfer die protokollierten Aktivitäten einfacher überprüfen können, wird die Filterung im Überwachungsprotokoll für **Insider-Risiken** unterstützt. Für die einfache Filterung stehen Warteschlangenspalten zur Verfügung, die der Ansicht hinzugefügt werden können, um verschiedene Pivots für die Dateien und Nachrichten bereitzustellen. Sie können Aktivitäten nach **Kategorie, Datumsbereich** und Aktivität filtern, die von Feldern **ausgeführt werden.**

Wenn Sie Spaltenüberschriften für die Aktivitätswarteschlange hinzufügen oder entfernen möchten, verwenden Sie das **Steuerelement "Spalten anpassen",** und wählen Sie aus den Spaltenoptionen aus. Diese Spalten entsprechen allgemeinen Bedingungen, die im **Überwachungsprotokoll für Insider-Risiken** unterstützt werden, und werden weiter unten in diesem Artikel aufgeführt.

## <a name="audit-log-export"></a>Export von Überwachungsprotokollen

Benutzer, die den Rollengruppen *"Insider-Risikomanagement"* oder "Auditor für *Insider-Risikomanagement"* zugewiesen sind, können alle Aktivitäten im Überwachungsprotokoll in eine .csv datei (durch Trennzeichen getrennte Werte) exportieren, indem sie auf der Seite **"Insider-Risikoüberwachungsprotokoll"** die Option **"Exportieren"** auswählen. Je nach Aktivität sind einige Felder für eine Aktivität möglicherweise nicht auf die Aktivität anwendbar, und diese Felder werden in der exportierten Datei als leer angezeigt.

Die Datei enthält Aktivitätsinformationen für die folgenden Felder:

- **Aktivität, die von:** Der Benutzername des Benutzers, der einen Elementwert ändert. Die hier aufgeführten Benutzer wurden einer oder mehreren der folgenden Rollengruppen für [Insider-Risikomanagement](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)zugewiesen: *Insider-Risikomanagement,* *Insider-Risikomanagement-Administratoren,* *Insider-Risikomanagementanalysten,* *Insider-Risikomanagement-Ermittler.* Jede Rollengruppe verfügt über unterschiedliche Berechtigungsstufen für die Verwaltung von Insider-Risikofeatures.
- **Aktivität:** Die Aktivität, die für ein Element ausgeführt wird. Werte sind *Angezeigt, Gelöscht, Hinzugefügt, Bearbeitete Richtlinie, Fall, Benutzer, Warnung* und *Einstellungen.*
- **Hinzugefügt:** Objekte, die während der Aktivität hinzugefügt wurden, z. B. Benutzer, Dateitypen oder Domänen.
- **Warnungsvolumen:** Die Ebene des Warnungsvolumens, das in den Einstellungen für das Insider-Risikomanagement definiert ist.
- **Betrag:** Die aktuell ausgewählten benutzerdefinierten Indikatorbeträge für eine Richtlinie.
- **Objekt-ID:** Die Objekt-ID der physischen Prioritätsresidität, für die die Aktivität ausgeführt wurde.
- **Kategorie:** Die Kategorie des geänderten Elements. Werte sind *Richtlinien, Fälle, Benutzer, Warnungen, Einstellungen* und *Benachrichtigungsvorlagen.*
- **Datum:** Datum und Uhrzeit, aufgelistet im lokalen Datum und der lokalen Uhrzeit Ihrer Organisation.
- **Beschreibung:** Die Vom Benutzer eingegebene Beschreibung für das Objekt, für das eine Aktion ausgeführt wird (z. B. eine Richtlinie oder eine Benutzergruppe mit Priorität).
- **DLP-Richtlinie:** Die Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP), die ausgewählt wurde, um die Aufnahme in eine Insider-Risikomanagementrichtlinie auszulösen.
- **Indikator:** Der Indikator in den Insider-Risikoeinstellungen, für die die Aktivität ausgeführt wurde (z. B. Hinzufügen oder Entfernen eines Indikators).
- **Hinweisvorlage:** Die Benachrichtigungsvorlage, für die die Aktivität ausgeführt wurde.
- **Anzahl der Tage:** Das in den Einstellungen für Insider-Risiken definierte Richtlinienaktivierungsfenster.
- **Anzahl der Dateien:** Das in den Einstellungen für das Insider-Risikomanagement definierte Dateivolumelimit.
- **Richtlinienvorlage:** Die Richtlinienvorlage, auf die die Indikatoren reagiert haben, gehört.
- **Vorheriger Betrag:** Die zuvor ausgewählten benutzerdefinierten Indikatorbeträge für eine Richtlinie.
- **Benutzergruppe "Priorität":** Die Prioritätsbenutzergruppe, für die die Aktivität ausgeführt wurde.
- **Entfernt:** Objekte, die während der Aktivität entfernt wurden, z. B. Benutzer, Dateitypen oder Domänen.
- **Sender**: Das Absenderfeld der Benachrichtigungsvorlage, für die die Aktivität ausgeführt wurde.
- **Zielrichtlinie:** Die Richtlinie, für die die Aktivität ausgeführt wurde (z. B. hinzufügen eines Benutzers oder Entfernen eines Benutzers).
- **Nachrichtentext** der Vorlage: Der Nachrichtentext der Benachrichtigungsvorlage, für die die Aktivität ausgeführt wurde.
- **Vorlagenbeantrager:** Das Betrefffeld der Benachrichtigungsvorlage, für die die Aktivität ausgeführt wurde.
- **Benutzer:** Benutzer, für den die Aktivität ausgeführt wurde.
