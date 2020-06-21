---
title: Konfigurieren von Anti-Phishing-Richtlinien in EoP
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
description: Administratoren können erfahren, wie Sie die AntiPhishing-Richtlinien erstellen, ändern und löschen, die in Exchange Online Protection (EoP)-Organisationen mit oder ohne Exchange Online Postfächern verfügbar sind.
ms.openlocfilehash: b6b95515ad44a65dbdd8a7516d8e6c8b2a386450
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726773"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="3b6f0-103">Konfigurieren von Anti-Phishing-Richtlinien in EoP</span><span class="sxs-lookup"><span data-stu-id="3b6f0-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="3b6f0-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer gibt es eine standardmäßige Anti-Phishing-Richtlinie, die eine beschränkte Anzahl von Antispoofing-Funktionen enthält, die standardmäßig aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="3b6f0-105">Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="3b6f0-106">Administratoren können die standardmäßige Anti-Phishing-Richtlinie anzeigen, bearbeiten und konfigurieren (jedoch nicht löschen).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="3b6f0-107">Um eine höhere Granularität zu erzielen, können Sie auch benutzerdefinierte Anti-Phishing-Richtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="3b6f0-108">Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="3b6f0-109">Organisationen mit Exchange Online Postfächern können Anti-Phishing-Richtlinien im Security & Compliance Center oder in Exchange Online PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="3b6f0-110">Eigenständige EoP-Organisationen können nur das Security & Compliance Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="3b6f0-111">Informationen zum Erstellen und Ändern der erweiterten ATP-Anti-Phishing-Richtlinien, die in Office 365 Advanced Threat Protection (Office 365 ATP) zur Verfügung stehen, finden Sie unter [configure ATP Anti-Phishing Policies](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="3b6f0-112">Anti-Phishing-Richtlinien im Security & Compliance Center vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b6f0-112">Anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="3b6f0-113">Die grundlegenden Elemente einer Anti-Phishing-Richtlinie sind:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-113">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="3b6f0-114">**Die Anti-Phishing-Richtlinie**: gibt die zu aktivierenden oder zu deaktivierenden Phishing-Schutzmaßnahmen sowie die Aktionen zum Anwenden von Optionen an.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="3b6f0-115">**Die Anti-Phishing-Regel**: gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) für eine Anti-Phishing-Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="3b6f0-116">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Anti-Phishing-Richtlinien im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-116">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="3b6f0-117">Wenn Sie eine Anti-Phishing-Richtlinie im Security & Compliance Center erstellen, erstellen Sie tatsächlich eine Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie gleichzeitig mit dem gleichen Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-117">When you create an anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="3b6f0-118">Wenn Sie eine Richtlinie zum Schutz vor Phishing im Security & Compliance Center ändern, ändern die Einstellungen im Zusammenhang mit dem Namen, der Priorität, den aktivierten oder deaktivierten und den Empfänger filtern die Anti-Phishing-Regel.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-118">When you modify an anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="3b6f0-119">Alle anderen Einstellungen ändern die zugehörige Anti-Phishing-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="3b6f0-120">Wenn Sie eine Richtlinie zum Schutz vor Phishing aus dem Security & Compliance Center entfernen, werden die Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie entfernt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-120">When you remove an anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="3b6f0-121">In Exchange Online PowerShell ist der Unterschied zwischen Anti-Phishing-Richtlinien und Anti-Phishing-Regeln offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="3b6f0-122">Sie können Anti-Phishing-Richtlinien mithilfe der \*\* \* -AntiPhishPolicy-\*\* Cmdlets verwalten und Anti-Phishing-Regeln mithilfe der Cmdlets \*\* \* -AntiPhishRule\*\* verwalten.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="3b6f0-123">In PowerShell erstellen Sie zuerst die Anti-Phishing-Richtlinie, dann erstellen Sie die Anti-Phishing-Regel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="3b6f0-124">In PowerShell ändern Sie die Einstellungen in der Anti-Phishing-Richtlinie und in der Anti-Phishing-Regel separat.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="3b6f0-125">Standardmäßige ATP-Anti-Phishing-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="3b6f0-125">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="3b6f0-126">Jede Organisation verfügt über eine integrierte Anti-Phishing-Richtlinie mit dem Namen "Office365 AntiPhishing default", die die folgenden Eigenschaften aufweist:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-126">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="3b6f0-127">Die Richtlinie mit dem Namen Office365 AntiPhishing Default wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine Anti-Phishing-Regel (Empfängerfilter) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-127">The policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="3b6f0-128">Die Richtlinie mit dem Namen Office365 AntiPhishing default weist den benutzerdefinierten Prioritätswert auf **niedrigster** Bedeutung auf, den Sie nicht ändern können (die Richtlinie wird immer zuletzt angewendet).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-128">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="3b6f0-129">Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität als die Richtlinie mit dem Namen Office365 AntiPhishing default.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-129">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="3b6f0-130">Die Richtlinie mit dem Namen Office365 AntiPhishing Default ist die Standardrichtlinie (die **IsDefault** -Eigenschaft hat den Wert `True` ), und die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-130">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="3b6f0-131">Um die Effektivität des Anti-Phishing-Schutzes zu verbessern, können Sie benutzerdefinierte Anti-Phishing-Richtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-131">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3b6f0-132">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="3b6f0-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3b6f0-133">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3b6f0-134">Wenn Sie direkt zur Seite **Anti-Phishing** wechseln möchten, verwenden Sie <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="3b6f0-134">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="3b6f0-135">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="3b6f0-136">Sie können keine Anti-Phishing-Richtlinien in eigenständigen EoP PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-136">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="3b6f0-137">Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Verfahren in diesem Thema ausführen können:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="3b6f0-138">Zum Hinzufügen, ändern und Löschen von Anti-Phishing-Richtlinien müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-138">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="3b6f0-139">**Organisationsverwaltung** oder **Sicherheits Administrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="3b6f0-140">**Organisationsverwaltung** oder **Hygiene Verwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="3b6f0-141">Für den schreibgeschützten Zugriff auf Anti-Phishing-Richtlinien müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-141">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="3b6f0-142">**Sicherheits Leser** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="3b6f0-143">**Organisationsverwaltung mit Ansichts** Schutz in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="3b6f0-144">Um antispamregeln in eigenständigen EoP erstellen und ändern zu können, müssen Sie für den Mandanten eine _Hydratation_ durchführen.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-144">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="3b6f0-145">Im Exchange Admin Center (EAC) können Sie beispielsweise zur Registerkarte **Berechtigungen** wechseln, eine vorhandene Rollengruppe auswählen, auf Bearbeitungssymbol **Bearbeiten** klicken ![ ](../../media/ITPro-EAC-EditIcon.png) und eine Rolle entfernen (die Sie letztendlich wieder hinzufügen werden).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-145">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="3b6f0-146">Wenn Ihr Mandant noch nie hydratisiert wurde, erhalten Sie ein Dialogfeld mit dem Namen **Update Organization Settings** with a Progress Bar, die erfolgreich abgeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-146">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="3b6f0-147">Weitere Informationen zur Hydratation finden Sie unter dem Cmdlet [enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (das nicht in eigenständigen EoP PowerShell oder im Security & Compliance Center verfügbar ist).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-147">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="3b6f0-148">Unsere empfohlenen Einstellungen für Anti-Phishing-Richtlinien finden Sie unter [EoP default Anti-Phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-148">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="3b6f0-149">Lassen Sie bis zu 30 Minuten für die Anwendung der aktualisierten Richtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-149">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="3b6f0-150">Informationen dazu, wo Anti-Phishing-Richtlinien in der Filter Pipeline angewendet werden, finden Sie unter [Order and Ranges of Email Protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-150">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="3b6f0-151">Verwenden des Security & Compliance Center zum Erstellen von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3b6f0-151">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="3b6f0-152">Durch das Erstellen einer benutzerdefinierten Anti-Phishing-Richtlinie im Security & Compliance Center werden die Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie gleichzeitig mit dem gleichen Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-152">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="3b6f0-153">Wenn Sie eine Anti-Phishing-Richtlinie erstellen, können Sie nur den Richtliniennamen, die Beschreibung und den Empfängerfilter angeben, der angibt, für wen die Richtlinie gilt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-153">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="3b6f0-154">Nachdem Sie die Richtlinie erstellt haben, können Sie die Richtlinie ändern, um die Standardeinstellungen für AntiPhishing zu ändern oder zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-154">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="3b6f0-155">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3b6f0-156">Klicken Sie auf der Seite **Anti-Phishing** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-156">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="3b6f0-157">Der Assistent zum **Erstellen eines neuen Anti-Phishing-Richtlinien** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-157">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="3b6f0-158">Konfigurieren Sie auf der Seite **Ihre Richtlinie benennen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-158">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="3b6f0-159">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-159">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="3b6f0-160">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-160">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="3b6f0-161">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-161">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="3b6f0-162">Identifizieren Sie auf der Seite **angewendet auf** , die angezeigt wird, die internen Empfänger, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="3b6f0-163">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="3b6f0-164">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="3b6f0-165">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="3b6f0-166">Klicken Sie auf **Bedingung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-166">Click **Add a condition**.</span></span> <span data-ttu-id="3b6f0-167">Wählen Sie in der Dropdownliste, die angezeigt wird, eine Bedingung unter **angewendet, wenn**:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="3b6f0-168">**Der Empfänger lautet**: gibt ein oder mehrere Postfächer, e-Mail-Benutzer oder e-Mail-Kontakte in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="3b6f0-169">**Der Empfänger ist Mitglied von**: gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="3b6f0-170">**Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="3b6f0-171">Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **der folgenden** Felder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="3b6f0-172">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der zu markierende Werte durch.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="3b6f0-173">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="3b6f0-174">Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="3b6f0-175">Wenn Sie einzelne Einträge entfernen möchten **Remove** , klicken Sie auf Entfernen- ![ Symbol ](../../media/scc-remove-icon.png) für den Wert entfernen.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="3b6f0-176">Wenn Sie die gesamte Bedingung entfernen möchten **, klicken Sie** ![ in der Bedingung auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="3b6f0-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="3b6f0-177">Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen** , und wählen Sie einen verbleibenden Wert unter **angewendet bei**aus.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="3b6f0-178">Wenn Sie Ausnahmen hinzufügen möchten, klicken Sie auf **Bedingung hinzufügen** , und wählen Sie unter **außer if**eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="3b6f0-179">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="3b6f0-180">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-180">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="3b6f0-181">Überprüfen Sie auf der angezeigten Seite **Ihre Einstellungen überprüfen** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="3b6f0-182">Sie können auf jeder Einstellung auf **Bearbeiten** klicken, um Sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="3b6f0-183">Wenn Sie fertig sind, klicken Sie auf **Diese Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-183">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="3b6f0-184">Klicken Sie im Bestätigungsdialogfeld, das angezeigt wird, auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="3b6f0-184">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="3b6f0-185">Nachdem Sie die Anti-Phishing-Richtlinie mit diesen allgemeinen Richtlinieneinstellungen erstellt haben, können Sie anhand der Anweisungen im nächsten Abschnitt die Schutzeinstellungen in der Richtlinie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-185">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="3b6f0-186">Verwenden des Security & Compliance Center zum Ändern von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3b6f0-186">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="3b6f0-187">Verwenden Sie die folgenden Verfahren, um Richtlinien zum Schutz vor Phishing zu ändern: eine neue Richtlinie, die Sie erstellt haben, oder vorhandene Richtlinien, die Sie bereits angepasst haben.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-187">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="3b6f0-188">Wenn Sie noch nicht vorhanden sind, öffnen Sie das Security & Compliance Center, und wechseln Sie zu **Threat Management** \> **Policy** \> **Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-188">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3b6f0-189">Wählen Sie die benutzerdefinierte Richtlinie zum Schutz vor Phishing aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-189">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="3b6f0-190">Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-190">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="3b6f0-191">Das Flyout **Richtlinie \<name\> Bearbeiten** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-191">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="3b6f0-192">Durch Klicken auf **Bearbeiten** in einem beliebigen Abschnitt erhalten Sie Zugriff auf die Einstellungen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-192">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="3b6f0-193">Die folgenden Schritte werden in der Reihenfolge angezeigt, in der die Abschnitte dargestellt werden, Sie sind jedoch nicht sequenziell (Sie können die Abschnitte in beliebiger Reihenfolge auswählen und ändern).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-193">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="3b6f0-194">Nachdem Sie in einem Abschnitt auf **Bearbeiten** klicken, werden die verfügbaren Einstellungen in einem Assistenten Format angezeigt, aber Sie können in beliebiger Reihenfolge auf die Seiten springen, und Sie können auf einer beliebigen Seite auf **Speichern** **(oder** **Abbrechen** oder Schließen schließen) klicken, um ![ ](../../media/scc-remove-icon.png) zur Seite **Richtlinie \<name\> Bearbeiten** zurückzukehren (Sie müssen nicht die letzte Seite des Assistenten zum Speichern oder verlassen besuchen).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-194">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="3b6f0-195">**Richtlinieneinstellung**: Klicken Sie auf **Bearbeiten** , um dieselben Einstellungen zu ändern, die beim [Erstellen der Richtlinie](#use-the-security--compliance-center-to-create-anti-phishing-policies) im vorherigen Abschnitt verfügbar waren:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-195">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="3b6f0-196">**Name**</span><span class="sxs-lookup"><span data-stu-id="3b6f0-196">**Name**</span></span>
   - <span data-ttu-id="3b6f0-197">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3b6f0-197">**Description**</span></span>
   - <span data-ttu-id="3b6f0-198">**Angewendet auf**</span><span class="sxs-lookup"><span data-stu-id="3b6f0-198">**Applied to**</span></span>
   - <span data-ttu-id="3b6f0-199">**Ihre Einstellungen überprüfen**</span><span class="sxs-lookup"><span data-stu-id="3b6f0-199">**Review your settings**</span></span>

   <span data-ttu-id="3b6f0-200">Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="3b6f0-200">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="3b6f0-201">**Spoof**: Klicken Sie auf **Bearbeiten** , um Spoof Intelligence ein-oder auszuschalten, die nicht authentifizierte Absender Identifikation in Outlook ein-oder auszuschalten und die Aktion so zu konfigurieren, dass Sie auf Nachrichten von blockierten gefälschten Absendern angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-201">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="3b6f0-202">Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-202">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="3b6f0-203">Beachten Sie, dass dieselben Einstellungen auch in Richtlinien für ATP-AntiPhishing verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-203">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="3b6f0-204">**Spoofing-Filtereinstellungen**: der Standardwert ist " **on**", und es wird empfohlen, dass Sie die Einstellung aktiviert lassen.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-204">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="3b6f0-205">Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-205">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="3b6f0-206">Weitere Informationen finden Sie unter [configure Spoof Intelligence in EoP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-206">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="3b6f0-207">Sie müssen den Schutz vor Spoofing nicht deaktivieren, wenn Ihr MX-Eintrag nicht auf Microsoft 365 verweist; Stattdessen aktivieren Sie die erweiterte Filterung für Connectors.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-207">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="3b6f0-208">Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-208">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="3b6f0-209">Nicht **authentifizierte Absender Funktion aktivieren**: der Standardwert ist **on**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-209">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="3b6f0-210">Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-210">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="3b6f0-211">**Actions: geben**Sie die Aktion an, die für Nachrichten ausgeführt werden soll, die Spoof Intelligence nicht ausführen:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-211">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="3b6f0-212">**Wenn e-Mails von Benutzern gesendet werden, die Ihre Domäne nicht spoofen dürfen**:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-212">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="3b6f0-213">**Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern**</span><span class="sxs-lookup"><span data-stu-id="3b6f0-213">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="3b6f0-214">**Nachricht isolieren**</span><span class="sxs-lookup"><span data-stu-id="3b6f0-214">**Quarantine the message**</span></span>

   - <span data-ttu-id="3b6f0-215">**Überprüfen Sie Ihre Einstellungen**: anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-215">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="3b6f0-216">Sie können in jedem Abschnitt auf **Bearbeiten** klicken, um zurück zur entsprechenden Seite zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-216">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="3b6f0-217">Sie können die **folgenden Einstellungen direkt auf dieser** Seite aktivieren oder **Deaktivieren** :</span><span class="sxs-lookup"><span data-stu-id="3b6f0-217">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="3b6f0-218">**Aktivieren von Schutz vor Spoofing**</span><span class="sxs-lookup"><span data-stu-id="3b6f0-218">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="3b6f0-219">**Nicht authentifizierte Absender Funktion aktivieren**</span><span class="sxs-lookup"><span data-stu-id="3b6f0-219">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="3b6f0-220">Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="3b6f0-220">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="3b6f0-221">Überprüfen Sie die Einstellungen auf der Seite **Richtlinie \<Name\> Bearbeiten** , und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-221">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="3b6f0-222">Verwenden des Security & Compliance Center zum Ändern der standardmäßigen Anti-Phishing-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="3b6f0-222">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="3b6f0-223">Die standardmäßige Anti-Phishing-Richtlinie heißt Office365 AntiPhishing Default, und Sie wird nicht in der Liste der Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-223">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="3b6f0-224">Führen Sie die folgenden Schritte aus, um die standardmäßige Anti-Phishing-Richtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-224">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="3b6f0-225">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-225">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3b6f0-226">Klicken Sie auf der Seite **Anti-Phishing** auf **Standardrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-226">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="3b6f0-227">Die **Standardseite Ihre Richtlinie Office365 AntiPhishing bearbeiten** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-227">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="3b6f0-228">Die folgenden Abschnitte sind verfügbar, die identische Einstellungen enthalten, wenn Sie [eine benutzerdefinierte Richtlinie ändern](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-228">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="3b6f0-229">**Impersonation**</span><span class="sxs-lookup"><span data-stu-id="3b6f0-229">**Impersonation**</span></span>
   - <span data-ttu-id="3b6f0-230">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="3b6f0-230">**Spoof**</span></span>
   - <span data-ttu-id="3b6f0-231">**Erweiterte Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="3b6f0-231">**Advanced settings**</span></span>

   <span data-ttu-id="3b6f0-232">Die folgenden Einstellungen sind nicht verfügbar, wenn Sie die Standardrichtlinie ändern:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-232">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="3b6f0-233">Sie können den Abschnitt mit den **Richtlinieneinstellungen** und die Werte anzeigen, es gibt jedoch keinen Link **Bearbeiten** , sodass Sie die Einstellungen nicht ändern können (Richtlinienname, Beschreibung und für wen die Richtlinie gilt (gilt für alle Empfänger)).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-233">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="3b6f0-234">Die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-234">You can't delete the default policy.</span></span>
   - <span data-ttu-id="3b6f0-235">Sie können die Priorität der Standardrichtlinie nicht ändern (Sie wird immer zuletzt angewendet).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-235">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="3b6f0-236">Überprüfen Sie auf der **Standardseite Richtlinie Office365 bearbeiten** die Einstellungen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-236">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="3b6f0-237">Aktivieren oder deaktivieren benutzerdefinierter Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3b6f0-237">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="3b6f0-238">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3b6f0-239">Beachten Sie den Wert in der Spalte **Status** :</span><span class="sxs-lookup"><span data-stu-id="3b6f0-239">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="3b6f0-240">Schieben Sie die Umschaltfläche auf **aus** , um die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-240">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="3b6f0-241">Schieben Sie die Umschaltfläche in **ein** , um die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-241">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="3b6f0-242">Sie können die standardmäßige Anti-Phishing-Richtlinie nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-242">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="3b6f0-243">Festlegen der Priorität von benutzerdefinierten Richtlinien zum Schutz vor Phishing</span><span class="sxs-lookup"><span data-stu-id="3b6f0-243">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="3b6f0-244">Standardmäßig erhalten Anti-Phishing-Richtlinien eine Priorität, die auf der Reihenfolge basiert, in der Sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-244">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="3b6f0-245">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-245">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="3b6f0-246">Zwei Richtlinien können nicht dieselbe Priorität haben.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-246">No two policies can have the same priority.</span></span>

<span data-ttu-id="3b6f0-247">Benutzerdefinierte Anti-Phishing-Richtlinien werden in der Reihenfolge angezeigt, in der Sie verarbeitet werden (die erste Richtlinie hat den **Prioritäts** Wert 0).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-247">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="3b6f0-248">Die standardmäßige Anti-Phishing-Richtlinie mit dem Namen "Office365 AntiPhishing default" weist den benutzerdefinierten Prioritätswert als " **niedrigste**" auf und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-248">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="3b6f0-249">**Hinweis**: im Security & Compliance Center können Sie die Priorität der Anti-Phishing-Richtlinie nur ändern, nachdem Sie Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-249">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="3b6f0-250">In PowerShell können Sie die Standardpriorität außer Kraft setzen, wenn Sie die Anti-Phishing-Regel erstellen (die sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-250">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="3b6f0-251">Um die Priorität einer Richtlinie zu ändern, klicken Sie in den Eigenschaften der Richtlinie auf **Priorität verbessern** oder **Priorität verringern** (die **Prioritäts** Nummer im Security & Compliance Center kann nicht direkt geändert werden).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-251">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="3b6f0-252">Das Ändern der Priorität einer Richtlinie ist nur dann sinnvoll, wenn Sie über mehrere Richtlinien verfügen.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-252">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="3b6f0-253">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3b6f0-254">Wählen Sie die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-254">Select the policy that you want to modify.</span></span> <span data-ttu-id="3b6f0-255">Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-255">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="3b6f0-256">Das Flyout **Richtlinie \<name\> Bearbeiten** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-256">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="3b6f0-257">Für die benutzerdefinierte Richtlinie zum Schutz vor Phishing mit dem **Prioritäts** Wert **0** ist nur die Schaltfläche **Priorität verringern** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-257">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="3b6f0-258">Für die benutzerdefinierte Richtlinie zum Schutz vor Phishing mit dem niedrigsten **Prioritäts** Wert (beispielsweise **3**) ist nur die Schaltfläche **Priorität verlängern** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-258">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="3b6f0-259">Wenn Sie über drei oder mehr benutzerdefinierte Anti-Phishing-Richtlinien verfügen, stehen für Richtlinien zwischen den Werten der höchsten und der niedrigsten Priorität **sowohl die Prioritätsschaltflächen "Priorität"** als auch " **Priorität verringern** " zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-259">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="3b6f0-260">Klicken Sie auf Priorität Verb **Essern** oder **Priorität verringern** , um den **Prioritäts** Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-260">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="3b6f0-261">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-261">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="3b6f0-262">Verwenden des Security & Compliance Center zum Anzeigen von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3b6f0-262">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="3b6f0-263">Im Security & Compliance Center und wechseln Sie zu **Threat Management** \> **Policy** \> **Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-263">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3b6f0-264">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-264">Do one of the following steps:</span></span>

   - <span data-ttu-id="3b6f0-265">Wählen Sie eine benutzerdefinierte Richtlinie zum Schutz vor Phishing aus, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-265">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="3b6f0-266">Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-266">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="3b6f0-267">Klicken Sie auf **Standardrichtlinie** , um die standardmäßige Anti-Phishing-Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-267">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="3b6f0-268">Das Flyout zum **Bearbeiten \<name\> Ihrer Richtlinie** wird angezeigt, in dem Sie die Einstellungen und Werte anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-268">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="3b6f0-269">Verwenden des Security & Compliance Center zum Entfernen von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3b6f0-269">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="3b6f0-270">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-270">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3b6f0-271">Wählen Sie die Richtlinie aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-271">Select the policy that you want to remove.</span></span> <span data-ttu-id="3b6f0-272">Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-272">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="3b6f0-273">Klicken Sie im daraufhin angezeigten Dialogfeld **Richtlinie \<name\> Bearbeiten** auf **Richtlinie löschen**, und klicken Sie dann im angezeigten Warndialogfeld auf **Ja** .</span><span class="sxs-lookup"><span data-stu-id="3b6f0-273">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="3b6f0-274">Die Standardrichtlinie kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-274">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="3b6f0-275">Konfigurieren von Anti-Phishing-Richtlinien mithilfe Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b6f0-275">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="3b6f0-276">Die folgenden Verfahren sind in eigenständigen EoP-Organisationen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-276">The following procedures aren't available in standalone EOP organizations.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="3b6f0-277">Verwenden von PowerShell zum Erstellen von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3b6f0-277">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="3b6f0-278">Das Erstellen einer Anti-Phishing-Richtlinie in PowerShell ist ein zweistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-278">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="3b6f0-279">Erstellen Sie die Anti-Phishing-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-279">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="3b6f0-280">Erstellen Sie die Anti-Phishing-Regel, die die Anti-Phishing-Richtlinie angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-280">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="3b6f0-281">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-281">**Notes**:</span></span>

- <span data-ttu-id="3b6f0-282">Sie können eine neue Anti-Phishing-Regel erstellen und ihr eine vorhandene, nicht zugeordnete Anti-Phishing-Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-282">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="3b6f0-283">Eine Anti-Phishing-Regel kann nicht mehr als einer Anti-Phishing-Richtlinie zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-283">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="3b6f0-284">Sie können die folgenden Einstellungen für neue Anti-Phishing-Richtlinien in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Security & Compliance Center verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-284">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="3b6f0-285">Erstellen Sie die neue Richtlinie als deaktiviert (_aktiviert_ im `$false` Cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-285">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="3b6f0-286">Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) für das Cmdlet **New-AntiPhishRule** fest).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-286">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="3b6f0-287">Eine neue Anti-Phishing-Richtlinie, die Sie in PowerShell erstellen, ist erst im Security & Compliance Center sichtbar, wenn Sie die Richtlinie einer Anti-Phishing-Regel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-287">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="3b6f0-288">Schritt 1: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="3b6f0-288">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="3b6f0-289">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Richtlinie zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-289">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="3b6f0-290">In diesem Beispiel wird die Anti-Phishing-Richtlinie mit dem Namen "Research Quarantine" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-290">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="3b6f0-291">Die Richtlinie ist aktiviert (der Parameter _Enabled_ wird nicht verwendet, und der Standardwert ist `$true` ).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-291">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="3b6f0-292">Die Beschreibung lautet: Abteilungs Richtlinie für Forschung.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-292">The description is: Research department policy.</span></span>
- <span data-ttu-id="3b6f0-293">Ändert die Standardaktion für Spoofing in Quarantäne.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-293">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="3b6f0-294">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-294">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="3b6f0-295">Schritt 2: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Regel</span><span class="sxs-lookup"><span data-stu-id="3b6f0-295">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="3b6f0-296">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-296">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="3b6f0-297">In diesem Beispiel wird eine Anti-Phishing-Regel namens "Research Department" mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-297">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="3b6f0-298">Die Regel ist der Anti-Phishing-Richtlinie "Research Quarantine" zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-298">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="3b6f0-299">Die Regel gilt für Mitglieder der Gruppe „Research Department“.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-299">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="3b6f0-300">Da wir den _Priority_ -Parameter nicht verwenden, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-300">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="3b6f0-301">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-301">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="3b6f0-302">Verwenden von PowerShell zum Anzeigen von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3b6f0-302">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="3b6f0-303">Verwenden Sie die folgende Syntax, um vorhandene Anti-Phishing-Richtlinien anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-303">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="3b6f0-304">In diesem Beispiel wird eine Zusammenfassungsliste aller Anti-Phishing-Richtlinien zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-304">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="3b6f0-305">In diesem Beispiel werden alle Eigenschaftswerte für die Anti-Phishing-Richtlinie "Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-305">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="3b6f0-306">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-306">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="3b6f0-307">Verwenden von PowerShell zum Anzeigen von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="3b6f0-307">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="3b6f0-308">Verwenden Sie die folgende Syntax, um vorhandene Anti-Phishing-Regeln anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-308">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="3b6f0-309">In diesem Beispiel wird eine Zusammenfassungsliste aller Anti-Phishing-Regeln zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-309">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="3b6f0-310">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-310">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="3b6f0-311">In diesem Beispiel werden alle Eigenschaftswerte für die Anti-Phishing-Regel namens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-311">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="3b6f0-312">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-312">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="3b6f0-313">Verwenden von PowerShell zum Ändern von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3b6f0-313">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="3b6f0-314">Anders als die folgenden Elemente sind die gleichen Einstellungen verfügbar, wenn Sie eine Anti-Phishing-Richtlinie in PowerShell wie beim Erstellen der Richtlinie wie im Abschnitt [Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie zu AntiPhishing-Richt](#step-1-use-powershell-to-create-an-anti-phish-policy) Linien weiter oben in diesem Thema ändern.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-314">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="3b6f0-315">Der _MakeDefault_ -Schalter, der die angegebene Richtlinie in die Standardrichtlinie umwandelt (gilt für alle, immer **niedrigste** Priorität, und Sie können Sie nicht löschen) ist nur verfügbar, wenn Sie eine Anti-Phishing-Richtlinie in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-315">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="3b6f0-316">Sie können keine Anti-Phishing-Richtlinie umbenennen (das Cmdlet " **AntiPhishPolicy** " hat keinen Parameter " _Name_ ").</span><span class="sxs-lookup"><span data-stu-id="3b6f0-316">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="3b6f0-317">Wenn Sie eine Richtlinie zum Schutz vor Phishing im Security & Compliance Center umbenennen, benennen Sie die Anti-Phishing- _Regel_nur um.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-317">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="3b6f0-318">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Richtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-318">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="3b6f0-319">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-319">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="3b6f0-320">Verwenden von PowerShell zum Ändern von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="3b6f0-320">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="3b6f0-321">Die einzige Einstellung, die beim Ändern einer Anti-Phishing-Regel in PowerShell nicht verfügbar ist, ist der Parameter _Enabled_ , mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-321">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="3b6f0-322">Informationen zum Aktivieren oder Deaktivieren vorhandener Anti-Phishing-Regeln finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-322">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="3b6f0-323">Andernfalls stehen keine zusätzlichen Einstellungen zur Verfügung, wenn Sie eine Anti-Phishing-Regel in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-323">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="3b6f0-324">Die gleichen Einstellungen sind verfügbar, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Regel](#step-2-use-powershell-to-create-an-anti-phish-rule) weiter oben in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-324">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="3b6f0-325">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel zu ändern:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-325">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="3b6f0-326">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-326">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="3b6f0-327">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="3b6f0-327">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="3b6f0-328">Durch das Aktivieren oder Deaktivieren einer Anti-Phishing-Regel in PowerShell wird die gesamte Richtlinie zum Schutz vor Phishing aktiviert oder deaktiviert (die Anti-Phishing-Regel und die zugewiesene Anti-Phishing-Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-328">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="3b6f0-329">Sie können die standardmäßige Anti-Phishing-Richtlinie nicht aktivieren oder deaktivieren (Sie wird immer auf alle Empfänger angewendet).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-329">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="3b6f0-330">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-330">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="3b6f0-331">In diesem Beispiel wird die Anti-Phishing-Regel namens "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-331">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3b6f0-332">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-332">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3b6f0-333">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) und [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-333">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="3b6f0-334">Verwenden von PowerShell zum Festlegen der Priorität von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="3b6f0-334">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="3b6f0-335">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-335">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="3b6f0-336">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-336">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="3b6f0-337">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-337">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="3b6f0-338">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-338">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="3b6f0-339">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-339">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="3b6f0-340">Verwenden Sie die folgende Syntax, um die Priorität einer Anti-Phishing-Regel in PowerShell festzulegen:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-340">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="3b6f0-341">This example sets the priority of the rule named Marketing Department to 2.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-341">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="3b6f0-342">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-342">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="3b6f0-343">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-343">**Notes**:</span></span>

- <span data-ttu-id="3b6f0-344">Wenn Sie die Priorität einer neuen Regel beim Erstellen festlegen möchten, verwenden Sie stattdessen den Parameter _Priority_ für das Cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="3b6f0-344">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="3b6f0-345">Die standardmäßige Anti-Phishing-Richtlinie verfügt nicht über eine entsprechende Anti-Phishing-Regel, und Sie hat immer den Wert unveränderbare Priorität **niedrigste**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-345">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="3b6f0-346">Verwenden von PowerShell zum Entfernen von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3b6f0-346">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="3b6f0-347">Wenn Sie PowerShell zum Entfernen einer Anti-Phishing-Richtlinie verwenden, wird die entsprechende Anti-Phishing-Regel nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-347">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="3b6f0-348">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Richtlinie in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-348">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="3b6f0-349">In diesem Beispiel wird die Anti-Phishing-Richtlinie namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-349">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="3b6f0-350">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-350">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="3b6f0-351">Verwenden von PowerShell zum Entfernen von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="3b6f0-351">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="3b6f0-352">Wenn Sie PowerShell zum Entfernen einer Anti-Phishing-Regel verwenden, wird die entsprechende Anti-Phishing-Richtlinie nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-352">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="3b6f0-353">Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-353">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="3b6f0-354">In diesem Beispiel wird die Anti-Phishing-Regel namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-354">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3b6f0-355">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="3b6f0-355">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="3b6f0-356">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="3b6f0-356">How do you know these procedures worked?</span></span>

<span data-ttu-id="3b6f0-357">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie die Richtlinien für ATP-Phishing erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-357">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="3b6f0-358">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-358">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="3b6f0-359">Überprüfen Sie die Liste der Richtlinien, deren **Status** Werte und deren **Prioritäts** Werte.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-359">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="3b6f0-360">Um weitere Details anzuzeigen, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-360">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="3b6f0-361">Wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-361">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="3b6f0-362">Klicken Sie auf **Standardrichtlinie** , und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-362">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="3b6f0-363">Ersetzen Sie in Exchange Online PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, und führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="3b6f0-363">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
