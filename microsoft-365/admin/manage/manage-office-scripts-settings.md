---
title: Einstellungen für Office-Skripts verwalten
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Erfahren Sie, wie Sie Office Skripteinstellungen für Benutzer in Ihrer Organisation verwalten.
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058423"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="46bea-103">Einstellungen für Office-Skripts verwalten</span><span class="sxs-lookup"><span data-stu-id="46bea-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="46bea-104">Office Mit Skripts können Benutzer Aufgaben automatisieren, indem Sie Skripts im Excel aufzeichnen, bearbeiten und ausführen.</span><span class="sxs-lookup"><span data-stu-id="46bea-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="46bea-105">Office Skripts funktionieren mit Power Automate, und Benutzer führen Skripts in Arbeitsmappen mithilfe des Excel Online (Business)-Connectors aus.</span><span class="sxs-lookup"><span data-stu-id="46bea-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="46bea-106">Microsoft 365 Administratoren können Office Skripteinstellungen über das Microsoft 365 verwalten.</span><span class="sxs-lookup"><span data-stu-id="46bea-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="46bea-107">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="46bea-107">Before you begin</span></span>

- <span data-ttu-id="46bea-108">Zum Verwalten Office Skripteinstellungen müssen Sie ein globaler Administrator sein. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="46bea-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="46bea-109">Stellen Sie sicher, dass Benutzer in Ihrer Organisation über eine gültige Lizenz für einen Microsoft 365- oder Office 365-kommerziellen oder EDU-Plan verfügen, der Zugriff auf Office-Desktop-Apps umfasst, z. B. einen der folgenden Pläne:</span><span class="sxs-lookup"><span data-stu-id="46bea-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="46bea-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="46bea-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="46bea-111">Microsoft 365 Apps for Business</span><span class="sxs-lookup"><span data-stu-id="46bea-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="46bea-112">Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="46bea-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="46bea-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="46bea-113">Office 365 E3</span></span>
    - <span data-ttu-id="46bea-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="46bea-114">Office 365 E5</span></span>
    - <span data-ttu-id="46bea-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="46bea-115">Office 365 A3</span></span>
    - <span data-ttu-id="46bea-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="46bea-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="46bea-117">Verwalten der Verfügbarkeit Office Skripts und freigabe von Skripts</span><span class="sxs-lookup"><span data-stu-id="46bea-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="46bea-118">Wechseln Sie Microsoft 365 Admin Center zur Registerkarte **Einstellungen** \> **Organisationseinstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Dienste.</a></span><span class="sxs-lookup"><span data-stu-id="46bea-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="46bea-119">Wählen **Sie Office Skripts aus.**</span><span class="sxs-lookup"><span data-stu-id="46bea-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="46bea-120">Office Skripts sind standardmäßig aktiviert, und alle Benutzer in Ihrer Organisation können auf das Feature zugreifen und diese verwenden und Skripts freigeben.</span><span class="sxs-lookup"><span data-stu-id="46bea-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="46bea-121">Deaktivieren Sie zum deaktivieren Office Skripts für Ihre Organisation das Kontrollkästchen Benutzer automatisieren ihre Aufgaben **in Excel im Web** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="46bea-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="46bea-122">Wenn Sie zuvor Office Skripts für Ihre Organisation deaktiviert haben und sie wieder aktivieren möchten, wählen Sie Benutzer automatisieren **in Excel im Web** aus, und geben Sie dann an, wer auf das Feature zugreifen und diese verwenden kann:</span><span class="sxs-lookup"><span data-stu-id="46bea-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="46bea-123">Damit alle Benutzer in Ihrer Organisation auf skripts zugreifen und Office verwenden können, lassen Sie **Jeder** (Standard) ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="46bea-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="46bea-124">Um nur Mitgliedern einer bestimmten Gruppe den Zugriff auf und die Verwendung von Office-Skripts zu ermöglichen, wählen Sie Bestimmte Gruppe **aus,** und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Liste der zulässigen Elemente hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="46bea-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="46bea-125">Sie können der Liste "Zulassen" nur eine Gruppe hinzufügen, und dies muss einer der folgenden Typen sein:</span><span class="sxs-lookup"><span data-stu-id="46bea-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="46bea-126">Microsoft 365 Gruppe</span><span class="sxs-lookup"><span data-stu-id="46bea-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="46bea-127">Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="46bea-127">Distribution group</span></span>
        - <span data-ttu-id="46bea-128">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="46bea-128">Security group</span></span>
        - <span data-ttu-id="46bea-129">E-Mail-aktivierte Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="46bea-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="46bea-130">Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter [Compare groups](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="46bea-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="46bea-131">Um Benutzern mit Zugriff auf Office-Skripts die Freigabe ihrer Skripts für andere Benutzer in Ihrer Organisation zu ermöglichen, wählen Sie Benutzer mit Zugriff auf Office Skripts freigeben für andere Benutzer in der **Organisation aus.**</span><span class="sxs-lookup"><span data-stu-id="46bea-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="46bea-132">Das Freigeben von Skripts außerhalb einer Organisation ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="46bea-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="46bea-133">Wenn Sie später die Skriptfreigabe für Ihre Organisation deaktivieren, können Benutzer weiterhin zuvor freigegebene Skripts ausführen.</span><span class="sxs-lookup"><span data-stu-id="46bea-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="46bea-134">Geben Sie an, welche Benutzer zugriff auf Office Skripts ihre Skripts freigeben können:</span><span class="sxs-lookup"><span data-stu-id="46bea-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="46bea-135">Damit alle Benutzer mit Zugriff auf skripts Office skripts freigeben können, lassen Sie **Jeder** (standard) ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="46bea-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="46bea-136">Um nur Mitgliedern einer bestimmten Gruppe mit Zugriff auf Office-Skripts die Freigabe ihrer Skripts zu ermöglichen, wählen Sie Bestimmte Gruppe **aus,** und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Liste der zulässigen Skripts hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="46bea-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="46bea-137">Sie können der Liste "Zulassen" nur eine Gruppe hinzufügen, und dies muss einer der folgenden Typen sein:</span><span class="sxs-lookup"><span data-stu-id="46bea-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="46bea-138">Microsoft 365 Gruppe</span><span class="sxs-lookup"><span data-stu-id="46bea-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="46bea-139">Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="46bea-139">Distribution group</span></span>
        - <span data-ttu-id="46bea-140">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="46bea-140">Security group</span></span>
        - <span data-ttu-id="46bea-141">E-Mail-aktivierte Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="46bea-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="46bea-142">Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter [Compare groups](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="46bea-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="46bea-143">Wenn Benutzer ihre Skripts Office in Power Automate ausführen können, wählen Sie Benutzer mit Zugriff auf **Office Skripts** ihre Skripts mit Power Automate .</span><span class="sxs-lookup"><span data-stu-id="46bea-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="46bea-144">Auf diese Weise können Benutzer Flussschritte mit der Excel [(Business)-Connector ausführen](/connectors/excelonlinebusiness) **hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="46bea-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="46bea-145">Damit alle Benutzer mit Zugriff auf Office Skripts ihre Skripts in Flüssen verwenden können, lassen Sie **Jeder** (Standard) ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="46bea-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="46bea-146">Um nur Mitgliedern einer bestimmten Gruppe mit Zugriff auf Office Scripts die Verwendung ihrer Skripts in Flüssen zu ermöglichen, wählen Sie Bestimmte Gruppe **aus,** und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Liste der zulässigen Skripts hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="46bea-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="46bea-147">Sie können der Liste "Zulassen" nur eine Gruppe hinzufügen, und dies muss einer der folgenden Typen sein:</span><span class="sxs-lookup"><span data-stu-id="46bea-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="46bea-148">Microsoft 365 Gruppe</span><span class="sxs-lookup"><span data-stu-id="46bea-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="46bea-149">Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="46bea-149">Distribution group</span></span>
        - <span data-ttu-id="46bea-150">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="46bea-150">Security group</span></span>
        - <span data-ttu-id="46bea-151">E-Mail-aktivierte Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="46bea-151">Mail-enabled security group</span></span>

        <span data-ttu-id="46bea-152">Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter [Compare groups](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="46bea-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="46bea-153">Weitere Informationen zur Verwendung von Office-Skripts mit Power Automate, einschließlich der Auswirkungen ihrer Richtlinien zur Verhinderung von Datenverlust, finden Sie unter [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span><span class="sxs-lookup"><span data-stu-id="46bea-153">To learn more about using Office Scripts with Power Automate, including how your data loss prevention policies may be impacted, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="46bea-154">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="46bea-154">Select **Save**.</span></span>

    <span data-ttu-id="46bea-155">Es kann bis zu 48 Stunden dauern, bis Änderungen Office Skripteinstellungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="46bea-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="46bea-156">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="46bea-156">Next steps</span></span>

<span data-ttu-id="46bea-157">Da Office Skripts mit Power Automate zusammenarbeiten, empfehlen wir, dass Sie Ihre vorhandenen Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) überprüfen, um sicherzustellen, dass die Daten Ihrer Organisation geschützt bleiben, während Benutzer skripts Office verwenden.</span><span class="sxs-lookup"><span data-stu-id="46bea-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="46bea-158">Weitere Informationen finden Sie unter [Data Loss Prevention (DLP)-Richtlinien](/power-automate/prevent-data-loss).</span><span class="sxs-lookup"><span data-stu-id="46bea-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="46bea-159">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="46bea-159">Related content</span></span>

<span data-ttu-id="46bea-160">[Office Technische Dokumentation zu Skripts](/office/dev/scripts/) (Linkseite)</span><span class="sxs-lookup"><span data-stu-id="46bea-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="46bea-161">[Einführung in Office Skripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="46bea-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="46bea-162">[Freigeben Office Skripts in Excel für das Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="46bea-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="46bea-163">[Aufzeichnen, Bearbeiten und Erstellen Office Skripts in Excel im Web](/office/dev/scripts/tutorials/excel-tutorial) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="46bea-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
