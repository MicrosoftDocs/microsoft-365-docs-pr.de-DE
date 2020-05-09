---
title: Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Erfahren Sie, wie Sie Ihre Kennwörter mithilfe des Self-Service-Kenn Wort Zurücksetzungs Tools zurücksetzen können.
ms.openlocfilehash: 01099f6f678bbaa3b163ac59e0417614352e0e97
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173530"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="eed66-103">Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten</span><span class="sxs-lookup"><span data-stu-id="eed66-103">Let users reset their own passwords</span></span>

<span data-ttu-id="eed66-104">Werden Sie öfter von Personen bedrängt, die Sie bitten, ihre Kennwörter zurückzusetzen?</span><span class="sxs-lookup"><span data-stu-id="eed66-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="eed66-105">Als Microsoft 365-Administrator können Sie Benutzern das [Tool zum Zurücksetzen von Self-Service-Kennwörtern](https://go.microsoft.com/fwlink/p/?LinkId=522677) zur Verfügung stellen, damit Sie keine Kennwörter für diese zurücksetzen müssen.</span><span class="sxs-lookup"><span data-stu-id="eed66-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="eed66-106">Geringerer Arbeitsaufwand!</span><span class="sxs-lookup"><span data-stu-id="eed66-106">Less work for you!</span></span> 
  
<span data-ttu-id="eed66-107">Hier sind ein paar Dinge, die Sie wissen müssen:</span><span class="sxs-lookup"><span data-stu-id="eed66-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="eed66-108">Sie erhalten Self-Service Password Reset für Cloud- **Benutzer mit** einem beliebigen Microsoft 365 Business-, Education-oder gemeinnützigen kostenpflichtigen Plan.</span><span class="sxs-lookup"><span data-stu-id="eed66-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="eed66-109">Sie funktioniert nicht mit der Microsoft 365-Testversion.</span><span class="sxs-lookup"><span data-stu-id="eed66-109">It doesn't work with Microsoft 365 trial.</span></span> 
    
- <span data-ttu-id="eed66-p103">Hierfür wird Azure verwendet. Sie erhalten dieses Feature in Azure automatisch **kostenlos**, wenn Sie diese Schritte ausführen. Die Aktivierung der Self-Service-Kennwortzurücksetzung kostet Sie nichts, falls Sie keine weiteren Azure-Features verwenden.</span><span class="sxs-lookup"><span data-stu-id="eed66-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="eed66-113">**Wenn Sie eine lokale Active Directory verwenden**, gelten die beiden folgenden Punkte nicht.</span><span class="sxs-lookup"><span data-stu-id="eed66-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="eed66-114">Stattdessen können Sie dies einrichten, **es ist jedoch ein kostenpflichtiges Abonnement für Azure AD Premium erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="eed66-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="eed66-115">Sehen Sie sich ein kurzes Video an, in dem Benutzer ihre eigenen Kennwörter zurücksetzen lassen.</span><span class="sxs-lookup"><span data-stu-id="eed66-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="eed66-116">Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816), an.</span><span class="sxs-lookup"><span data-stu-id="eed66-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="eed66-117">Zulassen, dass Benutzer ihre eigenen Kennwörter zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="eed66-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="eed66-118">Mit diesen Schritten aktivieren Sie die Self-Service-Kennwortzurücksetzung für jeden Benutzer in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="eed66-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1. <span data-ttu-id="eed66-119">Wechseln Sie im Admin Center zur Seite **Einstellungs** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Einstellungen.</a></span><span class="sxs-lookup"><span data-stu-id="eed66-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="eed66-120">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a>zur Seite **Einstellungen** \> - **Sicherheits &amp; Datenschutz** .</span><span class="sxs-lookup"><span data-stu-id="eed66-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="eed66-121">**Settings** \> Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">im Admin Center</a>zur Seite mit den Einstellungen für die **Sicherheit &amp; der Datenschutz** **Optionen** \>.</span><span class="sxs-lookup"><span data-stu-id="eed66-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="eed66-122">Wählen Sie oben auf der Seite Einstellungen die Option **Sicherheit & Datenschutz**aus.</span><span class="sxs-lookup"><span data-stu-id="eed66-122">At the top of the Settings page select **Security & Privacy**.</span></span>
  
3. <span data-ttu-id="eed66-123">Wählen Sie **Self-Service Password Reset**aus.</span><span class="sxs-lookup"><span data-stu-id="eed66-123">Select **Self Service Password Reset**.</span></span>
  
4. <span data-ttu-id="eed66-124">Wählen Sie auf der Seite Eigenschaften die Option **alle** aus, um Sie für alle Benutzer in Ihrem Unternehmen zu aktivieren, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="eed66-124">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="eed66-125">Wenn sich Ihre Benutzer anmelden, werden Sie aufgefordert, zusätzliche Kontaktinformationen einzugeben, mit denen Sie Ihr Kennwort in Zukunft zurücksetzen können.</span><span class="sxs-lookup"><span data-stu-id="eed66-125">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="eed66-126">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="eed66-126">Related articles</span></span>

[<span data-ttu-id="eed66-127">Festlegen der Kennwortablaufrichtlinie für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="eed66-127">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="eed66-128">Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft</span><span class="sxs-lookup"><span data-stu-id="eed66-128">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="eed66-129">Microsoft 365 Business-Schulungsvideos</span><span class="sxs-lookup"><span data-stu-id="eed66-129">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
