---
title: Microsoft 365-Berichte im Admin Center-Microsoft Teams-Benutzeraktivität
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 07f67fc4-c0a4-4d3f-ad20-f40c7f6db524
description: Hier erfahren Sie, wie Sie den Microsoft Teams-Benutzer Aktivitätsbericht abrufen und Einblicke in die Teams-Aktivitäten in Ihrer Organisation erhalten.
ms.openlocfilehash: 59fdeec9979b939524279d938e97baf6993d3cb0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387669"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 365-Berichte im Admin Center-Microsoft Teams-Benutzeraktivität

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an. Der Bericht "Microsoft Teams-Benutzeraktivität" bietet Ihnen Einblicke in die Microsoft Teams-Aktivitäten in Ihrer Organisation.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Abrufen des Berichts "Microsoft Teams-Benutzeraktivität"

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.

    
2. Wählen Sie in der Dropdownliste **Bericht auswählen** die Option **Microsoft Teams** - \> **Benutzeraktivität**aus.
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretieren des Berichts "Microsoft Teams-Benutzeraktivität"

Die Microsoft Teams-Benutzeraktivität wird in den Diagrammen **Aktivität** und **Benutzer** grafisch dargestellt.<br/>![Microsoft 365 Reports-Microsoft Teams-Benutzeraktivität.](../../media/40359f81-25f7-416d-bb1e-37289133ef6b.png)
  
|||
|:-----|:-----|
|1.  <br/> |Im Bericht **Microsoft Teams-Benutzeraktivität** werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab.  <br/> |
|3.  <br/> |In der Ansicht **Aktivität** wird die Anzahl der Microsoft Teams-Aktivitäten nach Aktivitätstyp angezeigt. Die Aktivitätstypen sind Anzahl von Teamchatnachrichten, privaten Chatnachrichten, Anrufen oder Besprechungen.  <br/> |
|4.  <br/> |In der Ansicht **Benutzer** wird die Anzahl der Benutzer nach Aktivitätstyp angezeigt. Die Aktivitätstypen sind Anzahl von Teamchatnachrichten, privaten Chatnachrichten, Anrufen oder Besprechungen.  <br/> |
|5.  <br/> | Im Diagramm **Aktivität** stellt die Y-Achse die Anzahl der angegebenen Aktivität dar.  <br/>  Im Diagramm **Dateien** stellt die Y-Achse die Anzahl der Benutzer dar, die an Teamchats, privaten Chats, Anrufen oder Besprechungen teilnehmen.  <br/>  Die X-Achse stellt in den Diagrammen den ausgewählten Datumsbereich für den jeweiligen Bericht dar.  <br/> |
|6.  <br/> |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Wählen Sie beispielsweise im **Aktivitäts** Diagramm **Kanal Nachrichten**, **Chat Nachrichten**, **Anrufe**oder **Besprechungen** aus, um nur die zugehörigen Informationen anzuzeigen. Durch das Ändern dieser Auswahl werden die Informationen in der Gitternetztabelle nicht geändert.  <br/> ![Filtern der Microsoft Teams-Aktivitätsdiagramme](../../media/c819c4ea-6e9a-4411-a0dd-9f800d64ce38.png)|
|7.  <br/> | Die Liste der angezeigten Gruppen wird von der Anzahl aller Gruppen bestimmt, die über den längsten Berichtszeitraum (180 Tage) vorhanden waren (nicht gelöscht wurden). Die Anzahl der Aktivitäten variiert entsprechend der Datumsauswahl.  <br/> HINWEIS: Möglicherweise werden nicht alle Elemente in der nachstehenden Liste in den Spalten angezeigt, solange Sie diese nicht hinzugefügt haben.<br/>**Benutzername** ist die E-Mail-Adresse des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonymisieren.  <br/> **Datum der letzten Aktivität (UTC)** bezieht sich auf das letzte Datum, an dem der Benutzer an einer Microsoft Teams-Aktivität teilgenommen hat.  <br/> **Kanalnachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer in einem Teamchat während des angegebenen Zeitraums gepostet hat.  <br/> **Chatnachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer in einem privaten Chat während des angegebenen Zeitraums gepostet hat.  <br/> **Anrufe** ist die Anzahl der Anrufe, an denen der Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> **Besprechungen** ist die Anzahl der Onlinebesprechungen, an denen der Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> **Andere Aktivität** ist die Anzahl anderer Teamaktivitäten des Benutzers.  <br/> **Gelöscht** gibt an, ob das Team gelöscht wurde. Wenn das Team gelöscht wurde, im Berichtszeitraum jedoch Aktivitäten ausgeführt wurden, wird es im Raster angezeigt, und die Gelöscht-Kennzeichnung ist auf TRUE festgelegt.  <br/> **Gelöscht am** ist das Datum, an dem das Team gelöscht wurde.  <br/> **Zugewiesenes Produkt** bezeichnet die Liste der Produkte, die dem Benutzer zugewiesen sind.  <br/>  Wenn die Richtlinien Ihrer Organisation eine Anzeige von Berichten verhindern, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt zum **Ausblenden von Details auf Benutzerebene** in den [Aktivitätsberichten im Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|8.  <br/> |Wählen Sie **Spalten** aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.  <br/> ![Teams user activity report - choose columns](../../media/eb5fbcee-e371-4d36-a0c6-fa54732311ec.png)|
|9.  <br/> |Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.  <br/> |
|||
   

