---
title: Microsoft 365-Berichte im Admin Center – Microsoft Teams-Benutzeraktivität
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
description: Erfahren Sie, wie Sie den Microsoft Teams-Benutzeraktivitätsbericht erhalten und Einblicke in die Microsoft Teams-Aktivitäten in Ihrer Organisation erhalten.
ms.openlocfilehash: e8e4ab6fd78fb290243d8fdc780b5a7a14ca2ee0
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233410"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 365-Berichte im Admin Center – Microsoft Teams-Benutzeraktivität

Das Microsoft 365-Dashboard "Berichte" zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten In Ihrer Organisation.  Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an. Der Bericht "Microsoft Teams-Benutzeraktivität" bietet Ihnen Einblicke in die Microsoft Teams-Aktivitäten in Ihrer Organisation.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams Communications- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Abrufen des Berichts "Microsoft Teams-Benutzeraktivität"

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.
2. Klicken Sie auf der Startseite des Dashboards auf die **Schaltfläche** "Weitere Anzeigen" auf der Microsoft Teams-Aktivitätskarte.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretieren des Berichts "Microsoft Teams-Benutzeraktivität"

Sie können die Benutzeraktivität im Bericht "Teams" anzeigen, indem Sie die Registerkarte **"Benutzeraktivität"** auswählen. <br/>![Microsoft 365-Berichte – Microsoft Teams-Benutzeraktivität.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Wählen **Sie Spalten zum** Hinzufügen oder Entfernen von Spalten aus dem Bericht aus.  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. Das exportierte Format für **Audiozeit,**  **Videozeit** und Bildschirmfreigabezeit folgt dem ISO8601-Dauerformat.

Im Bericht **Microsoft Teams-Benutzeraktivität** werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).

Um die Datenqualität sicherzustellen, führen wir tägliche Datenüberprüfungen für die letzten drei Tage durch und füllen alle erkannten Lücken. Möglicherweise sind während des Prozesses Unterschiede bei verlaufshistorischen Daten zu erkennen.

|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Benutzername  <br/> |Die E-Mail-Adresse des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonymisieren.   <br/> |
|Kanalnachrichten   <br/> |Die Anzahl der eindeutigen Nachrichten, die der Benutzer im angegebenen Zeitraum in einem Teamchat gepostet hat.  <br/> |
|Chatnachrichten   <br/> |Die Anzahl der eindeutigen Nachrichten, die der Benutzer im angegebenen Zeitraum in einem privaten Chat gepostet hat.  <br/> |
|Besprechungen insgesamt   <br/> |Die Anzahl der Onlinebesprechungen, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|1:1-Anrufe   <br/> | Die Anzahl der 1:1-Anrufe, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum, an dem der Benutzer an einer Microsoft Teams-Aktivität teilgenommen hat.<br/> |
|Besprechungen haben adhoc teilgenommen   <br/> | Die Anzahl der Besprechungen, die nicht im Kalender geplant sind, an dem der Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|Besprechungen, die adhoc organisiert wurden <br/> |Die Anzahl der Besprechungen, die nicht im Kalender geplant sind, die der Benutzer während des angegebenen Zeitraums organisiert hat. <br/>|
|Geplante Besprechungen  <br/> |Die Anzahl der geplanten Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.  <br/> |
|Ist lizenziert |Ausgewählt, wenn der Benutzer für die Verwendung von Teams lizenziert ist.|
|Andere Aktivitäten|Der Benutzer ist aktiv, hat jedoch andere Aktivitäten als im Bericht angebotene aktionstypen verfügbar gemacht (Senden oder Beantworten von Kanalnachrichten und Chatnachrichten, Planen oder Teilnehmen an 1:1-Anrufen und Besprechungen). Beispiele für Aktionen sind, wenn ein Benutzer den Status von Teams oder die Statusmeldung von Teams ändert oder einen Kanalnachrichtenbeitrag öffnet, aber nicht antwortet. |
|||