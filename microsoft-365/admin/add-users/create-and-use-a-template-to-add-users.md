---
title: Erstellen und Verwenden einer Vorlage, um Benutzer hinzuzufügen
f1.keywords:
- NOCSH
ms.author: v-sharos
author: shars
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
- MSStore_Link
search.appverid:
- MET150
- MOE150
description: Sie können eine Vorlage erstellen und verwenden, um Zeit zu sparen und Einstellungen zu standardisieren, wenn Sie mehrere Benutzer hinzufügen.
ms.openlocfilehash: a39ad3df7928e45f7cb93a13c6ffc40111f2ee48
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140652"
---
# <a name="create-and-use-a-template-to-add-users"></a><span data-ttu-id="e7f6a-103">Erstellen und Verwenden einer Vorlage, um Benutzer hinzuzufügen</span><span class="sxs-lookup"><span data-stu-id="e7f6a-103">Create and use a template to add users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e7f6a-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-104">The admin center is changing.</span></span> <span data-ttu-id="e7f6a-105">Wenn Ihre Erfahrung nicht mit den hier dargestellten Details übereinstimmt, lesen Sie [Informationen zum neuen Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="e7f6a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e7f6a-106">Sie können eine Vorlage erstellen und verwenden, um Zeit zu sparen und Einstellungen zu standardisieren, wenn Sie mehrere Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-106">You can create and use a template to save time and standardize settings when you are adding multiple users.</span></span> <span data-ttu-id="e7f6a-107">Vorlagen sind besonders nützlich, wenn Sie über Benutzer verfügen, die viele allgemeine Eigenschaften aufweisen, beispielsweise diejenigen, die dieselbe Rolle haben und am gleichen Speicherort arbeiten und die dieselbe Software benötigen.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-107">Templates are particularly useful if you have users who share many common properties, like those who have the same role and work at the same location and those who require the same software.</span></span> <span data-ttu-id="e7f6a-108">Möglicherweise verfügen Sie über ein Team von Supportingenieuren, die im gleichen Büro arbeiten.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-108">For example, you might have a team of support engineers who work in the same office.</span></span>  

## <a name="create-a-template"></a><span data-ttu-id="e7f6a-109">Erstellen einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="e7f6a-109">Create a template</span></span>

<span data-ttu-id="e7f6a-110">Vorlagen sind einfach zu erstellen&mdash;Sie können Benutzer**Vorlagen**für **Benutzer** > **aktive** > Benutzer auswählen und dann in der Dropdownliste **eine Vorlage hinzufügen** auswählen, oder Sie können einen neuen Benutzer hinzufügen, und wenn Sie fertig sind, haben Sie die Möglichkeit, den Eintrag als Vorlage zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-110">Templates are easy to create&mdash;you can select **Users** > **Active users** > **User templates**, and then select **Add a template** from the drop-down list, or you can add a new user and when you are finished, you will have the option of saving the entry as a template.</span></span>

<span data-ttu-id="e7f6a-111">Wenn Sie nach dem Hinzufügen eines Benutzers eine Vorlage erstellen, werden die Werte, die Sie für die folgenden Einstellungen auswählen, in der Vorlage gespeichert:</span><span class="sxs-lookup"><span data-stu-id="e7f6a-111">When you create a template after adding a user, the values you choose for the following settings are saved in the template:</span></span>

- <span data-ttu-id="e7f6a-112">Domänenname</span><span class="sxs-lookup"><span data-stu-id="e7f6a-112">Domain name</span></span>
- <span data-ttu-id="e7f6a-113">Auswahl der Kennworteinstellungen: Sie können auswählen, ob Kennwörter erstellt oder automatisch generiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-113">Password settings choice: you can choose to create passwords or have them auto-generated</span></span>
- <span data-ttu-id="e7f6a-114">Auswahl eines einmaligen Kennworts: Sie können festlegen, dass der Benutzer nach dem ersten Anmelden ein neues Kennwort erstellt.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-114">One-time password choice: you can require the user to create a new password after first sign in</span></span>
- <span data-ttu-id="e7f6a-115">Lizenz Speicherort</span><span class="sxs-lookup"><span data-stu-id="e7f6a-115">License location</span></span>
- <span data-ttu-id="e7f6a-116">Lizenzauswahl</span><span class="sxs-lookup"><span data-stu-id="e7f6a-116">License choices</span></span>
- <span data-ttu-id="e7f6a-117">Anwendungsoptionen</span><span class="sxs-lookup"><span data-stu-id="e7f6a-117">Application choices</span></span>
- <span data-ttu-id="e7f6a-118">Rolle</span><span class="sxs-lookup"><span data-stu-id="e7f6a-118">Role</span></span>
- <span data-ttu-id="e7f6a-119">Die meisten Profilinformationen wie **Auftragsprofil**, **Abteilung**, **Office**, **Office Phone**und **Street Address**</span><span class="sxs-lookup"><span data-stu-id="e7f6a-119">Most profile information, such as **Job profile**, **Department**, **Office**, **Office phone**, and **Street address**</span></span> 

