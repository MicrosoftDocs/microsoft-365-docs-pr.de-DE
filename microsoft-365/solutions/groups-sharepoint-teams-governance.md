---
title: 'Einstellungen: Interaktionen zwischen Microsoft 365-Gruppen, Teams und SharePoint'
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Informationen zu Einstellungen für Interaktionen zwischen Microsoft 365-Gruppen, Teams und SharePoint
ms.openlocfilehash: 3ad5011c2d7b4579e054b014237d5771049b3c91
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662655"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Einstellungen: Interaktionen zwischen Microsoft 365-Gruppen, Teams und SharePoint

Einige Einstellungen für Microsoft 365-Gruppen, Microsoft Teams und SharePoint in Microsoft 365, insbesondere im Zusammenhang mit Freigabe und Gruppen-, Team-und SharePoint-Websiteerstellung, überlappen sich miteinander. Dieser Artikel enthält eine Beschreibung dieser Interaktionen und bewährten Methoden für die Verwendung dieser Einstellungen.

![Venn-Diagramm von SharePoint-, Teams-und Gruppenfeatures](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>Auswirkungen von SharePoint-Einstellungen in Gruppen und Teams

|SharePoint-Einstellung|Beschreibung|Auswirkungen auf Microsoft 365-Gruppen und-Teams|Empfehlung|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Externe Freigabe für Organisation und Website|Bestimmt, ob Websites, Dateien und Ordner für Personen außerhalb der Organisation freigegeben werden können.|Wenn die Einstellungen für SharePoint, Gruppen und Teams nicht übereinstimmen, können Gäste im Team möglicherweise den Zugriff auf die Website sperren, oder es kann ein unerwarteter externer Zugriff auftreten.|Überprüfen Sie beim Ändern der Freigabeeinstellungen Gruppeneinstellungen, Teams-Einstellungen und SharePoint-Websiteeinstellungen für Gruppen verbundene Teamwebsites.<br><br> Siehe [Zusammenarbeit mit Gästen in einem Team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|Domäne zulassen/blockieren|Ermöglicht oder verhindert, dass Inhalte für bestimmte Domänen freigegeben werden.|Gruppen und Teams erkennen SharePoint-Zulassungs-oder Sperrlisten nicht. Benutzer aus Domänen, die in SharePoint nicht zugelassen sind, können über ein Team auf SharePoint-Websites oder-Inhalte zugreifen.|Verwalten von zugelassenen/blockierten Domänenlisten für Azure AD und SharePoint zusammen. Erstellen Sie einen organisationsweiten Steuerungsprozess für das zulassen und Blockieren von Domänen.<br><br>Siehe [SharePoint-Domäneneinstellungen](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) und [Azure AD Domäneneinstellungen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Ausschließlich Benutzern in bestimmten Sicherheitsgruppen die externe Freigabe erlauben|Gibt Sicherheitsgruppen an, die SharePoint-Websites,-Ordner und-Dateien extern freigeben können.|Diese Einstellung hindert Teambesitzer nicht daran, Teams extern freizugeben. Team Gäste haben Zugriff auf die zugehörige SharePoint-Website.||
|SharePoint-Website Freigabeeinstellungen|Bestimmt, wer die Website direkt außerhalb der Teammitgliedschaft freigeben kann. Dies wird vom Team-oder Websitebesitzer konfiguriert.|Diese Einstellung wirkt sich nicht direkt auf das Team aus, Sie kann jedoch Benutzern das Hinzufügen zu einer Website ermöglichen und keinen Zugriff auf das Team selbst oder auf Ressourcen anderer Teams haben.|Verwenden Sie diese Einstellung, um die Freigabe der Website direkt zu begrenzen und den Website Zugriff über das Team zu verwalten.|
|Zulassen, dass Benutzer Websites von der SharePoint-Startseite und OneDrive erstellen|Gibt an, ob Benutzer neue SharePoint-Websites erstellen können.|Wenn diese Einstellung deaktiviert ist, können Benutzer weiterhin Gruppen verbundene Teamwebsites erstellen, indem Sie ein Team erstellen.||

## <a name="the-effects-of-groups-settings-on-teams"></a>Auswirkungen von Gruppeneinstellungen in Microsoft Teams

|Microsoft 365 Gruppeneinstellung|Beschreibung|Auswirkung auf Teams|Empfehlung|
|:---------------------------|:----------|:--------------|:-------------|
|Benennungsrichtlinien|Gibt Gruppennamen Präfixe und Suffixe sowie blockierte Wörter für die Gruppenerstellung an.|Richtlinien werden für Benutzer erzwungen, die Teams erstellen.||
|Gruppengastzugriff|Gibt an, ob Personen außerhalb der Organisation Gruppen hinzugefügt werden können.|Wenn die Gast Freigabeeinstellungen für Gruppen oder Teams deaktiviert sind, kann das Team nicht für Gäste freigegeben werden.|Wenn Sie die Einstellungen für die Gast Freigabe ändern, überprüfen Sie die Einstellungen für Teams, Gruppen und die SharePoint-Website, die dem Team zugeordnet ist.<br><br> Siehe [Zusammenarbeit mit Gästen in einem Team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|Gruppenerstellung nach Sicherheitsgruppe|Gruppen können nur von Mitgliedern einer bestimmten Sicherheitsgruppe erstellt werden.|Benutzer, die keine Mitglieder der Sicherheitsgruppe sind, können kein Team erstellen.|Stellen Sie sicher, dass Ihr Prozess zum Anfordern einer Gruppe Anweisungen zum Anfordern eines Teams oder einer SharePoint-Website enthält.|
|Gruppenablaufrichtlinie|Gibt einen Zeitraum an, nach dem Gruppen, die nicht aktiv verwendet werden, automatisch gelöscht werden.|Wenn die Gruppe gelöscht wird, werden das Team und die zugehörige SharePoint-Website ebenfalls gelöscht. Durch Aufbewahrungsrichtlinien geschützte Inhalte werden beibehalten.|Verwenden Sie Ablaufrichtlinien, um eine Ausdehnung nicht verwendeter Teams, Gruppen und Websites zu vermeiden.|

## <a name="related-topics"></a>Verwandte Themen

[Zusammenarbeit mit Personen außerhalb Ihrer Organisation](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Verwalten der Websiteerstellung in SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)
