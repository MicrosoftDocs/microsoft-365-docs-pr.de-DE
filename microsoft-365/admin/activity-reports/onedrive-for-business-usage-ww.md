---
title: Microsoft 365-Berichte im Admin Center – OneDrive für Unternehmen Nutzung
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
description: 'Erhalten Sie den Bericht über die OneDrive für Unternehmen Nutzung, um die Gesamtzahl der in Ihrer Organisation verwendeten Dateien und Speicher zu kennen. '
ms.openlocfilehash: 3855c7d06d202ee4d0590fcf5b8ca758d8120133
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649805"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365-Berichte im Admin Center – OneDrive für Unternehmen Nutzung

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Die OneDrive Karte auf dem Dashboard bietet beispielsweise einen allgemeinen Überblick über den Wert, den Sie OneDrive for Business hinsichtlich der Anzahl von Dateien und des Ihrer Organisation verwendeten Speichers erhalten. Anschließend können Sie darin einen Drilldown ausführen, um die Trends der aktiven OneDrive Konten, die Anzahl von Dateien, mit denen Benutzer interagieren, sowie den verwendeten Speicher nachzuvollziehen. Außerdem werden Details pro Konto angezeigt OneDrive.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Wie erhalte ich den OneDrive-Aktivitätsbericht?

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf die Schaltfläche **mehr anzeigen** auf der OneDrive-Karte.
  
## <a name="interpret-the-onedrive-usage-report"></a>Interpretieren des Berichts zur Verwendung von OneDrive

Sie können die Verwendung im Bericht OneDrive anzeigen, indem Sie auf die Registerkarte **Verwendung** wählen.<br/>![Microsoft 365 Reports-Microsoft OneDrive Nutzungsbericht.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Wählen Sie **Spalten auswählen** aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.  <br/> ![OneDrive-Verwendungsbericht – Spalten auswählen](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|URL  <br/> |Die Webadresse für das OneDrive des Benutzers. <br/> |
|Gelöscht  <br/> |Der Löschstatus des OneDrive. Es dauert mindestens 7 Tage bis Konten als gelöscht gekennzeichnet werden.  <br/> |
|Besitzer  <br/> |Der Benutzername des primären Administrators des OneDrive.   <br/> |
|Besitzer Prinzipalname  <br/> |Die e-Mail-Adresse des Besitzers des OneDrive. <br/> |
|Datum der letzten Aktivität (UTC)  <br/> | Das letzte Datum, an dem eine Dateiaktivität in OneDrive durchgeführt wurde. Wenn die OneDrive keine Dateiaktivität aufweist, bleibt der Wert leer.  <br/> |
|Dateien  <br/> |Die Anzahl der Dateien in der OneDrive. <br/>|
|Aktive Dateien  <br/> | Die Anzahl der aktiven Dateien innerhalb des Zeitraums.<br/> Hinweis: Wenn Dateien während des angegebenen Zeitraums für den Bericht entfernt wurden, kann die Anzahl der aktiven Dateien, die im Bericht angezeigt werden, größer sein als die aktuelle Anzahl der Dateien im OneDrive. >  Gelöschte Benutzer werden in Berichten für 180 Tage weiterhin angezeigt.  <br/> |
|Verwendeter Speicherplatz (MB)  <br/> |Die Menge an Speicherplatz, die die OneDrive in MB verwendet. |
|||