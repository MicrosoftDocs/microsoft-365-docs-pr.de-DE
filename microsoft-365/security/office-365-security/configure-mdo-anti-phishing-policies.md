---
title: Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren erfahren, wie Sie die erweiterten Antiphishingrichtlinien erstellen, ändern und löschen, die in Organisationen mit Microsoft Defender for Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3660b9574f4faf4ee9c0602ac23b36f8634650dc
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537907"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f0d0e-103">Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f0d0e-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f0d0e-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-104">**Applies to**</span></span>
- [<span data-ttu-id="f0d0e-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="f0d0e-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f0d0e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0d0e-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f0d0e-107">Antiphishingrichtlinien in [Microsoft Defender for Office 365](defender-for-office-365.md) können Ihre Organisation vor phishingbasierten Phishingangriffen und anderen Arten von Phishingangriffen schützen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="f0d0e-108">Weitere Informationen zu den Unterschieden zwischen Antiphishingrichtlinien in Exchange Online Protection (EOP) und Antiphishingrichtlinien in Microsoft Defender for Office 365 finden Sie unter [Antiphishingschutz](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="f0d0e-109">Administratoren können die standardmäßige Antiphishingrichtlinie anzeigen, bearbeiten und konfigurieren (aber nicht löschen).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="f0d0e-110">Für eine höhere Granularität können Sie auch benutzerdefinierte Antiphishingrichtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="f0d0e-111">Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="f0d0e-112">Sie können Antiphishingrichtlinien im Security & Compliance Center oder in Exchange Online PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="f0d0e-113">Informationen zum Konfigurieren der eingeschränkteren In-Phishing-Richtlinien, die in Exchange Online Protection-Organisationen (d. h. Organisationen ohne Microsoft Defender für Office 365) verfügbar sind, finden Sie unter [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="f0d0e-114">Die grundlegenden Elemente einer Antiphishingrichtlinie sind:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="f0d0e-115">**Die Antiphishrichtlinie**: Gibt die zu aktivierenden oder deaktivierenden Phishingschutzmaßnahmen sowie die Aktionen zum Anwenden von Optionen an.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="f0d0e-116">**Die Antiphishregel**: Gibt die Priorität und empfängerfilter (auf wen die Richtlinie angewendet wird) für eine Antiphishrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="f0d0e-117">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Antiphishingrichtlinien im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="f0d0e-118">Wenn Sie eine Richtlinie erstellen, erstellen Sie tatsächlich eine Antiphishregel und die zugeordnete Antiphishrichtlinie gleichzeitig mit demselben Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="f0d0e-119">Wenn Sie eine Richtlinie ändern, ändern Einstellungen im Zusammenhang mit name, priority, enabled oder disabled und Empfängerfiltern die Antiphishregel.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="f0d0e-120">Alle anderen Einstellungen ändern die zugeordnete Antiphishrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="f0d0e-121">Wenn Sie eine Richtlinie entfernen, werden die Antiphishregel und die zugehörige Antiphishrichtlinie entfernt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="f0d0e-122">In Exchange Online PowerShell verwalten Sie die Richtlinie und die Regel separat.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="f0d0e-123">Weitere Informationen finden Sie im Abschnitt Use [Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="f0d0e-124">Jede Microsoft Defender for Office 365-Organisation verfügt über eine integrierte Antiphishingrichtlinie namens Office365 AntiPhish Default mit folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="f0d0e-125">Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, auch wenn der Richtlinie keine Antiphishregel (Empfängerfilter) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="f0d0e-126">Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="f0d0e-127">Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="f0d0e-128">Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="f0d0e-129">Um die Effektivität des Antiphishingschutzes in Microsoft Defender for Office 365 zu erhöhen, können Sie benutzerdefinierte Antiphishingrichtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f0d0e-130">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="f0d0e-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f0d0e-131">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f0d0e-132">Um direkt zur Seite **"Antiphishing" zu** wechseln, verwenden Sie <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="f0d0e-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="f0d0e-133">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f0d0e-134">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen in **Exchange Online** Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f0d0e-135">Zum Hinzufügen, Ändern und Löschen von Antiphishingrichtlinien müssen  Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f0d0e-136">Für den schreibgeschützten Zugriff auf Antiphishingrichtlinien müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** <sup>\*</sup> sein.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="f0d0e-137">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="f0d0e-138">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-138">**Notes**:</span></span>

  - <span data-ttu-id="f0d0e-139">Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f0d0e-140">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="f0d0e-141">Die **Rollengruppe "Nur-Ansichtsorganisationsverwaltung"** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) bietet auch schreibgeschützten Zugriff auf das <sup>\*</sup> Feature.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="f0d0e-142"><sup>\*</sup> Im Security & Compliance Center können Benutzer mit schreibgeschützten Zugriff die Einstellungen benutzerdefinierter Antiphishingrichtlinien anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="f0d0e-143">Schreibgeschützte Benutzer können die Einstellungen in der Standardmäßigen Antiphishingrichtlinie nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="f0d0e-144">Unsere empfohlenen Einstellungen für Antiphishingrichtlinien in Microsoft Defender for Office 365 finden Sie unter [Antiphishingrichtlinie in Defender für Office 365 Einstellungen](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="f0d0e-145">Es ist bis zu 30 Minuten zulässig, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="f0d0e-146">Informationen dazu, wo Antiphishingrichtlinien in der Filterpipeline angewendet werden, finden Sie unter [Reihenfolge und Rangfolge des E-Mail-Schutzes](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f0d0e-147">Verwenden Sie das Security & Compliance Center, um Antiphishingrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f0d0e-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="f0d0e-148">Beim Erstellen einer benutzerdefinierten Antiphishingrichtlinie im Security & Compliance Center werden die Antiphishregel und die zugehörige Antiphishingrichtlinie gleichzeitig mit demselben Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="f0d0e-149">Wenn Sie eine Antiphishingrichtlinie erstellen, können Sie nur den Richtliniennamen, die Beschreibung und den Empfängerfilter angeben, der identifiziert, auf wen die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="f0d0e-150">Nachdem Sie die Richtlinie erstellt haben, können Sie die Richtlinie ändern, um die Standardmäßigen Antiphishingeinstellungen zu ändern oder zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="f0d0e-151">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f0d0e-152">Klicken Sie **auf der Seite Antiphishing** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="f0d0e-153">Der **Assistent zum Erstellen einer neuen Antiphishingrichtlinie** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="f0d0e-154">Konfigurieren Sie **auf der Seite** Ihre Richtlinie benennen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="f0d0e-155">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="f0d0e-156">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="f0d0e-157">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f0d0e-158">Identifizieren Sie **auf der angezeigten** Seite Angewendet auf die internen Empfänger, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="f0d0e-159">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="f0d0e-160">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="f0d0e-161">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="f0d0e-162">Klicken **Sie auf Bedingung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-162">Click **Add a condition**.</span></span> <span data-ttu-id="f0d0e-163">Wählen Sie in der angezeigten Dropdownliste unter Angewendet eine **Bedingung aus, wenn**:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="f0d0e-164">**Der Empfänger ist**: Gibt ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="f0d0e-165">**Der Empfänger ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="f0d0e-166">**Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in der Organisation an.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="f0d0e-167">Nachdem Sie die Bedingung ausgewählt haben, wird ein entsprechendes Dropdownfeld mit einem **Beliebigen dieser Kontrollkästchen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="f0d0e-168">Klicken Sie in das Feld, und scrollen Sie durch die Liste der auszuwählende Werte.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="f0d0e-169">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="f0d0e-170">Klicken Sie auf einen leeren Bereich im Feld, um weitere Werte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="f0d0e-171">Klicken Sie zum Entfernen einzelner Einträge **auf Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für den Wert.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="f0d0e-172">Klicken Sie zum Entfernen der gesamten Bedingung auf **Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für die Bedingung.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="f0d0e-173">Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen,** und wählen Sie einen verbleibenden Wert unter **Angewendet wenn aus.**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="f0d0e-174">Klicken Sie zum Hinzufügen von Ausnahmen auf **Bedingung hinzufügen,** und wählen Sie unter **Except if eine Ausnahme aus.**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="f0d0e-175">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="f0d0e-176">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f0d0e-177">Überprüfen Sie **auf der angezeigten** Seite Einstellungen überprüfen Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="f0d0e-178">Sie können **für** jede Einstellung auf Bearbeiten klicken, um sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="f0d0e-179">Klicken Sie nach Abschluss des Abschlusses auf **Diese Richtlinie erstellen.**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="f0d0e-180">Klicken Sie im angezeigten Bestätigungsdialogfeld auf **OK.**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="f0d0e-181">Nachdem Sie die Antiphishingrichtlinie mit diesen allgemeinen Einstellungen erstellt haben, verwenden Sie die Anweisungen im nächsten Abschnitt, um die Schutzeinstellungen in der Richtlinie zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f0d0e-182">Verwenden Sie das Security & Compliance Center, um Antiphishingrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f0d0e-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="f0d0e-183">Verwenden Sie die folgenden Verfahren, um Antiphishingrichtlinien zu ändern: eine neue Richtlinie, die Sie erstellt haben, oder vorhandene Richtlinien, die Sie bereits angepasst haben.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="f0d0e-184">Wenn Sie noch nicht vorhanden sind, öffnen Sie das Security & Compliance Center, und wechseln Sie **zu** Richtlinie zur \>  \> **Bedrohungsverwaltung Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f0d0e-185">Wählen Sie die benutzerdefinierte Antiphishingrichtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="f0d0e-186">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="f0d0e-187">Das **Flyout \<name\> "Richtlinie bearbeiten"** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="f0d0e-188">Durch Klicken **auf Bearbeiten** in einem beliebigen Abschnitt erhalten Sie Zugriff auf die Einstellungen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="f0d0e-189">Die folgenden Schritte werden in der Reihenfolge dargestellt, in der die Abschnitte angezeigt werden, sie sind jedoch nicht sequenziell (Sie können die Abschnitte in beliebiger Reihenfolge auswählen und ändern).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="f0d0e-190">Nachdem Sie **in** einem Abschnitt auf Bearbeiten geklickt haben, werden die verfügbaren Einstellungen in einem  Assistentenformat angezeigt, Sie  können jedoch in beliebiger Reihenfolge innerhalb der Seiten springen, und Sie können auf einer beliebigen Seite auf Speichern klicken (oder  ![ ](../../media/scc-remove-icon.png) **\<name\>** Abbrechen oder Schließen schließen, um zur Seite Richtlinie bearbeiten zurückzukehren (Sie müssen nicht die letzte Seite des Assistenten zum Speichern oder Verlassen des Assistenten besuchen).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="f0d0e-191">**Richtlinieneinstellung**: Klicken Sie auf **Bearbeiten,** um dieselben Einstellungen zu ändern, die beim Erstellen der Richtlinie [im](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) vorherigen Abschnitt verfügbar waren:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="f0d0e-192">**Name**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-192">**Name**</span></span>
   - <span data-ttu-id="f0d0e-193">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-193">**Description**</span></span>
   - <span data-ttu-id="f0d0e-194">**Angewendet auf**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-194">**Applied to**</span></span>
   - <span data-ttu-id="f0d0e-195">**Überprüfen Der Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-195">**Review your settings**</span></span>

   <span data-ttu-id="f0d0e-196">Wenn Sie fertig sind, klicken Sie auf **einer beliebigen** Seite auf Speichern.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="f0d0e-197">**Identitätswechsel**: Klicken Sie auf **Bearbeiten,** um die geschützten Absender und geschützten Absenderdomänen in der Richtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-197">**Impersonation**: Click **Edit** to modify the protected senders and protected sender domains in the policy.</span></span> <span data-ttu-id="f0d0e-198">Diese Einstellungen sind eine Bedingung für die Richtlinie, die bestimmte Absender identifiziert, die in der Absenderadresse eingehender Nachrichten (einzeln oder nach Domäne) suchen müssen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-198">These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="f0d0e-199">Weitere Informationen finden Sie unter [Identitätswechseleinstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="f0d0e-200">**Benutzer zum Schützen hinzufügen:** Der Standardwert ist **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="f0d0e-200">**Add users to protect**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="f0d0e-201">Um es zu aktivieren, verschieben Sie die Umschaltfläche auf **Ein** ![ Umschaltfläche ein, und klicken Sie dann auf die angezeigte Schaltfläche Benutzer ](../../media/scc-toggle-on.png)  hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-201">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png), and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="f0d0e-202">Konfigurieren Sie **im angezeigten** Flyout Benutzer hinzufügen die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="f0d0e-203">**E-Mail-Adresse**:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-203">**Email address**:</span></span>

       - <span data-ttu-id="f0d0e-204">Klicken Sie in das Feld, und scrollen Sie durch die Liste der auszuwählende Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="f0d0e-205">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="f0d0e-206">Klicken Sie zum Entfernen eines Eintrags **auf Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="f0d0e-207">**Name**: Dieser Wert wird basierend auf der ausgewählten E-Mail-Adresse aufgefüllt, Sie können ihn jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="f0d0e-208">Wenn Sie fertig sind, klicken Sie auf **einer beliebigen** Seite auf Speichern.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="f0d0e-209">Wählen Sie zum Bearbeiten eines vorhandenen Eintrags den geschützten Benutzer in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="f0d0e-210">In jeder Antiphishingrichtlinie können Sie maximal 60 geschützte Benutzer (Absender-E-Mail-Adressen) angeben.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="f0d0e-211">Sie können denselben geschützten Benutzer nicht in mehreren Richtlinien angeben.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="f0d0e-212">Benutzerwechselschutz funktioniert nicht, wenn Absender und Empfänger zuvor per E-Mail kommuniziert haben.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="f0d0e-213">Wenn Absender und Empfänger nie per E-Mail kommuniziert haben, wird die Nachricht als Identitätswechselversuch identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="f0d0e-214">**Zu schützende Domänen hinzufügen:** Konfigurieren Sie eine oder beide der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="f0d0e-215">**Schließen Sie automatisch die Domänen ein, die** ich selbst habe: Der Standardwert ist **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="f0d0e-215">**Automatically include the domains I own**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="f0d0e-216">Um es zu aktivieren, verschieben Sie den Umschalter auf **On** ![ Toggle On ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="f0d0e-216">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png).</span></span>

       <span data-ttu-id="f0d0e-217">Wenn Sie die Domänen anzeigen möchten, die Sie besitzen, wählen **Sie Domänen anzeigen aus, die ich besitzt.**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-217">To view the domains that you own, select **View domains I own**.</span></span>

     - <span data-ttu-id="f0d0e-218">**Benutzerdefinierte Domänen hinzufügen:** Der Standardwert ist **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="f0d0e-218">**Include custom domains**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="f0d0e-219">Um es zu aktivieren, setzen  Sie den Umschalter auf Ein Umschalten ein, und geben Sie im Feld Domänen hinzufügen den Domänennamen ein (z. B. contoso.com), drücken Sie die EINGABETASTE, und wiederholen Sie dies bei ![ ](../../media/scc-toggle-on.png) Bedarf. </span><span class="sxs-lookup"><span data-stu-id="f0d0e-219">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png), and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="f0d0e-220">In allen Antiphishingrichtlinien können maximal 50 Domänen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-220">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="f0d0e-221">**Aktionen**: Klicken Sie auf **Bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-221">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="f0d0e-222">**Wenn E-Mails** von einem imitierten Benutzer gesendet werden: Konfigurieren Sie eine der folgenden Aktionen für Nachrichten, bei denen der Absender einer der geschützten Benutzer ist, die Sie unter Benutzer zum Schützen hinzufügen **angegeben haben:**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-222">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="f0d0e-223">**Keine Aktion anwenden**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-223">**Don't apply any action**</span></span>
       - <span data-ttu-id="f0d0e-224">**Umleiten von Nachrichten an andere E-Mail-Adressen**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-224">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="f0d0e-225">**Verschieben von Nachrichten in die Junk-E-Mail-Ordner der Empfänger**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-225">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="f0d0e-226">**Isolieren der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-226">**Quarantine the message**</span></span>
       - <span data-ttu-id="f0d0e-227">**Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-227">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="f0d0e-228">**Löschen der Nachricht, bevor sie zugestellt wird**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-228">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="f0d0e-229">**Wenn E-Mails** von einer identitätswechselten Domäne gesendet werden: Konfigurieren Sie eine der folgenden Aktionen für Nachrichten, bei denen sich die Domäne des Absenders in einer der geschützten Domänen befindet, die Sie unter Hinzufügen von Domänen zum Schützen angegeben **haben:**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-229">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the sender's domain is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="f0d0e-230">**Keine Aktion anwenden**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-230">**Don't apply any action**</span></span>
       - <span data-ttu-id="f0d0e-231">**Umleiten von Nachrichten an andere E-Mail-Adressen**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-231">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="f0d0e-232">**Verschieben von Nachrichten in die Junk-E-Mail-Ordner der Empfänger**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-232">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="f0d0e-233">**Isolieren der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-233">**Quarantine the message**</span></span>
       - <span data-ttu-id="f0d0e-234">**Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-234">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="f0d0e-235">**Löschen der Nachricht, bevor sie zugestellt wird**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-235">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="f0d0e-236">Klicken **Sie auf Identitätswechselsicherheitstipps aktivieren,** und konfigurieren Sie eine der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-236">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="f0d0e-237">**Tipps für imitierte Benutzer anzeigen**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-237">**Show tip for impersonated users**</span></span>
     - <span data-ttu-id="f0d0e-238">**Tipps für identitätswechselte Domänen anzeigen**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-238">**Show tip for impersonated domains**</span></span>
     - <span data-ttu-id="f0d0e-239">**Tipps für ungewöhnliche Zeichen anzeigen**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-239">**Show tip for unusual characters**</span></span>

     <span data-ttu-id="f0d0e-240">Der Standardwert für alle Tipps ist **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="f0d0e-240">The default value for all tips is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="f0d0e-241">Um diese zu aktivieren, verschieben Sie den Umschalter auf **On** [Toggle On](../../media/scc-toggle-on.png).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-241">To turn any of them on, slide the toggle to **On** [Toggle On](../../media/scc-toggle-on.png).</span></span>

     <span data-ttu-id="f0d0e-242">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="f0d0e-243">**Postfachintelligenz**:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="f0d0e-244">**Postfachintelligenz aktivieren?**: Der Standardwert ist **On** [Toggle On](../../media/scc-toggle-on.png).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-244">**Enable mailbox intelligence?**: The default value is **On** [Toggle On](../../media/scc-toggle-on.png).</span></span> <span data-ttu-id="f0d0e-245">Um es zu deaktivieren, verschieben Sie den Umschalter auf **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="f0d0e-245">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

     - <span data-ttu-id="f0d0e-246">**Aktivieren Despersonationschutzes für Postfachintelligenz?**: Diese Einstellung ist nur verfügbar, wenn **Postfachintelligenz aktivieren?** ist **On**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-246">**Enable mailbox intelligence based impersonation protection?**: This setting is available only if **Enable mailbox intelligence?** is **On**.</span></span> <span data-ttu-id="f0d0e-247">Aktivieren Sie diese Einstellung, um die Aktion für Nachrichten für Identitätswechselerkennungen aus Ergebnissen der Postfachintelligenz anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-247">Turn on this setting to specify the action to take on messages for impersonation detections from mailbox intelligence results.</span></span>

       <span data-ttu-id="f0d0e-248">In **Wenn E-Mails von** einem imitierten Benutzer gesendet werden, können Sie eine der folgenden Aktionen angeben (die gleichen Aktionen, die für geschützte Benutzer und geschützte Domänen verfügbar sind):</span><span class="sxs-lookup"><span data-stu-id="f0d0e-248">In **If email is sent by an impersonated user**, you can specify one of the following actions (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="f0d0e-249">**Keine Aktion** anwenden: Beachten Sie, dass dieser Wert das gleiche Ergebnis hat wie das Aktivieren von Postfachintelligenz **aktivieren?** aber deaktivieren Aktivieren des Postfachintelligenz-basierten **Identitätswechselschutzes?**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-249">**Don't apply any action**: Note that this value has the same result as turning on **Enable mailbox intelligence?** but turning off **Enable mailbox intelligence based impersonation protection?**.</span></span>
       - <span data-ttu-id="f0d0e-250">**Umleiten von Nachrichten an andere E-Mail-Adressen**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-250">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="f0d0e-251">**Verschieben von Nachrichten in die Junk-E-Mail-Ordner der Empfänger**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-251">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="f0d0e-252">**Isolieren der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-252">**Quarantine the message**</span></span>
       - <span data-ttu-id="f0d0e-253">**Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-253">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="f0d0e-254">**Löschen der Nachricht, bevor sie zugestellt wird**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-254">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="f0d0e-255">**Hinzufügen vertrauenswürdiger Absender und Domänen:** Geben Sie Ausnahmen für die Richtlinie an:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-255">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="f0d0e-256">**Vertrauenswürdige Absender**:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-256">**Trusted senders**:</span></span>

       - <span data-ttu-id="f0d0e-257">Klicken Sie in das Feld, und scrollen Sie durch die Liste der auszuwählende Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-257">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="f0d0e-258">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-258">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="f0d0e-259">Klicken Sie zum Entfernen eines Eintrags **auf Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-259">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="f0d0e-260">**Vertrauenswürdige** Domänen: Geben Sie den Domänennamen ein (z. B. contoso.com), drücken Sie die EINGABETASTE, und wiederholen Sie sie bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-260">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="f0d0e-261">**Überprüfen Sie Ihre Einstellungen:** Anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-261">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="f0d0e-262">Sie können in jedem **Abschnitt** auf Bearbeiten klicken, um zur relevanten Seite zurück zu springen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-262">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="f0d0e-263">Sie können die folgenden  Einstellungen  direkt auf dieser Seite ein- oder ausschalten:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-263">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="f0d0e-264">**Geschützte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-264">**Protected users**</span></span>
       - <span data-ttu-id="f0d0e-265">**Geschützte Domänen** \> **Schließen Sie Domänen ein, die ich selbst habe**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-265">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="f0d0e-266">**Geschützte Domänen** \> **Geschützte Domänen** (benutzerdefinierte Domänen)</span><span class="sxs-lookup"><span data-stu-id="f0d0e-266">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="f0d0e-267">**Mailbox Intelligence**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-267">**Mailbox intelligence**</span></span>

   <span data-ttu-id="f0d0e-268">Wenn Sie fertig sind, klicken Sie auf **einer beliebigen** Seite auf Speichern.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-268">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="f0d0e-269">**Spoof**:  Klicken Sie auf Bearbeiten, um die Spoofintelligenz ein- oder auszuschalten, die Identifikation nicht authentifizierter Absender in Outlook ein- oder auszuschalten und die Aktion so zu konfigurieren, dass sie auf Nachrichten von blockierten spoofierten Absendern angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-269">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="f0d0e-270">Weitere Informationen zu diesen Einstellungen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-270">For more information about these settings, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="f0d0e-271">Beachten Sie, dass diese Einstellungen auch in Antiphishingrichtlinien in EOP verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-271">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="f0d0e-272">**Spoofing-Filtereinstellungen:** Verwenden Sie die Einstellung **Spoofintelligenz aktivieren?** zum Aktivieren oder Deaktivieren der Spoofintelligenz.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-272">**Spoofing filter settings**: Use the **Enable spoof intelligence?** setting to turn spoof intelligence on or off.</span></span> <span data-ttu-id="f0d0e-273">Der Standardwert ist **On**, und es wird empfohlen, ihn zu be lassen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-273">The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="f0d0e-274">Um es zu deaktivieren, verschieben Sie den Umschalter auf **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="f0d0e-274">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

     > [!NOTE]
     > <span data-ttu-id="f0d0e-275">Sie müssen den Schutz vor Spoofing nicht deaktivieren, wenn Ihr #A0 nicht auf Microsoft 365. Stattdessen aktivieren Sie erweiterte Filterung für Connectors.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-275">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="f0d0e-276">Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-276">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="f0d0e-277">**Einstellungen für nicht authentifizierte Absender:** Sie können die folgenden Einstellungen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-277">**Unauthenticated sender settings**: You can configure the following settings:</span></span>
     - <span data-ttu-id="f0d0e-278">Aktivieren Sie das Nicht authentifizierte Absender-Fragezeichen **(?)-Symbol?**: Fügen Sie dem Foto des Absenders im Feld Von in  Outlook ein Fragezeichen hinzu, wenn die Nachricht keine SPF- oder DKIM-Überprüfungen bestehen und die Nachricht keine DMARC- oder zusammengesetzte Authentifizierung über über- oder über die Nachricht [verfügt.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="f0d0e-278">**Enable unauthenticated sender question mark (?) symbol?**: Add a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span> <span data-ttu-id="f0d0e-279">Der Standardwert ist **Aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-279">The default value is **On**.</span></span> <span data-ttu-id="f0d0e-280">Um es zu deaktivieren, verschieben Sie den Umschalter auf **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="f0d0e-280">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>
     - <span data-ttu-id="f0d0e-281">**Aktivieren Sie "via"-Tag?**: Fügen Sie das via-Tag (chris@contoso.com über fabrikam.com) hinzu, wenn sich die E-Mail-Adresse im Feld Von von von der Domäne in der DKIM-Signatur oder der **MAIL FROM-Adresse** unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-281">**Enable "via" tag?**: Add the via tag (chris@contoso.com via fabrikam.com) if the email address in the From box is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="f0d0e-282">Der Standardwert ist **Aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-282">The default value is **On**.</span></span> <span data-ttu-id="f0d0e-283">Um es zu deaktivieren, verschieben Sie den Umschalter auf **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="f0d0e-283">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="f0d0e-284">**Aktionen**: Geben Sie die Aktion für Nachrichten von blockierten spoofierten Absendern an:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-284">**Actions**: Specify the action to take on messages from blocked spoofed senders:</span></span>

     <span data-ttu-id="f0d0e-285">**Wenn E-Mails von einer Person** gesendet werden, die Ihre Domäne nicht spoofen darf:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-285">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="f0d0e-286">**Verschieben von Nachrichten in die Junk-E-Mail-Ordner der Empfänger**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-286">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="f0d0e-287">**Isolieren der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-287">**Quarantine the message**</span></span>

   - <span data-ttu-id="f0d0e-288">**Überprüfen Sie Ihre Einstellungen:** Anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-288">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="f0d0e-289">Sie können in jedem **Abschnitt** auf Bearbeiten klicken, um zur relevanten Seite zurück zu springen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-289">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="f0d0e-290">Sie können die folgenden  Einstellungen  direkt auf dieser Seite ein- oder ausschalten:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-290">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="f0d0e-291">**Spooffiltereinstellungen**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-291">**Spoof filter settings**</span></span>
       - <span data-ttu-id="f0d0e-292">**Einstellungen für nicht authentifizierte Absender**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-292">**Unauthenticated sender settings**</span></span>
       - <span data-ttu-id="f0d0e-293">**Aktionen**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-293">**Actions**</span></span>

   <span data-ttu-id="f0d0e-294">Wenn Sie fertig sind, klicken Sie auf **einer beliebigen** Seite auf Speichern.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-294">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="f0d0e-295">**Erweiterte Einstellungen**: Klicken Sie **auf Bearbeiten,** um die erweiterten Phishingschwellenwerte zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-295">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="f0d0e-296">Weitere Informationen finden Sie unter [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-296">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="f0d0e-297">**Erweiterte Phishingschwellenwerte:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-297">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="f0d0e-298">**1 – Standard** (Dies ist der Standardwert.)</span><span class="sxs-lookup"><span data-stu-id="f0d0e-298">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="f0d0e-299">**2 – Aggressiv**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-299">**2 - Aggressive**</span></span>
   - <span data-ttu-id="f0d0e-300">**3 – Aggressiver**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-300">**3 - More aggressive**</span></span>
   - <span data-ttu-id="f0d0e-301">**4 – Am aggressivsten**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-301">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="f0d0e-302">**Überprüfen Sie Ihre Einstellungen:** Klicken Sie **auf Bearbeiten,** um zur Seite **Erweiterte Phishingschwellenwerte zurück** zu springen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-302">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="f0d0e-303">Wenn Sie fertig sind, klicken Sie auf beiden **Seiten** auf Speichern.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-303">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="f0d0e-304">Überprüfen Sie auf **der Seite \<Name\>** Richtlinie bearbeiten Ihre Einstellungen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-304">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f0d0e-305">Verwenden Sie das Security & Compliance Center, um die Standardmäßige Antiphishingrichtlinie in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f0d0e-305">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="f0d0e-306">Die standardmäßige Antiphishingrichtlinie in Microsoft Defender für Office 365 heißt Office365 AntiPhish Default und wird nicht in der Liste der Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-306">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="f0d0e-307">Gehen Sie wie folgt vor, um die Standardmäßige Antiphishingrichtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-307">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="f0d0e-308">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-308">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f0d0e-309">Klicken Sie **auf der Seite Antiphishing** auf **Standardrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-309">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="f0d0e-310">Die **Seite Office365 AntiPhish Default** bearbeiten wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-310">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="f0d0e-311">Die folgenden Abschnitte sind verfügbar, die identische Einstellungen für das Ändern [einer benutzerdefinierten Richtlinie enthalten:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="f0d0e-311">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="f0d0e-312">**Impersonation**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-312">**Impersonation**</span></span>
   - <span data-ttu-id="f0d0e-313">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-313">**Spoof**</span></span>
   - <span data-ttu-id="f0d0e-314">**Erweiterte Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-314">**Advanced settings**</span></span>

   <span data-ttu-id="f0d0e-315">Die folgenden Einstellungen sind nicht verfügbar, wenn Sie die Standardrichtlinie ändern:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-315">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="f0d0e-316">Sie können  den Abschnitt Richtlinieneinstellung und -werte  anzeigen, es gibt jedoch keinen Link Bearbeiten, sodass Sie die Einstellungen nicht ändern können (Richtlinienname, Beschreibung und für wen die Richtlinie gilt (gilt für alle Empfänger)).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-316">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="f0d0e-317">Die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-317">You can't delete the default policy.</span></span>
   - <span data-ttu-id="f0d0e-318">Sie können die Priorität der Standardrichtlinie nicht ändern (sie wird immer zuletzt angewendet).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-318">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="f0d0e-319">Überprüfen Sie **auf der Seite Office365-Standardrichtlinie** bearbeiten Ihre Einstellungen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-319">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f0d0e-320">Aktivieren oder Deaktivieren von benutzerdefinierten Antiphishingrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f0d0e-320">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="f0d0e-321">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-321">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f0d0e-322">Beachten Sie den Wert in der **Spalte Status:**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-322">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="f0d0e-323">Verschieben Sie den Umschalter **auf Off** ![ Toggle ](../../media/scc-toggle-off.png) Off, um die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-323">Slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png) to disable the policy.</span></span>

   - <span data-ttu-id="f0d0e-324">Verschieben Sie den Umschalter auf **Ein** ![ umschalten, ](../../media/scc-toggle-on.png) um die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-324">Slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png) to enable the policy.</span></span>

<span data-ttu-id="f0d0e-325">Sie können die standardmäßige Antiphishingrichtlinie nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-325">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f0d0e-326">Legen Sie die Priorität von benutzerdefinierten Antiphishingrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f0d0e-326">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="f0d0e-327">Standardmäßig erhalten Antiphishingrichtlinien eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-327">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="f0d0e-328">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-328">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="f0d0e-329">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-329">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="f0d0e-330">Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-330">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="f0d0e-331">Benutzerdefinierte Antiphishingrichtlinien werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-331">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="f0d0e-332">Die Standardmäßige Antiphishingrichtlinie mit dem Namen Office365 AntiPhish Default hat den benutzerdefinierten Prioritätswert **Lowest**, und Sie können sie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-332">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="f0d0e-333">**Hinweis:** Im Security & Compliance Center können Sie die Priorität der Antiphishingrichtlinie nur ändern, nachdem Sie sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-333">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="f0d0e-334">In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Antiphishregel erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-334">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="f0d0e-335">Um die Priorität einer Richtlinie  zu ändern, klicken Sie **in** den Eigenschaften der Richtlinie  auf Priorität erhöhen oder Priorität verringern (Sie können die Prioritätsnummer im Security & Compliance Center nicht direkt ändern).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-335">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="f0d0e-336">Das Ändern der Priorität einer Richtlinie ist nur sinnvoll, wenn Sie über mehrere Richtlinien verfügen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-336">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="f0d0e-337">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-337">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f0d0e-338">Wählen Sie die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-338">Select the policy that you want to modify.</span></span> <span data-ttu-id="f0d0e-339">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-339">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="f0d0e-340">Das **Flyout \<name\> "Richtlinie bearbeiten"** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-340">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="f0d0e-341">Die benutzerdefinierte Antiphishingrichtlinie mit dem **Prioritätswert** **0** verfügt nur über die **Schaltfläche Priorität** verringern.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-341">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="f0d0e-342">Die benutzerdefinierte Antiphishingrichtlinie mit dem niedrigsten **Prioritätswert** (z. B. **3**) verfügt nur über die **Schaltfläche Priorität erhöhen.**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-342">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="f0d0e-343">Wenn Sie über drei oder mehr benutzerdefinierte Antiphishingrichtlinien verfügen, stehen Richtlinien zwischen den höchsten und niedrigsten Prioritätswerten sowohl die Schaltflächen **Priorität** erhöhen als auch **Priorität** verringern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-343">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="f0d0e-344">Klicken **Sie auf Priorität erhöhen** oder Priorität **verringern,** um den **Prioritätswert zu** ändern.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-344">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="f0d0e-345">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-345">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f0d0e-346">Verwenden Sie das Security & Compliance Center, um Antiphishingrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f0d0e-346">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="f0d0e-347">Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-347">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f0d0e-348">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-348">Do one of the following steps:</span></span>

   - <span data-ttu-id="f0d0e-349">Wählen Sie eine benutzerdefinierte Antiphishingrichtlinie aus, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-349">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="f0d0e-350">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-350">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="f0d0e-351">Klicken **Sie auf Standardrichtlinie,** um die Standardmäßige Antiphishingrichtlinie anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-351">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="f0d0e-352">Das **Flyout \<name\> "Richtlinie** bearbeiten" wird angezeigt, in dem Sie die Einstellungen und Werte anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-352">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f0d0e-353">Verwenden Sie das Security & Compliance Center, um Antiphishingrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f0d0e-353">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="f0d0e-354">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f0d0e-355">Wählen Sie die Richtlinie aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-355">Select the policy that you want to remove.</span></span> <span data-ttu-id="f0d0e-356">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-356">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="f0d0e-357">Klicken Sie **im \<name\> angezeigten** Flyout Richtlinie bearbeiten auf Richtlinie **löschen,** und klicken Sie **dann** im angezeigten Warndialogfeld auf Ja.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-357">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="f0d0e-358">Die Standardrichtlinie kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-358">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f0d0e-359">Verwenden Exchange Online PowerShell zum Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f0d0e-359">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="f0d0e-360">Wie bereits beschrieben, besteht eine Antispamrichtlinie aus einer Antiphishrichtlinie und einer Antispamregel.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-360">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="f0d0e-361">In Exchange Online PowerShell ist der Unterschied zwischen Antiphishrichtlinien und Antiphishregeln offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-361">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="f0d0e-362">Sie verwalten Antiphishrichtlinien mithilfe der **\* -AntiPhishPolicy-Cmdlets,** und Sie verwalten Antiphishregeln mithilfe der **\* -AntiPhishRule-Cmdlets.**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-362">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="f0d0e-363">In PowerShell erstellen Sie zuerst die Antiphishrichtlinie, dann erstellen Sie die Antiphishregel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-363">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="f0d0e-364">In PowerShell ändern Sie die Einstellungen in der Antiphishrichtlinie und der Antiphishregel separat.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-364">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="f0d0e-365">Wenn Sie eine Antiphishrichtlinie aus PowerShell entfernen, wird die entsprechende Antiphishregel nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-365">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="f0d0e-366">Erstellen von Antiphishingrichtlinien mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0d0e-366">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="f0d0e-367">Das Erstellen einer Antiphishingrichtlinie in PowerShell besteht aus zwei Stufen:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-367">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="f0d0e-368">Erstellen Sie die Antiphishrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-368">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="f0d0e-369">Erstellen Sie die Antiphishregel, die die Antiphishrichtlinie angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-369">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="f0d0e-370">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-370">**Notes**:</span></span>

- <span data-ttu-id="f0d0e-371">Sie können eine neue Antiphishregel erstellen und ihr eine vorhandene, nicht zugeordnete Antiphishrichtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-371">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="f0d0e-372">Eine Antiphishregel kann nicht mehr als einer Antiphishrichtlinie zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-372">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="f0d0e-373">Sie können die folgenden Einstellungen für neue Antiphishrichtlinien in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-373">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="f0d0e-374">Erstellen Sie die neue Richtlinie als deaktiviert (_Aktiviert_ `$false` im Cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-374">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="f0d0e-375">Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) für das Cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-375">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="f0d0e-376">Eine neue Antiphishrichtlinie, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Antiphishregel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-376">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="f0d0e-377">Schritt 1: Erstellen einer Antiphishrichtlinie mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0d0e-377">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="f0d0e-378">Verwenden Sie die folgende Syntax, um eine Antiphishrichtlinie zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-378">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="f0d0e-379">In diesem Beispiel wird eine Phishingrichtlinie mit dem Namen "Research Quarantine" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-379">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="f0d0e-380">Die Richtlinie ist aktiviert (der Parameter _Enabled_ wird nicht verwendet, und der Standardwert ist `$true` ).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-380">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="f0d0e-381">Die Beschreibung ist: Research department policy.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-381">The description is: Research department policy.</span></span>
- <span data-ttu-id="f0d0e-382">Ermöglicht den Schutz von Organisationsdomänen für alle akzeptierten Domänen und den gezielten Domänenschutz für fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-382">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="f0d0e-383">Gibt Mai Fujito (mfujito@fabrikam.com) als Benutzer an, der vor Identitätswechseln geschützt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-383">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="f0d0e-384">Aktiviert die Postfachintelligenz.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-384">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="f0d0e-385">Aktiviert den Postfachintelligenzschutz und gibt die Quarantäneaktion an.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-385">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="f0d0e-386">Aktiviert Sicherheitstipps.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-386">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="f0d0e-387">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-387">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="f0d0e-388">Schritt 2: Erstellen einer Antiphishregel mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0d0e-388">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="f0d0e-389">Verwenden Sie die folgende Syntax, um eine Antiphishregel zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-389">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="f0d0e-390">In diesem Beispiel wird eine Antiphishregel namens "Research Department" mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-390">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="f0d0e-391">Die Regel ist der Antiphishrichtlinie "Research Quarantine" zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-391">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="f0d0e-392">Die Regel gilt für Mitglieder der Gruppe „Research Department“.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-392">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="f0d0e-393">Da wir den Parameter _Priority_ nicht verwenden, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-393">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="f0d0e-394">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-394">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="f0d0e-395">Anzeigen von Antiphishrichtlinien mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0d0e-395">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="f0d0e-396">Verwenden Sie die folgende Syntax, um vorhandene Antiphishrichtlinien anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-396">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f0d0e-397">In diesem Beispiel wird eine Zusammenfassungsliste aller Antiphishrichtlinien zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-397">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="f0d0e-398">In diesem Beispiel werden alle Eigenschaftswerte für die Antiphishrichtlinie "Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-398">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="f0d0e-399">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-399">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="f0d0e-400">Anzeigen von Antiphishregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0d0e-400">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="f0d0e-401">Verwenden Sie die folgende Syntax, um vorhandene Antiphishregeln anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-401">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f0d0e-402">In diesem Beispiel wird eine Zusammenfassungsliste aller Antiphishregeln zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-402">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="f0d0e-403">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-403">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="f0d0e-404">In diesem Beispiel werden alle Eigenschaftswerte für die Antiphishregel namens Contoso Executives zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-404">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="f0d0e-405">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-405">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="f0d0e-406">Verwenden von PowerShell zum Ändern von Antiphishrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f0d0e-406">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="f0d0e-407">Neben den folgenden Elementen sind dieselben Einstellungen verfügbar, wenn Sie eine Antiphishrichtlinie in PowerShell ändern, als wenn Sie die Richtlinie wie im Abschnitt Schritt 1: Verwenden von [PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) beschrieben erstellen, um einen Richtlinienabschnitt zum Phishingschutz weiter oben in diesem Artikel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-407">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="f0d0e-408">Die _MakeDefault-Option,_ die die angegebene Richtlinie in die  Standardrichtlinie umstellt (auf alle Benutzer angewendet, immer niedrigste Priorität, und Sie können sie nicht löschen) ist nur verfügbar, wenn Sie eine Antiphishrichtlinie in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-408">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="f0d0e-409">Sie können eine Antiphishrichtlinie nicht umbenennen (das **Cmdlet Set-AntiPhishPolicy** hat keinen _Name-Parameter)._</span><span class="sxs-lookup"><span data-stu-id="f0d0e-409">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="f0d0e-410">Wenn Sie eine Antiphishingrichtlinie im Security & Compliance Center umbenennen, benennen Sie nur die Antiphishingregel _um._</span><span class="sxs-lookup"><span data-stu-id="f0d0e-410">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="f0d0e-411">Verwenden Sie die folgende Syntax, um eine Antiphishrichtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-411">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="f0d0e-412">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-412">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="f0d0e-413">Verwenden von PowerShell zum Ändern von Antiphishregeln</span><span class="sxs-lookup"><span data-stu-id="f0d0e-413">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="f0d0e-414">Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine Antiphishregel in PowerShell ändern, ist der _Parameter Enabled,_ mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-414">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="f0d0e-415">Informationen zum Aktivieren oder Deaktivieren vorhandener Antiphishregeln finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-415">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="f0d0e-416">Andernfalls sind keine zusätzlichen Einstellungen verfügbar, wenn Sie eine Antiphishregel in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-416">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="f0d0e-417">Die gleichen Einstellungen sind verfügbar, wenn Sie eine Regel wie im Abschnitt Schritt 2: Verwenden von PowerShell beschrieben erstellen, um einen [Antiphishregelabschnitt](#step-2-use-powershell-to-create-an-anti-phish-rule) weiter oben in diesem Artikel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-417">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="f0d0e-418">Verwenden Sie die folgende Syntax, um eine Antiphishregel zu ändern:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-418">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="f0d0e-419">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-419">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="f0d0e-420">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Antiphishregeln</span><span class="sxs-lookup"><span data-stu-id="f0d0e-420">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="f0d0e-421">Durch Aktivieren oder Deaktivieren einer Antiphishregel in PowerShell wird die gesamte Antiphishingrichtlinie (die Antiphishregel und die zugewiesene Antiphishingrichtlinie) aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-421">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="f0d0e-422">Sie können die standardmäßige Antiphishingrichtlinie nicht aktivieren oder deaktivieren (sie wird immer auf alle Empfänger angewendet).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-422">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="f0d0e-423">Verwenden Sie die folgende Syntax, um eine #A0 in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-423">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="f0d0e-424">In diesem Beispiel wird die Antiphishregel "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-424">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="f0d0e-425">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-425">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="f0d0e-426">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) und [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-426">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="f0d0e-427">Festlegen der Priorität von Antiphishregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0d0e-427">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="f0d0e-428">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-428">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="f0d0e-429">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-429">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="f0d0e-430">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-430">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="f0d0e-431">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-431">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="f0d0e-432">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-432">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="f0d0e-433">Verwenden Sie die folgende Syntax, um die Priorität einer #A0 in PowerShell zu setzen:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-433">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="f0d0e-p148">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-p148">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="f0d0e-436">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-436">**Notes**:</span></span>

- <span data-ttu-id="f0d0e-437">Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den _Parameter Priority_ im Cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-437">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="f0d0e-438">Die Standardmäßige Antiphishrichtlinie verfügt nicht über eine entsprechende Antiphishregel und hat immer den nicht veränderbaren Prioritätswert **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-438">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="f0d0e-439">Entfernen von Antiphishrichtlinien mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0d0e-439">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="f0d0e-440">Wenn Sie PowerShell verwenden, um eine Antiphishrichtlinie zu entfernen, wird die entsprechende Antiphishregel nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-440">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="f0d0e-441">Verwenden Sie die folgende Syntax, um eine #A0 in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-441">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="f0d0e-442">In diesem Beispiel wird die Antiphishrichtlinie "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-442">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="f0d0e-443">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-443">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="f0d0e-444">Entfernen von Antiphishregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0d0e-444">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="f0d0e-445">Wenn Sie PowerShell verwenden, um eine Antiphishregel zu entfernen, wird die entsprechende Antiphishrichtlinie nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-445">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="f0d0e-446">Verwenden Sie die folgende Syntax, um eine #A0 in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-446">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="f0d0e-447">In diesem Beispiel wird die Antiphishregel "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-447">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="f0d0e-448">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="f0d0e-448">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f0d0e-449">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="f0d0e-449">How do you know these procedures worked?</span></span>

<span data-ttu-id="f0d0e-450">Gehen Sie wie folgt vor, um zu überprüfen, ob Sie die Antiphishingrichtlinien in Microsoft Defender for Office 365 erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-450">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="f0d0e-451">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-451">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="f0d0e-452">Überprüfen Sie die Liste der Richtlinien, ihre **Statuswerte** und ihre **Priority-Werte.**</span><span class="sxs-lookup"><span data-stu-id="f0d0e-452">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="f0d0e-453">Gehen Sie wie folgt vor, um weitere Details anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-453">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="f0d0e-454">Wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-454">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="f0d0e-455">Klicken **Sie auf Standardrichtlinie,** und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-455">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="f0d0e-456">Ersetzen Exchange Online PowerShell durch den Namen der Richtlinie oder Regel, und führen Sie den folgenden Befehl aus, und überprüfen Sie \<Name\> die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f0d0e-456">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```