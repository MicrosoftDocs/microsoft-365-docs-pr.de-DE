---
title: Microsoft 365-Berichte im Admin Center – OneDrive for Business-Nutzung
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 0de3b312-c4e8-4e4b-a02d-32b2f726a680
description: 'Erfahren Sie im OneDrive for Business-Nutzungsbericht, wie viele Dateien und Speicherplatz in Ihrer Organisation insgesamt verwendet werden. '
ms.openlocfilehash: 1aaae0872863a7983598af009b2ecdffc81a6389
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904528"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365-Berichte im Admin Center – OneDrive for Business-Nutzung

Das Microsoft 365 **Reports-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Die OneDrive Karte auf dem Dashboard bietet beispielsweise einen allgemeinen Überblick über den Wert, den Sie OneDrive for Business hinsichtlich der Anzahl von Dateien und des Ihrer Organisation verwendeten Speichers erhalten. Anschließend können Sie darin einen Drilldown ausführen, um die Trends der aktiven OneDrive Konten, die Anzahl von Dateien, mit denen Benutzer interagieren, sowie den verwendeten Speicher nachzuvollziehen. Außerdem werden Details pro Konto angezeigt OneDrive.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams Communications- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.  
 
## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>Wie erhalte ich den OneDrive-Verwendungsbericht?

1. Wechseln Sie im Admin Center zu Verwendung **von** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Berichten</a>.

    
2. Wählen Sie **in der Dropdownliste** Bericht auswählen die Option **OneDrive-Nutzung** \> **aus.** 
  
## <a name="interpret-the-onedrive-usage-report"></a>Interpretieren des Berichts zur Verwendung von OneDrive

Sie können einen Überblick über die Verwendung von OneDrive for Business erhalten, indem Sie die Ansichten **Konten**, **Dateien** und **Speicher** betrachten. 
  
![OneDrive Usage Report](../../media/49c5b93b-d081-436e-8992-236343a6d46b.png)
  
