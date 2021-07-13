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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid: MET150
description: Erfahren Sie, wie Sie Office Skripteinstellungen für Benutzer in Ihrer Organisation verwalten.
ms.openlocfilehash: fea50838cf1089b73a6af5bbf86d490293831085
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392671"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="725d6-103">Einstellungen für Office-Skripts verwalten</span><span class="sxs-lookup"><span data-stu-id="725d6-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="725d6-104">[Office Skripts](/office/dev/scripts)ermöglicht Benutzern das Automatisieren von Aufgaben durch Aufzeichnen, Bearbeiten und Ausführen von Skripts in Excel im Web.</span><span class="sxs-lookup"><span data-stu-id="725d6-104">[Office Scripts](/office/dev/scripts)‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="725d6-105">Office Skripts funktionieren mit Power Automate, und Benutzer führen Skripts für Arbeitsmappen mithilfe des Excel Online-Connectors (Business) aus.</span><span class="sxs-lookup"><span data-stu-id="725d6-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="725d6-106">Microsoft 365 Administratoren können Office Skripteinstellungen über die Microsoft 365 Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="725d6-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="725d6-107">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="725d6-107">Before you begin</span></span>

- <span data-ttu-id="725d6-108">Um Office Skripteinstellungen zu verwalten, müssen Sie ein globaler Administrator sein. Weitere Informationen finden Sie unter ["Informationen zu Administratorrollen".](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="725d6-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="725d6-109">Stellen Sie sicher, dass Benutzer in Ihrer Organisation über eine gültige Lizenz für einen Microsoft 365- oder Office 365 kommerziellen oder EDU-Plan verfügen, der zugriff auf Office Desktop-Apps umfasst, z. B. einen der folgenden Pläne:</span><span class="sxs-lookup"><span data-stu-id="725d6-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="725d6-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="725d6-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="725d6-111">Microsoft 365 Apps for Business</span><span class="sxs-lookup"><span data-stu-id="725d6-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="725d6-112">Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="725d6-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="725d6-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="725d6-113">Office 365 E3</span></span>
    - <span data-ttu-id="725d6-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="725d6-114">Office 365 E5</span></span>
    - <span data-ttu-id="725d6-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="725d6-115">Office 365 A3</span></span>
    - <span data-ttu-id="725d6-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="725d6-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="725d6-117">Verwalten der Verfügbarkeit von Office Skripts und der Freigabe von Skripts</span><span class="sxs-lookup"><span data-stu-id="725d6-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="725d6-118">Wechseln Sie im Microsoft 365 Admin Center zur Registerkarte **Einstellungen** \> **Organisationseinstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">für Dienste.</a></span><span class="sxs-lookup"><span data-stu-id="725d6-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="725d6-119">Wählen Sie **Office Skripts aus.**</span><span class="sxs-lookup"><span data-stu-id="725d6-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="725d6-120">Office Skripts sind standardmäßig aktiviert, und jeder Benutzer in Ihrer Organisation kann auf das Feature zugreifen und es verwenden und Skripts freigeben.</span><span class="sxs-lookup"><span data-stu-id="725d6-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="725d6-121">Deaktivieren Sie zum Deaktivieren Office Skripts für Ihre Organisation das Kontrollkästchen **"Benutzer ihre Aufgaben automatisieren lassen" in Excel im Web** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="725d6-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="725d6-122">Wenn Sie zuvor Office Skripts für Ihre Organisation deaktiviert haben und sie wieder aktivieren möchten, wählen Sie **"Benutzer können ihre Aufgaben in Excel im Web automatisieren"** aus, und geben Sie dann an, wer auf das Feature zugreifen und es verwenden kann:</span><span class="sxs-lookup"><span data-stu-id="725d6-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="725d6-123">Damit alle Benutzer in Ihrer Organisation auf Office Skripts zugreifen und diese verwenden können, lassen **Sie "Jeder"** (Standard) ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="725d6-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="725d6-124">Damit nur Mitglieder einer bestimmten Gruppe auf Office Skripts zugreifen und diese verwenden können, wählen Sie **"Bestimmte Gruppe"** aus, und geben Sie dann den Namen oder den E-Mail-Alias der Gruppe ein, um sie der Zulassungsliste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="725d6-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="725d6-125">Sie können der Zulassungsliste nur eine Gruppe hinzufügen, und dies muss einer der folgenden Typen sein:</span><span class="sxs-lookup"><span data-stu-id="725d6-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="725d6-126">Microsoft 365 Gruppe</span><span class="sxs-lookup"><span data-stu-id="725d6-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="725d6-127">Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="725d6-127">Distribution group</span></span>
        - <span data-ttu-id="725d6-128">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="725d6-128">Security group</span></span>
        - <span data-ttu-id="725d6-129">E-Mail-aktivierte Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="725d6-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="725d6-130">Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter ["Gruppen vergleichen".](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="725d6-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="725d6-131">Um Benutzern mit Zugriff auf Office Skripts zu ermöglichen, ihre Skripts für andere Benutzer in Ihrer Organisation freizugeben, wählen Sie **"Benutzer mit Zugriff auf Office Skripts ihre Skripts für andere Personen in der Organisation freigeben"** aus.</span><span class="sxs-lookup"><span data-stu-id="725d6-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="725d6-132">Das Freigeben von Skripts außerhalb einer Organisation ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="725d6-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="725d6-133">Wenn Sie später die Skriptfreigabe für Ihre Organisation deaktivieren, können Benutzer weiterhin zuvor freigegebene Skripts ausführen.</span><span class="sxs-lookup"><span data-stu-id="725d6-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="725d6-134">Geben Sie an, welche Benutzer zugriff auf Office Skripts ihre Skripts freigeben können:</span><span class="sxs-lookup"><span data-stu-id="725d6-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="725d6-135">Damit alle Benutzer mit Zugriff auf Office Skripts ihre Skripts freigeben können, lassen **Sie "Jeder"** (Standard) ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="725d6-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="725d6-136">Um nur Mitgliedern einer bestimmten Gruppe mit Zugriff auf Office Skripts die Freigabe ihrer Skripts zu ermöglichen, wählen Sie **bestimmte Gruppe** aus, und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Zulassungsliste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="725d6-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="725d6-137">Sie können der Zulassungsliste nur eine Gruppe hinzufügen, und dies muss einer der folgenden Typen sein:</span><span class="sxs-lookup"><span data-stu-id="725d6-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="725d6-138">Microsoft 365 Gruppe</span><span class="sxs-lookup"><span data-stu-id="725d6-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="725d6-139">Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="725d6-139">Distribution group</span></span>
        - <span data-ttu-id="725d6-140">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="725d6-140">Security group</span></span>
        - <span data-ttu-id="725d6-141">E-Mail-aktivierte Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="725d6-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="725d6-142">Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter ["Gruppen vergleichen".](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="725d6-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="725d6-143">Um Benutzern das Ausführen ihrer Office Skripts in Power Automate Flüssen zu ermöglichen, wählen Sie **"Benutzer mit Zugriff auf Office Skripts ausführen ihre Skripts mit Power Automate .**</span><span class="sxs-lookup"><span data-stu-id="725d6-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="725d6-144">Auf diese Weise können Benutzer Flussschritte mit der **Skriptoption "Ausführen"** des [Excel Online (Business)-Connectors](/connectors/excelonlinebusiness) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="725d6-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="725d6-145">Damit alle Benutzer mit Zugriff auf Office Skripts ihre Skripts in Flüssen verwenden können, lassen **Sie "Jeder"** (Standard) ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="725d6-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="725d6-146">Damit nur Mitglieder einer bestimmten Gruppe mit Zugriff auf Office Skripts ihre Skripts in Flüssen verwenden können, wählen Sie **"Bestimmte Gruppe"** aus, und geben Sie dann den Namen oder E-Mail-Alias der Gruppe ein, um sie der Zulassungsliste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="725d6-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="725d6-147">Sie können der Zulassungsliste nur eine Gruppe hinzufügen, und dies muss einer der folgenden Typen sein:</span><span class="sxs-lookup"><span data-stu-id="725d6-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="725d6-148">Microsoft 365 Gruppe</span><span class="sxs-lookup"><span data-stu-id="725d6-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="725d6-149">Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="725d6-149">Distribution group</span></span>
        - <span data-ttu-id="725d6-150">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="725d6-150">Security group</span></span>
        - <span data-ttu-id="725d6-151">E-Mail-aktivierte Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="725d6-151">Mail-enabled security group</span></span>

        <span data-ttu-id="725d6-152">Weitere Informationen zu den verschiedenen Gruppentypen finden Sie unter ["Gruppen vergleichen".](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="725d6-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="725d6-153">Weitere Informationen zur Verwendung von Office Skripts mit Power Automate finden Sie unter [Ausführen Office Skripts mit Power Automate](/office/dev/scripts/develop/power-automate-integration).</span><span class="sxs-lookup"><span data-stu-id="725d6-153">To learn more about using Office Scripts with Power Automate, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="725d6-154">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="725d6-154">Select **Save**.</span></span>

    <span data-ttu-id="725d6-155">Es kann bis zu 48 Stunden dauern, bis Änderungen in den Einstellungen von Office-Skripts wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="725d6-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="725d6-156">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="725d6-156">Next steps</span></span>

<span data-ttu-id="725d6-157">Da Office Skripts mit Power Automate zusammenarbeiten, empfehlen wir, ihre vorhandenen DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) zu überprüfen, um sicherzustellen, dass die Daten Ihrer Organisation geschützt bleiben, während Benutzer Office Skripts verwenden.</span><span class="sxs-lookup"><span data-stu-id="725d6-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="725d6-158">Weitere Informationen finden Sie unter [Richtlinien zur Verhinderung von Datenverlust (DLP)](/power-automate/prevent-data-loss).</span><span class="sxs-lookup"><span data-stu-id="725d6-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="725d6-159">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="725d6-159">Related content</span></span>

<span data-ttu-id="725d6-160">[technische Dokumentation zu Office Skripts](/office/dev/scripts/) (Linkseite)</span><span class="sxs-lookup"><span data-stu-id="725d6-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="725d6-161">[Einführung in Office Skripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="725d6-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="725d6-162">[Freigeben Office Skripts in Excel für das Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="725d6-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="725d6-163">[Aufzeichnen, Bearbeiten und Erstellen Office Skripts in Excel im Web](/office/dev/scripts/tutorials/excel-tutorial) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="725d6-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
