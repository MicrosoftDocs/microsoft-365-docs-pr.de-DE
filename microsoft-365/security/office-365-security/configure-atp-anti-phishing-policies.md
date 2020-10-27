---
title: Konfigurieren der ATP Antiphishing-Richtlinien
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie die erweiterten Anti-Phishing-Richtlinien erstellen, ändern und löschen, die in Organisationen mit Office 365 Advanced Threat Protection (Office 365 ATP) verfügbar sind.
ms.openlocfilehash: d6655089556f7268222dc47e2196f8aa1fc3da4e
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769220"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="3a05c-103">Konfigurieren der ATP Antiphishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3a05c-103">Configure ATP anti-phishing policies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3a05c-104">ATP-Anti-Phishing-Richtlinien sind Teil [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="3a05c-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="3a05c-105">Durch ATP-Richtlinien zum Schutz vor Phishing können Sie Ihre Organisation vor böswilligen Identitätswechsel basierten Phishing-Angriffen und anderen Arten von Phishing-Angriffen schützen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="3a05c-106">Weitere Informationen zu den Unterschieden zwischen Anti-Phishing-Richtlinien in Exchange Online Protection (EoP) und ATP Anti-Phishing Policies finden Sie unter [Anti-Phishing Protection](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="3a05c-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="3a05c-107">Administratoren können die standardmäßige ATP-Anti-Phishing-Richtlinie anzeigen, bearbeiten und konfigurieren (jedoch nicht löschen).</span><span class="sxs-lookup"><span data-stu-id="3a05c-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="3a05c-108">Um eine höhere Granularität zu erzielen, können Sie auch benutzerdefinierte ATP-Anti-Phishing-Richtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="3a05c-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="3a05c-109">Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="3a05c-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="3a05c-110">Sie können ATP-Anti-Phishing-Richtlinien im Security & Compliance Center oder in Exchange Online PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3a05c-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="3a05c-111">Informationen zum Konfigurieren der eingeschränkteren AntiPhishing-Richtlinien, die in Exchange Online Schutzorganisationen (Microsoft 365-Organisationen ohne Office 365 ATP) zur Verfügung stehen, finden Sie unter [configure Anti-Phishing Policies in EoP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="3a05c-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="3a05c-112">ATP-Richtlinien zum Schutz vor Phishing im Security & Compliance Center vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a05c-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="3a05c-113">Die grundlegenden Elemente einer ATP-Anti-Phishing-Richtlinie sind:</span><span class="sxs-lookup"><span data-stu-id="3a05c-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="3a05c-114">**Die Anti-Phishing-Richtlinie** : gibt die zu aktivierenden oder zu deaktivierenden Phishing-Schutzmaßnahmen sowie die Aktionen zum Anwenden von Optionen an.</span><span class="sxs-lookup"><span data-stu-id="3a05c-114">**The anti-phish policy** : Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="3a05c-115">**Die Anti-Phishing-Regel** : gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) für eine Anti-Phishing-Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="3a05c-115">**The anti-phish rule** : Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="3a05c-116">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für die ATP-Anti-Phishing im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="3a05c-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="3a05c-117">Wenn Sie eine Richtlinie erstellen, erstellen Sie tatsächlich eine Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie gleichzeitig mit dem gleichen Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="3a05c-117">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="3a05c-118">Wenn Sie eine Richtlinie ändern, ändern die Einstellungen im Zusammenhang mit dem Namen, der Priorität, den aktivierten oder deaktivierten und den Empfänger filtern die Anti-Phishing-Regel.</span><span class="sxs-lookup"><span data-stu-id="3a05c-118">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="3a05c-119">Alle anderen Einstellungen ändern die zugehörige Anti-Phishing-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="3a05c-119">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="3a05c-120">Wenn Sie eine Richtlinie entfernen, werden die Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie entfernt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-120">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="3a05c-121">In Exchange Online PowerShell verwalten Sie die Richtlinie und die Regel separat.</span><span class="sxs-lookup"><span data-stu-id="3a05c-121">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="3a05c-122">Weitere Informationen finden Sie weiter unten in diesem Thema im Abschnitt [Verwenden von Exchange Online PowerShell zum Konfigurieren von Richtlinien für die ATP-Anti-Phishing](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) .</span><span class="sxs-lookup"><span data-stu-id="3a05c-122">For more information, see the [Use Exchange Online PowerShell to configure ATP anti-phishing policies](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) section later in this topic.</span></span>

<span data-ttu-id="3a05c-123">Jede Office 365 ATP-Organisation verfügt über eine integrierte ATP-Richtlinie zum Schutz vor Phishing mit dem Namen "Office365 AntiPhishing default" mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="3a05c-123">Every Office 365 ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="3a05c-124">Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine Anti-Phishing-Regel (Empfängerfilter) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3a05c-124">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="3a05c-125">Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet).</span><span class="sxs-lookup"><span data-stu-id="3a05c-125">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="3a05c-126">Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität.</span><span class="sxs-lookup"><span data-stu-id="3a05c-126">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="3a05c-127">Die Richtlinie ist die Standardrichtlinie (die **IsDefault** -Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3a05c-127">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="3a05c-128">Um die Effektivität des Anti-Phishing-Schutzes zu verbessern, können Sie benutzerdefinierte ATP-Anti-Phishing-Richtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a05c-128">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3a05c-129">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="3a05c-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3a05c-130">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3a05c-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3a05c-131">Um direkt zur Seite " **ATP-AntiPhishing** " zu wechseln, verwenden Sie <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="3a05c-131">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="3a05c-132">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3a05c-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="3a05c-133">Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Verfahren in diesem Artikel ausführen können:</span><span class="sxs-lookup"><span data-stu-id="3a05c-133">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="3a05c-134">Zum Hinzufügen, ändern und Löschen von ATP-Richtlinien zum Schutz vor Phishing müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="3a05c-134">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="3a05c-135">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3a05c-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="3a05c-136">**Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="3a05c-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="3a05c-137">Für den schreibgeschützten Zugriff auf ATP-Richtlinien für die Anti-Phishing müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="3a05c-137">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="3a05c-138">**Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3a05c-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="3a05c-139">**Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="3a05c-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="3a05c-140">Unsere empfohlenen Einstellungen für Richtlinien für die ATP-Anti-Phishing finden Sie unter [ATP Anti-Phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="3a05c-140">For our recommended settings for ATP anti-phishing policies, see [ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="3a05c-141">Erlauben Sie bis zu 30 Minuten, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a05c-141">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="3a05c-142">Informationen dazu, wo Anti-Phishing-Richtlinien in der Filter Pipeline angewendet werden, finden Sie unter [Order and Ranges of Email Protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="3a05c-142">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="3a05c-143">Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für die ATP-Anti-Phishing</span><span class="sxs-lookup"><span data-stu-id="3a05c-143">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="3a05c-144">Durch das Erstellen einer benutzerdefinierten ATP-Richtlinie zum Schutz vor Phishing im Security & Compliance Center werden die Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie gleichzeitig mit dem gleichen Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-144">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="3a05c-145">Wenn Sie eine ATP-Anti-Phishing-Richtlinie erstellen, können Sie nur den Richtliniennamen, die Beschreibung und den Empfängerfilter angeben, der angibt, für wen die Richtlinie gilt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-145">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="3a05c-146">Nachdem Sie die Richtlinie erstellt haben, können Sie die Richtlinie ändern, um die Standardeinstellungen für AntiPhishing zu ändern oder zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-146">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="3a05c-147">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="3a05c-148">Klicken Sie auf der Seite **Anti-Phishing** auf **Erstellen** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-148">On the **Anti-phishing** page, click **Create** .</span></span>

3. <span data-ttu-id="3a05c-149">Der Assistent zum **Erstellen eines neuen Anti-Phishing-Richtlinien** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3a05c-149">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="3a05c-150">Konfigurieren Sie auf der Seite **Ihre Richtlinie benennen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="3a05c-150">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="3a05c-151">**Name** : Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="3a05c-151">**Name** : Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="3a05c-152">**Beschreibung** : Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="3a05c-152">**Description** : Enter an optional description for the policy.</span></span>

   <span data-ttu-id="3a05c-153">Klicken Sie nach Abschluss des Vorgangs auf **Weiter** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-153">When you're finished, click **Next** .</span></span>

4. <span data-ttu-id="3a05c-154">Identifizieren Sie auf der Seite **angewendet auf** , die angezeigt wird, die internen Empfänger, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a05c-154">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="3a05c-155">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="3a05c-155">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="3a05c-156">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="3a05c-156">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="3a05c-157">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="3a05c-157">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

   <span data-ttu-id="3a05c-158">Klicken Sie auf **Bedingung hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-158">Click **Add a condition** .</span></span> <span data-ttu-id="3a05c-159">Wählen Sie in der Dropdownliste, die angezeigt wird, eine Bedingung unter **angewendet, wenn** :</span><span class="sxs-lookup"><span data-stu-id="3a05c-159">In the dropdown that appears, select a condition under **Applied if** :</span></span>

   - <span data-ttu-id="3a05c-160">**Der Empfänger lautet** : gibt ein oder mehrere Postfächer, e-Mail-Benutzer oder e-Mail-Kontakte in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="3a05c-160">**The recipient is** : Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="3a05c-161">**Der Empfänger ist Mitglied von** : gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="3a05c-161">**The recipient is a member of** : Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="3a05c-162">**Die Empfängerdomäne lautet** : gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in der Organisation an.</span><span class="sxs-lookup"><span data-stu-id="3a05c-162">**The recipient domain is** : Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="3a05c-163">Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **der folgenden** Felder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-163">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="3a05c-164">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der zu markierende Werte durch.</span><span class="sxs-lookup"><span data-stu-id="3a05c-164">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="3a05c-165">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-165">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="3a05c-166">Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="3a05c-166">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="3a05c-167">Wenn Sie einzelne Einträge entfernen möchten **Remove** , klicken Sie auf Entfernen- ![ Symbol ](../../media/scc-remove-icon.png) für den Wert entfernen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-167">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="3a05c-168">Wenn Sie die gesamte Bedingung entfernen möchten **, klicken Sie** ![ in der Bedingung auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="3a05c-168">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="3a05c-169">Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen** , und wählen Sie einen verbleibenden Wert unter **angewendet bei** aus.</span><span class="sxs-lookup"><span data-stu-id="3a05c-169">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if** .</span></span>

   <span data-ttu-id="3a05c-170">Wenn Sie Ausnahmen hinzufügen möchten, klicken Sie auf **Bedingung hinzufügen** , und wählen Sie unter **außer if** eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="3a05c-170">To add exceptions, click **Add a condition** and select an exception under **Except if** .</span></span> <span data-ttu-id="3a05c-171">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-171">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="3a05c-172">Klicken Sie nach Abschluss des Vorgangs auf **Weiter** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-172">When you're finished, click **Next** .</span></span>

5. <span data-ttu-id="3a05c-173">Überprüfen Sie auf der angezeigten Seite **Ihre Einstellungen überprüfen** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-173">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="3a05c-174">Sie können auf jeder Einstellung auf **Bearbeiten** klicken, um Sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3a05c-174">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="3a05c-175">Wenn Sie fertig sind, klicken Sie auf **Diese Richtlinie erstellen** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-175">When you're finished, click **Create this policy** .</span></span>

6. <span data-ttu-id="3a05c-176">Klicken Sie im Bestätigungsdialogfeld, das angezeigt wird, auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-176">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="3a05c-177">Nachdem Sie die ATP-Anti-Phishing-Richtlinie mit diesen allgemeinen Richtlinieneinstellungen erstellt haben, konfigurieren Sie die Schutzeinstellungen in der Richtlinie mithilfe der Anweisungen im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-177">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="3a05c-178">Verwenden des Security & Compliance Center zum Ändern von ATP-Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3a05c-178">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="3a05c-179">Verwenden Sie die folgenden Verfahren, um ATP-AntiPhishing-Richtlinien zu ändern: eine neue Richtlinie, die Sie erstellt haben, oder vorhandene Richtlinien, die Sie bereits angepasst haben.</span><span class="sxs-lookup"><span data-stu-id="3a05c-179">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="3a05c-180">Wenn Sie noch nicht vorhanden sind, öffnen Sie das Security & Compliance Center, und wechseln Sie zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-180">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="3a05c-181">Wählen Sie die benutzerdefinierte ATP-Anti-Phishing-Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3a05c-181">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="3a05c-182">Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.</span><span class="sxs-lookup"><span data-stu-id="3a05c-182">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="3a05c-183">Das Flyout **Richtlinie \<name\> Bearbeiten** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-183">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="3a05c-184">Durch Klicken auf **Bearbeiten** in einem beliebigen Abschnitt erhalten Sie Zugriff auf die Einstellungen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-184">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="3a05c-185">Die folgenden Schritte werden in der Reihenfolge angezeigt, in der die Abschnitte dargestellt werden, Sie sind jedoch nicht sequenziell (Sie können die Abschnitte in beliebiger Reihenfolge auswählen und ändern).</span><span class="sxs-lookup"><span data-stu-id="3a05c-185">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="3a05c-186">Nachdem Sie in einem Abschnitt auf **Bearbeiten** klicken, werden die verfügbaren Einstellungen in einem Assistenten Format angezeigt, aber Sie können in beliebiger Reihenfolge auf die Seiten springen, und Sie können auf einer beliebigen Seite auf **Speichern** **(oder** **Abbrechen** oder Schließen schließen) klicken, um ![ ](../../media/scc-remove-icon.png) zur Seite **Richtlinie \<name\> Bearbeiten** zurückzukehren (Sie müssen nicht die letzte Seite des Assistenten zum Speichern oder verlassen besuchen).</span><span class="sxs-lookup"><span data-stu-id="3a05c-186">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="3a05c-187">**Richtlinieneinstellung** : Klicken Sie auf **Bearbeiten** , um dieselben Einstellungen zu ändern, die beim [Erstellen der Richtlinie](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) im vorherigen Abschnitt verfügbar waren:</span><span class="sxs-lookup"><span data-stu-id="3a05c-187">**Policy setting** : Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="3a05c-188">**Name**</span><span class="sxs-lookup"><span data-stu-id="3a05c-188">**Name**</span></span>
   - <span data-ttu-id="3a05c-189">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3a05c-189">**Description**</span></span>
   - <span data-ttu-id="3a05c-190">**Angewendet auf**</span><span class="sxs-lookup"><span data-stu-id="3a05c-190">**Applied to**</span></span>
   - <span data-ttu-id="3a05c-191">**Überprüfen der Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="3a05c-191">**Review your settings**</span></span>

   <span data-ttu-id="3a05c-192">Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-192">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="3a05c-193">**Identitätswechsel** : Klicken Sie auf **Bearbeiten** , um die geschützten Absender und geschützten Domänen in der Richtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3a05c-193">**Impersonation** : Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="3a05c-194">Diese Einstellungen sind eine Bedingung für die Richtlinie, die gefälschte Absender identifiziert, die in der von-Adresse eingehende Nachrichten (einzeln oder nach Domäne) suchen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-194">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="3a05c-195">Weitere Informationen finden Sie unter [Identitätswechseleinstellungen in ATP-Richtlinien zum Schutz vor Phishing](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="3a05c-195">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="3a05c-196">**Hinzufügen von Benutzern zu Protect** : der Standardwert ist **Off** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-196">**Add users to protect** : The default value is **Off** .</span></span> <span data-ttu-id="3a05c-197">Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein** , und klicken Sie dann auf die Schaltfläche **Benutzer hinzufügen** , die angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3a05c-197">To turn it on, slide the toggle to **On** , and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="3a05c-198">Konfigurieren Sie im angezeigten **Benutzer Flyout hinzufügen** die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="3a05c-198">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="3a05c-199">**E-Mail-Adresse** :</span><span class="sxs-lookup"><span data-stu-id="3a05c-199">**Email address** :</span></span>

        - <span data-ttu-id="3a05c-200">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der Benutzer aus, die Sie auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="3a05c-200">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="3a05c-201">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-201">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="3a05c-202">Wenn Sie einen Eintrag entfernen möchten **Remove** , klicken Sie auf Entfernen- ![ Symbol ](../../media/scc-remove-icon.png) für den Benutzer entfernen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-202">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="3a05c-203">**Name** : dieser Wert wird basierend auf der e-Mail-Adresse aufgefüllt, die Sie ausgewählt haben, aber Sie können ihn ändern.</span><span class="sxs-lookup"><span data-stu-id="3a05c-203">**Name** : This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="3a05c-204">Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-204">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="3a05c-205">Um einen vorhandenen Eintrag zu bearbeiten, wählen Sie den geschützten Benutzer in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="3a05c-205">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3a05c-206">Sie können maximal 60 Benutzer im Security & Compliance Center oder in PowerShell eingeben.</span><span class="sxs-lookup"><span data-stu-id="3a05c-206">You can enter a maximum of 60 users in the Security & Compliance Center or in PowerShell.</span></span>
       
   - <span data-ttu-id="3a05c-207">**Hinzufügen von Domänen zu Protect** : Konfigurieren Sie eine oder beide der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="3a05c-207">**Add domains to protect** : Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="3a05c-208">**Automatisches einschließen der Domänen, die ich besitze** : der Standardwert ist **Off** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-208">**Automatically include the domains I own** : The default value is **Off** .</span></span> <span data-ttu-id="3a05c-209">Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-209">To turn it on, slide the toggle to **On** .</span></span>
     - <span data-ttu-id="3a05c-210">**Benutzerdefinierte Domänen einschließen** : der Standardwert ist **Off** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-210">**Include custom domains** : The default value is **Off** .</span></span> <span data-ttu-id="3a05c-211">Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein** , und geben Sie im Feld **Domänen hinzufügen** den Domänennamen ein (beispielsweise contoso.com), drücken Sie die EINGABETASTE, und wiederholen Sie den Vorgang bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="3a05c-211">To turn it on, slide the toggle to **On** , and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3a05c-212">Sie können im Security & Compliance Center oder in PowerShell maximal 50 Domänen eingeben.</span><span class="sxs-lookup"><span data-stu-id="3a05c-212">You can enter a maximum of 50 domains in the Security & Compliance Center or in PowerShell.</span></span>

   - <span data-ttu-id="3a05c-213">**Aktionen** : Klicken Sie auf **Bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="3a05c-213">**Actions** : Click **Edit**</span></span>

     - <span data-ttu-id="3a05c-214">**Wenn e-Mail von einem imitierten Benutzer gesendet wird** : Konfigurieren Sie eine der folgenden Aktionen für Nachrichten, bei denen der gefälschte Absender einer der geschützten Benutzer ist, die Sie in **Add users to Protect** angegeben haben:</span><span class="sxs-lookup"><span data-stu-id="3a05c-214">**If email is sent by an impersonated user** : Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect** :</span></span>

       - <span data-ttu-id="3a05c-215">**Keine Aktion anwenden**</span><span class="sxs-lookup"><span data-stu-id="3a05c-215">**Don't apply any action**</span></span>
       - <span data-ttu-id="3a05c-216">**Weiterleiten von Nachrichten an andere e-Mail-Adressen**</span><span class="sxs-lookup"><span data-stu-id="3a05c-216">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="3a05c-217">**Nachricht in Junk-E-Mail-Ordner verschieben**</span><span class="sxs-lookup"><span data-stu-id="3a05c-217">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="3a05c-218">**Nachricht isolieren**</span><span class="sxs-lookup"><span data-stu-id="3a05c-218">**Quarantine the message**</span></span>
       - <span data-ttu-id="3a05c-219">**Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**</span><span class="sxs-lookup"><span data-stu-id="3a05c-219">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="3a05c-220">**Löschen der Nachricht vor der Zustellung**</span><span class="sxs-lookup"><span data-stu-id="3a05c-220">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="3a05c-221">**Wenn e-Mail von einer imitierten Domäne gesendet wird** : Konfigurieren Sie eine der folgenden Aktionen für Nachrichten, bei denen sich der gefälschte Absender in einer der geschützten Domänen befindet, die Sie in **Add Domains to Protect** angegeben haben:</span><span class="sxs-lookup"><span data-stu-id="3a05c-221">**If email is sent by an impersonated domain** : Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect** :</span></span>

     - <span data-ttu-id="3a05c-222">**Keine Aktion anwenden**</span><span class="sxs-lookup"><span data-stu-id="3a05c-222">**Don't apply any action**</span></span>
     - <span data-ttu-id="3a05c-223">**Weiterleiten von Nachrichten an andere e-Mail-Adressen**</span><span class="sxs-lookup"><span data-stu-id="3a05c-223">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="3a05c-224">**Nachricht in Junk-E-Mail-Ordner verschieben**</span><span class="sxs-lookup"><span data-stu-id="3a05c-224">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="3a05c-225">**Nachricht isolieren**</span><span class="sxs-lookup"><span data-stu-id="3a05c-225">**Quarantine the message**</span></span>
     - <span data-ttu-id="3a05c-226">**Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**</span><span class="sxs-lookup"><span data-stu-id="3a05c-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="3a05c-227">**Löschen der Nachricht vor der Zustellung**</span><span class="sxs-lookup"><span data-stu-id="3a05c-227">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="3a05c-228">Klicken Sie auf **Identitätswechsel-Sicherheitstipps einschalten** , und konfigurieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="3a05c-228">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="3a05c-229">**Tipp für imitierte Benutzer anzeigen** : der Standardwert ist **Off** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-229">**Show tip for impersonated users** : The default value is **Off** .</span></span> <span data-ttu-id="3a05c-230">Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-230">To turn it on, slide the toggle to **On** .</span></span>
     - <span data-ttu-id="3a05c-231">**Tipp für imitierte Domänen anzeigen** : der Standardwert ist **Off** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-231">**Show tip for impersonated domains** : The default value is **Off** .</span></span> <span data-ttu-id="3a05c-232">Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-232">To turn it on, slide the toggle to **On** .</span></span>
     - <span data-ttu-id="3a05c-233">**Tipp für ungewöhnliche Zeichen anzeigen** : der Standardwert ist **Off** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-233">**Show tip for unusual characters** : The default value is **Off** .</span></span> <span data-ttu-id="3a05c-234">Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-234">To turn it on, slide the toggle to **On** .</span></span>

     <span data-ttu-id="3a05c-235">Klicken Sie nach Abschluss des Vorgangs auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-235">When you're finished, click **Save** .</span></span>

   - <span data-ttu-id="3a05c-236">**Post Fach Intelligenz** :</span><span class="sxs-lookup"><span data-stu-id="3a05c-236">**Mailbox intelligence** :</span></span>

     - <span data-ttu-id="3a05c-237">**Mailbox Intelligence aktivieren?** : der Standardwert ist **on** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-237">**Enable mailbox intelligence?** : The default value is **On** .</span></span> <span data-ttu-id="3a05c-238">Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-238">To turn it off, slide the toggle to **Off** .</span></span>

     - <span data-ttu-id="3a05c-239">**Aktivieren des Post Fach informationsbasierten Identitätswechsel Schutzes?** : Diese Einstellung ist nur verfügbar, wenn **Mailbox Intelligence aktivieren** aktiviert **ist.**</span><span class="sxs-lookup"><span data-stu-id="3a05c-239">**Enable mailbox intelligence based impersonation protection?** : This setting is only available if **Enable mailbox intelligence?** is **On** .</span></span>

       <span data-ttu-id="3a05c-240">**Wenn e-Mails von einem imitierten Benutzer gesendet** werden, können Sie eine der folgenden Aktionen für Nachrichten, die nicht die Post Fach Intelligenz ausführen (dieselben Aktionen, die für geschützte Benutzer und geschützte Domänen zur Verfügung stehen) angeben:</span><span class="sxs-lookup"><span data-stu-id="3a05c-240">In **If email is sent by an impersonated user** , you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="3a05c-241">**Keine Aktion anwenden**</span><span class="sxs-lookup"><span data-stu-id="3a05c-241">**Don't apply any action**</span></span>
       - <span data-ttu-id="3a05c-242">**Weiterleiten von Nachrichten an andere e-Mail-Adressen**</span><span class="sxs-lookup"><span data-stu-id="3a05c-242">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="3a05c-243">**Nachricht in Junk-E-Mail-Ordner verschieben**</span><span class="sxs-lookup"><span data-stu-id="3a05c-243">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="3a05c-244">**Nachricht isolieren**</span><span class="sxs-lookup"><span data-stu-id="3a05c-244">**Quarantine the message**</span></span>
       - <span data-ttu-id="3a05c-245">**Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**</span><span class="sxs-lookup"><span data-stu-id="3a05c-245">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="3a05c-246">**Löschen der Nachricht vor der Zustellung**</span><span class="sxs-lookup"><span data-stu-id="3a05c-246">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="3a05c-247">**Hinzufügen von vertrauenswürdigen Absendern und Domänen** : Angeben von Ausnahmen für die Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="3a05c-247">**Add trusted senders and domains** : Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="3a05c-248">**Vertrauenswürdige Absender** :</span><span class="sxs-lookup"><span data-stu-id="3a05c-248">**Trusted senders** :</span></span>

       - <span data-ttu-id="3a05c-249">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der Benutzer aus, die Sie auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="3a05c-249">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="3a05c-250">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-250">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="3a05c-251">Wenn Sie einen Eintrag entfernen möchten **Remove** , klicken Sie auf Entfernen- ![ Symbol ](../../media/scc-remove-icon.png) für den Benutzer entfernen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-251">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="3a05c-252">**Vertrauenswürdige Domänen** : Geben Sie den Domänennamen ein (beispielsweise contoso.com), drücken Sie die EINGABETASTE, und wiederholen Sie den Vorgang bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="3a05c-252">**Trusted domains** : Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="3a05c-253">**Überprüfen Sie Ihre Einstellungen** : anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-253">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="3a05c-254">Sie können in jedem Abschnitt auf **Bearbeiten** klicken, um zurück zur entsprechenden Seite zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="3a05c-254">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="3a05c-255">Sie können die **folgenden Einstellungen direkt auf dieser** Seite aktivieren oder **Deaktivieren** :</span><span class="sxs-lookup"><span data-stu-id="3a05c-255">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="3a05c-256">**Geschützte Benutzer**</span><span class="sxs-lookup"><span data-stu-id="3a05c-256">**Protected users**</span></span>
       - <span data-ttu-id="3a05c-257">**Geschützte Domänen** \> **Domänen einschließen, die ich besitze**</span><span class="sxs-lookup"><span data-stu-id="3a05c-257">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="3a05c-258">**Geschützte Domänen** \> **Geschützte Domänen** (benutzerdefinierte Domänen)</span><span class="sxs-lookup"><span data-stu-id="3a05c-258">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="3a05c-259">**Mailbox Intelligence**</span><span class="sxs-lookup"><span data-stu-id="3a05c-259">**Mailbox intelligence**</span></span>

   <span data-ttu-id="3a05c-260">Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-260">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="3a05c-261">**Spoof** : Klicken Sie auf **Bearbeiten** , um Spoof Intelligence ein-oder auszuschalten, die nicht authentifizierte Absender Identifikation in Outlook ein-oder auszuschalten und die Aktion so zu konfigurieren, dass Sie auf Nachrichten von blockierten gefälschten Absendern angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a05c-261">**Spoof** : Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="3a05c-262">Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="3a05c-262">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="3a05c-263">Beachten Sie, dass diese Einstellungen auch in Anti-Phishing-Richtlinien in EoP verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3a05c-263">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="3a05c-264">**Spoofing-Filtereinstellungen** : der Standardwert ist " **on** ", und es wird empfohlen, dass Sie die Einstellung aktiviert lassen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-264">**Spoofing filter settings** : The default value is **On** , and we recommend that you leave it on.</span></span> <span data-ttu-id="3a05c-265">Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-265">To turn it off, slide the toggle to **Off** .</span></span> <span data-ttu-id="3a05c-266">Weitere Informationen finden Sie unter [configure Spoof Intelligence in EoP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="3a05c-266">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="3a05c-267">Sie müssen den Schutz vor Spoofing nicht deaktivieren, wenn Ihr MX-Eintrag nicht auf Microsoft 365 verweist; Stattdessen aktivieren Sie die erweiterte Filterung für Connectors.</span><span class="sxs-lookup"><span data-stu-id="3a05c-267">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="3a05c-268">Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="3a05c-268">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="3a05c-269">Nicht **authentifizierte Absender Funktion aktivieren** : der Standardwert ist **on** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-269">**Enable Unauthenticated Sender feature** : The default value is **On** .</span></span> <span data-ttu-id="3a05c-270">Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-270">To turn it off, slide the toggle to **Off** .</span></span>

   - <span data-ttu-id="3a05c-271">**Actions: geben** Sie die Aktion an, die für Nachrichten ausgeführt werden soll, die Spoof Intelligence nicht ausführen:</span><span class="sxs-lookup"><span data-stu-id="3a05c-271">**Actions** : Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="3a05c-272">**Wenn e-Mails von Benutzern gesendet werden, die Ihre Domäne nicht spoofen dürfen** :</span><span class="sxs-lookup"><span data-stu-id="3a05c-272">**If email is sent by someone who's not allowed to spoof your domain** :</span></span>

     - <span data-ttu-id="3a05c-273">**Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern**</span><span class="sxs-lookup"><span data-stu-id="3a05c-273">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="3a05c-274">**Nachricht isolieren**</span><span class="sxs-lookup"><span data-stu-id="3a05c-274">**Quarantine the message**</span></span>

   - <span data-ttu-id="3a05c-275">**Überprüfen Sie Ihre Einstellungen** : anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-275">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="3a05c-276">Sie können in jedem Abschnitt auf **Bearbeiten** klicken, um zurück zur entsprechenden Seite zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="3a05c-276">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="3a05c-277">Sie können die **folgenden Einstellungen direkt auf dieser** Seite aktivieren oder **Deaktivieren** :</span><span class="sxs-lookup"><span data-stu-id="3a05c-277">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="3a05c-278">**Aktivieren von Schutz vor Spoofing**</span><span class="sxs-lookup"><span data-stu-id="3a05c-278">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="3a05c-279">**Nicht authentifizierte Absender Funktion aktivieren**</span><span class="sxs-lookup"><span data-stu-id="3a05c-279">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="3a05c-280">Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-280">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="3a05c-281">**Erweiterte Einstellungen** : Klicken Sie auf **Bearbeiten** , um die erweiterten Phishing-Schwellenwerte zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3a05c-281">**Advanced settings** : Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="3a05c-282">Weitere Informationen finden Sie unter [Advanced Phishing Thresholds in ATP Anti-Phishing Policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="3a05c-282">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="3a05c-283">**Erweiterte Phishing-Schwellen** Werte: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="3a05c-283">**Advanced phishing thresholds** : Select one of the following values:</span></span>

   - <span data-ttu-id="3a05c-284">**1-Standard** (Dies ist der Standardwert.)</span><span class="sxs-lookup"><span data-stu-id="3a05c-284">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="3a05c-285">**2-aggressiv**</span><span class="sxs-lookup"><span data-stu-id="3a05c-285">**2 - Aggressive**</span></span>
   - <span data-ttu-id="3a05c-286">**3-aggressiver**</span><span class="sxs-lookup"><span data-stu-id="3a05c-286">**3 - More aggressive**</span></span>
   - <span data-ttu-id="3a05c-287">**4-aggressiv**</span><span class="sxs-lookup"><span data-stu-id="3a05c-287">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="3a05c-288">**Überprüfen Sie Ihre Einstellungen** : Klicken Sie auf **Bearbeiten** , um zurück zur Seite **erweiterte Phishing-Schwellenwerte** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="3a05c-288">**Review your settings** : Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="3a05c-289">Wenn Sie fertig sind, klicken Sie auf einer der Seiten auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-289">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="3a05c-290">Überprüfen Sie die Einstellungen auf der Seite **Richtlinie \<Name\> Bearbeiten** , und klicken Sie dann auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-290">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close** .</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="3a05c-291">Verwenden Sie das Security & Compliance Center, um die standardmäßige ATP-Anti-Phishing-Richtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3a05c-291">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="3a05c-292">Die standardmäßige ATP-Anti-Phishing-Richtlinie heißt Office365 AntiPhishing default und wird nicht in der Liste der Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-292">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="3a05c-293">Führen Sie die folgenden Schritte aus, um die standardmäßige ATP-Anti-Phishing-Richtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="3a05c-293">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="3a05c-294">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-294">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="3a05c-295">Klicken Sie auf der Seite **Anti-Phishing** auf **Standardrichtlinie** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-295">On the **Anti-phishing** page, click **Default policy** .</span></span>

3. <span data-ttu-id="3a05c-296">Die **Standardseite Ihre Richtlinie Office365 AntiPhishing bearbeiten** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-296">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="3a05c-297">Die folgenden Abschnitte sind verfügbar, die identische Einstellungen für beim [Ändern einer benutzerdefinierten Richtlinie](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)enthalten:</span><span class="sxs-lookup"><span data-stu-id="3a05c-297">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="3a05c-298">**Impersonation**</span><span class="sxs-lookup"><span data-stu-id="3a05c-298">**Impersonation**</span></span>
   - <span data-ttu-id="3a05c-299">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="3a05c-299">**Spoof**</span></span>
   - <span data-ttu-id="3a05c-300">**Erweiterte Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="3a05c-300">**Advanced settings**</span></span>

   <span data-ttu-id="3a05c-301">Die folgenden Einstellungen sind nicht verfügbar, wenn Sie die Standardrichtlinie ändern:</span><span class="sxs-lookup"><span data-stu-id="3a05c-301">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="3a05c-302">Sie können den Abschnitt mit den **Richtlinieneinstellungen** und die Werte anzeigen, es gibt jedoch keinen Link **Bearbeiten** , sodass Sie die Einstellungen nicht ändern können (Richtlinienname, Beschreibung und für wen die Richtlinie gilt (gilt für alle Empfänger)).</span><span class="sxs-lookup"><span data-stu-id="3a05c-302">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="3a05c-303">Die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3a05c-303">You can't delete the default policy.</span></span>
   - <span data-ttu-id="3a05c-304">Sie können die Priorität der Standardrichtlinie nicht ändern (Sie wird immer zuletzt angewendet).</span><span class="sxs-lookup"><span data-stu-id="3a05c-304">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="3a05c-305">Überprüfen Sie auf der **Standardseite Richtlinie Office365 bearbeiten** die Einstellungen, und klicken Sie dann auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-305">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close** .</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="3a05c-306">Aktivieren oder Deaktivieren von benutzerdefinierten ATP-Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3a05c-306">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="3a05c-307">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-307">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="3a05c-308">Beachten Sie den Wert in der Spalte **Status** :</span><span class="sxs-lookup"><span data-stu-id="3a05c-308">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="3a05c-309">Schieben Sie die Umschaltfläche auf **aus** , um die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3a05c-309">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="3a05c-310">Schieben Sie die Umschaltfläche in **ein** , um die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3a05c-310">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="3a05c-311">Sie können die standardmäßige Anti-Phishing-Richtlinie nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3a05c-311">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="3a05c-312">Festlegen der Priorität von benutzerdefinierten ATP-Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3a05c-312">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="3a05c-313">Standardmäßig erhalten Richtlinien für ATP-AntiPhishing eine Priorität, die auf der Reihenfolge basiert, in der Sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="3a05c-313">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="3a05c-314">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="3a05c-314">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="3a05c-315">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="3a05c-315">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="3a05c-316">Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="3a05c-316">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="3a05c-317">Benutzerdefinierte ATP-Anti-Phishing-Richtlinien werden in der Reihenfolge angezeigt, in der Sie verarbeitet werden (die erste Richtlinie hat den **Prioritäts** Wert 0).</span><span class="sxs-lookup"><span data-stu-id="3a05c-317">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="3a05c-318">Die standardmäßige Anti-Phishing-Richtlinie mit dem Namen "Office365 AntiPhishing default" weist den benutzerdefinierten Prioritätswert als " **niedrigste** " auf und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3a05c-318">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest** , and you can't change it.</span></span>

 <span data-ttu-id="3a05c-319">**Hinweis** : im Security & Compliance Center können Sie die Priorität der ATP-Anti-Phishing-Richtlinie nur ändern, nachdem Sie Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3a05c-319">**Note** : In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="3a05c-320">In PowerShell können Sie die Standardpriorität außer Kraft setzen, wenn Sie die Anti-Phishing-Regel erstellen (die sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="3a05c-320">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="3a05c-321">Um die Priorität einer Richtlinie zu ändern, klicken Sie in den Eigenschaften der Richtlinie auf **Priorität verbessern** oder **Priorität verringern** (die **Prioritäts** Nummer im Security & Compliance Center kann nicht direkt geändert werden).</span><span class="sxs-lookup"><span data-stu-id="3a05c-321">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="3a05c-322">Das Ändern der Priorität einer Richtlinie ist nur dann sinnvoll, wenn Sie über mehrere Richtlinien verfügen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-322">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="3a05c-323">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-323">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="3a05c-324">Wählen Sie die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3a05c-324">Select the policy that you want to modify.</span></span> <span data-ttu-id="3a05c-325">Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.</span><span class="sxs-lookup"><span data-stu-id="3a05c-325">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="3a05c-326">Das Flyout **Richtlinie \<name\> Bearbeiten** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-326">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="3a05c-327">Die benutzerdefinierte ATP-Anti-Phishing-Richtlinie mit dem **Prioritäts** Wert **0** hat nur die Schaltfläche **Priorität verringern** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3a05c-327">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="3a05c-328">Die benutzerdefinierte ATP-Anti-Phishing-Richtlinie mit dem niedrigsten **Prioritäts** Wert (beispielsweise **3** ) hat nur die Schaltfläche " **Priorität verlängern** " zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3a05c-328">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3** ) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="3a05c-329">Wenn Sie über drei oder mehr benutzerdefinierte Anti-Phishing-Richtlinien verfügen, stehen für Richtlinien zwischen den Werten der höchsten und der niedrigsten Priorität **sowohl die Prioritätsschaltflächen "Priorität"** als auch " **Priorität verringern** " zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3a05c-329">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="3a05c-330">Klicken Sie auf Priorität Verb **Essern** oder **Priorität verringern** , um den **Prioritäts** Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3a05c-330">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="3a05c-331">Klicken Sie nach Abschluss des Vorgangs auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-331">When you're finished, click **Close** .</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="3a05c-332">Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien für die ATP-Anti-Phishing</span><span class="sxs-lookup"><span data-stu-id="3a05c-332">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="3a05c-333">Im Security & Compliance Center und wechseln Sie zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-333">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="3a05c-334">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3a05c-334">Do one of the following steps:</span></span>

   - <span data-ttu-id="3a05c-335">Wählen Sie eine benutzerdefinierte ATP-Anti-Phishing-Richtlinie aus, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="3a05c-335">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="3a05c-336">Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.</span><span class="sxs-lookup"><span data-stu-id="3a05c-336">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="3a05c-337">Klicken Sie auf **Standardrichtlinie** , um die standardmäßige Anti-Phishing-Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-337">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="3a05c-338">Das Flyout zum **Bearbeiten \<name\> Ihrer Richtlinie** wird angezeigt, in dem Sie die Einstellungen und Werte anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="3a05c-338">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="3a05c-339">Verwenden des Security & Compliance Center zum Entfernen von ATP-Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3a05c-339">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="3a05c-340">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-340">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="3a05c-341">Wählen Sie die Richtlinie aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="3a05c-341">Select the policy that you want to remove.</span></span> <span data-ttu-id="3a05c-342">Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.</span><span class="sxs-lookup"><span data-stu-id="3a05c-342">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="3a05c-343">Klicken Sie im daraufhin angezeigten Dialogfeld **Richtlinie \<name\> Bearbeiten** auf **Richtlinie löschen** , und klicken Sie dann im angezeigten Warndialogfeld auf **Ja** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-343">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy** , and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="3a05c-344">Die Standardrichtlinie kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="3a05c-344">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="3a05c-345">Konfigurieren von Richtlinien für die ATP-Anti-Phishing mithilfe Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a05c-345">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

<span data-ttu-id="3a05c-346">Wie bereits beschrieben, besteht eine Anti-Spam-Richtlinie für ATP aus einer Anti-Phishing-Richtlinie und einer Anti-Phishing-Regel.</span><span class="sxs-lookup"><span data-stu-id="3a05c-346">As previously described, an ATP anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="3a05c-347">In Exchange Online PowerShell ist der Unterschied zwischen Anti-Phishing-Richtlinien und Anti-Phishing-Regeln offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="3a05c-347">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="3a05c-348">Sie können Anti-Phishing-Richtlinien mithilfe der **\* -AntiPhishPolicy-** Cmdlets verwalten und Anti-Phishing-Regeln mithilfe der Cmdlets **\* -AntiPhishRule** verwalten.</span><span class="sxs-lookup"><span data-stu-id="3a05c-348">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="3a05c-349">In PowerShell erstellen Sie zuerst die Anti-Phishing-Richtlinie, dann erstellen Sie die Anti-Phishing-Regel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a05c-349">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="3a05c-350">In PowerShell ändern Sie die Einstellungen in der Anti-Phishing-Richtlinie und in der Anti-Phishing-Regel separat.</span><span class="sxs-lookup"><span data-stu-id="3a05c-350">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="3a05c-351">Wenn Sie eine Anti-Phishing-Richtlinie aus PowerShell entfernen, wird die entsprechende Anti-Phishing-Regel nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-351">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="3a05c-352">Verwenden von PowerShell zum Erstellen von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3a05c-352">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="3a05c-353">Das Erstellen einer Anti-Phishing-Richtlinie in PowerShell ist ein zweistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="3a05c-353">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="3a05c-354">Erstellen Sie die Anti-Phishing-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="3a05c-354">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="3a05c-355">Erstellen Sie die Anti-Phishing-Regel, die die Anti-Phishing-Richtlinie angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a05c-355">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="3a05c-356">**Hinweise** :</span><span class="sxs-lookup"><span data-stu-id="3a05c-356">**Notes** :</span></span>

- <span data-ttu-id="3a05c-357">Sie können eine neue Anti-Phishing-Regel erstellen und ihr eine vorhandene, nicht zugeordnete Anti-Phishing-Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-357">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="3a05c-358">Eine Anti-Phishing-Regel kann nicht mehr als einer Anti-Phishing-Richtlinie zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="3a05c-358">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="3a05c-359">Sie können die folgenden Einstellungen für neue Anti-Phishing-Richtlinien in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Security & Compliance Center verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="3a05c-359">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="3a05c-360">Erstellen Sie die neue Richtlinie als deaktiviert ( _aktiviert_ im `$false` Cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="3a05c-360">Create the new policy as disabled ( _Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="3a05c-361">Legen Sie die Priorität der Richtlinie während der Erstellung ( _Priorität_ _\<Number\>_ ) für das Cmdlet **New-AntiPhishRule** fest).</span><span class="sxs-lookup"><span data-stu-id="3a05c-361">Set the priority of the policy during creation ( _Priority_ _\<Number\>_ ) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="3a05c-362">Eine neue Anti-Phishing-Richtlinie, die Sie in PowerShell erstellen, ist erst im Security & Compliance Center sichtbar, wenn Sie die Richtlinie einer Anti-Phishing-Regel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3a05c-362">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="3a05c-363">Schritt 1: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="3a05c-363">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="3a05c-364">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Richtlinie zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="3a05c-364">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="3a05c-365">In diesem Beispiel wird die Anti-Phishing-Richtlinie mit dem Namen "Research Quarantine" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="3a05c-365">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="3a05c-366">Die Richtlinie ist aktiviert (der Parameter _Enabled_ wird nicht verwendet, und der Standardwert ist `$true` ).</span><span class="sxs-lookup"><span data-stu-id="3a05c-366">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="3a05c-367">Die Beschreibung lautet: Abteilungs Richtlinie für Forschung.</span><span class="sxs-lookup"><span data-stu-id="3a05c-367">The description is: Research department policy.</span></span>
- <span data-ttu-id="3a05c-368">Aktiviert den Schutz von Organisationsdomänen für alle akzeptierten Domänen und den Schutz von Zieldomänen für fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="3a05c-368">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="3a05c-369">Gibt Mai Fujito (mfujito@fabrikam.com) als Benutzer an, der vor Identitätswechsel geschützt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a05c-369">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="3a05c-370">Aktiviert Post Fach Intelligenz.</span><span class="sxs-lookup"><span data-stu-id="3a05c-370">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="3a05c-371">Aktiviert den Nachrichtenschutz für Postfächer und gibt die Quarantäneaktion an.</span><span class="sxs-lookup"><span data-stu-id="3a05c-371">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="3a05c-372">Aktiviert Sicherheitstipps.</span><span class="sxs-lookup"><span data-stu-id="3a05c-372">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="3a05c-373">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="3a05c-373">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="3a05c-374">Schritt 2: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Regel</span><span class="sxs-lookup"><span data-stu-id="3a05c-374">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="3a05c-375">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="3a05c-375">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="3a05c-376">In diesem Beispiel wird eine Anti-Phishing-Regel namens "Research Department" mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="3a05c-376">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="3a05c-377">Die Regel ist der Anti-Phishing-Richtlinie "Research Quarantine" zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="3a05c-377">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="3a05c-378">Die Regel gilt für Mitglieder der Gruppe „Research Department“.</span><span class="sxs-lookup"><span data-stu-id="3a05c-378">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="3a05c-379">Da wir den _Priority_ -Parameter nicht verwenden, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a05c-379">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="3a05c-380">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="3a05c-380">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="3a05c-381">Verwenden von PowerShell zum Anzeigen von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3a05c-381">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="3a05c-382">Verwenden Sie die folgende Syntax, um vorhandene Anti-Phishing-Richtlinien anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="3a05c-382">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="3a05c-383">In diesem Beispiel wird eine Zusammenfassungsliste aller Anti-Phishing-Richtlinien zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3a05c-383">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="3a05c-384">In diesem Beispiel werden alle Eigenschaftswerte für die Anti-Phishing-Richtlinie "Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3a05c-384">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="3a05c-385">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="3a05c-385">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="3a05c-386">Verwenden von PowerShell zum Anzeigen von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="3a05c-386">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="3a05c-387">Verwenden Sie die folgende Syntax, um vorhandene Anti-Phishing-Regeln anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="3a05c-387">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="3a05c-388">In diesem Beispiel wird eine Zusammenfassungsliste aller Anti-Phishing-Regeln zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3a05c-388">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="3a05c-389">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="3a05c-389">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="3a05c-390">In diesem Beispiel werden alle Eigenschaftswerte für die Anti-Phishing-Regel namens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3a05c-390">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="3a05c-391">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="3a05c-391">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="3a05c-392">Verwenden von PowerShell zum Ändern von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3a05c-392">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="3a05c-393">Anders als die folgenden Elemente sind die gleichen Einstellungen verfügbar, wenn Sie eine Anti-Phishing-Richtlinie in PowerShell wie beim Erstellen der Richtlinie wie im Abschnitt [Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie zu AntiPhishing-Richt](#step-1-use-powershell-to-create-an-anti-phish-policy) Linien weiter oben in diesem Thema ändern.</span><span class="sxs-lookup"><span data-stu-id="3a05c-393">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="3a05c-394">Der _MakeDefault_ -Schalter, der die angegebene Richtlinie in die Standardrichtlinie umwandelt (gilt für alle, immer **niedrigste** Priorität, und Sie können Sie nicht löschen) ist nur verfügbar, wenn Sie eine Anti-Phishing-Richtlinie in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="3a05c-394">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="3a05c-395">Sie können keine Anti-Phishing-Richtlinie umbenennen (das Cmdlet " **AntiPhishPolicy** " hat keinen Parameter " _Name_ ").</span><span class="sxs-lookup"><span data-stu-id="3a05c-395">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="3a05c-396">Wenn Sie eine Richtlinie zum Schutz vor Phishing im Security & Compliance Center umbenennen, benennen Sie die Anti-Phishing- _Regel_ nur um.</span><span class="sxs-lookup"><span data-stu-id="3a05c-396">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_ .</span></span>

<span data-ttu-id="3a05c-397">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Richtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="3a05c-397">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="3a05c-398">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="3a05c-398">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="3a05c-399">Verwenden von PowerShell zum Ändern von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="3a05c-399">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="3a05c-400">Die einzige Einstellung, die beim Ändern einer Anti-Phishing-Regel in PowerShell nicht verfügbar ist, ist der Parameter _Enabled_ , mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="3a05c-400">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="3a05c-401">Informationen zum Aktivieren oder Deaktivieren vorhandener Anti-Phishing-Regeln finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-401">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="3a05c-402">Andernfalls stehen keine zusätzlichen Einstellungen zur Verfügung, wenn Sie eine Anti-Phishing-Regel in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="3a05c-402">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="3a05c-403">Die gleichen Einstellungen sind verfügbar, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Regel](#step-2-use-powershell-to-create-an-anti-phish-rule) weiter oben in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3a05c-403">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="3a05c-404">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel zu ändern:</span><span class="sxs-lookup"><span data-stu-id="3a05c-404">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="3a05c-405">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="3a05c-405">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="3a05c-406">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="3a05c-406">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="3a05c-407">Durch das Aktivieren oder Deaktivieren einer Anti-Phishing-Regel in PowerShell wird die gesamte Richtlinie zum Schutz vor Phishing aktiviert oder deaktiviert (die Anti-Phishing-Regel und die zugewiesene Anti-Phishing-Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="3a05c-407">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="3a05c-408">Sie können die standardmäßige Anti-Phishing-Richtlinie nicht aktivieren oder deaktivieren (Sie wird immer auf alle Empfänger angewendet).</span><span class="sxs-lookup"><span data-stu-id="3a05c-408">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="3a05c-409">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="3a05c-409">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="3a05c-410">In diesem Beispiel wird die Anti-Phishing-Regel namens "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3a05c-410">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3a05c-411">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3a05c-411">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3a05c-412">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) und [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="3a05c-412">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="3a05c-413">Verwenden von PowerShell zum Festlegen der Priorität von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="3a05c-413">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="3a05c-414">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="3a05c-414">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="3a05c-415">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="3a05c-415">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="3a05c-416">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a05c-416">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="3a05c-417">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="3a05c-417">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="3a05c-418">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="3a05c-418">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="3a05c-419">Verwenden Sie die folgende Syntax, um die Priorität einer Anti-Phishing-Regel in PowerShell festzulegen:</span><span class="sxs-lookup"><span data-stu-id="3a05c-419">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="3a05c-p144">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="3a05c-p144">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="3a05c-422">**Hinweise** :</span><span class="sxs-lookup"><span data-stu-id="3a05c-422">**Notes** :</span></span>

- <span data-ttu-id="3a05c-423">Wenn Sie die Priorität einer neuen Regel beim Erstellen festlegen möchten, verwenden Sie stattdessen den Parameter _Priority_ für das Cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-423">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="3a05c-424">Die standardmäßige Anti-Phishing-Richtlinie verfügt nicht über eine entsprechende Anti-Phishing-Regel, und Sie hat immer den Wert unveränderbare Priorität **niedrigste** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-424">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest** .</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="3a05c-425">Verwenden von PowerShell zum Entfernen von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3a05c-425">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="3a05c-426">Wenn Sie PowerShell zum Entfernen einer Anti-Phishing-Richtlinie verwenden, wird die entsprechende Anti-Phishing-Regel nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-426">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="3a05c-427">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Richtlinie in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="3a05c-427">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="3a05c-428">In diesem Beispiel wird die Anti-Phishing-Richtlinie namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-428">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="3a05c-429">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="3a05c-429">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="3a05c-430">Verwenden von PowerShell zum Entfernen von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="3a05c-430">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="3a05c-431">Wenn Sie PowerShell zum Entfernen einer Anti-Phishing-Regel verwenden, wird die entsprechende Anti-Phishing-Richtlinie nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-431">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="3a05c-432">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="3a05c-432">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="3a05c-433">In diesem Beispiel wird die Anti-Phishing-Regel namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="3a05c-433">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3a05c-434">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="3a05c-434">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="3a05c-435">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="3a05c-435">How do you know these procedures worked?</span></span>

<span data-ttu-id="3a05c-436">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie die Richtlinien für ATP-Phishing erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="3a05c-436">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="3a05c-437">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing** .</span><span class="sxs-lookup"><span data-stu-id="3a05c-437">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span> <span data-ttu-id="3a05c-438">Überprüfen Sie die Liste der Richtlinien, deren **Status** Werte und deren **Prioritäts** Werte.</span><span class="sxs-lookup"><span data-stu-id="3a05c-438">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="3a05c-439">Um weitere Details anzuzeigen, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3a05c-439">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="3a05c-440">Wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="3a05c-440">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="3a05c-441">Klicken Sie auf **Standardrichtlinie** , und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="3a05c-441">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="3a05c-442">Ersetzen Sie in Exchange Online PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, und führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="3a05c-442">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
