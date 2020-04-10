---
title: Microsoft 365-Berichte im Admin Center – ProPlus-Nutzung
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: Informationen zum Abrufen eines ProPlus-Verwendungsberichts mithilfe des Microsoft 365 Reports-Dashboards im Microsoft 365 Admin Center.
ms.openlocfilehash: f697b6bcf0ae53c028ce2f13a97b1e11134a6112
ms.sourcegitcommit: 8a88b7526e6a3a907f33a8567e0d25b74fe60d80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43204078"
---
# <a name="microsoft-365-reports-in-the-admin-center---proplus-usage"></a>Microsoft 365-Berichte im Admin Center – ProPlus-Nutzung

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Sie können beispielsweise die Aktivität jedes Benutzers verstehen, der für die Verwendung von ProPlus-apps lizenziert ist, indem Sie sich Ihre Aktivitäten in den apps ansehen und wie Sie plattformübergreifend verwendet werden.  
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein berichtsleser in Microsoft 365 oder ein Exchange-, SharePoint-oder Skype for Business-Administrator sein, um Berichte anzuzeigen. 

## <a name="how-to-get-to-the-proplus-usage-report"></a>So gelangen Sie zum ProPlus-Verwendungsbericht

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.

    
2. Wählen Sie in der Dropdownliste **Bericht auswählen** die Option **Office 365** \> **ProPlus-Verwendung** aus.

## <a name="interpret-the-proplus-usage-report"></a>Interpretieren des ProPlus-Verwendungsberichts

Sie können eine Ansicht der ProPlus-Aktivität Ihrer Benutzer erhalten, indem Sie sich die Diagramme **Users** und **Platform** ansehen. 

![ProPlus-Verwendungsbericht](../../media/proplususagenumbers.png)

|||
|:-----|:-----|
|1.  <br/> |Der **ProPlus-Verwendungs** Bericht kann für Trends in den letzten 7 Tagen, 30 Tagen, 90 Tagen oder 180 Tagen angezeigt werden. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab.  <br/> |
|3.  <br/> |Die **Benutzer** Ansicht IEW zeigt den Trend bei der Anzahl der aktiven Benutzer für jede APP – Outlook, Word, Excel, PowerPoint, OneNote und Microsoft Teams. "Aktive Benutzer" sind alle, die absichtlich Aktionen in diesen apps durchführen.  <br/> |
|4.  <br/> |Die Ansicht **Plattformen** zeigt den Trend der aktiven Benutzer in allen Apps für jede Plattform – Windows, Mac, Internet und Mobile. <br/> |
|5.<br/>|Im Diagramm **Benutzer** ist die Y-Achse die Anzahl der eindeutigen aktiven Benutzer für die jeweilige app. Im Diagramm **Plattformen** ist die Y-Achse die Anzahl der eindeutigen Benutzer für die jeweilige Plattform. X-Achse in beiden Diagrammen ist das Datum, an dem eine APP auf einer bestimmten Plattform. RM verwendet wurde.<br/>|
|6.<br/>|Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Wählen Sie beispielsweise im Diagramm **Benutzer** die Option Outlook, Word, Excel, PowerPoint, OneDrive oder Teams aus, um nur die zugehörigen Informationen anzuzeigen. Wenn Sie diese Auswahl ändern, werden die Informationen in der Raster Tabelle darunter nicht geändert.|
|7.<br/>|Die Tabelle zeigt eine Auflistung der Daten nach Benutzerebene. Sie können Spalten zur Tabelle hinzufügen oder aus der Tabelle entfernen. <br/><br/>**Username** ist die e-Mail-Adresse des Benutzers, der die Aktivität in Microsoft apps ausgeführt hat.<br><br/>**Datum der letzten Aktivierung (UTC)** ist das Datum, an dem der Benutzer sein ProPlus-Abonnement zuletzt aktiviert hat.<br/><br/>**Datum der letzten Aktivität (UTC)** ist das letzte Datum, an dem eine absichtliche Aktivität vom Benutzer ausgeführt wurde. Um Aktivitäten anzuzeigen, die an einem bestimmten Datum stattfanden, wählen Sie das Datum direkt im Diagramm aus.<br/><br/>Die folgenden Spalten, die den einzelnen apps entsprechen, die ermitteln, ob der Benutzer in der ausgewählten Periode für diese APP aktiv war:<br> <br>**Outlook** <br>**Word** <br>**Excel**<br>**PowerPoint** <br>**OneNote**<br><br> Die folgenden Spalten entsprechen den einzelnen Plattformen, die ermitteln, ob der Benutzer auf dieser Plattform für eine beliebige app (innerhalb von ProPlus) in der ausgewählten Zeitspanne aktiv war:<br><br>**Outlook (Windows)**<br>**Outlook (Mac)**<br>**Outlook (im Internet)** <br>**Outlook (mobil)**<br> **Word (Windows)**<br> **Word (Mac)**<br> **Word (Internet)**<br> **Word (mobil)**<br> **Excel (Windows)**<br> **Excel (Mac)**<br> **Excel (im Internet)**<br> **Excel (Mobile)**<br> **PowerPoint (Windows)**<br> **PowerPoint (Mac)**<br>**PowerPoint (Internet)**<br> **PowerPoint (mobil)**<br> **OneNote (Windows)**<br> **OneNote (Mac)**<br> **OneNote (im Internet)**<br>**OneNote (mobil)**<br> **Teams (Windows)**<br> **Teams (Mac)**<br> **Teams (im Internet)**<br>**Teams (mobil)** |
|8.<br/>|Wählen Sie das Symbol " **Spalten verwalten** " aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.|
|9.<br/>|Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten für alle Benutzer exportiert, und Sie können einfache Aggregation, Sortierung und Filterung für weitere Analysen durchführen. Wenn Sie über weniger als 100 Benutzer verfügen, können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Wenn Sie über mehr als 100 Benutzer verfügen, müssen Sie die Daten exportieren, um Sie zu filtern und zu sortieren.|