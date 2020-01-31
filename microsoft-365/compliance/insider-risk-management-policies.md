---
title: Richtlinien für das Insider Risikomanagement (Vorschau)
description: Informationen zu Richtlinien für das Insider Risikomanagement in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 161118bb8ff8a5c79ee507d329e20bad1421d8fd
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41590616"
---
# <a name="insider-risk-management-policies-preview"></a>Richtlinien für das Insider Risikomanagement (Vorschau)

Richtlinien für Insider-Risikomanagement bestimmen, welche Mitarbeiter im Bereich sind und welche Arten von Risikoindikatoren für Warnungen konfiguriert sind. Sie können schnell eine Richtlinie erstellen, die für alle Benutzer in Ihrer Organisation gilt, oder einzelne Benutzer oder Gruppen für die Verwaltung in einer Richtlinie definieren. Richtlinien unterstützen Inhalts Prioritäten, um Richtlinienbedingungen auf mehrere oder bestimmte Microsoft Teams, SharePoint-Websites, Daten Sensitivitäts Typen und Datenbeschriftungen zu konzentrieren. Die Verwendung von Vorlagen umfasst spezifische Risikoindikatoren und deren Gewichtung innerhalb einer Richtlinie, wobei die Gewichtung der einzelnen Warnungsauslöser in der Richtlinie effektiv bestimmt wird. Richtlinien-Fenster ermöglichen Ihnen, den Zeitrahmen zu definieren, um die Richtlinie auf Warnungs Aktivitäten anzuwenden, und werden verwendet, um die Dauer der Richtlinie nach der Aktivierung zu bestimmen. Die maximale Richtlinien Grenze beträgt fünf aktive Richtlinien gleichzeitig. Sie können jedoch weitere Richtlinien konfigurieren und Richtlinien bei Bedarf aktivieren und deaktivieren.

## <a name="policy-dashboard"></a>Richtlinien Dashboard

Mit dem **Richtlinien Dashboard** können Sie schnell die Richtlinien in Ihrer Organisation und den aktuellen Status von Warnungen anzeigen, die den einzelnen Richtlinien zugeordnet sind.

- **Richtlinienname**: der Name, der der Richtlinie im Richtlinien-Assistenten zugewiesen ist.
- **Aktive Warnungen**: die Anzahl der aktiven Warnungen für jede Richtlinie.
- **Bestätigte Warnungen**: die Gesamtzahl der Warnungen, die in den Fällen aus der Richtlinie in den letzten 365 Tagen geführt wurden.
- **Bei Warnungen ausgeführte Aktionen**: die Gesamtzahl der Benachrichtigungen, die in den letzten 365 Tagen bestätigt oder entlassen wurden.
- **Richtlinien Effektivität**: der Prozentsatz, der durch die insgesamt bestätigten Warnungen dividiert durch die Gesamtanzahl der Aktionen, die für Warnungen vorgenommen wurden, bestimmt wird (die Summe der Warnungen, die im letzten Jahr bestätigt oder entlassen wurden).
- **Aktiv**: der Status des Falls, entweder *Ja* oder *Nein*.

