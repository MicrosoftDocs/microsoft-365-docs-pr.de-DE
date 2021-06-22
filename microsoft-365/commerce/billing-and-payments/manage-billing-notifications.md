---
title: Verwalten von Benachrichtigungen zur Abrechnung und Rechnungsanlagen
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: prkalid, guyb
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
search.appverid:
- MET150
description: Erfahren Sie, wie Sie verwalten, wer Rechnungsbenachrichtigungs-E-Mails und Rechnungsanlagen empfängt.
ms.date: 03/17/2021
ms.openlocfilehash: f41d93835fed1715803052f1cf79b46f43a1d200
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054583"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="be655-103">Verwalten von Benachrichtigungen zur Abrechnung und Rechnungsanlagen</span><span class="sxs-lookup"><span data-stu-id="be655-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="be655-104">Auf der Seite **"Abrechnungsbenachrichtigungen"** können Sie verwalten, wer Abrechnungsbenachrichtigungs-E-Mails für Ihre Organisation empfängt.</span><span class="sxs-lookup"><span data-stu-id="be655-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="be655-105">Die Seite bietet auch die Möglichkeit, [die Rechnungen Ihrer Organisation als E-Mail-Anlagen](#receive-your-organizations-invoices-as-email-attachments)zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="be655-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="be655-106">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="be655-106">Before you begin</span></span>

<span data-ttu-id="be655-107">Sie müssen ein globaler Administrator sein, um die in diesem Artikel beschriebenen Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="be655-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="be655-108">Abrechnungsadministratoren können einige dieser Änderungen vornehmen, wie in den folgenden Abschnitten angegeben.</span><span class="sxs-lookup"><span data-stu-id="be655-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="be655-109">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="be655-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="be655-110">Ändern der Sprache, in der Sie eine E-Mail erhalten</span><span class="sxs-lookup"><span data-stu-id="be655-110">Change the language you receive email in</span></span>

<span data-ttu-id="be655-111">Rechnungsbenachrichtigungs-E-Mails werden in der bevorzugten Sprache Ihrer Organisation gesendet.</span><span class="sxs-lookup"><span data-stu-id="be655-111">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="be655-112">Führen Sie die folgenden Schritte aus, um die bevorzugte Sprache zu ändern.</span><span class="sxs-lookup"><span data-stu-id="be655-112">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="be655-113">Wechseln Sie im Microsoft 365 Admin Center zur   >  Seite<a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">"Abrechnungsbenachrichtigungen".</a></span><span class="sxs-lookup"><span data-stu-id="be655-113">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="be655-114">Wählen Sie im Abschnitt **"Einstellungen für Abrechnungsbenachrichtigungen"** die **Option "Benachrichtigungseinstellungen bearbeiten" aus.**</span><span class="sxs-lookup"><span data-stu-id="be655-114">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="be655-115">Wählen Sie im Bereich "Einstellungen für **Abrechnungsbenachrichtigungen"** unter **"Bevorzugte Sprache"** die gewünschte Sprache aus, und wählen Sie dann **"Speichern"** aus.</span><span class="sxs-lookup"><span data-stu-id="be655-115">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="be655-116">Ändern, wer Abrechnungsbenachrichtigungen empfängt</span><span class="sxs-lookup"><span data-stu-id="be655-116">Change who receives billing notifications</span></span>

<span data-ttu-id="be655-117">Die Abrechnungsbenachrichtigungen Ihrer Organisation werden an die primäre und alternative E-Mail-Adresse jedes globalen und Abrechnungsadministrators gesendet. Führen Sie die folgenden Schritte aus, um zu ändern, welche Benutzer über die Rolle "Globaler Administrator" oder "Abrechnungsadministrator" verfügen.</span><span class="sxs-lookup"><span data-stu-id="be655-117">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="be655-118">Zuweisen von Administratorrollen über die Seite "Abrechnungsbenachrichtigungen"</span><span class="sxs-lookup"><span data-stu-id="be655-118">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="be655-119">Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.</span><span class="sxs-lookup"><span data-stu-id="be655-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="be655-120">Wählen Sie im Abschnitt **"Administratoren, die Abrechnungsbenachrichtigungen erhalten"** den Link **"Abrechnungsadministrator"** oder **"Globaler Administrator"** im Beschreibungstext aus.</span><span class="sxs-lookup"><span data-stu-id="be655-120">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="be655-121">Wählen Sie im rechten Bereich auf der Registerkarte **"Zugewiesene Administratoren"** die Option **"Hinzufügen"** aus.</span><span class="sxs-lookup"><span data-stu-id="be655-121">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="be655-122">Geben Sie im Bereich **"Administratoren hinzufügen"** den Anzeigenamen oder Benutzernamen des Benutzers ein, und wählen Sie dann den Benutzer aus der Liste der Vorschläge aus.</span><span class="sxs-lookup"><span data-stu-id="be655-122">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="be655-123">Fügen Sie mehrere Benutzer hinzu, bis Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="be655-123">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="be655-124">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="be655-124">Select **Save**.</span></span> <span data-ttu-id="be655-125">Der Benutzer wird der Liste der zugewiesenen Administratoren hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be655-125">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="be655-126">Entfernen von Administratorrollen über die Seite "Abrechnungsbenachrichtigungen"</span><span class="sxs-lookup"><span data-stu-id="be655-126">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="be655-127">Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.</span><span class="sxs-lookup"><span data-stu-id="be655-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="be655-128">Wählen Sie im Abschnitt **"Administratoren, die Abrechnungsbenachrichtigungen erhalten"** den Link **"Abrechnungsadministrator"** oder **"Globaler Administrator"** im Beschreibungstext aus.</span><span class="sxs-lookup"><span data-stu-id="be655-128">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="be655-129">Wählen Sie im rechten Bereich auf der Registerkarte **"Zugewiesene Administratoren"** die Benutzer aus, die aus der Rolle entfernt werden sollen, und wählen Sie dann **"Entfernen"** aus.</span><span class="sxs-lookup"><span data-stu-id="be655-129">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="be655-130">Wählen Sie im Bestätigungsfeld **"Entfernen" aus.**</span><span class="sxs-lookup"><span data-stu-id="be655-130">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="be655-131">Der Benutzer wird aus der Liste der zugewiesenen Administratoren entfernt.</span><span class="sxs-lookup"><span data-stu-id="be655-131">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="be655-132">Ändern der E-Mail-Adressen für Administratoren</span><span class="sxs-lookup"><span data-stu-id="be655-132">Change the email addresses for admins</span></span>

