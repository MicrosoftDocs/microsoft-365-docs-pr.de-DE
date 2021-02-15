---
title: Microsoft 365-Berichte im Admin Center – Nutzung der SharePoint-Website
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
description: Im Bericht zur Verwendung der SharePoint-Website erfahren Sie, wie viele Dateien Benutzer auf SharePoint-Websites speichern, wie viele aktiv verwendet werden und wie viel Speicherplatz insgesamt verbraucht wird.
ms.openlocfilehash: 403ebfd75fca5ba5777832140155bb09734db3c7
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233508"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365-Berichte im Admin Center – Nutzung der SharePoint-Website

Als Microsoft 365-Administrator  zeigt Ihnen das Dashboard "Berichte" eine Übersicht über die Aktivitäten in verschiedenen Produkten In Ihrer Organisation. Hiermit können Sie einen Drilldown ausführen, um genauere Einblicke in die Aktivitäten für die einzelnen Produkte zu erhalten. Sie erhalten beispielsweise eine allgemeine Ansicht des Werts, den Sie von SharePoint erhalten, in Bezug auf die Gesamtzahl der Dateien, die Benutzer auf SharePoint-Websites speichern, wie viele Dateien aktiv verwendet werden und wie viel Speicherplatz auf allen diesen Websites verbraucht wird. Anschließend können Sie einen Drilldown in den Bericht zur Verwendung der SharePoint-Website machen, um die Trends und Details auf Websiteebene für alle Websites zu verstehen. 
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams Communications- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.
Microsoft 365-Berichte im Admin Center werden für GCC High- und DoD-Mandanten nicht unterstützt.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Wie erhalten Sie einen Bericht zur Verwendung von SharePoint-Websites

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Startseite des Dashboards auf **die** Schaltfläche "Weitere Anzeigen" auf der SharePoint-Karte.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Interpretieren des Berichts zur Verwendung der SharePoint-Website

Sie können die Websitenutzung im SharePoint-Bericht anzeigen, indem Sie die Registerkarte **"Websiteverwendung"** auswählen.<br/>![Microsoft 365-Berichte – Microsoft SharePoint-Websitenutzungsbericht.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Wählen **Sie Spalten zum** Hinzufügen oder Entfernen von Spalten aus dem Bericht aus.  <br/> ![Bericht zur Verwendung der SharePoint-Website – Spalten auswählen](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Website-URL  <br/> |Die vollständige URL der Website. <br/> |
|Gelöscht  <br/> |Der Löschstatus der Website. Es dauert mindestens sieben Tage, bis Websites als gelöscht markiert werden.  <br/> |
|Websitebesitzer  <br/> |Der Benutzername des primären Besitzers der Website.   <br/> |
|Prinzipalname des Websitebesitzers  <br/> |Die E-Mail-Adresse des Websitebesitzers. <br/> |
|Datum der letzten Aktivität (UTC)  <br/> | Das Datum, an dem die Dateiaktivität zuletzt erkannt oder eine Seite auf der Website angezeigt wurde.  <br/> |
|Id der Vertraulichkeitsbezeichnung der Website  <br/> | Die Vertraulichkeitsbezeichnung auf der Website.  <br/> |
|Externe Freigabe  <br/> | Die einstellungen für das externe Teilbare auf der Website.  <br/> |
|Nicht verwaltete Geräterichtlinie  <br/> | Die Standortzugriffsrichtlinie für nicht verwaltete Geräte.  <br/> |
|Geografischer Standort  <br/> | Der geografische Standort der Website.  <br/> |
|Dateien  <br/> |Die Anzahl der Dateien auf der Website. <br/>|
|Aktive Dateien  <br/> | Die Anzahl der aktiven Dateien auf der Website.<br/> HINWEIS: Wenn Dateien während des angegebenen Zeitraums für den Bericht entfernt wurden, kann die Anzahl der aktiven Dateien im Bericht größer sein als die aktuelle Anzahl von Dateien auf der Website.  <br/> |
|Verwendeter Speicher (MB)  <br/> |Die Speichermenge, die derzeit auf der Website verwendet wird.  <br/>|
|Zugewiesener Speicher (MB)  <br/> |Die maximale Speichermenge, die für die Website reserviert ist.  <br/>|
|Seitenansichten  <br/> |Die Anzahl der Seiten, die auf der Website angezeigt wurden.  <br/>|
|Besuchte Seiten  <br/> |Die Anzahl der eindeutigen Seiten, die auf der Website besucht wurden.  <br/>|
|Anzahl anonymer Links  <br/> |Gibt an, wie oft Dokumente oder Ordner mithilfe von "Jeder mit dem Link" auf der Website freigegeben werden.  <br/>|
|Anzahl der Unternehmenslinks  <br/> |Die Anzahl der Freigaben von Dokumenten oder Ordnern mithilfe von "Personen in der Organisation mit dem Link" auf der Website.  <br/>|
|Sicherer Link für Die Anzahl der Gäste  <br/> |Gibt an, wie oft Dokumente oder Ordner mit "bestimmten Personen" auf der Website freigegeben werden.  <br/>|
|Sicherer Link für die Mitgliederanzahl  <br/> |Gibt an, wie oft Dokumente oder Ordner mit "bestimmten Personen" auf der Website freigegeben werden.  <br/>|
|Stammweb-Vorlage  <br/> |Die Vorlage, die zum Erstellen der Website verwendet wird.  <br/> HINWEIS: Wenn Sie die Daten nach verschiedenen Websitetypen filtern möchten, exportieren Sie die Daten, und verwenden Sie die Spalte "Stammwebvorlage". |
|||