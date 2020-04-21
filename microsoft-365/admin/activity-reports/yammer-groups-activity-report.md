---
title: Microsoft 365-Berichte im Admin Center-Aktivitätsbericht "Jammer Gruppen"
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 94dd92ec-ea73-43c6-b51f-2a11fd78aa31
description: Nutzen Sie den Bericht zur Yammer-Gruppenaktivität, um sich über die Anzahl der Yammer-Gruppen, die in Ihrer Organisation erstellt und verwendet werden, sowie über deren Aktivitäten zu informieren.
ms.openlocfilehash: 0b7dbfe7b578987103c63a9975ea61eb442297e8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43618932"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>Microsoft 365-Berichte im Admin Center-Aktivitätsbericht "Jammer Gruppen"

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an. Über den Yammer-Gruppenaktivitätsbericht erhalten Sie Einblicke in die Aktivitäten der Yammer-Gruppen innerhalb Ihrer Organisation und erfahren, wie viele Yammer-Gruppen erstellt und verwendet wurden.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.  

## <a name="how-to-get-to-the-yammer-groups-activity-report"></a>So gelangen Sie zum Bericht "Yammer-Gruppenaktivität"

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.

    
2. Wählen Sie in der Dropdownliste **Bericht auswählen** den Eintrag **Yammer** \> **Gruppenaktivität** aus.
  
## <a name="interpret-the-yammer-groups-activity-report"></a>Interpretieren des Berichts "Yammer-Gruppenaktivität"

Sie können sich einen Überblick über die Aktivitäten von Yammer-Gruppen verschaffen, indem Sie sich die Diagramme **Gruppen** und **Aktivität** ansehen.<br/>![Diagramm "Yammer-Gruppenaktivität"](../../media/4ba4ea03-2f74-4d86-8c63-2b18477c9769.png)
  
|||
|:-----|:-----|
|1.  <br/> |Im Bericht **Yammer-Gruppenaktivität** werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab. <br/> |
|3.  <br/> |In der Ansicht **Gruppen** wird die Gesamtanzahl der vorhanden Gruppen angezeigt, und Sie können sehen, wie viele an Gruppenunterhaltungen teilgenommen haben.  <br/> |
|4.  <br/> |In der Ansicht **Aktivität** wird die Anzahl der veröffentlichten, gelesenen und mit "Gefällt mir" markierten Yammer-Nachrichten in Gruppen angezeigt.  <br/> |
|5.  <br/> | Im Diagramm **Gruppen** gibt die Y-Achse die Anzahl der gesamten oder aktiven Gruppen an.  <br/>  Im Diagramm **Aktivität** stellt die Y-Achse die Anzahl der angegebenen Aktivität für Yammer-Gruppen dar.  <br/>  Die X-Achse stellt in allen drei Diagrammen den ausgewählten Datumsbereich für den jeweiligen Bericht dar.  <br/> |
|6.  <br/> |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Wählen Sie beispielsweise im Diagramm **Gruppen** die Option **Gesamt** oder **Aktiv**![Gesamtzahl der Gruppen und Anzahl der aktiven Symbole](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png), um nur die jeweils zugehörigen Informationen anzuzeigen. Durch das Ändern dieser Auswahl werden die Informationen in der Gitternetztabelle nicht geändert.  <br/> |
|7.  <br/> | Die Liste der angezeigten Gruppen wird von der Anzahl aller Gruppen bestimmt, die über den längsten Berichtszeitraum (180 Tage) vorhanden waren (nicht gelöscht wurden). Die Anzahl der Aktivitäten (empfangenen Nachrichten) variiert entsprechend der Datumsauswahl.  <br/> HINWEIS: Möglicherweise werden nicht alle Elemente in der nachstehenden Liste in den Spalten angezeigt, solange Sie diese nicht hinzugefügt haben.<br/>**Gruppenname** ist der Name der Gruppe.  <br/> **Gruppenadministrator** ist der Name des Gruppenadministrators oder Besitzers.  <br/> **Gelöscht** ist die Anzahl der gelöschten Yammer-Gruppen. Wenn eine Gruppe gelöscht wird, die im Berichtszeitraum Aktivitäten ausgeführt hat, wird sie im Raster mit dieser auf TRUE festgelegten Kennzeichnung angezeigt.  <br/> **Typ** gibt den Typ der Gruppe zurück (öffentlich oder privat).  <br/> **Verbunden mit Office 365** gibt an, ob es sich bei der Gruppe jammern auch um eine Microsoft 365-Gruppe handelt.  <br/> **Datum der letzten Aktivität** ist das letzte Datum, an dem eine Nachricht von der Gruppe gelesen, veröffentlicht oder mit "Gefällt mir" markiert wurde.  <br/> **Mitglieder** ist die Anzahl der Mitglieder der Gruppe.  <br/> **Veröffentlicht** ist die Anzahl der während des Berichtszeitraums in der Yammer-Gruppe veröffentlichten Nachrichten.  <br/> **Gelesen** ist die Anzahl der während des Berichtszeitraums in der Yammer-Gruppe gelesenen Unterhaltungen.  <br/> **Mit "Gefällt mir" markiert** ist die Anzahl der während des Berichtszeitraums in der Yammer-Gruppe mit "Gefällt mir" markierten Nachrichten.  <br/>  Wenn die Richtlinien Ihrer Organisation eine Anzeige von Berichten verhindern, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt zum **Ausblenden von Details auf Benutzerebene** in [Aktivitätsberichte im Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|8.  <br/> |Wählen Sie **Spalten** aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.  <br/> ![Aktivitäten in Yammer-Gruppen – Spalten auswählen](../../media/31bd549b-363d-4888-a45d-7af6fedb3588.png)|
|9.  <br/> |Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.  <br/> |
|||
   

