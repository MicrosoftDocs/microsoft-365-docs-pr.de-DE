---
title: Untersuchen von Benutzern im Microsoft 365 Security Center
description: Untersuchen von Benutzern im Microsoft 365 Security Center
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitscenter, Monitor, Bericht, Identitäten, Daten, Geräte, Apps
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 32c496a212e038d649fdc9880c8ac829ee4a5337
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927234"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="27930-104">Untersuchen von Benutzern im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="27930-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="27930-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="27930-105">**Applies to:**</span></span>

- <span data-ttu-id="27930-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27930-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="27930-107">Im Rahmen Ihrer Untersuchung können Sie feststellen, dass ein Benutzer gefährdet wurde.</span><span class="sxs-lookup"><span data-stu-id="27930-107">As part of your investigation, you might find that a user has been compromised.</span></span>

<span data-ttu-id="27930-108">Die Microsoft 365 Security Center-Benutzerseite kombiniert Informationen von Microsoft Defender for Endpoint, Microsoft Defender for Identity und Microsoft Cloud App Security (je nachdem, welche Lizenzen Sie besitzen).</span><span class="sxs-lookup"><span data-stu-id="27930-108">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> <span data-ttu-id="27930-109">Diese Seite ist der ideale Ausgangspunkt für die Untersuchung von Benutzern und potenziellen Vorfällen.</span><span class="sxs-lookup"><span data-stu-id="27930-109">This page is the ideal starting place for investigating users and potential incidents.</span></span>
<span data-ttu-id="27930-110">![Benutzerseite](../../media/m3d-userpage.png)</span><span class="sxs-lookup"><span data-stu-id="27930-110">![User page](../../media/m3d-userpage.png)</span></span>

<span data-ttu-id="27930-111">Diese Seite enthält Informationen, die speziell auf das Sicherheitsrisiko eines Benutzers spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="27930-111">This page shows information specific to the security risk of a user.</span></span> <span data-ttu-id="27930-112">Dies umfasst eine Bewertung, die bei der Bewertung von Risiken, aktuellen Ereignissen und Warnungen hilft, die zum Gesamtrisiko des Benutzers beigetragen haben, und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="27930-112">This includes a score that helps assess risk, recent events and alerts that contributed to the overall risk of the user, and more.</span></span>

<span data-ttu-id="27930-113">Sie können über mehrere Bereiche im Microsoft 365 Security Center auf diese Seite zugreifen.</span><span class="sxs-lookup"><span data-stu-id="27930-113">You can access this page from multiple areas in the Microsoft 365 security center.</span></span> <span data-ttu-id="27930-114">Sie können über einen bestimmten Vorfall auf der Registerkarte Benutzer auf **diese Seite** zugreifen. Einige Warnungen enthalten möglicherweise Benutzer als eine bestimmte betroffene Ressource.</span><span class="sxs-lookup"><span data-stu-id="27930-114">You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset.</span></span> <span data-ttu-id="27930-115">Sie können auch nach Benutzern suchen.</span><span class="sxs-lookup"><span data-stu-id="27930-115">You can also search for users.</span></span>  

<span data-ttu-id="27930-116">Weitere Informationen zum Untersuchen von Benutzern und potenziellen Risiken finden Sie [in diesem Lernprogramm für Cloud App Security](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).</span><span class="sxs-lookup"><span data-stu-id="27930-116">Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).</span></span>

## <a name="related-topics"></a><span data-ttu-id="27930-117">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="27930-117">Related topics</span></span>

- [<span data-ttu-id="27930-118">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="27930-118">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="27930-119">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="27930-119">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="27930-120">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="27930-120">Manage incidents</span></span>](manage-incidents.md)