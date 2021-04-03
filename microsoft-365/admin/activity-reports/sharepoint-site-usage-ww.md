---
title: Microsoft 365-Berichte im Admin Center – SharePoint-Websitenutzung
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Erfahren Sie im Bericht zur Verwendung der SharePoint-Website, wie viele Dateien Benutzer auf SharePoint-Websites speichern, wie viele aktiv verwendet werden und wie viel Speicherplatz insgesamt verbraucht wird.
ms.openlocfilehash: cfae7e1fc02d769328af46f75fdafc143467630b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579506"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365-Berichte im Admin Center – SharePoint-Websitenutzung

Als Microsoft 365-Administrator  zeigt Ihnen das Dashboard Berichte die Aktivitätsübersicht für verschiedene Produkte in Ihrer Organisation. Hiermit können Sie einen Drilldown ausführen, um genauere Einblicke in die Aktivitäten für die einzelnen Produkte zu erhalten. Sie können z. B. eine allgemeine Ansicht des Werts erhalten, den Sie von SharePoint erhalten, in Bezug auf die Gesamtanzahl der Dateien, die Benutzer auf SharePoint-Websites speichern, wie viele Dateien aktiv verwendet werden, und den Speicherplatz, der auf allen diesen Websites verbraucht wird. Anschließend können Sie in den SharePoint-Sitenutzungsbericht einsteigen, um die Trends und Details pro Site-Ebene für alle Sites zu verstehen. 
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams Communications- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.
Microsoft 365-Berichte im Admin Center werden für GCC High- und DoD-Mandanten nicht unterstützt.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Wie erhalten Sie einen Bericht zur Verwendung von SharePoint-Websites

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Startseite des Dashboards auf die Schaltfläche **Weitere** Anzeigen auf der SharePoint-Karte.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Interpretieren des SharePoint-Websitenutzungsberichts

Sie können die Websitenutzung im SharePoint-Bericht anzeigen, indem Sie die Registerkarte **Websitenutzung** auswählen.<br/>![Microsoft 365-Berichte – Microsoft SharePoint-Websitenutzungsbericht.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Wählen **Sie Spalten auswählen** aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.  <br/> ![SharePoint-Websitenutzungsbericht – Spalten auswählen](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Website-URL  <br/> |Die vollständige URL der Website. <br/> |
|Gelöscht  <br/> |Der Löschstatus der Website. Es dauert mindestens sieben Tage, bis Websites als gelöscht markiert werden.  <br/> |
|Websitebesitzer  <br/> |Der Benutzername des primären Besitzers der Website.   <br/> |
|Websitebesitzerprinzipalname  <br/> |Die E-Mail-Adresse des Besitzers der Website. <br/> |
|Datum der letzten Aktivität (UTC)  <br/> | Das Datum der letzten Dateiaktivität oder das Anzeigen einer Seite auf der Website.  <br/> |
|Id der Websitesensitivitätsbezeichnung  <br/> | Die Vertraulichkeitsbezeichnung auf der Website.  <br/> |
|Externe Freigabe  <br/> | Die externen sharable-Einstellungen auf der Website.  <br/> |
|Nicht verwaltete Geräterichtlinie  <br/> | Die Websitezugriffsrichtlinie für nicht verwaltete Geräte.  <br/> |
|Geografischer Standort  <br/> | Der Geografische Standort der Website.  <br/> |
|Dateien  <br/> |Die Anzahl der Dateien auf der Website. <br/>|
|Aktive Dateien  <br/> | Die Anzahl der aktiven Dateien auf der Website.<br/> HINWEIS: Wenn Dateien während des angegebenen Zeitraums für den Bericht entfernt wurden, ist die Anzahl der aktiven Dateien im Bericht möglicherweise größer als die aktuelle Anzahl von Dateien auf der Website.  <br/> |
|Verwendeter Speicher (MB)  <br/> |Die Speichermenge, die derzeit auf der Website verwendet wird.  <br/>|
|Zugeordneter Speicher (MB)  <br/> |Die maximale Speichermenge, die für die Website zugewiesen ist.  <br/>|
|Seitenansichten  <br/> |Die Anzahl der Seiten, die auf der Website angezeigt wurden.  <br/>|
|Besuchte Seiten  <br/> |Die Anzahl der eindeutigen Seiten, die auf der Website besucht wurden.  <br/>|
|Anzahl anonymer Links  <br/> |Die Anzahl der Freigaben von Dokumenten oder Ordnern mithilfe von "Jeder mit dem Link" auf der Website.  <br/>|
|Anzahl der Unternehmenslinks  <br/> |Die Anzahl der Freigaben von Dokumenten oder Ordnern mithilfe von "Personen in der Organisation mit dem Link" auf der Website.  <br/>|
|Sicherer Link für die Anzahl von Gästen  <br/> |Die Anzahl der Freigaben von Dokumenten oder Ordnern mithilfe von "bestimmten Personen" auf der Website.  <br/>|
|Sicherer Link für die Mitgliederanzahl  <br/> |Die Anzahl der Freigaben von Dokumenten oder Ordnern mithilfe von "bestimmten Personen" auf der Website.  <br/>|
|Stammweb-Vorlage  <br/> |Die Vorlage, die zum Erstellen der Website verwendet wird.  <br/> HINWEIS: Wenn Sie die Daten nach verschiedenen Websitetypen filtern möchten, exportieren Sie die Daten, und verwenden Sie die Spalte Stammwebvorlage. |
|||