---
title: Microsoft 365-Berichte im Admin Center-e-Mail-Aktivität
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
description: Erfahren Sie, wie Sie einen e-Mail-Aktivitätsbericht mithilfe des Microsoft 365 Reports-Dashboards im Microsoft 365 Admin Center erhalten.
ms.openlocfilehash: b2b322fe7e35c3fa7e4a5966919321b329004d92
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948232"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Microsoft 365-Berichte im Admin Center-e-Mail-Aktivität

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Sie können beispielsweise eine allgemeine Übersicht über den E-Mail-Verkehr innerhalb Ihrer Organisation auf der Seite "Berichte" abrufen und dann einen Drilldown in das Widget für E-Mail-Aktivität ausführen, um die Trends und die Details auf Ebene der einzelnen Benutzer für die E-Mail-Aktivität in Ihrer Organisation zu verstehen.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen. 

## <a name="how-to-get-to-the-email-activity-report"></a>Aufrufen des E-Mail-Aktivitätsberichts

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.

    
2. Wählen Sie in der Dropdownliste **Bericht auswählen** die Option **Exchange** \> **-e-Mail-Aktivität**aus.
  
## <a name="interpret-the-email-activity-report"></a>Interpretieren des E-Mail-Aktivitätsberichts

Sie erhalten einen Einblick in die E-Mail-Aktivitäten Ihrer Benutzer, indem Sie sich die Diagramme **Aktivität** und **Benutzer** ansehen. 
  
![E-Mail-Aktivitätsbericht](../../media/2317f03d-2d71-46bf-a5c7-d94dbc8cfbe1.png)
  
|Element|Beschreibung|
|:-----|:-----|
|1.  <br/> |Im Bericht **E-Mail-Aktivität** werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab.  <br/> |
|3.  <br/> |Anhand des Diagramms **Aktivität** können Sie den Trend in Hinsicht auf die Menge von E-Mail-Aktivitäten in Ihrer Organisation erkennen. Sie können die Aufteilung von e-Mail-Nachrichten, e-Mail-Lesevorgängen, empfangenen e-Mails, erstellten Besprechungen oder Aktivitäten mit Besprechungen verstehen.  <br/> |
|4.  <br/> |Anhand des Diagramms **Benutzer** können Sie den Trend in Hinsicht auf die Anzahl eindeutiger Benutzer erkennen, die die E-Mail-Aktivitäten generieren. Sie können sich die Entwicklung von Benutzern ansehen, die e-Mail-senden, e-Mail-lesen, e-Mail-Empfang, Besprechungs Erstellung oder interaktive Besprechungs Aktivitäten durchführen.  <br/> |
|5.  <br/> | Im **Aktivitäts** Diagramm ist die Y-Achse die Anzahl der Aktivitäten des Typs "gesendete e-Mail", "empfangene e-Mail", "e-Mail-lesen", "erstellte Besprechungen" und "Besprechungs Interaktion".  <br/>  Im Diagramm **Benutzer** Aktivität ist die Y-Achse die Leistungsfähigkeit des Benutzers, der die Art von e-Mail-Nachrichten, empfangene e-Mails, e-Mail-Lesevorgänge, erstellte Besprechungen oder interaktive Besprechungen ausführt.  <br/>  Die X-Achse bezeichnet in beiden Diagrammen den ausgewählten Zeitraum für diesen bestimmten Bericht.  <br/> |
|6.  <br/> |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Wählen Sie beispielsweise im Diagramm " **Aktivität** " die Diagramme " **gesendet**", " **empfangen**", " **gelesen**", " **Besprechung erstellt**" oder "mit **Interaktion interagierender** ![ Filter" für bestimmte verwandte Daten aus, ](../../media/6065f515-b97b-4829-b683-a7667542d1af.png) um nur die zugehörigen Informationen anzuzeigen.   Durch das Ändern dieser Auswahl werden die Informationen in der Gitternetztabelle nicht geändert.  <br/> |
|7.  <br/> | Die Tabelle zeigt eine Aufschlüsselung der E-Mail-Aktivitäten auf Ebene der einzelnen Benutzer. Hier werden alle Benutzer gezeigt, denen ein Exchange-Produkt zugewiesen ist, sowie deren E-Mail-Aktivitäten. <br/> <br/> **Benutzername** ist die E-Mail-Adresse des Benutzers.  <br/> **Anzeigename** ist der vollständige Name, wenn der Benutzer.  <br/> **Gelöscht** bezieht sich auf den Benutzer, dessen aktueller Status gelöscht ist, der aber während eines Teils des Berichtszeitraums aktiv war.  <br/> **Gelöscht am** ist das Datum, an dem der Benutzer gelöscht wurde.  <br/> **Letzte Aktivität** bezieht sich auf das Datum, an dem der Benutzer zuletzt eine E-Mail-Aktivität vom Typ Lesen oder Senden ausgeführt hat.  <br/> **Sendeaktionen** gibt an, wie oft eine E-Mail-Sendeaktion für den Benutzer erfasst wurde.  <br/> **Empfangsaktionen** gibt an, wie oft eine E-Mail-Empfangsaktion für den Benutzer erfasst wurde.  <br/> **Leseaktionen** gibt an, wie oft eine E-Mail-Leseaktion für den Benutzer erfasst wurde.  <br/> " **Besprechungs Erstellungsaktionen** " gibt an, wie oft eine Besprechungsanfrage-Sendeaktion für den Benutzer aufgezeichnet wurde.  <br/> " **Interaktive Besprechungs Aktionen** " gibt an, wie oft eine Besprechungsanfrage akzeptieren, mit Vorbehalt, ablehnen oder Abbrechen Aktion für den Benutzer aufgezeichnet wurde.  <br/> **Zugewiesenes Produkt** bezeichnet die Produkte, die diesem Benutzer zugewiesen sind.  <br/>  Wenn die Richtlinien Ihrer Organisation eine Anzeige von Berichten verhindern, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt zum **Ausblenden von Details auf Benutzerebene** in den [Aktivitätsberichten im Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|8.  <br/> |Sie können die Berichtsdaten auch in eine Excel. CSV-Datei exportieren, indem Sie den Link Exportschaltfläche **exportieren** auswählen ![ ](../../media/816a224b-6ca7-4967-a135-4f6427f64dc8.JPG) . Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.  <br/> |
|||
   
Hinweis: der Bericht über e-Mail-Aktivitäten steht nur für Postfächer zur Verfügung, die Benutzern mit Lizenzen zugeordnet sind.
