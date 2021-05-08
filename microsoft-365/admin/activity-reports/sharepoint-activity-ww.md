---
title: Microsoft 365 Berichte im Admin Center – SharePoint Aktivitäten
f1.keywords:
- NOCSH
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
- MST160
- MET150
- MOE150
description: Erhalten Sie SharePoint Aktivitätsverwendungsbericht, um informationen über die Aktivität jedes einzelnen SharePoint, die Anzahl der freigegebenen Dateien und die Speicherauslastung.
ms.openlocfilehash: f049a67e8444654e05cfe3dc72a8d4fe39792cb2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244080"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Microsoft 365 Berichte im Admin Center – SharePoint Aktivitäten

Als Microsoft 365 zeigt Ihnen das **Dashboard** Berichte die Aktivitätsübersicht für verschiedene Produkte in Ihrer Organisation. Hiermit können Sie einen Drilldown ausführen, um genauere Einblicke in die Aktivitäten für die einzelnen Produkte zu erhalten. Sehen Sie sich die [Aktivitätsberichte im Microsoft 365 Admin Center an.](activity-reports.md)
  
Sie können z. B. die Aktivität jedes Benutzers verstehen, der für die Verwendung von SharePoint lizenziert ist, indem Sie dessen Interaktion mit Dateien betrachten. Außerdem hilft es Ihnen, das Ausmaß der Zusammenarbeit zu erkennen, indem Sie sich die Anzahl der freigegebenen Dateien anschauen.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams-Kommunikations- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können. 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>Wie gelange ich zum SharePoint-Aktivitätsbericht?

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Startseite des Dashboards auf **die** Schaltfläche Weitere Anzeigen auf der SharePoint Karte.
  
## <a name="interpret-the-sharepoint-activity-report"></a>Interpretieren des SharePoint Aktivitätsberichts

Sie können die Aktivitäten im SharePoint anzeigen, indem Sie die Registerkarte **Aktivität** auswählen.<br/>![Microsoft 365 - Microsoft SharePoint Aktivitätsbericht.](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

Wählen **Sie Spalten auswählen** aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.  <br/> ![SharePoint Aktivitätsbericht – Spalten auswählen](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Benutzername  <br/> |Die E-Mail-Adresse des Benutzers, der die Aktivität auf der website SharePoint hat.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum, an dem eine Dateiaktivität ausgeführt oder eine Seite für den ausgewählten Datumsbereich besucht wurde. Um Aktivitäten anzuzeigen, die an einem bestimmten Datum stattfanden, wählen Sie das Datum direkt im Diagramm aus.  <br/> |
|Angezeigte oder bearbeitete Dateien  <br/> |Die Anzahl der Dateien, die der Benutzer hochgeladen, heruntergeladen, geändert oder angezeigt hat.   <br/> |
|Synchronisierte Dateien  <br/> |Die Anzahl der Dateien, die vom lokalen Gerät eines Benutzers mit dem lokalen SharePoint wurden. <br/> |
|Intern freigegebene Dateien  <br/> | Die Anzahl der Dateien, die für Benutzer innerhalb der Organisation oder für Benutzer innerhalb von Gruppen (die auch externe Benutzer enthalten können) freigegeben wurden.  <br/> |
|Extern freigegebene Dateien  <br/> |Die Anzahl der Dateien, die für Benutzer außerhalb der Organisation freigegeben wurden. <br/>|
|Besuchte Seiten  <br/> |Die Besuche eindeutiger Seiten durch den Benutzer. <br/>|
|Gelöscht  <br/> | Dies bedeutet, dass die Lizenz des Benutzers entfernt wurde.  <br/>  **HINWEIS:** Die Aktivität für einen gelöschten Benutzer wird weiterhin im Bericht angezeigt, solange er zu einem bestimmten Zeitpunkt während des ausgewählten Zeitraums lizenziert wurde. Durch die Spalte "Gelöscht" werden Sie darauf aufmerksam gemacht, dass der Benutzer möglicherweise nicht mehr aktiv ist, aber zu den Daten im Bericht beigetragen hat.  <br/> |
|Gelöschtes Datum  <br/> |Das Datum, an dem die Lizenz des Benutzers entfernt wurde. <br/>|
|Produkt zugewiesen  <br/> |Die Microsoft 365, die für den Benutzer lizenziert sind.|
|||