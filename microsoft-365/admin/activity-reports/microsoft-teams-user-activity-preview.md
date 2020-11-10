---
title: Microsoft 365-Berichte im Admin Center-Microsoft Teams-Benutzeraktivität
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Hier erfahren Sie, wie Sie den Microsoft Teams-Benutzer Aktivitätsbericht abrufen und Einblicke in die Teams-Aktivitäten in Ihrer Organisation erhalten.
ms.openlocfilehash: b85f073a2916b646a5a03e62913de44b410ca058
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988470"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 365-Berichte im Admin Center-Microsoft Teams-Benutzeraktivität

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an. Der Bericht "Microsoft Teams-Benutzeraktivität" bietet Ihnen Einblicke in die Microsoft Teams-Aktivitäten in Ihrer Organisation.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Abrufen des Berichts "Microsoft Teams-Benutzeraktivität"

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.
2. Klicken Sie auf der Dashboard-Startseite auf die Schaltfläche **mehr anzeigen** auf der Microsoft Teams-Aktivitäts Karte.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretieren des Berichts "Microsoft Teams-Benutzeraktivität"

Sie können die Benutzeraktivität im Bericht "Teams" anzeigen, indem Sie die Registerkarte **Benutzeraktivität** auswählen. <br/>![Microsoft 365 Reports-Microsoft Teams-Benutzeraktivität.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Wählen Sie **Spalten auswählen** aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. Das exportierte Format für **Audio-** , **Video** -und **Bildschirmfreigabe Zeit** folgt dem Format der ISO8601-Zeit.

|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Benutzername  <br/> |Die E-Mail-Adresse des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonymisieren.   <br/> |
|Kanal Nachrichten   <br/> |Die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamchat gepostet hat.  <br/> |
|Chat Nachrichten   <br/> |Die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem privaten Chat gepostet hat.  <br/> |
|Besprechungen insgesamt   <br/> |Die Anzahl der Onlinebesprechungen, an denen der Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|1:1 Anrufe   <br/> | Die Anzahl der 1:1 Anrufe, an denen der Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum, an dem der Benutzer an einer Microsoft Teams-Aktivität teilgenommen hat.<br/> |
|Teilnahme an Adhoc-Besprechungen   <br/> | Die Anzahl der Besprechungen, die im Kalender nicht geplant sind, an denen der Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|Organisierte Meetings Adhoc <br/> |Die Anzahl der Besprechungen, die im Kalender nicht geplant sind, die der Benutzer während des angegebenen Zeitraums organisiert hat. <br/>|
|Geplant organisierte Besprechungen  <br/> |Die Anzahl geplanter Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.  <br/> |
|Lizenziert |Ausgewählt, wenn der Benutzer für die Verwendung von Microsoft Teams lizenziert ist.|
|Andere Aktivität|Der Benutzer ist aktiv, hat aber andere Aktivitäten ausgeführt als in dem Bericht angebotene freigegebene Aktionstypen (senden oder beantworten von Kanal-und Chatnachrichten, Planung oder Teilnahme an 1:1-anrufen und Besprechungen). Beispiele für Aktionen sind, wenn ein Benutzer den Status der Teams oder die Teamstatus Meldung ändert oder einen Kanal Nachrichtenbeitrag öffnet, aber nicht antwortet. |
|||