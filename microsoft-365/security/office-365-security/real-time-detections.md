---
title: Grundlagen für den Bedrohungs-Explorer und die Echtzeiterkennung in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Verwenden Sie Explorer- oder Echtzeiterkennungen, um Bedrohungen effizient zu untersuchen und darauf zu reagieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300155"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a>Sicherheitsrisiken-Explorer und Grundlagen der Echtzeit-Erkennung

Inhalt dieses Artikels:

- [Unterschiede zwischen Bedrohungs-Explorer und Echtzeiterkennung](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [Erforderliche Lizenzen und Berechtigungen](#required-licenses-and-permissions)

> [!NOTE]
> Dies ist Teil einer **3-Artikel-Reihe** über Threat **Explorer (Explorer),** **E-Mail-Sicherheit** **und** Explorer- und Echtzeiterkennungsgrund grundlagen (z. B. Unterschiede zwischen den Tools und Berechtigungen, die für deren Betrieb erforderlich sind). Die anderen beiden Artikel in dieser Reihe sind Die [Bedrohungssuche im Bedrohungs-Explorer](threat-hunting-in-threat-explorer.md) und [E-Mail-Sicherheit mit Dem Bedrohungs-Explorer](email-security-in-microsoft-defender.md).

In diesem Artikel wird der Unterschied zwischen bedrohungserkundungs- und Echtzeiterkennungsberichten sowie den erforderlichen Lizenzen und Berechtigungen erläutert.

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Wenn Ihre Organisation [Über Microsoft Defender für Office 365](defender-for-office-365.md)verfügt und Sie über die Berechtigungen [verfügen,](#required-licenses-and-permissions)können Sie den Bedrohungs-Explorer (explorer **genannt)** oder **Echtzeiterkennungen** verwenden, um Bedrohungen zu erkennen und zu abwehren. 

Wechseln Sie im **Security & Compliance Center** zu Bedrohungsverwaltung, und wählen Sie dann **Explorer-**  oder **Echtzeiterkennungen aus.** 

<br>

****

|Mit Microsoft Defender für Office 365 Plan 2 sehen Sie:|Mit Microsoft Defender für Office 365 Plan 1 sehen Sie:|
|---|---|
|![Bedrohungs-Explorer](../../media/threatmgmt-explorer.png)|![Echtzeiterkennungen](../../media/threatmgmt-realtimedetections.png)|
|

Mit diesen Tools können Sie folgende Aktionen ausführen:

- Siehe Schadsoftware, die von Microsoft 365-Sicherheitsfeatures erkannt wird.
- Zeigen Sie die Phishing-URL an, und klicken Sie auf Diktierdaten.
- Starten Sie einen automatisierten Untersuchungs- und Reaktionsprozess aus einer Ansicht im Explorer.
- Untersuchen Sie bösartige E-Mails und vieles mehr.

Weitere Informationen finden Sie unter [E-Mail-Sicherheit mit Dem Bedrohungs-Explorer](email-security-in-microsoft-defender.md).

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>Unterschiede zwischen Bedrohungs-Explorer und Echtzeiterkennung

- *Echtzeiterkennung ist ein Berichterstellungstool,* das in Defender für Office 365 Plan 1 verfügbar ist. *Threat Explorer* ist ein Tool zur Bedrohungssuche und -behebung, das in Defender for Office 365 Plan 2 verfügbar ist.
- Mit dem Bericht über Echtzeiterkennungen können Sie Erkennungen in Echtzeit anzeigen. Der Bedrohungs-Explorer führt dies ebenfalls aus, bietet jedoch zusätzliche Details für einen bestimmten Angriff, z. B. das [](automated-investigation-response-office.md)Hervorheben von Angriffskampagnen, und bietet Sicherheitsteams die Möglichkeit, Bedrohungen zu be behebung (einschließlich auslösen einer automatisierten Untersuchung und Reaktionsuntersuchung).
- Eine *Alle-E-Mail-Ansicht* ist im Bedrohungs-Explorer verfügbar, aber nicht im Bericht über Echtzeiterkennungen enthalten.
- Umfangreiche Filterfunktionen und Korrekturaktionen sind im Bedrohungs-Explorer enthalten. Weitere Informationen finden Sie unter [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="required-licenses-and-permissions"></a>Erforderliche Lizenzen und Berechtigungen

Sie müssen [über Microsoft Defender für Office 365 verfügen,](defender-for-office-365.md) um Explorer- oder Echtzeiterkennungen verwenden zu können:

- Explorer ist jedoch nur in Defender for Office 365 Plan 2 enthalten.
- Der Bericht über Echtzeiterkennungen ist in Defender for Office 365 Plan 1 enthalten.

Security Operations Teams müssen lizenzen für alle Benutzer zuweisen, die von Defender for Office 365 geschützt werden sollten, und beachten Sie, dass Explorer- und Echtzeiterkennungen Erkennungsdaten für lizenzierte Benutzer anzeigen.

Zum Anzeigen und Verwenden von *Explorer- oder* Echtzeiterkennungen müssen Sie über Folgendes verfügen:

- Für das Security & Compliance Center:

  - Organisationsverwaltung
  - Sicherheitsadministrator (dies kann im Azure Active Directory Admin Center zugewiesen werden ( <https://aad.portal.azure.com> )
  - Sicherheitsleseberechtigter

- Für Exchange Online:

  - Organisationsverwaltung
  - Organisationsverwaltung – nur Leserechte
  - Schreibgeschützte Empfänger
  - Verwaltung der Richtlinientreue

Weitere Informationen zu Rollen und Berechtigungen finden Sie in den folgenden Ressourcen:

- [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)
- [Featureberechtigungen in Exchange Online](/exchange/permissions-exo/feature-permissions)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a>Weitere Informationen
- [Threat Explorer sammelt E-Mail-Details auf der E-Mail-Entitätsseite](mdo-email-entity-page.md)
- [Suchen und Untersuchen von bösartigen E-Mails, die zugestellt wurden](investigate-malicious-email-that-was-delivered.md)
- [Anzeigen schädlicher Dateien in SharePoint Online, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report)
- [Automatische Untersuchung und Reaktion in Microsoft Threat Protection](automated-investigation-response-office.md)