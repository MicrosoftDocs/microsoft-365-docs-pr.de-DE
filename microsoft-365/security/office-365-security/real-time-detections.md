---
title: Grundlagen von Bedrohungs-Explorer und Echtzeiterkennungen in Microsoft Defender für Office 365
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
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083188"
---
# <a name="explorer-and-real-time-detections-basics"></a>Grundlagen der Explorer- und Echtzeiterkennung

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Inhalt dieses Artikels:

- [Unterschiede zwischen Explorer- und Echtzeiterkennungen](#differences-between-explorer-and-real-time-detections)
- [Erforderliche Lizenzen und Berechtigungen](#required-licenses-and-permissions)

> [!NOTE]
> Dies ist Teil einer **Drei-Artikel-Reihe** zu **Explorer (auch bekannt als Bedrohungs-Explorer),** **E-Mail-Sicherheit** und **Explorer- und Echtzeiterkennungsgrundlagen** (z. B. Unterschiede zwischen den Tools und berechtigungen, die zum Betrieb erforderlich sind). Die beiden anderen Artikel dieser Reihe sind [die Bedrohungssuche im Explorer](threat-hunting-in-threat-explorer.md) und die [E-Mail-Sicherheit mit Explorer.](email-security-in-microsoft-defender.md)

In diesem Artikel wird der Unterschied zwischen Explorer- und Echtzeiterkennungsberichten sowie den erforderlichen Lizenzen und Berechtigungen erläutert.

Wenn Ihre Organisation [über Microsoft Defender für Office 365](defender-for-office-365.md)verfügt und Sie über die [Berechtigungen](#required-licenses-and-permissions)verfügen, können Sie **Explorer** (auch als **Bedrohungs-Explorer** bezeichnet) oder **Echtzeiterkennungen** verwenden, um Bedrohungen zu erkennen und zu beheben.

Wechseln Sie im Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ) zu **E-Mail & Zusammenarbeit,** und wählen Sie dann **Explorer-** _oder_ **Echtzeiterkennungen aus.**

Mit diesen Tools können Sie folgende Aktionen ausführen:

- Sehen Sie sich Schadsoftware an, die von Microsoft 365 Sicherheitsfeatures erkannt wurde.
- Zeigen Sie die Phishing-URL an, und klicken Sie auf Bewertungsdaten.
- Starten Sie einen automatisierten Untersuchungs- und Reaktionsprozess aus einer Ansicht im Explorer.
- Untersuchen Sie schädliche E-Mails und vieles mehr.

Weitere Informationen finden Sie unter [E-Mail-Sicherheit mit Explorer](email-security-in-microsoft-defender.md).

## <a name="differences-between-explorer-and-real-time-detections"></a>Unterschiede zwischen Explorer- und Echtzeiterkennungen

- *Echtzeiterkennungen* sind ein Berichterstellungstool, das in Defender für Office 365 Plan 1 verfügbar ist. *Der Bedrohungs-Explorer* ist ein Tool zur Bedrohungssuche und -behebung, das in Defender für Office 365 Plan 2 verfügbar ist.
- Mit dem Bericht über Echtzeiterkennungen können Sie Erkennungen in Echtzeit anzeigen. Der Bedrohungs-Explorer tut dies auch, bietet jedoch zusätzliche Details für einen bestimmten Angriff, z. B. das Hervorheben von Angriffskampagnen, und bietet Sicherheitsteams die Möglichkeit, Bedrohungen zu beheben (einschließlich des Auslösens einer [automatisierten Untersuchung und Reaktionsuntersuchung).](automated-investigation-response-office.md)
- Eine *Ansicht "Alle E-Mails"* ist im Bedrohungs-Explorer verfügbar, aber nicht im Bericht über Echtzeiterkennungen enthalten.
- Umfangreiche Filterfunktionen und Korrekturaktionen sind im Bedrohungs-Explorer enthalten. Weitere Informationen finden Sie unter [Microsoft Defender für Office 365 Dienstbeschreibung: Funktionsverfügbarkeit in Defender für Office 365-Plänen.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

## <a name="required-licenses-and-permissions"></a>Erforderliche Lizenzen und Berechtigungen

Sie benötigen [Microsoft Defender,](defender-for-office-365.md) damit Office 365 explorer- oder Echtzeiterkennungen verwenden können:

- Explorer ist nur in Defender für Office 365 Plan 2 enthalten.
- Der Bericht über Echtzeiterkennungen ist in Defender für Office 365 Plan 1 enthalten.

Sicherheitsteams müssen Lizenzen für alle Benutzer zuweisen, die von Defender für Office 365 geschützt werden sollen, und beachten, dass Explorer- und Echtzeiterkennungen Erkennungsdaten für lizenzierte Benutzer anzeigen.

Zum Anzeigen und Verwenden von Explorer- *oder* Echtzeiterkennungen benötigen Sie die folgenden Berechtigungen:

- In Defender für Office 365:
  - Organisationsverwaltung
  - Sicherheitsadministrator (kann im Azure Active Directory Admin Center ( ) zugewiesen werden. <https://aad.portal.azure.com>
  - Sicherheitsleseberechtigter
- In Exchange Online:
  - Organisationsverwaltung
  - Organisationsverwaltung – nur Leserechte
  - Schreibgeschützte Empfänger
  - Complianceverwaltung

Weitere Informationen zu Rollen und Berechtigungen finden Sie in den folgenden Artikeln:

- [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md)
- [Berechtigungen in Exchange Online](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a>Weitere Informationen

- [Bedrohungs-Explorer sammelt E-Mail-Details auf der E-Mail-Entitätsseite](mdo-email-entity-page.md)
- [Suchen und Untersuchen von bösartigen E-Mails, die zugestellt wurden](investigate-malicious-email-that-was-delivered.md)
- [Anzeigen schädlicher Dateien, die in SharePoint Online, OneDrive und Microsoft Teams erkannt wurden](mdo-for-spo-odb-and-teams.md)
- [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report)
- [Automatische Untersuchung und Reaktion in Microsoft Threat Protection](automated-investigation-response-office.md)
