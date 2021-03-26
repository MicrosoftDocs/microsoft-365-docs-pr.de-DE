---
title: Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Erfahren Sie, wie Sie Ihre Kennwörter mithilfe des Self-Service-Kennwortzurücksetzungstools zurücksetzen können.
ms.openlocfilehash: f43c409e98aa98e942bd7c7cbb15302422df241d
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222123"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="e35f5-103">Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten</span><span class="sxs-lookup"><span data-stu-id="e35f5-103">Let users reset their own passwords</span></span>

<span data-ttu-id="e35f5-104">Als Microsoft 365-Administrator können Sie es Personen gestatten, das [Self-Service-Kennwortzurücksetzungstool](https://go.microsoft.com/fwlink/p/?LinkId=522677) zu verwenden, damit Sie keine Kennwörter für sie zurücksetzen müssen.</span><span class="sxs-lookup"><span data-stu-id="e35f5-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="e35f5-105">Geringerer Arbeitsaufwand!</span><span class="sxs-lookup"><span data-stu-id="e35f5-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="e35f5-106">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="e35f5-106">Before you begin</span></span>
  
- <span data-ttu-id="e35f5-107">Sie erhalten die Self-Service-Kennwortzurücksetzung für Cloudbenutzer kostenlos mit einem beliebigen kostenpflichtigen Microsoft 365-Geschäfts-, Bildungs- oder gemeinnützigen Plan. </span><span class="sxs-lookup"><span data-stu-id="e35f5-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="e35f5-108">Es funktioniert nicht mit Microsoft 365-Testversion.</span><span class="sxs-lookup"><span data-stu-id="e35f5-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="e35f5-p103">Hierfür wird Azure verwendet. Sie erhalten dieses Feature in Azure automatisch **kostenlos**, wenn Sie diese Schritte ausführen. Die Aktivierung der Self-Service-Kennwortzurücksetzung kostet Sie nichts, falls Sie keine weiteren Azure-Features verwenden.</span><span class="sxs-lookup"><span data-stu-id="e35f5-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="e35f5-112">**Wenn Sie ein lokales Active Directory verwenden,** gelten die beiden oben genannten Punkte nicht.</span><span class="sxs-lookup"><span data-stu-id="e35f5-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="e35f5-113">Stattdessen können Sie dies einrichten, **aber es erfordert ein kostenpflichtiges Abonnement für Azure AD Premium.**</span><span class="sxs-lookup"><span data-stu-id="e35f5-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="e35f5-114">Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen.</span><span class="sxs-lookup"><span data-stu-id="e35f5-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="e35f5-115">Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="e35f5-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="e35f5-116">Was ist ein Administratorkonto?</span><span class="sxs-lookup"><span data-stu-id="e35f5-116">What's an admin account?</span></span>](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview)

<span data-ttu-id="e35f5-117">Sie müssen ein globaler [Administrator oder Kennwortadministrator sein,](about-admin-roles.md) um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="e35f5-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="e35f5-118">Watch: Benutzer können ihre eigenen Kennwörter zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="e35f5-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="e35f5-119">Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) an.</span><span class="sxs-lookup"><span data-stu-id="e35f5-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="e35f5-120">Schritte: Personen können ihre eigenen Kennwörter zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="e35f5-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="e35f5-121">Mit diesen Schritten aktivieren Sie die Self-Service-Kennwortzurücksetzung für jeden Benutzer in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="e35f5-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="e35f5-122">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">im Admin Center</a>zur **Einstellungsseite** > **"Organisationseinstellungen".**</span><span class="sxs-lookup"><span data-stu-id="e35f5-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e35f5-123">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">im Admin Center</a>zur Seite **Einstellungen** \> **Sicherheit &amp; Datenschutz.**</span><span class="sxs-lookup"><span data-stu-id="e35f5-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e35f5-124">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">im Admin Center</a>zur Seite **Einstellungen** \> **Einstellungen** \> **Sicherheit &amp; Datenschutz.**</span><span class="sxs-lookup"><span data-stu-id="e35f5-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="e35f5-125">Wählen Sie oben auf der Seite **Organisationseinstellungen** die Registerkarte **Sicherheit & Datenschutz** aus.</span><span class="sxs-lookup"><span data-stu-id="e35f5-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="e35f5-126">Wählen **Sie Self-Service Password Reset aus.**</span><span class="sxs-lookup"><span data-stu-id="e35f5-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="e35f5-127">Wählen **Sie unter Self-Service password reset** die Option Wechseln zum Azure-Portal aus, um die **Self-Service-Kennwortzurücksetzung zu aktivieren.**</span><span class="sxs-lookup"><span data-stu-id="e35f5-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="e35f5-128">Wählen Sie im linken Navigationsbereich **Benutzer** aus, und wählen Sie dann auf der Seite **Benutzer | Wählen Sie auf** der Seite Alle Benutzer die Option **Kennwortzurücksetzung aus.**</span><span class="sxs-lookup"><span data-stu-id="e35f5-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="e35f5-129">Wählen Sie **auf** der Seite Eigenschaften **alle** aus, um es für alle Benutzer in Ihrem Unternehmen zu aktivieren, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="e35f5-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="e35f5-130">Wenn sich Ihre Benutzer anmelden, werden sie aufgefordert, zusätzliche Kontaktinformationen einzugeben, mit denen sie ihr Kennwort in Zukunft zurücksetzen können.</span><span class="sxs-lookup"><span data-stu-id="e35f5-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="e35f5-131">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="e35f5-131">Related content</span></span>

[<span data-ttu-id="e35f5-132">Festlegen der Kennwortablaufrichtlinie für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="e35f5-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="e35f5-133">Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft</span><span class="sxs-lookup"><span data-stu-id="e35f5-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="e35f5-134">Microsoft 365 Business-Schulungsvideos</span><span class="sxs-lookup"><span data-stu-id="e35f5-134">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
