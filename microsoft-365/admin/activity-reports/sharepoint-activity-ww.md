---
title: Microsoft 365-Berichte im Admin Center – SharePoint-Aktivität
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Rufen Sie den SharePoint-Aktivitäts Verwendungsbericht ab, um die Aktivität aller SharePoint-Benutzer, die Anzahl der freigegebenen Dateien und die Speicherauslastung zu kennen.
ms.openlocfilehash: 1d4b288fed9e15139c92bc7e43795393d03ba2fb
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649834"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Microsoft 365-Berichte im Admin Center – SharePoint-Aktivität

Als Microsoft 365-Administrator zeigt das Dashboard **Berichte** die Aktivitätsübersicht für verschiedene Produkte in Ihrer Organisation an. Hiermit können Sie einen Drilldown ausführen, um genauere Einblicke in die Aktivitäten für die einzelnen Produkte zu erhalten. Schauen Sie sich die [Aktivitätsberichte im Microsoft 365 Admin Center an](activity-reports.md).
  
Sie können z. B. die Aktivität jedes Benutzers verstehen, der für die Verwendung von SharePoint lizenziert ist, indem Sie dessen Interaktion mit Dateien betrachten. Außerdem hilft es Ihnen, das Ausmaß der Zusammenarbeit zu erkennen, indem Sie sich die Anzahl der freigegebenen Dateien anschauen.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen. 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>Wie gelange ich zum SharePoint-Aktivitätsbericht?

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf der SharePoint-Karte auf die Schaltfläche **mehr anzeigen** .
  
## <a name="interpret-the-sharepoint-activity-report"></a>Interpretieren des SharePoint-Aktivitätsberichts

Sie können die Aktivitäten im SharePoint-Bericht anzeigen, indem Sie die Registerkarte **Aktivität** auswählen.<br/>![Microsoft 365 Reports-Microsoft SharePoint-Aktivitätsbericht.](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

Wählen Sie **Spalten auswählen** aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.  <br/> ![SharePoint-Aktivitätsbericht – Spalten auswählen](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Username  <br/> |Die e-Mail-Adresse des Benutzers, der die Aktivität auf der SharePoint-Website ausgeführt hat.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum, an dem eine Dateiaktivität ausgeführt wurde oder eine Seite wurde für den ausgewählten Datumsbereich besucht. Um Aktivitäten anzuzeigen, die an einem bestimmten Datum stattfanden, wählen Sie das Datum direkt im Diagramm aus.  <br/> |
|Betrachtete oder bearbeitete Dateien  <br/> |Die Anzahl der Dateien, die der Benutzer hochgeladen, heruntergeladen, geändert oder angezeigt hat.   <br/> |
|Synchronisierte Dateien  <br/> |Die Anzahl der Dateien, die vom lokalen Gerät eines Benutzers mit der SharePoint-Website synchronisiert wurden. <br/> |
|Intern freigegebene Dateien  <br/> | Die Anzahl der Dateien, die für Benutzer innerhalb der Organisation oder für Benutzer innerhalb von Gruppen (die auch externe Benutzer enthalten können) freigegeben wurden.  <br/> |
|Extern freigegebene Dateien  <br/> |Die Anzahl der Dateien, die für Benutzer außerhalb der Organisation freigegeben wurden. <br/>|
|Besuchte Seiten  <br/> |Die Besuche auf eindeutigen Seiten durch den Benutzer. <br/>|
|Gelöscht  <br/> | Dies deutet darauf hin, dass die Lizenz des Benutzers entfernt wurde.  <br/>  **Hinweis:** Aktivitäten für einen gelöschten Benutzer werden weiterhin im Bericht angezeigt, solange er während des ausgewählten Zeitraums zu einem bestimmten Zeitpunkt lizenziert wurde. Durch die Spalte "Gelöscht" werden Sie darauf aufmerksam gemacht, dass der Benutzer möglicherweise nicht mehr aktiv ist, aber zu den Daten im Bericht beigetragen hat.  <br/> |
|Gelöschtes Datum  <br/> |Das Datum, an dem die Lizenz des Benutzers entfernt wurde. <br/>|
|Produkt zugewiesen  <br/> |Die Microsoft 365-Produkte, die für den Benutzer lizenziert sind.|
|||