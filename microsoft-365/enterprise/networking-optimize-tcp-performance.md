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
# <a name="step-5-optimize-client-and-office-365-service-performance"></a><span data-ttu-id="ee524-103">Schritt 5: Optimieren der Leistung des Clients und des Office 365-Diensts</span><span class="sxs-lookup"><span data-stu-id="ee524-103">Step 5: Optimize client and Office 365 service performance</span></span>

<span data-ttu-id="ee524-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ee524-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Phase 1 – Netzwerken](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="ee524-106">Sie können die Leistung durch die Optimierung der Art und Weise, wie TCP (Transmission Control-Protokoll) zwischen Clientgeräten und Office 365-Diensten funktioniert, erhöhen.</span><span class="sxs-lookup"><span data-stu-id="ee524-106">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Office 365 services.</span></span>

<span data-ttu-id="ee524-107">Für Clientgeräte können Sie die folgenden TCP-Einstellungen auf Clientgeräten zum Optimieren der Leistung von TCP ändern:</span><span class="sxs-lookup"><span data-stu-id="ee524-107">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="ee524-108">[TCP-Fensterskalierung](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), damit Ihr Clientgerät mehr Daten senden kann, bevor eine Bestätigung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="ee524-108">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="ee524-109">[TCP-Leerlaufzeit](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), damit Ihr Clientgerät offene Verbindungen effizienter verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="ee524-109">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="ee524-110">[Maximale TCP-Segmentgröße](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), damit Ihr Clientgerät die größten Datenblöcke in einem Paket senden kann.</span><span class="sxs-lookup"><span data-stu-id="ee524-110">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="ee524-111">[Selektive TCP-Empfangsbestätigungen](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), damit Ihr Clientgerät empfangene Daten effizienter bestätigen kann.</span><span class="sxs-lookup"><span data-stu-id="ee524-111">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="ee524-112">Für Office 365-Dienste finden Sie hier weitere Informationsquellen zum Optimieren der Leistung:</span><span class="sxs-lookup"><span data-stu-id="ee524-112">For Office 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="ee524-113">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ee524-113">Exchange Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [<span data-ttu-id="ee524-114">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ee524-114">Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [<span data-ttu-id="ee524-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ee524-115">SharePoint Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [<span data-ttu-id="ee524-116">Project Web App in Project Online</span><span class="sxs-lookup"><span data-stu-id="ee524-116">Project Web App in Project Online</span></span>](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

<span data-ttu-id="ee524-117">Als Zwischenprüfung können Sie die [Beendigungskriterien](networking-exit-criteria.md#crit-networking-step5) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="ee524-117">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="ee524-118">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="ee524-118">Next step</span></span>

[<span data-ttu-id="ee524-119">Beendigungskriterien für die Netzwerkinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="ee524-119">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
