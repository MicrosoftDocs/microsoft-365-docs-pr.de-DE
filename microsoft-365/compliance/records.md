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
ms.openlocfilehash: 35d1becad78cdb01402ba50ba44b277f8c511567
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080102"
---
# <a name="learn-about-records"></a>Informationen zu Datensätzen

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Die Verwaltung von Datensätzen in Microsoft 365 hilft Ihrer Organisation bei der Einhaltung von Unternehmensrichtlinien und gesetzlichen oder regulatorischer Verpflichtungen bei gleichzeitiger Verringerung der Risiken und der gesetzlichen Haftung.

Wenn Inhalt als Datensatz gekennzeichnet ist, gilt Folgendes:

- Das Element wird unveränderlich, d. h. es kann nicht geändert oder gelöscht werden.

- Andere Aktivitäten in Verbindung mit dem Element werden protokolliert.

- Sie verfügen über einen Dispositionsnachweis, wenn Datensätze am Ende ihrer Aufbewahrungsfrist gelöscht werden.

Verwenden Sie [Aufbewahrungsbezeichnungen](labels.md), um Inhalte als Datensätze zu kennzeichnen. Nachdem Sie Aufbewahrungsbezeichnungen zur Kennzeichnung von Datensätzen erstellt haben, können Sie diese Bezeichnungen entweder veröffentlichen (sodass Benutzer und Administratoren diese manuell auf Inhalte anwenden können) oder automatisch auf Inhalte anwenden, die Sie als Datensatz kennzeichnen möchten. Eine Anleitung finden Sie unter [Erstellen, Veröffentlichen und automatisches Anwenden von Aufbewahrungsbezeichnungen ](create-retention-labels.md).

Mithilfe von Aufbewahrungsbezeichnungen zur Kennzeichnung von Datensätzen können Sie eine einheitliche Strategie für die Datensatzverwaltung in Ihrer Microsoft 365-Umgebung implementieren.

