---
title: Microsoft 365-Berichte im Admin Center – Verwendung von SharePoint-Websites
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
description: Rufen Sie den Bericht über die SharePoint-Websitenutzung ab, um zu erfahren, wie viele Dateien Benutzer in SharePoint-Websites speichern, wie viele aktiv verwendet werden und wie viel Speicher insgesamt verbraucht wird.
ms.openlocfilehash: bc9345a5e281f1e7343bf62a2dc6832587d0786e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649825"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365-Berichte im Admin Center – Verwendung von SharePoint-Websites

Als Microsoft 365-Administrator zeigt das Dashboard **Berichte** die Aktivitätsübersicht für verschiedene Produkte in Ihrer Organisation an. Hiermit können Sie einen Drilldown ausführen, um genauere Einblicke in die Aktivitäten für die einzelnen Produkte zu erhalten. Sie können beispielsweise eine allgemeine Übersicht über den Wert erhalten, den Sie von SharePoint erhalten, in Bezug auf die Gesamtzahl der Dateien, die Benutzer in SharePoint-Websites speichern, die Anzahl der aktiven Dateien und den Speicherplatz, der für alle diese Websites genutzt wird. Anschließend können Sie einen Drilldown zum SharePoint-Websiteverwendungsbericht durchführen, um die Trends und Details auf Websiteebene für alle Websites zu verstehen. 
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.
Microsoft 365-Berichte im Admin Center werden für gcc High-und DoD-Mandanten nicht unterstützt.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Wie erhalten Sie einen Bericht zur Verwendung von SharePoint-Websites

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf der SharePoint-Karte auf die Schaltfläche **mehr anzeigen** .
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Interpretieren des Berichts zur Verwendung der SharePoint-Website

Sie können die Websiteverwendung im SharePoint-Bericht anzeigen, indem Sie die Registerkarte **Websitenutzung** auswählen.<br/>![Microsoft 365-Berichte – Nutzungsbericht zur Microsoft SharePoint-Website.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Wählen Sie **Spalten auswählen** aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.  <br/> ![SharePoint-Websiteverwendungsbericht – auswählen von Spalten](../../media/639f3cfd-6725-4318-a225-6d5c2f01770c.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 
  
|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Website-URL  <br/> |Die vollständige URL der Website. <br/> |
|Gelöscht  <br/> |Der Löschstatus der Website. Es dauert mindestens sieben Tage, bis Websites als gelöscht markiert werden.  <br/> |
|Websitebesitzer  <br/> |Der Benutzername des primären Besitzers der Website.   <br/> |
|Prinzipalname des Websitebesitzers  <br/> |Die e-Mail-Adresse des Besitzers der Website. <br/> |
|Datum der letzten Aktivität (UTC)  <br/> | Das Datum, an dem die Dateiaktivität der letzten Zeit erkannt oder eine Seite auf der Website angezeigt wurde.  <br/> |
|Dateien  <br/> |Die Anzahl der Dateien auf der Website. <br/>|
|Aktive Dateien  <br/> | Die Anzahl der aktiven Dateien auf der Website.<br/> Hinweis: Wenn Dateien während des angegebenen Zeitraums für den Bericht entfernt wurden, kann die Anzahl der aktiven Dateien, die im Bericht angezeigt werden, größer sein als die aktuelle Anzahl der Dateien auf der Website.  <br/> |
|Verwendeter Speicherplatz (MB)  <br/> |Die derzeit auf der Website verwendete Speichermenge.  <br/>|
|Zugewiesener Speicherplatz (MB)  <br/> |Die maximale Menge an Speicherplatz, die für die Website reserviert ist.  <br/>|
|Seitenansichten  <br/> |Die Anzahl der Seiten, die auf der Website angezeigt wurden.  <br/>|
|Besuchte Seiten  <br/> |Die Anzahl der eindeutigen Seiten, die auf der Website besucht wurden.  <br/>|
|Stammweb-Vorlage  <br/> |Die Vorlage, die zum Erstellen der Website verwendet wird.  <br/> Hinweis: Wenn Sie die Daten nach unterschiedlichen Websitetypen filtern möchten, exportieren Sie die Daten, und verwenden Sie die Stamm-Webvorlagen Spalte. |
|||