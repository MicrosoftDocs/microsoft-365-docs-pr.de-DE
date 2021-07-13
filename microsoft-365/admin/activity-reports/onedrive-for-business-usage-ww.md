---
title: Microsoft 365 Berichte im Admin Center – OneDrive for Business Nutzung
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 'Informieren Sie sich über den OneDrive for Business Nutzungsbericht über die Gesamtanzahl der Dateien und des Speichers, die in Ihrer Organisation verwendet werden. '
ms.openlocfilehash: 92dd18c8e8f6ded655ac6f41d1179e96ef81090b
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393343"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365 Berichte im Admin Center – OneDrive for Business Nutzung

Das Dashboard Microsoft 365 **Berichte** zeigt Ihnen die Aktivitätsübersicht für alle Produkte in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Die OneDrive Karte auf dem Dashboard bietet beispielsweise einen allgemeinen Überblick über den Wert, den Sie OneDrive for Business hinsichtlich der Anzahl von Dateien und des Ihrer Organisation verwendeten Speichers erhalten. Anschließend können Sie darin einen Drilldown ausführen, um die Trends der aktiven OneDrive Konten, die Anzahl von Dateien, mit denen Benutzer interagieren, sowie den verwendeten Speicher nachzuvollziehen. Außerdem werden Details pro Konto angezeigt OneDrive.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtsleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-, Teams- oder Skype for Business administrator sein, um Berichte anzeigen zu können.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Wie erhalte ich den OneDrive-Aktivitätsbericht?

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf die Schaltfläche **"Weitere Anzeigen"** auf der OneDrive Karte.
  
## <a name="interpret-the-onedrive-usage-report"></a>Interpretieren des Berichts zur Verwendung von OneDrive

Sie können die Verwendung im bericht OneDrive anzeigen, indem Sie die Registerkarte **"Nutzung"** auswählen.<br/>![Microsoft 365 Berichte – Microsoft OneDrive Verwendungsbericht.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Wählen Sie **"Spalten auswählen"** aus, um Dem Bericht Spalten hinzuzufügen oder daraus zu entfernen.  <br/> ![OneDrive Nutzungsbericht – Spalten auswählen](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|URL  <br/> |Die Webadresse für die OneDrive des Benutzers. <br/> |
|Gelöscht  <br/> |Der Löschstatus des OneDrive. Es dauert mindestens 7 Tage bis Konten als gelöscht gekennzeichnet werden.  <br/> |
|Besitzer  <br/> |Der Benutzername des primären Administrators des OneDrive.   <br/> |
|Besitzerprinzipalname  <br/> |Die E-Mail-Adresse des Besitzers des OneDrive. <br/> |
|Datum der letzten Aktivität (UTC)  <br/> | Das neueste Datum, an dem eine Dateiaktivität im OneDrive ausgeführt wurde. Wenn die OneDrive keine Dateiaktivität aufweist, bleibt der Wert leer.  <br/> |
|Dateien  <br/> |Die Anzahl der Dateien im OneDrive. <br/>|
|Aktive Dateien  <br/> | Die Anzahl der aktiven Dateien innerhalb des Zeitraums.<br/> HINWEIS: Wenn Dateien während des angegebenen Zeitraums für den Bericht entfernt wurden, kann die Anzahl der aktiven Dateien, die im Bericht angezeigt werden, größer sein als die aktuelle Anzahl von Dateien im OneDrive. >  Gelöschte Benutzer werden in Berichten für 180 Tage weiterhin angezeigt.  <br/> |
|verwendeter Storage (MB)  <br/> |Der Speicherplatz, den die OneDrive in MB verwendet. |
|||