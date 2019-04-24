---
title: 'Schritt 5: Optimieren der Leistung des Clients und des Office 365-Diensts'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Konfigurieren von TCP-Einstellungen und Office 365-Diensten für eine bessere Leistung.
ms.openlocfilehash: cf172bcaa87b7c69d33d349d18c449efff30a1d9
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290882"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>Schritt 5: Optimieren der Leistung des Clients und des Office 365-Diensts

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Sie können die Leistung durch die Optimierung der Art und Weise, wie TCP (Transmission Control-Protokoll) zwischen Clientgeräten und Office 365-Diensten funktioniert, erhöhen.

Für Clientgeräte können Sie die folgenden TCP-Einstellungen auf Clientgeräten zum Optimieren der Leistung von TCP ändern:

- [TCP-Fensterskalierung](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), damit Ihr Clientgerät mehr Daten senden kann, bevor eine Bestätigung angefordert wird.
- [TCP-Leerlaufzeit](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), damit Ihr Clientgerät offene Verbindungen effizienter verwalten kann.
- [Maximale TCP-Segmentgröße](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), damit Ihr Clientgerät die größten Datenblöcke in einem Paket senden kann.
- [Selektive TCP-Empfangsbestätigungen](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), damit Ihr Clientgerät empfangene Daten effizienter bestätigen kann.

Für Office 365-Dienste finden Sie hier weitere Informationsquellen zum Optimieren der Leistung:

- [Exchange Online](https://support.office.com/article/Tune-Exchange-Online-performance-026e83cb-a945-4543-97b0-a8af6e80ac61)
- [Skype for Business Online](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802)
- [SharePoint Online](https://support.office.com/article/Tune-SharePoint-Online-performance-f0522d4a-fbf4-41f9-854e-c9b59555091d)
- [Project Online](https://support.office.com/article/Tune-Project-Online-performance-12ba0ebd-c616-42e5-b9b6-cad570e8409c)

Als Zwischenprüfung können Sie die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step5) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

[Beendigungskriterien für die Netzwerkinfrastruktur](networking-exit-criteria.md)
