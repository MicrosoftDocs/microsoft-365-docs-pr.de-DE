---
title: Microsoft 365-Berichte im Admin Center-Microsoft 365-Gruppen
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Informieren Sie sich über die Gruppen und ihre Aktivitäten über einen Microsoft 365-Gruppenbericht.
ms.openlocfilehash: 4a89f09f89e399905d0cb6927eca76c1242dfc62
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611950"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Microsoft 365-Berichte im Admin Center-Microsoft 365-Gruppen

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an. Im Microsoft 365 Groups-Bericht erhalten Sie Einblicke in die Aktivitäten von Gruppen in Ihrer Organisation und sehen, wie viele Gruppen erstellt und verwendet werden.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.  
  
## <a name="how-to-get-to-the-groups-report"></a>So gelangen Sie zum Gruppenbericht

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
2. Klicken Sie auf der Dashboard-Startseite auf die Schaltfläche **mehr anzeigen** der aktiven Benutzer – Microsoft 365-Apps oder der aktiven Benutzer – Microsoft 365-Dienst Karte, um zur Seite Office 365 Bericht zu gelangen.
  
## <a name="interpret-the-groups-report"></a>Interpretieren des Gruppenberichts

Sie können die Aktivierungen im Bericht Office 365 anzeigen, indem Sie auf die Registerkarte **Gruppenaktivität** wählen.<br/>![Microsoft 365 Reports-Microsoft Office 365 Gruppenaktivität.](../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png)

Wählen Sie **Spalten auswählen** aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.  <br/> ![Aktivitätsbericht für Office 365 Gruppen – Spalten auswählen](../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png)

Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren. 

|Element|Beschreibung|
|:-----|:-----|
|**Metrik**|**Definition**|
|Name der Gruppe  <br/> |Der Name der Gruppe.  <br/> |
|Gelöscht  <br/> |Die Anzahl der gelöschten Gruppen. Wenn eine Gruppe gelöscht wird, die im Berichtszeitraum Aktivitäten ausgeführt hat, wird sie im Raster mit dieser auf TRUE festgelegten Kennzeichnung angezeigt.  <br/> |
|Gruppenbesitzer  <br/> |Der Name des Gruppen Besitzers.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum, an dem eine Nachricht von der Gruppe empfangen wurde. Dies ist das aktuellste Datum, an dem eine Aktivität in einer E-Mail-Unterhaltung, in Yammer oder auf der Website stattfand.  <br/> |
|Typ  <br/> |Der Typ der Gruppe. Es kann sich um eine private oder eine öffentliche Gruppe handeln.  <br/> |
|In Exchange empfangene e-Mails  <br/> |Die Anzahl der Nachrichten, die von der Gruppe empfangen wurden.|
|E-Mails in Exchange (Gesamt)  <br/> |Die Gesamtzahl der Elemente im Postfach der Gruppe.  <br/> |
|Für Exchange verwendeter Postfachspeicher (MB)  <br/> |Der Speicherplatz, der vom Postfach der Gruppe verwendet wird. <br/>|
|SharePoint-Dateien (Gesamt)  <br/> |Die Anzahl der Dateien, die auf SharePoint-Gruppen Websites gespeichert sind.  <br/> |
|SharePoint-Dateien (aktiv)  <br/> |Die Anzahl der Dateien auf der SharePoint-Gruppen Website, die während des Berichtszeitraums verarbeitet wurden (angezeigt oder geändert, synchronisiert, intern oder extern freigegeben).  <br/> |
|Gesamter Websitespeicher, der für SharePoint verwendet wird (MB)  <br/> |Die Größe des Speichers in MB, der während des Berichtszeitraums verwendet wurde.  <br/> |
|Nachrichten in "jammern" (veröffentlicht)  <br/> |Die Anzahl der Nachrichten, die während des Berichtszeitraums in der Gruppe "jammern" veröffentlicht wurden.  <br/> |
|Nachrichten in "jammern" (lesen)  <br/> |Die Anzahl der Unterhaltungen, die während des Berichtszeitraums in der Gruppe "jammern" gelesen wurden.  <br/> |
|Nachrichten in jammern (liked)  <br/> |Die Anzahl der Nachrichten, die während des Berichtszeitraums in der Gruppe "jammern" gewünscht werden.  <br/> |
|Members  <br/> |Die Anzahl der Mitglieder in der Gruppe.  <br/> |
|Externe Mitglieder |Die Anzahl der externen Benutzer in der Gruppe.|
|||