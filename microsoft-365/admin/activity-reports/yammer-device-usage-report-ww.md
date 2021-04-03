---
title: Microsoft 365-Berichte im Admin Center – Yammer Gerätenutzungsbericht
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
description: Rufen Sie den Yammer-Geräteverwendungsbericht ab, um Informationen darüber zu erhalten, auf welchen Geräten Ihre Benutzer Yammer nutzen.
ms.openlocfilehash: 01749c21dd0f8355556718ee9179244fb250c97a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579470"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Microsoft 365-Berichte im Admin Center – Yammer Gerätenutzungsbericht

Das Microsoft 365 **Reports-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Die Yammer-Geräteverwendungsberichte geben Ihnen Aufschluss darüber, auf welchen Geräten Ihre Benutzer Yammer nutzen. Sie können die Anzahl der täglichen Benutzer nach Gerätetyp sowie die Anzahl der Benutzer pro Gerätetyp anzeigen. Für beide Berichtsarten können Sie einen bestimmten Zeitraum auswählen. Zudem können Sie auch Details für einzelne Benutzer anzeigen.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams Communications- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.  
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Wie kann ich den Yammer-Geräteverwendungsbericht abrufen?

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Homepage auf **die** Schaltfläche Weitere Anzeigen auf der Yammer Karte.
  
## <a name="interpret-the-yammer-device-usage-report"></a>Interpretieren des Yammer Geräteverwendungsberichts

Sie können die Verwendung im #A0 anzeigen, indem Sie die Registerkarte **Geräteverwendung** auswählen.<br/>![Microsoft 365-Berichte – Microsoft Yammer Geräteverwendungsbericht.](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

Wählen **Sie Spalten auswählen** aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.  <br/> ![Yammer Gerätenutzungsbericht – Spalten auswählen](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Username  <br/> |Die E-Mail-Adresse des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonymisieren. Dieses Raster zeigt Benutzer, die sich mit Yammer Microsoft 365-Konto angemeldet haben oder sich über einmaliges Anmelden am Netzwerk angemeldet haben. <br/> |
|Name  <br/> |Der vollständige Name des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonymisieren.  <br/> |
|Benutzerstatus  <br/> |Einer von drei Werten: Active, Deleted oder Suspended. Diese Berichte zeigen Daten für aktive, angehaltene und gelöschte Benutzer. Sie zeigen keine ausstehenden Benutzer, weil ausstehende Benutzer nicht posten, lesen oder eine Nachricht mit "Gefällt mir" bewerten können.   <br/> |
|Statusänderungsdatum (UTC)  <br/> |Das Datum, an dem der Status des Benutzers in der Yammer.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum (UTC), an dem der Benutzer an einer Yammer teilgenommen hat.  <br/> |
|Netz  <br/> |Gibt an, ob der Benutzer Yammer im Web verwendet hat.  <br/> |
|Windows Phone  <br/> | Gibt an, ob der Benutzer Yammer windows phone verwendet hat.  <br/> |
|Android-Smartphone  <br/> |Gibt an, ob der Benutzer Yammer auf einem Android-Smartphone verwendet hat. <br/>|
|iphone <br/> | Gibt an, ob der Benutzer Yammer iPhone verwendet hat.  <br/> |
|ipad  <br/> |Gibt an, ob der Benutzer Yammer iPad verwendet hat. <br/>|
|other  <br/> |Gibt an, ob der Benutzer die Yammer auf einem anderen Gerät verwendet hat, das zuvor nicht aufgeführt wurde. <br/>|
|||