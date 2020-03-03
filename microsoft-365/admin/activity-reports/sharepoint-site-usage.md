---
title: Microsoft 365-Berichte im Admin Center – Verwendung von SharePoint-Websites
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
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
- GEA150
- SPO160
- BSA160
ms.assetid: 4ecfb843-e5d5-464d-8bf6-7ed512a9b213
description: 'Rufen Sie den Bericht über die SharePoint-Websitenutzung ab, um zu erfahren, wie viele Dateien Benutzer in SharePoint-Websites speichern, wie viele aktiv verwendet werden und wie viel Speicher insgesamt verbraucht wird. '
ms.openlocfilehash: c60d33ce299d63edafc4ce996bb4ba07ce9b7fa0
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353466"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365-Berichte im Admin Center – Verwendung von SharePoint-Websites

Als Microsoft 365-Administrator zeigt das Dashboard **Berichte** die Aktivitätsübersicht für verschiedene Produkte in Ihrer Organisation an. Hiermit können Sie einen Drilldown ausführen, um genauere Einblicke in die Aktivitäten für die einzelnen Produkte zu erhalten. Sie können beispielsweise eine allgemeine Übersicht über den Wert erhalten, den Sie von SharePoint erhalten, in Bezug auf die Gesamtzahl der Dateien, die Benutzer in SharePoint-Websites speichern, die Anzahl der aktiven Dateien und den Speicherplatz, der für alle diese Websites genutzt wird. Anschließend können Sie einen Drilldown zum SharePoint-Websiteverwendungsbericht durchführen, um die Trends und Details auf Websiteebene für alle Websites zu verstehen. 
  
> Hinweis: Sie müssen ein globaler Administrator, ein globaler Leser oder ein berichtsleser in Microsoft 365 oder ein Exchange-, SharePoint-oder Skype for Business-Administrator sein, um Berichte anzuzeigen. 
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Wie erhalten Sie einen Bericht zur Verwendung von SharePoint-Websites

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.

    
2. Wählen Sie in der Dropdownliste **Bericht auswählen** die Option **SharePoint** \> - **Websitenutzung**aus.
  
## <a name="interpreting-the-sharepoint-site-usage-report"></a>Interpretieren des Berichts zur Verwendung von SharePoint-Websites

