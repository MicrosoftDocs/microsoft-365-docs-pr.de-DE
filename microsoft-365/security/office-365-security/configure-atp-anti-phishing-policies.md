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
description: Administratoren erfahren, wie Sie die erweiterten Antiphishingrichtlinien erstellen, ändern und löschen, die in Organisationen mit Microsoft Defender für Office 365 verfügbar sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d75455df972e9db0ef1cf4bbeba9f3b78b11002b
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406198"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ee413-103">Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="ee413-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ee413-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="ee413-104">**Applies to**</span></span>
- [<span data-ttu-id="ee413-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="ee413-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ee413-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ee413-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ee413-107">Antiphishingrichtlinien in [Microsoft Defender für Office 365](office-365-atp.md) können Ihre Organisation vor phishingbasierten Phishingangriffen und anderen Arten von Phishingangriffen schützen.</span><span class="sxs-lookup"><span data-stu-id="ee413-107">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="ee413-108">Weitere Informationen zu den Unterschieden zwischen Antiphishingrichtlinien in Exchange Online Protection (EOP) und Antiphishingrichtlinien in Microsoft Defender für Office 365 finden Sie unter [Antiphishingschutz](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="ee413-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="ee413-109">Administratoren können die standardmäßige Antiphishingrichtlinie anzeigen, bearbeiten und konfigurieren (aber nicht löschen).</span><span class="sxs-lookup"><span data-stu-id="ee413-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="ee413-110">Für eine höhere Granularität können Sie auch benutzerdefinierte Antiphishingrichtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="ee413-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="ee413-111">Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="ee413-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="ee413-112">Sie können Antiphishingrichtlinien im Security & Compliance Center oder in Exchange Online PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ee413-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="ee413-113">Informationen zum Konfigurieren der eingeschränkteren Antiphishingrichtlinien in Exchange Online Protection-Organisationen (d. h. Organisationen ohne Microsoft Defender für Office 365) finden Sie unter [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="ee413-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="ee413-114">Die grundlegenden Elemente einer Antiphishingrichtlinie sind:</span><span class="sxs-lookup"><span data-stu-id="ee413-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="ee413-115">**Die Antiphishrichtlinie**: Gibt die zu aktivierenden oder deaktivierenden Phishingschutzmaßnahmen sowie die Aktionen zum Anwenden von Optionen an.</span><span class="sxs-lookup"><span data-stu-id="ee413-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="ee413-116">**Die Antiphishregel**: Gibt die Priorität und empfängerfilter (auf wen die Richtlinie angewendet wird) für eine Antiphishrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="ee413-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="ee413-117">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Antiphishingrichtlinien im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="ee413-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="ee413-118">Wenn Sie eine Richtlinie erstellen, erstellen Sie tatsächlich eine Antiphishregel und die zugeordnete Antiphishrichtlinie gleichzeitig mit demselben Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="ee413-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="ee413-119">Wenn Sie eine Richtlinie ändern, ändern Einstellungen im Zusammenhang mit name, priority, enabled oder disabled und Empfängerfiltern die Antiphishregel.</span><span class="sxs-lookup"><span data-stu-id="ee413-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="ee413-120">Alle anderen Einstellungen ändern die zugeordnete Antiphishrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="ee413-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="ee413-121">Wenn Sie eine Richtlinie entfernen, werden die Antiphishregel und die zugehörige Antiphishrichtlinie entfernt.</span><span class="sxs-lookup"><span data-stu-id="ee413-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="ee413-122">In Exchange Online PowerShell verwalten Sie die Richtlinie und die Regel separat.</span><span class="sxs-lookup"><span data-stu-id="ee413-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="ee413-123">Weitere Informationen finden Sie im Abschnitt Verwenden von Exchange Online PowerShell zum Konfigurieren von [Antiphishingrichtlinien in Microsoft Defender für Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="ee413-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="ee413-124">Jede Microsoft Defender for Office 365-Organisation verfügt über eine integrierte Antiphishingrichtlinie namens Office365 AntiPhish Default mit folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ee413-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="ee413-125">Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, auch wenn der Richtlinie keine Antiphishregel (Empfängerfilter) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ee413-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="ee413-126">Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet).</span><span class="sxs-lookup"><span data-stu-id="ee413-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="ee413-127">Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität.</span><span class="sxs-lookup"><span data-stu-id="ee413-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="ee413-128">Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ee413-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="ee413-129">Um die Effektivität des Antiphishingschutzes in Microsoft Defender für Office 365 zu erhöhen, können Sie benutzerdefinierte Antiphishingrichtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee413-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ee413-130">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="ee413-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ee413-131">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ee413-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ee413-132">Um direkt zur **ATP-Antiphishingseite zu** wechseln, verwenden Sie <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="ee413-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="ee413-133">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ee413-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ee413-134">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in **Exchange Online** die entsprechenden Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="ee413-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ee413-135">Zum Hinzufügen, Ändern und Löschen von Antiphishingrichtlinien müssen  Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein.</span><span class="sxs-lookup"><span data-stu-id="ee413-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ee413-136">Für den schreibgeschützten Zugriff auf Antiphishingrichtlinien müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** <sup>\*</sup> sein.</span><span class="sxs-lookup"><span data-stu-id="ee413-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="ee413-137">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="ee413-137">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="ee413-138">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="ee413-138">**Notes**:</span></span>

  - <span data-ttu-id="ee413-139">Durch hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft  365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen und Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee413-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ee413-140">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ee413-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="ee413-141">Die **Rollengruppe "Nur-Ansichtsorganisationsverwaltung"** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) gewährt auch schreibgeschützten Zugriff auf das <sup>\*</sup> Feature.</span><span class="sxs-lookup"><span data-stu-id="ee413-141">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="ee413-142"><sup>\*</sup> Im Security & Compliance Center können Benutzer mit schreibgeschützten Zugriff die Einstellungen benutzerdefinierter Antiphishingrichtlinien anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ee413-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="ee413-143">Schreibgeschützte Benutzer können die Einstellungen in der Standardmäßigen Antiphishingrichtlinie nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="ee413-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="ee413-144">Unsere empfohlenen Einstellungen für Antiphishingrichtlinien in Microsoft Defender für Office 365 finden Sie unter [Antiphishingrichtlinie in Defender for Office 365-Einstellungen](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="ee413-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="ee413-145">Es ist bis zu 30 Minuten zulässig, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee413-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="ee413-146">Informationen dazu, wo Antiphishingrichtlinien in der Filterpipeline angewendet werden, finden Sie unter [Reihenfolge und Rangfolge des E-Mail-Schutzes](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="ee413-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ee413-147">Verwenden des Security & Compliance Center zum Erstellen von Antiphishingrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="ee413-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ee413-148">Beim Erstellen einer benutzerdefinierten Antiphishingrichtlinie im Security & Compliance Center werden die Antiphishregel und die zugehörige Antiphishingrichtlinie gleichzeitig mit demselben Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="ee413-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="ee413-149">Wenn Sie eine Antiphishingrichtlinie erstellen, können Sie nur den Richtliniennamen, die Beschreibung und den Empfängerfilter angeben, der identifiziert, auf wen die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee413-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="ee413-150">Nachdem Sie die Richtlinie erstellt haben, können Sie die Richtlinie ändern, um die Standardmäßigen Antiphishingeinstellungen zu ändern oder zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ee413-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="ee413-151">Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP-Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="ee413-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ee413-152">Klicken Sie **auf der Seite Antiphishing** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ee413-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="ee413-153">Der **Assistent zum Erstellen einer neuen Antiphishingrichtlinie** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ee413-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="ee413-154">Konfigurieren Sie **auf der Seite** Ihre Richtlinie benennen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ee413-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="ee413-155">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="ee413-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="ee413-156">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="ee413-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="ee413-157">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ee413-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ee413-158">Identifizieren Sie **auf der angezeigten** Seite Angewendet auf die internen Empfänger, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee413-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="ee413-159">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="ee413-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="ee413-160">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="ee413-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="ee413-161">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="ee413-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="ee413-162">Klicken **Sie auf Bedingung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ee413-162">Click **Add a condition**.</span></span> <span data-ttu-id="ee413-163">Wählen Sie in der angezeigten Dropdownliste unter Angewendet eine **Bedingung aus, wenn**:</span><span class="sxs-lookup"><span data-stu-id="ee413-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="ee413-164">**Der Empfänger ist**: Gibt ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="ee413-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="ee413-165">**Der Empfänger ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="ee413-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="ee413-166">**Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in der Organisation an.</span><span class="sxs-lookup"><span data-stu-id="ee413-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="ee413-167">Nachdem Sie die Bedingung ausgewählt haben, wird ein entsprechendes Dropdownfeld mit einem **Beliebigen dieser Kontrollkästchen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee413-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="ee413-168">Klicken Sie in das Feld, und scrollen Sie durch die Liste der auszuwählende Werte.</span><span class="sxs-lookup"><span data-stu-id="ee413-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="ee413-169">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ee413-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="ee413-170">Klicken Sie auf einen leeren Bereich im Feld, um weitere Werte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ee413-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="ee413-171">Klicken Sie zum Entfernen einzelner Einträge **auf Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für den Wert.</span><span class="sxs-lookup"><span data-stu-id="ee413-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="ee413-172">Klicken Sie zum Entfernen der gesamten Bedingung auf **Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für die Bedingung.</span><span class="sxs-lookup"><span data-stu-id="ee413-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="ee413-173">Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen,** und wählen Sie einen verbleibenden Wert unter **Angewendet wenn aus.**</span><span class="sxs-lookup"><span data-stu-id="ee413-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="ee413-174">Klicken Sie zum Hinzufügen von Ausnahmen auf **Bedingung hinzufügen,** und wählen Sie unter **Except if eine Ausnahme aus.**</span><span class="sxs-lookup"><span data-stu-id="ee413-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="ee413-175">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="ee413-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="ee413-176">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ee413-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ee413-177">Überprüfen Sie **auf der angezeigten** Seite Einstellungen überprüfen Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ee413-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="ee413-178">Sie können **für** jede Einstellung auf Bearbeiten klicken, um sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ee413-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="ee413-179">Klicken Sie nach Abschluss des Abschlusses auf **Diese Richtlinie erstellen.**</span><span class="sxs-lookup"><span data-stu-id="ee413-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="ee413-180">Klicken Sie im angezeigten Bestätigungsdialogfeld auf **OK.**</span><span class="sxs-lookup"><span data-stu-id="ee413-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="ee413-181">Nachdem Sie die Antiphishingrichtlinie mit diesen allgemeinen Einstellungen erstellt haben, verwenden Sie die Anweisungen im nächsten Abschnitt, um die Schutzeinstellungen in der Richtlinie zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ee413-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ee413-182">Verwenden des Security & Compliance Center zum Ändern von Antiphishingrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="ee413-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ee413-183">Verwenden Sie die folgenden Verfahren, um Antiphishingrichtlinien zu ändern: eine neue Richtlinie, die Sie erstellt haben, oder vorhandene Richtlinien, die Sie bereits angepasst haben.</span><span class="sxs-lookup"><span data-stu-id="ee413-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="ee413-184">Wenn Sie noch nicht vorhanden sind, öffnen Sie das Security & Compliance Center, und wechseln Sie zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP-Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="ee413-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ee413-185">Wählen Sie die benutzerdefinierte Antiphishingrichtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="ee413-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="ee413-186">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="ee413-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ee413-187">Das **Flyout \<name\> "Richtlinie bearbeiten"** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee413-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="ee413-188">Durch Klicken **auf Bearbeiten** in einem beliebigen Abschnitt erhalten Sie Zugriff auf die Einstellungen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="ee413-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="ee413-189">Die folgenden Schritte werden in der Reihenfolge dargestellt, in der die Abschnitte angezeigt werden, sie sind jedoch nicht sequenziell (Sie können die Abschnitte in beliebiger Reihenfolge auswählen und ändern).</span><span class="sxs-lookup"><span data-stu-id="ee413-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="ee413-190">Nachdem Sie **in** einem Abschnitt auf Bearbeiten geklickt haben, werden die verfügbaren Einstellungen in einem  Assistentenformat angezeigt, Sie  können jedoch in beliebiger Reihenfolge innerhalb der Seiten springen, und Sie können auf einer beliebigen Seite auf Speichern klicken (oder  ![ ](../../media/scc-remove-icon.png) **\<name\>** Abbrechen oder Schließen schließen, um zur Seite Richtlinie bearbeiten zurückzukehren (Sie müssen nicht die letzte Seite des Assistenten zum Speichern oder Verlassen des Assistenten besuchen).</span><span class="sxs-lookup"><span data-stu-id="ee413-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="ee413-191">**Richtlinieneinstellung**: Klicken Sie auf **Bearbeiten,** um dieselben Einstellungen zu ändern, die beim Erstellen der Richtlinie [im](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) vorherigen Abschnitt verfügbar waren:</span><span class="sxs-lookup"><span data-stu-id="ee413-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="ee413-192">**Name**</span><span class="sxs-lookup"><span data-stu-id="ee413-192">**Name**</span></span>
   - <span data-ttu-id="ee413-193">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ee413-193">**Description**</span></span>
   - <span data-ttu-id="ee413-194">**Angewendet auf**</span><span class="sxs-lookup"><span data-stu-id="ee413-194">**Applied to**</span></span>
   - <span data-ttu-id="ee413-195">**Überprüfen Der Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="ee413-195">**Review your settings**</span></span>

   <span data-ttu-id="ee413-196">Wenn Sie fertig sind, klicken Sie auf **einer beliebigen** Seite auf Speichern.</span><span class="sxs-lookup"><span data-stu-id="ee413-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="ee413-197">**Identitätswechsel**: Klicken Sie auf **Bearbeiten,** um die geschützten Absender und geschützten Domänen in der Richtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ee413-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="ee413-198">Diese Einstellungen sind eine Bedingung für die Richtlinie, die spoofierte Absender identifiziert, nach der (einzeln oder nach Domäne) in der Absenderadresse eingehender Nachrichten ermittelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ee413-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="ee413-199">Weitere Informationen finden Sie unter [Identitätswechseleinstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="ee413-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="ee413-200">**Benutzer zum Schützen hinzufügen:** Der Standardwert ist **Aus**.</span><span class="sxs-lookup"><span data-stu-id="ee413-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="ee413-201">Um es zu aktivieren, verschieben Sie den Umschalter auf **Ein**, und klicken Sie dann auf die schaltfläche Benutzer **hinzufügen,** die angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ee413-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="ee413-202">Konfigurieren Sie **im angezeigten** Flyout Benutzer hinzufügen die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="ee413-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="ee413-203">**E-Mail-Adresse**:</span><span class="sxs-lookup"><span data-stu-id="ee413-203">**Email address**:</span></span>

       - <span data-ttu-id="ee413-204">Klicken Sie in das Feld, und scrollen Sie durch die Liste der auszuwählende Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ee413-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="ee413-205">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ee413-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="ee413-206">Klicken Sie zum Entfernen eines Eintrags **auf Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ee413-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="ee413-207">**Name**: Dieser Wert wird basierend auf der ausgewählten E-Mail-Adresse aufgefüllt, Sie können ihn jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="ee413-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="ee413-208">Wenn Sie fertig sind, klicken Sie auf **einer beliebigen** Seite auf Speichern.</span><span class="sxs-lookup"><span data-stu-id="ee413-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="ee413-209">Wählen Sie zum Bearbeiten eines vorhandenen Eintrags den geschützten Benutzer in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="ee413-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="ee413-210">In jeder Antiphishingrichtlinie können Sie maximal 60 geschützte Benutzer (Absender-E-Mail-Adressen) angeben.</span><span class="sxs-lookup"><span data-stu-id="ee413-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="ee413-211">Sie können denselben geschützten Benutzer nicht in mehreren Richtlinien angeben.</span><span class="sxs-lookup"><span data-stu-id="ee413-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="ee413-212">Benutzerwechselschutz funktioniert nicht, wenn Absender und Empfänger zuvor per E-Mail kommuniziert haben.</span><span class="sxs-lookup"><span data-stu-id="ee413-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="ee413-213">Wenn Absender und Empfänger nie per E-Mail kommuniziert haben, wird die Nachricht als Identitätswechselversuch identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ee413-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="ee413-214">**Zu schützende Domänen hinzufügen:** Konfigurieren Sie eine oder beide der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ee413-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="ee413-215">**Schließen Sie automatisch die Domänen ein, die** ich selbst bin: Der Standardwert ist **Off**.</span><span class="sxs-lookup"><span data-stu-id="ee413-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="ee413-216">Um es zu aktivieren, verschieben Sie den Umschalter auf **Ein**.</span><span class="sxs-lookup"><span data-stu-id="ee413-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="ee413-217">**Benutzerdefinierte Domänen hinzufügen:** Der Standardwert ist **Aus**.</span><span class="sxs-lookup"><span data-stu-id="ee413-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="ee413-218">Verschieben Sie zum Aktivieren den Umschalter auf  **Ein**, und geben Sie im Feld Domänen hinzufügen den Domänennamen ein (z. B. contoso.com), drücken Sie die EINGABETASTE, und wiederholen Sie den Vorgang bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="ee413-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="ee413-219">In allen Antiphishingrichtlinien können maximal 50 Domänen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="ee413-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="ee413-220">**Aktionen**: Klicken Sie auf **Bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="ee413-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="ee413-221">**Wenn E-Mails** von einem imitierten Benutzer gesendet werden: Konfigurieren Sie eine der folgenden Aktionen für Nachrichten, bei denen der gefälschte Absender einer der geschützten Benutzer ist, die Sie unter Benutzer zum Schützen hinzufügen angegeben **haben:**</span><span class="sxs-lookup"><span data-stu-id="ee413-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="ee413-222">**Keine Aktion anwenden**</span><span class="sxs-lookup"><span data-stu-id="ee413-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="ee413-223">**Umleiten von Nachrichten an andere E-Mail-Adressen**</span><span class="sxs-lookup"><span data-stu-id="ee413-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="ee413-224">**Nachricht in Junk-E-Mail-Ordner verschieben**</span><span class="sxs-lookup"><span data-stu-id="ee413-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="ee413-225">**Isolieren der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="ee413-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="ee413-226">**Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**</span><span class="sxs-lookup"><span data-stu-id="ee413-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="ee413-227">**Löschen der Nachricht, bevor sie zugestellt wird**</span><span class="sxs-lookup"><span data-stu-id="ee413-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="ee413-228">**Wenn E-Mails** von einer imitierten Domäne gesendet werden: Konfigurieren Sie eine der folgenden Aktionen für Nachrichten, bei denen sich der gefälschte Absender in einer der geschützten Domänen befindet, die Sie unter Hinzufügen von Domänen zum Schützen angegeben **haben:**</span><span class="sxs-lookup"><span data-stu-id="ee413-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="ee413-229">**Keine Aktion anwenden**</span><span class="sxs-lookup"><span data-stu-id="ee413-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="ee413-230">**Umleiten von Nachrichten an andere E-Mail-Adressen**</span><span class="sxs-lookup"><span data-stu-id="ee413-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="ee413-231">**Nachricht in Junk-E-Mail-Ordner verschieben**</span><span class="sxs-lookup"><span data-stu-id="ee413-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="ee413-232">**Isolieren der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="ee413-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="ee413-233">**Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**</span><span class="sxs-lookup"><span data-stu-id="ee413-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="ee413-234">**Löschen der Nachricht, bevor sie zugestellt wird**</span><span class="sxs-lookup"><span data-stu-id="ee413-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="ee413-235">Klicken **Sie auf Identitätswechselsicherheitstipps aktivieren,** und konfigurieren Sie eine der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ee413-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="ee413-236">**Tipp für imitierte Benutzer anzeigen:** Der Standardwert ist **Aus**.</span><span class="sxs-lookup"><span data-stu-id="ee413-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="ee413-237">Um es zu aktivieren, verschieben Sie den Umschalter auf **Ein**.</span><span class="sxs-lookup"><span data-stu-id="ee413-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="ee413-238">**Tipp für identitätswechselte Domänen anzeigen:** Der Standardwert ist **Aus**.</span><span class="sxs-lookup"><span data-stu-id="ee413-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="ee413-239">Um es zu aktivieren, verschieben Sie den Umschalter auf **Ein**.</span><span class="sxs-lookup"><span data-stu-id="ee413-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="ee413-240">**Tipp für ungewöhnliche Zeichen anzeigen:** Der Standardwert ist **Off**.</span><span class="sxs-lookup"><span data-stu-id="ee413-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="ee413-241">Um es zu aktivieren, verschieben Sie den Umschalter auf **Ein**.</span><span class="sxs-lookup"><span data-stu-id="ee413-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="ee413-242">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ee413-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="ee413-243">**Postfachintelligenz**:</span><span class="sxs-lookup"><span data-stu-id="ee413-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="ee413-244">**Postfachintelligenz aktivieren?**: Der Standardwert ist **On**.</span><span class="sxs-lookup"><span data-stu-id="ee413-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="ee413-245">Um es zu deaktivieren, verschieben Sie den Umschalter auf **Aus**.</span><span class="sxs-lookup"><span data-stu-id="ee413-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="ee413-246">**Aktivieren Despersonationsschutzes für Postfachintelligenz aktivieren?**: Diese Einstellung ist nur verfügbar, wenn **Postfachintelligenz aktivieren?** ist **On**.</span><span class="sxs-lookup"><span data-stu-id="ee413-246">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="ee413-247">In **Wenn E-Mails** von einem imitierten Benutzer gesendet werden, können Sie eine der folgenden Aktionen für Nachrichten angeben, bei der die Postfachintelligenz fehlschlägt (die gleichen Aktionen, die für geschützte Benutzer und geschützte Domänen verfügbar sind):</span><span class="sxs-lookup"><span data-stu-id="ee413-247">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="ee413-248">**Keine Aktion anwenden**</span><span class="sxs-lookup"><span data-stu-id="ee413-248">**Don't apply any action**</span></span>
       - <span data-ttu-id="ee413-249">**Umleiten von Nachrichten an andere E-Mail-Adressen**</span><span class="sxs-lookup"><span data-stu-id="ee413-249">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="ee413-250">**Nachricht in Junk-E-Mail-Ordner verschieben**</span><span class="sxs-lookup"><span data-stu-id="ee413-250">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="ee413-251">**Isolieren der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="ee413-251">**Quarantine the message**</span></span>
       - <span data-ttu-id="ee413-252">**Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**</span><span class="sxs-lookup"><span data-stu-id="ee413-252">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="ee413-253">**Löschen der Nachricht, bevor sie zugestellt wird**</span><span class="sxs-lookup"><span data-stu-id="ee413-253">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="ee413-254">**Hinzufügen vertrauenswürdiger Absender und Domänen:** Geben Sie Ausnahmen für die Richtlinie an:</span><span class="sxs-lookup"><span data-stu-id="ee413-254">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="ee413-255">**Vertrauenswürdige Absender**:</span><span class="sxs-lookup"><span data-stu-id="ee413-255">**Trusted senders**:</span></span>

       - <span data-ttu-id="ee413-256">Klicken Sie in das Feld, und scrollen Sie durch die Liste der auszuwählende Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ee413-256">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="ee413-257">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ee413-257">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="ee413-258">Klicken Sie zum Entfernen eines Eintrags **auf Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ee413-258">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="ee413-259">**Vertrauenswürdige** Domänen: Geben Sie den Domänennamen ein (z. B. contoso.com), drücken Sie die EINGABETASTE, und wiederholen Sie sie bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="ee413-259">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="ee413-260">**Überprüfen Sie Ihre Einstellungen:** Anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee413-260">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="ee413-261">Sie können in jedem **Abschnitt** auf Bearbeiten klicken, um zur relevanten Seite zurück zu springen.</span><span class="sxs-lookup"><span data-stu-id="ee413-261">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="ee413-262">Sie können die folgenden  Einstellungen  direkt auf dieser Seite ein- oder ausschalten:</span><span class="sxs-lookup"><span data-stu-id="ee413-262">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="ee413-263">**Geschützte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="ee413-263">**Protected users**</span></span>
       - <span data-ttu-id="ee413-264">**Geschützte Domänen** \> **Schließen Sie Domänen ein, die ich selbst habe**</span><span class="sxs-lookup"><span data-stu-id="ee413-264">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="ee413-265">**Geschützte Domänen** \> **Geschützte Domänen** (benutzerdefinierte Domänen)</span><span class="sxs-lookup"><span data-stu-id="ee413-265">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="ee413-266">**Mailbox Intelligence**</span><span class="sxs-lookup"><span data-stu-id="ee413-266">**Mailbox intelligence**</span></span>

   <span data-ttu-id="ee413-267">Wenn Sie fertig sind, klicken Sie auf **einer beliebigen** Seite auf Speichern.</span><span class="sxs-lookup"><span data-stu-id="ee413-267">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="ee413-268">**Spoof**:  Klicken Sie auf Bearbeiten, um die Spoofintelligenz ein- oder auszuschalten, die Identifikation nicht authentifizierter Absender in Outlook ein- oder auszuschalten und die Aktion so zu konfigurieren, dass sie auf Nachrichten von blockierten spoofierten Absendern angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee413-268">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="ee413-269">Weitere Informationen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="ee413-269">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="ee413-270">Beachten Sie, dass diese Einstellungen auch in Antiphishingrichtlinien in EOP verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ee413-270">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="ee413-271">**Spoofing-Filtereinstellungen:** Der Standardwert ist **Ein**, und es wird empfohlen, ihn zu be lassen.</span><span class="sxs-lookup"><span data-stu-id="ee413-271">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="ee413-272">Um es zu deaktivieren, verschieben Sie den Umschalter auf **Aus**.</span><span class="sxs-lookup"><span data-stu-id="ee413-272">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="ee413-273">Weitere Informationen finden Sie unter [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="ee413-273">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="ee413-274">Sie müssen den Schutz vor Spoofing nicht deaktivieren, wenn Ihr #A0 nicht auf Microsoft 365 verweisen soll. Stattdessen aktivieren Sie erweiterte Filterung für Connectors.</span><span class="sxs-lookup"><span data-stu-id="ee413-274">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="ee413-275">Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="ee413-275">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="ee413-276">**Feature Nicht authentifizierter Absender aktivieren:** Der Standardwert ist **Ein**.</span><span class="sxs-lookup"><span data-stu-id="ee413-276">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="ee413-277">Um es zu deaktivieren, verschieben Sie den Umschalter auf **Aus**.</span><span class="sxs-lookup"><span data-stu-id="ee413-277">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="ee413-278">**Aktionen**: Geben Sie die Aktion für Nachrichten an, bei der spoof intelligence fehlschlagen:</span><span class="sxs-lookup"><span data-stu-id="ee413-278">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="ee413-279">**Wenn E-Mails von einer Person** gesendet werden, die Ihre Domäne nicht spoofen darf:</span><span class="sxs-lookup"><span data-stu-id="ee413-279">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="ee413-280">**Verschieben von Nachrichten in die Junk-E-Mail-Ordner der Empfänger**</span><span class="sxs-lookup"><span data-stu-id="ee413-280">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="ee413-281">**Isolieren der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="ee413-281">**Quarantine the message**</span></span>

   - <span data-ttu-id="ee413-282">**Überprüfen Sie Ihre Einstellungen:** Anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee413-282">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="ee413-283">Sie können in jedem **Abschnitt** auf Bearbeiten klicken, um zur relevanten Seite zurück zu springen.</span><span class="sxs-lookup"><span data-stu-id="ee413-283">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="ee413-284">Sie können die folgenden  Einstellungen  direkt auf dieser Seite ein- oder ausschalten:</span><span class="sxs-lookup"><span data-stu-id="ee413-284">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="ee413-285">**Aktivieren des Antispoofingschutzes**</span><span class="sxs-lookup"><span data-stu-id="ee413-285">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="ee413-286">**Aktivieren des Features "Nicht authentifizierter Absender"**</span><span class="sxs-lookup"><span data-stu-id="ee413-286">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="ee413-287">Wenn Sie fertig sind, klicken Sie auf **einer beliebigen** Seite auf Speichern.</span><span class="sxs-lookup"><span data-stu-id="ee413-287">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="ee413-288">**Erweiterte Einstellungen**: Klicken Sie **auf Bearbeiten,** um die erweiterten Phishingschwellenwerte zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ee413-288">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="ee413-289">Weitere Informationen finden Sie unter [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="ee413-289">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="ee413-290">**Erweiterte Phishingschwellenwerte:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="ee413-290">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="ee413-291">**1 – Standard** (Dies ist der Standardwert.)</span><span class="sxs-lookup"><span data-stu-id="ee413-291">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="ee413-292">**2 – Aggressiv**</span><span class="sxs-lookup"><span data-stu-id="ee413-292">**2 - Aggressive**</span></span>
   - <span data-ttu-id="ee413-293">**3 – Aggressiver**</span><span class="sxs-lookup"><span data-stu-id="ee413-293">**3 - More aggressive**</span></span>
   - <span data-ttu-id="ee413-294">**4 – Am aggressivsten**</span><span class="sxs-lookup"><span data-stu-id="ee413-294">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="ee413-295">**Überprüfen Sie Ihre Einstellungen:** Klicken Sie **auf Bearbeiten,** um zur Seite **Erweiterte Phishingschwellenwerte zurück** zu springen.</span><span class="sxs-lookup"><span data-stu-id="ee413-295">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="ee413-296">Wenn Sie fertig sind, klicken Sie auf beiden **Seiten** auf Speichern.</span><span class="sxs-lookup"><span data-stu-id="ee413-296">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="ee413-297">Überprüfen Sie auf **der Seite \<Name\>** Richtlinie bearbeiten Ihre Einstellungen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ee413-297">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ee413-298">Verwenden des Security & Compliance Center zum Ändern der Standardmäßigen Antiphishingrichtlinie in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="ee413-298">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ee413-299">Die standardmäßige Antiphishingrichtlinie in Microsoft Defender für Office 365 heißt Office365 AntiPhish Default und wird nicht in der Liste der Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee413-299">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="ee413-300">Gehen Sie wie folgt vor, um die Standardmäßige Antiphishingrichtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="ee413-300">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="ee413-301">Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP-Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="ee413-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ee413-302">Klicken Sie **auf der Seite Antiphishing** auf **Standardrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="ee413-302">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="ee413-303">Die **Seite Office365 AntiPhish Default** bearbeiten wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee413-303">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="ee413-304">Die folgenden Abschnitte sind verfügbar, die identische Einstellungen für das Ändern [einer benutzerdefinierten Richtlinie enthalten:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="ee413-304">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="ee413-305">**Impersonation**</span><span class="sxs-lookup"><span data-stu-id="ee413-305">**Impersonation**</span></span>
   - <span data-ttu-id="ee413-306">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="ee413-306">**Spoof**</span></span>
   - <span data-ttu-id="ee413-307">**Erweiterte Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="ee413-307">**Advanced settings**</span></span>

   <span data-ttu-id="ee413-308">Die folgenden Einstellungen sind nicht verfügbar, wenn Sie die Standardrichtlinie ändern:</span><span class="sxs-lookup"><span data-stu-id="ee413-308">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="ee413-309">Sie können  den Abschnitt Richtlinieneinstellung und -werte  anzeigen, es gibt jedoch keinen Link Bearbeiten, sodass Sie die Einstellungen nicht ändern können (Richtlinienname, Beschreibung und für wen die Richtlinie gilt (gilt für alle Empfänger)).</span><span class="sxs-lookup"><span data-stu-id="ee413-309">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="ee413-310">Die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ee413-310">You can't delete the default policy.</span></span>
   - <span data-ttu-id="ee413-311">Sie können die Priorität der Standardrichtlinie nicht ändern (sie wird immer zuletzt angewendet).</span><span class="sxs-lookup"><span data-stu-id="ee413-311">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="ee413-312">Überprüfen Sie **auf der Seite Office365-Standardrichtlinie** bearbeiten Ihre Einstellungen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ee413-312">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ee413-313">Aktivieren oder Deaktivieren benutzerdefinierter Antiphishingrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="ee413-313">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="ee413-314">Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP-Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="ee413-314">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ee413-315">Beachten Sie den Wert in der **Spalte Status:**</span><span class="sxs-lookup"><span data-stu-id="ee413-315">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="ee413-316">Verschieben Sie den Umschalter auf **Aus,** um die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ee413-316">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="ee413-317">Verschieben Sie den Umschalter auf **Ein,** um die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ee413-317">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="ee413-318">Sie können die standardmäßige Antiphishingrichtlinie nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ee413-318">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ee413-319">Festlegen der Priorität von benutzerdefinierten Antiphishingrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="ee413-319">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ee413-320">Standardmäßig erhalten Antiphishingrichtlinien eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="ee413-320">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="ee413-321">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="ee413-321">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="ee413-322">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ee413-322">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="ee413-323">Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="ee413-323">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="ee413-324">Benutzerdefinierte Antiphishingrichtlinien werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0).</span><span class="sxs-lookup"><span data-stu-id="ee413-324">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="ee413-325">Die Standardmäßige Antiphishingrichtlinie mit dem Namen Office365 AntiPhish Default hat den benutzerdefinierten Prioritätswert **Lowest**, und Sie können sie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="ee413-325">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="ee413-326">**Hinweis:** Im Security & Compliance Center können Sie die Priorität der Antiphishingrichtlinie nur ändern, nachdem Sie sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ee413-326">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="ee413-327">In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Antiphishregel erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="ee413-327">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="ee413-328">Um die Priorität einer Richtlinie  zu ändern, klicken Sie **in** den Eigenschaften der Richtlinie  auf Priorität erhöhen oder Priorität verringern (Sie können die Prioritätsnummer im Security & Compliance Center nicht direkt ändern).</span><span class="sxs-lookup"><span data-stu-id="ee413-328">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="ee413-329">Das Ändern der Priorität einer Richtlinie ist nur sinnvoll, wenn Sie über mehrere Richtlinien verfügen.</span><span class="sxs-lookup"><span data-stu-id="ee413-329">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="ee413-330">Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP-Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="ee413-330">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ee413-331">Wählen Sie die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="ee413-331">Select the policy that you want to modify.</span></span> <span data-ttu-id="ee413-332">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="ee413-332">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ee413-333">Das **Flyout \<name\> "Richtlinie bearbeiten"** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee413-333">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="ee413-334">Die benutzerdefinierte Antiphishingrichtlinie mit dem **Prioritätswert** **0** verfügt nur über die **Schaltfläche Priorität** verringern.</span><span class="sxs-lookup"><span data-stu-id="ee413-334">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="ee413-335">Die benutzerdefinierte Antiphishingrichtlinie mit dem niedrigsten **Prioritätswert** (z. B. **3**) verfügt nur über die **Schaltfläche Priorität erhöhen.**</span><span class="sxs-lookup"><span data-stu-id="ee413-335">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="ee413-336">Wenn Sie über drei oder mehr benutzerdefinierte Antiphishingrichtlinien verfügen, stehen Richtlinien zwischen den höchsten und niedrigsten Prioritätswerten sowohl die Schaltflächen **Priorität** erhöhen als auch **Priorität** verringern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ee413-336">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="ee413-337">Klicken **Sie auf Priorität erhöhen** oder Priorität **verringern,** um den **Prioritätswert zu** ändern.</span><span class="sxs-lookup"><span data-stu-id="ee413-337">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="ee413-338">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ee413-338">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ee413-339">Anzeigen von Antiphishingrichtlinien im Security & Compliance Center in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="ee413-339">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="ee413-340">Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP-Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="ee413-340">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ee413-341">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ee413-341">Do one of the following steps:</span></span>

   - <span data-ttu-id="ee413-342">Wählen Sie eine benutzerdefinierte Antiphishingrichtlinie aus, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="ee413-342">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="ee413-343">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="ee413-343">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="ee413-344">Klicken **Sie auf Standardrichtlinie,** um die Standardmäßige Antiphishingrichtlinie anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="ee413-344">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="ee413-345">Das **Flyout \<name\> "Richtlinie** bearbeiten" wird angezeigt, in dem Sie die Einstellungen und Werte anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="ee413-345">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ee413-346">Verwenden des Security & Compliance Center zum Entfernen von Antiphishingrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="ee413-346">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="ee413-347">Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP-Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="ee413-347">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ee413-348">Wählen Sie die Richtlinie aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="ee413-348">Select the policy that you want to remove.</span></span> <span data-ttu-id="ee413-349">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="ee413-349">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ee413-350">Klicken Sie **im \<name\> angezeigten** Flyout Richtlinie bearbeiten auf Richtlinie **löschen,** und klicken Sie **dann** im angezeigten Warndialogfeld auf Ja.</span><span class="sxs-lookup"><span data-stu-id="ee413-350">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="ee413-351">Die Standardrichtlinie kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="ee413-351">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ee413-352">Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365 mithilfe von Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee413-352">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ee413-353">Wie bereits beschrieben, besteht eine Antispamrichtlinie aus einer Antiphishrichtlinie und einer Antispamregel.</span><span class="sxs-lookup"><span data-stu-id="ee413-353">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="ee413-354">In Exchange Online PowerShell ist der Unterschied zwischen Antiphishrichtlinien und Antiphishregeln offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="ee413-354">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="ee413-355">Sie verwalten Antiphishrichtlinien mithilfe der **\* -AntiPhishPolicy-Cmdlets,** und Sie verwalten Antiphishregeln mithilfe der **\* -AntiPhishRule-Cmdlets.**</span><span class="sxs-lookup"><span data-stu-id="ee413-355">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="ee413-356">In PowerShell erstellen Sie zuerst die Antiphishrichtlinie, dann erstellen Sie die Antiphishregel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee413-356">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="ee413-357">In PowerShell ändern Sie die Einstellungen in der Antiphishrichtlinie und der Antiphishregel separat.</span><span class="sxs-lookup"><span data-stu-id="ee413-357">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="ee413-358">Wenn Sie eine Antiphishrichtlinie aus PowerShell entfernen, wird die entsprechende Antiphishregel nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="ee413-358">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="ee413-359">Erstellen von Antiphishingrichtlinien mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee413-359">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="ee413-360">Das Erstellen einer Antiphishingrichtlinie in PowerShell besteht aus zwei Stufen:</span><span class="sxs-lookup"><span data-stu-id="ee413-360">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="ee413-361">Erstellen Sie die Antiphishrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="ee413-361">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="ee413-362">Erstellen Sie die Antiphishregel, die die Antiphishrichtlinie angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee413-362">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="ee413-363">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="ee413-363">**Notes**:</span></span>

- <span data-ttu-id="ee413-364">Sie können eine neue Antiphishregel erstellen und ihr eine vorhandene, nicht zugeordnete Antiphishrichtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ee413-364">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="ee413-365">Eine Antiphishregel kann nicht mehr als einer Antiphishrichtlinie zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ee413-365">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="ee413-366">Sie können die folgenden Einstellungen für neue Antiphishrichtlinien in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="ee413-366">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="ee413-367">Erstellen Sie die neue Richtlinie als deaktiviert (_Aktiviert_ `$false` im Cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="ee413-367">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="ee413-368">Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) für das Cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="ee413-368">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="ee413-369">Eine neue Antiphishrichtlinie, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Antiphishregel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ee413-369">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="ee413-370">Schritt 1: Erstellen einer Antiphishrichtlinie mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee413-370">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="ee413-371">Verwenden Sie die folgende Syntax, um eine Antiphishrichtlinie zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="ee413-371">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="ee413-372">In diesem Beispiel wird eine Phishingrichtlinie mit dem Namen "Research Quarantine" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="ee413-372">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="ee413-373">Die Richtlinie ist aktiviert (der Parameter _Enabled_ wird nicht verwendet, und der Standardwert ist `$true` ).</span><span class="sxs-lookup"><span data-stu-id="ee413-373">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="ee413-374">Die Beschreibung ist: Research department policy.</span><span class="sxs-lookup"><span data-stu-id="ee413-374">The description is: Research department policy.</span></span>
- <span data-ttu-id="ee413-375">Ermöglicht den Schutz von Organisationsdomänen für alle akzeptierten Domänen und den gezielten Domänenschutz für fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="ee413-375">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="ee413-376">Gibt Mai Fujito (mfujito@fabrikam.com) als Benutzer an, der vor Identitätswechseln geschützt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ee413-376">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="ee413-377">Aktiviert die Postfachintelligenz.</span><span class="sxs-lookup"><span data-stu-id="ee413-377">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="ee413-378">Aktiviert den Postfachintelligenzschutz und gibt die Quarantäneaktion an.</span><span class="sxs-lookup"><span data-stu-id="ee413-378">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="ee413-379">Aktiviert Sicherheitstipps.</span><span class="sxs-lookup"><span data-stu-id="ee413-379">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="ee413-380">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="ee413-380">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="ee413-381">Schritt 2: Erstellen einer Antiphishregel mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee413-381">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="ee413-382">Verwenden Sie die folgende Syntax, um eine Antiphishregel zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="ee413-382">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="ee413-383">In diesem Beispiel wird eine Antiphishregel namens "Research Department" mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="ee413-383">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="ee413-384">Die Regel ist der Antiphishrichtlinie "Research Quarantine" zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ee413-384">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="ee413-385">Die Regel gilt für Mitglieder der Gruppe „Research Department“.</span><span class="sxs-lookup"><span data-stu-id="ee413-385">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="ee413-386">Da wir den Parameter _Priority_ nicht verwenden, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="ee413-386">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="ee413-387">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="ee413-387">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="ee413-388">Anzeigen von Antiphishrichtlinien mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee413-388">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="ee413-389">Verwenden Sie die folgende Syntax, um vorhandene Antiphishrichtlinien anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="ee413-389">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ee413-390">In diesem Beispiel wird eine Zusammenfassungsliste aller Antiphishrichtlinien zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ee413-390">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="ee413-391">In diesem Beispiel werden alle Eigenschaftswerte für die Antiphishrichtlinie "Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ee413-391">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="ee413-392">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="ee413-392">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="ee413-393">Anzeigen von Antiphishregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee413-393">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="ee413-394">Verwenden Sie die folgende Syntax, um vorhandene Antiphishregeln anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="ee413-394">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ee413-395">In diesem Beispiel wird eine Zusammenfassungsliste aller Antiphishregeln zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ee413-395">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="ee413-396">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="ee413-396">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="ee413-397">In diesem Beispiel werden alle Eigenschaftswerte für die Antiphishregel namens Contoso Executives zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ee413-397">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="ee413-398">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="ee413-398">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="ee413-399">Verwenden von PowerShell zum Ändern von Antiphishrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ee413-399">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="ee413-400">Neben den folgenden Elementen sind dieselben Einstellungen verfügbar, wenn Sie eine Antiphishrichtlinie in PowerShell ändern, als wenn Sie die Richtlinie wie im Abschnitt Schritt 1: Verwenden von [PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) beschrieben erstellen, um einen Richtlinienabschnitt zum Phishingschutz weiter oben in diesem Artikel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ee413-400">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="ee413-401">Die _MakeDefault-Option,_ die die angegebene Richtlinie in die  Standardrichtlinie umstellt (auf alle Benutzer angewendet, immer niedrigste Priorität, und Sie können sie nicht löschen) ist nur verfügbar, wenn Sie eine Antiphishrichtlinie in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="ee413-401">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="ee413-402">Sie können eine Antiphishrichtlinie nicht umbenennen (das **Cmdlet Set-AntiPhishPolicy** hat keinen _Name-Parameter)._</span><span class="sxs-lookup"><span data-stu-id="ee413-402">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="ee413-403">Wenn Sie eine Antiphishingrichtlinie im Security & Compliance Center umbenennen, benennen Sie nur die Antiphishingregel _um._</span><span class="sxs-lookup"><span data-stu-id="ee413-403">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="ee413-404">Verwenden Sie die folgende Syntax, um eine Antiphishrichtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="ee413-404">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="ee413-405">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="ee413-405">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="ee413-406">Verwenden von PowerShell zum Ändern von Antiphishregeln</span><span class="sxs-lookup"><span data-stu-id="ee413-406">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="ee413-407">Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine Antiphishregel in PowerShell ändern, ist der _Parameter Enabled,_ mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="ee413-407">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="ee413-408">Informationen zum Aktivieren oder Deaktivieren vorhandener Antiphishregeln finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="ee413-408">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="ee413-409">Andernfalls sind keine zusätzlichen Einstellungen verfügbar, wenn Sie eine Antiphishregel in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="ee413-409">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="ee413-410">Die gleichen Einstellungen sind verfügbar, wenn Sie eine Regel wie im Abschnitt Schritt 2: Verwenden von PowerShell beschrieben erstellen, um einen [Antiphishregelabschnitt](#step-2-use-powershell-to-create-an-anti-phish-rule) weiter oben in diesem Artikel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ee413-410">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="ee413-411">Verwenden Sie die folgende Syntax, um eine Antiphishregel zu ändern:</span><span class="sxs-lookup"><span data-stu-id="ee413-411">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="ee413-412">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="ee413-412">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="ee413-413">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Antiphishregeln</span><span class="sxs-lookup"><span data-stu-id="ee413-413">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="ee413-414">Durch Aktivieren oder Deaktivieren einer Antiphishregel in PowerShell wird die gesamte Antiphishingrichtlinie (die Antiphishregel und die zugewiesene Antiphishingrichtlinie) aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ee413-414">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="ee413-415">Sie können die standardmäßige Antiphishingrichtlinie nicht aktivieren oder deaktivieren (sie wird immer auf alle Empfänger angewendet).</span><span class="sxs-lookup"><span data-stu-id="ee413-415">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="ee413-416">Verwenden Sie die folgende Syntax, um eine #A0 in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="ee413-416">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="ee413-417">In diesem Beispiel wird die Antiphishregel "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ee413-417">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ee413-418">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ee413-418">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ee413-419">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) und [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="ee413-419">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="ee413-420">Festlegen der Priorität von Antiphishregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee413-420">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="ee413-421">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="ee413-421">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="ee413-422">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="ee413-422">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="ee413-423">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee413-423">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="ee413-424">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="ee413-424">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="ee413-425">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="ee413-425">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="ee413-426">Verwenden Sie die folgende Syntax, um die Priorität einer #A0 in PowerShell zu setzen:</span><span class="sxs-lookup"><span data-stu-id="ee413-426">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="ee413-p148">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="ee413-p148">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="ee413-429">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="ee413-429">**Notes**:</span></span>

- <span data-ttu-id="ee413-430">Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den _Parameter Priority_ im Cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="ee413-430">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="ee413-431">Die Standardmäßige Antiphishrichtlinie verfügt nicht über eine entsprechende Antiphishregel und hat immer den nicht veränderbaren Prioritätswert **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="ee413-431">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="ee413-432">Entfernen von Antiphishrichtlinien mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee413-432">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="ee413-433">Wenn Sie PowerShell verwenden, um eine Antiphishrichtlinie zu entfernen, wird die entsprechende Antiphishregel nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="ee413-433">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="ee413-434">Verwenden Sie die folgende Syntax, um eine #A0 in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="ee413-434">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="ee413-435">In diesem Beispiel wird die Antiphishrichtlinie "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="ee413-435">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="ee413-436">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="ee413-436">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="ee413-437">Entfernen von Antiphishregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee413-437">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="ee413-438">Wenn Sie PowerShell verwenden, um eine Antiphishregel zu entfernen, wird die entsprechende Antiphishrichtlinie nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="ee413-438">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="ee413-439">Verwenden Sie die folgende Syntax, um eine #A0 in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="ee413-439">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="ee413-440">In diesem Beispiel wird die Antiphishregel "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="ee413-440">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ee413-441">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="ee413-441">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ee413-442">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="ee413-442">How do you know these procedures worked?</span></span>

<span data-ttu-id="ee413-443">Gehen Sie wie folgt vor, um zu überprüfen, ob Sie Antiphishingrichtlinien in Microsoft Defender für Office 365 erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="ee413-443">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="ee413-444">Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP-Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="ee413-444">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="ee413-445">Überprüfen Sie die Liste der Richtlinien, ihre **Statuswerte** und ihre **Priority-Werte.**</span><span class="sxs-lookup"><span data-stu-id="ee413-445">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="ee413-446">Gehen Sie wie folgt vor, um weitere Details anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="ee413-446">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="ee413-447">Wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="ee413-447">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="ee413-448">Klicken **Sie auf Standardrichtlinie,** und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="ee413-448">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="ee413-449">Ersetzen Sie in Exchange Online PowerShell durch den Namen der Richtlinie oder Regel, und führen Sie den folgenden Befehl aus, und überprüfen Sie \<Name\> die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ee413-449">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
