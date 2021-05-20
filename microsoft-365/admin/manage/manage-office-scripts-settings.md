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
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572309"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="0349d-103">Einstellungen für Office-Skripts verwalten</span><span class="sxs-lookup"><span data-stu-id="0349d-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="0349d-104">[Office-Skripts](/office/dev/scripts)ermöglicht es Benutzern, Aufgaben zu automatisieren, indem sie Skripts in Excel im Web aufzeichnen, bearbeiten und ausführen.</span><span class="sxs-lookup"><span data-stu-id="0349d-104">[Office Scripts](/office/dev/scripts)‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="0349d-105">Office Skripts arbeiten mit Power Automate, und Benutzer führen Skripts in Arbeitsmappen mithilfe des Excel Online-Connector (Business) aus.</span><span class="sxs-lookup"><span data-stu-id="0349d-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="0349d-106">Microsoft 365 Administratoren können Office Scripts-Einstellungen über das Microsoft 365 Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="0349d-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0349d-107">Bevor Sie loslegen</span><span class="sxs-lookup"><span data-stu-id="0349d-107">Before you begin</span></span>

- <span data-ttu-id="0349d-108">Um Office Scripts-Einstellungen zu verwalten, müssen Sie ein globaler Administrator sein. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0349d-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="0349d-109">Stellen Sie sicher, dass Benutzer in Ihrer Organisation über eine gültige Lizenz für einen Microsoft 365 oder Office 365 kommerziellen oder EDU-Plan verfügen, der den Zugriff auf Office Desktop-Apps umfasst, z. B. einen der folgenden Pläne:</span><span class="sxs-lookup"><span data-stu-id="0349d-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="0349d-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="0349d-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="0349d-111">Microsoft 365 Apps for Business</span><span class="sxs-lookup"><span data-stu-id="0349d-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="0349d-112">Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="0349d-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="0349d-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="0349d-113">Office 365 E3</span></span>
    - <span data-ttu-id="0349d-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="0349d-114">Office 365 E5</span></span>
    - <span data-ttu-id="0349d-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="0349d-115">Office 365 A3</span></span>
    - <span data-ttu-id="0349d-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="0349d-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="0349d-117">Verwalten der Verfügbarkeit Office Skripts und Freigeben von Skripts</span><span class="sxs-lookup"><span data-stu-id="0349d-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="0349d-118">Wechseln Sie im Microsoft 365 Admin Center zur Registerkarte **Einstellungen** \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Organisationsdienste.</a></span><span class="sxs-lookup"><span data-stu-id="0349d-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="0349d-119">Wählen Sie **Office Scripts** aus.</span><span class="sxs-lookup"><span data-stu-id="0349d-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="0349d-120">Office Skripts sind standardmäßig aktiviert, und jeder in Ihrer Organisation kann auf die Feature- und Freigabeskripts zugreifen und diese verwenden.</span><span class="sxs-lookup"><span data-stu-id="0349d-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="0349d-121">Um Office Skripts für Ihre Organisation zu deaktivieren, deaktivieren Sie das Kontrollkästchen **Benutzer automatisieren lassen, Excel im Web.**</span><span class="sxs-lookup"><span data-stu-id="0349d-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="0349d-122">Wenn Sie zuvor Office Skripts für Ihre Organisation deaktiviert haben und sie wieder aktivieren möchten, wählen Sie **Benutzer in Excel im Web automatisieren** aus, und geben Sie dann an, wer auf die Funktion zugreifen und diese verwenden kann:</span><span class="sxs-lookup"><span data-stu-id="0349d-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="0349d-123">Damit alle Benutzer in Ihrer Organisation auf Office Skripts zugreifen und diese verwenden können, lassen Sie **Alle** (Standard) ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="0349d-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="0349d-124">Um nur Mitgliedern einer bestimmten Gruppe den Zugriff auf und die Verwendung Office Skripts zu ermöglichen, wählen Sie **Spezifische Gruppe** aus, und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Zulassungsliste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0349d-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="0349d-125">Sie können der Zulassungsliste nur eine Gruppe hinzufügen, und es muss einer der folgenden Typen sein:</span><span class="sxs-lookup"><span data-stu-id="0349d-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="0349d-126">Microsoft 365 Gruppe</span><span class="sxs-lookup"><span data-stu-id="0349d-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="0349d-127">Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="0349d-127">Distribution group</span></span>
        - <span data-ttu-id="0349d-128">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="0349d-128">Security group</span></span>
        - <span data-ttu-id="0349d-129">E-Mail-aktivierte Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="0349d-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="0349d-130">Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter Vergleichen von [Gruppen](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0349d-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="0349d-131">Damit Benutzer mit Zugriff auf Office Skripts ihre Skripts für andere Benutzer in Ihrer Organisation freigeben können, wählen Sie **Benutzer mit Zugriff auf Office Skripts für andere in der Organisation freigeben.**</span><span class="sxs-lookup"><span data-stu-id="0349d-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="0349d-132">Das Freigeben von Skripts außerhalb einer Organisation ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="0349d-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="0349d-133">Wenn Sie später die Skriptfreigabe für Ihre Organisation deaktivieren, können Benutzer weiterhin zuvor freigegebene Skripts ausführen.</span><span class="sxs-lookup"><span data-stu-id="0349d-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="0349d-134">Geben Sie an, welche Benutzer mit Zugriff auf Office Skripts ihre Skripts freigeben können:</span><span class="sxs-lookup"><span data-stu-id="0349d-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="0349d-135">Damit alle Benutzer mit Zugriff auf Office Skripts ihre Skripts freigeben können, lassen Sie **Alle** (standardwert) ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="0349d-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="0349d-136">Um nur Mitgliedern einer bestimmten Gruppe mit Zugriff auf Office Skripts die Freigabe ihrer Skripts zu ermöglichen, wählen Sie **Spezifische Gruppe** aus, und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Zulassungsliste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0349d-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="0349d-137">Sie können der Zulassungsliste nur eine Gruppe hinzufügen, und es muss einer der folgenden Typen sein:</span><span class="sxs-lookup"><span data-stu-id="0349d-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="0349d-138">Microsoft 365 Gruppe</span><span class="sxs-lookup"><span data-stu-id="0349d-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="0349d-139">Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="0349d-139">Distribution group</span></span>
        - <span data-ttu-id="0349d-140">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="0349d-140">Security group</span></span>
        - <span data-ttu-id="0349d-141">E-Mail-aktivierte Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="0349d-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="0349d-142">Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter Vergleichen von [Gruppen](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0349d-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="0349d-143">Damit Benutzer ihre Office Skripts in Power Automate-Flows ausführen können, wählen Sie **Zulassen, dass Benutzer mit Zugriff auf Office Skripts ihre Skripts mit Power Automate ausführen.**</span><span class="sxs-lookup"><span data-stu-id="0349d-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="0349d-144">Auf diese Weise können Benutzer Flow-Schritte mit der **Skriptoption** [Excel Online (Business) Connector hinzufügen.](/connectors/excelonlinebusiness)</span><span class="sxs-lookup"><span data-stu-id="0349d-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="0349d-145">Damit alle Benutzer mit Zugriff auf Office Skripts ihre Skripts in Flows verwenden können, lassen Sie **Alle** (standard) ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="0349d-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="0349d-146">Um nur Mitgliedern einer bestimmten Gruppe mit Zugriff auf Office Skripts die Verwendung ihrer Skripts in Flows zu ermöglichen, wählen Sie **Spezifische Gruppe** aus, und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Zulassungsliste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0349d-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="0349d-147">Sie können der Zulassungsliste nur eine Gruppe hinzufügen, und es muss einer der folgenden Typen sein:</span><span class="sxs-lookup"><span data-stu-id="0349d-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="0349d-148">Microsoft 365 Gruppe</span><span class="sxs-lookup"><span data-stu-id="0349d-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="0349d-149">Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="0349d-149">Distribution group</span></span>
        - <span data-ttu-id="0349d-150">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="0349d-150">Security group</span></span>
        - <span data-ttu-id="0349d-151">E-Mail-aktivierte Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="0349d-151">Mail-enabled security group</span></span>

        <span data-ttu-id="0349d-152">Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter Vergleichen von [Gruppen](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0349d-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="0349d-153">Weitere Informationen zur Verwendung von Office Skripts mit Power Automate finden Sie unter [Ausführen Office Skripts mit Power Automate](/office/dev/scripts/develop/power-automate-integration).</span><span class="sxs-lookup"><span data-stu-id="0349d-153">To learn more about using Office Scripts with Power Automate, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="0349d-154">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="0349d-154">Select **Save**.</span></span>

    <span data-ttu-id="0349d-155">Es kann bis zu 48 Stunden dauern, bis Änderungen an Office Scripts-Einstellungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="0349d-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0349d-156">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0349d-156">Next steps</span></span>

<span data-ttu-id="0349d-157">Da Office Skripts mit Power Automate funktioniert, wird empfohlen, dass Sie Ihre vorhandenen DLP-Richtlinien (Data Loss Prevention) überprüfen, um sicherzustellen, dass die Daten Ihrer Organisation geschützt bleiben, während Benutzer Office Skripts verwenden.</span><span class="sxs-lookup"><span data-stu-id="0349d-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="0349d-158">Weitere Informationen finden Sie unter [DLP-Richtlinien (Data Loss Prevention)](/power-automate/prevent-data-loss).</span><span class="sxs-lookup"><span data-stu-id="0349d-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="0349d-159">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="0349d-159">Related content</span></span>

<span data-ttu-id="0349d-160">[Office technische Dokumentation von Scripts](/office/dev/scripts/) (Linkseite)</span><span class="sxs-lookup"><span data-stu-id="0349d-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)\</span></span>
<span data-ttu-id="0349d-161">[Einführung in Office Skripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="0349d-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)\</span></span>
<span data-ttu-id="0349d-162">[Freigeben Office Skripts in Excel für das Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="0349d-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)\</span></span>
<span data-ttu-id="0349d-163">[Aufzeichnen, Bearbeiten und Erstellen Office Skripts in Excel im Web](/office/dev/scripts/tutorials/excel-tutorial) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="0349d-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
