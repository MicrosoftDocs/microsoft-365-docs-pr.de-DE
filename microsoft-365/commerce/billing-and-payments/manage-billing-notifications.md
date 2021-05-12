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
ms.openlocfilehash: d4083dc5a9d70eb8c20b4107389ec5fec65749ad
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332138"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="7adae-103">Verwalten von Benachrichtigungen zur Abrechnung und Rechnungsanlagen</span><span class="sxs-lookup"><span data-stu-id="7adae-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="7adae-104">Auf **der Seite Abrechnungsbenachrichtigungen** können Sie verwalten, wer Rechnungsbenachrichtigungs-E-Mails für Ihre Organisation empfängt.</span><span class="sxs-lookup"><span data-stu-id="7adae-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="7adae-105">Die Seite bietet auch die Möglichkeit, die Rechnungen Ihrer Organisation [als E-Mail-Anlagen zu empfangen.](#receive-your-organizations-invoices-as-email-attachments)</span><span class="sxs-lookup"><span data-stu-id="7adae-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7adae-106">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="7adae-106">Before you begin</span></span>

<span data-ttu-id="7adae-107">Sie müssen ein globaler Administrator sein, um die in diesem Artikel beschriebenen Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="7adae-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="7adae-108">Abrechnungsadministratoren können einige dieser Änderungen vornehmen, wie in den folgenden Abschnitten erwähnt.</span><span class="sxs-lookup"><span data-stu-id="7adae-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="7adae-109">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7adae-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="7adae-110">Ändern der Sprache, in der Sie E-Mails erhalten</span><span class="sxs-lookup"><span data-stu-id="7adae-110">Change the language you receive email in</span></span>

> [!NOTE]
> <span data-ttu-id="7adae-111">Abrechnungsadministratoren können auch die Schritte in diesem Abschnitt ausführen.</span><span class="sxs-lookup"><span data-stu-id="7adae-111">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="7adae-112">Abrechnungsbenachrichtigungs-E-Mails werden in der bevorzugten Sprache Ihrer Organisation gesendet.</span><span class="sxs-lookup"><span data-stu-id="7adae-112">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="7adae-113">Um die bevorzugte Sprache zu ändern, verwenden Sie die folgenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="7adae-113">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="7adae-114">Wechseln Sie im Microsoft 365 Admin Center zur **Seite**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen.</a></span><span class="sxs-lookup"><span data-stu-id="7adae-114">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="7adae-115">Wählen Sie **im Abschnitt Abrechnungsbenachrichtigungseinstellungen** die Option **Benachrichtigungseinstellungen bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="7adae-115">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="7adae-116">Wählen Sie **im Bereich** Abrechnungsbenachrichtigungseinstellungen **unter** Bevorzugte Sprache die gewünschte Sprache aus, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="7adae-116">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="7adae-117">Ändern, wer Abrechnungsbenachrichtigungen erhält</span><span class="sxs-lookup"><span data-stu-id="7adae-117">Change who receives billing notifications</span></span>

<span data-ttu-id="7adae-118">Die Abrechnungsbenachrichtigungen Ihrer Organisation werden an die primäre und alternative E-Mail-Adresse jedes globalen und Abrechnungsadministrators gesendet. Verwenden Sie die folgenden Schritte, um zu ändern, welche Benutzer die Administratorrolle "Global" oder "Abrechnung" haben.</span><span class="sxs-lookup"><span data-stu-id="7adae-118">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="7adae-119">Zuweisen von Administratorrollen mithilfe der Seite Abrechnungsbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="7adae-119">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="7adae-120">Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.</span><span class="sxs-lookup"><span data-stu-id="7adae-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="7adae-121">Wählen Sie **im Abschnitt Admins receiving billing notifications** den Link **Abrechnungsadministrator** oder **globaler** Administrator im Beschreibungstext aus.</span><span class="sxs-lookup"><span data-stu-id="7adae-121">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="7adae-122">Wählen Sie im rechten Bereich auf der Registerkarte **Zugewiesene Administratoren** die Option **Hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="7adae-122">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="7adae-123">Geben Sie im Bereich Administrator **hinzufügen** den Anzeigenamen oder Benutzernamen des Benutzers ein, und wählen Sie dann den Benutzer aus der Liste der Vorschläge aus.</span><span class="sxs-lookup"><span data-stu-id="7adae-123">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="7adae-124">Fügen Sie mehrere Benutzer hinzu, bis Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="7adae-124">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="7adae-125">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="7adae-125">Select **Save**.</span></span> <span data-ttu-id="7adae-126">Der Benutzer wird der Liste der zugewiesenen Administratoren hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7adae-126">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="7adae-127">Entfernen von Administratorrollen mithilfe der Seite Abrechnungsbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="7adae-127">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="7adae-128">Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.</span><span class="sxs-lookup"><span data-stu-id="7adae-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="7adae-129">Wählen Sie **im Abschnitt Admins receiving billing notifications** den Link **Abrechnungsadministrator** oder **globaler** Administrator im Beschreibungstext aus.</span><span class="sxs-lookup"><span data-stu-id="7adae-129">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="7adae-130">Wählen Sie im rechten Bereich auf der Registerkarte Zugewiesene **Administratoren** die Zu entfernenden Benutzer aus der Rolle aus, und wählen Sie dann **Entfernen aus.**</span><span class="sxs-lookup"><span data-stu-id="7adae-130">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="7adae-131">Wählen Sie im Bestätigungsfeld Entfernen **aus.**</span><span class="sxs-lookup"><span data-stu-id="7adae-131">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="7adae-132">Der Benutzer wird aus der Liste der zugewiesenen Administratoren entfernt.</span><span class="sxs-lookup"><span data-stu-id="7adae-132">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="7adae-133">Ändern der E-Mail-Adressen für Administratoren</span><span class="sxs-lookup"><span data-stu-id="7adae-133">Change the email addresses for admins</span></span>

