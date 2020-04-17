---
title: Was Microsoft-Sicherheitsbewertung in Kürze verfügbar ist
description: Beschreibt Microsoft-Sicherheitsbewertung im Microsoft 365 Security Center, erläutert die Berechnung von Details und was Sicherheitsadministratoren erwarten dürfen.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitsbewertung, Security Center, Verbesserungsmaßnahmen
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 1a5c5ae702f16bbf47be83837cf244cdd64278cd
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541107"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="fa5ce-104">Was Microsoft-Sicherheitsbewertung in Kürze verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="fa5ce-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="fa5ce-105">Um Microsoft-Sicherheitsbewertung zu einem besseren Anlaufpunkt für Ihren Sicherheitsstatus zu machen und die Benutzerfreundlichkeit zu verbessern, nehmen wir in naher Zukunft einige Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="fa5ce-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="fa5ce-106">Ihre Bewertung und die maximale Punktzahl werden geändert.</span><span class="sxs-lookup"><span data-stu-id="fa5ce-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="fa5ce-107">Dies bedeutet jedoch nicht, dass sich Ihr Sicherheitsstatus ändert.</span><span class="sxs-lookup"><span data-stu-id="fa5ce-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="fa5ce-108">Wenn Sie mehr über die neuesten Änderungen wissen möchten, lesen Sie [Neuerungen in Microsoft-Sicherheitsbewertung](microsoft-secure-score.md#whats-new).</span><span class="sxs-lookup"><span data-stu-id="fa5ce-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="fa5ce-109">21. April 2020</span><span class="sxs-lookup"><span data-stu-id="fa5ce-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="fa5ce-110">Verbesserungsmaßnahmen, die die Erwartungen an zuverlässige Messungen nicht erfüllen oder keine nützlichen Darstellung des Sicherheitsstatus bieten, wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="fa5ce-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="fa5ce-111">Um sicherzustellen, dass Microsoft-Sicherheitsbewertung aussagekräftig ist und jede Verbesserungsmaßnahme messbar und zuverlässig ist, entfernen wir die folgenden Verbesserungsmaßnahmen.</span><span class="sxs-lookup"><span data-stu-id="fa5ce-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="fa5ce-112">IRM-Schutz auf Dokumente anwenden</span><span class="sxs-lookup"><span data-stu-id="fa5ce-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="fa5ce-113">Richtlinien zur Verhinderung von Datenverlust anwenden</span><span class="sxs-lookup"><span data-stu-id="fa5ce-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-in-the-preview-version"></a><span data-ttu-id="fa5ce-114">Hinzufügen von Azure AD Verbesserungs Aktion in der Vorschauversion</span><span class="sxs-lookup"><span data-stu-id="fa5ce-114">Adding Azure AD improvement action in the preview version</span></span>

- <span data-ttu-id="fa5ce-115">Nicht zulassen, dass Benutzer nicht verwalteten Anwendungen zustimmen (zurzeit in der veröffentlichten Version verfügbar)</span><span class="sxs-lookup"><span data-stu-id="fa5ce-115">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-in-the-preview-version"></a><span data-ttu-id="fa5ce-116">Hinzufügen von Azure ATP-Verbesserungs Aktionen in der Vorschauversion</span><span class="sxs-lookup"><span data-stu-id="fa5ce-116">Adding Azure ATP improvement actions in the preview version</span></span>

- <span data-ttu-id="fa5ce-117">Druckerspoolerdienst auf Domänencontrollern deaktivieren</span><span class="sxs-lookup"><span data-stu-id="fa5ce-117">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="fa5ce-118">Unsichere Kerberos-Delegierungen ändern, um einen Identitätswechsel zu verhindern</span><span class="sxs-lookup"><span data-stu-id="fa5ce-118">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="fa5ce-119">Lokale Administratorkennwörter mit Microsoft LAPS schützen und verwalten</span><span class="sxs-lookup"><span data-stu-id="fa5ce-119">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="fa5ce-120">Risiko des lateralen Bewegungspfads auf sensible Entitäten reduzieren</span><span class="sxs-lookup"><span data-stu-id="fa5ce-120">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="fa5ce-121">Ruhende Konten aus sensiblen Gruppen entfernen</span><span class="sxs-lookup"><span data-stu-id="fa5ce-121">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="fa5ce-122">Unsichere SID-Verlaufsattribute aus Entitäten entfernen</span><span class="sxs-lookup"><span data-stu-id="fa5ce-122">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="fa5ce-123">Unsichere Kontoattribute auflösen</span><span class="sxs-lookup"><span data-stu-id="fa5ce-123">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="fa5ce-124">Offenlegung von Anmeldeinformationen in Klartext verhindern</span><span class="sxs-lookup"><span data-stu-id="fa5ce-124">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="fa5ce-125">Kommunikation über Legacy-Protokolle verhindern</span><span class="sxs-lookup"><span data-stu-id="fa5ce-125">Stop legacy protocols communication</span></span>
- <span data-ttu-id="fa5ce-126">Verwendung schwacher Verschlüsselung verhindern</span><span class="sxs-lookup"><span data-stu-id="fa5ce-126">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-the-preview-version"></a><span data-ttu-id="fa5ce-127">Unterstützung für Sicherheitsempfehlungen für Microsoft Defender ATP Threat & Vulnerability Management (TVM) in der Vorschauversion</span><span class="sxs-lookup"><span data-stu-id="fa5ce-127">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in the preview version</span></span>

- <span data-ttu-id="fa5ce-128">Alle von TVM bereitgestellten Sicherheitsempfehlungen sind nun auch in Microsoft-Sicherheitsbewertung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fa5ce-128">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
