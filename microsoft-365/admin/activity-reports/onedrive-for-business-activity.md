---
title: Microsoft 365-Berichte im Admin Center – OneDrive für Unternehmen Aktivität
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 8bbe4bf8-221b-46d6-99a5-2fb3c8ef9353
description: Rufen Sie den OneDrive-Verwendungsbericht für Ihre Organisation ab, und kennen Sie die Aktivitäten aller OneDrive-Benutzer, die Anzahl der freigegebenen Dateien und die Speicherauslastung.
ms.openlocfilehash: 2c755a9a5cf2f2085ec02029387a884f38aecb53
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241814"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365-Berichte im Admin Center – OneDrive für Unternehmen Aktivität

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht zu Berichten](activity-reports.md) an.
  
Sie können z. B. die Aktivität jedes Benutzers verstehen, der für die Verwendung von OneDrive lizenziert ist, indem Sie dessen Interaktion mit Dateien auf OneDrive betrachten. Außerdem hilft es Ihnen, das Ausmaß der Zusammenarbeit zu erkennen, indem Sie die Anzahl der freigegebenen Dateien betrachten.
  
> [!NOTE]
> Einige Funktionen werden schrittweise eingeführt. Das bedeutet, dass diese Funktion möglicherweise noch nicht angezeigt wird oder anders aussieht, als in den Hilfeartikeln beschrieben. Doch machen Sie sich keine Sorgen - sie ist in Kürze verfügbar! 
  
Wenn Sie den Umfang der Aktivität für die einzelnen OneDrive-Konten und die Speichernutzung erfahren möchten , können Sie den [Bericht zur OneDrive-Verwendung](onedrive-for-business-usage.md) anzeigen.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein berichtsleser in Microsoft 365 oder ein Exchange-, SharePoint-oder Skype for Business-Administrator sein, um Berichte anzuzeigen. 
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Wie erhalte ich den OneDrive-Aktivitätsbericht?

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.

    
2. Wählen Sie in der Dropdownliste **Bericht auswählen** die Option **OneDrive** \> - **Aktivität**aus.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Interpretieren des Aktivitätsberichts für OneDrive for Business

Sie können einen Einblick in die OneDrive for Business-Aktivität erhalten, indem Sie die Ansichten **Dateien** und **Benutzer** betrachten. 
  
![OneDrive Activity Report](../media/316b2a03-8e42-447c-aae8-080813eebe84.png)
  
|||
|:-----|:-----|
|1.  <br/> |Im Bericht **OneDrive for Business-Aktivität** werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab. <br/>|
|3.  <br/> |Anhand der Ansicht **Dateien** können Sie die eindeutige Anzahl an lizenzierten Benutzern erkennen, die Dateiinteraktionen für beliebige OneDrive-Konten ausgeführt haben.  <br/> |
|4.  <br/> |Anhand der Ansicht **Benutzer** können Sie den Trend in Hinsicht auf die Anzahl der aktiven OneDrive-Benutzer erkennen. Ein Benutzer wird als "aktiv" betrachtet, wenn er eine Dateiaktivität (Speichern, Synchronisieren, Ändern oder Freigeben) innerhalb des angegebenen Zeitraums ausgeführt hat.  <br/> Hinweis: eine Dateiaktivität kann mehrere Male für eine einzelne Datei auftreten, wird aber nur als eine aktive Datei gezählt. Sie können die gleiche Datei beispielsweise in einem bestimmten Zeitraum mehrmals speichern und synchronisieren, aber Sie wird nur als eine einzelne aktive Datei und eine einzelne synchronisierte Datei in den Daten gezählt.           |
|5.  <br/> | Im Diagramm **Dateien** stellt die Y-Achse die Anzahl der eindeutigen Dateien dar, die ein beliebiger Benutzer gespeichert, synchronisiert, geändert oder freigegeben hat.  <br/>  Im Diagramm **Benutzer** stellt die Y-Achse die Anzahl der eindeutigen Benutzer dar, die Dateiinteraktionen (Speichern, Synchronisieren, Ändern oder Freigeben) für ein beliebiges OneDrive-Konto ausgeführt haben.  <br/>  Die x-Achse in allen Diagrammen entspricht dem ausgewählten Zeitraum für diesen bestimmten Bericht.  <br/> |
|6.  <br/> |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Wählen Sie beispielsweise im Diagramm **Dateien** die Option **angezeigt oder bearbeitet** oder **synchronisiert** aus, um nur die zugehörigen Informationen anzuzeigen. Durch das Ändern dieser Auswahl werden die Informationen in der Gitternetztabelle nicht geändert.  <br/> |
|7.  <br/> | Die Tabelle zeigt eine Auflistung der Daten nach Benutzerebene. Sie können Spalten zur Tabelle hinzufügen oder aus der Tabelle entfernen.   <br/>  **Username** ist der Benutzername des Besitzers des OneDrive-Kontos.  <br/> **Datum der letzten Aktivität (UTC)** ist das letzte Datum, an dem eine Dateiaktivität für das OneDrive-Konto für den ausgewählten Datumsbereich ausgeführt wurde. Um Aktivitäten anzuzeigen, die an einem bestimmten Datum stattfanden, wählen Sie das Datum direkt im Diagramm aus.  <br/> ![Auswählen eines bestimmten Datums im Diagramm](../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png)  <br/>  Dadurch wird die Tabelle so gefiltert, dass Datei Aktivitätsdaten nur für Benutzer angezeigt werden, die die Aktivität an diesem bestimmten Tag ausgeführt haben.  <br/> **Angezeigte oder bearbeitete Dateien** gibt die Anzahl der Dateien an, die der Benutzer hochgeladen, heruntergeladen, geändert oder angezeigt hat.  <br/> **Synchronisierte Dateien** gibt die Anzahl der Dateien an, die vom lokalen Gerät eines Benutzers mit dem OneDrive-Konto synchronisiert wurden.  <br/> **Intern freigegebene Dateien** ist die Anzahl der Dateien, die für Benutzer innerhalb der Organisation freigegeben wurden, oder mit Benutzern innerhalb von Gruppen (die externe Benutzer enthalten können).  <br/> **Extern freigegebene Dateien** gibt die Anzahl der Dateien an, die für Benutzer außerhalb der Organisation freigegeben wurden.  <br/> **Gelöscht** gibt an, dass die Lizenz des Benutzers entfernt wurde.  <br/> Hinweis: Aktivitäten für einen gelöschten Benutzer werden weiterhin in einem Bericht angezeigt, solange er während des ausgewählten Zeitraums zu einem bestimmten Zeitpunkt lizenziert wurde. Der Spalte **Gelöscht** können Sie entnehmen, dass der Benutzer zwar möglicherweise nicht mehr aktiv ist, aber dass der Bericht dennoch ihn betreffende Daten enthält.<br/>**Gelöscht am** ist das Datum, an dem die Lizenz des Benutzers entfernt wurde.  <br/> **Produkt zugewiesen** sind die Microsoft 365-Produkte, die für den Benutzer lizenziert sind.  <br/>  Wenn die Richtlinien Ihrer Organisation das Anzeigen von Berichten verhindern, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt zum **Ausblenden von Details auf Benutzerebene** in den [Aktivitätsberichten im Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|8.  <br/> |Wählen ![Sie **das Symbol Spalten verwalten** aus](../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) , um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.  <br/> |
|9.  <br/> |Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.  <br/> |
|||
   

