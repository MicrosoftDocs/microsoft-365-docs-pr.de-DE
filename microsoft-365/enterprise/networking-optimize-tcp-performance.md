---
title: 'Schritt 5: Optimieren der Leistung des Clients und des Office 365-Diensts'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Konfigurieren von TCP-Einstellungen und Office 365-Diensten für eine bessere Leistung.
ms.openlocfilehash: e3aefb417330ab791a3dd217e2e34591eba3e1d1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066541"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>Schritt 5: Optimieren der Leistung des Clients und des Office 365-Diensts

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![Phase 1 – Netzwerken](../media/deploy-foundation-infrastructure/networking_icon-small.png)

Sie können die Leistung durch die Optimierung der Art und Weise, wie TCP (Transmission Control-Protokoll) zwischen Clientgeräten und Office 365-Diensten funktioniert, erhöhen.

Für Clientgeräte können Sie die folgenden TCP-Einstellungen auf Clientgeräten zum Optimieren der Leistung von TCP ändern:

- [TCP-Fensterskalierung](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), damit Ihr Clientgerät mehr Daten senden kann, bevor eine Bestätigung angefordert wird.
- [TCP-Leerlaufzeit](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), damit Ihr Clientgerät offene Verbindungen effizienter verwalten kann.
- [Maximale TCP-Segmentgröße](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), damit Ihr Clientgerät die größten Datenblöcke in einem Paket senden kann.
- [Selektive TCP-Empfangsbestätigungen](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), damit Ihr Clientgerät empfangene Daten effizienter bestätigen kann.

Für Office 365-Dienste finden Sie hier weitere Informationsquellen zum Optimieren der Leistung:

- [Exchange Online](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [Skype for Business Online](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [SharePoint Online](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [Project Web App in Project Online](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

Als Zwischenprüfung können Sie die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step5) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

[Beendigungskriterien für die Netzwerkinfrastruktur](networking-exit-criteria.md)