<span data-ttu-id="7adae-134">Verwenden Sie die folgenden Schritte, um die primäre und alternative E-Mail-Adresse anderer Administratoren in Ihrer Organisation zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7adae-134">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="7adae-135">Abrechnungsadministratoren können ihre eigenen primären und alternativen E-Mail-Adressen ändern, jedoch nicht für andere Administratoren.</span><span class="sxs-lookup"><span data-stu-id="7adae-135">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="7adae-136">Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.</span><span class="sxs-lookup"><span data-stu-id="7adae-136">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="7adae-137">Wählen Sie **im Abschnitt Admins receiving billing notifications** einen Namen aus.</span><span class="sxs-lookup"><span data-stu-id="7adae-137">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="7adae-138">Fügen Sie im rechten Bereich die primäre und alternative E-Mail-Adresse nach Bedarf hinzu, oder aktualisieren Sie sie, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="7adae-138">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="7adae-139">Ändern der Kontakt-E-Mail Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="7adae-139">Change your organization's contact email</span></span>

<span data-ttu-id="7adae-140">Zusätzlich zu Ihren globalen und Abrechnungsadministratoren senden wir Abrechnungsbenachrichtigungen an die E-Mail-Adresse Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="7adae-140">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="7adae-141">Um die E-Mail-Adresse zu ändern, verwenden Sie die folgenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="7adae-141">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="7adae-142">Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.</span><span class="sxs-lookup"><span data-stu-id="7adae-142">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="7adae-143">Wählen **Sie unter Organisationskontakt, der Abrechnungsbenachrichtigungen empfängt,** den Organisationskontakt aus.</span><span class="sxs-lookup"><span data-stu-id="7adae-143">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="7adae-144">Geben Sie im rechten Bereich die E-Mail-Adresse ein, die Sie verwenden möchten, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="7adae-144">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="7adae-145">Empfangen der Rechnungen Ihrer Organisation als E-Mail-Anlagen</span><span class="sxs-lookup"><span data-stu-id="7adae-145">Receive your organization's invoices as email attachments</span></span>

> [!NOTE]
> <span data-ttu-id="7adae-146">Abrechnungsadministratoren können auch die Schritte in diesem Abschnitt ausführen.</span><span class="sxs-lookup"><span data-stu-id="7adae-146">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="7adae-147">Sie können eine Kopie der Rechnung Ihrer Organisation als PDF-Datei an die Rechnung von Benachrichtigungs-E-Mails angefügt haben, wenn eine neue Rechnung bereit ist.</span><span class="sxs-lookup"><span data-stu-id="7adae-147">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="7adae-148">Verwenden Sie die folgenden Schritte, um Rechnungen als Anlagen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="7adae-148">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="7adae-149">Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.</span><span class="sxs-lookup"><span data-stu-id="7adae-149">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="7adae-150">Wählen **Sie unter Abrechnungsbenachrichtigungseinstellungen** die **Option Benachrichtigungseinstellungen bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="7adae-150">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="7adae-151">Aktivieren Sie **im** Bereich Abrechnungsbenachrichtigungseinstellungen unter Anfügen einer PDF an Ihre **Rechnungs-E-Mails** das Kontrollkästchen, und wählen Sie **dann Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="7adae-151">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="7adae-152">Um den Empfang der Rechnungsanlage jederzeit zu beenden, führen Sie die obigen Schritte aus, und aktivieren Sie das Kontrollkästchen **Pdf** an Ihre Rechnungs-E-Mails anfügen in Schritt 3.</span><span class="sxs-lookup"><span data-stu-id="7adae-152">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="7adae-153">Was passiert, wenn ich ein Abrechnungsprofil habe?</span><span class="sxs-lookup"><span data-stu-id="7adae-153">What if I have a billing profile?</span></span>

