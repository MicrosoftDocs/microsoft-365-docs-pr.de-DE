---
title: Einrichten von Microsoft Viva Learning (Preview) im Teams Admin Center
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/24/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Erfahren Sie, wie Sie Microsoft Viva Learning (Preview) im Teams konfigurieren.
ms.openlocfilehash: a96a2f3ecf7d4e1ee0c136ae155868218f08aaf4
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636134"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="e72b5-103">Einrichten von Microsoft Viva Learning (Preview) im Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="e72b5-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="e72b5-104">Die Informationen in diesem Artikel beziehen sich auf ein Vorschauprodukt, das möglicherweise erheblich geändert wird, bevor es kommerziell veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="e72b5-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="e72b5-105">Der Teams installiert Viva Learning (Preview) und wendet Berechtigungsrichtlinien über das Teams Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="e72b5-105">The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.</span></span>

1. <span data-ttu-id="e72b5-106">Für Viva Learning (Preview) müssen Sie zuerst die Updaterichtlinie in Teams.</span><span class="sxs-lookup"><span data-stu-id="e72b5-106">For Viva Learning (Preview), you must first set the Update policy in Teams.</span></span> <span data-ttu-id="e72b5-107">Weitere Informationen finden Sie unter [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).</span><span class="sxs-lookup"><span data-stu-id="e72b5-107">For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).</span></span>

    1. <span data-ttu-id="e72b5-108">Melden Sie sich beim Teams Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="e72b5-108">Sign in to the Teams admin center.</span></span>

    2. <span data-ttu-id="e72b5-109">Wählen **Teams**  >  **Updaterichtlinien aus.**</span><span class="sxs-lookup"><span data-stu-id="e72b5-109">Select **Teams** > **Update policies**.</span></span>

    3. <span data-ttu-id="e72b5-110">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e72b5-110">Select **Add**.</span></span> 

    4. <span data-ttu-id="e72b5-111">Benennen Sie die Updaterichtlinie, fügen Sie eine Richtlinie hinzu, und aktivieren Sie **Vorschaufeatures anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="e72b5-111">Name the update policy, add a policy, and turn on **Show preview features**.</span></span>

