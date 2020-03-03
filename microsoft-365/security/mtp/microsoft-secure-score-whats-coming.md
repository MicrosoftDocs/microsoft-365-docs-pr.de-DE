---
title: Was kommt in Microsoft Secure Score vor?
description: Beschreibt Microsoft Secure Score im Microsoft 365 Security Center, wie Details berechnet werden und welche Sicherheitsadministratoren erwarten können.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, sicheres Ergebnis, Sicherheitscenter, Verbesserungs Aktionen
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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372003"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="d527a-104">Was kommt in Microsoft Secure Score vor?</span><span class="sxs-lookup"><span data-stu-id="d527a-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="d527a-105">Um Microsoft Secure Score zu einem besseren Vertreter ihrer Sicherheitsposition zu machen und die Benutzerfreundlichkeit zu verbessern, werden wir in naher Zukunft einige Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="d527a-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="d527a-106">Ihre Punktzahl und die maximal mögliche Punktzahl ändern sich.</span><span class="sxs-lookup"><span data-stu-id="d527a-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="d527a-107">Dies impliziert jedoch keine Änderung ihrer Sicherheitsposition.</span><span class="sxs-lookup"><span data-stu-id="d527a-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="d527a-108">Informationen zu den neuesten Änderungen finden Sie unter [What es New in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="d527a-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="d527a-109">16. März 2020</span><span class="sxs-lookup"><span data-stu-id="d527a-109">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="d527a-110">Entfernen von Verbesserungs Aktionen, die nicht den Erwartungen für eine zuverlässige Messung entsprechen oder keine sinnvolle Darstellung der Sicherheitsposition bieten</span><span class="sxs-lookup"><span data-stu-id="d527a-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="d527a-111">Um sicherzustellen, dass die Microsoft Secure Score sinnvoll ist und dass jede Verbesserungs Aktion messbar und zuverlässig ist, entfernen wir die folgenden Verbesserungs Aktionen.</span><span class="sxs-lookup"><span data-stu-id="d527a-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="d527a-112">Speichern von Benutzerdokumenten in OneDrive für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d527a-112">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="d527a-113">Einrichten Office 365 Richtlinien für ATP-sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="d527a-113">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="d527a-114">Einrichten Office 365 sicherer Links zum Überprüfen von URLs</span><span class="sxs-lookup"><span data-stu-id="d527a-114">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="d527a-115">Post Fach Delegierung nicht zulassen</span><span class="sxs-lookup"><span data-stu-id="d527a-115">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="d527a-116">Zulassen von anonymen Gast Freigabelinks für Websites und Dokumente</span><span class="sxs-lookup"><span data-stu-id="d527a-116">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="d527a-117">Aktivieren der Cloud-App-Sicherheitskonsole</span><span class="sxs-lookup"><span data-stu-id="d527a-117">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="d527a-118">Konfigurieren der Ablaufzeit für externe Freigabelinks</span><span class="sxs-lookup"><span data-stu-id="d527a-118">Configure expiration time for external sharing links</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="d527a-119">Unterstützen von Sicherheitsstandards für Azure AD Verbesserungs Aktionen</span><span class="sxs-lookup"><span data-stu-id="d527a-119">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="d527a-120">Microsoft Secure Score wird Update Verbesserungs Aktionen zur Unterstützung von [Sicherheitsstandards in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), die es einfacher machen, Ihre Organisation mit vorkonfigurierten Sicherheitseinstellungen für häufige Angriffe zu schützen.</span><span class="sxs-lookup"><span data-stu-id="d527a-120">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="d527a-121">Dies wirkt sich auf die folgenden Verbesserungs Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="d527a-121">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="d527a-122">Sicherstellen, dass alle Benutzer mehrstufige Authentifizierung für sicheren Zugriff ausführen können</span><span class="sxs-lookup"><span data-stu-id="d527a-122">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="d527a-123">MFA für Administratorrollen erforderlich</span><span class="sxs-lookup"><span data-stu-id="d527a-123">Require MFA for administrative roles</span></span>
- <span data-ttu-id="d527a-124">Aktivieren der Richtlinie zum Blockieren der Legacy Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d527a-124">Enable policy to block legacy authentication</span></span>
