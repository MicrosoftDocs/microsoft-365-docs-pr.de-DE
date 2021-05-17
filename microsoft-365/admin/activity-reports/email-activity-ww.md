---
title: Microsoft 365 Berichte im Admin Center – E-Mail-Aktivität
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
- MET150
- MOE150
- GEA150
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: Erfahren Sie, wie Sie einen E-Mail-Aktivitätsbericht mithilfe des Microsoft 365 Berichte-Dashboards im Microsoft 365 erhalten.
ms.openlocfilehash: 65ef74ccd05aa4b55fc127985c03a490bb109b4b
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921954"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Microsoft 365 Berichte im Admin Center – E-Mail-Aktivität

Das Microsoft 365 **-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Sie können beispielsweise eine allgemeine Übersicht über den E-Mail-Verkehr innerhalb Ihrer Organisation auf der Seite "Berichte" abrufen und dann einen Drilldown in das Widget für E-Mail-Aktivität ausführen, um die Trends und die Details auf Ebene der einzelnen Benutzer für die E-Mail-Aktivität in Ihrer Organisation zu verstehen.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams-Kommunikations- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können. 

## <a name="how-to-get-to-the-email-activity-report"></a>Aufrufen des E-Mail-Aktivitätsberichts

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.
2. Wählen **Sie Weitere Anzeigen** unter **E-Mail-Aktivität aus.** 
3. Wählen Sie **in der** Dropdownliste E-Mail-Aktivität **Exchange** \> **E-Mail-Aktivität aus.**
  
## <a name="interpret-the-email-activity-report"></a>Interpretieren des E-Mail-Aktivitätsberichts

Sie erhalten einen Einblick in die E-Mail-Aktivitäten Ihrer Benutzer, indem Sie sich die Diagramme **Aktivität** und **Benutzer** ansehen. 
  
![E-Mail-Aktivitätsbericht](../../media/5eb1d9e9-8106-4843-acb7-c0238c0da816.png)
  
|Element|Beschreibung|
|:-----|:-----|
|1.  <br/> |Im Bericht **E-Mail-Aktivität** werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab.  <br/> |
|3.  <br/> |Anhand des Diagramms **Aktivität** können Sie den Trend in Hinsicht auf die Menge von E-Mail-Aktivitäten in Ihrer Organisation erkennen. Sie können die Aufteilung von E-Mail-Senden, E-Mail-Lese-, E-Mail-empfangenen, erstellten Besprechungs- oder Besprechungsaktivitäten verstehen.  <br/> |
|4.  <br/> |Anhand des Diagramms **Benutzer** können Sie den Trend in Hinsicht auf die Anzahl eindeutiger Benutzer erkennen, die die E-Mail-Aktivitäten generieren. Sie können den Trend der Benutzer sehen, die E-Mail-Senden, E-Mail-Lesen, E-Mail-Empfangen, Erstellen von Besprechungen oder Interaktionsaktivitäten für Besprechungen durchführen.  <br/> |
|5.  <br/> | Im Diagramm **Aktivität** ist die Y-Achse die Anzahl der Aktivitäten des Typs E-Mail gesendet, empfangene E-Mails, E-Mail-Lese-, Besprechungs- und Besprechungs interagiert.  <br/>  Im Diagramm **Benutzeraktivität** ist die Y-Achse die Aktivität des Benutzers, die E-Mails vom Typ gesendet, empfangene E-Mails, E-Mails gelesen, erstellte Besprechungen oder Besprechungen interagiert hat.  <br/>  Die X-Achse bezeichnet in beiden Diagrammen den ausgewählten Zeitraum für diesen bestimmten Bericht.  <br/> |
|6.  <br/> |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen.  <br/> |
|7.  <br/> | Die Tabelle zeigt eine Aufschlüsselung der E-Mail-Aktivitäten auf Ebene der einzelnen Benutzer. Hier werden alle Benutzer gezeigt, denen ein Exchange-Produkt zugewiesen ist, sowie deren E-Mail-Aktivitäten. <br/> <br/> **Benutzername** ist die E-Mail-Adresse des Benutzers.  <br/> **Anzeigename** ist der vollständige Name, wenn der Benutzer.  <br/> **Gelöscht** bezieht sich auf den Benutzer, dessen aktueller Status gelöscht ist, der aber während eines Teils des Berichtszeitraums aktiv war.  <br/> **Gelöscht am** ist das Datum, an dem der Benutzer gelöscht wurde.  <br/> **Letzte Aktivität** bezieht sich auf das Datum, an dem der Benutzer zuletzt eine E-Mail-Aktivität vom Typ Lesen oder Senden ausgeführt hat.  <br/> **Sendeaktionen** gibt an, wie oft eine E-Mail-Sendeaktion für den Benutzer erfasst wurde.  <br/> **Empfangsaktionen** gibt an, wie oft eine E-Mail-Empfangsaktion für den Benutzer erfasst wurde.  <br/> **Leseaktionen** gibt an, wie oft eine E-Mail-Leseaktion für den Benutzer erfasst wurde.  <br/> **Von Besprechungsaktionen erstellte** Aktionen gibt an, wie oft eine Aktion zum Senden von Besprechungsanfrage für den Benutzer aufgezeichnet wurde.  <br/> **Interaktionsaktionen für Besprechungen** gibt an, wie oft eine Besprechungsanfrage akzeptiert, mit Zag, Ablehnen oder Abbrechen für den Benutzer aufgezeichnet wurde.  <br/> **Zugewiesenes Produkt** bezeichnet die Produkte, die diesem Benutzer zugewiesen sind.  <br/>  Wenn die Richtlinien Ihrer Organisation eine Anzeige von Berichten verhindern, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt zum **Ausblenden von Details auf Benutzerebene** in den [Aktivitätsberichten im Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|8.  <br/> |Wählen **Sie Spalten auswählen** aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.  <br/> ![E-Mail-Aktivitätsbericht – Spalten auswählen](../../media/80ffa0ad-61c5-4a6f-8a1d-5f6730ff7da9.png)|
|9.  <br/> |Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.  <br/> |
|||
   
> [!NOTE]
> Der Bericht "E-Mail-Aktivität" ist nur für Postfächer verfügbar, die Benutzern zugeordnet sind, die über Lizenzen verfügen.