2. <span data-ttu-id="e72b5-112">Der Administrator muss die Benutzer über das Richtlinienupdate benachrichtigen, damit er seinen Build in die öffentliche Vorschau für Teams.</span><span class="sxs-lookup"><span data-stu-id="e72b5-112">The admin must notify users of the policy update so that they move their build into the Public Preview for Teams.</span></span> 

    1. <span data-ttu-id="e72b5-113">Benutzer müssen ihr Profilbild > **Informationen zur**  >  **öffentlichen Vorschau auswählen.**</span><span class="sxs-lookup"><span data-stu-id="e72b5-113">Users must select their profile image > **About** > **Public Preview**.</span></span>
   
        ![Obere Navigation in der Teams, die das Benutzerprofil zeigt](../media/learning/learning-app-select-profile-teams.png)
    
    2. <span data-ttu-id="e72b5-115">Benutzer müssen die öffentlichen **Vorschaubedingungen** akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="e72b5-115">Users must accept the **Public preview** terms and conditions.</span></span>

        ![Wechseln zum öffentlichen Vorschau-Build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="e72b5-117">For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.</span><span class="sxs-lookup"><span data-stu-id="e72b5-117">For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.</span></span>

## <a name="manage-settings-for-viva-learning-preview"></a><span data-ttu-id="e72b5-118">Verwalten von Einstellungen für Viva Learning (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="e72b5-118">Manage settings for Viva Learning (Preview)</span></span>

<span data-ttu-id="e72b5-119">Sie müssen ein Administrator im Teams Admin Center sein, um diese Aufgaben ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="e72b5-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="e72b5-120">Führen Sie die folgenden Schritte aus, um Viva Learning (Vorschau) für Benutzer in Ihrer Organisation verfügbar zu machen:</span><span class="sxs-lookup"><span data-stu-id="e72b5-120">To make Viva Learning (Preview) available for users in your organization, follow these steps:</span></span>

1. <span data-ttu-id="e72b5-121">Navigieren Sie in der linken Navigation des Teams Admin Center zu **Teams Apps**  >  **verwalten.**</span><span class="sxs-lookup"><span data-stu-id="e72b5-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Linke Navigation im Teams Admin Center mit Teams apps und Manage apps.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="e72b5-123">Geben Sie **auf** der Seite Apps verwalten im Suchfeld *"Viva learning"* ein, und wählen Sie dann **Viva Learning (Vorschau) aus.**</span><span class="sxs-lookup"><span data-stu-id="e72b5-123">On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![Verwalten Sie die Seite apps im Teams Admin Center, das das Suchfeld zeigt.](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="e72b5-125">Auf der **Seite "Viva Learning(Preview)"**</span><span class="sxs-lookup"><span data-stu-id="e72b5-125">On the **Viva Learning (Preview)** page:</span></span>

   1. <span data-ttu-id="e72b5-126">Wählen **Sie unter Status** die Option **Zum** Aktivieren von "Viva Learning" (Vorschau) zugelassen aus.</span><span class="sxs-lookup"><span data-stu-id="e72b5-126">Under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   2. <span data-ttu-id="e72b5-127">Wechseln Sie **Einstellungen** Registerkarte unter **App-Einstellungen** zum Microsoft 365 Admin Center, um [Lerninhaltsquellen zu konfigurieren.](content-sources-365-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="e72b5-127">On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).</span></span>

   ![Lernseite im Teams Admin Center mit Status- und App-Einstellungen.](../media/learning/learning-app-teams-learning-page.png)

4. <span data-ttu-id="e72b5-129">Wechseln **Sie nach** Verwalten  von App-Einstellungen zu Berechtigungsrichtlinien und **Setuprichtlinien,** um Mitarbeitern, die im Rahmen der Teilnahme Ihrer Organisation an der Vorschau Zugriff auf Viva Learning (Preview) haben sollen, Die Berechtigung zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="e72b5-129">After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="e72b5-130">Wenn Sich Ihre Organisation im Rahmen des TEAMS TAP100-Programms in Ring 4.0 befindet, müssen Sie möglicherweise genehmigte Benutzer in Ring 3.0 für den Zugriff auf "Viva Learning" (Vorschau) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e72b5-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview).</span></span> <br><br><span data-ttu-id="e72b5-131">Im Rahmen der Vorschau wird Viva Learning (Preview) in Ring 3.0 veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="e72b5-131">As part of the preview, Viva Learning (Preview) is released in Ring 3.0.</span></span> <span data-ttu-id="e72b5-132">Wenn Sich Ihre Organisation in Ring 4.0 befindet, wird auf der Seite Apps verwalten kein Viva Learning (Preview) **angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="e72b5-132">If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page.</span></span> <span data-ttu-id="e72b5-133">Zum Testen der App müssen Sie eine benutzerdefinierte App-Berechtigungsrichtlinie erstellen, sie auf Alle Apps zulassen festlegen und sie genehmigten Benutzern in Ring 3.0 zuweisen. </span><span class="sxs-lookup"><span data-stu-id="e72b5-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span> <br><br>   <span data-ttu-id="e72b5-134">![TAP-AppsPermission-Plcy-Seite mit Ausgewählte Apps zulassen.](../media/learning/learning-app-tap-appspermission-plcy.png)</span><span class="sxs-lookup"><span data-stu-id="e72b5-134">![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)</span></span>

## <a name="next-step"></a><span data-ttu-id="e72b5-135">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="e72b5-135">Next step</span></span>

[<span data-ttu-id="e72b5-136">Konfigurieren von Lerninhaltsquellen für Viva Learning (Vorschau) im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="e72b5-136">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
