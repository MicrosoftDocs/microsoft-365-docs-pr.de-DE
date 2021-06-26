---
title: Weitere Informationen zur Standardrichtlinie zur Verhinderung von Datenverlust in Microsoft Teams (Vorschau)
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
description: Erfahren Sie mehr über die Standardmäßige Richtlinie zur Verhinderung von Datenverlust in Microsoft Teams
ms.openlocfilehash: c6b7413fdd4017fe1211e804c00a2e9c0684468d
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149118"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="43028-103">Weitere Informationen zur Standardrichtlinie zur Verhinderung von Datenverlust in Microsoft Teams (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="43028-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="43028-104">Die Funktionen [zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md) wurden erweitert, um Microsoft Teams Chat- und Kanalnachrichten, einschließlich Nachrichten im privaten Kanal, einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="43028-104">[Data loss prevention](dlp-learn-about-dlp.md) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="43028-105">Als Teil dieser Version haben wir eine Standard-DLP-Richtlinie für Microsoft Teams für Erstmalige Kunden im Compliance Center erstellt.</span><span class="sxs-lookup"><span data-stu-id="43028-105">As a part of this release, we created a default DLP policy for Microsoft Teams for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="43028-106">Gilt für</span><span class="sxs-lookup"><span data-stu-id="43028-106">Applies to</span></span>

<span data-ttu-id="43028-107">Jeder Mandant, der mit einer oder mehreren der folgenden Lizenzen lizenziert ist und über aktive Teams Benutzer verfügt</span><span class="sxs-lookup"><span data-stu-id="43028-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="43028-108">ME5,</span><span class="sxs-lookup"><span data-stu-id="43028-108">ME5,</span></span> 
- <span data-ttu-id="43028-109">MA5,</span><span class="sxs-lookup"><span data-stu-id="43028-109">MA5,</span></span> 
- <span data-ttu-id="43028-110">E5/A5 Compliance,</span><span class="sxs-lookup"><span data-stu-id="43028-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="43028-111">IP+G,</span><span class="sxs-lookup"><span data-stu-id="43028-111">IP+G,</span></span> 
- <span data-ttu-id="43028-112">OE5,</span><span class="sxs-lookup"><span data-stu-id="43028-112">OE5,</span></span> 
- <span data-ttu-id="43028-113">O365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="43028-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="43028-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="43028-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="43028-115">Was bewirkt die Standardrichtlinie?</span><span class="sxs-lookup"><span data-stu-id="43028-115">What does the default policy do?</span></span>

<span data-ttu-id="43028-116">Die Standardmäßige DLP-Richtlinie für Teams verfolgt alle Kreditkartennummern nach, die intern und extern für die Organisation freigegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="43028-116">The default DLP policy for Teams tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="43028-117">Diese Richtlinie ist standardmäßig für alle Benutzer des Mandanten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="43028-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="43028-118">Es generiert keine Richtlinientipps für Endbenutzer, generiert jedoch ein Warnungsereignis und löst auch eine E-Mail mit geringem Schweregrad an den Administrator aus (hinzugefügt in der Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="43028-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="43028-119">Der Administrator kann die Aktivitäten anzeigen und die Richtliniendetails bearbeiten, indem er sich beim Compliance Center anmeldet.</span><span class="sxs-lookup"><span data-stu-id="43028-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="43028-120">Administratoren können diese Richtlinie im [Compliance Center](https://compliance.microsoft.com/compliancesettings) > Seite "Richtlinien zur Verhinderung von Datenverlust" anzeigen.</span><span class="sxs-lookup"><span data-stu-id="43028-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="43028-121">![Standardmäßige Teams DLP-Richtlinie](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="43028-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="43028-122">Bearbeiten oder Löschen der Standardrichtlinie</span><span class="sxs-lookup"><span data-stu-id="43028-122">Edit or delete the default policy</span></span>

<span data-ttu-id="43028-123">Um [die Standardrichtlinie für eine bessere Leistung zu bearbeiten oder zu löschen,](create-test-tune-dlp-policy.md#tune-a-dlp-policy)verwenden Sie einfach ein Konto mit **DLP-Complianceverwaltungsberechtigungen.**</span><span class="sxs-lookup"><span data-stu-id="43028-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="43028-124">Weitere Informationen finden Sie unter ["Berechtigungen".](create-test-tune-dlp-policy.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="43028-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>

