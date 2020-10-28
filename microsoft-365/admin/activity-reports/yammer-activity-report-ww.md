---
title: Microsoft 365-Berichte im Admin Center – jammern-Aktivitätsbericht
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
description: Rufen Sie den Yammer-Aktivitätsbericht ab. Dieser stellt Ihnen Informationen über die Anzahl der Benutzer bereit, die Yammer verwenden, um eine Nachricht zu posten, mit "Gefällt mir" zu kennzeichnen oder zu lesen.
ms.openlocfilehash: fc6bf252892cc9b3f30cdcf464cd44cfc83c4f75
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779376"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>Microsoft 365-Berichte im Admin Center – jammern-Aktivitätsbericht

Das Dashboard **Berichte** zeigt Ihnen als Microsoft 365-Administrator Ihre Daten im Hinblick auf die Nutzung der Produkte innerhalb Ihrer Organisation an. Schauen Sie sich [Aktivitätsberichte im Admin Center](activity-reports.md) an. Mit dem **Yammer-Aktivitätsbericht** können Sie den Grad des Engagements Ihrer Organisation mit Yammer erkennen. Dazu schauen Sie sich die Anzahl eindeutiger Benutzer, die über Yammer eine Nachricht posten, lesen oder mit "Gefällt mir" bewerten, und den Umfang der Aktivitäten an, die organisationsweit generiert wurden. 
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.  
 
## <a name="how-do-i-get-to-the-yammer-activity-report"></a>Wie komme ich zum jammern-Aktivitätsbericht?

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf die Schaltfläche **mehr anzeigen** auf der Karte jammern.

  
## <a name="interpret-the-yammer-activity-report"></a>Interpretieren des Yammer-Aktivitätsberichts

Sie können die Aktivitäten im Bericht "jammern" anzeigen, indem Sie auf die Registerkarte **Aktivität** wählen.<br/>![Microsoft 365 Reports-Microsoft jammern-Aktivitätsbericht.](../../media/9b251183-c2b3-430c-ab2d-58bf11e7e3ae.png)

Wählen Sie **Spalten auswählen** aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.  <br/> ![Jammern-Aktivitätsbericht – Spalten auswählen](../../media/7ef6351d-f7e9-4504-913d-2c2df9062bf6.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Username  <br/> |Die E-Mail-Adresse des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonymisieren. Dieses Raster zeigt Benutzer an, die sich bei jammern mit dem Microsoft 365-Konto angemeldet haben oder sich mit einmaligem Anmelden am Netzwerk angemeldet haben. <br/> |
|Anzeigename  <br/> |Der vollständige Name des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonymisieren.  <br/> |
|Benutzerstatus  <br/> |Einer von drei Werten: aktiviert, gelöscht oder angehalten. Diese Berichte zeigen Daten für aktive, angehaltene und gelöschte Benutzer. Sie zeigen keine ausstehenden Benutzer, weil ausstehende Benutzer nicht posten, lesen oder eine Nachricht mit "Gefällt mir" bewerten können.  <br/> |
|Datum der Statusänderung (UTC)  <br/> |Das Datum, an dem der Zustand des Benutzers in "jammern" geändert wurde.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> | Das letzte Datum, an dem der Benutzer eine Nachricht gepostet, gelesen oder gemocht hat.  <br/> |
|Gepostet  <br/> |Die Anzahl der Nachrichten, die der Benutzer während des angegebenen Zeitraums gepostet hat. <br/>|
|Lesen  <br/> |Die Anzahl der Unterhaltungen, die der Benutzer während des angegebenen Zeitraums gelesen hat.  <br/> |
|Gelikt  <br/> |Die Anzahl der Nachrichten, die der Benutzer während des angegebenen Zeitraums gewünscht hat.  <br/>|
|Produkt zugewiesen  <br/> |Die Produkte, die diesem Benutzer zugewiesen sind.|
|||