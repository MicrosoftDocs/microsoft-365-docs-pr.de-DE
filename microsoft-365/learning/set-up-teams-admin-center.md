---
title: Einrichten von Microsoft Viva Learning (Vorschau) im Teams Admin Center
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: ''
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Erfahren Sie, wie Sie Microsoft Viva Learning (Vorschau) im Teams Admin Center konfigurieren.
ms.openlocfilehash: 99e63210e8f8c10e3721c35fb69df7880c7e1929
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290219"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="b2ef8-103">Einrichten von Microsoft Viva Learning (Vorschau) im Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="b2ef8-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="b2ef8-104">Die Informationen in diesem Artikel beziehen sich auf ein Vorschauprodukt, das vor der kommerziellen Veröffentlichung erheblich geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="b2ef8-105">Der Teams-Administrator muss bestimmte Schritte ausführen, um Viva Learning (Vorschau) für seine Benutzer im Mandanten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-105">The Teams administrator needs to perform certain steps to enable Viva Learning (Preview) for their users in the tenant.</span></span> <span data-ttu-id="b2ef8-106">Diese Schritte variieren je nach Aktivierung des Mandanten: [*Public Preview*](set-up-teams-admin-center.md#public-preview-tenants) oder [ *Private Preview* (oder Beta).](set-up-teams-admin-center.md#private-preview-tenants)</span><span class="sxs-lookup"><span data-stu-id="b2ef8-106">These steps vary based on how the tenant is enabled:  [*Public Preview*](set-up-teams-admin-center.md#public-preview-tenants) or [*Private Preview* (or Beta)](set-up-teams-admin-center.md#private-preview-tenants).</span></span>

## <a name="public-preview-tenants"></a><span data-ttu-id="b2ef8-107">Öffentliche Vorschaumandanten</span><span class="sxs-lookup"><span data-stu-id="b2ef8-107">Public Preview tenants</span></span>

### <a name="administrator-steps-for-public-preview-tenants"></a><span data-ttu-id="b2ef8-108">Administratorschritte für Öffentliche Vorschaumandanten</span><span class="sxs-lookup"><span data-stu-id="b2ef8-108">Administrator steps for Public Preview tenants</span></span>

<span data-ttu-id="b2ef8-109">Da viva Learning (Vorschau) noch nicht allgemein verfügbar ist, sind bestimmte Schritte erforderlich, um die Features zu aktivieren und Berechtigungen für bestimmte Benutzer oder Gruppen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-109">Because the Viva Learning (Preview) is not yet generally available, certain steps are required to enable the features and set permissions for specific users or groups.</span></span> 

