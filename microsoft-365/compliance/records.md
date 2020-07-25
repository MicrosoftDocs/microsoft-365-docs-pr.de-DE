---
title: Informationen zu Datensätzen
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
description: Erfahren Sie mehr über Datensätze, um Sie beim Implementieren einer Datensatzverwaltungslösung in Microsoft 365 zu unterstützen.
ms.openlocfilehash: 6cdf29493a3fd95b060c52d9f9587ee34748edde
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372520"
---
# <a name="learn-about-records"></a>Informationen zu Datensätzen

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Die Verwaltung von Datensätzen in Microsoft 365 hilft Ihrer Organisation bei der Einhaltung von Unternehmensrichtlinien und gesetzlichen oder regulatorischer Verpflichtungen bei gleichzeitiger Verringerung der Risiken und der gesetzlichen Haftung.

Wenn Inhalt als Datensatz markiert ist:

- Die Elemente werden hinsichtlich der [zulässigen oder blockierten Aktionen](#compare-restrictions-for-what-actions-are-allowed-or-blocked) eingeschränkt.

- Andere Aktivitäten in Verbindung mit dem Element werden protokolliert.

- Sie haben einen Verfügungsnachweis, wenn die Elemente am Ende ihrer Aufbewahrungsfrist gelöscht werden.

Verwenden Sie [Aufbewahrungsbezeichnungen](retention.md#retention-labels), um Inhalte als Datensätze zu kennzeichnen. Sie können diese Bezeichnungen entweder veröffentlichen, damit Benutzer und Administratoren sie manuell auf Inhalte anwenden können, oder diese Bezeichnungen automatisch auf Inhalte anwenden, die Sie als Datensatz markieren möchten.

Durch die Verwendung von Aufbewahrungsbezeichnungen zum Markieren von Inhalten als Datensätze können Sie eine einzige und konsistente Strategie für die Verwaltung von Datensätzen in Ihrer Microsoft 365-Umgebung implementieren.

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Vergleichen Sie die Einschränkungen für die zulässigen oder blockierten Aktionen

Verwenden Sie die folgende Tabelle, um zu ermitteln, welche Einschränkungen für den Inhalt durch das Anwenden einer Standardaufbewahrungsbezeichnung und von Aufbewahrungsbezeichnungen, die den Inhalt als Datensatz kennzeichnen, gelten. 

Eine Standardaufbewahrungsbezeichnung kann Daten speichern, ohne den Inhalt als Datensatz zu markieren.

>[!NOTE] 
> Der Vollständigkeit halber enthält die Tabelle Spalten für einen gesperrten und entsperrten Datensatz, die für SharePoint und OneDrive gelten, jedoch nicht für Exchange. Die Möglichkeit zum Sperren und Entsperren eines Datensatzes verwendet die [Datensatzversionsverwaltung](#record-versioning), die für Exchange-Elemente nicht unterstützt wird. Für alle Exchange-Elemente, die als Datensatz markiert sind, ist das Verhalten der Spalte **Datensatz gesperrt** und der Spalte **Datensatz entsperrt** nicht relevant.


|Aktion| Aufbewahrungsbezeichnung |Datensatz – gesperrt| Datensatz – entsperrt|
|:-----|:-----|:-----|:-----|:-----|
|Inhalt bearbeiten|Zulässig | **Gesperrt** | Zulässig|
|Bearbeiten Sie Eigenschaften, einschließlich Umbenennen|Allowed |Zulässig | Allowed|
|Löschen|Zulässig <sup>1</sup> |**Gesperrt** | **Gesperrt**|
|Kopie|Allowed |Zulässig | Allowed|
|Innerhalb eines Containers bewegen<sup>2</sup>|Allowed |Zulässig | Allowed|
|Über Container hinweg bewegen <sup>2</sup>|Zulässig |Zulässig, wenn nie entsperrt | Zulässig|
|Öffnen/Lesen|Allowed |Zulässig | Allowed|
|Ändern der Bezeichnung|Zulässig |Zulässig – nur Container-Administrator | Zulässig – nur Container-Administrator|
|Bezeichnung entfernen|Zulässig |Zulässig – nur Container-Administrator | Zulässig – nur Container-Administrator|

Fußnoten:

<sup>1</sup> Unterstützt von OneDrive und Exchange durch Aufbewahren einer Kopie an einem gesicherten Ort, jedoch blockiert von SharePoint.

Nachricht, die ein Benutzer sieht, wenn er versucht, ein beschriftetes Dokument in SharePoint zu löschen:

![Nachricht, dass das Element nicht aus SharePoint gelöscht wurde](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<sup>2</sup> Zu den Containern gehören SharePoint-Dokumentbibliotheken und Exchange-Postfächer.


## <a name="using-retention-labels-to-declare-records"></a>Verwenden von Aufbewahrungsbezeichnungen zum Kennzeichnen von Datensätzen

Wenn Sie eine Aufbewahrungsbezeichnung erstellen, können Sie die Aufbewahrungsbezeichnung dazu verwenden, Inhalte als Datensatz zu kennzeichnen:

1. Wechseln Sie im Microsoft 365 Compliance Center zu **Records Management-** \> **Dateiplan**. Wählen Sie von der Seite **Dateiplan** **Eine Bezeichnung erstellen**.

2. Wählen Sie auf der Seite **Bezeichnungseinstellungen** im Assistenten die Option zum Klassifizieren von Inhalten als Datensatz aus.
    
   ![Aktivieren Sie das Kontrollkästchen „Bezeichnung zum Klassifizieren von Inhalt als „Datensatz“ verwenden“](../media/recordversioning6.png)

3. Wenden Sie die Aufbewahrungsbezeichnung nach Bedarf auf SharePoint- oder OneDrive-Dokumente und Exchange-E-Mails an. Für Anweisungen:
    
    - [Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)
    
    - [Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)

### <a name="applying-the-configured-retention-label-to-content"></a>Anwenden der konfigurierten Aufbewahrungsbezeichnung auf Inhalte

Wenn Aufbewahrungsbezeichnungen, die Inhalte als Datensatz markieren, Benutzern zur Verfügung gestellt werden, um sie in Apps anzuwenden:

- Bei Exchange kann jeder Benutzer mit Schreibzugriff auf das Postfach diese Bezeichnung anwenden. 
- Bei SharePoint und OneDrive kann jeder Benutzer in der Standardgruppe "Mitglieder" (Berechtigungsstufe "Beitrag") diese Bezeichnung anwenden.

Beispiel für ein Dokument, das mithilfe einer Aufbewahrungsbezeichnung als Datensatz markiert wurde:

![Detailbereich für ein als Datensatz markiertes Dokument](../media/recordversioning7.png)

## <a name="record-versioning"></a>Datensatzversionsverwaltung

Die Möglichkeit, ein Dokument als Datensatz zu markieren und Aktionen einzuschränken, die für den Datensatz ausgeführt werden können, ist ein wesentliches Ziel jeder Datensatzverwaltungslösung. Möglicherweise ist jedoch auch eine Zusammenarbeit erforderlich, damit Benutzer nachfolgende Versionen erstellen können.

Beispielsweise können Sie einen Kaufvertrag als Datensatz markieren, müssen dann jedoch den Vertrag mit neuen Bedingungen aktualisieren und die neueste Version als neuen Datensatz markieren, während die vorherige Datensatzversion beibehalten wird. Bei diesen Szenarien unterstützt SharePoint und OneDrive die *Versionsverwaltung für Datensätze*. OneNote-Notizbuchordner unterstützen keine Datensatzversionsverwaltung.

Um die Datensatzversionsverwaltung zu verwenden, beschriften Sie zuerst das Dokument und markieren Sie es als Datensatz. Zu diesem Zeitpunkt wird neben der Aufbewahrungsbezeichnung eine Dokumenteigenschaft mit dem Namen *Datensatzstatus* angezeigt, und der anfängliche Datensatzstatus ist **Gesperrt**. 

Sie können jetzt Folgendes tun:

  - **Bearbeiten und speichern Sie einzelne Versionen des Dokuments kontinuierlich als Datensätze, indem Sie die Eigenschaft Datensatzstatus entsperren und sperren.** Nur wenn die Eigenschaft **Datensatzstatus** auf **Gesperrt** gesetzt ist, wird eine neue Version des Datensatzes beibehalten. Durch das Umschalten zwischen gesperrt und entsperrt wird das Risiko verringert, dass unnötige Versionen und Kopien des Dokuments aufbewahrt werden.

  - **Lassen Sie die Datensätze automatisch in einem in-situ-Datensatzrepository speichern, das sich in der Websitesammlung befindet.** Jede Websitesammlung in SharePoint und OneDrive bewahrt Inhalte in ihrer Aufbewahrungsspeicherbibliothek auf. Datensatzversionen werden im Ordner „Datensätze“ in dieser Bibliothek gespeichert.

  - **Verwalten Sie ein erneuerndes Dokument, das alle Versionen enthält.** Standardmäßig enthält jedes SharePoint- und OneDrive-Dokument einen Versionsverlauf, der im Element „Menü“ zur Verfügung steht. In diesem Versionsverlauf können Sie leicht sehen, welche Versionen Datensätze sind und diese Dokumente anzeigen.

Die Datensatzversionsverwaltung ist automatisch für alle Dokumente verfügbar, deren Aufbewahrungsbezeichnung das Element als Datensatz kennzeichnet. Wenn ein Benutzer die Dokumenteigenschaften im Detailbereich anzeigt, kann er den **Datensatzstatus** von **Gesperrt** auf **Entsperrt** umschalten. Diese Aktion erstellt einen Datensatz im Ordner "Datensätze" in dem permanenten Dokumentarchiv, in dem er sich für den Rest seiner Aufbewahrungsdauer befindet. 

Während das Dokument entsperrt ist, kann jeder Benutzer mit Standardbearbeitungsberechtigungen die Datei bearbeiten. Benutzer können die Datei jedoch nicht löschen, da es sich immer noch um einen Datensatz handelt. Wenn die Bearbeitung abgeschlossen ist, kann ein Benutzer den **Datensatzstatus** von **Entsperrt** auf **Gesperrt** umschalten, wodurch weitere Änderungen in diesem Status verhindert werden.
<br/><br/>

![Datensatzstatus-Eigenschaft in einem Dokument, das als Datensatz gekennzeichnet ist](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a>Sperren und Entsperren eines Datensatzes

Nachdem eine Aufbewahrungsbezeichnung, die den Inhalt als Datensatz kennzeichnet, auf ein Dokument angewendet wurde, kann jeder Benutzer mit Beitragsberechtigungen oder einer engeren Berechtigungsstufe einen Datensatz entsperren oder einen entsperrten Datensatz sperren.
<br/><br/>

![Der Datensatzstatus zeigt, dass das Datensatzdokument entsperrt ist](../media/recordversioning9.png)

Wenn ein Benutzer einen Datensatz entsperrt, werden die folgenden Aktionen ausgeführt:

1. Wenn für die aktuelle Websitesammlung kein Permanentes Dokumentarchiv vorhanden ist, wird eine erstellt.

2. Wenn das permanente Dokumentarchiv nicht über einen Datensatzordner verfügt, wird einer erstellt.

3. Eine **Kopieren in**-Aktion kopiert die neueste Version des Dokuments in den Ordner „Datensätze“. Die Aktion **Kopieren in** ist nur für die neueste Version und für keine früheren Versionen wirksam. Dieses kopierte Dokument wird jetzt als Datensatzversion des Dokuments betrachtet, und der Dateiname hat das Format: \[Titel GUID Version\#\]

4. Die im Ordner "Datensätze" erstellte Kopie wird dem Versionsverlauf des Originaldokuments hinzugefügt. In dieser Version wird das Wort **Datensatz** im Kommentarfeld angezeigt.

5. Das Originaldokument ist eine neue Version, die bearbeitet, aber nicht gelöscht werden kann. In der Spalte Dokumentbibliothek **Element ist ein Datensatz** wird weiterhin der Wert **Ja** angezeigt, da das Dokument weiterhin ein Datensatz ist, auch wenn es jetzt bearbeitet werden kann.

Wenn ein Benutzer einen Datensatz sperrt, kann das ursprüngliche Dokument erneut nicht bearbeitet werden. Es handelt sich aber um die Aktion zum Entsperren eines Datensatzes, der eine Version in den Ordner „Datensätze“ in dem permanenten Dokumentarchiv kopiert.

### <a name="record-versions"></a>Datensatzversionen

Jedes Mal, wenn ein Benutzer einen Datensatz entsperrt, wird die aktuelle Version in den Ordner Datensätze in dem permanenten Dokumentarchiv kopiert, und diese Version enthält den Wert **Datensatz** im Feld **Kommentare** des Versionsverlaufs.
<br/><br/>

![Datensatz, der in dem permanenten Dokumentarchiv angezeigt wird](../media/recordversioning10.png)

Um den Versionsverlauf anzuzeigen, wählen Sie ein Dokument in der Dokumentbibliothek aus, und klicken Sie dann im Element „Menü“ auf **Versionsverlauf**.

### <a name="where-records-are-stored"></a>Speicherort von Datensätzen

Die Datensätze werden im Ordner „Datensätze“ in dem permanenten Dokumentarchiv auf der Website auf oberster Ebene in der Websitesammlung gespeichert. Wählen Sie in der linken Navigation auf der Site der obersten Ebene die Option **Siteinhalte** \> **Permanentes Dokumentarchiv**.
<br/><br/>

![Permanentes Dokumentarchiv](../media/recordversioning11.png)

<br/><br/>

![Datensatzordner in dem permanenten Dokumentarchiv](../media/recordversioning12.png)

Das permanente Dokumentarchiv ist nur für Websitesammlungsadministratoren sichtbar. Außerdem ist das permanente Dokumentarchiv nicht standardmäßig vorhanden. Er wird nur erstellt, wenn Inhalte, die einer Aufbewahrungsbezeichnung oder einer Aufbewahrungsrichtlinie unterliegen, zum ersten Mal in der Websitesammlung gelöscht werden.

### <a name="searching-the-audit-log-for-record-versioning-events"></a>Durchsuchen des Überwachungsprotokolls nach Ereignissen für die Versionsverwaltung

Die Aktionen zum Sperren und Entsperren von Datensätzen werden im Überwachungsprotokoll protokolliert. Sie können nach den spezifischen Aktivitäten **Datensatzstatus auf „gesperrt“ geändert** und **Datensatzstatus auf „entsperrt“ geändert** suchen, die sich im Abschnitt **Datei- und Seitenaktivitäten** auf der Dropdownliste **Aktivitäten** auf der Seite **Überprüfungsprotokoll durchsuchen** im Security & Compliance Center befinden.
<br/><br/>

![Durchsuchen des Überwachungsprotokolls nach Ereignissen für die Versionsverwaltung](../media/recordversioning13.png)

Weitere Informationen zum Durchsuchen dieser Ereignisse finden Sie im Abschnitt „Datei- und Seitenaktivitäten“ im [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie noch keine Aufbewahrungsbezeichnungen für die Datensatzverwaltung besitzen, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).

Informationen zur Löschung von Datensätzen finden Sie unter [Löschen von Inhalten](disposition.md).
