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
ms.openlocfilehash: 234ae17ab31d56d1bbd65f1aa8ed29475e9cd155
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583715"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="8c93f-104">Was Microsoft-Sicherheitsbewertung in Kürze verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="8c93f-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="8c93f-105">Um [Microsoft Secure Score](microsoft-secure-score.md) zu einem besseren Vertreter ihrer Sicherheitsposition zu machen und die Benutzerfreundlichkeit zu verbessern, werden wir in naher Zukunft einige Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="8c93f-105">To make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="8c93f-106">Ihre Bewertung und die maximale Punktzahl werden geändert.</span><span class="sxs-lookup"><span data-stu-id="8c93f-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="8c93f-107">Dies bedeutet jedoch nicht, dass sich Ihr Sicherheitsstatus ändert.</span><span class="sxs-lookup"><span data-stu-id="8c93f-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="8c93f-108">Wenn Sie mehr über die neuesten Änderungen wissen möchten, lesen Sie [Neuerungen in Microsoft-Sicherheitsbewertung](microsoft-secure-score.md#whats-new).</span><span class="sxs-lookup"><span data-stu-id="8c93f-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="8c93f-109">21. April 2020</span><span class="sxs-lookup"><span data-stu-id="8c93f-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="8c93f-110">Verbesserungsmaßnahmen, die die Erwartungen an zuverlässige Messungen nicht erfüllen oder keine nützlichen Darstellung des Sicherheitsstatus bieten, wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="8c93f-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="8c93f-111">Um sicherzustellen, dass Microsoft-Sicherheitsbewertung aussagekräftig ist und jede Verbesserungsmaßnahme messbar und zuverlässig ist, entfernen wir die folgenden Verbesserungsmaßnahmen.</span><span class="sxs-lookup"><span data-stu-id="8c93f-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="8c93f-112">IRM-Schutz auf Dokumente anwenden</span><span class="sxs-lookup"><span data-stu-id="8c93f-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="8c93f-113">Richtlinien zur Verhinderung von Datenverlust anwenden</span><span class="sxs-lookup"><span data-stu-id="8c93f-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-to-preview"></a><span data-ttu-id="8c93f-114">Hinzufügen von Azure AD Verbesserungs Aktion zur Vorschau</span><span class="sxs-lookup"><span data-stu-id="8c93f-114">Adding Azure AD improvement action to preview</span></span>

<span data-ttu-id="8c93f-115">Hinzufügen der folgenden Azure Active Directory-Verbesserungs Aktion zur [Vorschauversion von Microsoft Secure Score](microsoft-secure-score-preview.md):</span><span class="sxs-lookup"><span data-stu-id="8c93f-115">Adding the following Azure Active Directory improvement action to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="8c93f-116">Nicht zulassen, dass Benutzer nicht verwalteten Anwendungen zustimmen (zurzeit in der veröffentlichten Version verfügbar)</span><span class="sxs-lookup"><span data-stu-id="8c93f-116">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-to-preview"></a><span data-ttu-id="8c93f-117">Hinzufügen von Azure ATP-Verbesserungs Aktionen zur Vorschau</span><span class="sxs-lookup"><span data-stu-id="8c93f-117">Adding Azure ATP improvement actions to preview</span></span>

<span data-ttu-id="8c93f-118">Hinzufügen der folgenden Azure Advanced Threat Protection-Verbesserungs Aktionen zur [Vorschauversion von Microsoft Secure Score](microsoft-secure-score-preview.md):</span><span class="sxs-lookup"><span data-stu-id="8c93f-118">Adding the following Azure Advanced Threat Protection improvement actions to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="8c93f-119">Druckerspoolerdienst auf Domänencontrollern deaktivieren</span><span class="sxs-lookup"><span data-stu-id="8c93f-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="8c93f-120">Unsichere Kerberos-Delegierungen ändern, um einen Identitätswechsel zu verhindern</span><span class="sxs-lookup"><span data-stu-id="8c93f-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="8c93f-121">Lokale Administratorkennwörter mit Microsoft LAPS schützen und verwalten</span><span class="sxs-lookup"><span data-stu-id="8c93f-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="8c93f-122">Risiko des lateralen Bewegungspfads auf sensible Entitäten reduzieren</span><span class="sxs-lookup"><span data-stu-id="8c93f-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="8c93f-123">Ruhende Konten aus sensiblen Gruppen entfernen</span><span class="sxs-lookup"><span data-stu-id="8c93f-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="8c93f-124">Unsichere SID-Verlaufsattribute aus Entitäten entfernen</span><span class="sxs-lookup"><span data-stu-id="8c93f-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="8c93f-125">Unsichere Kontoattribute auflösen</span><span class="sxs-lookup"><span data-stu-id="8c93f-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="8c93f-126">Offenlegung von Anmeldeinformationen in Klartext verhindern</span><span class="sxs-lookup"><span data-stu-id="8c93f-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="8c93f-127">Kommunikation über Legacy-Protokolle verhindern</span><span class="sxs-lookup"><span data-stu-id="8c93f-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="8c93f-128">Verwendung schwacher Verschlüsselung verhindern</span><span class="sxs-lookup"><span data-stu-id="8c93f-128">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-preview"></a><span data-ttu-id="8c93f-129">Unterstützung für Microsoft Defender ATP Threat & Vulnerability Management (TVM) Sicherheitsempfehlungen in der Vorschau</span><span class="sxs-lookup"><span data-stu-id="8c93f-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in preview</span></span>

<span data-ttu-id="8c93f-130">Alle veröffentlichten Sicherheitsempfehlungen von TVM werden nun auch [in der Preview-Version von Microsoft Secure Score](microsoft-secure-score-preview.md)zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="8c93f-130">All released security recommendations supplied by TVM will now also be available the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md).</span></span>
