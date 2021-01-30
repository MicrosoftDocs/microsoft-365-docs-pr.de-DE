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
description: Erfahren Sie, wie Sie Einstellungen für Office-Skripts für Benutzer in Ihrer Organisation verwalten.
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058423"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="fbd0c-103">Einstellungen für Office-Skripts verwalten</span><span class="sxs-lookup"><span data-stu-id="fbd0c-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="fbd0c-104">Mit Office Scripts können Benutzer Aufgaben automatisieren, indem Skripts in Excel im Web aufgezeichnet, bearbeitet und ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="fbd0c-105">Office Scripts funktioniert mit Power Automate, und Benutzer führen Skripts in Arbeitsmappen mithilfe des Excel Online (Business)-Connectors aus.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="fbd0c-106">Microsoft 365-Administratoren können Einstellungen für Office-Skripts über das Microsoft 365 Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fbd0c-107">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="fbd0c-107">Before you begin</span></span>

- <span data-ttu-id="fbd0c-108">Zum Verwalten von Einstellungen für Office-Skripts müssen Sie ein globaler Administrator sein. Weitere Informationen finden Sie unter ["Informationen zu Administratorrollen".](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="fbd0c-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="fbd0c-109">Stellen Sie sicher, dass Benutzer in Ihrer Organisation über eine gültige Lizenz für einen kommerziellen Microsoft 365- oder Office 365-Bildungsplan verfügen, der Zugriff auf Office-Desktop-Apps umfasst, z. B. einen der folgenden Pläne:</span><span class="sxs-lookup"><span data-stu-id="fbd0c-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="fbd0c-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="fbd0c-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="fbd0c-111">Microsoft 365 Apps for Business</span><span class="sxs-lookup"><span data-stu-id="fbd0c-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="fbd0c-112">Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="fbd0c-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="fbd0c-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="fbd0c-113">Office 365 E3</span></span>
    - <span data-ttu-id="fbd0c-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="fbd0c-114">Office 365 E5</span></span>
    - <span data-ttu-id="fbd0c-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="fbd0c-115">Office 365 A3</span></span>
    - <span data-ttu-id="fbd0c-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="fbd0c-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="fbd0c-117">Verwalten der Verfügbarkeit von Office-Skripts und der Freigabe von Skripts</span><span class="sxs-lookup"><span data-stu-id="fbd0c-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="fbd0c-118">Wechseln Sie im Microsoft 365 Admin Center zur Registerkarte **"Einstellungen** \> **für** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Organisationseinstellungen".</a></span><span class="sxs-lookup"><span data-stu-id="fbd0c-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="fbd0c-119">Wählen Sie **Office-Skripts aus.**</span><span class="sxs-lookup"><span data-stu-id="fbd0c-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="fbd0c-120">Office-Skripts sind standardmäßig aktiviert, und jeder in Ihrer Organisation kann auf das Feature zugreifen und es verwenden und Skripts freigeben.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="fbd0c-121">Deaktivieren Sie das Kontrollkästchen "Benutzern das Automatisieren ihrer Aufgaben **in Excel im Web** ermöglichen", um die Office-Skripts für Ihre Organisation zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="fbd0c-122">Wenn Sie zuvor die Office-Skripts für Ihre Organisation deaktiviert haben und wieder aktivieren möchten, wählen Sie "Benutzern das Automatisieren ihrer Aufgaben **in Excel im Web** ermöglichen" aus, und geben Sie dann an, wer auf das Feature zugreifen und es verwenden kann:</span><span class="sxs-lookup"><span data-stu-id="fbd0c-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="fbd0c-123">Um allen Benutzern in Ihrer Organisation den Zugriff auf und die Verwendung von Office-Skripts zu ermöglichen, lassen Sie **"Jeder"** (Standard) ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="fbd0c-124">Um nur Mitgliedern einer bestimmten Gruppe den Zugriff auf und die Verwendung von Office-Skripts zu ermöglichen, wählen Sie eine bestimmte Gruppe **aus,** und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Liste "Zulassen" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="fbd0c-125">Sie können nur eine Gruppe zur Liste der zulässigen Gruppen hinzufügen, und dies muss einer der folgenden Typen sein:</span><span class="sxs-lookup"><span data-stu-id="fbd0c-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="fbd0c-126">Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="fbd0c-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="fbd0c-127">Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="fbd0c-127">Distribution group</span></span>
        - <span data-ttu-id="fbd0c-128">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fbd0c-128">Security group</span></span>
        - <span data-ttu-id="fbd0c-129">E-Mail-aktivierte Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fbd0c-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="fbd0c-130">Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter [Vergleichen von Gruppen.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="fbd0c-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="fbd0c-131">Damit Benutzer mit Zugriff auf Office-Skripts ihre Skripts für andere Personen in Ihrer Organisation freigeben können, wählen Sie "Benutzern mit Zugriff auf Office-Skripts erlauben" aus, ihre Skripts für andere Personen in der **Organisation zu freigeben.**</span><span class="sxs-lookup"><span data-stu-id="fbd0c-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="fbd0c-132">Das Freigeben von Skripts außerhalb einer Organisation ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="fbd0c-133">Wenn Sie später die Skriptfreigabe für Ihre Organisation deaktivieren, können Benutzer weiterhin zuvor freigegebene Skripts ausführen.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="fbd0c-134">Geben Sie an, welche Benutzer mit Zugriff auf Office-Skripts ihre Skripts freigeben können:</span><span class="sxs-lookup"><span data-stu-id="fbd0c-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="fbd0c-135">Damit alle Benutzer mit Zugriff auf Office-Skripts ihre Skripts freigeben können, lassen Sie **"Jeder"** (Standard) ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="fbd0c-136">Damit nur Mitglieder einer bestimmten Gruppe mit Zugriff auf Office-Skripts ihre Skripts freigeben können, wählen Sie eine bestimmte Gruppe **aus,** und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Liste "Zulassen" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="fbd0c-137">Sie können nur eine Gruppe zur Liste der zulässigen Gruppen hinzufügen, und dies muss einer der folgenden Typen sein:</span><span class="sxs-lookup"><span data-stu-id="fbd0c-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="fbd0c-138">Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="fbd0c-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="fbd0c-139">Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="fbd0c-139">Distribution group</span></span>
        - <span data-ttu-id="fbd0c-140">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fbd0c-140">Security group</span></span>
        - <span data-ttu-id="fbd0c-141">E-Mail-aktivierte Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fbd0c-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="fbd0c-142">Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter [Vergleichen von Gruppen.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="fbd0c-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="fbd0c-143">Damit Benutzer ihre Office-Skripts in Power Automate-Flüssen ausführen können, wählen Sie "Benutzern mit Zugriff auf Office-Skripts die Ausführung ihrer Skripts mit **Power Automate erlauben" aus.**</span><span class="sxs-lookup"><span data-stu-id="fbd0c-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="fbd0c-144">Auf diese Weise können Benutzer Flussschritte mit der Skriptoption "Ausführen" des [Excel Online (Business)-Connectors](/connectors/excelonlinebusiness) **hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="fbd0c-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="fbd0c-145">Damit alle Benutzer mit Zugriff auf Office-Skripts ihre Skripts in Flüssen verwenden können, lassen Sie **"Jeder"** (Standard) ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="fbd0c-146">Damit nur Mitglieder einer bestimmten Gruppe mit Zugriff auf Office-Skripts ihre Skripts in Flüssen verwenden können, wählen Sie eine bestimmte Gruppe **aus,** und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Liste "Zulassen" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="fbd0c-147">Sie können der Liste "Zulassen" nur eine Gruppe hinzufügen, und dies muss einer der folgenden Typen sein:</span><span class="sxs-lookup"><span data-stu-id="fbd0c-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="fbd0c-148">Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="fbd0c-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="fbd0c-149">Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="fbd0c-149">Distribution group</span></span>
        - <span data-ttu-id="fbd0c-150">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fbd0c-150">Security group</span></span>
        - <span data-ttu-id="fbd0c-151">E-Mail-aktivierte Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fbd0c-151">Mail-enabled security group</span></span>

        <span data-ttu-id="fbd0c-152">Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter [Vergleichen von Gruppen.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="fbd0c-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="fbd0c-153">Weitere Informationen zur Verwendung von Office-Skripts mit Power Automate, einschließlich der Auswirkungen auf Ihre Richtlinien zur Verhinderung von Datenverlust, finden Sie unter Ausführen von [Office-Skripts mit Power Automate.](/office/dev/scripts/develop/power-automate-integration)</span><span class="sxs-lookup"><span data-stu-id="fbd0c-153">To learn more about using Office Scripts with Power Automate, including how your data loss prevention policies may be impacted, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="fbd0c-154">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-154">Select **Save**.</span></span>

    <span data-ttu-id="fbd0c-155">Es kann bis zu 48 Stunden dauern, bis Änderungen an den Einstellungen für Office-Skripts wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fbd0c-156">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fbd0c-156">Next steps</span></span>

<span data-ttu-id="fbd0c-157">Da Office Scripts mit Power Automate verwendet werden können, sollten Sie Ihre vorhandenen Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) überprüfen, um sicherzustellen, dass die Daten Ihrer Organisation geschützt bleiben, während Benutzer Office Scripts verwenden.</span><span class="sxs-lookup"><span data-stu-id="fbd0c-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="fbd0c-158">Weitere Informationen finden Sie unter Richtlinien zur [Verhinderung von Datenverlust (Data Loss Prevention, DLP).](/power-automate/prevent-data-loss)</span><span class="sxs-lookup"><span data-stu-id="fbd0c-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="fbd0c-159">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="fbd0c-159">Related content</span></span>

<span data-ttu-id="fbd0c-160">[Technische Dokumentation zu Office Scripts](/office/dev/scripts/) (Linkseite)</span><span class="sxs-lookup"><span data-stu-id="fbd0c-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="fbd0c-161">[Einführung in Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="fbd0c-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="fbd0c-162">[Freigeben von Office-Skripts in Excel für das Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="fbd0c-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="fbd0c-163">[Aufzeichnen, Bearbeiten und Erstellen von Office-Skripts in Excel im Web](/office/dev/scripts/tutorials/excel-tutorial) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="fbd0c-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
