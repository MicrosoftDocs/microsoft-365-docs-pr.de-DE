---
title: Informationen zur standardmäßigen Richtlinie zur Verhinderung von Datenverlust in Microsoft Teams (Vorschau)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Informationen zur standardmäßigen Richtlinie zur Verhinderung von Datenverlust in Microsoft Teams
ms.openlocfilehash: 3992daf9431dbd87ed5e947a1e5a2b0acd20edce
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826233"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="c1b94-103">Informationen zur standardmäßigen Richtlinie zur Verhinderung von Datenverlust in Microsoft Teams (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c1b94-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="c1b94-104">Die Funktionen zur Verhinderung von Datenverlust [(Data Loss Prevention,](data-loss-prevention-policies.md) DLP) wurden um Microsoft Teams-Chat- und Kanalnachrichten erweitert, einschließlich Nachrichten im privaten Kanal.</span><span class="sxs-lookup"><span data-stu-id="c1b94-104">[Data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="c1b94-105">Als Teil dieser Version haben wir eine Standard-DLP-Richtlinie für Erstkunden im Compliance Center erstellt.</span><span class="sxs-lookup"><span data-stu-id="c1b94-105">As a part of this release, we created a default DLP policy for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="c1b94-106">Betrifft</span><span class="sxs-lookup"><span data-stu-id="c1b94-106">Applies to</span></span>

<span data-ttu-id="c1b94-107">Jeder Mandant, der mit einer oder mehreren der folgenden Lizenzen lizenziert ist und über aktive Teams-Benutzer verfügt</span><span class="sxs-lookup"><span data-stu-id="c1b94-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="c1b94-108">ME5,</span><span class="sxs-lookup"><span data-stu-id="c1b94-108">ME5,</span></span> 
- <span data-ttu-id="c1b94-109">MA5,</span><span class="sxs-lookup"><span data-stu-id="c1b94-109">MA5,</span></span> 
- <span data-ttu-id="c1b94-110">E5/A5 Compliance,</span><span class="sxs-lookup"><span data-stu-id="c1b94-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="c1b94-111">IP+G,</span><span class="sxs-lookup"><span data-stu-id="c1b94-111">IP+G,</span></span> 
- <span data-ttu-id="c1b94-112">OE5,</span><span class="sxs-lookup"><span data-stu-id="c1b94-112">OE5,</span></span> 
- <span data-ttu-id="c1b94-113">O365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="c1b94-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="c1b94-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="c1b94-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="c1b94-115">Was macht die Standardrichtlinie?</span><span class="sxs-lookup"><span data-stu-id="c1b94-115">What does the default policy do?</span></span>

<span data-ttu-id="c1b94-116">Die Standardmäßige DLP-Richtlinie verfolgt alle Kreditkartennummern, die intern und extern für die Organisation freigegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="c1b94-116">The default DLP policy tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="c1b94-117">Diese Richtlinie ist standardmäßig für alle Benutzer des Mandanten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c1b94-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="c1b94-118">Es generiert keine Richtlinientipps für Endbenutzer, generiert aber ein Warnungsereignis und löst auch eine E-Mail mit geringem Schweregrad an den Administrator aus (in der Richtlinie hinzugefügt).</span><span class="sxs-lookup"><span data-stu-id="c1b94-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="c1b94-119">Der Administrator kann die Aktivitäten anzeigen und die Richtliniendetails bearbeiten, indem er sich beim Compliance Center einmeldet.</span><span class="sxs-lookup"><span data-stu-id="c1b94-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="c1b94-120">Administratoren können diese Richtlinie auf der Seite Compliance [Center >](https://compliance.microsoft.com/compliancesettings) Richtlinie zur Verhinderung von Datenverlust anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c1b94-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="c1b94-121">![Standardmäßige Teams-DLP-Richtlinie](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="c1b94-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="c1b94-122">Bearbeiten oder Löschen der Standardrichtlinie</span><span class="sxs-lookup"><span data-stu-id="c1b94-122">Edit or delete the default policy</span></span>

<span data-ttu-id="c1b94-123">Um [die Standardrichtlinie zu](create-test-tune-dlp-policy.md#tune-a-dlp-policy)bearbeiten, um eine bessere Leistung zu erzielen oder sie zu löschen, verwenden Sie einfach ein Konto mit **DLP Compliance Management-Berechtigungen.**</span><span class="sxs-lookup"><span data-stu-id="c1b94-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="c1b94-124">Weitere Informationen finden Sie unter [Permissions](create-test-tune-dlp-policy.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="c1b94-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>

