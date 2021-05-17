---
title: Microsoft 365 Berichte im Admin Center – Microsoft Teams Benutzeraktivität
ms.author: kwekua
author: kwekua
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
description: Erfahren Sie, wie Sie Microsoft Teams Benutzeraktivitätsbericht erhalten und Einblicke in Teams Aktivitäten in Ihrer Organisation erhalten.
ms.openlocfilehash: a4f8cd995d1559da3846fbb38cc5a9441358da72
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579614"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 365 Berichte im Admin Center – Microsoft Teams Benutzeraktivität

Das Microsoft 365 **-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an. Der Bericht "Microsoft Teams-Benutzeraktivität" bietet Ihnen Einblicke in die Microsoft Teams-Aktivitäten in Ihrer Organisation.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams-Kommunikations- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Abrufen des Berichts "Microsoft Teams-Benutzeraktivität"

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.
2. Klicken Sie auf der Dashboard-Homepage auf **die** Schaltfläche Weitere Anzeigen auf der Microsoft Teams Aktivitätskarte.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretieren des Berichts "Microsoft Teams-Benutzeraktivität"

Sie können die Benutzeraktivität im Teams anzeigen, indem Sie die Registerkarte **Benutzeraktivität** auswählen. <br/>![Microsoft 365 Berichte – Microsoft Teams Benutzeraktivität.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Wählen **Sie Spalten auswählen** aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.  <br/> ![Teams user activity report - choose columns](../../media/6d3c013e-2c5e-4d66-bb41-998aa4bd1c20.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. Das exportierte Format für **Audiozeit,** **Videozeit** und **Bildschirmfreigabezeit** folgt dem ISO8601-Dauerformat.

Im Bericht **Microsoft Teams-Benutzeraktivität** werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).

Um die Datenqualität sicherzustellen, führen wir tägliche Datenüberprüfungen für die letzten drei Tage durch und füllen alle erkannten Lücken. Während des Prozesses können Unterschiede in verlaufshistorischen Daten festgestellt werden.

|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Benutzername  <br/> |Die E-Mail-Adresse des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonymisieren.   <br/> |
|Kanalnachrichten   <br/> |Die Anzahl eindeutiger Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamchat gepostet hat.  <br/> |
|Chat-Nachrichten   <br/> |Die Anzahl eindeutiger Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem privaten Chat gepostet hat.  <br/> |
|Besprechungen insgesamt   <br/> |Die Anzahl der Onlinebesprechungen, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|1:1-Anrufe   <br/> | Die Anzahl der 1:1-Anrufe, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum, an dem der Benutzer an einer Microsoft Teams teilgenommen hat.<br/> |
|Ad-hoc-Besprechungen   <br/> | Die Anzahl der Ad-hoc-Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|Ad-hoc-Organisierte Besprechungen <br/> |Die Anzahl der Ad-hoc-Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat. <br/>|
|Insgesamt organisierte Besprechungen  <br/> |Die Summe der einmal geplanten, wiederkehrenden, ad hoc- und nicht klassifizierten Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.  <br/> |
|Insgesamt teilgenommene Besprechungen  <br/> |Die Summe der einmal geplanten, wiederkehrenden, ad hoc und nicht klassifizierten Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|Einmal geplante Besprechungen  <br/> |Die Anzahl der einmal geplanten Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.  <br/> |
|Besprechungen mit geplanten Terminserien  <br/> |Die Anzahl wiederkehrender Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.  <br/> |
|Besprechungen wurden einmal geplant  <br/> |Die Anzahl der einmal geplanten Besprechungen, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|Besprechungen teilnahmen an geplanten Terminserien  <br/> |Die Anzahl der besprechungsserien, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|Ist lizenziert  <br/> |Ausgewählt, wenn der Benutzer für die Verwendung von Teams. <br/>|
|Andere Aktivitäten  <br/>|Der Benutzer ist aktiv, hat aber andere Aktivitäten ausgeführt als im Bericht angebotene offengelegte Aktionstypen (Senden oder Antworten auf Kanalnachrichten und Chatnachrichten, Planen oder Teilnehmen an 1:1-Anrufen und Besprechungen). Beispielaktionen sind, wenn ein Benutzer den Status Teams status oder Teams oder einen Kanalnachrichtenbeitrag öffnet, aber nicht antwortet.  <br/>|
|Nicht klassifizierte Besprechungen <br/>|Die, die nicht als Zeitplan oder Terminserie oder ad hoc klassifiziert werden kann. Diese sind kurz und können aufgrund manipulierter Telemetrieinformationen meist nicht identifiziert werden. |
|||