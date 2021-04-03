---
title: Microsoft 365-Berichte im Admin Center – Formularaktivität
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: Erfahren Sie, wie Sie einen Microsoft Forms-Aktivitätsbericht mithilfe des Microsoft 365 Reports-Dashboards im Microsoft 365 Admin Center erhalten.
ms.openlocfilehash: ce1109c6d6d626079794085b4dc742829841d06e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579674"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Microsoft 365-Berichte im Admin Center – Formularaktivität

Das Microsoft 365 **Reports-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Beispielsweise können Sie die Aktivität jedes Benutzers verstehen, der für die Verwendung von Microsoft Forms lizenziert ist, indem Sie sich deren Interaktion mit Formularen anschauen. Es hilft Ihnen auch, den Grad der Zusammenarbeit zu verstehen, indem Sie sich die Anzahl der erstellten Und Formulare anschauen, auf die der Benutzer geantwortet hat.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams Communications- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können. 

## <a name="how-to-get-to-the-forms-activity-report"></a>So erhalten Sie den Formularaktivitätsbericht

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.

    
2. Wählen Sie **in der Dropdownliste** Bericht auswählen die Option  \> **Formularaktivität aus.**

## <a name="interpret-the-forms-activity-report"></a>Interpretieren des Formularaktivitätsberichts

Sie können eine Ansicht der Formularaktivität Ihres Benutzers erhalten, indem Sie sich die Diagramme **Aktivität** und **Benutzer** ansehen. 

![Formularaktivitätsbericht](../../media/adminformsactivity.png)

|Element|Beschreibung|
|:-----|:-----|
|1.  <br/> |Der **Aktivitätsbericht** Formulare kann für Trends der letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt werden. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab.  <br/> |
|3.  <br/> |Die **Benutzeransicht** hilft Ihnen, den Trend bei der Anzahl der aktiven Formularbenutzer zu verstehen. Ein Benutzer wird als aktiv betrachtet, wenn er eine Aktivität um ein Formular herum ausgeführt hat (erstellen, bearbeiten, anzeigen usw.) oder innerhalb eines bestimmten Zeitraums auf ein Formular geantwortet hat.  <br/> |
|4.  <br/> |Die **Aktivitätsansicht** hilft Ihnen, den Trend bei der Anzahl aktiver Benutzer zu verstehen. Ein Benutzer wird als "aktiv" betrachtet, wenn er innerhalb eines bestimmten Zeitraums eine Dateiaktivität (Speichern, Synchronisieren, Ändern oder Freigeben) ausgeführt oder eine Seite besucht hat.<br/> HINWEIS: Eine Aktivität kann für ein einzelnes Formular mehrmals auftreten, zählt jedoch nur als ein aktives Formular. Sie können beispielsweise ein Formular erstellen und dasselbe Formular über einen bestimmten Zeitraum mehrmals bearbeiten, es zählt jedoch nur als einzelnes Formular. Wenn ein Benutzer jedoch mehrere Antworten für dasselbe Formular übermittelt hat, wäre jede Antwort immer noch eine einzelne Antwort und wird daher mehrmals gezählt. <br/> |
|5.<br/>|Im **Diagramm Benutzer** ist die Y-Achse die Anzahl eindeutiger Benutzer. X-Achse ist das Datum, an dem die eindeutigen Benutzer aktiv sind. Die Legenden sind:<br/><br/>**Designer** bedeutet, dass der Benutzer ein Formular erstellt oder bearbeitet hat.<br/>**Responders** bedeutet, dass der Benutzer Eine Antwort(n) an ein Formular übermittelt hat.<br/> **Gesamtbenutzer** sind alle Personen im Unternehmen, die als Designer oder Responder tätig waren.<br/><br/> Im **Diagramm Aktivität** ist die Y-Achse die Anzahl eindeutiger Formulare oder Antworten. X-Achse ist das Datum, an dem das Formular oder die Antwortaktivität aufgetreten ist. Die Legenden sind:<br/><br/>**Bei erstellten** Formularen handelt es sich um die Anzahl eindeutiger Formulare, die von den Benutzern erstellt wurden.<br/> **Angemeldete Antworten** die Anzahl der angemeldeten Antworten, die die Benutzer in der Organisation erhalten haben.<br/> **Anonyme Antworten** ist die Anzahl anonymer Antworten, die die Benutzer in der Organisation erhalten haben.<br/><br/>|
|6.<br/>|Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Wählen Sie beispielsweise im Diagramm Benutzer Designer, Responder oder Benutzer insgesamt aus, um nur die Informationen zu den einzelnen Benutzern zu sehen. Wenn Sie diese Auswahl ändern, werden die Informationen in der darunter stehenden Rastertabelle nicht geändert.|
|7.<br/>|Die Tabelle zeigt eine Aufschlüsselung der Aktivitäten auf Benutzerebene. Die Legenden sind:<br/><br/>**Benutzername** ist die E-Mail-Adresse des Benutzers, der die Aktivität in Microsoft Forms ausgeführt hat.<br/>**Das Datum der letzten Aktivität (UTC)** ist das letzte Datum, an dem eine Formularaktivität vom Benutzer für den ausgewählten Datumsbereich ausgeführt wurde. Um Aktivitäten anzuzeigen, die an einem bestimmten Datum stattfanden, wählen Sie das Datum direkt im Diagramm aus.<br/><br/>Dadurch wird die Tabelle so gefiltert, dass Dateiaktivitätsdaten nur für Benutzer angezeigt werden, die die Aktivität an diesem bestimmten Tag ausgeführt haben.<br/><br/>**Die Anzahl der erstellten** Formulare ist die Anzahl der Vom Benutzer erstellten Formulare.<br/> **Die Anzahl der beantworteten** Formulare ist die Anzahl der Formulare, auf die der Benutzer Antworten übermittelt hat.|
|8.<br/>|Wählen Sie das **Symbol Spalten** verwalten aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.|
|9.<br/>|Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten für alle Benutzer exportiert, und Sie können einfache Aggregation, Sortierung und Filterung für die weitere Analyse durchführen. Wenn Sie weniger als 100 Benutzer haben, können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Wenn Sie mehr als 100 Benutzer haben, müssen Sie die Daten exportieren, um filtern und sortieren zu können.|