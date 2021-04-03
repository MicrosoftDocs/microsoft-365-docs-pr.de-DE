---
title: 'Microsoft 365-Berichte im Admin Center – OneDrive for #A0'
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 'Holen Sie sich den #A0 für Ihre Organisation, und kennen Sie die Aktivitäten jedes OneDrive-Benutzers, die Anzahl der freigegebenen Dateien und die Speicherauslastung.'
ms.openlocfilehash: 7b6173b3a86187e4612aaaa51bafbfbe965a6cfa
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579530"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365-Berichte im Admin Center – OneDrive for #A0

Das Microsoft 365 **Reports-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht zu Berichten](activity-reports.md) an.
  
Sie können z. B. die Aktivität jedes Benutzers verstehen, der für die Verwendung von OneDrive lizenziert ist, indem Sie dessen Interaktion mit Dateien auf OneDrive betrachten. Außerdem hilft es Ihnen, das Ausmaß der Zusammenarbeit zu erkennen, indem Sie die Anzahl der freigegebenen Dateien betrachten.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams Communications- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Wie erhalte ich den OneDrive-Aktivitätsbericht?

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Startseite des Dashboards **auf** die Schaltfläche Weitere Anzeigen auf der OneDrive-Karte.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Interpretieren des Aktivitätsberichts für OneDrive for Business

Sie können die Aktivitäten im #A0 anzeigen, indem Sie die Registerkarte **Aktivität** auswählen.<br/>![Microsoft 365-Berichte – Microsoft OneDrive-Aktivitätsbericht.](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

Wählen **Sie Spalten auswählen** aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.  <br/> ![#A0 – Spalten auswählen](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Username  <br/> |Der Benutzername des Besitzers des OneDrive-Kontos.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum, an dem eine Dateiaktivität für das #A0 für den ausgewählten Datumsbereich ausgeführt wurde. . Um Aktivitäten anzuzeigen, die an einem bestimmten Datum stattfanden, wählen Sie das Datum direkt im Diagramm aus.  <br/> |
|Angezeigte oder bearbeitete Dateien  <br/> |Die Anzahl der Dateien, die der Benutzer hochgeladen, heruntergeladen, geändert oder angezeigt hat.   <br/> |
|Synchronisierte Dateien  <br/> |Die Anzahl der Dateien, die vom lokalen Gerät eines Benutzers mit dem #A0 synchronisiert wurden. <br/> |
|Intern freigegebene Dateien  <br/> | Die Anzahl der Dateien, die für Benutzer innerhalb der Organisation oder für Benutzer innerhalb von Gruppen freigegeben wurden (z. B. externe Benutzer).  <br/> |
|Extern freigegebene Dateien  <br/> |Die Anzahl der Dateien, die für Benutzer außerhalb der Organisation freigegeben wurden. <br/>|
|Gelöscht  <br/> | Dies bedeutet, dass die Lizenz des Benutzers entfernt wurde.  <br/> HINWEIS: Die Aktivität für einen gelöschten Benutzer wird weiterhin in einem Bericht angezeigt, solange er zu einem bestimmten Zeitpunkt während des ausgewählten Zeitraums lizenziert wurde. Der Spalte **Gelöscht** können Sie entnehmen, dass der Benutzer zwar möglicherweise nicht mehr aktiv ist, aber dass der Bericht dennoch ihn betreffende Daten enthält.  <br/> |
|Gelöschtes Datum  <br/> |Das Datum, an dem die Lizenz des Benutzers entfernt wurde. <br/>|
|Produkt zugewiesen  <br/> |Die Microsoft 365-Produkte, die für den Benutzer lizenziert sind.|
|||