![SharePoint Site Usage Report](../../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|||
|:-----|:-----|
|1.  <br/> |Im Bericht zur **SharePoint-Nutzung** werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab. <br/> |
|3.  <br/> |Das Diagramm **Websites** zeigt die Anzahl der gesamten und aktiven Websites an. Eine beliebige Website, in der Benutzer innerhalb des Berichtszeitraums Daten angezeigt, geändert, hochgeladen, heruntergeladen, freigegeben oder synchronisiert bzw. eine Seite angezeigt haben.  <br/> |
|4.  <br/> |Im Diagramm **Dateien** werden die Gesamtanzahl der Dateien auf allen Websites und die Anzahl der aktiven Dateien angezeigt. Die Anzahl aller Dateien umfasst sowohl Benutzerdateien als auch Systemdateien. Eine Datei wird als aktiv betrachtet, wenn sie gespeichert, synchronisiert, geändert oder innerhalb eines bestimmten Zeitraums freigegeben wurde.  <br/> Hinweis: eine Dateiaktivität kann mehrere Male für eine einzelne Datei auftreten, wird aber nur als eine aktive Datei gezählt. Sie können beispielsweise dieselbe Datei über einen angegebenen Zeitraum mehrmals speichern und synchronisieren, aber sie wird nur als einzelne aktive Datei und als einzelne synchronisierte Datei in den Daten gezählt.           |
|5.  <br/> |Das Diagramm **Speicher** zeigt den Trend hinsichtlich des im Berichtszeitraum belegten Speicherplatzes an.  <br/> |
|6.  <br/> |Im Diagramm **Seiten** wird die Anzahl der in allen Websites aufgerufenen Seiten angezeigt.  <br/> |
|7.  <br/> |Sie können Diagramme, die angezeigt werden, Filtern, indem Sie ein Element in der Legende auswählen. Wählen Sie beispielsweise im Diagramm **Dateien** die Option **Dateien** oder **aktive Dateien**aus. Im Diagramm **Websites** können Sie **Gesamt Websites** oder **aktive Standorte**auswählen. Im **Speicher** Diagramm können Sie die **Speicherzuordnung** oder den **Speicherverbrauch auswählen.** Durch das Ändern dieser Auswahl werden die Informationen in der Gitternetztabelle nicht geändert.  <br/> |
|8.  <br/> | Die Tabelle zeigt eine Aufschlüsselung der Aktivitäten auf Ebene der einzelnen Websites.  <br/> ![Spaltenoptionen für Verwendungsbericht](../../media/sharepointsite-usage.png)           <br/> **Website-URL** ist die vollständige URL der Website.  <br/> **Gelöscht** ist der Löschstatus der Website. Es dauert mindestens sieben Tage, bis Websites als gelöscht markiert werden.  <br/> **Websitebesitzer** ist der Benutzername des primären Besitzers der Website.  <br/>Der **Prinzipalname des Websitebesitzers** ist die e-Mail-Adresse des Besitzers der Website.  <br/> **Datum der letzten Aktivität (UTC)** bezieht sich auf das Datum, wann die letzte Dateiaktivität erkannt bzw. wann eine Seite auf der Website angezeigt wurde.      <br/> **Dateien** entspricht der Anzahl von Dateien auf der Website.  <br/> **Aktive Dateien** ist die Anzahl der aktiven Dateien auf der Website. Eine Datei wird als aktiv betrachtet, wenn sie gespeichert, synchronisiert, geändert oder innerhalb eines bestimmten Zeitraums freigegeben wurde.  <br/> Hinweis: eine Dateiaktivität kann mehrere Male für eine einzelne Datei auftreten, wird aber nur als eine aktive Datei gezählt. Sie können beispielsweise dieselbe Datei über einen angegebenen Zeitraum mehrmals speichern und synchronisieren, aber sie wird nur als einzelne aktive Datei und als einzelne synchronisierte Datei in den Daten gezählt. >  Wenn während des angegebenen Zeitraums für den Bericht Dateien entfernt wurden, ist die Anzahl der aktiven Dateien, die im Bericht angegeben ist, möglicherweise größer als die aktuelle Anzahl der Dateien auf der Website.<br/>**Verwendeter Speicherplatz (MB)** entspricht der auf der Website aktuell verwendeten Speichermenge.  <br/> **Zugeordneter Speicher (MB)** entspricht dem maximalen Speicherplatz, der der Website zugeordnet ist.  <br/> **Seitenansichten** gibt an, wie oft Seiten auf der Website angezeigt wurden.  <br/> **Besuchte Seiten** gibt an, wie viele verschiedene Seiten auf der Website aufgerufen wurden.  <br/> **Stammwebvorlage** ist die zum Erstellen der Website verwendete Vorlage.  <br/> Hinweis: Wenn Sie die Daten nach unterschiedlichen Websitetypen filtern möchten, exportieren Sie die Daten, und verwenden Sie die Stamm-Webvorlagen Spalte. <br/>Wenn die Richtlinien Ihrer Organisation das Anzeigen von Berichten verhindern, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt zum **Ausblenden von Details auf Benutzerebene** in den [Aktivitätsberichten im Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|9.  <br/> |Wählen **Sie Spalten verwalten**![Spalten](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) verwalten aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.    <br/> |
|10.  <br/> |Sie können die Berichtsdaten auch in eine Excel. CSV-Datei exportieren, indem Sie **** ![den](../../media/4dc548cc-8061-48d5-9240-6793affca43a.png) Link Export exportieren auswählen. Dadurch werden Daten für alle Websites exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2000 Websites können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2000 Websites müssen Sie die Daten zum Filtern und Sortieren exportieren.  <br/> Hinweis: Wenn die Daten in eine Excel-Datei exportiert werden, beachten Sie, dass das Datum, an dem der Inhaltsbericht generiert wurde, in der Datei in der Spalte **Daten als von** angezeigt wird.      <br/>   |
|||
   

