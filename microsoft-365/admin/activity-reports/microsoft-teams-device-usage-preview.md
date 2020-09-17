---
title: Microsoft Teams-Gerätenutzung
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
description: Erhalten Sie Einblicke in die Microsoft Teams-apps, die in Ihrer Organisation verwendet werden, indem Sie den Microsoft Teams-App-Nutzungsbericht aus Microsoft 365-Berichten erhalten.
ms.openlocfilehash: 98b8d6241b94445c9cb47d2c464d47c5609efdfe
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949078"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Microsoft 365-Berichte im Admin Center-Microsoft Teams-Geräteverwendung

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an. Der Bericht "Microsoft Teams-App-Verwendung" bietet Ihnen Einblicke in die Microsoft Teams-Apps, die in Ihrer Organisation verwendet werden.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Abrufen des Berichts "Microsoft Teams-App-Verwendung"

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf die Schaltfläche **mehr anzeigen** auf der Microsoft Teams-Aktivitäts Karte.
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Interpretieren des Berichts "Microsoft Teams-App-Verwendung"

Sie können die Verwendung des Geräts im Bericht "Teams" anzeigen, indem Sie die Registerkarte " **Gerätenutzung** " auswählen.<br/>![Microsoft 365 Reports-Microsoft Teams-Geräteverwendung.](../../media/e46c7f7c-8371-4a20-ae82-b20df64b0205.png)

Wählen Sie **Spalten auswählen** aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.  <br/> ![Teams-Benutzer gerätebericht – auswählen von Spalten](../../media/3358d5d9-931b-4d30-931f-450b2f5717da.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Benutzername  <br/> |Der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Seite Einstellungen des Benutzers im Microsoft Teams Admin Center zu wechseln.  <br/> |
|Windows  <br/> |Ausgewählt, wenn der Benutzer im Microsoft Teams-Desktop Client auf einem Windows-basierten Computer aktiv war.  <br/> |
|Mac  <br/> |Ausgewählt, wenn der Benutzer auf einem macOS-Computer im Microsoft Teams-Desktop Client aktiv war.  <br/> |
|iOS  <br/> |Ausgewählt, wenn der Benutzer auf dem mobilen Microsoft Teams-Client für IOS aktiv war.  <br/> |
|Android-Smartphone  <br/> | Ausgewählt, wenn der Benutzer auf dem mobilen Microsoft Teams-Client für Android aktiv war.  <br/> |
|Chrome OS  <br/> |Ausgewählt, wenn der Benutzer im Microsoft Teams-Desktop Client auf einem Computer mit Chrome aktiv war.|
|Linux  <br/> | Ausgewählt, wenn der Benutzer im Microsoft Teams-Desktop Client auf einem Linux-Computer aktiv war.  <br/> |
|Web  <br/> |Ausgewählt, wenn der Benutzer im Microsoft Teams-WebClient auf Geräten aktiv war.|
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum (UTC), an dem der Benutzer an einer Teams-Aktivität teilgenommen hat.  <br/> |
|Lizenziert|Ausgewählt, wenn der Benutzer für die Verwendung von Microsoft Teams lizenziert ist.|
|||