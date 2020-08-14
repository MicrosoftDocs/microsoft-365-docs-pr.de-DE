---
title: Einstellungen für Interaktionen zwischen Microsoft 365-Gruppen und SharePoint
ms.reviewer: mmclean
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
description: Informationen zu Einstellungen für Interaktionen zwischen Microsoft 365-Gruppen und SharePoint
ms.openlocfilehash: 0c9fdd69db82985039bae03768aa0c19f514c99f
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662656"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Einstellungen für Interaktionen zwischen Microsoft 365-Gruppen und SharePoint

Einige Einstellungen für Microsoft 365-Gruppen und SharePoint in Microsoft 365, insbesondere im Zusammenhang mit der Freigabe und der Erstellung von Gruppen-und Teamwebsites, überlappen sich miteinander. Dieser Artikel enthält eine Beschreibung dieser Interaktionen und bewährten Methoden für die Verwendung dieser Einstellungen.

![Venn-Diagramm von SharePoint-, Jammer-und Gruppenfeatures](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Die Auswirkungen von SharePoint-Einstellungen in Microsoft 365-Gruppen

|SharePoint-Einstellung|Beschreibung|Auswirkung auf Microsoft 365-Gruppen|Empfehlung|
|:-----------------|:----------|:-----------------------------|:-------------|
|Externe Freigabe für Organisation und Website|Bestimmt, ob Websites, Dateien und Ordner für Personen außerhalb der Organisation freigegeben werden können.|Wenn die Einstellungen für SharePoint und Gruppen nicht übereinstimmen, können Gäste in der Gruppe möglicherweise nicht auf die Website zugreifen, oder der externe Zugriff ist möglicherweise in der Website, jedoch nicht in der Gruppe verfügbar.|Überprüfen Sie beim Ändern der Freigabeeinstellungen sowohl Gruppeneinstellungen als auch SharePoint-Websiteeinstellungen für Gruppen verbundene Teamwebsites.<br><br>Siehe [Zusammenarbeit mit Gästen in einer Website](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site).|
|Domäne zulassen/blockieren|Ermöglicht oder verhindert, dass Inhalte für bestimmte Domänen freigegeben werden.|Gruppen erkennen SharePoint-Zulassungs-oder Sperrlisten nicht. Benutzer aus Domänen, die in SharePoint nicht zugelassen sind, können über eine Gruppe auf SharePoint zugreifen.|Verwalten von zugelassenen/blockierten Domänenlisten für Azure AD und SharePoint zusammen. Erstellen Sie einen organisationsweiten Steuerungsprozess für das zulassen und Blockieren von Domänen.<br><br>Siehe [SharePoint-Domäneneinstellungen](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) und [Azure AD Domäneneinstellungen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Ausschließlich Benutzern in bestimmten Sicherheitsgruppen die externe Freigabe erlauben|Gibt Sicherheitsgruppen an, die Websites, Ordner und Dateien extern freigeben können.|Diese Einstellung wirkt sich nicht auf Gruppenbesitzer aus, die Gruppen extern freigeben. Gruppengäste haben Zugriff auf die zugehörige SharePoint-Website.||
|SharePoint-Website Freigabeeinstellungen|Bestimmt, wer die Website direkt außerhalb der Gruppenmitgliedschaft freigeben kann. Dies wird vom Gruppen-oder Websitebesitzer konfiguriert.|Diese Einstellung wirkt sich nicht direkt auf die Gruppe aus, aber Sie kann Benutzern das Hinzufügen zu einer Website und keinen Zugriff auf andere Gruppen Ressourcen gestatten.|Verwenden Sie diese Einstellung, um die Freigabe der Website direkt zu begrenzen und den Website Zugriff über die Gruppe zu verwalten.|
|Zulassen, dass Benutzer Websites von der SharePoint-Startseite und OneDrive erstellen|Gibt an, ob Benutzer neue SharePoint-Websites erstellen können.|Wenn diese Einstellung deaktiviert ist, können Benutzer weiterhin Gruppen verbundene Teamwebsites erstellen, indem Sie eine Gruppe erstellen.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>Die Auswirkungen von Microsoft 365-Gruppeneinstellung in SharePoint

|Microsoft 365 Gruppeneinstellung|Beschreibung|Auswirkung auf SharePoint|Empfehlung|
|:---------------------------|:----------|:-------------------|:-------------|
|Benennungsrichtlinien|Gibt Gruppennamen Präfixe und Suffixe sowie blockierte Wörter für die Gruppenerstellung an.|Richtlinien werden für Benutzer erzwungen, die Gruppen verbundene Teamwebsites erstellen, jedoch keine Kommunikationswebsites oder-Websites mit anderen Vorlagen.|Erstellen Sie bei Bedarf separate Benennungs Anleitungen für Kommunikationswebsites.|
|Gruppengastzugriff|Gibt an, ob Personen außerhalb der Organisation Gruppen hinzugefügt werden können.|Wenn die Einstellungen für SharePoint und Gruppen nicht übereinstimmen, können Gäste in der Gruppe möglicherweise nicht auf die Website zugreifen, oder der externe Zugriff ist möglicherweise in der Website, jedoch nicht in der Gruppe verfügbar.|Überprüfen Sie beim Ändern der Freigabeeinstellungen sowohl Gruppeneinstellungen als auch SharePoint-Websiteeinstellungen für Gruppen verbundene Teamwebsites.<br><br>Siehe [Zusammenarbeit mit Gästen in einer Website](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)|
|Gruppenerstellung nach Sicherheitsgruppe|Gruppen können nur von Mitgliedern einer bestimmten Sicherheitsgruppe erstellt werden.|Benutzer, die keine Mitglieder der Sicherheitsgruppe sind, können keine Gruppen verbundene Teamwebsite erstellen.|Stellen Sie sicher, dass Ihr Prozess zum Anfordern einer Gruppe Anweisungen zum Anfordern einer Website enthält.|
|Gruppenablaufrichtlinie|Gibt einen Zeitraum an, nach dem Gruppen, die nicht aktiv verwendet werden, automatisch gelöscht werden.|Wenn die Gruppe gelöscht wird, wird die zugehörige SharePoint-Website ebenfalls gelöscht. Durch Aufbewahrungsrichtlinien geschützte Inhalte werden beibehalten.|Verwenden Sie Ablaufrichtlinien, um eine Ausdehnung nicht verwendeter Gruppen und Websites zu vermeiden.|

## <a name="related-topics"></a>Verwandte Themen

[Zusammenarbeit mit Personen außerhalb Ihrer Organisation](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Verwalten der Websiteerstellung in SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)