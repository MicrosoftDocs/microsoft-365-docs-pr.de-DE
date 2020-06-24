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
ms.openlocfilehash: 43312ee6eff9b56ac4faf8173666a1ba79b9e067
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726730"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="96f6a-104">Entfernen von blockierten Benutzern aus dem Portal "Eingeschränkte Benutzer" in Office 365</span><span class="sxs-lookup"><span data-stu-id="96f6a-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

<span data-ttu-id="96f6a-105">Wenn ein Benutzer einen der Grenzwerte für den ausgehendem Versand überschreitet, wie unter[Sendegrenzwerte](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) oder [Richtlinien für ausgehenden Spam](configure-the-outbound-spam-policy.md) angegeben, wird der Benutzer am Senden von E-Mails gehindert, kann aber weiterhin E-Mails empfangen.</span><span class="sxs-lookup"><span data-stu-id="96f6a-105">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="96f6a-106">Der Benutzer wird zum Portal für eingeschränkte Benutzer im Security & Compliance Center hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="96f6a-106">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="96f6a-107">Wenn der Benutzer versuch, eine E-Mail zu senden, wird die Nachricht in einem Unzustellbarkeitsbericht (auch als NDR- oder Unzustellbarkeitsnachricht bezeichnet) mit dem Fehlercode [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) und dem folgenden Text zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="96f6a-107">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="96f6a-108">„Ihre Nachricht konnte nicht übermittelt werden, weil Sie nicht als gültiger Absender erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="96f6a-108">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="96f6a-109">Der häufigste Grund dafür ist, dass der Verdacht besteht, dass von Ihrer E-Mail-Adresse Spam versandt wurde, und dass deshalb das Senden von E-Mails nicht mehr zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="96f6a-109">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="96f6a-110">Sollten Sie Unterstützung benötigen, wenden Sie sich an Ihren E-Mail-Administrator.</span><span class="sxs-lookup"><span data-stu-id="96f6a-110">Contact  your email admin for assistance.</span></span> <span data-ttu-id="96f6a-111">Der Remoteserver hat „550 5.1.8 Zugriff verweigert, ungültiger ausgehender Absender“ zurückgegeben.“</span><span class="sxs-lookup"><span data-stu-id="96f6a-111">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="96f6a-112">Im Security & Compliance Center oder in Exchange Online PowerShell können Administratoren Benutzer aus dem Portal mit eingeschränkte Absender entfernen.</span><span class="sxs-lookup"><span data-stu-id="96f6a-112">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="96f6a-113">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="96f6a-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="96f6a-114">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="96f6a-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="96f6a-115">Verwenden Sie <https://protection.office.com/restrictedusers>, um direkt zur Seite **Eingeschränkte Benutzer** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="96f6a-115">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="96f6a-116">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="96f6a-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="96f6a-117">Bevor Sie die in diesem Artikel besprochenen Verfahren ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="96f6a-117">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="96f6a-118">Wenn Sie Benutzer aus dem Portal mit eingeschränkten Benutzern entfernen möchten, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="96f6a-118">To remove users from the Restricted Users portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="96f6a-119">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="96f6a-119">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="96f6a-120">**Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="96f6a-120">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="96f6a-121">Für den schreibgeschützten Zugriff auf das eingeschränkte Benutzerportal müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="96f6a-121">For read-only access to the Restricted Users portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="96f6a-122">**Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="96f6a-122">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="96f6a-123">**Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="96f6a-123">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="96f6a-124">Werden die Grenzwerte für ausgehende E-Mail-Nachrichten von einem Absender überschritten, ist dies ein Hinweis auf ein kompromittiertes Konto.</span><span class="sxs-lookup"><span data-stu-id="96f6a-124">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="96f6a-125">Bevor Sie den Benutzer aus dem Portal für eingeschränkte Benutzer entfernen, führen Sie die erforderlichen Schritte aus, um die Kontrolle über das Konto wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="96f6a-125">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="96f6a-126">Weitere Informationen finden Sie unter [Reagieren auf ein kompromittiertes E-Mail-Konto in Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="96f6a-126">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="96f6a-127">Verwenden des Security & Compliance Centers zum Entfernen eines Benutzers aus der Liste der eingeschränkten Benutzer</span><span class="sxs-lookup"><span data-stu-id="96f6a-127">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="96f6a-128">Wechseln Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Eingeschränkte Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="96f6a-128">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="96f6a-129">Wählen Sie den Benutzer aus, dessen Blockierung Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="96f6a-129">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="96f6a-130">Klicken Sie in der Spalte **Aktionen** auf **Blockierung aufheben**.</span><span class="sxs-lookup"><span data-stu-id="96f6a-130">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="96f6a-131">Details zu dem Konto, für das das Senden eingeschränkt wurde, werden in einem Popup-Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="96f6a-131">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="96f6a-132">Gehen Sie die Empfehlungen durch und stellen Sie sicher, dass Sie die richtigen Maßnahmen für den Fall ergreifen, dass das Konto tatsächlich kompromittiert ist.</span><span class="sxs-lookup"><span data-stu-id="96f6a-132">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="96f6a-133">Klicken Sie abschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="96f6a-133">Click **Next** when done.</span></span>

