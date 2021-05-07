---
title: Microsoft 365 Berichte im Admin Center – OneDrive for Business Verwendung
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
description: 'Erhalten Sie OneDrive for Business Verwendungsbericht, um mehr über die Gesamtzahl der in Ihrer Organisation verwendeten Dateien und Speicher zu erfahren. '
ms.openlocfilehash: 20b9ce6aff01942c23c0f8a98234432ea54d5953
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52242048"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365 Berichte im Admin Center – OneDrive for Business Verwendung

Das Microsoft 365 **-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Die OneDrive Karte auf dem Dashboard bietet beispielsweise einen allgemeinen Überblick über den Wert, den Sie OneDrive for Business hinsichtlich der Anzahl von Dateien und des Ihrer Organisation verwendeten Speichers erhalten. Anschließend können Sie darin einen Drilldown ausführen, um die Trends der aktiven OneDrive Konten, die Anzahl von Dateien, mit denen Benutzer interagieren, sowie den verwendeten Speicher nachzuvollziehen. Außerdem werden Details pro Konto angezeigt OneDrive.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams-Kommunikations- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Wie erhalte ich den OneDrive-Aktivitätsbericht?

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Startseite des Dashboards auf **die** Schaltfläche Weitere Anzeigen auf der OneDrive Karte.
  
## <a name="interpret-the-onedrive-usage-report"></a>Interpretieren des Berichts zur Verwendung von OneDrive

Sie können die Verwendung im Bericht OneDrive anzeigen, indem Sie die Registerkarte **Verwendung** auswählen.<br/>![Microsoft 365 Berichte – Microsoft OneDrive Verwendungsbericht.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Wählen **Sie Spalten auswählen** aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.  <br/> ![OneDrive Verwendungsbericht – Spalten auswählen](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|URL  <br/> |Die Webadresse für die Benutzeradresse OneDrive. <br/> |
|Gelöscht  <br/> |Der Löschstatus der OneDrive. Es dauert mindestens 7 Tage bis Konten als gelöscht gekennzeichnet werden.  <br/> |
|Besitzer  <br/> |Der Benutzername des primären Administrators der OneDrive.   <br/> |
|Besitzerprinzipalname  <br/> |Die E-Mail-Adresse des Besitzers der OneDrive. <br/> |
|Datum der letzten Aktivität (UTC)  <br/> | Das letzte Datum, an dem eine Dateiaktivität im OneDrive. Wenn die OneDrive keine Dateiaktivität aufweist, bleibt der Wert leer.  <br/> |
|Dateien  <br/> |Die Anzahl der Dateien im OneDrive. <br/>|
|Aktive Dateien  <br/> | Die Anzahl der aktiven Dateien innerhalb des Zeitraums.<br/> HINWEIS: Wenn Dateien während des angegebenen Zeitraums für den Bericht entfernt wurden, ist die Anzahl der aktiven Dateien im Bericht möglicherweise größer als die aktuelle Anzahl von Dateien im OneDrive. >  Gelöschte Benutzer werden in Berichten für 180 Tage weiterhin angezeigt.  <br/> |
|Storage verwendet (MB)  <br/> |Die Speichermenge, die von OneDrive in MB verwendet wird. |
|||