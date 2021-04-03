---
title: Microsoft 365-Berichte im Admin Center – Microsoft 365-Gruppen
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
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Erhalten Sie einen Microsoft 365-Gruppenbericht, um die Gruppen und ihre Aktivitäten kennen zu lernen.
ms.openlocfilehash: fd3aa664b5a40bb5fffe0ed23e07ba6f1a5907c2
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579566"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Microsoft 365-Berichte im Admin Center – Microsoft 365-Gruppen

Das Microsoft 365 **Reports-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an. Im Microsoft 365-Gruppenbericht können Sie Einblicke in die Aktivitäten von Gruppen in Ihrer Organisation gewinnen und sehen, wie viele Gruppen erstellt und verwendet werden.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams Communications- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.  
  
## <a name="how-to-get-to-the-groups-report"></a>So gelangen Sie zum Gruppenbericht

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der  Dashboard-Homepage auf die Schaltfläche Weitere Anzeigen auf der Seite Aktive Benutzer – Microsoft 365-Apps oder aktive Benutzer – Microsoft 365-Dienste, um zur Office 365-Berichtsseite zu gelangen.
  
## <a name="interpret-the-groups-report"></a>Interpretieren des Gruppenberichts

Sie können die Aktivierungen im Office 365-Bericht anzeigen, indem Sie die Registerkarte **Gruppenaktivität** auswählen.<br/>![Microsoft 365-Berichte – Microsoft Office 365 Gruppenaktivitäten.](../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png)

Wählen **Sie Spalten auswählen** aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.  <br/> ![Aktivitätsbericht für Office 365-Gruppen – Spalten auswählen](../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 

|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Name der Gruppe  <br/> |Der Name der Gruppe.  <br/> |
|Gelöscht  <br/> |Die Anzahl der gelöschten Gruppen. Wenn eine Gruppe gelöscht wird, die im Berichtszeitraum Aktivitäten ausgeführt hat, wird sie im Raster mit dieser auf TRUE festgelegten Kennzeichnung angezeigt.  <br/> |
|Gruppenbesitzer  <br/> |Der Name des Gruppenbesitzers.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum, an dem eine Nachricht von der Gruppe empfangen wurde. Dies ist das aktuellste Datum, an dem eine Aktivität in einer E-Mail-Unterhaltung, in Yammer oder auf der Website stattfand.  <br/> |
|Typ  <br/> |Der Typ der Gruppe. Es kann sich um eine private oder eine öffentliche Gruppe handeln.  <br/> |
|In Exchange empfangene E-Mails  <br/> |Die Anzahl der nachrichten, die von der Gruppe empfangen werden.|
|E-Mails in Exchange (gesamt)  <br/> |Die Gesamtanzahl der Elemente im Postfach der Gruppe.  <br/> |
|Postfachspeicher für Exchange (MB)  <br/> |Der vom Postfach der Gruppe verwendete Speicher. <br/>|
|SharePoint-Dateien (gesamt)  <br/> |Die Anzahl der auf SharePoint-Gruppenwebsites gespeicherten Dateien.  <br/> |
|SharePoint-Dateien (aktiv)  <br/> |Die Anzahl der Dateien auf der SharePoint-Gruppenwebsite, die während des Berichtszeitraums bearbeitet (angezeigt oder geändert, synchronisiert, intern oder extern freigegeben) wurden.  <br/> |
|Insgesamt für SharePoint (MB) verwendeter Websitespeicher  <br/> |Die Speichermenge in MB, die während des Berichtszeitraums verwendet wurde.  <br/> |
|Nachrichten in Yammer (veröffentlicht)  <br/> |Die Anzahl der Nachrichten, die in der Yammer Berichtszeitraum veröffentlicht wurden.  <br/> |
|Nachrichten in Yammer (Lesen)  <br/> |Die Anzahl der Unterhaltungen, die in der gruppe Yammer Berichtszeitraum gelesen werden.  <br/> |
|Nachrichten in Yammer (gefällt)  <br/> |Die Anzahl der nachrichten, die in der gruppe Yammer Berichtszeitraum gefielen.  <br/> |
|Mitglieder  <br/> |Die Anzahl der Mitglieder in der Gruppe.  <br/> |
|Externe Mitglieder |Die Anzahl der externen Benutzer in der Gruppe.|
|||