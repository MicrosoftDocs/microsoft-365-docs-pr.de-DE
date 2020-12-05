---
title: Bereitstellen von VoIP in Microsoft 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-voice
- M365-voice
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Erfahren Sie, wie Sie die richtige Microsoft Teams-VoIP-Lösung für Ihre Organisation auswählen und bereitstellen.
ms.openlocfilehash: b5dda0ed3d9310c3c43052b9bac4996802e0ed2f
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580899"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="6fe8d-103">Planen und Bereitstelleneiner VoIP-Lösung für Teams</span><span class="sxs-lookup"><span data-stu-id="6fe8d-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="6fe8d-104">Mit einer VoIP-Lösung für Teams können Personen in Ihrer Organisation Anrufe innerhalb und außerhalb Ihrer Organisation tätigen.</span><span class="sxs-lookup"><span data-stu-id="6fe8d-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="6fe8d-105">Eine vollständige Sprachlösung besteht aus Teams, Microsoft Phone System und einer Auswahl von Optionen zum Herstellen einer Verbindung mit dem Telefon Festnetz (Public Switched Telephone Network, PSTN).</span><span class="sxs-lookup"><span data-stu-id="6fe8d-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Übersicht über Teams-VoIP-Lösungen](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="6fe8d-107">Telefon System bietet vollständige PBX-Funktionen (Private Branch Exchange) für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="6fe8d-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="6fe8d-108">Anrufe zwischen Benutzern in Ihrer Organisation – unabhängig von ihrem geografischen Standort – werden intern innerhalb des Telefonsystems behandelt, wodurch die Kosten für den Fernabsatz für diese internen Anrufe entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="6fe8d-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="6fe8d-109">Durch das Verbinden von Telefon System mit dem Telefon Festnetz (Public Switched Telephone Network, PSTN) können Ihre Teams-Benutzer auch außerhalb Ihrer Organisation Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="6fe8d-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="6fe8d-110">Dieser Lösungsleitfaden hilft Ihnen:</span><span class="sxs-lookup"><span data-stu-id="6fe8d-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="6fe8d-111">Auswählen der richtigen VoIP-Lösung für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="6fe8d-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="6fe8d-112">Bereitstellen der ausgewählten VoIP-Lösung</span><span class="sxs-lookup"><span data-stu-id="6fe8d-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="6fe8d-113">Führen Sie die folgenden Schritte aus, um Ihre VoIP-Lösung auszuwählen, zu planen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="6fe8d-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Auswählen Ihrer VoIP-Lösung](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="6fe8d-115">Auswählen Ihrer VoIP-Lösung</span><span class="sxs-lookup"><span data-stu-id="6fe8d-115">Choose your voice solution</span></span>](https://docs.microsoft.com/MicrosoftTeams/cloud-voice-landing-page?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

2. [<span data-ttu-id="6fe8d-116">Einrichten des Telefonsystems</span><span class="sxs-lookup"><span data-stu-id="6fe8d-116">Set up Phone System</span></span>](https://docs.microsoft.com/microsoftteams/setting-up-your-phone-system?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

3. <span data-ttu-id="6fe8d-117">Richten Sie die PSTN-Konnektivität ein, indem Sie eine oder eine Kombination der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="6fe8d-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="6fe8d-118">[Calling Plan](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) – die all-in-the-Cloud-Lösung von Microsoft als PSTN-Carrier</span><span class="sxs-lookup"><span data-stu-id="6fe8d-118">[Calling Plan](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="6fe8d-119">[Direktes Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) – verwenden Sie das direkte Routing, um Ihren eigenen PSTN-Carrier mit Microsoft Teams zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="6fe8d-119">[Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="6fe8d-120">Darüber hinaus können Sie in der [contoso-Fallstudie](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)erfahren, wie ein großes, multinationales Unternehmen zu einer VoIP-Lösung für Teams migriert wurde.</span><span class="sxs-lookup"><span data-stu-id="6fe8d-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span></span>

<span data-ttu-id="6fe8d-121">Informationen zu erforderlichen Lizenzen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="6fe8d-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="6fe8d-122">Microsoft Teams-Add-on-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="6fe8d-122">Teams add-on licenses</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

- [<span data-ttu-id="6fe8d-123">Lizenzierungsanforderungen für das direkte Routing</span><span class="sxs-lookup"><span data-stu-id="6fe8d-123">Direct Routing licensing requirements</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)
