---
title: Microsoft 365-Berichte im Admin Center – OneDrive for Business-Nutzung
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
description: 'Erfahren Sie im OneDrive for Business-Nutzungsbericht, wie viele Dateien und Speicherplatz in Ihrer Organisation insgesamt verwendet werden. '
ms.openlocfilehash: 54a3b1e041ee6155b5ce89d6cd5bc73233d1f69b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579542"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365-Berichte im Admin Center – OneDrive for Business-Nutzung

Das Microsoft 365 **Reports-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Die OneDrive Karte auf dem Dashboard bietet beispielsweise einen allgemeinen Überblick über den Wert, den Sie OneDrive for Business hinsichtlich der Anzahl von Dateien und des Ihrer Organisation verwendeten Speichers erhalten. Anschließend können Sie darin einen Drilldown ausführen, um die Trends der aktiven OneDrive Konten, die Anzahl von Dateien, mit denen Benutzer interagieren, sowie den verwendeten Speicher nachzuvollziehen. Außerdem werden Details pro Konto angezeigt OneDrive.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams Communications- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Wie erhalte ich den OneDrive-Aktivitätsbericht?

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Startseite des Dashboards **auf** die Schaltfläche Weitere Anzeigen auf der OneDrive-Karte.
  
## <a name="interpret-the-onedrive-usage-report"></a>Interpretieren des Berichts zur Verwendung von OneDrive

Sie können die Verwendung im #A0 anzeigen, indem Sie die Registerkarte **Verwendung** auswählen.<br/>![Microsoft 365-Berichte – Microsoft OneDrive-Nutzungsbericht.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Wählen **Sie Spalten auswählen** aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.  <br/> ![#A0 – Spalten auswählen](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|URL  <br/> |Die Webadresse für das OneDrive des Benutzers. <br/> |
|Gelöscht  <br/> |Der Löschstatus von OneDrive. Es dauert mindestens 7 Tage bis Konten als gelöscht gekennzeichnet werden.  <br/> |
|Besitzer  <br/> |Der Benutzername des primären Administrators von OneDrive.   <br/> |
|Besitzerprinzipalname  <br/> |Die E-Mail-Adresse des Besitzers von OneDrive. <br/> |
|Datum der letzten Aktivität (UTC)  <br/> | Das letzte Datum, an dem eine Dateiaktivität in OneDrive ausgeführt wurde. Wenn die OneDrive keine Dateiaktivität aufweist, bleibt der Wert leer.  <br/> |
|Dateien  <br/> |Die Anzahl der Dateien in OneDrive. <br/>|
|Aktive Dateien  <br/> | Die Anzahl der aktiven Dateien innerhalb des Zeitraums.<br/> HINWEIS: Wenn Dateien während des angegebenen Zeitraums für den Bericht entfernt wurden, kann die Anzahl der im Bericht angezeigten aktiven Dateien größer als die aktuelle Anzahl von Dateien in OneDrive sein. >  Gelöschte Benutzer werden in Berichten für 180 Tage weiterhin angezeigt.  <br/> |
|Verwendeter Speicher (MB)  <br/> |Die Speichermenge, die OneDrive in MB verwendet. |
|||