<span data-ttu-id="e7f6a-120">Die folgenden Informationen sind benutzerspezifisch und werden in der Vorlage nicht gespeichert:</span><span class="sxs-lookup"><span data-stu-id="e7f6a-120">The following information is user-specific and isn't saved in the template:</span></span>

- <span data-ttu-id="e7f6a-121">Vor- und Nachname</span><span class="sxs-lookup"><span data-stu-id="e7f6a-121">First and last name</span></span>
- <span data-ttu-id="e7f6a-122">Distinguished Name (DN)</span><span class="sxs-lookup"><span data-stu-id="e7f6a-122">Display name</span></span>
- <span data-ttu-id="e7f6a-123">Benutzername</span><span class="sxs-lookup"><span data-stu-id="e7f6a-123">User name</span></span>
- <span data-ttu-id="e7f6a-124">Auswahl, um das Kennwort in einer e-Mail zu senden und an wen die Kennwort-e-Mail gesendet wird</span><span class="sxs-lookup"><span data-stu-id="e7f6a-124">Choice to send the password in email and who the password email is sent to</span></span>
- <span data-ttu-id="e7f6a-125">Mobiltelefonnummer</span><span class="sxs-lookup"><span data-stu-id="e7f6a-125">Mobile phone number</span></span>

<span data-ttu-id="e7f6a-126">Wenn Sie keine Informationen für eine Einstellung in einem Abschnitt eingeben, ist dieser Wert leer, und diese Einstellung wird in der Vorlage nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-126">If you choose not to enter information for a setting within a section, that value will be blank and that setting will not display in the template.</span></span> <span data-ttu-id="e7f6a-127">Wenn Sie beispielsweise die **Position des Auftrags** leer lassen, wird bei der Überprüfung ihrer Vorlage und bei der Verwendung Ihrer Vorlage keine **Auftragsbezeichnung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-127">For example, if you leave **Job title** blank, when you review your template and when you use your template, **Job title** will not appear at all.</span></span> <span data-ttu-id="e7f6a-128">Wenn Sie alle **Profil** Abschnittseinstellungen leer lassen, wird im Abschnitt **Profil** keine in der endgültigen Vorlage **bereitgestellte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-128">If you leave all the **Profile** section settings blank, the **Profile** section will display **None provided** in your final template.</span></span>

<span data-ttu-id="e7f6a-129">Wenn Sie eine Vorlage erstellen, indem Sie die Option **Vorlage hinzufügen** auswählen, können Sie auswählen, welche Werte abgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-129">When you create a template by selecting the **Add a template** option, you can choose which values to complete.</span></span> <span data-ttu-id="e7f6a-130">Alle Elemente, die leer gelassen werden, werden in der Vorlage als **keine angegeben** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-130">Anything that is left blank will appear as **None provided** in the template.</span></span>

## <a name="use-a-template-to-add-a-user"></a><span data-ttu-id="e7f6a-131">Verwenden einer Vorlage zum Hinzufügen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="e7f6a-131">Use a template to add a user</span></span>

<span data-ttu-id="e7f6a-132">So verwenden Sie eine vorhandene Vorlage zum Hinzufügen eines Benutzers:</span><span class="sxs-lookup"><span data-stu-id="e7f6a-132">To use an existing template to add a user:</span></span>

