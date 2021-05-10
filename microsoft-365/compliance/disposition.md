---
title: Disposition von Inhalten
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Überwachen und Verwalten der Entsorgung von Inhalten, unabhängig davon, ob Sie die Löschungsprüfung verwenden oder Inhalte automatisch entsprechend den von Ihnen konfigurierten Einstellungen gelöscht werden.
ms.openlocfilehash: b64db336aa619313f2ff744e94d48e44c13856a0
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296756"
---
# <a name="disposition-of-content"></a>Disposition von Inhalten

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Verwenden Sie die Registerkarte **Disposition** aus der **Datensatzverwaltung** im Microsoft 365 Compliance Center, um die Löschungsprüfungen zu verwalten und [Datensätze](records-management.md#records) anzuzeigen, die am Ende des Aufbewahrungszeitraums automatisch gelöscht wurden. 

## <a name="prerequisites-for-viewing-content-dispositions"></a>Voraussetzungen für die Anzeige von Inhaltsdispositionen

Zum Verwalten von Löschungsprüfungen und zum bestätigen, dass Datensätze gelöscht wurden, müssen Sie über ausreichende Berechtigungen verfügen, und die Überwachung muss aktiviert sein.

### <a name="permissions-for-disposition"></a>Berechtigungen für Dispositionen

Wenn Sie im Microsoft 365 Compliance Center auf die Registerkarte **Disposition** erfolgreich zugreifen möchten, müssen die Benutzer über die Administratorrolle der **Dispositionsverwaltung** verfügen. Ab Dezember 2020 ist diese Rolle nun in der Standardadministrator-Rollengruppe **Datensatzverwaltung** enthalten.

> [!NOTE]
> Die Rolle **Dispositionsverwaltung** wird einem globalen Administrator standardmäßig nicht zugewiesen. 

Um Benutzern nur die Berechtigungen zu gewähren, die sie für Dispositionsprüfungen benötigen, ohne ihnen Berechtigungen zum Anzeigen und Konfigurieren anderer Features für die Aufbewahrung und die Datensatzverwaltung zu gewähren, erstellen Sie eine benutzerdefinierte Rollengruppe (z. B. mit dem Namen „Dispositionsprüfer“) und gewähren dieser Gruppe die Rolle „Dispositionsverwaltung“.

Um den Inhalt von Elementen während des Dispositionsvorgangs anzuzeigen, fügen Sie zusätzlich Benutzer zu den folgenden beiden Rollengruppen hinzu: **Inhalts-Explorer-Inhaltsanzeige** und **Inhalts-Explorer-Listenanzeige**. Verfügen Benutzer nicht über die Berechtigungen dieser Rollengruppen, können sie zwar trotzdem eine Löschungsprüfungsaktion auswählen, um die Löschungsprüfung abzuschließen, müssen dies jedoch tun, ohne den Inhalt des Artikels im Compliance Center anzeigen zu können.

Anweisungen zum Konfigurieren dieser Berechtigungen finden Sie unter [Gewähren des Zugriffs auf das Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).

### <a name="enable-auditing"></a>Überwachung aktivieren

Vergewissern Sie sich, dass die Überwachung mindestens einen Tag vor der ersten Dispositionsaktion aktiviert ist. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md). 

## <a name="disposition-reviews"></a>Löschungsprüfungen

Wenn Inhalte das Ende des Aufbewahrungszeitraums erreichen, können Sie aus mehreren Gründen überprüfen und bestätigen, ob sie dauerhaft gelöscht ("verworfen") werden können. Anstatt den Inhalt zu löschen, müssen Sie möglicherweise Folgendes:
  
- Aussetzten der Löschung relevanter Inhalte im Falle eines Rechtsstreits oder einer Prüfung.

- Zuweisen eines anderen Aufbewahrungszeitraums für die Inhalte, vielleicht, weil die ursprünglichen Aufbewahrungseinstellungen eine vorübergehende oder vorläufige Lösung waren.

- Verschieben des Inhalts von seinem bisherigen Speicherort an einen Archivspeicherort, z. B. wenn dieser Inhalt von wissenschaftlichem oder historischem Wert ist.

Wenn am Ende des Aufbewahrungszeitraums eine Löschungsprüfung ausgelöst wird:
  
