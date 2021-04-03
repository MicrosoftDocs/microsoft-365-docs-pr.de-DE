---
title: Microsoft Teams-Gerätenutzung
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 917b3e1d-203e-4439-8539-634e80196687
description: Erhalten Sie Einblicke in die in Ihrer Organisation verwendeten Microsoft Teams-Apps, indem Sie den Microsoft Teams-App-Nutzungsbericht aus Microsoft 365-Berichten abrufen.
ms.openlocfilehash: 453b5767a6da1361ba8121fa2d49d9db8224aa68
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579626"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Microsoft 365-Berichte im Admin Center – Geräteverwendung von Microsoft Teams

Das Microsoft 365 **Reports-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an. Der Bericht "Microsoft Teams-App-Verwendung" bietet Ihnen Einblicke in die Microsoft Teams-Apps, die in Ihrer Organisation verwendet werden.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams Communications- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Abrufen des Berichts "Microsoft Teams-App-Verwendung"

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.

    
2. Wählen Sie **in der Dropdownliste** Bericht auswählen die **Option Microsoft Teams** Device usage \> **aus.**
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Interpretieren des Berichts "Microsoft Teams-App-Verwendung"

Die Microsoft Teams-App-Verwendung wird in den Diagrammen **Benutzer** und **Verteilung** grafisch dargestellt. 
  
![Microsoft 365-Berichte – Microsoft Teams-App-Verwendung](../../media/de35c4de-76b4-4109-a806-66774665499b.png)
  
|Element|Beschreibung|
|:-----|:-----|
|1.  <br/> |Im Bericht **Microsoft Teams-Gerätenutzung** werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab.  <br/> |
|3.  <br/> |In der Ansicht **Benutzer** wird die tägliche Anzahl der eindeutigen Benutzer nach App angezeigt.  <br/> |
|4.  <br/> |In der Ansicht **Verteilung** wird die Anzahl der eindeutigen Benutzer im ausgewählten Zeitraum nach App angezeigt.  <br/> |
|5.  <br/> | Im Diagramm **Benutzer** stellt die Y-Achse die Anzahl der Benutzer pro App dar.  <br/>  Im Diagramm **Verteilung** stellt die Y-Achse die Anzahl der Benutzer der angegebenen App dar.  <br/>  Die X-Achse stellt in den Diagrammen den ausgewählten Datumsbereich für den jeweiligen Bericht dar.  <br/> |
|6.  <br/> |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Wählen Sie im  Diagramm Benutzer beispielsweise **Windows,** **Mac,** **Anrufe,** **Web,** **Android-Telefon** oder **Windows-Telefon** aus, um nur die Informationen zu den einzelnen Telefonen zu sehen. Durch das Ändern dieser Auswahl werden die Informationen in der Gitternetztabelle nicht geändert.  <br/> ![Sie können Microsoft Teams-App-Verwendungsdiagramme filtern, indem Sie den App-Typ auswählen.](../../media/64ee1cb1-ca80-4964-8234-7fc671135c3d.png)|
|7.  <br/> | Die Liste der angezeigten Gruppen wird von der Anzahl aller Gruppen bestimmt, die über den längsten Berichtszeitraum (180 Tage) vorhanden waren (nicht gelöscht wurden). Die Anzahl der Aktivitäten variiert entsprechend der Datumsauswahl.  <br/> HINWEIS: Möglicherweise werden nicht alle Elemente in der nachstehenden Liste in den Spalten angezeigt, solange Sie diese nicht hinzugefügt haben.<br/> **Benutzername** ist die E-Mail-Adresse des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonymisieren.  <br/> **Datum der letzten Aktivität (UTC)** bezieht sich auf das letzte Datum, an dem der Benutzer an einer Microsoft Teams-Aktivität in einer App teilgenommen hat.  <br/> **Gelöscht** gibt an, ob das Team gelöscht wurde. Wenn das Team gelöscht wurde, im Berichtszeitraum jedoch Aktivitäten ausgeführt wurden, wird es im Raster angezeigt, und die Gelöscht-Kennzeichnung ist auf TRUE festgelegt.  <br/> **Gelöscht am** ist das Datum, an dem das Team gelöscht wurde.  <br/> **Windows** ist ausgewählt, wenn der Benutzer während des angegebenen Zeitraums in der Windows-App aktiv war.  <br/> **Mac** ist ausgewählt, wenn der Benutzer während des angegebenen Zeitraums in einer Mac-App aktiv war.  <br/> **Web** ist ausgewählt, wenn der Benutzer während des angegebenen Zeitraums in einer Web-App aktiv war.  <br/> **iOS** ist ausgewählt, wenn der Benutzer während des angegebenen Zeitraums in einer iOS-App aktiv war.  <br/> **Android-Smartphone** ist ausgewählt, wenn der Benutzer während des angegebenen Zeitraums an einem Android-Smartphone aktiv war.  <br/> **Windows Phone** ist ausgewählt, wenn der Benutzer während des angegebenen Zeitraums an einem Windows Phone aktiv war.  <br/>  Wenn die Richtlinien Ihrer Organisation eine Anzeige von Berichten verhindern, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt zum **Ausblenden von Details auf Benutzerebene** in den [Aktivitätsberichten im Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|8.  <br/> |Wählen Sie **Spalten** aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.  <br/> ![Teams uapp usage report - choose columns](../../media/333f3077-696d-4829-b0a7-1046b3822222.png)|
|9.  <br/> |Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.  <br/> |
|||
   
  

