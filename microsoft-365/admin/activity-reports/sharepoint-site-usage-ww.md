---
title: Microsoft 365 Berichte im Admin Center – SharePoint Websitenutzung
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Rufen Sie den Bericht SharePoint Websitenutzung ab, um zu erfahren, wie viele Dateien Benutzer auf SharePoint Websites speichern, wie viele aktiv verwendet werden und wie viel Speicherplatz insgesamt verbraucht wird.
ms.openlocfilehash: d2c549dbb5ab456dddedf0422cd8aebafab1987d
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393331"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365 Berichte im Admin Center – SharePoint Websitenutzung

Als Microsoft 365-Administrator zeigt Ihnen das **Dashboard "Berichte"** die Aktivitätsübersicht für verschiedene Produkte in Ihrer Organisation an. Hiermit können Sie einen Drilldown ausführen, um genauere Einblicke in die Aktivitäten für die einzelnen Produkte zu erhalten. Sie können z. B. einen allgemeinen Überblick über den Wert erhalten, den Sie von SharePoint erhalten, in Bezug auf die Gesamtzahl der Dateien, die Benutzer auf SharePoint Websites speichern, wie viele Dateien aktiv verwendet werden, und den Speicher, der für alle diese Websites genutzt wird. Anschließend können Sie in den SharePoint-Sitenutzungsbericht einsteigen, um die Trends und Details pro Site-Ebene für alle Sites zu verstehen. 
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtsleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-, Teams- oder Skype for Business administrator sein, um Berichte anzeigen zu können.
Microsoft 365 Berichte im Admin Center werden für GCC High- und DoD-Mandanten nicht unterstützt.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Wie erhalten Sie einen Bericht zur Verwendung von SharePoint-Websites

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf die Schaltfläche **"Weitere Anzeigen"** auf der SharePoint Karte.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Interpretieren des SharePoint Websitenutzungsberichts

Sie können die Websitenutzung im SharePoint Bericht anzeigen, indem Sie die Registerkarte **"Websitenutzung"** auswählen.<br/>![Microsoft 365 Berichte – Microsoft SharePoint Websitenutzungsbericht.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Wählen Sie **"Spalten auswählen"** aus, um Dem Bericht Spalten hinzuzufügen oder daraus zu entfernen.  <br/> ![SharePoint Websitenutzungsbericht – Spalten auswählen](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Website-URL  <br/> |Die vollständige URL der Website. <br/> |
|Gelöscht  <br/> |Der Löschstatus der Website. Es dauert mindestens sieben Tage, bis Websites als gelöscht markiert werden.  <br/> |
|Websitebesitzer  <br/> |Der Benutzername des primären Besitzers der Website.   <br/> |
|Prinzipalname des Websitebesitzers  <br/> |Die E-Mail-Adresse des Besitzers der Website. <br/> |
|Datum der letzten Aktivität (UTC)  <br/> | Das Datum der letzten Erkennung der Dateiaktivität oder das Anzeigen einer Seite auf der Website.  <br/> |
|Id der Vertraulichkeitsbezeichnung der Website  <br/> | Die Vertraulichkeitsbezeichnung auf der Website.  <br/> |
|Externe Freigabe  <br/> | Die externen Freigabeeinstellungen auf der Website.  <br/> |
|Richtlinie für nicht verwaltete Geräte  <br/> | Die Standortzugriffsrichtlinie für nicht verwaltete Geräte.  <br/> |
|Geografischer Standort  <br/> | Der geografische Standort der Website.  <br/> |
|Dateien  <br/> |Die Anzahl der Dateien auf der Website. <br/>|
|Aktive Dateien  <br/> | Die Anzahl der aktiven Dateien auf der Website.<br/> HINWEIS: Wenn Dateien während des angegebenen Zeitraums für den Bericht entfernt wurden, kann die Anzahl der aktiven Dateien, die im Bericht angezeigt werden, größer als die aktuelle Anzahl von Dateien auf der Website sein.  <br/> |
|verwendeter Storage (MB)  <br/> |Der Speicherplatz, der derzeit auf der Website verwendet wird.  <br/>|
|zugewiesene Storage (MB)  <br/> |Der maximale Speicherplatz, der für die Website reserviert ist.  <br/>|
|Seitenaufrufe  <br/> |Die Anzahl der Male, mit denen Seiten auf der Website angezeigt wurden.  <br/>|
|Besuchte Seiten  <br/> |Die Anzahl der eindeutigen Seiten, die auf der Website besucht wurden.  <br/>|
|Anzahl anonymer Links  <br/> |Gibt an, wie oft Dokumente oder Ordner mithilfe von "Jeder mit dem Link" auf der Website freigegeben werden.  <br/>|
|Anzahl der Unternehmenslinks  <br/> |Gibt an, wie oft Dokumente oder Ordner mithilfe von "Personen in organisation mit dem Link" auf der Website freigegeben werden.  <br/>|
|Sicherer Link für die Anzahl der Gäste  <br/> |Gibt an, wie oft Dokumente oder Ordner mit "bestimmten Personen" auf der Website freigegeben werden.  <br/>|
|Sicherer Link für die Mitgliederanzahl  <br/> |Gibt an, wie oft Dokumente oder Ordner mit "bestimmten Personen" auf der Website freigegeben werden.  <br/>|
|Stammweb-Vorlage  <br/> |Die Vorlage, die zum Erstellen der Website verwendet wird.  <br/> HINWEIS: Wenn Sie die Daten nach verschiedenen Websitetypen filtern möchten, exportieren Sie die Daten, und verwenden Sie die Spalte "Stammwebvorlage". |
|||