- Die von Ihnen ausgewählten Personen erhalten eine E-Mail-Benachrichtigung, dass für sie Inhalte zur Überprüfung bereitstehen. Bei diesen Prüfern kann es sich um einzelne Benutzer oder E-Mail-aktivierte Sicherheitsgruppen handeln. Beachten Sie, dass Benachrichtigungen wöchentlich gesendet werden.
    
- Die Bearbeiter wechseln im Microsoft 365 Compliance Center zur Registerkarte **Disposition**, um den Inhalt zu überprüfen und zu entscheiden, ob er endgültig gelöscht, der Aufbewahrungszeitraum verlängert oder ein anderes Aufbewahrungsetikett angewendet werden soll.

Eine Löschungsprüfung kann Inhalte in Exchange-Postfächern, SharePoint-Websites, OneDrive-Konten und Microsoft 365-Gruppen enthalten. Inhalte, die an diesen Speicherorten auf eine Löschungsprüfung warten, werden erst gelöscht, nachdem ein Prüfer die endgültige Löschung der Inhalte verfügt hat.

> [!NOTE]
> Ein Postfach muss mindestens 10 MB Daten aufweisen, um Löschungsprüfungen zu unterstützen.

Sie können eine Übersicht aller ausstehenden Löschungen auf der Registerkarte **Übersicht** anzeigen. Zum Beispiel:

![Ausstehende Löschungen in der Übersicht der Datensatzverwaltung](../media/dispositions-overview.png)

Wenn Sie **Alle ausstehenden Löschungen anzeigen** auswählen, werden Sie zur Seite **Disposition** geleitet. Beispiel:

