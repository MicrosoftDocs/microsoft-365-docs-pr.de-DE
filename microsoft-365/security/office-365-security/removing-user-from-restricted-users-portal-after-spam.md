---
title: Entfernen von blockierten Benutzern aus dem Portal "Eingeschränkte Benutzer"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Hier erfahren Administratoren, wie sie Benutzer aus dem Portal für eingeschränkte Benutzer in Office 365 entfernen können. Benutzer werden aufgrund des Versands von ausgehenden Spamnachrichten zum Portal für eingeschränkte Benutzer hinzugefügt, in der Regel als Folge einer Kontokompromittierung.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9865b409be6bce14b84a9175e8f17cdad58befe
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351007"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="50a2d-104">Entfernen von blockierten Benutzern aus dem Portal "Eingeschränkte Benutzer" in Office 365</span><span class="sxs-lookup"><span data-stu-id="50a2d-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

<span data-ttu-id="50a2d-105">Wenn ein Benutzer einen der Grenzwerte für den ausgehendem Versand überschreitet, wie unter[Sendegrenzwerte](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) oder [Richtlinien für ausgehenden Spam](configure-the-outbound-spam-policy.md) angegeben, wird der Benutzer am Senden von E-Mails gehindert, kann aber weiterhin E-Mails empfangen.</span><span class="sxs-lookup"><span data-stu-id="50a2d-105">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="50a2d-106">Der Benutzer wird zum Portal für eingeschränkte Benutzer im Security & Compliance Center hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="50a2d-106">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="50a2d-107">Wenn der Benutzer versuch, eine E-Mail zu senden, wird die Nachricht in einem Unzustellbarkeitsbericht (auch als NDR- oder Unzustellbarkeitsnachricht bezeichnet) mit dem Fehlercode [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) und dem folgenden Text zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="50a2d-107">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="50a2d-108">„Ihre Nachricht konnte nicht übermittelt werden, weil Sie nicht als gültiger Absender erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="50a2d-108">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="50a2d-109">Der häufigste Grund dafür ist, dass der Verdacht besteht, dass von Ihrer E-Mail-Adresse Spam versandt wurde, und dass deshalb das Senden von E-Mails nicht mehr zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="50a2d-109">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="50a2d-110">Sollten Sie Unterstützung benötigen, wenden Sie sich an Ihren E-Mail-Administrator.</span><span class="sxs-lookup"><span data-stu-id="50a2d-110">Contact  your email admin for assistance.</span></span> <span data-ttu-id="50a2d-111">Der Remoteserver hat „550 5.1.8 Zugriff verweigert, ungültiger ausgehender Absender“ zurückgegeben.“</span><span class="sxs-lookup"><span data-stu-id="50a2d-111">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="50a2d-112">Im Security & Compliance Center oder in Exchange Online PowerShell können Administratoren Benutzer aus dem Portal mit eingeschränkte Absender entfernen.</span><span class="sxs-lookup"><span data-stu-id="50a2d-112">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="50a2d-113">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="50a2d-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="50a2d-114">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="50a2d-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="50a2d-115">Verwenden Sie <https://protection.office.com/restrictedusers>, um direkt zur Seite **Eingeschränkte Benutzer** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="50a2d-115">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="50a2d-116">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="50a2d-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="50a2d-117">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="50a2d-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="50a2d-118">Wenn Sie Benutzer aus dem Portal für eingeschränkte Benutzer entfernen möchten, müssen Sie Mitglied der Rollengruppen**Organisationsverwaltung** oder **Sicherheitsadministrator** sein.</span><span class="sxs-lookup"><span data-stu-id="50a2d-118">To remove users from the Restricted Users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="50a2d-119">Für den schreibgeschützten Zugriff auf das Portal für eingeschränkte Benutzer müssen Sie Mitglied der Rollengruppe **Sicherheitsleseberechtigter** sein.</span><span class="sxs-lookup"><span data-stu-id="50a2d-119">For read-only access to the Restricted Users portal, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="50a2d-120">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="50a2d-120">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="50a2d-121">Werden die Grenzwerte für ausgehende E-Mail-Nachrichten von einem Absender überschritten, ist dies ein Hinweis auf ein kompromittiertes Konto.</span><span class="sxs-lookup"><span data-stu-id="50a2d-121">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="50a2d-122">Bevor Sie den Benutzer aus dem Portal für eingeschränkte Benutzer entfernen, führen Sie die erforderlichen Schritte aus, um die Kontrolle über das Konto wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="50a2d-122">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="50a2d-123">Weitere Informationen finden Sie unter [Reagieren auf ein kompromittiertes E-Mail-Konto in Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="50a2d-123">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="50a2d-124">Verwenden des Security & Compliance Centers zum Entfernen eines Benutzers aus der Liste der eingeschränkten Benutzer</span><span class="sxs-lookup"><span data-stu-id="50a2d-124">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="50a2d-125">Wechseln Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Eingeschränkte Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="50a2d-125">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="50a2d-126">Wählen Sie den Benutzer aus, dessen Blockierung Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="50a2d-126">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="50a2d-127">Klicken Sie in der Spalte **Aktionen** auf **Blockierung aufheben**.</span><span class="sxs-lookup"><span data-stu-id="50a2d-127">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="50a2d-128">Details zu dem Konto, für das das Senden eingeschränkt wurde, werden in einem Popup-Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="50a2d-128">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="50a2d-129">Gehen Sie die Empfehlungen durch und stellen Sie sicher, dass Sie die richtigen Maßnahmen für den Fall ergreifen, dass das Konto tatsächlich kompromittiert ist.</span><span class="sxs-lookup"><span data-stu-id="50a2d-129">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="50a2d-130">Klicken Sie abschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="50a2d-130">Click **Next** when done.</span></span>

