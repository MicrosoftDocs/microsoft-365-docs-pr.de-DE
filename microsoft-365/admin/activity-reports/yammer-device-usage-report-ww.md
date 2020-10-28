---
title: Microsoft 365-Berichte im Admin Center – Nutzungsbericht zum Jammern von Geräten
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
description: Rufen Sie den Yammer-Geräteverwendungsbericht ab, um Informationen darüber zu erhalten, auf welchen Geräten Ihre Benutzer Yammer nutzen.
ms.openlocfilehash: fae76e9ef769248217140c059004efc7ad330928
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779386"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Microsoft 365-Berichte im Admin Center – Nutzungsbericht zum Jammern von Geräten

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Die Yammer-Geräteverwendungsberichte geben Ihnen Aufschluss darüber, auf welchen Geräten Ihre Benutzer Yammer nutzen. Sie können die Anzahl der täglichen Benutzer nach Gerätetyp sowie die Anzahl der Benutzer pro Gerätetyp anzeigen. Für beide Berichtsarten können Sie einen bestimmten Zeitraum auswählen. Zudem können Sie auch Details für einzelne Benutzer anzeigen.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.  
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Wie kann ich den Yammer-Geräteverwendungsbericht abrufen?

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf die Schaltfläche **mehr anzeigen** auf der Karte jammern.
  
## <a name="interpret-the-yammer-device-usage-report"></a>Interpretieren des Verwendungsberichts "Jammer Gerät"

Sie können die Verwendung im OneDrive-Bericht anzeigen, indem Sie die Registerkarte **Gerätenutzung** auswählen.<br/>![Microsoft 365 Berichte-Microsoft jammern-Geräte Verwendungsbericht.](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

Wählen Sie **Spalten auswählen** aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.  <br/> ![Verwendungsbericht für jammern von Geräten – Spalten auswählen](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Username  <br/> |Die E-Mail-Adresse des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonymisieren. Dieses Raster zeigt Benutzer an, die sich bei jammern mit dem Microsoft 365-Konto angemeldet haben oder sich mit einmaligem Anmelden am Netzwerk angemeldet haben. <br/> |
|Anzeigename  <br/> |Der vollständige Name des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonymisieren.  <br/> |
|Benutzerstatus  <br/> |Einer von drei Werten: "aktiv", "gelöscht" oder "angehalten". Diese Berichte zeigen Daten für aktive, angehaltene und gelöschte Benutzer. Sie zeigen keine ausstehenden Benutzer, weil ausstehende Benutzer nicht posten, lesen oder eine Nachricht mit "Gefällt mir" bewerten können.   <br/> |
|Datum der Statusänderung (UTC)  <br/> |Das Datum, an dem der Zustand des Benutzers in "jammern" geändert wurde.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum (UTC), an dem der Benutzer an einer Jammer Aktivität teilgenommen hat.  <br/> |
|Netz  <br/> |Gibt an, ob der Benutzer "jammern" im Internet verwendet hat.  <br/> |
|Windows Phone  <br/> | Gibt an, ob der Benutzer "jammern" auf einem Windows Phone verwendet hat.  <br/> |
|Android-Smartphone  <br/> |Gibt an, ob der Benutzer "jammern" auf einem Android-Telefon verwendet hat. <br/>|
|iPhone <br/> | Gibt an, ob der Benutzer "jammern" auf einem iPhone verwendet hat.  <br/> |
|iPad  <br/> |Gibt an, ob der Benutzer "jammern" auf einem iPad verwendet hat. <br/>|
|anderen  <br/> |Gibt an, ob der Benutzer "jammern" auf einem anderen Gerät verwendet hat, das zuvor nicht aufgeführt wurde. <br/>|
|||