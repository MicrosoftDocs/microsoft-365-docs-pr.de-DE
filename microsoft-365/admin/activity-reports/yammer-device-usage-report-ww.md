---
title: Microsoft 365 Berichte im Admin Center – Yammer Geräteverwendungsbericht
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
description: Rufen Sie den Yammer-Geräteverwendungsbericht ab, um Informationen darüber zu erhalten, auf welchen Geräten Ihre Benutzer Yammer nutzen.
ms.openlocfilehash: 817627cac791d35f49cd240ceb48de15ef328ef8
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241844"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Microsoft 365 Berichte im Admin Center – Yammer Geräteverwendungsbericht

Das Microsoft 365 **-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Die Yammer-Geräteverwendungsberichte geben Ihnen Aufschluss darüber, auf welchen Geräten Ihre Benutzer Yammer nutzen. Sie können die Anzahl der täglichen Benutzer nach Gerätetyp sowie die Anzahl der Benutzer pro Gerätetyp anzeigen. Für beide Berichtsarten können Sie einen bestimmten Zeitraum auswählen. Zudem können Sie auch Details für einzelne Benutzer anzeigen.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams-Kommunikations- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.  
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Wie kann ich den Yammer-Geräteverwendungsbericht abrufen?

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Homepage auf **die** Schaltfläche Weitere Anzeigen auf der Yammer Karte.
  
## <a name="interpret-the-yammer-device-usage-report"></a>Interpretieren des Yammer Geräteverwendungsberichts

Sie können die Verwendung im Bericht OneDrive anzeigen, indem Sie die Registerkarte **Geräteverwendung** auswählen.<br/>![Microsoft 365 - Microsoft Yammer Geräteverwendungsbericht.](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

Wählen **Sie Spalten auswählen** aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.  <br/> ![Yammer Geräteverwendungsbericht – Spalten auswählen](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Benutzername  <br/> |Die E-Mail-Adresse des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonymisieren. Dieses Raster zeigt Benutzer an, die sich Yammer mit dem Microsoft 365 angemeldet haben oder die sich über einmaliges Anmelden am Netzwerk angemeldet haben. <br/> |
|Anzeigename  <br/> |Der vollständige Name des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonymisieren.  <br/> |
|Benutzerstatus  <br/> |Einer von drei Werten: Active, Deleted oder Suspended. Diese Berichte zeigen Daten für aktive, angehaltene und gelöschte Benutzer. Sie zeigen keine ausstehenden Benutzer, weil ausstehende Benutzer nicht posten, lesen oder eine Nachricht mit "Gefällt mir" bewerten können.   <br/> |
|Statusänderungsdatum (UTC)  <br/> |Das Datum, an dem der Status des Benutzers in der Yammer.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum (UTC), an dem der Benutzer an einer Yammer teilgenommen hat.  <br/> |
|Netz  <br/> |Gibt an, ob der Benutzer Yammer im Web verwendet hat.  <br/> |
|Windows Telefon  <br/> | Gibt an, ob der Benutzer die Yammer auf einem Windows verwendet hat.  <br/> |
|Android-Smartphone  <br/> |Gibt an, ob der Benutzer Yammer auf einem Android-Smartphone verwendet hat. <br/>|
|iphone <br/> | Gibt an, ob der Benutzer Yammer einem iPhone.  <br/> |
|ipad  <br/> |Gibt an, ob der Benutzer Yammer einem iPad. <br/>|
|other  <br/> |Gibt an, ob der Benutzer Yammer einem anderen Gerät verwendet hat, das zuvor nicht aufgeführt wurde. <br/>|
|||