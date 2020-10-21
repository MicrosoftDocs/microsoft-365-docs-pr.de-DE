---
title: Verwalten von Self-Service-Anmelde Abonnements
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
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Hier erfahren Sie, wie Sie ﻿kostenlose Self-Service-Anmelde Abonnements für Ihre Organisation verwalten.
ms.openlocfilehash: fb70d0c40d4358abc227c8f6ff4a0e0dce1a7265
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48647831"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="57d41-103">Verwalten von Self-Service-Anmelde Abonnements</span><span class="sxs-lookup"><span data-stu-id="57d41-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="57d41-104">Was sind Self-Service-Anmelde Abonnements?</span><span class="sxs-lookup"><span data-stu-id="57d41-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="57d41-105">Es gibt eine beschränkte Anzahl von kostenlosen Self-Service-Anmelde Abonnements, für die sich Benutzer in Ihrer Organisation anmelden können.</span><span class="sxs-lookup"><span data-stu-id="57d41-105">There are a limited number of free self-service sign-up subscriptions that users in your organization can sign up for.</span></span> <span data-ttu-id="57d41-106">Ein Benutzer kann sich nur für sich selbst registrieren und ein Self-Service-Anmelde Abonnement verwenden.</span><span class="sxs-lookup"><span data-stu-id="57d41-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="57d41-107">Diese Abonnements werden auf der Seite **Ihre Produkte** angezeigt, als **kostenlos**gekennzeichnet und weisen darauf hin, dass es sich um ein kostenloses Abonnement handelt, das von Benutzern in Ihrem Unternehmen aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="57d41-107">These subscriptions appear on the **Your products** page, are marked as **Free**, and have a note that says, "This is a free subscription activated by users in your company."</span></span> <span data-ttu-id="57d41-108">Sie können Self-Service-Anmelde Abonnements verwalten, indem Sie Benutzer daran hindern, sich anzumelden, und indem Sie ﻿Kostenlose Abonnements löschen, für die Benutzer sich angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="57d41-108">You can manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="57d41-109">Weitere Informationen zur Self-Service-Registrierung und den verfügbaren Abonnements finden Sie unter [Verwenden der Self-Service-Registrierung in Ihrer Organisation](../../admin/misc/self-service-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="57d41-109">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="57d41-110">Inwiefern unterscheiden sich diese Abonnements von Self-Service-Abonnements für den Kauf?</span><span class="sxs-lookup"><span data-stu-id="57d41-110">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="57d41-111">Self-Service-Anmelde Abonnements sind kostenlos und stehen für eine größere Produktliste als Self-Service-Abonnements zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="57d41-111">Self-service sign-up subscriptions are free, and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="57d41-112">Wenn sich ein Benutzer für ein Self-Service-Abonnement anmeldet, ist er für die Zahlung verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="57d41-112">When a user signs up for a self-service purchase subscription, they are responsible for paying for it.</span></span> <span data-ttu-id="57d41-113">Außerdem stehen Self-Service Subscription-Abonnements nur für Power Platform-Produkte (Power BI, Power apps und Power Automation) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="57d41-113">Also, self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate).</span></span> <span data-ttu-id="57d41-114">Weitere Informationen finden Sie unter [Self-Service purchase FAQ](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="57d41-114">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="57d41-115">Blockieren der Anmeldung von Benutzern</span><span class="sxs-lookup"><span data-stu-id="57d41-115">Block users from signing up</span></span>

<span data-ttu-id="57d41-116">Verwenden Sie das Cmdlet " [**MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) " mit dem Parameter " **AllowAdHocSubscriptions** ", um zu steuern, ob sich Benutzer für Self-Service-Anmelde Abonnements anmelden können.</span><span class="sxs-lookup"><span data-stu-id="57d41-116">You use the [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="57d41-117">Weitere Informationen finden Sie unter [wie kann ich Self-Service-Einstellungen steuern?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="57d41-117">For more information, see [How do I control self-service settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="57d41-118">Löschen eines Self-Service-Anmelde Abonnements</span><span class="sxs-lookup"><span data-stu-id="57d41-118">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="57d41-119">Wenn Sie ein Self-Service-Anmelde Abonnement löschen, werden alle Benutzer daran gehindert, auf Ihre Daten zuzugreifen und alle Daten und e-Mails zu löschen.</span><span class="sxs-lookup"><span data-stu-id="57d41-119">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="57d41-120">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="57d41-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="57d41-121">Suchen Sie nach dem Self-Service-Anmelde Abonnement, das Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="57d41-121">Find the self-service sign-up subscription that you want to delete.</span></span> <span data-ttu-id="57d41-122">Wählen Sie im Abschnitt **Einstellungen & Aktionen** die Option **Abonnement löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="57d41-122">In the **Settings & Actions** section, select **Delete subscription**.</span></span>
3. <span data-ttu-id="57d41-123">Aktivieren Sie im Bereich **Abonnement löschen** das Kontrollkästchen, und wählen Sie dann **Abonnement löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="57d41-123">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="57d41-124">Ich habe ein Self-Service-Anmelde Abonnement, das das Löschen von Verzeichnissen blockiert.</span><span class="sxs-lookup"><span data-stu-id="57d41-124">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="57d41-125">Die Self-Service-Anmelde Produkte, mit denen sich einzelne Benutzer anmelden können, erstellen auch einen Gastbenutzer für die Authentifizierung in Ihrem Azure AD-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="57d41-125">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="57d41-126">Um Datenverlust zu vermeiden, blockieren diese Self-Service-Produkte Verzeichnis Löschungen, bis Sie vollständig aus dem Verzeichnis gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="57d41-126">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="57d41-127">Sie können nur vom Azure AD Administrator gelöscht werden. Weitere Informationen finden Sie unter [Löschen eines Verzeichnisses in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span><span class="sxs-lookup"><span data-stu-id="57d41-127">They can be deleted only by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>