<span data-ttu-id="7adae-154">Wenn Sie über ein Abrechnungsprofil verfügen, unterscheiden sich einige der in diesem Artikel beschriebenen Schritte für einige Ihrer Abonnements möglicherweise geringfügig.</span><span class="sxs-lookup"><span data-stu-id="7adae-154">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="7adae-155">In diesem Abschnitt werden diese Unterschiede beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7adae-155">This section describes those differences.</span></span> [<span data-ttu-id="7adae-156">Wo kann ich wissen, ob ich ein Abrechnungsprofil habe?</span><span class="sxs-lookup"><span data-stu-id="7adae-156">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="7adae-157">Wer empfängt Abrechnungsbenachrichtigungen?</span><span class="sxs-lookup"><span data-stu-id="7adae-157">Who receives Billing notifications?</span></span>

<span data-ttu-id="7adae-158">Abrechnungsbenachrichtigungs-E-Mails werden an die primären und alternativen E-Mail-Adressen für Benutzer gesendet, denen eine der folgenden Rollen zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="7adae-158">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="7adae-159">Abrechnungsprofilbesitzer</span><span class="sxs-lookup"><span data-stu-id="7adae-159">Billing profile owner</span></span>
- <span data-ttu-id="7adae-160">Mitwirkender des Abrechnungsprofils</span><span class="sxs-lookup"><span data-stu-id="7adae-160">Billing profile contributor</span></span>
- <span data-ttu-id="7adae-161">Rechnungs-Manager</span><span class="sxs-lookup"><span data-stu-id="7adae-161">Invoice manager</span></span>

<span data-ttu-id="7adae-162">Weitere Informationen zu Abrechnungsprofilrollen und deren Verwaltung finden Sie unter [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span><span class="sxs-lookup"><span data-stu-id="7adae-162">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="7adae-163">Um zu ändern, wer die Abrechnungsbenachrichtigungen Ihrer Organisation empfängt, verwenden Sie die folgenden Schritte, um die Den Benutzern zugewiesenen Rollen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7adae-163">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="7adae-164">Wechseln Sie im Admin Center zur Seite  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Abrechnungsrechnungen & Zahlungen.</a></span><span class="sxs-lookup"><span data-stu-id="7adae-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="7adae-165">Wählen Sie **auf der Registerkarte** Abrechnungsprofil ein Abrechnungsprofil aus.</span><span class="sxs-lookup"><span data-stu-id="7adae-165">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="7adae-166">Weisen Sie **im Abschnitt Abrechnungsprofilrollen** Rollen für Abrechnungsprofilbesitzer,  **Abrechnungsprofilbeitragszahler** oder **Rechnungs-Manager zu** oder entfernen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="7adae-166">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="7adae-167">Empfangen von Rechnungen als E-Mail-Anlagen</span><span class="sxs-lookup"><span data-stu-id="7adae-167">Receive invoices as email attachments</span></span>

<span data-ttu-id="7adae-168">Um Ihre Rechnungen als Anlagen zu Ihren Rechnungsbenachrichtigungen zu erhalten, verwenden Sie die folgenden Schritte, um diese Einstellung für ein bestimmtes Abrechnungsprofil zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7adae-168">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="7adae-169">Wechseln Sie im Admin Center zur Seite  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Abrechnungsrechnungen & Zahlungen.</a></span><span class="sxs-lookup"><span data-stu-id="7adae-169">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="7adae-170">Wählen Sie **die Registerkarte Abrechnungsprofile** aus, und wählen Sie dann ein Abrechnungsprofil aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="7adae-170">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="7adae-171">Wechseln Sie auf der Seite **Abrechnungsprofildetails** unter Rechnungen in E-Mail-Anlagen erhalten zu **Ein**.</span><span class="sxs-lookup"><span data-stu-id="7adae-171">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="7adae-172">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="7adae-172">Related content</span></span>

<span data-ttu-id="7adae-173">[Anzeigen Ihrer Rechnung](view-your-bill-or-invoice.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="7adae-173">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="7adae-174">[Verstehen Ihrer Rechnung oder Rechnung für Microsoft 365 Business](understand-your-invoice2.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="7adae-174">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="7adae-175">[Hinzufügen von Benutzern und gleichzeitiges Zuweisen von Lizenzen](../../admin/add-users/add-users.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="7adae-175">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>