4. <span data-ttu-id="50a2d-131">Der nächste Bildschirm enthält Empfehlungen zur Verhinderung zukünftiger Kompromittierungen.</span><span class="sxs-lookup"><span data-stu-id="50a2d-131">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="50a2d-132">Das Aktivieren der mehrstufigen Authentifizierung (MFA) und das Ändern der Kennwörter sind eine gute Abwehr.</span><span class="sxs-lookup"><span data-stu-id="50a2d-132">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="50a2d-133">Klicken Sie abschließend auf **Benutzer entsperren**.</span><span class="sxs-lookup"><span data-stu-id="50a2d-133">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="50a2d-134">Klicken Sie zur Änderungsbestätigung auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="50a2d-134">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="50a2d-135">Es kann bis zu 30 Minuten oder länger dauern, bis Einschränkungen aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="50a2d-135">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="50a2d-136">Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer</span><span class="sxs-lookup"><span data-stu-id="50a2d-136">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="50a2d-137">Die standardmäßige Benachrichtigungsrichtlinie mit dem Namen **Benutzer, dessen E-Mail-Versand blockiert wurde** benachrichtigt Administratoren automatisch, wenn Benutzer blockiert werden, damit sie keine ausgehenden E-Mails mehr senden können.</span><span class="sxs-lookup"><span data-stu-id="50a2d-137">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="50a2d-138">Sie können diese Einstellungen überprüfen und weitere Benutzer hinzufügen, die benachrichtigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="50a2d-138">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="50a2d-139">Weitere Informationen über Benachrichtigungsrichtlinien finden Sie unter [Benachrichtigungsrichtlinien im Security & Compliance Center](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="50a2d-139">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50a2d-140">Damit Benachrichtigungen funktionieren, muss die Überwachungsprotokollsuche aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="50a2d-140">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="50a2d-141">Weitere Informationen finden Sie unter [Aktivieren und Deaktivieren der Überwachungsprotokollsuche](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="50a2d-141">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="50a2d-142">Wechseln Sie im Security & Compliance Center zu **Benachrichtigungen** \> **Benachrichtigungsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="50a2d-142">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="50a2d-143">Wählen Sie die Benachrichtigung **Benutzer, dessen E-Mail-Versand blockiert wurde**.</span><span class="sxs-lookup"><span data-stu-id="50a2d-143">Find an select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="50a2d-144">Überprüfen oder konfigurieren Sie im Flyout die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="50a2d-144">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="50a2d-145">**Status**: Überprüfen Sie, ob die Benachrichtigung aktiviert ist ![Aktiviert](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span><span class="sxs-lookup"><span data-stu-id="50a2d-145">**Status**: Verify the alert is turned on ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="50a2d-146">**E-Mail-Empfänger**: Klicken Sie auf **Bearbeiten**, und überprüfen oder konfigurieren Sie die folgenden Einstellungen im angezeigten Flyout **Empfänger bearbeiten**:</span><span class="sxs-lookup"><span data-stu-id="50a2d-146">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="50a2d-147">**Senden von E-Mail-Benachrichtigungen**: Vergewissern Sie sich, ob das Kontrollkästchen aktiviert ist (**Ein**).</span><span class="sxs-lookup"><span data-stu-id="50a2d-147">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="50a2d-148">**E-Mail-Empfänger**: Der Standardwert ist **TenantAdmins** (dies bedeutet Mitglieder von **Globaler Administrator**).</span><span class="sxs-lookup"><span data-stu-id="50a2d-148">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="50a2d-149">Wenn Sie weitere Empfänger hinzufügen möchten, klicken Sie auf einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="50a2d-149">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="50a2d-150">Eine Liste von Empfängern wird angezeigt, und Sie können mit der Eingabe eines Namens beginnen, um die Liste zu filtern und einen Empfänger auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="50a2d-150">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="50a2d-151">Sie können einen vorhandenen Empfänger aus dem Feld entfernen, indem Sie auf das Symbol ![Entfernen](../../media/scc-remove-icon.png) neben seinem Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="50a2d-151">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="50a2d-152">**Tägliche Benachrichtigungsgrenze**: Der Standardwert ist **Keine Grenze**, aber Sie können eine Grenze für die maximale Anzahl von Benachrichtigungen pro Tag festlegen.</span><span class="sxs-lookup"><span data-stu-id="50a2d-152">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="50a2d-153">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="50a2d-153">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="50a2d-154">Zurück im Flyout **Benutzer, dessen E-Mail-Versand blockiert wurde** klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="50a2d-154">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="50a2d-155">Verwenden Sie die Exchange Online-PowerShell, um die Liste der eingeschränkten Benutzer anzuzeigen und Benutzer daraus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="50a2d-155">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="50a2d-156">Um diese Liste der Benutzer anzuzeigen, deren E-Mail-Versand beschränkt ist, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="50a2d-156">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="50a2d-157">Um Details zu einem bestimmten Benutzer anzuzeigen, ersetzen Sie \<emailaddress\> durch die E-Mail-Adresse des Benutzers, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="50a2d-157">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="50a2d-158">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="50a2d-158">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="50a2d-159">Um einen Benutzer aus der Liste der eingeschränkten Benutzer zu entfernen, ersetzen Sie \<emailaddress\> durch seine E-Mail-Adresse, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="50a2d-159">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="50a2d-160">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-BlockedSenderAddres](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="50a2d-160">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