![Richtlinien-Dashboard für Insider Risikomanagement](media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>Richtlinienvorlagen

Vorlagen für Insider Risikomanagement sind vordefinierte Richtlinienbedingungen, mit denen die Typen von Risikoindikatoren definiert werden, die von einer Richtlinie überwacht werden. Für jede Richtlinie muss eine Vorlage im Richtlinien Erstellungs-Assistenten zugewiesen sein, bevor die Richtlinie erstellt wird. Wenn Sie eine neue Insider Risiko Richtlinie erstellen, wählen Sie eine der folgenden Vorlagen aus.

### <a name="departing-employee-data-theft"></a>Verabschiedung von Datendiebstahl durch Mitarbeiter

Wenn Mitarbeiter Ihre Organisation verlassen, gibt es bestimmte Risikoindikatoren, die typischerweise mit dem Datendiebstahl durch abfliegende Mitarbeiter verbunden sind. Diese Richtlinienvorlage priorisiert diese Indikatoren und konzentriert die Erkennung und Warnungen auf diesen Risikobereich. Der Datendiebstahl für abwesende Mitarbeiter kann das Herunterladen von Dateien aus SharePoint Online, das Kopieren von Dateien auf tragbare Geräte wie USB-Laufwerke, das Drucken von Dateien und das Kopieren von Daten in persönliche Cloud-Messaging-und-Speicherdienste in der Nähe ihrer Arbeitsplatz Rücktritts Arbeiten umfassen. End dates. In dieser Vorlage werden die Risikoindikatoren für diese Aktivitäten sowie deren Korrelation mit dem Status der Mitarbeitereinstellung priorisiert.

>[!IMPORTANT]
>Bei Verwendung dieser Vorlage müssen Sie einen Microsoft 365-HR-Connector für die regelmäßige Einfuhr von Rücktritts-und Kündigungsdatum-Informationen für Mitarbeiter in Ihrer Organisation konfigurieren. Lesen Sie den Abschnitt [Importieren von Daten mit dem HR-Connector](import-hr-data.md) , um Schritt-für-Schritt-Anleitungen zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation zu erhalten.

### <a name="data-leaks"></a>Datenlecks

Das Schützen von Daten und das verhindern von Datenverlusten stellt für die meisten Organisationen eine ständige Herausforderung dar, insbesondere mit dem schnellen Wachstum neuer Daten, die von Mitarbeitern, Geräten und Diensten erstellt wurden. Mitarbeiter sind befugt, Informationen über Dienste und Geräte hinweg zu erstellen, zu speichern und gemeinsam zu nutzen, mit denen die Verwaltung von Datenverlusten immer komplexer und schwieriger wird. Datenlecks können eine versehentliche Übernutzung von Informationen außerhalb Ihrer Organisation oder Datendiebstahl mit böswilliger Absicht umfassen. Diese Vorlage priorisiert die Echtzeiterkennung verdächtiger SharePoint Online von Daten Downloads, die Datei-und Ordnerfreigabe, das Kopieren von Dateien auf tragbare Geräte wie USB-Laufwerke, das Drucken von Dateien und das Kopieren von Daten in persönliche Cloud-Messaging-und-Speicherdienste.

>[!IMPORTANT]
>Bei Verwendung dieser Vorlage müssen Sie mindestens eine DLP-Richtlinie (Data Loss Prevention) konfigurieren, um vertrauliche Informationen in Ihrer Organisation zu definieren. Eine schrittweise Anleitung zum Konfigurieren von DLP-Richtlinien für Ihre Organisation finden Sie unter [erstellen, testen und Optimieren eines DLP-Richtlinien](create-test-tune-dlp-policy.md) Themas.

### <a name="offensive-language-in-email"></a>Anstößige Sprache in e-Mail

Das erkennen und ergreifen von Aktionen zur Vorbeugung gegen beleidigendes und missbräuchliches Verhalten ist eine wichtige Komponente zur Vermeidung von Risiken. Integrierte beleidigende sprach Klassifizierungen in Microsoft 365 können gesendete e-Mail-Nachrichten von Exchange Online Postfächern in Ihrer Organisation für unterschiedliche Arten von Kompatibilitätsproblemen überprüfen. Diese Klassifizierungen verwenden eine Kombination aus künstlicher Intelligenz und Stichwörtern, um die Sprache in e-Mails zu identifizieren, die gegen Belästigungs Richtlinien verstoßen dürften. Verwenden Sie diese Vorlage, um schnell eine Richtlinie zu erstellen, die diese Klassifizierungen verwendet, um e-Mail-Nachrichteninhalte, die als missbräuchlich oder beleidigend eingestuft werden können, automatisch zu erkennen. Für das Insider Risikomanagement werden Klassifizierungen verwendet, die gesendete e-Mail-Nachrichten für anstößige Sprachen nach englischen sprach Begriffen und-Ansichten scannen.

## <a name="monitoring-windows"></a>Überwachen von Fenstern

Mithilfe von Richtlinien-Überwachungsfenstern können Sie Zeiträume definieren, die die Richtlinien Aktivierung basierend auf Ereignissen und Aktivitäten für die Richtlinien für Insider-Risiko-Management-Vorlagen auslösen. Je nach der ausgewählten Richtlinienvorlage stehen die folgenden Überwachungsfenster zur Verfügung:

- **In-Scope TimeSpan**: verfügbar für alle Richtlinienvorlagen ist die *in-Scope-TimeSpan* die definierte Anzahl von Tagen, die das Fenster **nach** einem auslösendem Ereignis aktiviert. Das Fenster wird für 1 bis 30 Tage aktiviert, nachdem für einen Benutzer, der der Richtlinie zugewiesen ist, ein auslösendes Ereignis auftritt. Sie haben beispielsweise eine Richtlinie für das Risikomanagement für Insider konfiguriert und die *Gültigkeitszeit Spanne* auf 30 Tage festgelegt. Seit dem Konfigurieren der Richtlinie sind mehrere Monate vergangen, und für einen der in der Richtlinie enthaltenen Benutzer tritt ein auslösendes Ereignis ein. Das auslösende Ereignis aktiviert die *gültigkeitsbereichsbezogene TimeSpan* , und die Richtlinie ist für diesen Benutzer 30 Tage nach dem Auslösen des auslösendes Ereignisses aktiv.
- **Historisches TimeSpan**: für alle Richtlinienvorlagen verfügbar ist die *historische TimeSpan* die definierte Anzahl von Tagen, die das Fenster **vor** einem auslösendem Ereignis aktiviert. Das Fenster wird für 0 bis 180 Tage aktiviert, bevor ein auslösendes Ereignis für einen Benutzer eintritt, der der Richtlinie zugewiesen ist. Sie haben beispielsweise eine Richtlinie für Insider-Risikoverwaltung konfiguriert und die *historische Zeitspanne* auf 90 Tage festgelegt. Seit dem Konfigurieren der Richtlinie sind mehrere Monate vergangen, und für einen der in der Richtlinie enthaltenen Benutzer tritt ein auslösendes Ereignis ein. Das auslösende Ereignis aktiviert die *historische TimeSpan* , und die Richtlinie sammelt historische Aktivitäten für diesen Benutzer 90 Tage vor dem auslösendem Ereignis.
- **Fenster für die zukünftige Beendigung**: Diese Einstellung wird in der Scham Vorschau angezeigt, wird jedoch nicht auf alle Richtlinien angewendet und für die Produktionsversion dieser Lösung entfernt.
- **Fenster für vergangene Beendigung**: Diese Einstellung wird in der Scham Vorschau angezeigt, wird jedoch nicht auf alle Richtlinien angewendet und für die Produktionsversion dieser Lösung entfernt.

## <a name="create-a-new-policy"></a>Erstellen einer neuen Richtlinie

Um eine neue Richtlinie für das Insider Risikomanagement zu erstellen, verwenden Sie den Richtlinien-Assistenten in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center.

Führen Sie die folgenden Schritte aus, um eine neue Richtlinie zu erstellen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie **Richtlinie erstellen** aus, um den richtlinienassistenten zu öffnen
3. Füllen Sie auf der Seite **neue Insider Risiko Richtlinie** die folgenden Felder aus:
    - **Name (erforderlich)**: Geben Sie einen Anzeigenamen für die Richtlinie ein.
    - **Description (optional)**: Geben Sie eine Beschreibung für die Richtlinie ein.
    - **Richtlinienvorlage auswählen (erforderlich)**: Wählen Sie eine der [Richtlinienvorlagen](insider-risk-management-policies.md#policy-templates) aus, um die Arten von Risikoindikatoren zu definieren, die von der Richtlinie überwacht werden.

    >[!IMPORTANT]
    >Wenn Sie die *Datenlecks* -Vorlage auswählen, müssen Sie mindestens eine DLP-Richtlinie konfigurieren, die Sie später im Assistenten zuweisen. Wenn Sie die *Datendiebstahl Vorlage "departing Employee* " auswählen, müssen Sie den HR-Connector so konfigurieren, dass er die vollständigen Signal Erkennungsfunktionen der Richtlinienvorlage verwendet.

4. Wählen Sie **weiter** aus, um fortzufahren.
5. Wählen Sie auf der Seite **Benutzer** die Option **Benutzer oder Gruppe hinzufügen** aus, um zu definieren, welche Benutzer in das Kontrollkästchen Richtlinie eingeschlossen sind, oder **alle Benutzer und e-Mail-aktivierten Gruppen** auswählen. Wählen Sie **weiter** aus, um fortzufahren.
6. Auf der Seite geben Sie an, **welche Inhalte priorisiert werden sollen (optional)** , können Sie die Quellen zuweisen, um riskante Benutzeraktivitäten zu priorisieren:
    - SharePoint-Websites: Wählen Sie **SharePoint-Website hinzufügen** und die SharePoint-Organisationen aus, die Sie priorisieren möchten. Beispiel: *"group1@contoso.SharePoint.com/Sites/Group1"*.
    - Typ vertraulicher Informationen: Wählen Sie **vertraulichen Infotyp hinzufügen** aus, und wählen Sie die Vertraulichkeits Typen aus, die Sie priorisieren möchten. Beispiel: *"US Bank Account Number"* und *"Kreditkartennummer"*.
    - Vertraulichkeits Bezeichnungen: Wählen Sie **Vertraulichkeits Bezeichnung hinzufügen** aus, und wählen Sie die Beschriftungen aus, die Sie priorisieren möchten. Beispiel: *"vertraulich"* und *"geheim"*.
7. Wählen Sie **weiter** aus, um fortzufahren.
8. Auf der Seite **Warnungsindikatoren auswählen** werden die Indikatoren angezeigt, die in der Vorlage enthalten sind, die Sie für diese Richtlinie ausgewählt haben. Wenn Sie die *Datenlecks* -Vorlage zu Beginn des Assistenten ausgewählt haben, müssen Sie in der Dropdownliste DLP- **Richtlinie** eine DLP-Richtlinie auswählen.
9. Auf der Seite **Überwachungsfenster auswählen** definieren Sie die Bedingungen für das [Überwachungsfenster](insider-risk-management-policies.md#monitoring-windows) für die Richtlinie. Konfigurieren Sie die Überwachungsfenster entsprechend.
10. Wählen Sie **weiter** aus, um fortzufahren.
11. Überprüfen Sie auf der Seite **überprüfen** die Einstellungen, die Sie für die Richtlinie ausgewählt haben. Wählen Sie **Bearbeiten** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **senden** aus, um die Richtlinie zu erstellen und zu aktivieren.

## <a name="update-a-policy"></a>Aktualisieren einer Richtlinie

Um eine vorhandene Richtlinie für das Insider Risikomanagement zu aktualisieren, verwenden Sie den Richtlinien-Assistenten in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center.

Führen Sie die folgenden Schritte aus, um eine vorhandene Richtlinie zu verwalten:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie im Richtlinien Dashboard die Richtlinie aus, die Sie verwalten möchten.
3. Wählen Sie auf der Seite Richtliniendetails die Option **Richtlinie bearbeiten** aus.
4. Im Richtlinien-Assistenten können Sie die folgenden Felder nicht bearbeiten:
    - **Name**: der Anzeigename für die Richtlinie
    - **Wählen Sie**Textbuch: die Vorlage, mit der die Typen von Risikoindikatoren definiert werden, die von der Richtlinie überwacht werden.
5. Geben Sie eine neue Beschreibung für die Richtlinie in das Feld **Beschreibung** ein. Wählen Sie **weiter** aus, um fortzufahren.
6. Wählen Sie auf der Seite **Benutzer** die Option **Benutzer oder Gruppe hinzufügen** aus, um zu definieren, welche Benutzer in das Kontrollkästchen Richtlinie eingeschlossen sind, oder **alle Benutzer und e-Mail-aktivierten Gruppen** auswählen. Wählen Sie **weiter** aus, um fortzufahren
7. Aktualisieren Sie auf der Seite **Geben Sie an, welche Inhalte priorisiert werden sollen (optional)** die Quellen an, um Prioritäten für riskante Benutzeraktivitäten zu setzen:
    - SharePoint-Websites: Wählen Sie **SharePoint-Website hinzufügen** und die SharePoint-Organisationen aus, die Sie priorisieren möchten. Beispiel: *"group1@contoso.SharePoint.com/Sites/Group1"*.
    - Typ vertraulicher Informationen: Wählen Sie **vertraulichen Infotyp hinzufügen** aus, und wählen Sie die Vertraulichkeits Typen aus, die Sie priorisieren möchten. Beispiel: *"US Bank Account Number"* und *"Kreditkartennummer"*.
    - Vertraulichkeits Bezeichnungen: Wählen Sie **Vertraulichkeits Bezeichnung hinzufügen** aus, und wählen Sie die Beschriftungen aus, die Sie priorisieren möchten. Beispiel: *"vertraulich"* und *"geheim"*.
8. Wählen Sie **weiter** aus, um fortzufahren.
9. Auf der Seite **Warnungsindikatoren auswählen** werden die Indikatoren angezeigt, die in der Vorlage enthalten sind, die Sie für diese Richtlinie ausgewählt haben. Wenn Sie die *Datenlecks* -Vorlage zu Beginn des Assistenten ausgewählt haben, müssen Sie in der Dropdownliste DLP- **Richtlinie** eine DLP-Richtlinie auswählen.
10. Auf der Seite **Überwachungsfenster auswählen** definieren Sie die Bedingungen für das [Überwachungsfenster](insider-risk-management-policies.md#monitoring-windows) für die Richtlinie. Konfigurieren Sie die Überwachungsfenster entsprechend.
11. Überprüfen Sie auf der Seite **überprüfen** die Einstellungen, die Sie für die Richtlinie ausgewählt haben. Wählen Sie **Bearbeiten** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **Submit** to Update aus, und aktivieren Sie die Änderungen in der Richtlinie.

## <a name="delete-a-policy"></a>Löschen einer Richtlinie

>[!NOTE]
>Durch das Löschen einer Richtlinie werden keine aktiven oder archivierten Warnungen gelöscht, die aus der Richtlinie generiert wurden.

Führen Sie die folgenden Schritte aus, um eine vorhandene Richtlinie für Insider-Risikomanagement zu löschen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie im Richtlinien Dashboard die Richtlinie aus, die Sie verwalten möchten.
3. Wählen Sie auf der Dashboard-Symbolleiste **Löschen** aus.
4. Wählen Sie im Dialogfeld **Löschen** die Option **Ja** aus, um die Richtlinie zu löschen, oder klicken Sie auf **Abbrechen** , um das Dialogfeld zu schließen.