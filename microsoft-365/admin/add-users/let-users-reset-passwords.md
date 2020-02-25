---
title: Zulassen, dass Benutzer ihre eigenen Kennwörter in Office 365 zurücksetzen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.openlocfilehash: 87accc393d08b922ebc3f75ef1aa5ddb2d0b2955
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241604"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="38d71-103">Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten</span><span class="sxs-lookup"><span data-stu-id="38d71-103">Let users reset their own passwords</span></span>

<span data-ttu-id="38d71-104">Werden Sie öfter von Personen bedrängt, die Sie bitten, ihre Kennwörter zurückzusetzen?</span><span class="sxs-lookup"><span data-stu-id="38d71-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="38d71-105">Als Microsoft 365-Administrator können Sie Benutzern das [Tool zum Zurücksetzen von Self-Service-Kennwörtern](https://go.microsoft.com/fwlink/p/?LinkId=522677) zur Verfügung stellen, damit Sie keine Kennwörter für diese zurücksetzen müssen.</span><span class="sxs-lookup"><span data-stu-id="38d71-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="38d71-106">Geringerer Arbeitsaufwand!</span><span class="sxs-lookup"><span data-stu-id="38d71-106">Less work for you!</span></span> 
  
<span data-ttu-id="38d71-107">Hier sind ein paar Dinge, die Sie wissen müssen:</span><span class="sxs-lookup"><span data-stu-id="38d71-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="38d71-p102">In jedem kostenpflichtigen Office 365 Business-, Education- oder Non-Profit-Plan ist die Self-Service-Kennwortzurücksetzung für Cloudbenutzer **kostenlos**. In der Office 365-Testversion funktioniert sie jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="38d71-p102">You get self-service password reset for cloud users **free** with any Office 365 business, education, or nonprofit paid plan. It doesn't work with Office 365 trial.</span></span> 
    
- <span data-ttu-id="38d71-p103">Hierfür wird Azure verwendet. Sie erhalten dieses Feature in Azure automatisch **kostenlos**, wenn Sie diese Schritte ausführen. Die Aktivierung der Self-Service-Kennwortzurücksetzung kostet Sie nichts, falls Sie keine weiteren Azure-Features verwenden.</span><span class="sxs-lookup"><span data-stu-id="38d71-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="38d71-113">**Wenn Sie eine lokale Active Directory verwenden**, gelten die beiden folgenden Punkte nicht.</span><span class="sxs-lookup"><span data-stu-id="38d71-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="38d71-114">Stattdessen können Sie dies einrichten, **es ist jedoch ein kostenpflichtiges Abonnement für Azure AD Premium erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="38d71-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="38d71-115">Sehen Sie sich ein kurzes Video an, in dem Benutzer ihre eigenen Kennwörter zurücksetzen lassen.</span><span class="sxs-lookup"><span data-stu-id="38d71-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="38d71-116">Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816), an.</span><span class="sxs-lookup"><span data-stu-id="38d71-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="38d71-117">Zulassen, dass Benutzer ihre eigenen Kennwörter zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="38d71-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="38d71-118">Mit diesen Schritten aktivieren Sie die Self-Service-Kennwortzurücksetzung für jeden Benutzer in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="38d71-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1.  <span data-ttu-id="38d71-119">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Sicherheit & Privatsphäre</a> .</span><span class="sxs-lookup"><span data-stu-id="38d71-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="38d71-120">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a>zur Seite **Einstellungen** \> - **Sicherheits &amp; Datenschutz** .</span><span class="sxs-lookup"><span data-stu-id="38d71-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="38d71-121">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>zur Seite **Einstellungen** \> - **Sicherheits &amp; Datenschutz** .</span><span class="sxs-lookup"><span data-stu-id="38d71-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="38d71-122">Wählen Sie unter zulassen, dass **Ihre Personen Ihre eigenen Kennwörter zurücksetzen**die Verknüpfung für das **Azure AD Admin Center**aus.</span><span class="sxs-lookup"><span data-stu-id="38d71-122">Under **Let your people reset their own passwords**, select the link for the **Azure AD admin center**.</span></span> <span data-ttu-id="38d71-123">Azure wird kostenlos zur Verfügung gestellt!</span><span class="sxs-lookup"><span data-stu-id="38d71-123">You'll get Azure for free!</span></span>
  
3. <span data-ttu-id="38d71-124">Wählen Sie im linken Navigationsbereich die Option **Benutzer** aus, und wählen Sie dann **Kennwortzurücksetzung**aus.</span><span class="sxs-lookup"><span data-stu-id="38d71-124">Select **Users** in the left navigation, and then select **Password reset**.</span></span>
  
4. <span data-ttu-id="38d71-125">Wählen Sie auf der Seite Eigenschaften die Option **alle** aus, um Sie für alle Benutzer in Ihrem Unternehmen zu aktivieren, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="38d71-125">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="38d71-126">Wenn sich Ihre Benutzer bei Office 365 anmelden, werden sie zur Eingabe zusätzlicher Kontaktinformationen aufgefordert, mit denen sie ihr Kennwort künftig zurücksetzen können.</span><span class="sxs-lookup"><span data-stu-id="38d71-126">When your users sign in to Office 365, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="38d71-127">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="38d71-127">Related articles</span></span>

[<span data-ttu-id="38d71-128">Festlegen der Kennwortablaufrichtlinie für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="38d71-128">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="38d71-129">Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft</span><span class="sxs-lookup"><span data-stu-id="38d71-129">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="38d71-130">Microsoft 365 Business-Schulungsvideos</span><span class="sxs-lookup"><span data-stu-id="38d71-130">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
