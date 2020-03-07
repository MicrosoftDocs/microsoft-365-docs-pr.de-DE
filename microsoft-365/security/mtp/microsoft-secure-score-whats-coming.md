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
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372003"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="d1a56-104">Was Microsoft-Sicherheitsbewertung in Kürze verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="d1a56-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="d1a56-105">Um Microsoft-Sicherheitsbewertung zu einem besseren Anlaufpunkt für Ihren Sicherheitsstatus zu machen und die Benutzerfreundlichkeit zu verbessern, nehmen wir in naher Zukunft einige Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="d1a56-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="d1a56-106">Ihre Bewertung und die maximale Punktzahl werden geändert.</span><span class="sxs-lookup"><span data-stu-id="d1a56-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="d1a56-107">Dies bedeutet jedoch nicht, dass sich Ihr Sicherheitsstatus ändert.</span><span class="sxs-lookup"><span data-stu-id="d1a56-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="d1a56-108">Wenn Sie mehr über die neuesten Änderungen wissen möchten, lesen Sie [Neuerungen in Microsoft-Sicherheitsbewertung](microsoft-secure-score.md#whats-new).</span><span class="sxs-lookup"><span data-stu-id="d1a56-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="d1a56-109">16. März 2020</span><span class="sxs-lookup"><span data-stu-id="d1a56-109">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="d1a56-110">Verbesserungsmaßnahmen, die die Erwartungen an zuverlässige Messungen nicht erfüllen oder keine nützlichen Darstellung des Sicherheitsstatus bieten, wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="d1a56-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="d1a56-111">Um sicherzustellen, dass Microsoft-Sicherheitsbewertung aussagekräftig ist und jede Verbesserungsmaßnahme messbar und zuverlässig ist, entfernen wir die folgenden Verbesserungsmaßnahmen.</span><span class="sxs-lookup"><span data-stu-id="d1a56-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="d1a56-112">Benutzerdokumente in OneDrive for Business speichern</span><span class="sxs-lookup"><span data-stu-id="d1a56-112">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="d1a56-113">Office 365 ATP-Richtlinien für sichere Anlagen einrichten</span><span class="sxs-lookup"><span data-stu-id="d1a56-113">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="d1a56-114">Sichere Links zum Überprüfen von URLs in Office 365 einrichten</span><span class="sxs-lookup"><span data-stu-id="d1a56-114">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="d1a56-115">Postfachdelegierung nicht zulassen</span><span class="sxs-lookup"><span data-stu-id="d1a56-115">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="d1a56-116">Anonyme Gastfreigabelinks für Websites und Dokumente zulassen</span><span class="sxs-lookup"><span data-stu-id="d1a56-116">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="d1a56-117">Cloud App Security-Konsole aktivieren</span><span class="sxs-lookup"><span data-stu-id="d1a56-117">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="d1a56-118">Ablaufzeit für externe Freigabelinks konfigurieren</span><span class="sxs-lookup"><span data-stu-id="d1a56-118">Configure expiration time for external sharing links</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="d1a56-119">Sicherheitsstandards für Azure AD-Verbesserungsmaßnahmen unterstützen</span><span class="sxs-lookup"><span data-stu-id="d1a56-119">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="d1a56-120">Microsoft-Sicherheitsbewertung aktualisiert Verbesserungsmaßnahmen zur Unterstützung von [Sicherheitsstandards in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), die es einfacher machen, Ihre Organisation mit vorkonfigurierten Sicherheitseinstellungen für häufige Angriffe zu schützen.</span><span class="sxs-lookup"><span data-stu-id="d1a56-120">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="d1a56-121">Dies betrifft die folgenden Verbesserungsmaßnahmen:</span><span class="sxs-lookup"><span data-stu-id="d1a56-121">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="d1a56-122">Sicherstellen, dass alle Benutzer die mehrstufige Authentifizierung für sicheren Zugriff durchführen können</span><span class="sxs-lookup"><span data-stu-id="d1a56-122">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="d1a56-123">MFA für Administratorrollen erzwingen</span><span class="sxs-lookup"><span data-stu-id="d1a56-123">Require MFA for administrative roles</span></span>
- <span data-ttu-id="d1a56-124">Richtlinie zum Blockieren veralteter Authentifizierung aktivieren</span><span class="sxs-lookup"><span data-stu-id="d1a56-124">Enable policy to block legacy authentication</span></span>
