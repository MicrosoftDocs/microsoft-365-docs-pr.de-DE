---
title: Microsoft 365-Berichte im Admin Center – Dynamics 365-VoIP-Aktivität für Kunden
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
description: In diesem Artikel erfahren Sie, wie Sie einen Microsoft Dynamics 365-Bericht zur Kunden Sprachaktivität mithilfe des Microsoft 365-Berichts Dashboards im Microsoft 365 Admin Center erhalten.
ms.openlocfilehash: 0a854c7a89977a96e11d8ec28fd7789e8418c1cf
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988925"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Microsoft 365-Berichte im Admin Center – Dynamics 365-VoIP-Aktivität für Kunden

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht zu Berichten](activity-reports.md) an.
  
Sie können beispielsweise die Aktivität jedes Benutzers verstehen, der Microsoft Dynamics 365-Kunden VoIP verwendet, indem Sie sich ihre Interaktionen mit Dynamics 365 Kundenstimme ansehen. Außerdem können Sie die Ebene der Zusammenarbeit verstehen, indem Sie die Anzahl der erstellten pro-Umfragen und pro-Umfragen betrachten, auf die die Benutzer geantwortet haben. 
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.  
 
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>So gelangen Sie zum Bericht "Dynamics 365 Customer Voice Activity"

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf die Schaltfläche **mehr anzeigen** auf der Dynamics 365-Kunden-VoIP-Karte.
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Interpretieren des Berichts "Dynamics 365-Kunden VoIP-Aktivität"

Sie können die Aktivitäten im Dynamics 365-Kunden sprach Bericht anzeigen, indem Sie auf die Registerkarte **Aktivität** wählen.<br/>![Microsoft 365-Berichte – Microsoft Dynamics 365-Bericht zur Sprachaktivität für Kunden.](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

Wählen Sie **Spalten auswählen** aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.  <br/> ![Dynamics 365-Berichts zur Kunden Sprachaktivität – auswählen von Spalten](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Username  <br/> |Die e-Mail-Adresse des Benutzers, der die Aktivität in Microsoft Forms ausgeführt hat.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum, an dem eine Formular Aktivität vom Benutzer für den ausgewählten Datumsbereich ausgeführt wurde. Um Aktivitäten anzuzeigen, die an einem bestimmten Datum stattfanden, wählen Sie das Datum direkt im Diagramm aus.<br/>Dadurch wird die Tabelle so gefiltert, dass Datei Aktivitätsdaten nur für Benutzer angezeigt werden, die die Aktivität an diesem bestimmten Tag ausgeführt haben.  <br/> |
|Anzahl der erstellten Umfragen  <br/> |Die Anzahl der vom Benutzer erstellten Umfragen.   <br/> |
|Anzahl der Umfrage Antworten  <br/> |Die Anzahl der Antworten von Respondern, an die die Umfrage verteilt wurde.|
|||