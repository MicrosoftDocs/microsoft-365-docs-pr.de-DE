---
title: Aktiver Benutzer in Microsoft 365-Nutzungsberichten
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Erfahren Sie mehr über einen aktiven Benutzer von Microsoft 365-Nutzungsanalysen, Aktivitätsberichten und Akzeptanz Metriken.
ms.openlocfilehash: 2117bae32913ad713318c1df25be66d6ef6859e5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631791"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Aktiver Benutzer in Microsoft 365-Nutzungsberichten

## <a name="active-user-in-usage-reports"></a>Aktive Benutzer in Verwendungsberichten

Ein aktiver Benutzer von Microsoft 365-Produkten für [Microsoft 365-Verwendungsanalyse](usage-analytics.md) und die [Aktivitätsberichte im Admin Center](../activity-reports/activity-reports.md) ist wie folgt definiert. 
  
|**Produkt**|**Definition eines aktiven Benutzers**|**Anmerkungen**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Jeder Benutzer, der eine E-Mail gelesen oder gesendet hat.  <br/> |Es werden keine Kalenderinformationen dargestellt. Dies wird in einem bevorstehenden Update enthalten sein.  <br/> |
|SharePoint Online  <br/> |Jeder Benutzer, der mit einer Datei interagiert hat, entweder durch Erstellen, Ändern, Anzeigen, Löschen, internes oder externes Freigeben oder Synchronisieren mit Clients auf einer beliebigen Website oder Anzeigen einer Seite auf einer beliebigen Website.  <br/> |Die aktive Benutzer Metrik für SharePoint Online in der Vorlagen-App für Microsoft 365 Usage Analytics spiegelt nur Benutzer wider, die eine Dateiaktivität für eine SharePoint-Team Website oder eine Gruppen Website durchführte. Die Vorlagen-APP wird aktualisiert, um die Definition auf dieselbe Weise wie die in den Nutzungsberichten im Admin Center zu synchronisieren.  <br/> |
|OneDrive for Business  <br/> |Jeder Benutzer, der mit einer Datei interagiert hat, entweder durch Erstellen, Ändern, Anzeigen, Löschen, internes oder externes Freigeben oder Synchronisieren mit Clients.  <br/> ||
|Yammer  <br/> |Jeder Benutzer, der eine Nachricht auf Yammer gelesen, gepostet oder mit "Gefällt mir" gekennzeichnet hat.  <br/> ||
|Skype for Business  <br/> |Jeder Benutzer, der an einer Peer-zu-Peer-Sitzung teilgenommen hat (einschließlich Chatnachrichten, Audio- und Videoanrufen, Anwendungsfreigaben und Dateiübertragungen) oder eine Konferenz organisiert bzw. daran teilgenommen hat.  <br/> ||
|Office  <br/> |Jeder Benutzer, der sein Microsoft 365 pro Plus-, Visio pro-oder Project pro-Abonnement auf mindestens einem Gerät aktiviert hat.  <br/> ||
|Microsoft 365-Gruppen  <br/> |Jedes Gruppenmitglied mit Postfachaktivität (wenn eine Nachricht an die Gruppe gesendet wurde).  <br/> |Diese Definition wird mit der Aktivität "Gruppen Websitedatei Aktivität" und "jammern der Gruppe" (Dateiaktivität auf der Gruppen Website und Nachricht, die der Gruppe zugeordnet ist, in die Gruppe "jammern" gesendet) erweitert. Diese Daten sind derzeit in der Microsoft 365-Verwendungsanalyse-Vorlagen-APP nicht verfügbar.  <br/> |
|Microsoft Teams  <br/> |Jeder Benutzer, der an Chatnachrichten, privaten Chatnachrichten, anrufen, Besprechungen oder anderen Aktivitäten teilgenommen hat. Andere Aktivität ist definiert als die Anzahl von anderen Teamaktivitäten des Benutzers, von denen einige, und nicht ausschließlich: Nachrichten, apps, arbeiten an Dateien, suchen, Folgen von Teams und Kanal und Bevorzugung für Sie sind.  <br/> ||
   
## <a name="adoption-metrics"></a>Akzeptanz Metriken

[Microsoft 365 Usage Analytics](usage-analytics.md) enthält zusätzliche Akzeptanz Metriken im Zusammenhang mit aktiven Benutzern, um die Einführung der Produkte im Laufe der Zeit zu zeigen. Diese Metriken sind für den ausgewählten Monat, das Jahr und das Produkt gültig und werden wie folgt definiert. 
  
|**Metrik**|**Beschreibung**|
|:-----|:-----|
|EnabledUsers  <br/> |Die Anzahl der Benutzer, die für die Verwendung des Produkts im Monat aktiviert sind.  <br/> |
|ActiveUsers  <br/> |Die Anzahl der Benutzer, die im Monat aktiv sind.  <br/> |
|MoMReturningUsers  <br/> |Die Anzahl der Benutzer, die in dem Monat aktiv sind, die auch im vorherigen Monat aktiv waren.  <br/> |
|FirstTimeUsers  <br/> |Die Anzahl der Benutzer, die in dem Monat aktiv sind, der den Dienst zuvor noch nie verwendet hatte.  <br/> |
|CumulativeActiveUsers  <br/> |Die Anzahl der Benutzer, die im Monat aktiv sind, sowie alle vorherigen Monate.  <br/> |
|ActiveUsers (%)  <br/> |Prozentsatz der Benutzer, gerundet auf das nächste Zehntel, aktiv im Monat im Vergleich zur Anzahl der in diesem Monat aktivierten Benutzer.  <br/> |
|MoMReturningUsers (%)  <br/> |Prozentsatz der Benutzer, gerundet auf das nächste Zehntel, aktiv in dem Monat, der im vorherigen Monat ebenfalls aktiv war, im Vergleich zur Anzahl der aktiven Benutzer.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, &amp; CumulativeActiveUsers wurden ab dem 1. Januar 2018 mit der Aufnahme von Microsoft Teams zurückgesetzt.
  
