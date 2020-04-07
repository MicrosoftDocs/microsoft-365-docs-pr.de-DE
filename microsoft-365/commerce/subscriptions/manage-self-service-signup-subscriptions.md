---
title: Verwalten von Self-Service-Anmelde Abonnements
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
- commerce
- Adm_NonTOC
search.appverid:
- MET150
description: Hier erfahren Sie, wie Sie ﻿kostenlose Self-Service-Anmelde Abonnements für Ihre Organisation verwalten.
ms.openlocfilehash: 056ae95f9f5067ea3fa86164b620c72c84e3aad4
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "43154132"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="687b1-103">Verwalten von Self-Service-Anmelde Abonnements</span><span class="sxs-lookup"><span data-stu-id="687b1-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="687b1-104">Was sind Self-Service-Anmelde Abonnements?</span><span class="sxs-lookup"><span data-stu-id="687b1-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="687b1-105">Es gibt eine beschränkte Anzahl von kostenlosen Self-Service-Anmelde Abonnements, für die sich Benutzer in Ihrer Organisation anmelden können.</span><span class="sxs-lookup"><span data-stu-id="687b1-105">There are a limited number of free self-service sign-up subscriptions that users in your organization can sign up for.</span></span> <span data-ttu-id="687b1-106">Ein Benutzer kann sich nur für sich selbst registrieren und ein Self-Service-Anmelde Abonnement verwenden.</span><span class="sxs-lookup"><span data-stu-id="687b1-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="687b1-107">Diese Abonnements werden auf der Seite **Produkte & Dienste** angezeigt, sind als **kostenlos**gekennzeichnet und weisen einen Hinweis darauf auf, dass "dies ein kostenloses Abonnement ist, das von Benutzern in Ihrem Unternehmen aktiviert wird."</span><span class="sxs-lookup"><span data-stu-id="687b1-107">These subscriptions appear on the **Products & services** page, are marked as **Free**, and have a note that says, "This is a free subscription activated by users in your company."</span></span> <span data-ttu-id="687b1-108">Sie können Self-Service-Anmelde Abonnements verwalten, indem Sie Benutzer daran hindern, sich anzumelden, und indem Sie ﻿Kostenlose Abonnements löschen, für die Benutzer sich angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="687b1-108">You can manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="687b1-109">Weitere Informationen zur Self-Service-Registrierung und den verfügbaren Abonnements finden Sie unter [Verwenden der Self-Service-Registrierung in Ihrer Organisation](../../admin/misc/self-service-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="687b1-109">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="687b1-110">Inwiefern unterscheiden sich diese Abonnements von Self-Service-Abonnements für den Kauf?</span><span class="sxs-lookup"><span data-stu-id="687b1-110">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="687b1-111">Self-Service-Anmelde Abonnements sind kostenlos und stehen für eine größere Produktliste als Self-Service-Abonnements zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="687b1-111">Self-service sign-up subscriptions are free, and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="687b1-112">Wenn sich ein Benutzer für ein Self-Service-Abonnement anmeldet, ist er für die Zahlung verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="687b1-112">When a user signs up for a self-service purchase subscription, they are responsible for paying for it.</span></span> <span data-ttu-id="687b1-113">Außerdem stehen Self-Service Subscription-Abonnements nur für Power Platform-Produkte (Power BI, Power apps und Power Automation) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="687b1-113">Also, self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate).</span></span> <span data-ttu-id="687b1-114">Weitere Informationen finden Sie unter [Self-Service purchase FAQ](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="687b1-114">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="687b1-115">Blockieren der Anmeldung von Benutzern</span><span class="sxs-lookup"><span data-stu-id="687b1-115">Block users from signing up</span></span>

<span data-ttu-id="687b1-116">Verwenden Sie das Cmdlet " [**MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) " mit dem Parameter " **AllowAdHocSubscriptions** ", um zu steuern, ob sich Benutzer für Self-Service-Anmelde Abonnements anmelden können.</span><span class="sxs-lookup"><span data-stu-id="687b1-116">You use the [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="687b1-117">Weitere Informationen finden Sie unter [wie kann ich Self-Service-Einstellungen steuern?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="687b1-117">For more information, see [How do I control self-service settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="687b1-118">Löschen eines Self-Service-Anmelde Abonnements</span><span class="sxs-lookup"><span data-stu-id="687b1-118">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="687b1-119">Wenn Sie ein Self-Service-Anmelde Abonnement löschen, werden alle Benutzer daran gehindert, auf Ihre Daten zuzugreifen und alle Daten und e-Mails zu löschen.</span><span class="sxs-lookup"><span data-stu-id="687b1-119">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="687b1-120">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Produkte & Dienste</a> .</span><span class="sxs-lookup"><span data-stu-id="687b1-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>
2. <span data-ttu-id="687b1-121">Suchen Sie nach dem Self-Service-Anmelde Abonnement, das Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="687b1-121">Find the self-service sign-up subscription that you want to delete.</span></span> <span data-ttu-id="687b1-122">Wählen Sie im Abschnitt **Einstellungen & Aktionen** die Option **Abonnement löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="687b1-122">In the **Settings & Actions** section, select **Delete subscription**.</span></span>
3. <span data-ttu-id="687b1-123">Aktivieren Sie im Bereich **Abonnement löschen** das Kontrollkästchen, und wählen Sie dann **Abonnement löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="687b1-123">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="687b1-124">Ich habe ein Self-Service-Anmelde Abonnement, das das Löschen von Verzeichnissen blockiert.</span><span class="sxs-lookup"><span data-stu-id="687b1-124">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="687b1-125">Die Self-Service-Anmelde Produkte, mit denen sich einzelne Benutzer anmelden können, erstellen auch einen Gastbenutzer für die Authentifizierung in Ihrem Azure AD-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="687b1-125">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="687b1-126">Um Datenverlust zu vermeiden, blockieren diese Self-Service-Produkte Verzeichnis Löschungen, bis Sie vollständig aus dem Verzeichnis gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="687b1-126">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="687b1-127">Sie können nur vom Azure AD Administrator gelöscht werden. Weitere Informationen finden Sie unter [Löschen eines Verzeichnisses in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span><span class="sxs-lookup"><span data-stu-id="687b1-127">They can be deleted only by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>