---
title: Microsoft 365-Berichte im Admin Center-Microsoft 365 apps Usage
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
description: Erfahren Sie, wie Sie einen Microsoft 365 apps for Usage-Bericht mithilfe des Microsoft 365-Berichts Dashboards im Microsoft 365 Admin Center erhalten.
ms.openlocfilehash: 0c30cee0c1abd76553d3adfebebb8fe38e92c56a
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611917"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Microsoft 365-Berichte im Admin Center-Microsoft 365 apps Usage

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.

 Sie können beispielsweise die Aktivität jedes Benutzers verstehen, der für die Verwendung von Microsoft 365 apps-apps lizenziert ist, indem Sie sich Ihre Aktivitäten in den apps ansehen und wie Sie plattformübergreifend verwendet werden.


 > [!NOTE]
 > Sie müssen ein globaler Administrator, ein globaler Leser oder ein berichtsleser in Microsoft 365 oder ein Exchange-, SharePoint-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>So gelangen Sie zum Microsoft 365 apps-Nutzungsbericht

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf die Schaltfläche **mehr anzeigen** der aktiven Benutzer – Microsoft 365-apps-Karte.

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Interpretieren des Verwendungsberichts für Microsoft 365-apps

Sie können die Microsoft 365-apps-Aktivität Ihres Benutzers anzeigen, indem Sie sich die Diagramme **Users** und **Platform** ansehen.

![Microsoft 365 apps-Nutzungsbericht](../../media/0bcf67e6-a6e4-4109-a215-369f9f20ad84.png)

|Element|Beschreibung|
 |:-----|:-----|
 |1. <br/> |Der **Microsoft 365 apps-Verwendungs** Bericht kann für Trends in den letzten 7 Tagen, 30 Tagen, 90 Tagen oder 180 Tagen angezeigt werden. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde). <br/> |
 |2. <br/> |Die Daten in den einzelnen Berichten umfassen in der Regel bis zu den letzten sieben Tagen. <br/> |
 |3. <br/> |In der Ansicht **Benutzer** wird der Trend zur Anzahl der aktiven Benutzer für jede APP angezeigt – Outlook, Word, Excel, PowerPoint, OneNote und Microsoft Teams. "Aktive Benutzer" sind alle, die absichtlich Aktionen in diesen apps durchführen. <br/> |
 |4. <br/> |Die Ansicht **Plattformen** zeigt den Trend der aktiven Benutzer in allen Apps für jede Plattform – Windows, Mac, Internet und Mobile. <br/> |
 |5.<br/>|Im Diagramm **Benutzer** ist die Y-Achse die Anzahl der eindeutigen aktiven Benutzer für die jeweilige app. Im Diagramm **Plattformen**   ist die Y-Achse die Anzahl der eindeutigen Benutzer für die jeweilige Plattform. Die X-Achse in beiden Diagrammen ist das Datum, an dem eine APP auf einer bestimmten Plattform verwendet wurde.<br/>|
 6.<br/>|Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Wählen Sie beispielsweise im Diagramm **Benutzer** die Option Outlook, Word, Excel, PowerPoint, OneDrive oder Teams aus, um nur die zugehörigen Informationen anzuzeigen. Wenn Sie diese Auswahl ändern, werden die Informationen in der Raster Tabelle darunter nicht geändert.|
 |7.<br/>|Die Tabelle zeigt eine Auflistung der Daten nach Benutzerebene. Sie können Spalten zur Tabelle hinzufügen oder aus der Tabelle entfernen. <br/><br/>**Username** ist die e-Mail-Adresse des Benutzers, der die Aktivität in Microsoft apps ausgeführt hat.<br><br/>**Datum der letzten Aktivierung (UTC)** ist das Datum, an dem der Benutzer sein Microsoft 365-apps-Abonnement zuletzt aktiviert hat.<br/><br/>**Datum der letzten Aktivität (UTC)** ist das letzte Datum, an dem eine absichtliche Aktivität vom Benutzer ausgeführt wurde. Um Aktivitäten anzuzeigen, die an einem bestimmten Datum stattfanden, wählen Sie das Datum direkt im Diagramm aus.<br/><br/>In den anderen Spalten wird ermittelt, ob der Benutzer auf dieser Plattform für diese APP (innerhalb von Microsoft 365-Apps) in dem ausgewählten Zeitraum aktiv war. |
 |8.<br/>|Wählen Sie das Symbol **Spalten auswählen** aus, um Spalten aus dem Bericht hinzuzufügen oder daraus zu entfernen.|
 |9.<br/>|Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten für alle Benutzer exportiert, und Sie können eine einfache Aggregation, Sortierung und Filterung für weitere Analysen durchführen. Wenn Sie über weniger als 100 Benutzer verfügen, können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Wenn Sie über mehr als 100 Benutzer verfügen, müssen Sie die Daten exportieren, um Sie zu filtern und zu sortieren.|