1. <span data-ttu-id="b2ef8-110">Aktivieren Sie public Preview-Features für Viva Learning (Vorschau)-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-110">Enable Public Preview features for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="b2ef8-111">a.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-111">a.</span></span> <span data-ttu-id="b2ef8-112">Ändern Sie Teams Updaterichtlinie, um Public Preview-Features zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-112">Modify Teams update policy to enable Public Preview features.</span></span> <span data-ttu-id="b2ef8-113">Siehe [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).</span><span class="sxs-lookup"><span data-stu-id="b2ef8-113">See [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).</span></span>

    <span data-ttu-id="b2ef8-114">b.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-114">b.</span></span> <span data-ttu-id="b2ef8-115">Aktivieren Sie die Updaterichtlinie für Benutzer oder Gruppen, die Viva Learning (Vorschau) testen.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-115">Enable the update policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="b2ef8-116">Siehe [Zuweisen von Richtlinien zu Benutzern und Gruppen.](/microsoftteams/assign-policies-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="b2ef8-116">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

2. <span data-ttu-id="b2ef8-117">Ändern Sie die App-Berechtigungsrichtlinie für Benutzer von Viva Learning (Vorschau).</span><span class="sxs-lookup"><span data-stu-id="b2ef8-117">Modify the app permission policy for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="b2ef8-118">a.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-118">a.</span></span> <span data-ttu-id="b2ef8-119">Sofern sie nicht aktuell Teil der globalen Richtlinie ist, lassen Sie alle Microsoft-Apps in der App-Berechtigungsrichtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-119">Unless it's currently part of the global policy, allow all Microsoft apps in the app permission policy.</span></span> <span data-ttu-id="b2ef8-120">Weitere Informationen finden [Sie unter Verwalten von App-Berechtigungsrichtlinien in Microsoft Teams.](/microsoftteams/teams-app-permission-policies)</span><span class="sxs-lookup"><span data-stu-id="b2ef8-120">See [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span> 

    <span data-ttu-id="b2ef8-121">b.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-121">b.</span></span> <span data-ttu-id="b2ef8-122">Aktivieren Sie die App-Berechtigungsrichtlinie für Benutzer oder Gruppen, die Viva Learning (Vorschau) testen.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-122">Enable the app permission policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="b2ef8-123">Siehe [Zuweisen von Richtlinien zu Benutzern und Gruppen.](/microsoftteams/assign-policies-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="b2ef8-123">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

3. <span data-ttu-id="b2ef8-124">Benachrichtigen Sie Benutzer, die Viva Learning (Vorschau) testen werden, [ihren Buildclient für Teams in die öffentliche Vorschau zu wechseln.](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants)</span><span class="sxs-lookup"><span data-stu-id="b2ef8-124">Notify users who will test Viva Learning (Preview) to [switch their build client to Public Preview for Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2ef8-125">Für Öffentliche Vorschau-Mandanten wird Viva Learning (Vorschau) erst in der endgültigen Produktversion in **verwalteten Apps** im Teams Admin Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-125">For Public Preview tenants, Viva Learning (Preview) will not be displayed in **Managed apps** in the Teams admin center until final product release.</span></span> <span data-ttu-id="b2ef8-126">Aktivierte Benutzer der öffentlichen Vorschau können Viva Learning (Vorschau) jedoch im Teams App Store finden und verwenden, sobald die richtigen Richtlinien und Berechtigungen eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-126">However, enabled Public Preview users can find Viva Learning (Preview) in the Teams app store and use it, once the correct policies and permissions have been set up.</span></span>

### <a name="user-steps-for-public-preview-tenants"></a><span data-ttu-id="b2ef8-127">Benutzerschritte für Öffentliche Vorschaumandanten</span><span class="sxs-lookup"><span data-stu-id="b2ef8-127">User steps for Public Preview tenants</span></span>

<span data-ttu-id="b2ef8-128">Benutzer, die für öffentliche Vorschautests aktiviert wurden – durch Aktivieren der [zuvor beschriebenen Richtlinien](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) – müssen in ihrem Teams Client [zur öffentlichen Vorschau wechseln.](/microsoftteams/public-preview-doc-updates#enable-public-preview)</span><span class="sxs-lookup"><span data-stu-id="b2ef8-128">Users who have been enabled for Public Preview testing — by enabling the [policies previously described](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) — need to [switch to Public Preview](/microsoftteams/public-preview-doc-updates#enable-public-preview) in their Teams client.</span></span>

1. <span data-ttu-id="b2ef8-129">Benutzer müssen ihr Profilbild > **Informationen**  >  **zur öffentlichen Vorschau** auswählen.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-129">Users must select their profile image > **About** > **Public Preview**.</span></span>

    ![Obere Navigation in der Teams-Anwendung, die das Profil des Benutzers anzeigt](../media/learning/learning-app-select-profile-teams.png)

2. <span data-ttu-id="b2ef8-131">Benutzer müssen die Allgemeinen Geschäftsbedingungen für die öffentliche Vorschau akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-131">Users must accept the Public Preview terms and conditions.</span></span>

    ![Wechseln zum öffentlichen Vorschaubuild](../media/learning/learning-app-switch-to-public-preview.png)

3. <span data-ttu-id="b2ef8-133">Benutzer finden Viva Learning (Vorschau) jetzt im Teams App Store und beginnen mit der Verwendung.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-133">Users can now find Viva Learning (Preview) in the Teams app store and start using it.</span></span>

## <a name="private-preview-tenants"></a><span data-ttu-id="b2ef8-134">Private Preview-Mandanten</span><span class="sxs-lookup"><span data-stu-id="b2ef8-134">Private Preview tenants</span></span>

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a><span data-ttu-id="b2ef8-135">Administratorschritte für Private Preview-Mandanten (oder Beta-Mandanten)</span><span class="sxs-lookup"><span data-stu-id="b2ef8-135">Administrator steps for Private Preview (or Beta) tenants</span></span>

<span data-ttu-id="b2ef8-136">Für Private Preview-Mandanten gibt es keine zusätzlichen Richtlinien, die aktiviert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-136">For Private Preview tenants, there are no additional policies that need to be enabled.</span></span> <span data-ttu-id="b2ef8-137">Viva Learning (Vorschau) muss jedoch für Benutzer in Ihrer Organisation zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-137">However, Viva Learning (Preview) must be made available for users in your organization.</span></span>

1. <span data-ttu-id="b2ef8-138">Wechseln Sie in der linken Navigationsleiste des Teams Admin Centers zu **Teams Apps** Verwalten  >  **von Apps.**</span><span class="sxs-lookup"><span data-stu-id="b2ef8-138">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Linksnavigation im Teams Admin Center mit Teams Abschnitt "Apps verwalten".](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="b2ef8-140">Geben Sie auf der Seite **"Apps verwalten"** im Suchfeld *Viva Learning* ein, und wählen Sie dann **Viva Learning (Vorschau)** aus.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-140">On the **Manage apps** page, in the search box, type *Viva Learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![Seite "Apps verwalten" im Teams Admin Center, auf der das Suchfeld angezeigt wird.](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="b2ef8-142">On the **Viva Learning (Preview)** page, under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="b2ef8-142">On the **Viva Learning (Preview)** page, under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   ![Learning Seite im Teams Admin Center, auf der der Abschnitt "Status- und App-Einstellungen" angezeigt wird.](../media/learning/learning-app-teams-learning-page.png)

<!---
The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.

1. For Viva Learning (Preview), you must first set the Update policy in Teams. For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Sign in to the Teams admin center.

    2. Select **Teams** > **Update policies**.

    3. Select **Add**. 

    4. Name the update policy, add a policy, and turn on **Show preview features**.

2. The admin must notify users of the policy update so that they move their build into the Public Preview for Teams. 

    1. Users must select their profile image > **About** > **Public Preview**.
   
        ![Upper navigation in the Teams application showing user's profile](../media/learning/learning-app-select-profile-teams.png)
    
    2. Users must accept the **Public preview** terms and conditions.

        ![Switch to public preview build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.

## Manage settings for Viva Learning (Preview)

You must be an administrator in the Teams admin center to perform these tasks.

To make Viva Learning (Preview) available for users in your organization, follow these steps:

1. In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.

   ![Left navigation in the Teams admin center showing Teams apps and Manage apps section.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.

   ![Manage apps page in the Teams admin center showing the search box.](../media/learning/learning-app-teams-manage-apps-page.png)

3. On the **Viva Learning (Preview)** page:

   1. Under **Status**, select **Allowed** to turn on Viva Learning (Preview).

   2. On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).

   ![Learning page in the Teams admin center showing Status and App settings section.](../media/learning/learning-app-teams-learning-page.png)

4. After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.

> [!NOTE]
>  If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview). <br><br>As part of the preview, Viva Learning (Preview) is released in Ring 3.0. If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page. To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users. <br><br>   ![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)

--->

## <a name="next-step"></a><span data-ttu-id="b2ef8-144">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b2ef8-144">Next step</span></span>

[<span data-ttu-id="b2ef8-145">Konfigurieren von Lerninhaltsquellen für Viva Learning (Vorschau) im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="b2ef8-145">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
