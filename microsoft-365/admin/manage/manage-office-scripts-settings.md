---
title: Office-Skripts-Einstellungen verwalten
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
description: Hier erfahren Sie, wie Sie Office-Skripteinstellungen für Benutzer in Ihrer Organisation verwalten.
ms.openlocfilehash: 44e2a5c0e0577db344fdbb00a110674df3e71bdc
ms.sourcegitcommit: 04f196528a7a91b404478553433af3fa94d7eee7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2020
ms.locfileid: "47317493"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="fea84-103">Office-Skripts-Einstellungen verwalten</span><span class="sxs-lookup"><span data-stu-id="fea84-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="fea84-104">Office-Skripts ermöglichen Benutzern das Automatisieren von Aufgaben durch aufzeichnen, bearbeiten und Ausführen von Skripts in Excel im Internet.</span><span class="sxs-lookup"><span data-stu-id="fea84-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="fea84-105">Office-Skripts arbeiten mit Power Automation, und Benutzer führen Skripts für Arbeitsmappen mithilfe des Excel Online (Business)-Connectors aus.</span><span class="sxs-lookup"><span data-stu-id="fea84-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="fea84-106">Microsoft 365-Administratoren können Office-Skripteinstellungen im Microsoft 365 Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="fea84-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fea84-107">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="fea84-107">Before you begin</span></span>

