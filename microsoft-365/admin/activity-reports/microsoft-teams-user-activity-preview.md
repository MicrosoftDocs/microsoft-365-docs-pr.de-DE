---
title: Microsoft 365-Berichte im Admin Center-Microsoft Teams-Benutzeraktivität – Vorschau
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie den Microsoft Teams-Benutzer Aktivitätsbericht abrufen und Einblicke in die Teams-Aktivitäten in Ihrer Organisation erhalten.
ms.openlocfilehash: 734a4dfd62160c2f4d29b8faffb3268a1962fe4f
ms.sourcegitcommit: a50260b7c5be7374e8e2bea19cc08406ef51ac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "45167341"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity--preview"></a>Microsoft 365-Berichte im Admin Center-Microsoft Teams-Benutzeraktivität – Vorschau

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an. Der Bericht "Microsoft Teams-Benutzeraktivität" bietet Ihnen Einblicke in die Microsoft Teams-Aktivitäten in Ihrer Organisation.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.  
 
## <a name="how-to-get-to-the-preview-microsoft-teams-user-activity-report"></a>So gelangen Sie zum Bericht "Microsoft Teams-Benutzeraktivität" in der Vorschau

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.
2. Wählen Sie in der Dropdownliste **Bericht auswählen** die Option **Microsoft Teams**aus.
  
## <a name="interpret-the-preview-microsoft-teams-user-activity-report"></a>Interpretieren des Berichts "Microsoft Teams-Benutzeraktivität Vorschau"

Sie können die Benutzeraktivität im Bericht "Vorschau Teams" anzeigen, indem Sie die Registerkarte **Benutzeraktivität** auswählen.
  
|||
|:-----|:-----|
|**Metrik**|**Definition**|
|Benutzername  <br/> |Die E-Mail-Adresse des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonymisieren.   <br/> |
|Kanal Nachrichten   <br/> |Die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamchat gepostet hat.  <br/> |
|Chat Nachrichten   <br/> |Die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem privaten Chat gepostet hat.  <br/> |
|Besprechungen insgesamt   <br/> |Die Anzahl der Onlinebesprechungen, an denen der Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|1:1 Anrufe   <br/> | Die Anzahl der 1:1 Anrufe, an denen der Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|Datum der letzten Aktivität (UTC)  <br/> |Das letzte Datum, an dem der Benutzer an einer Microsoft Teams-Aktivität teilgenommen hat.<br/> |
|Teilnahme an Adhoc-Besprechungen   <br/> | Die Anzahl der Besprechungen, die im Kalender nicht geplant sind, an denen der Benutzer während des angegebenen Zeitraums teilgenommen hat.  <br/> |
|Organisierte Meetings Adhoc <br/> |Die Anzahl der Besprechungen, die im Kalender nicht geplant sind, die der Benutzer während des angegebenen Zeitraums organisiert hat. <br/>|
|Geplant organisierte Besprechungen  <br/> |Die Anzahl geplanter Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.  <br/> |
|Lizenziert |Ausgewählt, wenn der Benutzer für die Verwendung von Microsoft Teams lizenziert ist.|
|Andere Aktivität|Der Benutzer wird als aktiv betrachtet, hat aber einen Nullwert für die Chat Nachrichten, 1:1 Anrufe, Kanal Nachrichten, Gesamt Besprechungen und Besprechungen organisiert. Beispiele für Aktionen sind, wenn der Microsoft Teams-Client im Vordergrund aktiviert wird, Aktionen im Bereich zum Verfassen von Nachrichten ausgeführt wurden, Popups im Microsoft Teams-Client, Banner im Microsoft Teams-Client usw. angezeigt wurden. |
|||