Beachten Sie im Hinblick auf Aufbewahrungsbezeichnungen die folgenden Punkte:

  - **Die Bezeichnungen sind unveränderlich.** Eine Aufbewahrungsbezeichnung, die Inhalte als Datensatz kennzeichnet, kann neben SharePoint und OneDrive auch auf Exchange-Inhalte angewendet werden. Allerdings ist die [Versionsverwaltung der Bezeichnung](#record-versioning) nur in SharePoint und OneDrive und nicht für Exchange verfügbar.

    In Exchange sind Inhalte, die als Datensatz gekennzeichnet sind, bis zum endgültigen Löschen unveränderlich. Wenn ein Exchange-Element als Datensatz bezeichnet wird, geschehen vier Dinge:

    - Das Element kann nicht endgültig gelöscht werden.

    - Das Element kann nicht bearbeitet werden.

    - Die Bezeichnung kann nicht geändert werden.

    - Die Bezeichnung kann nicht entfernt werden.

  - **Datensätze und Ordner.** Sie können eine Aufbewahrungsbezeichnung auf einen Ordner in Exchange, SharePoint und OneDrive anwenden. Wenn ein Ordner als Datensatz bezeichnet wird und Sie ein Element in den Ordner verschieben, wird das Element als Datensatz bezeichnet. Wenn Sie das Element aus dem Ordner verschieben, bleibt es weiterhin als Datensatz gekennzeichnet.

    Wenn Sie die Datensatzkennzeichnung eines Ordners (in SharePoint und OneDrive), in eine Aufbewahrungskennzeichnung abändern, die den Inhalt nicht als Datensatz deklariert, behalten die Elemente im Ordner ihre bestehende Datensatzkennzeichnung.

    Weitere Informationen zum Anwenden von Datensatzkennzeichnungen auf SharePoint- und OneDrive-Ordner finden Sie unter [Anwenden einer Aufbewahrungsbezeichnung auf alle Inhalte in einer Bibliothek, einem Ordner oder einer Dokumentenmappe in SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).

  - **Datensätze können nicht gelöscht werden**. Wenn ein Benutzer versucht, einen Datensatz in Exchange zu löschen, wird das Element in den Ordner „Wiederherstellbare Elemente“ verschoben, wie unter [Funktionsweise einer Aufbewahrungsrichtlinie mit Exchange-Speicherorten](retention-policies-exchange.md#how-a-retention-policy-works-with-exchange) beschrieben.

    Wenn ein Benutzer versucht, einen Datensatz in SharePoint zu löschen, wird eine Fehlermeldung angezeigt, dass das Element nicht gelöscht wurde und in der Bibliothek verbleibt.

    ![Nachricht, dass das Element nicht aus SharePoint gelöscht wurde](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)

    Wenn ein Benutzer versucht, einen Datensatz in OneDrive zu löschen, wird das Element in das permanente Dokumentarchiv verschoben, wie unter [Funktionsweise einer Aufbewahrungsrichtlinie mit SharePoint und OneDrive](retention-policies-sharepoint.md#how-a-retention-policy-works-with-sharepoint-and-onedrive) beschrieben.

  - **Datensatzbezeichnungen können nicht entfernt werden.** Nachdem eine Datensatzbezeichnung auf ein Element angewendet wurde, kann nur der Administrator dieses Speicherorts (beispielsweise ein Websitesammlungsadministrator einer SharePoint-Website) diese Datensatzbezeichnung entfernen.

## <a name="using-retention-labels-to-declare-records"></a>Verwenden von Aufbewahrungsbezeichnungen zum Kennzeichnen von Datensätzen

Wenn Sie eine Aufbewahrungsbezeichnung erstellen, können Sie die Aufbewahrungsbezeichnung dazu verwenden, Inhalte als Datensatz zu kennzeichnen:

1. Wechseln Sie im Microsoft 365 Compliance Center zu **Records Management-** \> **Dateiplan**. Wählen Sie von der Seite **Dateiplan** **Eine Bezeichnung erstellen**.

2. Wählen Sie auf der Seite **Bezeichnungseinstellungen** im Assistenten die Option aus, mit der die Aufbewahrungsbezeichnung Inhalte als Datensatz kennzeichnen soll.
    
   ![Aktivieren Sie das Kontrollkästchen „Bezeichnung zum Klassifizieren von Inhalt als „Datensatz“ verwenden“](../media/recordversioning6.png)

3. [Veröffentlichen](labels.md#how-retention-labels-work-with-retention-label-policies) Sie oder [wenden Sie](labels.md#applying-a-retention-label-automatically-based-on-conditions) die Aufbewahrungsbezeichnung auf SharePoint-Websites und/ oder OneDrive-Konten automatisch an.


### <a name="applying-a-retention-label-to-content"></a>Anwenden einer Aufbewahrungsbezeichnung auf Inhalte

Bei Exchange kann jeder Benutzer mit Schreibzugriff auf das Postfach eine Datensatzbezeichnung auf eine E-Mail-Nachricht anwenden. Bei Inhalten auf SharePoint und OneDrive kann jeder Benutzer in der Standardgruppe "Mitglieder" (Berechtigungsstufe "Mitwirken") eine Datensatzbezeichnung auf Inhalte anwenden. Nur der Websitesammlungsadministrator kann diese Datensatzbezeichnung entfernen oder ändern, nachdem sie angewendet wurde. Wie zuvor erläutert, kann eine Aufbewahrungsbezeichnung, die Inhalte als Datensatz kennzeichnet, automatisch auf Inhalte angewendet werden.

Es sieht so aus, als ob eine Datensatzbezeichnung auf ein Dokument auf einer SharePoint-Website oder ein OneDrive-Konto angewendet wurde.
<br/><br/>

![Detailbereich für ein als Datensatz markiertes Dokument](../media/recordversioning7.png)

## <a name="record-versioning"></a>Datensatzversionsverwaltung

Ein wesentlicher Bestandteil der Datensatzverwaltung ist die Möglichkeit, ein Dokument als Datensatz zu kennzeichnen und den Datensatz unveränderlich zu halten. Gleichzeitig wird durch die Datensatzunveränderlichkeit die Zusammenarbeit am Dokument verhindert, wenn andere Benutzer eine spätere Version erstellen müssen. Sie können z. B. einen Kaufvertrag als Datensatz kennzeichnen, den Vertrag dann aber mit neuen Bedingungen aktualisieren und die neueste Version als neuen Datensatz kennzeichnen, während die vorherige Datensatzversion weiterhin beibehalten wird. Bei diesen Szenarien unterstützt SharePoint und OneDrive die *Versionsverwaltung für Datensätze*. OneNote-Notizbuchordner unterstützen keine Datensatzversionsverwaltung.

Wenn Sie die Datensatzversionsverwaltung verwenden möchten, besteht der erste Schritt darin, Aufbewahrungsbezeichnungen, die Datensätze kennzeichnen, im Microsoft 365 Compliance Center zu erstellen und für alle SharePoint-Websites und OneDrive-Konten bzw. für bestimmte SharePoint-Websites oder OneDrive-Konten zu veröffentlichen. Der nächste Schritt besteht darin, eine veröffentlichte Aufbewahrungsdatenbezeichnung für einen Datensatz auf ein Dokument anzuwenden. Wenn dies erfolgt ist, wird neben der Aufbewahrungsbezeichnung eine Dokumenteigenschaft mit dem Namen *Datensatzstatus* angezeigt, und der ursprüngliche Datensatzstatus wird **Gesperrt** sein. An dieser Stelle können Sie die folgenden Aktionen durchführen:

  - **Sie können einzelne Versionen des Dokuments kontinuierlich bearbeiten und als Datensätze kennzeichnen, indem Sie die Eigenschaft „Datensatzstatus“ ordnungsgemäß entsperren und sperren.** Nur die als Datensätze gekennzeichneten Versionen bleiben erhalten, wenn die Eigenschaft **Datensatzstatus** auf **Gesperrt** gestellt ist. Dadurch wird das Risiko verringert, dass nicht benötigte Versionen und Kopien des Dokuments aufbewahrt werden.

  - **Lassen Sie die Datensätze automatisch in einem in-situ-Datensatzrepository speichern, das sich in der Websitesammlung befindet.** Jede Websitesammlung in SharePoint und OneDrive bewahrt Inhalte in ihrer Aufbewahrungsspeicherbibliothek auf. Datensatzversionen werden im Ordner „Datensätze“ in dieser Bibliothek gespeichert.

  - **Verwalten Sie ein erneuerndes Dokument, das alle Versionen enthält.** Standardmäßig enthält jedes SharePoint- und OneDrive-Dokument einen Versionsverlauf, der im Element „Menü“ zur Verfügung steht. In diesem Versionsverlauf können Sie leicht sehen, welche Versionen Datensätze sind und diese Dokumente anzeigen.

Die Datensatzversionsverwaltung steht für alle Dokumente mit einer Aufbewahrungsbezeichnung , die das Element als Datensatz kennzeichnet, automatisch zur Verfügung. Wenn ein Benutzer die Dokumenteigenschaften über den Detailbereich anzeigt, wechselt er **Datensatzstatus** von **Gesperrt** zu **Entsperrt**. Dieser einzelne Klick erstellt einen Datensatz im Ordner „Datensätze des permanenten Dokumentenarchiv, in dem er sich für den Rest des Aufbewahrungszeitraums befindet. 

Während das Dokument entsperrt ist, kann jeder Benutzer mit Berechtigungen die Datei bearbeiten. Benutzer können die Datei jedoch nicht löschen, weil Sie als Datensatz betrachtet wird. Nachdem die erforderlichen Änderungen vorgenommen wurden, kann der Benutzer den **Datensatzstatus** von **Entsperrt** auf **Gesperrt**wechseln, sodass das Dokument erneut als Datensatz gekennzeichnet wird und nicht bearbeitet werden kann.
<br/><br/>

![Datensatzstatus-Eigenschaft in einem Dokument, das als Datensatz gekennzeichnet ist](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a>Sperren und Entsperren eines Datensatzes

Nachdem einem Dokument eine Datensatzbezeichnung zugeordnet wurde, kann jeder Benutzer in der Berechtigung "Mitwirken" oder einer engeren Berechtigungsstufe einen Datensatz entsperren oder einen entsperrten Datensatz sperren.
<br/><br/>

![Der Datensatzstatus zeigt, dass das Datensatzdokument entsperrt ist](../media/recordversioning9.png)

Wenn ein Benutzer einen Datensatz entsperrt, werden die folgenden Aktionen ausgeführt:

1. Wenn für die aktuelle Websitesammlung kein Permanentes Dokumentarchiv vorhanden ist, wird eine erstellt.

2. Wenn das permanente Dokumentarchiv nicht über einen Datensatzordner verfügt, wird einer erstellt.

3. Eine **Kopieren in**-Aktion kopiert die neueste Version des Dokuments in den Ordner „Datensätze“. Die Aktion **Kopieren in** ist nur für die neueste Version und für keine früheren Versionen wirksam. Dieses kopierte Dokument wird jetzt als Datensatzversion des Dokuments betrachtet, und der Dateiname hat das Format: \[Titel GUID Version\#\]

4. Die Kopie, die im Ordner „Datensätze“ erstellt wurde, wurde dem Versionsverlauf des ursprünglichen Dokuments hinzugefügt, und diese Version zeigt das Wort **Datensatz** im Feld „Kommentare“.

5. Bei dem Originaldokument handelt es sich um eine neue Version, die bearbeitet (aber nicht gelöscht) werden kann. Die Dokumentbibliothekspalte **Element ist ein Datensatz** weist weiterhin den Wert **Ja** auf, weil das Dokument noch als Datensatz betrachtet wird, selbst wenn es jetzt bearbeitet werden kann.

Wenn ein Benutzer einen Datensatz sperrt, kann das ursprüngliche Dokument erneut nicht bearbeitet werden. Es handelt sich aber um die Aktion zum Entsperren eines Datensatzes, der eine Version in den Ordner „Datensätze“ in dem permanenten Dokumentarchiv kopiert.

### <a name="record-versions"></a>Datensatzversionen

Jedes Mal, wenn ein Benutzer einen Datensatz entsperrt, wird die aktuelle Version in den Ordner Datensätze in dem permanenten Dokumentarchiv kopiert, und diese Version enthält den Wert **Datensatz** im Feld **Kommentare** des Versionsverlaufs.
<br/><br/>

![Datensatz, der in dem permanenten Dokumentarchiv angezeigt wird](../media/recordversioning10.png)

Um den Versionsverlauf anzuzeigen, wählen Sie ein Dokument in der Dokumentbibliothek aus, und klicken Sie dann im Element „Menü“ auf **Versionsverlauf**.

### <a name="where-records-are-stored"></a>Speicherort von Datensätzen

Die Datensätze werden im Ordner „Datensätze“ in dem permanenten Dokumentarchiv auf der Website auf oberster Ebene in der Websitesammlung gespeichert. Wählen Sie in der linken Navigationsleiste auf der Website auf oberster Ebene **Websiteinhalte** \> **Permanentes Dokumentarchiv** aus.
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

Anweisungen zum Erstellen und Veröffentlichen der Aufbewahrungsbezeichnungen, die die Einstellung enthalten, Inhalte als Datensatz zu kennzeichnen, finden Sie [Erstellen, Veröffentlichen und automatisches Anwenden von Aufbewahrungsbezeichnungen](create-retention-labels.md).
