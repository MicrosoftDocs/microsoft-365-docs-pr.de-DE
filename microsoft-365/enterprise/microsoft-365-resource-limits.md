---
title: Microsoft 365-Ressourcengrenzwerte
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In diesem Artikel finden Sie Informationen zu den Ressourcen Grenzwerten für die verschiedenen Anwendungen in Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6053740d41b02461432243c8527391a4f8ae22ea
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690709"
---
# <a name="resource-limits"></a><span data-ttu-id="c5d92-103">Ressourcenbeschränkungen</span><span class="sxs-lookup"><span data-stu-id="c5d92-103">Resource Limits</span></span>

<span data-ttu-id="c5d92-104">Ressourcengrenzwerte werden mithilfe von Kontingenten (Limits) und Drosselung erzwungen.</span><span class="sxs-lookup"><span data-stu-id="c5d92-104">Resource limits are enforced using quotas (limits) and throttling.</span></span> <span data-ttu-id="c5d92-105">Azure Active Directory (Azure AD) und die einzelnen Microsoft 365-Dienste verwenden beide.</span><span class="sxs-lookup"><span data-stu-id="c5d92-105">Azure Active Directory (Azure AD) and the individual Microsoft 365 services use both.</span></span> <span data-ttu-id="c5d92-106">Grenzen sind Dienst spezifisch und ändern sich im Laufe der Zeit, wenn neue Funktionen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c5d92-106">Limits are service-specific and change over time as new capabilities are added.</span></span> <span data-ttu-id="c5d92-107">Ausführliche Informationen zu den aktuellen Grenzwerten für die verschiedenen Dienste finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c5d92-107">For details on the current limits for the various services, see the following topics:</span></span>

- [<span data-ttu-id="c5d92-108">Azure Ad Service Limits und-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c5d92-108">Azure AD service limits and restrictions</span></span>](https://docs.microsoft.com/azure/azure-resource-manager/management/azure-subscription-service-limits)
- [<span data-ttu-id="c5d92-109">Exchange Online-Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="c5d92-109">Exchange Online Limits</span></span>](https://technet.microsoft.com/library/exchange-online-limits.aspx)
- [<span data-ttu-id="c5d92-110">Beschränkungen von Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c5d92-110">Exchange Online Protection Limits</span></span>](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx)
- [<span data-ttu-id="c5d92-111">Grenzen und Grenzwerte für SharePoint Online Software</span><span class="sxs-lookup"><span data-stu-id="c5d92-111">SharePoint Online software boundaries and limits</span></span>](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [<span data-ttu-id="c5d92-112">Skype for Business Grenzen</span><span class="sxs-lookup"><span data-stu-id="c5d92-112">Skype for Business Limits</span></span>](https://technet.microsoft.com/library/skype-for-business-online-limits.aspx)
- [<span data-ttu-id="c5d92-113">Jammern der Rest-API und Raten Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="c5d92-113">Yammer REST API and Rate Limits</span></span>](https://developer.yammer.com/docs/rest-api-rate-limits)
- [<span data-ttu-id="c5d92-114">Dateigrößenbeschränkungen in Sway</span><span class="sxs-lookup"><span data-stu-id="c5d92-114">File Size Limits in Sway</span></span>](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

<span data-ttu-id="c5d92-115">Zusätzlich zu diesen Grenzwerten werden mehrere Einschränkungs Mechanismen in Azure AD und in Microsoft 365 verwendet.</span><span class="sxs-lookup"><span data-stu-id="c5d92-115">In addition to these limits, several throttling mechanisms are used throughout Azure AD and Microsoft 365.</span></span> <span data-ttu-id="c5d92-116">Die Drosselung innerhalb des Diensts ist besonders wichtig, da Netzwerkressourcen in Microsoft-Rechenzentren für die breite Palette von Kunden optimiert sind, die die Dienste nutzen.</span><span class="sxs-lookup"><span data-stu-id="c5d92-116">Throttling within the service is especially important, given that network resources in Microsoft's datacenters are optimized for the broad set of customers that use the services.</span></span> <span data-ttu-id="c5d92-117">Zu den Einschränkungs Mechanismen gehören:</span><span class="sxs-lookup"><span data-stu-id="c5d92-117">Throttling mechanisms include:</span></span>

- <span data-ttu-id="c5d92-118">Azure AD-und Microsoft 365-Einschränkung auf Benutzerebene, die die Anzahl von Transaktionen oder gleichzeitigen anrufen (durch Skript oder Code) begrenzen, die von einem einzelnen Benutzer ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="c5d92-118">Azure AD and Microsoft 365 feature user-level throttling, which limit the number of transactions or concurrent calls (by script or code) that can be performed by a single user.</span></span>
- <span data-ttu-id="c5d92-119">Jedem Mandanten wird bei der Mandanten Erstellung eine standardmäßige PowerShell-Einschränkungsrichtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c5d92-119">A default PowerShell throttling policy is assigned to each tenant at tenant creation.</span></span> <span data-ttu-id="c5d92-120">Diese Einstellungen wirken sich auf andere Elemente aus, beispielsweise die maximale Anzahl gleichzeitiger PowerShell-Sitzungen, die von einem einzelnen Administrator geöffnet werden können.</span><span class="sxs-lookup"><span data-stu-id="c5d92-120">These settings affect other items, such as the maximum number of simultaneous PowerShell sessions that can be opened by a single administrator.</span></span>
- <span data-ttu-id="c5d92-121">Jeder Exchange Online-Kunde verfügt über eine standardmäßige Exchange-Webdienste-Richtlinie, die für EWS-Client Vorgänge optimiert ist, sowie für Einschränkungen, die für alle Outlook-Clients gelten.</span><span class="sxs-lookup"><span data-stu-id="c5d92-121">Each Exchange Online customer has a default Exchange Web Services (EWS) policy that is tuned for EWS client operations, and throttling that applies to all Outlook clients.</span></span>
