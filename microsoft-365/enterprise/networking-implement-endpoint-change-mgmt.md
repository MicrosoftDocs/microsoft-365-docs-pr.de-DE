---
title: 'Schritt 4: Planen von URL- und IP-Adressänderungen'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: 626d0e242c549fb16880710bbca31db0bdee9029
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291324"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a>Schritt 4: Planen von URL- und IP-Adressänderungen

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
>Dieser Schritt erfordert [Schritt 3](networking-configure-proxies-firewalls.md). Wenn Sie Schritt 3 nicht durchgeführt haben, können Sie mit [Schritt 5](networking-optimize-tcp-performance.md) fortfahren.
>

Die URLs und IP-Adressen, die vom globalen Microsoft 365-Netzwerk verwendet werden, ändern sich im Laufe der Zeit. Daher ist es wichtig, Updates an diesen Endpunkten zu planen. Möglicherweise müssen Sie Ihre Sicherheitsperimetergeräte neu konfigurieren mit:

- Neue URLs für neue Dienste, die ungehinderte Verarbeitung erfordern
- URLs für nicht mehr unterstützte Dienste entfernt
- Neue IP-Adressbereiche für neue Microsoft-Netzwerkspeicherorte und -Server im Internet 
- Änderungen an IP-Adressbereichen für die unterschiedlichen Dienste

Weitere Informationen zum Einrichten eines Implementierungsplans für Änderungen an Endpunkten, einschließlich Benachrichtigung über Änderungen, finden Sie unter [Verwalten von Office 365-Endpunkten-Integration](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) und [Verwalten von Office 365 Endpunkten-Proxys](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).

Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step4) für diesen Schritt ansehen.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[Optimieren der Leistung des Clients und des Office 365-Diensts](networking-optimize-tcp-performance.md)|