- <span data-ttu-id="fea84-108">Zum Verwalten von Office-Skripteinstellungen müssen Sie ein globaler Administrator sein. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="fea84-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="fea84-109">Stellen Sie sicher, dass Benutzer in Ihrer Organisation über eine gültige Lizenz für einen Microsoft 365-oder Office 365-Geschäfts-oder-edu-Plan verfügen, der Zugriff auf Office-Desktop-Apps umfasst, beispielsweiseeines der folgenden Pläne:</span><span class="sxs-lookup"><span data-stu-id="fea84-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="fea84-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="fea84-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="fea84-111">Microsoft 365 Apps for Business</span><span class="sxs-lookup"><span data-stu-id="fea84-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="fea84-112">Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="fea84-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="fea84-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="fea84-113">Office 365 E3</span></span>
    - <span data-ttu-id="fea84-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="fea84-114">Office 365 E5</span></span>
    - <span data-ttu-id="fea84-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="fea84-115">Office 365 A3</span></span>
    - <span data-ttu-id="fea84-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="fea84-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="fea84-117">Verwalten der Verfügbarkeit von Office-Skripts und der Freigabe von Skripts</span><span class="sxs-lookup"><span data-stu-id="fea84-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="fea84-118">Wechseln Sie im Microsoft 365 Admin Center zur Registerkarte **Settings** \> **org Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> .</span><span class="sxs-lookup"><span data-stu-id="fea84-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="fea84-119">Wählen Sie **Office-Skripts**aus.</span><span class="sxs-lookup"><span data-stu-id="fea84-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="fea84-120">Office-Skripts sind standardmäßig aktiviert, und jeder in Ihrer Organisation kann auf das Feature und die Freigabe von Skripts zugreifen und diese verwenden.</span><span class="sxs-lookup"><span data-stu-id="fea84-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="fea84-121">Wenn Sie Office-Skripts für Ihre Organisation deaktivieren möchten, deaktivieren Sie das Kontrollkästchen zulassen, dass **Benutzer ihre Aufgaben in Excel im Internet automatisieren** .</span><span class="sxs-lookup"><span data-stu-id="fea84-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="fea84-122">Wenn Sie zuvor Office-Skripts für Ihre Organisation deaktiviert haben und Sie wieder aktivieren möchten, wählen Sie **Benutzer können Ihre Aufgaben in Excel im Internet automatisieren**aus, und geben Sie dann an, wer auf das Feature zugreifen und dieses verwenden kann:</span><span class="sxs-lookup"><span data-stu-id="fea84-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="fea84-123">Wenn Sie allen Benutzern in Ihrer Organisation den Zugriff auf und die Verwendung von Office-Skripts gestatten möchten, lassen Sie **alle** (Standard) ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="fea84-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span> 

    - <span data-ttu-id="fea84-124">Wenn Sie nur Mitgliedern einer bestimmten Gruppe den Zugriff auf und die Verwendung von Office-Skripts gestatten möchten, wählen Sie **bestimmte Gruppe**aus, und geben Sie dann den Namen oder e-Mail-Alias der Gruppe ein, um ihn der Zulassungsliste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fea84-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="fea84-125">Sie können nur eine Gruppe zur Zulassungsliste hinzufügen, und es muss sich um einen der folgenden Typen handeln:</span><span class="sxs-lookup"><span data-stu-id="fea84-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="fea84-126">Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="fea84-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="fea84-127">Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="fea84-127">Distribution group</span></span>
        - <span data-ttu-id="fea84-128">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fea84-128">Security group</span></span>
        - <span data-ttu-id="fea84-129">E-Mail-aktivierte Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fea84-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="fea84-130">Weitere Informationen zu den verschiedenen Typen von Gruppen finden Sie unter [Compare Groups](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="fea84-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="fea84-131">Um Benutzern mit Zugriff auf Office-Skripts das Freigeben Ihrer Skripts für andere Personen in Ihrer Organisation zu ermöglichen, wählen Sie **Benutzer mit Zugriff auf Office-Skripts zulassen, dass Ihre Skripts für andere Personen in der Organisation freigegeben**werden.</span><span class="sxs-lookup"><span data-stu-id="fea84-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="fea84-132">Das Freigeben von Skripts außerhalb einer Organisation ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="fea84-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="fea84-133">Wenn Sie später die Skript Freigabe für Ihre Organisation deaktivieren, können Benutzer weiterhin zuvor freigegebene Skripts ausführen.</span><span class="sxs-lookup"><span data-stu-id="fea84-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="fea84-134">Geben Sie an, welche Benutzer mit Zugriff auf Office-Skripts Ihre Skripts freigeben können:</span><span class="sxs-lookup"><span data-stu-id="fea84-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="fea84-135">Damit alle Benutzer, die Zugriff auf Office-Skripts haben, Ihre Skripts freigeben können, lassen Sie **alle** (Standard) ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="fea84-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="fea84-136">Wenn Sie nur Mitgliedern einer bestimmten Gruppe mit Zugriff auf Office-Skripts das Freigeben Ihrer Skripts gestatten möchten, wählen Sie **bestimmte Gruppe**aus, und geben Sie dann den Namen oder e-Mail-Alias der Gruppe ein, um Sie der Zulassungsliste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fea84-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="fea84-137">Sie können nur eine Gruppe zur Zulassungsliste hinzufügen, und es muss sich um einen der folgenden Typen handeln:</span><span class="sxs-lookup"><span data-stu-id="fea84-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="fea84-138">Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="fea84-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="fea84-139">Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="fea84-139">Distribution group</span></span>
        - <span data-ttu-id="fea84-140">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fea84-140">Security group</span></span>
        - <span data-ttu-id="fea84-141">E-Mail-aktivierte Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fea84-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="fea84-142">Weitere Informationen zu den verschiedenen Typen von Gruppen finden Sie unter [Compare Groups](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="fea84-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="fea84-143">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fea84-143">Select **Save**.</span></span>

    <span data-ttu-id="fea84-144">Es kann bis zu 48 Stunden dauern, bis Änderungen an Office-Skripteinstellungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="fea84-144">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fea84-145">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fea84-145">Next steps</span></span>

<span data-ttu-id="fea84-146">Da Office-Skripts mit Power Automation verwendet werden, sollten Sie die vorhandenen DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) überprüfen, um sicherzustellen, dass die Daten Ihrer Organisation geschützt bleiben, während Benutzer Office-Skripts verwenden.</span><span class="sxs-lookup"><span data-stu-id="fea84-146">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="fea84-147">Weitere Informationen finden Sie unter [Richtlinien zur Verhinderung von Datenverlust (DLP)](/power-automate/prevent-data-loss).</span><span class="sxs-lookup"><span data-stu-id="fea84-147">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="fea84-148">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="fea84-148">Related content</span></span>

<span data-ttu-id="fea84-149">[Technische Dokumentation zu Office-Skripts](/office/dev/scripts/) (Linkseite) </span><span class="sxs-lookup"><span data-stu-id="fea84-149">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="fea84-150">[Einführung in Office-Skripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (Artikel) </span><span class="sxs-lookup"><span data-stu-id="fea84-150">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="fea84-151">[Freigeben von Office-Skripts in Excel für das Internet](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (Artikel) </span><span class="sxs-lookup"><span data-stu-id="fea84-151">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="fea84-152">[Aufzeichnen, bearbeiten und Erstellen von Office-Skripts in Excel im Internet](/office/dev/scripts/tutorials/excel-tutorial) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="fea84-152">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>