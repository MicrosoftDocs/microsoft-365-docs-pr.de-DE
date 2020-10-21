---
title: Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Erfahren Sie, wie Sie Ihre Kennwörter mithilfe des Self-Service-Kenn Wort Zurücksetzungs Tools zurücksetzen können.
ms.openlocfilehash: 7ecadaa42610e0b77dc1727c11140080bd7b1779
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646679"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="2393d-103">Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten</span><span class="sxs-lookup"><span data-stu-id="2393d-103">Let users reset their own passwords</span></span>

<span data-ttu-id="2393d-104">Als Microsoft 365-Administrator können Sie Benutzern das [Tool zum Zurücksetzen von Self-Service-Kennwörtern](https://go.microsoft.com/fwlink/p/?LinkId=522677) zur Verfügung stellen, damit Sie keine Kennwörter für diese zurücksetzen müssen.</span><span class="sxs-lookup"><span data-stu-id="2393d-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="2393d-105">Geringerer Arbeitsaufwand!</span><span class="sxs-lookup"><span data-stu-id="2393d-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="2393d-106">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="2393d-106">Before you begin</span></span>
  
- <span data-ttu-id="2393d-107">Sie erhalten Self-Service Password Reset für Cloud- **Benutzer mit** einem beliebigen Microsoft 365 Business-, Education-oder gemeinnützigen kostenpflichtigen Plan.</span><span class="sxs-lookup"><span data-stu-id="2393d-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="2393d-108">Sie funktioniert nicht mit der Microsoft 365-Testversion.</span><span class="sxs-lookup"><span data-stu-id="2393d-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="2393d-p103">Hierfür wird Azure verwendet. Sie erhalten dieses Feature in Azure automatisch **kostenlos**, wenn Sie diese Schritte ausführen. Die Aktivierung der Self-Service-Kennwortzurücksetzung kostet Sie nichts, falls Sie keine weiteren Azure-Features verwenden.</span><span class="sxs-lookup"><span data-stu-id="2393d-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="2393d-112">**Wenn Sie eine lokale Active Directory verwenden**, gelten die beiden folgenden Punkte nicht.</span><span class="sxs-lookup"><span data-stu-id="2393d-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="2393d-113">Stattdessen können Sie dies einrichten, **es ist jedoch ein kostenpflichtiges Abonnement für Azure AD Premium erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="2393d-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="2393d-114">Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen.</span><span class="sxs-lookup"><span data-stu-id="2393d-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="2393d-115">Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="2393d-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="2393d-116">Was ist ein Administratorkonto?</span><span class="sxs-lookup"><span data-stu-id="2393d-116">What's an admin account?</span></span>](../admin-overview/admin-overview.md)

<span data-ttu-id="2393d-117">Sie müssen ein [globaler Administrator oder Kenn Wort Administrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="2393d-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="2393d-118">Watch: Benutzer können Ihre eigenen Kennwörter zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="2393d-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="2393d-119">Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816), an.</span><span class="sxs-lookup"><span data-stu-id="2393d-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="2393d-120">Schritte: zulassen, dass Benutzer ihre eigenen Kennwörter zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="2393d-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="2393d-121">Mit diesen Schritten aktivieren Sie die Self-Service-Kennwortzurücksetzung für jeden Benutzer in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="2393d-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="2393d-122">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a>zur Seite **Einstellungen** für > **Organisations** Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="2393d-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="2393d-123">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a>zur Seite **Einstellungen** - \> **Sicherheits &amp; Datenschutz** .</span><span class="sxs-lookup"><span data-stu-id="2393d-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="2393d-124">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>zur Seite mit den **Einstellungen** für die \> **Settings** \> **Sicherheit der &amp; Datenschutz** Optionen.</span><span class="sxs-lookup"><span data-stu-id="2393d-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="2393d-125">Wählen Sie oben auf der Seite " **org-Einstellungen** " die Registerkarte **Sicherheit & Datenschutz** aus.</span><span class="sxs-lookup"><span data-stu-id="2393d-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="2393d-126">Wählen Sie **Self-Service Password Reset**aus.</span><span class="sxs-lookup"><span data-stu-id="2393d-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="2393d-127">Wählen Sie unter **Self-Service Password Reset** **die Option zum Azure-Portal wechseln aus, um Self-Service Password Reset zu aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="2393d-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="2393d-128">Wählen Sie im linken Navigationsbereich **Benutzer**aus, und klicken Sie dann auf der Seite **Benutzer | Seite "alle Benutzer" die** Option **Kennwort zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="2393d-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="2393d-129">Wählen Sie auf der Seite **Eigenschaften** die Option **alle** aus, um Sie für alle Benutzer in Ihrem Unternehmen zu aktivieren, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="2393d-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="2393d-130">Wenn sich Ihre Benutzer anmelden, werden Sie aufgefordert, zusätzliche Kontaktinformationen einzugeben, mit denen Sie Ihr Kennwort in Zukunft zurücksetzen können.</span><span class="sxs-lookup"><span data-stu-id="2393d-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="2393d-131">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="2393d-131">Related content</span></span>

[<span data-ttu-id="2393d-132">Festlegen der Kennwortablaufrichtlinie für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="2393d-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="2393d-133">Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft</span><span class="sxs-lookup"><span data-stu-id="2393d-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="2393d-134">Microsoft 365 Business-Schulungsvideos</span><span class="sxs-lookup"><span data-stu-id="2393d-134">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
