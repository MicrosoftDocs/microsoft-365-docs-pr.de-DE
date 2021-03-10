---
title: Aktiver Benutzer in Microsoft 365-Verwendungsberichten
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Erfahren Sie mehr über einen aktiven Benutzer von Microsoft 365-Nutzungsanalysen, Aktivitätsberichten und Einführungsmetriken.
ms.openlocfilehash: 7b8d15a88568c9af8b11a157dad2ec5f76ace6d3
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50603972"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Aktiver Benutzer in Microsoft 365-Verwendungsberichten

## <a name="active-user-in-usage-reports"></a>Aktive Benutzer in Verwendungsberichten

Ein aktiver Benutzer von Microsoft 365-Produkten für [Microsoft 365-Nutzungsanalysen](usage-analytics.md) und die Aktivitätsberichte im [Admin Center](../activity-reports/activity-reports.md) sind wie folgt definiert. 
  
|**Produkt**|**Definition eines aktiven Benutzers**|**Anmerkungen**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Jeder Benutzer, der eine der folgenden Aktionen ausgeführt hat: Markieren Sie Besprechungsanfragen als gelesen, senden Sie Nachrichten, erstellen Sie Termine, senden Sie Besprechungsanfragen, akzeptieren (als zaglos) oder ablehnen Sie Besprechungsanfragen, brechen Sie Besprechungen ab.  <br/> |Es werden keine Kalenderinformationen dargestellt. Dies wird in einem bevorstehenden Update enthalten sein.  <br/> |
|SharePoint Online  <br/> |Jeder Benutzer, der mit einer Datei interagiert hat, entweder durch Erstellen, Ändern, Anzeigen, Löschen, internes oder externes Freigeben oder Synchronisieren mit Clients auf einer beliebigen Website oder Anzeigen einer Seite auf einer beliebigen Website.  <br/> |Die aktive Benutzermetrik für SharePoint Online in der Microsoft 365 Usage Analytics-Vorlagen-App spiegelt nur Benutzer wider, die Dateiaktivitäten für eine SharePoint-Teamwebsite oder eine Gruppenwebsite erstellt haben. Die Vorlagen-App wird aktualisiert, um die Definition mit der definition in den Verwendungsberichten im Admin Center zu synchronisieren.  <br/> |
|OneDrive for Business  <br/> |Jeder Benutzer, der mit einer Datei interagiert hat, entweder durch Erstellen, Ändern, Anzeigen, Löschen, internes oder externes Freigeben oder Synchronisieren mit Clients.  <br/> ||
|Yammer  <br/> |Jeder Benutzer, der eine Nachricht auf Yammer gelesen, gepostet oder mit "Gefällt mir" gekennzeichnet hat.  <br/> ||
|Skype for Business  <br/> |Jeder Benutzer, der an einer Peer-zu-Peer-Sitzung teilgenommen hat (einschließlich Chatnachrichten, Audio- und Videoanrufen, Anwendungsfreigaben und Dateiübertragungen) oder eine Konferenz organisiert bzw. daran teilgenommen hat.  <br/> ||
|Office  <br/> |Jeder Benutzer, der sein Microsoft 365 Pro Plus-, Visio Pro- oder Project Pro-Abonnement auf mindestens einem Gerät aktiviert hat.  <br/> ||
|Microsoft 365-Gruppen  <br/> |Jedes Gruppenmitglied mit Postfachaktivität (wenn eine Nachricht an die Gruppe gesendet wurde).  <br/> |Diese Definition wird um gruppenwebsitedateiaktivität und Yammer Gruppenaktivität erweitert (Dateiaktivität auf der Gruppenwebsite und Nachricht, die Yammer gruppe zugeordnet ist.) Diese Daten sind derzeit nicht in der Microsoft 365 Usage Analytics-Vorlagen-App verfügbar.  <br/> |
|Microsoft Teams  <br/> |Jeder Benutzer, der an Chatnachrichten, privaten Chatnachrichten, Anrufen, Besprechungen oder anderen Aktivitäten teilgenommen hat. Andere Aktivitäten sind definiert als die Anzahl anderer Teamaktivitäten durch den Benutzer, von denen einige umfassen und nicht beschränkt auf: Liking-Nachrichten, Apps, Arbeiten an Dateien, Suchen, Folgen von Teams und Kanal und Favorisieren.  <br/> ||
   
## <a name="adoption-metrics"></a>Einführungsmetriken

[Die Microsoft 365-Verwendungsanalyse](usage-analytics.md) enthält zusätzliche Einführungsmetriken im Zusammenhang mit aktiven Benutzern, um die Einführung der Produkte im Laufe der Zeit anzuzeigen. Diese Metriken gelten für den ausgewählten Monat, das Jahr und das ausgewählte Produkt und werden wie folgt definiert. 
  
|**Metrik**|**Beschreibung**|
|:-----|:-----|
|EnabledUsers  <br/> |Anzahl der Benutzer, die für die Verwendung des Produkts im Monat aktiviert sind.  <br/> |
|ActiveUsers  <br/> |Anzahl der im Monat aktiven Benutzer.  <br/> |
|MoMReturningUsers  <br/> |Anzahl der im Monat aktiven Benutzer, die auch im vorigen Monat aktiv waren.  <br/> |
|FirstTimeUsers  <br/> |Anzahl der im Monat aktiven Benutzer, die den Dienst noch nie verwendet haben.  <br/> |
|CumulativeActiveUsers  <br/> |Anzahl der im Monat aktiven Benutzer plus eines beliebigen vorherigen Monats.  <br/> |
|ActiveUsers(%)  <br/> |Prozent der Benutzer, gerundet auf den nächsten Zehnten, aktiv im Monat im Vergleich zur Anzahl der in diesem Monat aktivierten Benutzer.  <br/> |
|MoMReturningUsers(%)  <br/> |Prozent der Benutzer, gerundet auf den nächsten Zehnten, aktiv im Monat, die auch im vorigen Monat aktiv waren, im Vergleich zur Anzahl der aktiven Benutzer.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, CumulativeActiveUsers wurden ab dem 1. Januar 2018 unter Einbeziehung von &amp; Microsoft Teams zurückgesetzt.
  
