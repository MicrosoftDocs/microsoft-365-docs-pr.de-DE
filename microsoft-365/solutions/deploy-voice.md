---
title: Bereitstellen von Voice in Microsoft 365
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
description: Erfahren Sie, wie Sie die richtige Teams-Sprachlösung für Ihre Organisation auswählen und bereitstellen.
ms.openlocfilehash: ede8075767e9d0a80123ac742403f8a4d171392e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918382"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="52698-103">Eine Teams Voice Solution planen und bereitstellen</span><span class="sxs-lookup"><span data-stu-id="52698-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="52698-104">Eine Teams-Sprachlösung ermöglicht es Personen in Ihrer Organisation, Anrufe innerhalb und außerhalb Ihrer Organisation zu machen.</span><span class="sxs-lookup"><span data-stu-id="52698-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="52698-105">Eine vollständige Sprachlösung besteht aus Teams, Microsoft Phone System und einer Auswahl von Optionen für die Verbindung mit dem Telefonnetz (Public Switched Telephone Network, PSTN).</span><span class="sxs-lookup"><span data-stu-id="52698-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Übersicht über Teams-Sprachlösungen](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="52698-107">Das Telefonsystem bietet vollständige Nebenstellenanlagenfunktionen (Private Branch Exchange) für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="52698-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="52698-108">Anrufe zwischen Benutzern in Ihrer Organisation werden – unabhängig von ihrem geografischen Standort – intern innerhalb des Telefonsystems verarbeitet, wodurch Die Fernkosten für diese internen Anrufe entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="52698-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="52698-109">Durch das Verbinden des Telefonsystems mit dem Telefonnetz (Public Switched Telephone Network, PSTN) können Ihre Teams-Benutzer auch Anrufe außerhalb Ihrer Organisation machen.</span><span class="sxs-lookup"><span data-stu-id="52698-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="52698-110">Diese Lösungsanleitung hilft Ihnen dabei,</span><span class="sxs-lookup"><span data-stu-id="52698-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="52698-111">Wählen Sie die für Ihre Organisation richtige Sprachlösung aus.</span><span class="sxs-lookup"><span data-stu-id="52698-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="52698-112">Bereitstellen der ausgewählten Sprachlösung</span><span class="sxs-lookup"><span data-stu-id="52698-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="52698-113">Führen Sie die folgenden Schritte aus, um Ihre Sprachlösung zu wählen, zu planen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="52698-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Lösung für die Spracherkennung auswählen](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="52698-115">Lösung für die Spracherkennung auswählen</span><span class="sxs-lookup"><span data-stu-id="52698-115">Choose your voice solution</span></span>](/MicrosoftTeams/cloud-voice-landing-page?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

2. [<span data-ttu-id="52698-116">Einrichten des Telefonsystems</span><span class="sxs-lookup"><span data-stu-id="52698-116">Set up Phone System</span></span>](/microsoftteams/setting-up-your-phone-system?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

3. <span data-ttu-id="52698-117">Richten Sie die PSTN-Konnektivität ein, indem Sie eine oder eine Kombination der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="52698-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="52698-118">[Anrufplan](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) – Die All-in-the-Cloud-Lösung von Microsoft mit Microsoft als PstN-Netzbetreiber</span><span class="sxs-lookup"><span data-stu-id="52698-118">[Calling Plan](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="52698-119">[Direktes Routing](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) – Verwenden von Direct Routing zum Verbinden Ihres eigenen PSTN-Netzbetreibers mit Teams</span><span class="sxs-lookup"><span data-stu-id="52698-119">[Direct Routing](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="52698-120">Darüber hinaus sollten Sie in der Contoso-Fallstudie lesen, wie ein großes, multinationales Unternehmen zu einer Teams-Sprachlösung [migriert wurde.](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="52698-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json).</span></span>

<span data-ttu-id="52698-121">Weitere Informationen zu erforderlichen Lizenzen finden Sie unter den folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="52698-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="52698-122">Teams-Add-On-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="52698-122">Teams add-on licenses</span></span>](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json)

- [<span data-ttu-id="52698-123">Lizenzierungsanforderungen für direktes Routing</span><span class="sxs-lookup"><span data-stu-id="52698-123">Direct Routing licensing requirements</span></span>](/microsoftteams/direct-routing-plan?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json#licensing-and-other-requirements/toc.json)