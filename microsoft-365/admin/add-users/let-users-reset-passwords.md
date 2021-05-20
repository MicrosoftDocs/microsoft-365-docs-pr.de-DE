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
description: Erfahren Sie, wie Sie eine Richtlinie festlegen können, damit Benutzer ihre eigenen Kennwörter mithilfe des Self-Service-Kennwortzurücksetzungstools zurücksetzen können.
ms.openlocfilehash: 2c79d5611ab2db00f4de5f227b0ec2f411955558
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571853"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="ad95d-103">Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten</span><span class="sxs-lookup"><span data-stu-id="ad95d-103">Let users reset their own passwords</span></span>

<span data-ttu-id="ad95d-104">Als Microsoft 365 Admin können Sie Es können Personen zulassen, dass sie das [Self-Service-Kennwort-Reset-Tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) verwenden, sodass Sie keine Kennwörter für sie zurücksetzen müssen.</span><span class="sxs-lookup"><span data-stu-id="ad95d-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="ad95d-105">Geringerer Arbeitsaufwand!</span><span class="sxs-lookup"><span data-stu-id="ad95d-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="ad95d-106">Bevor Sie loslegen</span><span class="sxs-lookup"><span data-stu-id="ad95d-106">Before you begin</span></span>
  
- <span data-ttu-id="ad95d-107">Sie erhalten Self-Service-Passwort-Reset für Cloud-Benutzer **kostenlos** mit jedem Microsoft 365 Business-, Bildungs- oder Non-Profit-Kosten-Plan.</span><span class="sxs-lookup"><span data-stu-id="ad95d-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="ad95d-108">Es funktioniert nicht mit Microsoft 365 Test.</span><span class="sxs-lookup"><span data-stu-id="ad95d-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="ad95d-p103">Hierfür wird Azure verwendet. Sie erhalten dieses Feature in Azure automatisch **kostenlos**, wenn Sie diese Schritte ausführen. Die Aktivierung der Self-Service-Kennwortzurücksetzung kostet Sie nichts, falls Sie keine weiteren Azure-Features verwenden.</span><span class="sxs-lookup"><span data-stu-id="ad95d-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="ad95d-112">**Wenn Sie ein lokal ansässiges Active Directory verwenden,** gelten die beiden oben genannten Punkte nicht.</span><span class="sxs-lookup"><span data-stu-id="ad95d-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="ad95d-113">Sie können dies vielmehr einrichten, es ist jedoch **ein kostenpflichtiges Abonnement für Azure AD Premium** erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ad95d-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="ad95d-114">Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen.</span><span class="sxs-lookup"><span data-stu-id="ad95d-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="ad95d-115">Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="ad95d-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="ad95d-116">Was ist ein Administratorkonto?</span><span class="sxs-lookup"><span data-stu-id="ad95d-116">What's an admin account?</span></span>](../../business-video/admin-center-overview.md)

<span data-ttu-id="ad95d-117">Sie müssen ein [globaler Administrator oder Kennwortadministrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="ad95d-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="ad95d-118">Sehen Sie: Lassen Sie Benutzer ihre eigenen Passwörter zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="ad95d-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="ad95d-119">Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](../../business-video/index.yml) an.</span><span class="sxs-lookup"><span data-stu-id="ad95d-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="ad95d-120">Schritte: Lassen Sie Menschen ihre eigenen Passwörter zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="ad95d-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="ad95d-121">Mit diesen Schritten aktivieren Sie die Self-Service-Kennwortzurücksetzung für jeden Benutzer in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="ad95d-121">These steps turn on self-service password reset for everyone in your business.</span></span>

1. <span data-ttu-id="ad95d-122">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a>zur Seite   >  **Einstellungen-Organisationseinstellungen.**</span><span class="sxs-lookup"><span data-stu-id="ad95d-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

2. <span data-ttu-id="ad95d-123">Wählen Sie oben auf der Seite **"Org-Einstellungen"** die Registerkarte **Sicherheit & Datenschutz** aus.</span><span class="sxs-lookup"><span data-stu-id="ad95d-123">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="ad95d-124">Wählen Sie **Self-Service Password Reset**.</span><span class="sxs-lookup"><span data-stu-id="ad95d-124">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="ad95d-125">Wählen Sie unter **Self-Service-Kennwortzurücksetzung** aus, und wählen Sie **Zum Azure-Portal wechseln aus, um das Zurücksetzen von Self-Service-Kennwörtern zu aktivieren.**</span><span class="sxs-lookup"><span data-stu-id="ad95d-125">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="ad95d-126">Wählen Sie im linken Navigationsbereich **Benutzer** aus, und dann im **| Alle Benutzer** Seite, wählen **Kennwort zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="ad95d-126">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="ad95d-127">Wählen Sie auf der Seite **Eigenschaften** **alle** aus, um sie für alle Benutzer in Ihrem Unternehmen zu aktivieren, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="ad95d-127">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="ad95d-128">Wenn sich Ihre Benutzer anmelden, werden sie aufgefordert, zusätzliche Kontaktinformationen einzugeben, die ihnen helfen, ihr Kennwort in Zukunft zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="ad95d-128">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="ad95d-129">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="ad95d-129">Related content</span></span>

<span data-ttu-id="ad95d-130">[Festlegen der Kennwortablaufrichtlinie für Ihre Organisation](../manage/set-password-expiration-policy.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="ad95d-130">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>

<span data-ttu-id="ad95d-131">[Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft](set-password-to-never-expire.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="ad95d-131">[Set an individual user's password to never expire](set-password-to-never-expire.md) (article)</span></span>

<span data-ttu-id="ad95d-132">[Microsoft 365 Business Schulungsvideos](../../business-video/index.yml) (Linkseite)</span><span class="sxs-lookup"><span data-stu-id="ad95d-132">[Microsoft 365 Business training videos](../../business-video/index.yml) (link page)</span></span>
