---
title: Microsoft 365-Berichte im Admin Center – OneDrive für Unternehmen Aktivität
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
description: Rufen Sie den OneDrive-Verwendungsbericht für Ihre Organisation ab, und kennen Sie die Aktivitäten aller OneDrive-Benutzer, die Anzahl der freigegebenen Dateien und die Speicherauslastung.
ms.openlocfilehash: e83ec835f0aa4a453f14a44d9582edcfd5aa6433
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649814"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365-Berichte im Admin Center – OneDrive für Unternehmen Aktivität

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht zu Berichten](activity-reports.md) an.
  
Sie können z. B. die Aktivität jedes Benutzers verstehen, der für die Verwendung von OneDrive lizenziert ist, indem Sie dessen Interaktion mit Dateien auf OneDrive betrachten. Außerdem hilft es Ihnen, das Ausmaß der Zusammenarbeit zu erkennen, indem Sie die Anzahl der freigegebenen Dateien betrachten.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Wie erhalte ich den OneDrive-Aktivitätsbericht?

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf die Schaltfläche **mehr anzeigen** auf der OneDrive-Karte.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Interpretieren des Aktivitätsberichts für OneDrive for Business

Sie können die Aktivitäten im Bericht OneDrive anzeigen, indem Sie auf die Registerkarte **Aktivität** wählen.<br/>![Microsoft 365 Berichte – Microsoft OneDrive Aktivitätsbericht.](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

Wählen Sie **Spalten auswählen** aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.  <br/> ![OneDrive-Aktivitätsbericht – Spalten auswählen](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Username  <br/> |Der Benutzername des Besitzers des OneDrive-Kontos.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum, an dem eine Dateiaktivität für das OneDrive-Konto für den ausgewählten Datumsbereich ausgeführt wurde. . Um Aktivitäten anzuzeigen, die an einem bestimmten Datum stattfanden, wählen Sie das Datum direkt im Diagramm aus.  <br/> |
|Betrachtete oder bearbeitete Dateien  <br/> |Die Anzahl der Dateien, die der Benutzer hochgeladen, heruntergeladen, geändert oder angezeigt hat.   <br/> |
|Synchronisierte Dateien  <br/> |Die Anzahl der Dateien, die vom lokalen Gerät eines Benutzers mit dem OneDrive-Konto synchronisiert wurden. <br/> |
|Intern freigegebene Dateien  <br/> | Die Anzahl der Dateien, die für Benutzer innerhalb der Organisation freigegeben wurden, oder mit Benutzern in Gruppen (die externe Benutzer enthalten können).  <br/> |
|Extern freigegebene Dateien  <br/> |Die Anzahl der Dateien, die für Benutzer außerhalb der Organisation freigegeben wurden. <br/>|
|Gelöscht  <br/> | Dies deutet darauf hin, dass die Lizenz des Benutzers entfernt wurde.  <br/> Hinweis: Aktivitäten für einen gelöschten Benutzer werden weiterhin in einem Bericht angezeigt, solange er während des ausgewählten Zeitraums zu einem bestimmten Zeitpunkt lizenziert wurde. Der Spalte **Gelöscht** können Sie entnehmen, dass der Benutzer zwar möglicherweise nicht mehr aktiv ist, aber dass der Bericht dennoch ihn betreffende Daten enthält.  <br/> |
|Gelöschtes Datum  <br/> |Das Datum, an dem die Lizenz des Benutzers entfernt wurde. <br/>|
|Produkt zugewiesen  <br/> |Die Microsoft 365-Produkte, die für den Benutzer lizenziert sind.|
|||