<span data-ttu-id="be655-133">Um die primäre und alternative E-Mail-Adresse anderer Administratoren in Ihrer Organisation zu ändern, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="be655-133">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="be655-134">Abrechnungsadministratoren können ihre eigenen primären und alternativen E-Mail-Adressen ändern, jedoch nicht für andere Administratoren.</span><span class="sxs-lookup"><span data-stu-id="be655-134">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="be655-135">Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.</span><span class="sxs-lookup"><span data-stu-id="be655-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="be655-136">Wählen Sie im Abschnitt **"Administratoren, die Abrechnungsbenachrichtigungen erhalten"** einen Namen aus.</span><span class="sxs-lookup"><span data-stu-id="be655-136">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="be655-137">Fügen Sie im rechten Bereich die primäre und alternative E-Mail-Adresse nach Bedarf hinzu oder aktualisieren Sie sie, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="be655-137">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="be655-138">Ändern der Kontakt-E-Mail-Adresse Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="be655-138">Change your organization's contact email</span></span>

<span data-ttu-id="be655-139">Zusätzlich zu Ihren globalen Administratoren und Abrechnungsadministratoren senden wir Abrechnungsbenachrichtigungen an die E-Mail-Kontaktadresse Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="be655-139">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="be655-140">Führen Sie die folgenden Schritte aus, um die E-Mail-Adresse zu ändern.</span><span class="sxs-lookup"><span data-stu-id="be655-140">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="be655-141">Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.</span><span class="sxs-lookup"><span data-stu-id="be655-141">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="be655-142">Wählen Sie unter **Organisationskontakt, der Abrechnungsbenachrichtigungen empfängt,** den Organisationskontakt aus.</span><span class="sxs-lookup"><span data-stu-id="be655-142">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="be655-143">Geben Sie im rechten Bereich die E-Mail-Adresse ein, die Sie verwenden möchten, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="be655-143">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="be655-144">Empfangen der Rechnungen Ihrer Organisation als E-Mail-Anlagen</span><span class="sxs-lookup"><span data-stu-id="be655-144">Receive your organization's invoices as email attachments</span></span>

> [!NOTE]
> <span data-ttu-id="be655-145">Abrechnungsadministratoren können auch die Schritte in diesem Abschnitt ausführen.</span><span class="sxs-lookup"><span data-stu-id="be655-145">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="be655-146">Sie können eine Kopie der Rechnung Ihrer Organisation als PDF-Datei an E-Mails mit Rechnungsbenachrichtigungen anhängen lassen, wenn eine neue Rechnung fertig ist.</span><span class="sxs-lookup"><span data-stu-id="be655-146">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="be655-147">Gehen Sie folgendermaßen vor, um Rechnungen als Anlagen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="be655-147">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="be655-148">Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.</span><span class="sxs-lookup"><span data-stu-id="be655-148">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="be655-149">Wählen Sie unter **"Abrechnungsbenachrichtigungseinstellungen"** die Option **"Benachrichtigungseinstellungen bearbeiten" aus.**</span><span class="sxs-lookup"><span data-stu-id="be655-149">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="be655-150">Aktivieren Sie im Bereich "Einstellungen für **Abrechnungsbenachrichtigungen"** unter **"PDF an Ihre Rechnungs-E-Mails anhängen"** das Kontrollkästchen, und wählen Sie **"Speichern"** aus.</span><span class="sxs-lookup"><span data-stu-id="be655-150">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="be655-151">Um den Empfang der Rechnungsanlage jederzeit zu beenden, führen Sie die oben beschriebenen Schritte aus, und deaktivieren Sie das Kontrollkästchen **"PDF an Ihre E-Mails** an Rechnung anhängen" in Schritt 3.</span><span class="sxs-lookup"><span data-stu-id="be655-151">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="be655-152">Was geschieht, wenn ich ein Abrechnungsprofil habe?</span><span class="sxs-lookup"><span data-stu-id="be655-152">What if I have a billing profile?</span></span>

