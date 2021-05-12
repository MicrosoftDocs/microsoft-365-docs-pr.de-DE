---
title: Verwalten von Self-Service-Anmeldeabonnements
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Erfahren Sie, wie Sie kostenlose Self-Service-Anmeldeabonnements für Ihre Organisation verwalten.
ms.date: 03/17/2021
ms.openlocfilehash: b469515a649399c71ef64ba2567dfa376f21e9a7
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333218"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="77abc-103">Verwalten von Self-Service-Anmeldeabonnements</span><span class="sxs-lookup"><span data-stu-id="77abc-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="77abc-104">Was sind Self-Service-Anmeldeabonnements?</span><span class="sxs-lookup"><span data-stu-id="77abc-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="77abc-105">Es gibt eine begrenzte Anzahl kostenloser Self-Service-Anmeldeabonnements, für die sich Benutzer in Ihrer Organisation registrieren können.</span><span class="sxs-lookup"><span data-stu-id="77abc-105">There are a limited number of free self-service sign-up subscriptions available for users in your organization to sign up for.</span></span> <span data-ttu-id="77abc-106">Ein Benutzer kann sich nur für sich selbst registrieren und ein Self-Service-Anmeldeabonnement verwenden.</span><span class="sxs-lookup"><span data-stu-id="77abc-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="77abc-107">Sie verwalten Self-Service-Anmeldeabonnements, indem Sie Die Anmeldung von Benutzern blockieren und kostenlose Abonnements löschen, für die sich Benutzer angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="77abc-107">You manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="77abc-108">Weitere Informationen zur Self-Service-Anmeldung und den verfügbaren Abonnements finden Sie unter [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="77abc-108">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a><span data-ttu-id="77abc-109">Anzeigen einer Liste der Self-Service-Anmeldeabonnements</span><span class="sxs-lookup"><span data-stu-id="77abc-109">View a list of self-service sign-up subscriptions</span></span>

1. <span data-ttu-id="77abc-110">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="77abc-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="77abc-111">Wählen Sie **auf der** Registerkarte Produkte das Filtersymbol aus, und wählen Sie dann **Frei aus.**</span><span class="sxs-lookup"><span data-stu-id="77abc-111">On the **Products** tab, select the filter icon, then select **Free**.</span></span> <span data-ttu-id="77abc-112">Eine Liste aller Self-Service-Anmeldeabonnements wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="77abc-112">A list of all self-service sign-up subscriptions is displayed.</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="77abc-113">Wie unterscheiden sich diese Abonnements von Self-Service-Kaufabonnements?</span><span class="sxs-lookup"><span data-stu-id="77abc-113">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="77abc-114">Self-Service-Anmeldeabonnements sind kostenlos und stehen für eine größere Liste von Produkten zur Verfügung als Self-Service-Kaufabonnements.</span><span class="sxs-lookup"><span data-stu-id="77abc-114">Self-service sign-up subscriptions are free and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="77abc-115">Wenn sich ein Benutzer für ein Self-Service-Kaufabonnement einschreibt, ist er für die Zahlung verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="77abc-115">When a user signs up for a self-service purchase subscription, they're responsible for paying for it.</span></span> <span data-ttu-id="77abc-116">Self-Service-Kaufabonnements sind nur für Power Platform-Produkte (Power BI, Power Apps und Power Automate), Project und Visio verfügbar.</span><span class="sxs-lookup"><span data-stu-id="77abc-116">Self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span> <span data-ttu-id="77abc-117">Weitere Informationen finden Sie unter Häufig gestellte Fragen [zum Self-Service-Kauf.](self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="77abc-117">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="77abc-118">Blockieren der Anmeldung von Benutzern</span><span class="sxs-lookup"><span data-stu-id="77abc-118">Block users from signing up</span></span>

<span data-ttu-id="77abc-119">Sie verwenden das [**Cmdlet Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) mit dem **Parameter AllowAdHocSubscriptions,** um zu steuern, ob Sich Benutzer für Self-Service-Anmeldeabonnements registrieren können.</span><span class="sxs-lookup"><span data-stu-id="77abc-119">You use the [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="77abc-120">Weitere Informationen finden Sie unter [How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="77abc-120">For more information, see [How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="77abc-121">Löschen eines Self-Service-Anmeldeabonnements</span><span class="sxs-lookup"><span data-stu-id="77abc-121">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77abc-122">Wenn Sie ein Self-Service-Anmeldeabonnement löschen, blockieren Sie alle Benutzer am Zugriff auf ihre Daten und E-Mails und löschen alle Daten und E-Mails.</span><span class="sxs-lookup"><span data-stu-id="77abc-122">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="77abc-123">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="77abc-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="77abc-124">Wählen Sie **auf der** Registerkarte Produkte das Filtersymbol aus, und wählen Sie dann **Frei aus.**</span><span class="sxs-lookup"><span data-stu-id="77abc-124">On the **Products** tab, select the filter icon, then select **Free**.</span></span>
3. <span data-ttu-id="77abc-125">Wählen Sie das Self-Service-Anmeldeabonnement aus, das Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="77abc-125">Select the self-service sign-up subscription that you want to delete.</span></span> 
4. <span data-ttu-id="77abc-126">Wählen Sie auf der Seite Abonnementdetails im Abschnitt **Abonnements und** Zahlungseinstellungen Abonnement **löschen aus.**</span><span class="sxs-lookup"><span data-stu-id="77abc-126">On the subscription details page, in the **Subscriptions and payment settings** section, select **Delete subscription**.</span></span>
5. <span data-ttu-id="77abc-127">Aktivieren Sie **im Bereich** Abonnement löschen das Kontrollkästchen und dann **Abonnement löschen.**</span><span class="sxs-lookup"><span data-stu-id="77abc-127">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="77abc-128">Ich habe ein Self-Service-Anmeldeabonnement, das die Verzeichnislöschung blockiert</span><span class="sxs-lookup"><span data-stu-id="77abc-128">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="77abc-129">Die Self-Service-Anmeldeprodukte, für die sich einzelne Benutzer registrieren können, erstellen auch einen Gastbenutzer für die Authentifizierung in Ihrem Azure AD-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="77abc-129">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="77abc-130">Um Datenverluste zu vermeiden, blockieren diese Self-Service-Produkte Verzeichnislöschungen, bis sie vollständig aus dem Verzeichnis gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="77abc-130">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="77abc-131">Sie können nur vom Azure AD-Administrator gelöscht werden. Weitere Informationen finden Sie [unter Löschen eines Verzeichnisses in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).</span><span class="sxs-lookup"><span data-stu-id="77abc-131">They can only be deleted by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>