![Seite "Dispositionen" im Microsoft 365 Compliance Center](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a>Workflow für die Löschungsprüfung

Das folgende Diagramm zeigt den grundlegenden Arbeitsablauf einer Löschungsprüfung, wenn eine Aufbewahrungsbezeichnung veröffentlicht und dann manuell von einem Benutzer angewendet wird. Alternativ kann eine für eine Löschungsprüfung konfigurierte Aufbewahrungsbezeichnung automatisch auf Inhalte angewendet werden.
  
![Diagramm, in dem die Funktionsweise der Disposition angezeigt wird](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
Das Auslösen einer Löschungsprüfung am Ende des Aufbewahrungszeitraums ist eine Konfigurationsoption, die nur mit einer Aufbewahrungsbezeichnung verfügbar ist. Diese Option steht nicht für eine Aufbewahrungsrichtlinie zur Verfügung. Weitere Informationen zu diesen beiden Aufbewahrungslösungen finden Sie unter [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](retention.md).

Von der Seite **Aufbewahrungseinstellungen definieren** für eine Aufbewahrungsbezeichnung:

![Aufbewahrungseinstellungen für eine Bezeichnung](../media/disposition-review-option.png)
 
Nachdem Sie die Option **Löschungsprüfung auslösen** ausgewählt haben, geben Sie auf der nächsten Seite des Assistenten die Dispositionsprüfer an:

![Angeben von Dispositionsprüfern](../media/disposition-reviewers.png)

Geben Sie als Prüfer einen Benutzer oder eine E-Mail-aktivierte Sicherheitsgruppe an. Microsoft 365-Gruppen ([vormals Office 365-Gruppen](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) werden für diese Option nicht unterstützt.

### <a name="viewing-and-disposing-of-content"></a>Anzeigen und Verwerfen von Inhalten

Wenn ein Prüfer per E-Mail benachrichtigt wird, dass Inhalte zur Überprüfung bereitstehen, wechseln sie zur Registerkarte **Disposition** aus der **Datensatzverwaltung** im Microsoft 365 Compliance Center. Die Prüfer können sehen, wie viele Elemente für jede Aufbewahrungsbezeichnung auf Disposition warten und dann eine Aufbewahrungsbezeichnung auswählen, um den gesamten Inhalt dieser Bezeichnung anzuzeigen.

Nachdem Sie eine Aufbewahrungsbezeichnung ausgewählt haben, werden alle ausstehenden Löschungen für diese Bezeichnung auf der Registerkarte **Ausstehende Löschung** angezeigt. Wählen Sie ein oder mehrere Elemente aus, für welches Sie dann eine Aktion auswählen und einen Begründungskommentar eingeben können:

![Dispositionsoptionen](../media/retention-disposition-options.png)

Wie Sie im Bild sehen können, sind die unterstützten Aktionen: 
  
- Das Element endgültig löschen
- Verlängern des Aufbewahrungszeitraums
- Anwenden einer anderen Aufbewahrungsbezeichnung

Wenn Sie über Berechtigungen für den Speicherort und den Inhalt verfügen, können Sie den Link in der Spalte **Speicherort** verwenden, um Dokumente am ursprünglichen Speicherort anzuzeigen. Während einer Löschungsprüfung werden die Inhalte nie von ihrem ursprünglichen Speicherort fort bewegt und in keinem Fall gelöscht, es sei denn, der Prüfer entscheidet dies.

Die E-Mail-Benachrichtigungen werden automatisch wöchentlich an die Überprüfer gesendet. Dieser geplante Prozess bedeutet, dass es möglicherweise bis zu sieben Tage dauern kann, bis die Überprüfer die E-Mail-Benachrichtigung erhalten, dass der Inhalt zur Disposition steht, wenn der Inhalt das Ende seiner Aufbewahrungszeitraum erreicht.
  
Alle Dispositionsaktionen können überwacht werden, und der vom Prüfer eingegebene Begründungstext wird gespeichert und in der Spalte **Kommentar** auf der Seite **Verworfene Elemente** angezeigt.
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a>Zeitspanne bis zur endgültigen Löschung verworfener Inhalte

Inhalte, für die eine Löschungsprüfung ansteht, werden erst gelöscht, nachdem ein Prüfer die endgültige Löschung der Inhalte entschieden hat. Wenn der Prüfer diese Option auswählt, wird der Inhalt auf der SharePoint-Website oder dem OneDrive-Konto für den Standardbereinigungsprozess qualifiziert, der in [Funktionsweise von Aufbewahrungseinstellungen bei vorhandenem Inhalt](retention.md#how-retention-settings-work-with-content-in-place) beschrieben ist.

## <a name="disposition-of-records"></a>Disposition von Datensätzen

Verwenden Sie die Registerkarte **Löschung** von der Seite **Datensatzverwaltung** zur Identifikation von:

- Elemente, die als Ergebnis einer Löschungsprüfung gelöscht wurden.
- Elemente, die als Datensatz oder behördlicher Eintrag gekennzeichnet sind und am Ende ihres Aufbewahrungszeitraums automatisch gelöscht wurden.

Diese Elemente zeigen **Verworfene Datensätze** in der Spalte **Typ** an. Beispiel:

![Elemente, die ohne eine Löschungsprüfung verworfen wurden](../media/records-disposed2.png)

Elemente, die in der Registerkarte **Verworfene Elemente** angezeigt werden, werden bis zu sieben Jahre nach der Verwerfung des Elements gespeichert, und es wird ein Limit von 1 Million Elementen pro Datensatz für diesen Zeitraum angezeigt. Wenn sich die **Anzahl** dem Limit von 1 Million nähert und Sie einen Dispositionsnachweis benötigen, wenden Sie sich an [Microsoft-Support](../business-video/get-help-support.md).

> [!NOTE]
> Diese Funktionalität verwendet Informationen aus dem [einheitlichen Überwachungsprotokoll](search-the-audit-log-in-security-and-compliance.md) und erfordert daher, dass die Überwachung [aktiviert und durchsuchbar ist](turn-audit-log-search-on-or-off.md) damit die entsprechenden Ereignisse erfasst werden.

Um gelöschte Elemente zu überwachen, die als Datensätze oder behördliche Einträge gekennzeichnet wurden, suchen Sie **Gelöschte Datei, die als Datensatz gekennzeichnet ist** in der Kategorie **Datei- und Seitenaktivitäten**. Dieses Überwachungsereignis gilt für Dokumente und E-Mails.

## <a name="filter-and-export-the-views"></a>Filtern und Exportieren von Ansichten

Wenn Sie auf der Seite **Disposition** eine Aufbewahrungsbezeichnung auswählen, können Sie mit der Registerkarte **Ausstehende Löschung** (sofern zutreffend) und der Registerkarte **Verworfene Elemente** die Ansichten filtern, damit Sie Elemente leichter finden können. 

Bei ausstehenden Löschungen basiert der Zeitraum auf dem Ablaufdatum. Bei verworfenen Elementen basiert der Zeitraum auf dem Löschdatum.
  
Sie können Informationen zu den Elementen in einer der beiden Ansichten als CSV-Datei exportieren, die Sie dann mithilfe von Excel sortieren und verwalten können:

![Exportoption zur Disposition](../media/retention-export-option.png)