<span data-ttu-id="be655-153">Wenn Sie über ein Abrechnungsprofil verfügen, können sich einige der in diesem Artikel beschriebenen Schritte für einige Ihrer Abonnements geringfügig unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="be655-153">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="be655-154">In diesem Abschnitt werden diese Unterschiede beschrieben.</span><span class="sxs-lookup"><span data-stu-id="be655-154">This section describes those differences.</span></span> [<span data-ttu-id="be655-155">Woher weiß ich, ob ich ein Abrechnungsprofil habe?</span><span class="sxs-lookup"><span data-stu-id="be655-155">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="be655-156">Wer erhält Abrechnungsbenachrichtigungen?</span><span class="sxs-lookup"><span data-stu-id="be655-156">Who receives Billing notifications?</span></span>

<span data-ttu-id="be655-157">Abrechnungsbenachrichtigungs-E-Mails werden an die primären und alternativen E-Mail-Adressen für Benutzer gesendet, denen eine der folgenden Rollen zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="be655-157">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="be655-158">Besitzer des Abrechnungsprofils</span><span class="sxs-lookup"><span data-stu-id="be655-158">Billing profile owner</span></span>
- <span data-ttu-id="be655-159">Abrechnungsprofilmitwirkender</span><span class="sxs-lookup"><span data-stu-id="be655-159">Billing profile contributor</span></span>
- <span data-ttu-id="be655-160">Rechnungsmanager</span><span class="sxs-lookup"><span data-stu-id="be655-160">Invoice manager</span></span>

<span data-ttu-id="be655-161">Weitere Informationen zu Rollen für Abrechnungsprofilen und deren Verwaltung finden Sie unter ["Grundlegendes zu Verwaltungsrollen der Microsoft-Kundenvereinbarung" in Azure.](/azure/cost-management-billing/manage/understand-mca-roles)</span><span class="sxs-lookup"><span data-stu-id="be655-161">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="be655-162">Um zu ändern, wer die Abrechnungsbenachrichtigungen Ihrer Organisation erhält, verwenden Sie die folgenden Schritte, um die Den Benutzern zugewiesenen Rollen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="be655-162">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="be655-163">Wechseln Sie im Admin Center zur Seite **"Abrechnungsrechnungen**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">& Zahlungen".</a></span><span class="sxs-lookup"><span data-stu-id="be655-163">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="be655-164">Wählen Sie auf der Registerkarte **"Abrechnungsprofil"** ein Abrechnungsprofil aus.</span><span class="sxs-lookup"><span data-stu-id="be655-164">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="be655-165">Weisen Sie im Abschnitt **"Abrechnungsprofilrollen"** Rollen für den Besitzer des **Abrechnungsprofils,** den **Abrechnungsprofilmitwirkenden** oder **den Rechnungsverwalter** zu oder entfernen Sie diese.</span><span class="sxs-lookup"><span data-stu-id="be655-165">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="be655-166">Empfangen von Rechnungen als E-Mail-Anlagen</span><span class="sxs-lookup"><span data-stu-id="be655-166">Receive invoices as email attachments</span></span>

<span data-ttu-id="be655-167">Um Ihre Rechnungen als Anlagen zu Ihren Rechnungsbenachrichtigungen zu erhalten, verwenden Sie die folgenden Schritte, um diese Einstellung für ein bestimmtes Abrechnungsprofil zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="be655-167">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="be655-168">Wechseln Sie im Admin Center zur Seite **"Abrechnungsrechnungen**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">& Zahlungen".</a></span><span class="sxs-lookup"><span data-stu-id="be655-168">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="be655-169">Wählen Sie die Registerkarte **"Abrechnungsprofile"** und dann ein Abrechnungsprofil aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="be655-169">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="be655-170">Wechseln Sie auf der Seite "Abrechnungsprofildetails" unter **"Rechnungen in E-Mail-Anlagen abrufen"** zu **"Ein".**</span><span class="sxs-lookup"><span data-stu-id="be655-170">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="be655-171">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="be655-171">Related content</span></span>

<span data-ttu-id="be655-172">[Anzeigen Ihrer Rechnung](view-your-bill-or-invoice.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="be655-172">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="be655-173">[Abrechnungsinformationen für Microsoft 365 für Unternehmen in Mexiko](/microsoft-365/commerce/billing-and-payments/mexico-billing-info) (Artikel) </span><span class="sxs-lookup"><span data-stu-id="be655-173">[Billing information for Microsoft 365 for business in Mexico](/microsoft-365/commerce/billing-and-payments/mexico-billing-info) (article) </span></span>\
<span data-ttu-id="be655-174">[Grundlegendes zu Ihrer Rechnung für Microsoft 365 business](understand-your-invoice2.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="be655-174">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="be655-175">[Gleichzeitiges Hinzufügen von Benutzern und Zuweisen von Lizenzen](../../admin/add-users/add-users.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="be655-175">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>
