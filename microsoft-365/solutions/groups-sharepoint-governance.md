---
title: Einstellungsinteraktionen zwischen Microsoft 365-Gruppen und SharePoint
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
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Informationen zu Einstellungeninteraktionen zwischen Microsoft 365-Gruppen und SharePoint
ms.openlocfilehash: e1aeaca792fb551de503bd4c68256ccf14f45022
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921036"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Einstellungsinteraktionen zwischen Microsoft 365-Gruppen und SharePoint

Einige Einstellungen für Microsoft 365-Gruppen und SharePoint in Microsoft 365, insbesondere im Zusammenhang mit freigabe- und gruppen- und teamwebsiteerstellung, überlappen sich miteinander. Dieser Artikel enthält Beschreibungen dieser Interaktionen und bewährte Methoden für die Verwendung dieser Einstellungen.

![Venn-Diagramm von SharePoint-, Yammer- und Gruppenfeatures](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Auswirkungen von SharePoint-Einstellungen auf Microsoft 365-Gruppen

|SharePoint-Einstellung|Beschreibung|Auswirkungen auf Microsoft 365-Gruppen|Empfehlung|
|:-----------------|:----------|:-----------------------------|:-------------|
|Externe Freigabe für Organisation und Website|Bestimmt, ob Websites, Dateien und Ordner für Personen außerhalb der Organisation freigegeben werden können.|Wenn die Einstellungen für SharePoint und Gruppen nicht übereinstimmen, können Gäste in der Gruppe nicht auf die Website zugreifen, oder der externe Zugriff ist möglicherweise auf der Website, aber nicht in der Gruppe verfügbar.|Überprüfen Sie beim Ändern von Freigabeeinstellungen sowohl Gruppeneinstellungen als auch SharePoint-Websiteeinstellungen für gruppenverkn nnte Teamwebsites.<br><br>Weitere [Informationen finden Sie unter Zusammenarbeiten mit Gästen auf einer Website](./collaborate-in-site.md).|
|Domänen zulassen/blockieren|Ermöglicht oder verhindert, dass Inhalte für angegebene Domänen freigegeben werden.|Gruppen erkennen keine Von SharePoint zulässigen oder blockierten Listen. Benutzer von Domänen, die in SharePoint nicht zulässig sind, können über eine Gruppe Zugriff auf SharePoint erhalten.|Verwalten von Zulässig/Blockieren von Domänenlisten für Azure AD und SharePoint zusammen. Erstellen Sie einen organisationsweiten Steuerungsprozess zum Zulassen und Blockieren von Domänen.<br><br>Siehe [SharePoint-Domäneneinstellungen](/sharepoint/restricted-domains-sharing) und [Azure AD-Domäneneinstellungen](/azure/active-directory/b2b/allow-deny-list)|
|Ausschließlich Benutzern in bestimmten Sicherheitsgruppen die externe Freigabe erlauben|Gibt Sicherheitsgruppen an, die Websites, Ordner und Dateien extern freigeben können.|Diese Einstellung wirkt sich nicht auf die externe Freigabe von Gruppen durch Gruppenbesitzer aus. Gruppengäste haben Zugriff auf die zugeordnete SharePoint-Website.||
|Einstellungen für die Freigabe von SharePoint-Website|Bestimmt, wer die Website direkt außerhalb der Gruppenmitgliedschaft freigeben kann. Dies wird vom Gruppen- oder Websitebesitzer konfiguriert.|Diese Einstellung wirkt sich nicht direkt auf die Gruppe aus, kann jedoch zulassen, dass Benutzer einer Website hinzugefügt werden und keinen Zugriff auf andere Gruppenressourcen haben.|Erwägen Sie die Verwendung dieser Einstellung, um die Freigabe der Website direkt zu beschränken und den Websitezugriff über die Gruppe zu verwalten.|
|Benutzern das Erstellen von Websites über die #A0 und OneDrive ermöglichen|Gibt an, ob Benutzer neue SharePoint-Websites erstellen können.|Wenn diese Einstellung deaktiviert ist, können Benutzer weiterhin gruppenverkn nnte Teamwebsites erstellen, indem sie eine Gruppe erstellen.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>Die Auswirkungen der Microsoft 365-Gruppeneinstellung auf SharePoint

|Microsoft 365-Gruppeneinstellung|Beschreibung|Auswirkungen auf SharePoint|Empfehlung|
|:---------------------------|:----------|:-------------------|:-------------|
|Benennungsrichtlinien|Gibt Präfixe und Suffixe für Gruppennamen und blockierte Wörter für die Gruppenerstellung an.|Richtlinien werden für Benutzer erzwungen, die gruppenvermittelte Teamwebsites erstellen, aber keine Kommunikationswebsites oder Websites mit anderen Vorlagen.|Erstellen Sie bei Bedarf separate Benennungsleitfäden für Kommunikationswebsites.|
|Gruppengastzugriff|Gibt an, ob Personen außerhalb der Organisation Gruppen hinzugefügt werden können.|Wenn die Einstellungen für SharePoint und Gruppen nicht übereinstimmen, können Gäste in der Gruppe nicht auf die Website zugreifen, oder der externe Zugriff ist möglicherweise auf der Website, aber nicht in der Gruppe verfügbar.|Überprüfen Sie beim Ändern von Freigabeeinstellungen sowohl Gruppeneinstellungen als auch SharePoint-Websiteeinstellungen für gruppenverkn nnte Teamwebsites.<br><br>Siehe [Zusammenarbeit mit Gästen auf einer Website](./collaborate-in-site.md)|
|Gruppenerstellung nach Sicherheitsgruppe|Gruppen können nur von Mitgliedern einer bestimmten Sicherheitsgruppe erstellt werden.|Benutzer, die nicht Mitglied der Sicherheitsgruppe sind, können keine mit einer Gruppe verbundene Teamwebsite erstellen.|Stellen Sie sicher, dass Ihr Prozess zum Anfordern einer Gruppe Anweisungen zum Anfordern einer Website enthält.|
|Gruppenablaufrichtlinie|Gibt einen Zeitraum an, nach dem nicht aktiv verwendete Gruppen automatisch gelöscht werden.|Wenn die Gruppe gelöscht wird, wird auch die zugeordnete SharePoint-Website gelöscht. Durch Aufbewahrungsrichtlinien geschützte Inhalte werden beibehalten.|Verwenden Sie Ablaufrichtlinien, um nicht verwendete Gruppen und Websites zu vermeiden.|

## <a name="related-topics"></a>Verwandte Themen

[Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Plans für die Zusammenarbeitsgovernance](collaboration-governance-first.md)

[Zusammenarbeit mit Personen außerhalb Ihrer Organisation](./collaborate-with-people-outside-your-organization.md)

[Verwalten der Websiteerstellung in SharePoint](/sharepoint/manage-site-creation)