4. <span data-ttu-id="96f6a-134">Der nächste Bildschirm enthält Empfehlungen zur Verhinderung zukünftiger Kompromittierungen.</span><span class="sxs-lookup"><span data-stu-id="96f6a-134">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="96f6a-135">Das Aktivieren der mehrstufigen Authentifizierung (MFA) und das Ändern der Kennwörter sind eine gute Abwehr.</span><span class="sxs-lookup"><span data-stu-id="96f6a-135">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="96f6a-136">Klicken Sie abschließend auf **Benutzer entsperren**.</span><span class="sxs-lookup"><span data-stu-id="96f6a-136">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="96f6a-137">Klicken Sie zur Änderungsbestätigung auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="96f6a-137">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="96f6a-138">Es kann bis zu 30 Minuten oder länger dauern, bis Einschränkungen aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="96f6a-138">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="96f6a-139">Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer</span><span class="sxs-lookup"><span data-stu-id="96f6a-139">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="96f6a-140">Die standardmäßige Benachrichtigungsrichtlinie mit dem Namen **Benutzer, dessen E-Mail-Versand blockiert wurde** benachrichtigt Administratoren automatisch, wenn Benutzer blockiert werden, damit sie keine ausgehenden E-Mails mehr senden können.</span><span class="sxs-lookup"><span data-stu-id="96f6a-140">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="96f6a-141">Sie können diese Einstellungen überprüfen und weitere Benutzer hinzufügen, die benachrichtigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="96f6a-141">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="96f6a-142">Weitere Informationen über Benachrichtigungsrichtlinien finden Sie unter [Benachrichtigungsrichtlinien im Security & Compliance Center](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="96f6a-142">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96f6a-143">Damit Benachrichtigungen funktionieren, muss die Überwachungsprotokollsuche aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="96f6a-143">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="96f6a-144">Weitere Informationen finden Sie unter [Aktivieren und Deaktivieren der Überwachungsprotokollsuche](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="96f6a-144">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="96f6a-145">Wechseln Sie im Security & Compliance Center zu **Benachrichtigungen** \> **Benachrichtigungsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="96f6a-145">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="96f6a-146">Wählen Sie die Benachrichtigung **Benutzer, dessen E-Mail-Versand blockiert wurde**.</span><span class="sxs-lookup"><span data-stu-id="96f6a-146">Find an select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="96f6a-147">Überprüfen oder konfigurieren Sie im Flyout die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="96f6a-147">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="96f6a-148">**Status**: Überprüfen Sie, ob die Benachrichtigung aktiviert ist ![Aktiviert](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span><span class="sxs-lookup"><span data-stu-id="96f6a-148">**Status**: Verify the alert is turned on ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="96f6a-149">**E-Mail-Empfänger**: Klicken Sie auf **Bearbeiten**, und überprüfen oder konfigurieren Sie die folgenden Einstellungen im angezeigten Flyout **Empfänger bearbeiten**:</span><span class="sxs-lookup"><span data-stu-id="96f6a-149">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="96f6a-150">**Senden von E-Mail-Benachrichtigungen**: Vergewissern Sie sich, ob das Kontrollkästchen aktiviert ist (**Ein**).</span><span class="sxs-lookup"><span data-stu-id="96f6a-150">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="96f6a-151">**E-Mail-Empfänger**: Der Standardwert ist **TenantAdmins** (dies bedeutet Mitglieder von **Globaler Administrator**).</span><span class="sxs-lookup"><span data-stu-id="96f6a-151">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="96f6a-152">Wenn Sie weitere Empfänger hinzufügen möchten, klicken Sie auf einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="96f6a-152">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="96f6a-153">Eine Liste von Empfängern wird angezeigt, und Sie können mit der Eingabe eines Namens beginnen, um die Liste zu filtern und einen Empfänger auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="96f6a-153">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="96f6a-154">Sie können einen vorhandenen Empfänger aus dem Feld entfernen, indem Sie auf das Symbol ![Entfernen](../../media/scc-remove-icon.png) neben seinem Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="96f6a-154">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="96f6a-155">**Tägliche Benachrichtigungsgrenze**: Der Standardwert ist **Keine Grenze**, aber Sie können eine Grenze für die maximale Anzahl von Benachrichtigungen pro Tag festlegen.</span><span class="sxs-lookup"><span data-stu-id="96f6a-155">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="96f6a-156">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="96f6a-156">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="96f6a-157">Zurück im Flyout **Benutzer, dessen E-Mail-Versand blockiert wurde** klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="96f6a-157">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="96f6a-158">Verwenden Sie die Exchange Online-PowerShell, um die Liste der eingeschränkten Benutzer anzuzeigen und Benutzer daraus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="96f6a-158">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="96f6a-159">Um diese Liste der Benutzer anzuzeigen, deren E-Mail-Versand beschränkt ist, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="96f6a-159">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="96f6a-160">Um Details zu einem bestimmten Benutzer anzuzeigen, ersetzen Sie \<emailaddress\> durch die E-Mail-Adresse des Benutzers, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="96f6a-160">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="96f6a-161">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="96f6a-161">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="96f6a-162">Um einen Benutzer aus der Liste der eingeschränkten Benutzer zu entfernen, ersetzen Sie \<emailaddress\> durch seine E-Mail-Adresse, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="96f6a-162">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="96f6a-163">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-BlockedSenderAddres](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="96f6a-163">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
