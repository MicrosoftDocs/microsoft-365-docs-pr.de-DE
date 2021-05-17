---
title: Microsoft 365 Berichte im Admin Center – Microsoft Teams Geräteverwendung
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
description: Erhalten Sie Einblicke in Microsoft Teams apps, die in Ihrer Organisation verwendet werden, indem Sie den Microsoft Teams-App-Nutzungsbericht aus Microsoft 365 abrufen.
ms.openlocfilehash: 096954ad246f3b10369dfbf683d04b6c81950b5e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579638"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Microsoft 365 Berichte im Admin Center – Microsoft Teams Geräteverwendung

Das Microsoft 365 **-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an. Der Bericht "Microsoft Teams-App-Verwendung" bietet Ihnen Einblicke in die Microsoft Teams-Apps, die in Ihrer Organisation verwendet werden.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams-Kommunikations- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Abrufen des Berichts "Microsoft Teams-App-Verwendung"

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Homepage auf **die** Schaltfläche Weitere Anzeigen auf der Microsoft Teams Aktivitätskarte.
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Interpretieren des Berichts "Microsoft Teams-App-Verwendung"

Sie können die Geräteverwendung im Teams anzeigen, indem Sie die Registerkarte **Geräteverwendung** auswählen.<br/>![Microsoft 365 - Microsoft Teams Geräteverwendung.](../../media/e46c7f7c-8371-4a20-ae82-b20df64b0205.png)

Wählen **Sie Spalten auswählen** aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.  <br/> ![Teams Benutzergerätebericht – Spalten auswählen](../../media/3358d5d9-931b-4d30-931f-450b2f5717da.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 

Im Bericht **Microsoft Teams-Gerätenutzung** werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Benutzername  <br/> |Der Anzeigename des Benutzers.  <br/> |
|Windows  <br/> |Ausgewählt, wenn der Benutzer im Teams auf einem Windows-basierten Computer aktiv war.  <br/> |
|Mac  <br/> |Ausgewählt, wenn der Benutzer im Teams auf einem macOS-Computer aktiv war.  <br/> |
|iOS  <br/> |Ausgewählt, wenn der Benutzer auf dem mobilen Teams für iOS aktiv war.  <br/> |
|Android-Smartphone  <br/> | Ausgewählt, wenn der Benutzer auf dem mobilen Teams für Android aktiv war.  <br/> |
|Chrome OS  <br/> |Ausgewählt, wenn der Benutzer im Teams auf einem ChromeOS-Computer aktiv war.|
|Linux  <br/> | Ausgewählt, wenn der Benutzer im Teams auf einem Linux-Computer aktiv war.  <br/> |
|Netz  <br/> |Ausgewählt, wenn der Benutzer im Teams auf Geräten aktiv war.|
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum (UTC), an dem der Benutzer an einer Teams teilgenommen hat.  <br/> |
|Ist lizenziert|Ausgewählt, wenn der Benutzer für die Verwendung von Teams.|
|||