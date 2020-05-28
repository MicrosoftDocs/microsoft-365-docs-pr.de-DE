---
title: Microsoft 365-Berichte in der Admin Center-Formular Aktivität
ms.author: sirkkuw
author: sirkkuw
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
description: Informationen zum Abrufen eines Microsoft Forms-Aktivitätsberichts mithilfe des Microsoft 365 Reports-Dashboards im Microsoft 365 Admin Center.
ms.openlocfilehash: f835533fb626c8d6e7bd408b90abaa558304e20b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387753"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Microsoft 365-Berichte in der Admin Center-Formular Aktivität

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Sie können beispielsweise die Aktivität jedes Benutzers verstehen, der für die Verwendung von Microsoft Forms autorisiert ist, indem Sie sich Ihre Interaktion mit Formularen ansehen. Außerdem können Sie die Ebene der Zusammenarbeit verstehen, indem Sie die Anzahl der erstellten Formulare und Formulare betrachten, auf die der Benutzer geantwortet hat.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen. 

## <a name="how-to-get-to-the-forms-activity-report"></a>So gelangen Sie zum Formular Aktivitätsbericht

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.

    
2. Wählen Sie in der Dropdownliste **Bericht auswählen** die Option **Formular** \> **Aktivität**aus.

## <a name="interpret-the-forms-activity-report"></a>Interpretieren des Berichts "Formular Aktivität"

Sie können eine Ansicht der Formular Aktivitäten Ihrer Benutzer anzeigen, indem Sie sich die Diagramme **Aktivität** und **Benutzer** ansehen. 

![Formular Aktivitätsbericht](../../media/adminformsactivity.png)

|||
|:-----|:-----|
|1.  <br/> |Der **Formular Aktivitäts** Bericht kann für Trends in den letzten 7 Tagen, 30 Tagen, 90 Tagen oder 180 Tagen angezeigt werden. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab.  <br/> |
|3.  <br/> |In der Ansicht **Benutzer** können Sie den Trend bei der Anzahl aktiver Formular Benutzer verstehen. Ein Benutzer wird als "aktiv" betrachtet, wenn er eine Aktivität um ein Formular (erstellen, bearbeiten, Anzeigen usw.) oder ein Formular innerhalb eines bestimmten Zeitraums geantwortet hat.  <br/> |
|4.  <br/> |Die **Aktivitäts** Ansicht hilft Ihnen, den Trend bei der Anzahl aktiver Benutzer zu verstehen. Ein Benutzer wird als "aktiv" betrachtet, wenn er innerhalb eines bestimmten Zeitraums eine Dateiaktivität (Speichern, Synchronisieren, Ändern oder Freigeben) ausgeführt oder eine Seite besucht hat.<br/> Hinweis: eine Aktivität kann mehrere Male für ein einzelnes Formular auftreten, wird aber nur als ein aktives Formular gezählt. Sie können beispielsweise ein Formular erstellen und das gleiche Formular mehrmals in einem bestimmten Zeitraum bearbeiten, aber es wird nur als ein einzelnes Formular gezählt. Wenn ein Benutzer jedoch mehrere Antworten für dasselbe Formular übermittelt hat, wäre jede Antwort immer noch eine individuelle Antwort und wird daher mehrmals gezählt. <br/> |
|5.<br/>|Im Diagramm **Benutzer** ist die Y-Achse die Anzahl der eindeutigen Benutzer. X-Achse ist das Datum, an dem die eindeutigen Benutzer aktiv sind. Die Legenden sind:<br/><br/>**Designer** bedeutet, dass der Benutzer ein Formular erstellt oder bearbeitet hat.<br/>**Responder** bedeutet, dass der Benutzer eine Antwort (en) an ein Formular übermittelt hat.<br/> " **Total Users** " bedeutet, dass jeder Benutzer im Unternehmen, der ein Designer oder Responder war.<br/><br/> Im **Aktivitäts** Diagramm ist die Y-Achse die Anzahl der eindeutigen Formulare oder Antworten. X-Achse ist das Datum, an dem das Formular oder die Antwort Aktivität aufgetreten ist. Die Legenden sind:<br/><br/>" **Erstellte Formulare** " ist die Anzahl der eindeutigen Formulare, die von den Benutzern erstellt wurden.<br/> **In Antworten angemeldet** die Anzahl der angemeldeten Antworten, die die Benutzer in der Organisation erhalten haben.<br/> **Anonyme Antworten** ist die Anzahl der anonymen Antworten, die die Benutzer in der Organisation erhalten haben.<br/><br/>|
|6.<br/>|Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Wählen Sie beispielsweise im Diagramm Benutzer die Option Designer, Responder oder Gesamtbenutzer aus, um nur die zugehörigen Informationen anzuzeigen. Wenn Sie diese Auswahl ändern, werden die Informationen in der Raster Tabelle darunter nicht geändert.|
|7.<br/>|Die Tabelle zeigt eine Aufschlüsselung der Aktivitäten auf Einzelbenutzerebene. Die Legenden sind:<br/><br/>**Username** ist die e-Mail-Adresse des Benutzers, der die Aktivität in Microsoft Forms ausgeführt hat.<br/>**Datum der letzten Aktivität (UTC)** ist das letzte Datum, an dem eine Formular Aktivität vom Benutzer für den ausgewählten Datumsbereich ausgeführt wurde. Um Aktivitäten anzuzeigen, die an einem bestimmten Datum stattfanden, wählen Sie das Datum direkt im Diagramm aus.<br/><br/>Dadurch wird die Tabelle so gefiltert, dass Datei Aktivitätsdaten nur für Benutzer angezeigt werden, die die Aktivität an diesem bestimmten Tag ausgeführt haben.<br/><br/>" **Anzahl der erstellten Formulare** " ist die Anzahl der vom Benutzer erstellten Formulare.<br/> " **Anzahl der geantwortten Formulare** " ist die Anzahl der Formulare, an die der Benutzer Antworten gesendet hat.|
|8.<br/>|Wählen Sie das Symbol " **Spalten verwalten** " aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.|
|9.<br/>|Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten für alle Benutzer exportiert, und Sie können einfache Aggregation, Sortierung und Filterung für weitere Analysen durchführen. Wenn Sie über weniger als 100 Benutzer verfügen, können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Wenn Sie über mehr als 100 Benutzer verfügen, müssen Sie die Daten exportieren, um Sie zu filtern und zu sortieren.|