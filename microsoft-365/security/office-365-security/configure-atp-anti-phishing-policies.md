---
title: Konfigurieren der ATP Antiphishing-Richtlinien
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie die erweiterten Anti-Phishing-Richtlinien erstellen, ändern und löschen, die in Organisationen mit Office 365 Advanced Threat Protection (Office 365 ATP) verfügbar sind.
ms.openlocfilehash: 458a4eac348598d1b752267ed7d79b97bc594580
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726767"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="74d60-103">Konfigurieren der ATP Antiphishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="74d60-103">Configure ATP anti-phishing policies</span></span>

<span data-ttu-id="74d60-104">ATP-Anti-Phishing-Richtlinien sind Teil [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="74d60-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="74d60-105">Durch ATP-Richtlinien zum Schutz vor Phishing können Sie Ihre Organisation vor böswilligen Identitätswechsel basierten Phishing-Angriffen und anderen Arten von Phishing-Angriffen schützen.</span><span class="sxs-lookup"><span data-stu-id="74d60-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="74d60-106">Weitere Informationen zu den Unterschieden zwischen Anti-Phishing-Richtlinien in Exchange Online Protection (EoP) und ATP Anti-Phishing Policies finden Sie unter [Anti-Phishing Protection](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="74d60-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="74d60-107">Administratoren können die standardmäßige ATP-Anti-Phishing-Richtlinie anzeigen, bearbeiten und konfigurieren (jedoch nicht löschen).</span><span class="sxs-lookup"><span data-stu-id="74d60-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="74d60-108">Um eine höhere Granularität zu erzielen, können Sie auch benutzerdefinierte ATP-Anti-Phishing-Richtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="74d60-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="74d60-109">Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="74d60-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="74d60-110">Sie können ATP-Anti-Phishing-Richtlinien im Security & Compliance Center oder in Exchange Online PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="74d60-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="74d60-111">Informationen zum Konfigurieren der eingeschränkteren AntiPhishing-Richtlinien, die in Exchange Online Schutzorganisationen (Microsoft 365-Organisationen ohne Office 365 ATP) zur Verfügung stehen, finden Sie unter [configure Anti-Phishing Policies in EoP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="74d60-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="74d60-112">ATP-Richtlinien zum Schutz vor Phishing im Security & Compliance Center vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="74d60-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="74d60-113">Die grundlegenden Elemente einer ATP-Anti-Phishing-Richtlinie sind:</span><span class="sxs-lookup"><span data-stu-id="74d60-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="74d60-114">**Die Anti-Phishing-Richtlinie**: gibt die zu aktivierenden oder zu deaktivierenden Phishing-Schutzmaßnahmen sowie die Aktionen zum Anwenden von Optionen an.</span><span class="sxs-lookup"><span data-stu-id="74d60-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="74d60-115">**Die Anti-Phishing-Regel**: gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) für eine Anti-Phishing-Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="74d60-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="74d60-116">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für die ATP-Anti-Phishing im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="74d60-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="74d60-117">Wenn Sie eine ATP-Richtlinie zum Schutz vor Phishing im Security & Compliance Center erstellen, erstellen Sie tatsächlich eine Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie gleichzeitig mit dem gleichen Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="74d60-117">When you create an ATP anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="74d60-118">Wenn Sie eine ATP-Richtlinie zum Schutz vor Phishing im Security & Compliance Center ändern, ändern die Einstellungen im Zusammenhang mit dem Namen, der Priorität, den aktivierten oder deaktivierten und den Empfänger filtern die Anti-Phishing-Regel.</span><span class="sxs-lookup"><span data-stu-id="74d60-118">When you modify an ATP anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="74d60-119">Alle anderen Einstellungen ändern die zugehörige Anti-Phishing-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="74d60-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="74d60-120">Wenn Sie eine ATP-Richtlinie zum Schutz vor Phishing aus dem Security & Compliance Center entfernen, werden die Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie entfernt.</span><span class="sxs-lookup"><span data-stu-id="74d60-120">When you remove an ATP anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="74d60-121">In Exchange Online PowerShell ist der Unterschied zwischen Anti-Phishing-Richtlinien und Anti-Phishing-Regeln offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="74d60-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="74d60-122">Sie können Anti-Phishing-Richtlinien mithilfe der \*\* \* -AntiPhishPolicy-\*\* Cmdlets verwalten und Anti-Phishing-Regeln mithilfe der Cmdlets \*\* \* -AntiPhishRule\*\* verwalten.</span><span class="sxs-lookup"><span data-stu-id="74d60-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="74d60-123">In PowerShell erstellen Sie zuerst die Anti-Phishing-Richtlinie, dann erstellen Sie die Anti-Phishing-Regel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="74d60-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="74d60-124">In PowerShell ändern Sie die Einstellungen in der Anti-Phishing-Richtlinie und in der Anti-Phishing-Regel separat.</span><span class="sxs-lookup"><span data-stu-id="74d60-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

- <span data-ttu-id="74d60-125">Wenn Sie eine Anti-Phishing-Richtlinie aus PowerShell entfernen, wird die entsprechende Anti-Phishing-Regel nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="74d60-125">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="74d60-126">Standardmäßige ATP-Anti-Phishing-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="74d60-126">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="74d60-127">Jede ATP-Organisation verfügt über eine integrierte ATP-Richtlinie zum Schutz vor Phishing mit dem Namen "Office365 AntiPhishing default", die die folgenden Eigenschaften aufweist:</span><span class="sxs-lookup"><span data-stu-id="74d60-127">Every ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="74d60-128">Die Anti-Phishing-Richtlinie mit dem Namen "Office365 AntiPhishing default" wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine Anti-Phishing-Regel (Empfängerfilter) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="74d60-128">The anti-phish policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="74d60-129">Die Richtlinie mit dem Namen Office365 AntiPhishing default weist den benutzerdefinierten Prioritätswert auf **niedrigster** Bedeutung auf, den Sie nicht ändern können (die Richtlinie wird immer zuletzt angewendet).</span><span class="sxs-lookup"><span data-stu-id="74d60-129">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="74d60-130">Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität als die Richtlinie mit dem Namen Office365 AntiPhishing default.</span><span class="sxs-lookup"><span data-stu-id="74d60-130">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="74d60-131">Die Richtlinie mit dem Namen Office365 AntiPhishing Default ist die Standardrichtlinie (die **IsDefault** -Eigenschaft hat den Wert `True` ), und die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="74d60-131">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="74d60-132">Um die Effektivität des Anti-Phishing-Schutzes zu verbessern, können Sie benutzerdefinierte ATP-Anti-Phishing-Richtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="74d60-132">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="74d60-133">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="74d60-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="74d60-134">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="74d60-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="74d60-135">Um direkt zur Seite " **ATP-AntiPhishing** " zu wechseln, verwenden Sie <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="74d60-135">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="74d60-136">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="74d60-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="74d60-137">Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Verfahren in diesem Thema ausführen können:</span><span class="sxs-lookup"><span data-stu-id="74d60-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="74d60-138">Zum Hinzufügen, ändern und Löschen von ATP-Richtlinien zum Schutz vor Phishing müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="74d60-138">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="74d60-139">**Organisationsverwaltung** oder **Sicherheits Administrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="74d60-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="74d60-140">**Organisationsverwaltung** oder **Hygiene Verwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="74d60-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="74d60-141">Für den schreibgeschützten Zugriff auf ATP-Richtlinien für die Anti-Phishing müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="74d60-141">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="74d60-142">**Sicherheits Leser** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="74d60-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="74d60-143">**Organisationsverwaltung mit Ansichts** Schutz in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="74d60-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="74d60-144">Unsere empfohlenen Einstellungen für ATP-AntiPhishing-Richtlinien finden Sie unter Einstellungen für Anti-Phishing-Richtlinien für [Office ATP](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="74d60-144">For our recommended settings for ATP anti-phishing policies, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="74d60-145">Erlauben Sie bis zu 30 Minuten, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="74d60-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="74d60-146">Informationen dazu, wo Anti-Phishing-Richtlinien in der Filter Pipeline angewendet werden, finden Sie unter [Order and Ranges of Email Protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="74d60-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="74d60-147">Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für die ATP-Anti-Phishing</span><span class="sxs-lookup"><span data-stu-id="74d60-147">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="74d60-148">Durch das Erstellen einer benutzerdefinierten ATP-Richtlinie zum Schutz vor Phishing im Security & Compliance Center werden die Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie gleichzeitig mit dem gleichen Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="74d60-148">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="74d60-149">Wenn Sie eine ATP-Anti-Phishing-Richtlinie erstellen, können Sie nur den Richtliniennamen, die Beschreibung und den Empfängerfilter angeben, der angibt, für wen die Richtlinie gilt.</span><span class="sxs-lookup"><span data-stu-id="74d60-149">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="74d60-150">Nachdem Sie die Richtlinie erstellt haben, können Sie die Richtlinie ändern, um die Standardeinstellungen für AntiPhishing zu ändern oder zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="74d60-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="74d60-151">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="74d60-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="74d60-152">Klicken Sie auf der Seite **Anti-Phishing** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="74d60-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="74d60-153">Der Assistent zum **Erstellen eines neuen Anti-Phishing-Richtlinien** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="74d60-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="74d60-154">Konfigurieren Sie auf der Seite **Ihre Richtlinie benennen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="74d60-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="74d60-155">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="74d60-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="74d60-156">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="74d60-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="74d60-157">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="74d60-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="74d60-158">Identifizieren Sie auf der Seite **angewendet auf** , die angezeigt wird, die internen Empfänger, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="74d60-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="74d60-159">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="74d60-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="74d60-160">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="74d60-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="74d60-161">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="74d60-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="74d60-162">Klicken Sie auf **Bedingung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="74d60-162">Click **Add a condition**.</span></span> <span data-ttu-id="74d60-163">Wählen Sie in der Dropdownliste, die angezeigt wird, eine Bedingung unter **angewendet, wenn**:</span><span class="sxs-lookup"><span data-stu-id="74d60-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="74d60-164">**Der Empfänger lautet**: gibt ein oder mehrere Postfächer, e-Mail-Benutzer oder e-Mail-Kontakte in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="74d60-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="74d60-165">**Der Empfänger ist Mitglied von**: gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="74d60-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="74d60-166">**Die Empfängerdomäne lautet**: gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in der Organisation an.</span><span class="sxs-lookup"><span data-stu-id="74d60-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="74d60-167">Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **der folgenden** Felder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74d60-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="74d60-168">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der zu markierende Werte durch.</span><span class="sxs-lookup"><span data-stu-id="74d60-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="74d60-169">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="74d60-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="74d60-170">Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="74d60-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="74d60-171">Wenn Sie einzelne Einträge entfernen möchten **Remove** , klicken Sie auf Entfernen- ![ Symbol ](../../media/scc-remove-icon.png) für den Wert entfernen.</span><span class="sxs-lookup"><span data-stu-id="74d60-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="74d60-172">Wenn Sie die gesamte Bedingung entfernen möchten **, klicken Sie** ![ in der Bedingung auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="74d60-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="74d60-173">Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen** , und wählen Sie einen verbleibenden Wert unter **angewendet bei**aus.</span><span class="sxs-lookup"><span data-stu-id="74d60-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="74d60-174">Wenn Sie Ausnahmen hinzufügen möchten, klicken Sie auf **Bedingung hinzufügen** , und wählen Sie unter **außer if**eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="74d60-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="74d60-175">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="74d60-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="74d60-176">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="74d60-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="74d60-177">Überprüfen Sie auf der angezeigten Seite **Ihre Einstellungen überprüfen** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="74d60-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="74d60-178">Sie können auf jeder Einstellung auf **Bearbeiten** klicken, um Sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="74d60-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="74d60-179">Wenn Sie fertig sind, klicken Sie auf **Diese Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="74d60-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="74d60-180">Klicken Sie im Bestätigungsdialogfeld, das angezeigt wird, auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="74d60-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="74d60-181">Nachdem Sie die ATP-Anti-Phishing-Richtlinie mit diesen allgemeinen Richtlinieneinstellungen erstellt haben, konfigurieren Sie die Schutzeinstellungen in der Richtlinie mithilfe der Anweisungen im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="74d60-181">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="74d60-182">Verwenden des Security & Compliance Center zum Ändern von ATP-Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="74d60-182">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="74d60-183">Verwenden Sie die folgenden Verfahren, um ATP-AntiPhishing-Richtlinien zu ändern: eine neue Richtlinie, die Sie erstellt haben, oder vorhandene Richtlinien, die Sie bereits angepasst haben.</span><span class="sxs-lookup"><span data-stu-id="74d60-183">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="74d60-184">Wenn Sie noch nicht vorhanden sind, öffnen Sie das Security & Compliance Center, und wechseln Sie zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="74d60-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="74d60-185">Wählen Sie die benutzerdefinierte ATP-Anti-Phishing-Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="74d60-185">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="74d60-186">Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.</span><span class="sxs-lookup"><span data-stu-id="74d60-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="74d60-187">Das Flyout **Richtlinie \<name\> Bearbeiten** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74d60-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="74d60-188">Durch Klicken auf **Bearbeiten** in einem beliebigen Abschnitt erhalten Sie Zugriff auf die Einstellungen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="74d60-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="74d60-189">Die folgenden Schritte werden in der Reihenfolge angezeigt, in der die Abschnitte dargestellt werden, Sie sind jedoch nicht sequenziell (Sie können die Abschnitte in beliebiger Reihenfolge auswählen und ändern).</span><span class="sxs-lookup"><span data-stu-id="74d60-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="74d60-190">Nachdem Sie in einem Abschnitt auf **Bearbeiten** klicken, werden die verfügbaren Einstellungen in einem Assistenten Format angezeigt, aber Sie können in beliebiger Reihenfolge auf die Seiten springen, und Sie können auf einer beliebigen Seite auf **Speichern** **(oder** **Abbrechen** oder Schließen schließen) klicken, um ![ ](../../media/scc-remove-icon.png) zur Seite **Richtlinie \<name\> Bearbeiten** zurückzukehren (Sie müssen nicht die letzte Seite des Assistenten zum Speichern oder verlassen besuchen).</span><span class="sxs-lookup"><span data-stu-id="74d60-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="74d60-191">**Richtlinieneinstellung**: Klicken Sie auf **Bearbeiten** , um dieselben Einstellungen zu ändern, die beim [Erstellen der Richtlinie](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) im vorherigen Abschnitt verfügbar waren:</span><span class="sxs-lookup"><span data-stu-id="74d60-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="74d60-192">**Name**</span><span class="sxs-lookup"><span data-stu-id="74d60-192">**Name**</span></span>
   - <span data-ttu-id="74d60-193">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="74d60-193">**Description**</span></span>
   - <span data-ttu-id="74d60-194">**Angewendet auf**</span><span class="sxs-lookup"><span data-stu-id="74d60-194">**Applied to**</span></span>
   - <span data-ttu-id="74d60-195">**Ihre Einstellungen überprüfen**</span><span class="sxs-lookup"><span data-stu-id="74d60-195">**Review your settings**</span></span>

   <span data-ttu-id="74d60-196">Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="74d60-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="74d60-197">**Identitätswechsel**: Klicken Sie auf **Bearbeiten** , um die geschützten Absender und geschützten Domänen in der Richtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="74d60-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="74d60-198">Diese Einstellungen sind eine Bedingung für die Richtlinie, die gefälschte Absender identifiziert, die in der von-Adresse eingehende Nachrichten (einzeln oder nach Domäne) suchen.</span><span class="sxs-lookup"><span data-stu-id="74d60-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="74d60-199">Weitere Informationen finden Sie unter [Identitätswechseleinstellungen in ATP-Richtlinien zum Schutz vor Phishing](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="74d60-199">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="74d60-200">**Hinzufügen von Benutzern zu Protect**: der Standardwert ist **Off**.</span><span class="sxs-lookup"><span data-stu-id="74d60-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="74d60-201">Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein**, und klicken Sie dann auf die Schaltfläche **Benutzer hinzufügen** , die angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="74d60-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="74d60-202">Konfigurieren Sie im angezeigten **Benutzer Flyout hinzufügen** die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="74d60-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="74d60-203">**E-Mail-Adresse**:</span><span class="sxs-lookup"><span data-stu-id="74d60-203">**Email address**:</span></span>

        - <span data-ttu-id="74d60-204">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der Benutzer aus, die Sie auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="74d60-204">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="74d60-205">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="74d60-205">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="74d60-206">Wenn Sie einen Eintrag entfernen möchten **Remove** , klicken Sie auf Entfernen- ![ Symbol ](../../media/scc-remove-icon.png) für den Benutzer entfernen.</span><span class="sxs-lookup"><span data-stu-id="74d60-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="74d60-207">**Name**: dieser Wert wird basierend auf der e-Mail-Adresse aufgefüllt, die Sie ausgewählt haben, aber Sie können ihn ändern.</span><span class="sxs-lookup"><span data-stu-id="74d60-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="74d60-208">Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="74d60-208">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="74d60-209">Um einen vorhandenen Eintrag zu bearbeiten, wählen Sie den geschützten Benutzer in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="74d60-209">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="74d60-210">**Hinzufügen von Domänen zu Protect**: Konfigurieren Sie eine oder beide der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="74d60-210">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="74d60-211">**Automatisches einschließen der Domänen, die ich besitze**: der Standardwert ist **Off**.</span><span class="sxs-lookup"><span data-stu-id="74d60-211">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="74d60-212">Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein**.</span><span class="sxs-lookup"><span data-stu-id="74d60-212">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="74d60-213">**Benutzerdefinierte Domänen einschließen**: der Standardwert ist **Off**.</span><span class="sxs-lookup"><span data-stu-id="74d60-213">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="74d60-214">Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein**, und geben Sie im Feld **Domänen hinzufügen** den Domänennamen ein (beispielsweise contoso.com), drücken Sie die EINGABETASTE, und wiederholen Sie den Vorgang bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="74d60-214">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="74d60-215">**Aktionen**: Klicken Sie auf **Bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="74d60-215">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="74d60-216">**Wenn e-Mail von einem imitierten Benutzer gesendet wird**: Konfigurieren Sie eine der folgenden Aktionen für Nachrichten, bei denen der gefälschte Absender einer der geschützten Benutzer ist, die Sie in **Add users to Protect**angegeben haben:</span><span class="sxs-lookup"><span data-stu-id="74d60-216">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="74d60-217">**Keine Aktion anwenden**</span><span class="sxs-lookup"><span data-stu-id="74d60-217">**Don't apply any action**</span></span>
       - <span data-ttu-id="74d60-218">**Weiterleiten von Nachrichten an andere e-Mail-Adressen**</span><span class="sxs-lookup"><span data-stu-id="74d60-218">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="74d60-219">**Nachricht in Junk-E-Mail-Ordner verschieben**</span><span class="sxs-lookup"><span data-stu-id="74d60-219">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="74d60-220">**Nachricht isolieren**</span><span class="sxs-lookup"><span data-stu-id="74d60-220">**Quarantine the message**</span></span>
       - <span data-ttu-id="74d60-221">**Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**</span><span class="sxs-lookup"><span data-stu-id="74d60-221">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="74d60-222">**Löschen der Nachricht vor der Zustellung**</span><span class="sxs-lookup"><span data-stu-id="74d60-222">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="74d60-223">**Wenn e-Mail von einer imitierten Domäne gesendet wird**: Konfigurieren Sie eine der folgenden Aktionen für Nachrichten, bei denen sich der gefälschte Absender in einer der geschützten Domänen befindet, die Sie in **Add Domains to Protect**angegeben haben:</span><span class="sxs-lookup"><span data-stu-id="74d60-223">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="74d60-224">**Keine Aktion anwenden**</span><span class="sxs-lookup"><span data-stu-id="74d60-224">**Don't apply any action**</span></span>
     - <span data-ttu-id="74d60-225">**Weiterleiten von Nachrichten an andere e-Mail-Adressen**</span><span class="sxs-lookup"><span data-stu-id="74d60-225">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="74d60-226">**Nachricht in Junk-E-Mail-Ordner verschieben**</span><span class="sxs-lookup"><span data-stu-id="74d60-226">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="74d60-227">**Nachricht isolieren**</span><span class="sxs-lookup"><span data-stu-id="74d60-227">**Quarantine the message**</span></span>
     - <span data-ttu-id="74d60-228">**Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**</span><span class="sxs-lookup"><span data-stu-id="74d60-228">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="74d60-229">**Löschen der Nachricht vor der Zustellung**</span><span class="sxs-lookup"><span data-stu-id="74d60-229">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="74d60-230">Klicken Sie auf **Identitätswechsel-Sicherheitstipps einschalten** , und konfigurieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="74d60-230">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="74d60-231">**Tipp für imitierte Benutzer anzeigen**: der Standardwert ist **Off**.</span><span class="sxs-lookup"><span data-stu-id="74d60-231">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="74d60-232">Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein**.</span><span class="sxs-lookup"><span data-stu-id="74d60-232">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="74d60-233">**Tipp für imitierte Domänen anzeigen**: der Standardwert ist **Off**.</span><span class="sxs-lookup"><span data-stu-id="74d60-233">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="74d60-234">Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein**.</span><span class="sxs-lookup"><span data-stu-id="74d60-234">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="74d60-235">**Tipp für ungewöhnliche Zeichen anzeigen**: der Standardwert ist **Off**.</span><span class="sxs-lookup"><span data-stu-id="74d60-235">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="74d60-236">Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein**.</span><span class="sxs-lookup"><span data-stu-id="74d60-236">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="74d60-237">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="74d60-237">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="74d60-238">**Post Fach Intelligenz**:</span><span class="sxs-lookup"><span data-stu-id="74d60-238">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="74d60-239">**Mailbox Intelligence aktivieren?**: der Standardwert ist **on**.</span><span class="sxs-lookup"><span data-stu-id="74d60-239">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="74d60-240">Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus**.</span><span class="sxs-lookup"><span data-stu-id="74d60-240">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="74d60-241">**Aktivieren des Post Fach informationsbasierten Identitätswechsel Schutzes?**: Diese Einstellung ist nur verfügbar, wenn **Mailbox Intelligence aktivieren** aktiviert **ist.**</span><span class="sxs-lookup"><span data-stu-id="74d60-241">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="74d60-242">**Wenn e-Mails von einem imitierten Benutzer gesendet**werden, können Sie eine der folgenden Aktionen für Nachrichten, die nicht die Post Fach Intelligenz ausführen (dieselben Aktionen, die für geschützte Benutzer und geschützte Domänen zur Verfügung stehen) angeben:</span><span class="sxs-lookup"><span data-stu-id="74d60-242">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="74d60-243">**Keine Aktion anwenden**</span><span class="sxs-lookup"><span data-stu-id="74d60-243">**Don't apply any action**</span></span>
       - <span data-ttu-id="74d60-244">**Weiterleiten von Nachrichten an andere e-Mail-Adressen**</span><span class="sxs-lookup"><span data-stu-id="74d60-244">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="74d60-245">**Nachricht in Junk-E-Mail-Ordner verschieben**</span><span class="sxs-lookup"><span data-stu-id="74d60-245">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="74d60-246">**Nachricht isolieren**</span><span class="sxs-lookup"><span data-stu-id="74d60-246">**Quarantine the message**</span></span>
       - <span data-ttu-id="74d60-247">**Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**</span><span class="sxs-lookup"><span data-stu-id="74d60-247">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="74d60-248">**Löschen der Nachricht vor der Zustellung**</span><span class="sxs-lookup"><span data-stu-id="74d60-248">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="74d60-249">**Hinzufügen von vertrauenswürdigen Absendern und Domänen**: Angeben von Ausnahmen für die Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="74d60-249">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="74d60-250">**Vertrauenswürdige Absender**:</span><span class="sxs-lookup"><span data-stu-id="74d60-250">**Trusted senders**:</span></span>

       - <span data-ttu-id="74d60-251">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der Benutzer aus, die Sie auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="74d60-251">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="74d60-252">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="74d60-252">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="74d60-253">Wenn Sie einen Eintrag entfernen möchten **Remove** , klicken Sie auf Entfernen- ![ Symbol ](../../media/scc-remove-icon.png) für den Benutzer entfernen.</span><span class="sxs-lookup"><span data-stu-id="74d60-253">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="74d60-254">**Vertrauenswürdige Domänen**: Geben Sie den Domänennamen ein (beispielsweise contoso.com), drücken Sie die EINGABETASTE, und wiederholen Sie den Vorgang bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="74d60-254">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="74d60-255">**Überprüfen Sie Ihre Einstellungen**: anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74d60-255">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="74d60-256">Sie können in jedem Abschnitt auf **Bearbeiten** klicken, um zurück zur entsprechenden Seite zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="74d60-256">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="74d60-257">Sie können die **folgenden Einstellungen direkt auf dieser** Seite aktivieren oder **Deaktivieren** :</span><span class="sxs-lookup"><span data-stu-id="74d60-257">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="74d60-258">**Geschützte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="74d60-258">**Protected users**</span></span>
       - <span data-ttu-id="74d60-259">**Geschützte Domänen** \> **Domänen einschließen, die ich besitze**</span><span class="sxs-lookup"><span data-stu-id="74d60-259">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="74d60-260">**Geschützte Domänen** \> **Geschützte Domänen** (benutzerdefinierte Domänen)</span><span class="sxs-lookup"><span data-stu-id="74d60-260">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="74d60-261">**Mailbox Intelligence**</span><span class="sxs-lookup"><span data-stu-id="74d60-261">**Mailbox intelligence**</span></span>

   <span data-ttu-id="74d60-262">Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="74d60-262">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="74d60-263">**Spoof**: Klicken Sie auf **Bearbeiten** , um Spoof Intelligence ein-oder auszuschalten, die nicht authentifizierte Absender Identifikation in Outlook ein-oder auszuschalten und die Aktion so zu konfigurieren, dass Sie auf Nachrichten von blockierten gefälschten Absendern angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="74d60-263">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="74d60-264">Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="74d60-264">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="74d60-265">Beachten Sie, dass diese Einstellungen auch in Anti-Phishing-Richtlinien in EoP verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="74d60-265">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="74d60-266">**Spoofing-Filtereinstellungen**: der Standardwert ist " **on**", und es wird empfohlen, dass Sie die Einstellung aktiviert lassen.</span><span class="sxs-lookup"><span data-stu-id="74d60-266">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="74d60-267">Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus**.</span><span class="sxs-lookup"><span data-stu-id="74d60-267">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="74d60-268">Weitere Informationen finden Sie unter [configure Spoof Intelligence in EoP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="74d60-268">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="74d60-269">Sie müssen den Schutz vor Spoofing nicht deaktivieren, wenn Ihr MX-Eintrag nicht auf Microsoft 365 verweist; Stattdessen aktivieren Sie die erweiterte Filterung für Connectors.</span><span class="sxs-lookup"><span data-stu-id="74d60-269">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="74d60-270">Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="74d60-270">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="74d60-271">Nicht **authentifizierte Absender Funktion aktivieren**: der Standardwert ist **on**.</span><span class="sxs-lookup"><span data-stu-id="74d60-271">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="74d60-272">Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus**.</span><span class="sxs-lookup"><span data-stu-id="74d60-272">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="74d60-273">**Actions: geben**Sie die Aktion an, die für Nachrichten ausgeführt werden soll, die Spoof Intelligence nicht ausführen:</span><span class="sxs-lookup"><span data-stu-id="74d60-273">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="74d60-274">**Wenn e-Mails von Benutzern gesendet werden, die Ihre Domäne nicht spoofen dürfen**:</span><span class="sxs-lookup"><span data-stu-id="74d60-274">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="74d60-275">**Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern**</span><span class="sxs-lookup"><span data-stu-id="74d60-275">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="74d60-276">**Nachricht isolieren**</span><span class="sxs-lookup"><span data-stu-id="74d60-276">**Quarantine the message**</span></span>

   - <span data-ttu-id="74d60-277">**Überprüfen Sie Ihre Einstellungen**: anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74d60-277">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="74d60-278">Sie können in jedem Abschnitt auf **Bearbeiten** klicken, um zurück zur entsprechenden Seite zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="74d60-278">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="74d60-279">Sie können die **folgenden Einstellungen direkt auf dieser** Seite aktivieren oder **Deaktivieren** :</span><span class="sxs-lookup"><span data-stu-id="74d60-279">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="74d60-280">**Aktivieren von Schutz vor Spoofing**</span><span class="sxs-lookup"><span data-stu-id="74d60-280">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="74d60-281">**Nicht authentifizierte Absender Funktion aktivieren**</span><span class="sxs-lookup"><span data-stu-id="74d60-281">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="74d60-282">Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="74d60-282">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="74d60-283">**Erweiterte Einstellungen**: Klicken Sie auf **Bearbeiten** , um die erweiterten Phishing-Schwellenwerte zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="74d60-283">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="74d60-284">Weitere Informationen finden Sie unter [Advanced Phishing Thresholds in ATP Anti-Phishing Policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="74d60-284">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="74d60-285">**Erweiterte Phishing-Schwellen**Werte: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="74d60-285">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="74d60-286">**1-Standard** (Dies ist der Standardwert.)</span><span class="sxs-lookup"><span data-stu-id="74d60-286">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="74d60-287">**2-aggressiv**</span><span class="sxs-lookup"><span data-stu-id="74d60-287">**2 - Aggressive**</span></span>
   - <span data-ttu-id="74d60-288">**3-aggressiver**</span><span class="sxs-lookup"><span data-stu-id="74d60-288">**3 - More aggressive**</span></span>
   - <span data-ttu-id="74d60-289">**4-aggressiv**</span><span class="sxs-lookup"><span data-stu-id="74d60-289">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="74d60-290">**Überprüfen Sie Ihre Einstellungen**: Klicken Sie auf **Bearbeiten** , um zurück zur Seite **erweiterte Phishing-Schwellenwerte** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="74d60-290">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="74d60-291">Wenn Sie fertig sind, klicken Sie auf einer der Seiten auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="74d60-291">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="74d60-292">Überprüfen Sie die Einstellungen auf der Seite **Richtlinie \<Name\> Bearbeiten** , und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="74d60-292">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="74d60-293">Verwenden Sie das Security & Compliance Center, um die standardmäßige ATP-Anti-Phishing-Richtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="74d60-293">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="74d60-294">Die standardmäßige ATP-Anti-Phishing-Richtlinie heißt Office365 AntiPhishing default und wird nicht in der Liste der Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74d60-294">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="74d60-295">Führen Sie die folgenden Schritte aus, um die standardmäßige ATP-Anti-Phishing-Richtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="74d60-295">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="74d60-296">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="74d60-296">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="74d60-297">Klicken Sie auf der Seite **Anti-Phishing** auf **Standardrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="74d60-297">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="74d60-298">Die **Standardseite Ihre Richtlinie Office365 AntiPhishing bearbeiten** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74d60-298">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="74d60-299">Die folgenden Abschnitte sind verfügbar, die identische Einstellungen für beim [Ändern einer benutzerdefinierten Richtlinie](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)enthalten:</span><span class="sxs-lookup"><span data-stu-id="74d60-299">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="74d60-300">**Impersonation**</span><span class="sxs-lookup"><span data-stu-id="74d60-300">**Impersonation**</span></span>
   - <span data-ttu-id="74d60-301">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="74d60-301">**Spoof**</span></span>
   - <span data-ttu-id="74d60-302">**Erweiterte Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="74d60-302">**Advanced settings**</span></span>

   <span data-ttu-id="74d60-303">Die folgenden Einstellungen sind nicht verfügbar, wenn Sie die Standardrichtlinie ändern:</span><span class="sxs-lookup"><span data-stu-id="74d60-303">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="74d60-304">Sie können den Abschnitt mit den **Richtlinieneinstellungen** und die Werte anzeigen, es gibt jedoch keinen Link **Bearbeiten** , sodass Sie die Einstellungen nicht ändern können (Richtlinienname, Beschreibung und für wen die Richtlinie gilt (gilt für alle Empfänger)).</span><span class="sxs-lookup"><span data-stu-id="74d60-304">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="74d60-305">Die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="74d60-305">You can't delete the default policy.</span></span>
   - <span data-ttu-id="74d60-306">Sie können die Priorität der Standardrichtlinie nicht ändern (Sie wird immer zuletzt angewendet).</span><span class="sxs-lookup"><span data-stu-id="74d60-306">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="74d60-307">Überprüfen Sie auf der **Standardseite Richtlinie Office365 bearbeiten** die Einstellungen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="74d60-307">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="74d60-308">Aktivieren oder Deaktivieren von benutzerdefinierten ATP-Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="74d60-308">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="74d60-309">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="74d60-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="74d60-310">Beachten Sie den Wert in der Spalte **Status** :</span><span class="sxs-lookup"><span data-stu-id="74d60-310">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="74d60-311">Schieben Sie die Umschaltfläche auf **aus** , um die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="74d60-311">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="74d60-312">Schieben Sie die Umschaltfläche in **ein** , um die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="74d60-312">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="74d60-313">Sie können die standardmäßige Anti-Phishing-Richtlinie nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="74d60-313">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="74d60-314">Festlegen der Priorität von benutzerdefinierten ATP-Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="74d60-314">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="74d60-315">Standardmäßig erhalten Richtlinien für ATP-AntiPhishing eine Priorität, die auf der Reihenfolge basiert, in der Sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="74d60-315">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="74d60-316">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="74d60-316">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="74d60-317">Zwei Richtlinien können nicht dieselbe Priorität haben.</span><span class="sxs-lookup"><span data-stu-id="74d60-317">No two policies can have the same priority.</span></span>

<span data-ttu-id="74d60-318">Benutzerdefinierte ATP-Anti-Phishing-Richtlinien werden in der Reihenfolge angezeigt, in der Sie verarbeitet werden (die erste Richtlinie hat den **Prioritäts** Wert 0).</span><span class="sxs-lookup"><span data-stu-id="74d60-318">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="74d60-319">Die standardmäßige Anti-Phishing-Richtlinie mit dem Namen "Office365 AntiPhishing default" weist den benutzerdefinierten Prioritätswert als " **niedrigste**" auf und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="74d60-319">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="74d60-320">**Hinweis**: im Security & Compliance Center können Sie die Priorität der ATP-Anti-Phishing-Richtlinie nur ändern, nachdem Sie Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="74d60-320">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="74d60-321">In PowerShell können Sie die Standardpriorität außer Kraft setzen, wenn Sie die Anti-Phishing-Regel erstellen (die sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="74d60-321">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="74d60-322">Um die Priorität einer Richtlinie zu ändern, klicken Sie in den Eigenschaften der Richtlinie auf **Priorität verbessern** oder **Priorität verringern** (die **Prioritäts** Nummer im Security & Compliance Center kann nicht direkt geändert werden).</span><span class="sxs-lookup"><span data-stu-id="74d60-322">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="74d60-323">Das Ändern der Priorität einer Richtlinie ist nur dann sinnvoll, wenn Sie über mehrere Richtlinien verfügen.</span><span class="sxs-lookup"><span data-stu-id="74d60-323">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="74d60-324">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="74d60-324">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="74d60-325">Wählen Sie die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="74d60-325">Select the policy that you want to modify.</span></span> <span data-ttu-id="74d60-326">Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.</span><span class="sxs-lookup"><span data-stu-id="74d60-326">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="74d60-327">Das Flyout **Richtlinie \<name\> Bearbeiten** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74d60-327">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="74d60-328">Die benutzerdefinierte ATP-Anti-Phishing-Richtlinie mit dem **Prioritäts** Wert **0** hat nur die Schaltfläche **Priorität verringern** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="74d60-328">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="74d60-329">Die benutzerdefinierte ATP-Anti-Phishing-Richtlinie mit dem niedrigsten **Prioritäts** Wert (beispielsweise **3**) hat nur die Schaltfläche " **Priorität verlängern** " zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="74d60-329">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="74d60-330">Wenn Sie über drei oder mehr benutzerdefinierte Anti-Phishing-Richtlinien verfügen, stehen für Richtlinien zwischen den Werten der höchsten und der niedrigsten Priorität **sowohl die Prioritätsschaltflächen "Priorität"** als auch " **Priorität verringern** " zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="74d60-330">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="74d60-331">Klicken Sie auf Priorität Verb **Essern** oder **Priorität verringern** , um den **Prioritäts** Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="74d60-331">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="74d60-332">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="74d60-332">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="74d60-333">Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien für die ATP-Anti-Phishing</span><span class="sxs-lookup"><span data-stu-id="74d60-333">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="74d60-334">Im Security & Compliance Center und wechseln Sie zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="74d60-334">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="74d60-335">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="74d60-335">Do one of the following steps:</span></span>

   - <span data-ttu-id="74d60-336">Wählen Sie eine benutzerdefinierte ATP-Anti-Phishing-Richtlinie aus, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="74d60-336">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="74d60-337">Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.</span><span class="sxs-lookup"><span data-stu-id="74d60-337">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="74d60-338">Klicken Sie auf **Standardrichtlinie** , um die standardmäßige Anti-Phishing-Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="74d60-338">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="74d60-339">Das Flyout zum **Bearbeiten \<name\> Ihrer Richtlinie** wird angezeigt, in dem Sie die Einstellungen und Werte anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="74d60-339">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="74d60-340">Verwenden des Security & Compliance Center zum Entfernen von ATP-Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="74d60-340">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="74d60-341">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="74d60-341">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="74d60-342">Wählen Sie die Richtlinie aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="74d60-342">Select the policy that you want to remove.</span></span> <span data-ttu-id="74d60-343">Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.</span><span class="sxs-lookup"><span data-stu-id="74d60-343">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="74d60-344">Klicken Sie im daraufhin angezeigten Dialogfeld **Richtlinie \<name\> Bearbeiten** auf **Richtlinie löschen**, und klicken Sie dann im angezeigten Warndialogfeld auf **Ja** .</span><span class="sxs-lookup"><span data-stu-id="74d60-344">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="74d60-345">Die Standardrichtlinie kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="74d60-345">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="74d60-346">Konfigurieren von Richtlinien für die ATP-Anti-Phishing mithilfe Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="74d60-346">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="74d60-347">Verwenden von PowerShell zum Erstellen von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="74d60-347">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="74d60-348">Das Erstellen einer Anti-Phishing-Richtlinie in PowerShell ist ein zweistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="74d60-348">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="74d60-349">Erstellen Sie die Anti-Phishing-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="74d60-349">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="74d60-350">Erstellen Sie die Anti-Phishing-Regel, die die Anti-Phishing-Richtlinie angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="74d60-350">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="74d60-351">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="74d60-351">**Notes**:</span></span>

- <span data-ttu-id="74d60-352">Sie können eine neue Anti-Phishing-Regel erstellen und ihr eine vorhandene, nicht zugeordnete Anti-Phishing-Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="74d60-352">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="74d60-353">Eine Anti-Phishing-Regel kann nicht mehr als einer Anti-Phishing-Richtlinie zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="74d60-353">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="74d60-354">Sie können die folgenden Einstellungen für neue Anti-Phishing-Richtlinien in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Security & Compliance Center verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="74d60-354">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="74d60-355">Erstellen Sie die neue Richtlinie als deaktiviert (_aktiviert_ im `$false` Cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="74d60-355">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="74d60-356">Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) für das Cmdlet **New-AntiPhishRule** fest).</span><span class="sxs-lookup"><span data-stu-id="74d60-356">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="74d60-357">Eine neue Anti-Phishing-Richtlinie, die Sie in PowerShell erstellen, ist erst im Security & Compliance Center sichtbar, wenn Sie die Richtlinie einer Anti-Phishing-Regel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="74d60-357">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="74d60-358">Schritt 1: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="74d60-358">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="74d60-359">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Richtlinie zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="74d60-359">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="74d60-360">In diesem Beispiel wird die Anti-Phishing-Richtlinie mit dem Namen "Research Quarantine" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="74d60-360">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="74d60-361">Die Richtlinie ist aktiviert (der Parameter _Enabled_ wird nicht verwendet, und der Standardwert ist `$true` ).</span><span class="sxs-lookup"><span data-stu-id="74d60-361">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="74d60-362">Die Beschreibung lautet: Abteilungs Richtlinie für Forschung.</span><span class="sxs-lookup"><span data-stu-id="74d60-362">The description is: Research department policy.</span></span>
- <span data-ttu-id="74d60-363">Aktiviert den Schutz von Organisationsdomänen für alle akzeptierten Domänen und den Schutz von Zieldomänen für fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="74d60-363">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="74d60-364">Gibt Mai Fujito (mfujito@fabrikam.com) als Benutzer an, der vor Identitätswechsel geschützt werden soll.</span><span class="sxs-lookup"><span data-stu-id="74d60-364">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="74d60-365">Aktiviert Post Fach Intelligenz.</span><span class="sxs-lookup"><span data-stu-id="74d60-365">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="74d60-366">Aktiviert den Nachrichtenschutz für Postfächer und gibt die Quarantäneaktion an.</span><span class="sxs-lookup"><span data-stu-id="74d60-366">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="74d60-367">Aktiviert Sicherheitstipps.</span><span class="sxs-lookup"><span data-stu-id="74d60-367">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="74d60-368">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="74d60-368">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="74d60-369">Schritt 2: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Regel</span><span class="sxs-lookup"><span data-stu-id="74d60-369">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="74d60-370">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="74d60-370">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="74d60-371">In diesem Beispiel wird eine Anti-Phishing-Regel namens "Research Department" mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="74d60-371">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="74d60-372">Die Regel ist der Anti-Phishing-Richtlinie "Research Quarantine" zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="74d60-372">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="74d60-373">Die Regel gilt für Mitglieder der Gruppe „Research Department“.</span><span class="sxs-lookup"><span data-stu-id="74d60-373">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="74d60-374">Da wir den _Priority_ -Parameter nicht verwenden, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="74d60-374">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="74d60-375">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="74d60-375">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="74d60-376">Verwenden von PowerShell zum Anzeigen von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="74d60-376">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="74d60-377">Verwenden Sie die folgende Syntax, um vorhandene Anti-Phishing-Richtlinien anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="74d60-377">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="74d60-378">In diesem Beispiel wird eine Zusammenfassungsliste aller Anti-Phishing-Richtlinien zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="74d60-378">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="74d60-379">In diesem Beispiel werden alle Eigenschaftswerte für die Anti-Phishing-Richtlinie "Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="74d60-379">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="74d60-380">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="74d60-380">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="74d60-381">Verwenden von PowerShell zum Anzeigen von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="74d60-381">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="74d60-382">Verwenden Sie die folgende Syntax, um vorhandene Anti-Phishing-Regeln anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="74d60-382">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="74d60-383">In diesem Beispiel wird eine Zusammenfassungsliste aller Anti-Phishing-Regeln zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="74d60-383">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="74d60-384">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="74d60-384">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="74d60-385">In diesem Beispiel werden alle Eigenschaftswerte für die Anti-Phishing-Regel namens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="74d60-385">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="74d60-386">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="74d60-386">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="74d60-387">Verwenden von PowerShell zum Ändern von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="74d60-387">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="74d60-388">Anders als die folgenden Elemente sind die gleichen Einstellungen verfügbar, wenn Sie eine Anti-Phishing-Richtlinie in PowerShell wie beim Erstellen der Richtlinie wie im Abschnitt [Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie zu AntiPhishing-Richt](#step-1-use-powershell-to-create-an-anti-phish-policy) Linien weiter oben in diesem Thema ändern.</span><span class="sxs-lookup"><span data-stu-id="74d60-388">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="74d60-389">Der _MakeDefault_ -Schalter, der die angegebene Richtlinie in die Standardrichtlinie umwandelt (gilt für alle, immer **niedrigste** Priorität, und Sie können Sie nicht löschen) ist nur verfügbar, wenn Sie eine Anti-Phishing-Richtlinie in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="74d60-389">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="74d60-390">Sie können keine Anti-Phishing-Richtlinie umbenennen (das Cmdlet " **AntiPhishPolicy** " hat keinen Parameter " _Name_ ").</span><span class="sxs-lookup"><span data-stu-id="74d60-390">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="74d60-391">Wenn Sie eine Richtlinie zum Schutz vor Phishing im Security & Compliance Center umbenennen, benennen Sie die Anti-Phishing- _Regel_nur um.</span><span class="sxs-lookup"><span data-stu-id="74d60-391">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="74d60-392">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Richtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="74d60-392">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="74d60-393">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="74d60-393">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="74d60-394">Verwenden von PowerShell zum Ändern von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="74d60-394">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="74d60-395">Die einzige Einstellung, die beim Ändern einer Anti-Phishing-Regel in PowerShell nicht verfügbar ist, ist der Parameter _Enabled_ , mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="74d60-395">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="74d60-396">Informationen zum Aktivieren oder Deaktivieren vorhandener Anti-Phishing-Regeln finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="74d60-396">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="74d60-397">Andernfalls stehen keine zusätzlichen Einstellungen zur Verfügung, wenn Sie eine Anti-Phishing-Regel in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="74d60-397">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="74d60-398">Die gleichen Einstellungen sind verfügbar, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Regel](#step-2-use-powershell-to-create-an-anti-phish-rule) weiter oben in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74d60-398">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="74d60-399">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel zu ändern:</span><span class="sxs-lookup"><span data-stu-id="74d60-399">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="74d60-400">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="74d60-400">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="74d60-401">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="74d60-401">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="74d60-402">Durch das Aktivieren oder Deaktivieren einer Anti-Phishing-Regel in PowerShell wird die gesamte Richtlinie zum Schutz vor Phishing aktiviert oder deaktiviert (die Anti-Phishing-Regel und die zugewiesene Anti-Phishing-Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="74d60-402">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="74d60-403">Sie können die standardmäßige Anti-Phishing-Richtlinie nicht aktivieren oder deaktivieren (Sie wird immer auf alle Empfänger angewendet).</span><span class="sxs-lookup"><span data-stu-id="74d60-403">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="74d60-404">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="74d60-404">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="74d60-405">In diesem Beispiel wird die Anti-Phishing-Regel namens "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="74d60-405">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="74d60-406">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="74d60-406">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="74d60-407">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) und [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="74d60-407">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="74d60-408">Verwenden von PowerShell zum Festlegen der Priorität von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="74d60-408">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="74d60-409">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="74d60-409">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="74d60-410">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="74d60-410">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="74d60-411">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="74d60-411">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="74d60-412">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="74d60-412">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="74d60-413">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="74d60-413">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="74d60-414">Verwenden Sie die folgende Syntax, um die Priorität einer Anti-Phishing-Regel in PowerShell festzulegen:</span><span class="sxs-lookup"><span data-stu-id="74d60-414">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="74d60-415">This example sets the priority of the rule named Marketing Department to 2.</span><span class="sxs-lookup"><span data-stu-id="74d60-415">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="74d60-416">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span><span class="sxs-lookup"><span data-stu-id="74d60-416">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="74d60-417">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="74d60-417">**Notes**:</span></span>

- <span data-ttu-id="74d60-418">Wenn Sie die Priorität einer neuen Regel beim Erstellen festlegen möchten, verwenden Sie stattdessen den Parameter _Priority_ für das Cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="74d60-418">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="74d60-419">Die standardmäßige Anti-Phishing-Richtlinie verfügt nicht über eine entsprechende Anti-Phishing-Regel, und Sie hat immer den Wert unveränderbare Priorität **niedrigste**.</span><span class="sxs-lookup"><span data-stu-id="74d60-419">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="74d60-420">Verwenden von PowerShell zum Entfernen von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="74d60-420">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="74d60-421">Wenn Sie PowerShell zum Entfernen einer Anti-Phishing-Richtlinie verwenden, wird die entsprechende Anti-Phishing-Regel nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="74d60-421">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="74d60-422">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Richtlinie in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="74d60-422">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="74d60-423">In diesem Beispiel wird die Anti-Phishing-Richtlinie namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="74d60-423">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="74d60-424">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="74d60-424">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="74d60-425">Verwenden von PowerShell zum Entfernen von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="74d60-425">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="74d60-426">Wenn Sie PowerShell zum Entfernen einer Anti-Phishing-Regel verwenden, wird die entsprechende Anti-Phishing-Richtlinie nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="74d60-426">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="74d60-427">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="74d60-427">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="74d60-428">In diesem Beispiel wird die Anti-Phishing-Regel namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="74d60-428">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="74d60-429">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="74d60-429">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="74d60-430">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="74d60-430">How do you know these procedures worked?</span></span>

<span data-ttu-id="74d60-431">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie die Richtlinien für ATP-Phishing erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="74d60-431">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="74d60-432">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="74d60-432">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="74d60-433">Überprüfen Sie die Liste der Richtlinien, deren **Status** Werte und deren **Prioritäts** Werte.</span><span class="sxs-lookup"><span data-stu-id="74d60-433">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="74d60-434">Um weitere Details anzuzeigen, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="74d60-434">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="74d60-435">Wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="74d60-435">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="74d60-436">Klicken Sie auf **Standardrichtlinie** , und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="74d60-436">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="74d60-437">Ersetzen Sie in Exchange Online PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, und führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="74d60-437">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
