---
title: Microsoft 365-Berichte im Admin Center – Microsoft 365-Apps-Nutzung
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
description: Erfahren Sie, wie Sie einen Microsoft 365 Apps for Usage Report mithilfe des Microsoft 365 Reports-Dashboards im Microsoft 365 Admin Center erhalten.
ms.openlocfilehash: 5b45e7994126018701c409d4fbfc6f1172924773
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644267"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Microsoft 365-Berichte im Admin Center – Microsoft 365-Apps-Nutzung

Das Microsoft 365 **Reports-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.

 Sie können beispielsweise die Aktivitäten der einzelnen Benutzer verstehen, die für die Verwendung von Microsoft 365-Apps-Apps lizenziert sind, indem Sie sich deren Aktivitäten in den Apps und deren Nutzung auf verschiedenen Plattformen anschauen.


 > [!NOTE]
 > Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können. Aktivierungen freigegebener Computer werden in diesem Bericht nicht unterstützt.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>So erhalten Sie den Microsoft 365 Apps-Nutzungsbericht

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der  Dashboard-Homepage auf der Karte Aktive Benutzer – Microsoft 365 Apps auf die Schaltfläche Weitere Anzeigen.

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Interpretieren des Microsoft 365 Apps-Nutzungsberichts

Sie können einen Einblick in die Microsoft 365-Apps-Aktivität Ihres Benutzers erhalten, indem Sie sich die Benutzer- **und** **Plattformdiagramme** ansehen.

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Apps-Nutzungsbericht](../../media/0bcf67e6-a6e4-4109-a215-369f9f20ad84.png)

|Element|Beschreibung|
 |:-----|:-----|
 |1. <br/> |Der **Microsoft 365** Apps-Nutzungsbericht kann für Trends der letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt werden. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde). <br/> |
 |2. <br/> |Die Daten in den einzelnen Berichten decken in der Regel bis zu den letzten sieben Tagen ab. <br/> |
 |3. <br/> |Die **Benutzeransicht** zeigt den Trend in der Anzahl der aktiven Benutzer für jede App – Outlook, Word, Excel, PowerPoint, OneNote und Teams. "Aktive Benutzer" sind alle Personen, die beabsichtigte Aktionen in diesen Apps ausführen. <br/> |
 |4. <br/> |Die **Ansicht Plattformen** zeigt den Trend aktiver Benutzer für alle Apps für jede Plattform – Windows, Mac, Web und Mobile. <br/> |
 |5.<br/>|Im Diagramm **Benutzer** ist die Y-Achse die Anzahl der eindeutigen aktiven Benutzer für die jeweilige App. Im **Diagramm Plattformen**   ist die Y-Achse die Anzahl eindeutiger Benutzer für die jeweilige Plattform. Die X-Achse in beiden Diagrammen ist das Datum, an dem eine App auf einer bestimmten Plattform verwendet wurde.<br/>|
 6.<br/>|Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Wählen Sie im  Diagramm Benutzer beispielsweise Outlook, Word, Excel, PowerPoint, OneDrive oder Teams aus, um nur die informationen zu den einzelnen zu sehen. Wenn Sie diese Auswahl ändern, werden die Informationen in der darunter stehenden Rastertabelle nicht geändert.|
 |7.<br/>|Die Tabelle zeigt eine Auflistung der Daten nach Benutzerebene. Sie können Spalten zur Tabelle hinzufügen oder aus der Tabelle entfernen. <br/><br/>**Benutzername** ist die E-Mail-Adresse des Benutzers, der die Aktivität in Microsoft Apps ausgeführt hat.<br><br/>**Das letzte Aktivierungsdatum (UTC)** ist das letzte Datum, an dem der Benutzer sein Microsoft 365 Apps-Abonnement aktiviert hat.<br/><br/>**Das Datum der letzten Aktivität (UTC)** ist das letzte Datum, an dem eine beabsichtigte Aktivität vom Benutzer ausgeführt wurde. Um Aktivitäten anzuzeigen, die an einem bestimmten Datum stattfanden, wählen Sie das Datum direkt im Diagramm aus.<br/><br/>Die anderen Spalten identifizieren, ob der Benutzer in dem ausgewählten Zeitraum auf dieser Plattform für diese App (innerhalb von Microsoft 365 Apps) aktiv war. |
 |8.<br/>|Wählen Sie **das Symbol Spalten auswählen** aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.|
 |9.<br/>|Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten für alle Benutzer exportiert, und Sie können einfache Aggregation, Sortierung und Filterung für weitere Analysen durchführen. Wenn Sie weniger als 100 Benutzer haben, können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Wenn Sie mehr als 100 Benutzer haben, müssen Sie die Daten exportieren, um filtern und sortieren zu können.|
