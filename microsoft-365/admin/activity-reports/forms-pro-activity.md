---
title: Microsoft 365-Berichte im Admin Center-Formulare pro-Aktivität
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
description: Erfahren Sie, wie Sie einen Microsoft Forms pro-Aktivitätsbericht mithilfe des Microsoft 365 Reports-Dashboards im Microsoft 365 Admin Center erhalten.
ms.openlocfilehash: 58c7a76c49b7c925a4e7851f7e81c7f47d465d3a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949192"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-pro-activity"></a>Microsoft 365-Berichte im Admin Center-Formulare pro-Aktivität

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Sie können beispielsweise die Aktivität jedes Benutzers verstehen, der für die Verwendung von Microsoft Forms pro lizenziert ist, indem Sie sich ihre Interaktionen mit Formularen pro ansehen. Außerdem können Sie die Ebene der Zusammenarbeit verstehen, indem Sie die Anzahl der erstellten pro-Umfragen und pro-Umfragen betrachten, auf die die Benutzer geantwortet haben. 
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen. 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>So gelangen Sie zum Formular pro-Aktivitätsbericht

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.

    
2. Wählen Sie in der Dropdownliste **Bericht auswählen** die Option **Forms pro** - \> **Aktivität**aus.

## <a name="interpret-the-forms-activity-report"></a>Interpretieren des Berichts "Formular Aktivität"

Sie können eine Ansicht der Formulare pro-Aktivität Ihres Benutzers abrufen, indem Sie die Diagramme " **Aktivität** " und " **Benutzer** " betrachten. 

![Formular Aktivitätsbericht](../../media/formsproactivity.png)

|Element|Beschreibung|
|:-----|:-----|
|1.  <br/> |Der **Formular pro** -Aktivitätsbericht kann für Trends in den letzten 7 Tagen, 30 Tagen, 90 Tagen oder 180 Tagen angezeigt werden. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).   <br/> |
|2.  <br/> |Die Daten in jedem Bericht sind in der Regel so aktuell wie die letzten 48 Stunden.  <br/> |
|3.  <br/> |In der Ansicht **Benutzer** können Sie den Trend bei der Anzahl aktiver Formulare pro-Benutzer verstehen. Ein Benutzer wird als aktiv betrachtet, wenn er eine Aktivität um eine pro-Umfrage (erstellen, bearbeiten, Anzeigen usw.) innerhalb eines bestimmten Zeitraums ausgeführt hat.  <br/> |
|4.  <br/> |Die **Aktivitäts** Ansicht hilft Ihnen, den Trend bei der Anzahl aktiver Benutzer zu verstehen. Ein Benutzer wird als "aktiv" betrachtet, wenn er innerhalb eines bestimmten Zeitraums eine Dateiaktivität (Speichern, Synchronisieren, Ändern oder Freigeben) ausgeführt oder eine Seite besucht hat.<br/> Hinweis: eine Aktivität kann mehrere Male für eine einzelne Umfrage auftreten, wird aber nur als eine aktive Umfrage gezählt. Sie können beispielsweise eine pro-Umfrage erstellen und die gleiche Umfrage in einem bestimmten Zeitraum mehrmals bearbeiten, und Sie wird nur als eine einzige Umfrage gezählt. <br>|
|5.<br/>|Im Diagramm **Benutzer** ist die Y-Achse die Anzahl der eindeutigen Benutzer. X-Achse ist das Datum, an dem die eindeutigen Benutzer aktiv sind. Die Legenden sind:<br/><br/>**Designer** bedeutet, dass der Benutzer eine Formulare pro-Umfrage erstellt oder bearbeitet hat.<br><br>Im **Aktivitäts** Diagramm ist die Y-Achse die Anzahl von Formular pro-Antworten pro Umfrage. X-Achse ist das Datum, an dem die Umfrage-oder Antwort Aktivität aufgetreten ist. Die Legenden sind:<br/><br/>" **Erstellte Umfragen** " ist die Anzahl der eindeutigen Formulare pro-Umfragen, die von den Benutzern erstellt wurden.<br>**Antworten** ist die Anzahl anonymer oder nicht anonymer Antworten, die die Benutzer, die die Umfrage erhalten haben, übermittelt haben. |
|6.<br/>|Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Wählen Sie beispielsweise im Diagramm Benutzer die Option Designer, Responder oder Gesamtbenutzer aus, um nur die zugehörigen Informationen anzuzeigen. Wenn Sie diese Auswahl ändern, werden die Informationen in der Raster Tabelle darunter nicht geändert.|
|7.<br/>|Die Tabelle zeigt eine Aufschlüsselung der Aktivitäten auf Einzelbenutzerebene. Die Legenden sind:<br/><br/>**Username** ist die e-Mail-Adresse des Benutzers, der die Aktivität in Microsoft Forms ausgeführt hat.<br/>**Datum der letzten Aktivität (UTC)** ist das letzte Datum, an dem eine Formular Aktivität vom Benutzer für den ausgewählten Datumsbereich ausgeführt wurde. Um Aktivitäten anzuzeigen, die an einem bestimmten Datum stattfanden, wählen Sie das Datum direkt im Diagramm aus.<br/>Dadurch wird die Tabelle so gefiltert, dass Datei Aktivitätsdaten nur für Benutzer angezeigt werden, die die Aktivität an diesem bestimmten Tag ausgeführt haben.<br/><br/>" **Anzahl der erstellten Umfragen** " ist die Anzahl der vom Benutzer erstellten Umfragen.<br/> **Anzahl der Umfrage Antworten** ist die Anzahl der Antworten von antwortern, an die die Umfrage verteilt wurde.|
|8.<br/>|Wählen Sie das Symbol " **Spalten verwalten** " aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.|
|9.<br/>|Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten für alle Benutzer exportiert, und Sie können einfache Aggregation, Sortierung und Filterung für weitere Analysen durchführen. Wenn Sie über weniger als 100 Benutzer verfügen, können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Wenn Sie über mehr als 100 Benutzer verfügen, müssen Sie die Daten exportieren, um Sie zu filtern und zu sortieren.|