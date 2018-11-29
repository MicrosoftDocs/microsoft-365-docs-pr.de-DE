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
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: 44990dcfd09e5cc2a44666da43fdeeaffd59da7d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867549"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a><span data-ttu-id="a730d-102">Schritt 4: Planen von URL- und IP-Adressänderungen</span><span class="sxs-lookup"><span data-stu-id="a730d-102">Step 4: Plan for URL and IP address changes</span></span>

<span data-ttu-id="a730d-103">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a730d-103">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
><span data-ttu-id="a730d-p101">Dieser Schritt erfordert [Schritt 3](networking-configure-proxies-firewalls.md). Wenn Sie Schritt 3 nicht durchgeführt haben, können Sie mit [Schritt 5](networking-optimize-tcp-performance.md) fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a730d-p101">This step requires [Step 3](networking-configure-proxies-firewalls.md). If you have not done Step 3, you can skip to [Step 5](networking-optimize-tcp-performance.md).</span></span>
>

<span data-ttu-id="a730d-p102">Die URLs und IP-Adressen, die vom globalen Microsoft 365-Netzwerk verwendet werden, ändern sich im Laufe der Zeit. Daher ist es wichtig, Updates an diesen Endpunkten zu planen. Möglicherweise müssen Sie Ihre Sicherheitsperimetergeräte neu konfigurieren mit:</span><span class="sxs-lookup"><span data-stu-id="a730d-p102">The URLs and IP addresses used by the global Microsoft 365 network change over time, so it’s important to plan for updates to these endpoints. For example, you may need to reconfigure your security perimeter devices with:</span></span>

- <span data-ttu-id="a730d-108">Neue URLs für neue Dienste, die ungehinderte Verarbeitung erfordern</span><span class="sxs-lookup"><span data-stu-id="a730d-108">New URLs for new services that will need unhindered processing</span></span>
- <span data-ttu-id="a730d-109">URLs für nicht mehr unterstützte Dienste entfernt</span><span class="sxs-lookup"><span data-stu-id="a730d-109">Removed URLs for discontinued services</span></span>
- <span data-ttu-id="a730d-110">Neue IP-Adressbereiche für neue Microsoft-Netzwerkspeicherorte und -Server im Internet</span><span class="sxs-lookup"><span data-stu-id="a730d-110">New IP address ranges for new Microsoft network locations and servers on the Internet</span></span> 
- <span data-ttu-id="a730d-111">Änderungen an IP-Adressbereichen für die unterschiedlichen Dienste</span><span class="sxs-lookup"><span data-stu-id="a730d-111">Changes in IP address ranges for the different services</span></span>

<span data-ttu-id="a730d-112">Weitere Informationen zum Einrichten eines Implementierungsplans für Änderungen an Endpunkten, einschließlich Benachrichtigung über Änderungen, finden Sie unter [Verwalten von Office 365-Endpunkten-Integration](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) und [Verwalten von Office 365 Endpunkten-Proxys](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span><span class="sxs-lookup"><span data-stu-id="a730d-112">For more information about establishing an implementation plan for changes in endpoints, which includes being notified of changes, see [Managing Office 365 endpoints-Integration](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) and [Managing Office 365 endpoints-Proxies](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span></span>

<span data-ttu-id="a730d-113">Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step4) für diesen Schritt ansehen.</span><span class="sxs-lookup"><span data-stu-id="a730d-113">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a730d-114">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="a730d-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="a730d-115">Optimieren der Leistung des Clients und des Office 365-Diensts</span><span class="sxs-lookup"><span data-stu-id="a730d-115">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|