1. <span data-ttu-id="e7f6a-133">Wählen Sie im Admin Center die Option **Users** > **Active Users**aus.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-133">In the admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="e7f6a-134">Wählen Sie **Benutzervorlagen**aus, und wählen Sie dann in der Dropdownliste eine Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-134">Select **User templates**, and then select a template from the drop-down list.</span></span> <span data-ttu-id="e7f6a-135">(Die Liste enthält nur die Vorlagen, die Sie erstellt haben, nicht jene, die von anderen Administratoren erstellt wurden.)</span><span class="sxs-lookup"><span data-stu-id="e7f6a-135">(The list will contain only the templates that you created, not those created by other admins.)</span></span>

 > [!NOTE]
 > <span data-ttu-id="e7f6a-136">Sie können auch eine Vorlage verwenden, um einen Benutzer hinzuzufügen, indem Sie **Benutzervorlagen** > Vorlagen**Verwalten**auswählen, eine Vorlage auswählen und dann **Vorlage verwenden**auswählen.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-136">You can also use a template to add a user by selecting **User templates** > **Manage templates**, selecting a template, and then selecting **Use template**.</span></span>

3. <span data-ttu-id="e7f6a-137">Führen Sie die Schritte aus, um einen Benutzer aus der ausgewählten Vorlage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-137">Follow the steps to create a user from the template you selected.</span></span>

> [!NOTE]
> <span data-ttu-id="e7f6a-138">Wenn Sie nicht über ausreichende Lizenzen für einen Benutzer verfügen, den Sie hinzufügen, und Ihre Zahlungsinformationen verfügbar sind, werden wir versuchen, eine andere Lizenz mit Ihren vorhandenen Zahlungsinformationen zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-138">If you have insufficient licenses available for a user that you add, and your payment information is available, we will attempt to purchase another license using your existing payment information.</span></span> <span data-ttu-id="e7f6a-139">Wenn Ihre Zahlungsinformationen nicht verfügbar sind, wird der Benutzer als nicht lizenzierter Benutzer erstellt.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-139">If your payment information is unavailable, the user will be created as an unlicensed user.</span></span>

## <a name="manage-templates"></a><span data-ttu-id="e7f6a-140">Vorlagen verwalten</span><span class="sxs-lookup"><span data-stu-id="e7f6a-140">Manage templates</span></span>

<span data-ttu-id="e7f6a-141">Vorlagen, die Sie nicht mehr benötigen, können Sie ganz einfach löschen und neue hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-141">You can easily delete templates you no longer need and add new ones.</span></span> <span data-ttu-id="e7f6a-142">So löschen Sie eine Vorlage:</span><span class="sxs-lookup"><span data-stu-id="e7f6a-142">To delete a template:</span></span>

1. <span data-ttu-id="e7f6a-143">Wählen Sie im Admin Center die Option **Users** > **Active Users**aus.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-143">In the admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="e7f6a-144">Wählen Sie **Vorlagen**aus, und wählen Sie dann **Vorlagen verwalten** in der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-144">Select **Templates**, and then select **Manage templates** from the drop-down list.</span></span>

3. <span data-ttu-id="e7f6a-145">Eine Liste mit Vorlagen wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-145">A list of templates will appear.</span></span> <span data-ttu-id="e7f6a-146">Sie können eine Vorlage löschen, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="e7f6a-146">You can delete a template by doing any of the following:</span></span>
    - <span data-ttu-id="e7f6a-147">Wählen Sie eine oder mehrere Vorlagen aus, und wählen Sie dann **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-147">Select one or more templates, and then select **Delete**.</span></span> 
    - <span data-ttu-id="e7f6a-148">Wählen Sie die drei Punkte rechts neben dem Vorlagennamen aus, und wählen Sie dann **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-148">Select the three dots to the right of the template name, and then select **Delete**.</span></span>
    - <span data-ttu-id="e7f6a-149">Wählen Sie den Vorlagennamen aus.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-149">Select the template name.</span></span> <span data-ttu-id="e7f6a-150">Wenn die Vorlagen Details auf der rechten Seite des Bildschirms angezeigt werden, wählen Sie **Vorlage löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="e7f6a-150">When the template details appear on the right side of your screen, select **Delete template**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e7f6a-151">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="e7f6a-151">Related articles</span></span>

[<span data-ttu-id="e7f6a-152">Hinzufügen von Benutzern einzeln oder in Massen zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7f6a-152">Add users individually or in bulk to Microsoft 365</span></span>](add-users.md)

[<span data-ttu-id="e7f6a-153">Entfernen eines ehemaligen Mitarbeiters aus Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7f6a-153">Remove a former employee from Microsoft 365</span></span>](remove-former-employee.md)
  
