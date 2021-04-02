---
title: Untersuchen von Benutzern im Microsoft 365 Security Center
description: Untersuchen von Benutzern im Microsoft 365 Security Center
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitscenter, Monitor, Bericht, Identitäten, Daten, Geräte, Apps
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: ab6ce0e8572fc20d3e5dd9f36e84ce9894280fe2
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498192"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="ca3a7-104">Untersuchen von Benutzern im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="ca3a7-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="ca3a7-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ca3a7-105">**Applies to:**</span></span>

- <span data-ttu-id="ca3a7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca3a7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ca3a7-107">Im Rahmen Ihrer Untersuchung können Sie feststellen, dass ein Benutzer gefährdet wurde.</span><span class="sxs-lookup"><span data-stu-id="ca3a7-107">As part of your investigation, you might find that a user has been compromised.</span></span>

<span data-ttu-id="ca3a7-108">Die Microsoft 365 Security Center-Benutzerseite kombiniert Informationen von Microsoft Defender for Endpoint, Microsoft Defender for Identity und Microsoft Cloud App Security (je nachdem, welche Lizenzen Sie besitzen).</span><span class="sxs-lookup"><span data-stu-id="ca3a7-108">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> <span data-ttu-id="ca3a7-109">Diese Seite ist der ideale Ausgangspunkt für die Untersuchung von Benutzern und potenziellen Vorfällen.</span><span class="sxs-lookup"><span data-stu-id="ca3a7-109">This page is the ideal starting place for investigating users and potential incidents.</span></span>
<span data-ttu-id="ca3a7-110">![Benutzerseite](../../media/m3d-userpage.png)</span><span class="sxs-lookup"><span data-stu-id="ca3a7-110">![User page](../../media/m3d-userpage.png)</span></span>

<span data-ttu-id="ca3a7-111">Diese Seite enthält Informationen, die speziell auf das Sicherheitsrisiko eines Benutzers spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="ca3a7-111">This page shows information specific to the security risk of a user.</span></span> <span data-ttu-id="ca3a7-112">Dies umfasst eine Bewertung, die bei der Bewertung von Risiken, aktuellen Ereignissen und Warnungen hilft, die zum Gesamtrisiko des Benutzers beigetragen haben, und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="ca3a7-112">This includes a score that helps assess risk, recent events and alerts that contributed to the overall risk of the user, and more.</span></span>

<span data-ttu-id="ca3a7-113">Sie können über mehrere Bereiche im Microsoft 365 Security Center auf diese Seite zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ca3a7-113">You can access this page from multiple areas in the Microsoft 365 security center.</span></span> <span data-ttu-id="ca3a7-114">Sie können über einen bestimmten Vorfall auf der Registerkarte Benutzer auf **diese Seite** zugreifen. Einige Warnungen enthalten möglicherweise Benutzer als eine bestimmte betroffene Ressource.</span><span class="sxs-lookup"><span data-stu-id="ca3a7-114">You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset.</span></span> <span data-ttu-id="ca3a7-115">Sie können auch nach Benutzern suchen.</span><span class="sxs-lookup"><span data-stu-id="ca3a7-115">You can also search for users.</span></span>  

<span data-ttu-id="ca3a7-116">Weitere Informationen zum Untersuchen von Benutzern und potenziellen Risiken finden Sie [in diesem Lernprogramm für Cloud App Security](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).</span><span class="sxs-lookup"><span data-stu-id="ca3a7-116">Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ca3a7-117">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ca3a7-117">Related topics</span></span>

- [<span data-ttu-id="ca3a7-118">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="ca3a7-118">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="ca3a7-119">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="ca3a7-119">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="ca3a7-120">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="ca3a7-120">Manage incidents</span></span>](manage-incidents.md)