|Element|Beschreibung|
|:-----|:-----|
|1.  <br/> |Im Bericht **OneDrive-Nutzung** werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab. <br/>|
|3.  <br/> |In der Ansicht **Konten** wird der Trend hinsichtlich der Anzahl von insgesamt und aktiven OneDrive Konten angezeigt. "Aktive Konten" sind alle, in denen die Benutzer Dateien ansehen, ändern, hochladen, runterladen, teilen oder synchronisieren.  <br/> |
|4.  <br/> |In der Ansicht **Dateien** wird die Gesamtzahl der aktiven Dateien angezeigt. Eine Datei wird als aktiv betrachtet, wenn sie innerhalb eines bestimmten Zeitraums gespeichert, synchronisiert, geändert oder freigegeben wurde.  <br/> HINWEIS: Eine Dateiaktivität kann für eine einzelne Datei mehrmals auftreten, zählt jedoch nur als eine aktive Datei. Sie können beispielsweise dieselbe Datei über einen angegebenen Zeitraum mehrmals speichern und synchronisieren, aber sie wird nur als einzelne aktive Datei und als einzelne synchronisierte Datei in den Daten gezählt.           |
|5.  <br/> |In der Ansicht **Speicher** wird der Trend hinsichtlich des in OneDrive verwendeten Speicherplatzes angezeigt. Wenn Sie die Speichergrenzwerte überprüfen möchten, lesen Sie Überprüfen, ob ein Benutzer den Standardspeichergrenzwert oder [einen bestimmten Grenzwert hat.](/onedrive/set-default-storage-space#check-if-a-user-has-the-default-storage-limit-or-a-specific-limit)  <br/> HINWEIS: Die Größe enthält alle Versionen und Metadaten, die den Dateien zugeordnet sind.           |
|6.  <br/> | Im Diagramm **Konten** stellt die Y-Achse die Anzahl der OneDrive Konten dar.  <br/>  Im Diagramm **Dateien** stellt die Y-Achse die Anzahl der gespeicherten Dateien dar OneDrive.  <br/>  Im Diagramm **Speicher** gibt die y-Achse die Menge des OneDrive verwendeten Speicherplatzes an.  <br/>  Die x-Achse in allen Diagrammen entspricht dem ausgewählten Zeitraum für diesen bestimmten Bericht.  <br/> |
|7.  <br/> |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Wählen Sie beispielsweise im **Diagramm Dateien** die Option **Dateien insgesamt** oder Aktive **Dateien aus.** Wählen Sie **im Diagramm Konten** die Option Konten **insgesamt** oder Aktive **Konten aus.** Oder wählen Sie **im Diagramm Speicher** die Option Speicher verwendet **aus.** Wenn Sie Ihre Auswahl ändern, werden die Informationen in der Tabelle nicht geändert.  <br/> |
|8.  <br/> | Die Tabelle zeigt eine Auflistung der Daten für jeden Benutzer OneDrive. Um in der Tabelle zu erscheinen, muss einem Benutzer eine Produktlizenz zugeordnet wurden, die OneDrive enthält, und sie müssen SharePoint Online aktivieren. Der Benutzer muss sich auch entweder im OneDrive Synchronisierungsclient anmelden, oder mithilfe eines Webbrowsers zu seiner OneDrive gehen.  <br/>  Wenn Dateiaktivitäten für das OneDrive stattgefunden haben, weist es das aktuelle Datum auf, an dem die Dateiaktivität ausgeführt wurde. Die Zeilen in der Tabelle sind nach dem Wert **Datum der letzten Aktivität** sortiert, damit die OneDrive mit der letzten Dateiaktivität am Anfange der Liste angezeigt werden.  <br/>  Sie können der Tabelle Spalten hinzufügen oder daraus entfernen.  <br/> ![Spaltenoptionen](../../media/onedriveusage-columns.png)  <br/> **URL** ist die Webadresse für das OneDrive des Benutzers.  <br/> **Gelöscht** ist der Löschstatus des OneDrive. Es dauert mindestens 7 Tage bis Konten als gelöscht gekennzeichnet werden.  <br/> **Besitzer** ist der Benutzername des primären Administrators der OneDrive.  <br/> **Besitzerprinzipalname** ist die E-Mail-Adresse des Besitzers von OneDrive.  <br/> **Datum der letzten Aktivität (UTC)** ist das letzte Datum, an dem eine Dateiaktivität für die OneDrive ausgeführt wurde. Wenn die OneDrive keine Dateiaktivität aufweist, bleibt der Wert leer.  <br/> **Dateien** entspricht der Anzahl von Dateien auf der OneDrive.  <br/> **Aktive Dateien** entspricht der Anzahl der aktiven Dateien für einen Zeitraum.<br/> HINWEIS: Wenn Dateien während des angegebenen Zeitraums für den Bericht entfernt wurden, kann die Anzahl der im Bericht angezeigten aktiven Dateien größer als die aktuelle Anzahl von Dateien in OneDrive sein. Gelöschte Benutzer werden weiterhin 180 Tage lang in Berichten angezeigt.<br/>**Verwendeter Speicherplatz (MB)** entspricht der auf der OneDrive verwendeten Speichermenge in MB. <br/>  Wenn die Richtlinien Ihrer Organisation verhindern, dass Berichte angezeigt werden, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt zum **Ausblenden von Details auf Benutzerebene** in den [Aktivitätsberichten im Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|9.  <br/> |Wählen Sie das **Symbol Spalten verwalten** Spalten verwalten aus, um Spalten aus dem Bericht hinzuzufügen oder zu ![ ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) entfernen.  <br/> |
|10.  <br/> |Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller OneDrive exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2000 OneDrive Konten können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2000 OneDrive Konten müssen Sie die Daten zum Filtern und Sortieren exportieren.  <br/> HINWEIS: Wenn die Daten in eine Excel-Datei exportiert werden, wird das Datum, an dem der Inhaltsbericht generiert wurde, in der Datei in der **Spalte Daten ab Spalte** angezeigt.  <br/> |
|||
