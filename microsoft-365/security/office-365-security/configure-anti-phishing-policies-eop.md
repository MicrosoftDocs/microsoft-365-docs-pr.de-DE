---
title: Konfigurieren von Anti-Phishing-Richtlinien in EOP
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
description: Administratoren können erfahren, wie Sie die Antiphishingrichtlinien erstellen, ändern und löschen, die in Exchange Online Protection (EOP)-Organisationen mit oder ohne Exchange Online verfügbar sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c277558bad32e1926030483d202b70ae3c910315
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206211"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="69cab-103">Konfigurieren von Anti-Phishing-Richtlinien in EOP</span><span class="sxs-lookup"><span data-stu-id="69cab-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="69cab-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="69cab-104">**Applies to**</span></span>
- [<span data-ttu-id="69cab-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="69cab-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="69cab-106">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer gibt es eine Standardmäßige Antiphishingrichtlinie, die eine begrenzte Anzahl von Antis spoofing-Features enthält, die standardmäßig aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="69cab-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="69cab-107">Weitere Informationen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="69cab-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="69cab-108">Administratoren können die standardmäßige Antiphishingrichtlinie anzeigen, bearbeiten und konfigurieren (aber nicht löschen).</span><span class="sxs-lookup"><span data-stu-id="69cab-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="69cab-109">Für eine höhere Granularität können Sie auch benutzerdefinierte Antiphishingrichtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="69cab-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="69cab-110">Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="69cab-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="69cab-111">Organisationen mit Exchange Online Postfächern können Antiphishingrichtlinien im Security & Compliance Center oder in Exchange Online PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="69cab-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="69cab-112">Eigenständige EOP-Organisationen können nur das Security & Compliance Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="69cab-112">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="69cab-113">Informationen zum Erstellen und Ändern der erweiterten Antiphishingrichtlinien in Microsoft Defender für Office 365, die in Defender for Office 365 verfügbar sind, finden Sie unter [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="69cab-113">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="69cab-114">Die grundlegenden Elemente einer Antiphishingrichtlinie sind:</span><span class="sxs-lookup"><span data-stu-id="69cab-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="69cab-115">**Die Antiphishrichtlinie**: Gibt die zu aktivierenden oder deaktivierenden Phishingschutzmaßnahmen sowie die Aktionen zum Anwenden von Optionen an.</span><span class="sxs-lookup"><span data-stu-id="69cab-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="69cab-116">**Die Antiphishregel**: Gibt die Priorität und empfängerfilter (auf wen die Richtlinie angewendet wird) für eine Antiphishrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="69cab-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="69cab-117">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Antiphishingrichtlinien im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="69cab-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="69cab-118">Wenn Sie eine Antiphishingrichtlinie erstellen, erstellen Sie tatsächlich eine Antiphishregel und die zugehörige Antiphishrichtlinie gleichzeitig mit demselben Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="69cab-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="69cab-119">Wenn Sie eine Antiphishingrichtlinie ändern, ändern Einstellungen im Zusammenhang mit name, priority, enabled oder disabled und Empfängerfiltern die Antiphishregel.</span><span class="sxs-lookup"><span data-stu-id="69cab-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="69cab-120">Alle anderen Einstellungen ändern die zugeordnete Antiphishrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="69cab-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="69cab-121">Wenn Sie eine Antiphishingrichtlinie entfernen, werden die Antiphishregel und die zugehörige Antiphishingrichtlinie entfernt.</span><span class="sxs-lookup"><span data-stu-id="69cab-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="69cab-122">In Exchange Online PowerShell verwalten Sie die Richtlinie und die Regel separat.</span><span class="sxs-lookup"><span data-stu-id="69cab-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="69cab-123">Weitere Informationen finden Sie im Abschnitt [Verwenden Exchange Online PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies) zum Konfigurieren von Antiphishingrichtlinien weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="69cab-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="69cab-124">Jede Organisation verfügt über eine integrierte Antiphishingrichtlinie namens Office365 AntiPhish Default mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="69cab-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="69cab-125">Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, auch wenn der Richtlinie keine Antiphishregel (Empfängerfilter) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="69cab-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="69cab-126">Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet).</span><span class="sxs-lookup"><span data-stu-id="69cab-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="69cab-127">Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität.</span><span class="sxs-lookup"><span data-stu-id="69cab-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="69cab-128">Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="69cab-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="69cab-129">Um die Effektivität des Antiphishingschutzes zu erhöhen, können Sie benutzerdefinierte Antiphishingrichtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="69cab-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="69cab-130">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="69cab-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="69cab-131">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="69cab-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="69cab-132">Um direkt zur Seite **"Antiphishing" zu** wechseln, verwenden Sie <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="69cab-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="69cab-133">Wie Sie eine Verbindung mit Exchange Online-PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="69cab-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="69cab-134">Antiphishingrichtlinien können nicht in eigenständigen EOP PowerShell verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="69cab-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="69cab-135">Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:</span><span class="sxs-lookup"><span data-stu-id="69cab-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="69cab-136">Zum Hinzufügen, Ändern und Löschen von Antiphishingrichtlinien müssen  Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein.</span><span class="sxs-lookup"><span data-stu-id="69cab-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="69cab-137">Für den schreibgeschützten Zugriff auf Antiphishingrichtlinien müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** <sup>\*</sup> sein.</span><span class="sxs-lookup"><span data-stu-id="69cab-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="69cab-138">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="69cab-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="69cab-139">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="69cab-139">**Notes**:</span></span>

  - <span data-ttu-id="69cab-140">Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69cab-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="69cab-141">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="69cab-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="69cab-142">Die **Rollengruppe "Nur-Ansichtsorganisationsverwaltung"** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) bietet auch schreibgeschützten Zugriff auf das <sup>\*</sup> Feature.</span><span class="sxs-lookup"><span data-stu-id="69cab-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="69cab-143"><sup>\*</sup> Im Security & Compliance Center können Benutzer mit schreibgeschützten Zugriff die Einstellungen benutzerdefinierter Antiphishingrichtlinien anzeigen.</span><span class="sxs-lookup"><span data-stu-id="69cab-143"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="69cab-144">Schreibgeschützte Benutzer können die Einstellungen in der Standardmäßigen Antiphishingrichtlinie nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="69cab-144">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="69cab-145">Zum Erstellen und Ändern von Antiphishingrichtlinien in eigenständigem EOP müssen Sie etwas tun, das eine _Hydratation_ für Ihren Mandanten erfordert.</span><span class="sxs-lookup"><span data-stu-id="69cab-145">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="69cab-146">Beispielsweise können Sie im Exchange Admin Center (EAC)  zur Registerkarte Berechtigungen wechseln, eine  vorhandene Rollengruppe auswählen, auf Bearbeiten (Symbol bearbeiten) klicken und eine Rolle entfernen (die Sie schließlich wieder ![ ](../../media/ITPro-EAC-EditIcon.png) hinzufügen).</span><span class="sxs-lookup"><span data-stu-id="69cab-146">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="69cab-147">Wenn Ihr Mandant noch nie hydratisiert wurde, erhalten Sie ein Dialogfeld namens **Update Organization Einstellungen** mit einer Statusleiste, die erfolgreich abgeschlossen werden sollte.</span><span class="sxs-lookup"><span data-stu-id="69cab-147">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="69cab-148">Weitere Informationen zur Hydratation finden Sie im [Cmdlet Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) (das nicht in der eigenständigen EOP PowerShell oder im Security & Compliance Center verfügbar ist).</span><span class="sxs-lookup"><span data-stu-id="69cab-148">For more information about hydration, see the [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="69cab-149">Unsere empfohlenen Einstellungen für Antiphishingrichtlinien finden Sie unter [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="69cab-149">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="69cab-150">Es ist bis zu 30 Minuten zulässig, bis die aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="69cab-150">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="69cab-151">Informationen dazu, wo Antiphishingrichtlinien in der Filterpipeline angewendet werden, finden Sie unter [Reihenfolge und Rangfolge des E-Mail-Schutzes](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="69cab-151">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="69cab-152">Erstellen von Antiphishingrichtlinien mithilfe & Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="69cab-152">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="69cab-153">Beim Erstellen einer benutzerdefinierten Antiphishingrichtlinie im Security & Compliance Center werden die Antiphishregel und die zugehörige Antiphishingrichtlinie gleichzeitig mit demselben Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="69cab-153">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="69cab-154">Wenn Sie eine Antiphishingrichtlinie erstellen, können Sie nur den Richtliniennamen, die Beschreibung und den Empfängerfilter angeben, der identifiziert, auf wen die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="69cab-154">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="69cab-155">Nachdem Sie die Richtlinie erstellt haben, können Sie die Richtlinie ändern, um die Standardmäßigen Antiphishingeinstellungen zu ändern oder zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="69cab-155">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="69cab-156">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="69cab-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="69cab-157">Klicken Sie **auf der Seite Antiphishing** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="69cab-157">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="69cab-158">Der **Assistent zum Erstellen einer neuen Antiphishingrichtlinie** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="69cab-158">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="69cab-159">Konfigurieren Sie **auf der Seite** Ihre Richtlinie benennen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="69cab-159">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="69cab-160">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="69cab-160">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="69cab-161">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="69cab-161">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="69cab-162">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="69cab-162">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="69cab-163">Identifizieren Sie **auf der angezeigten** Seite Angewendet auf die internen Empfänger, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="69cab-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="69cab-164">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="69cab-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="69cab-165">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="69cab-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="69cab-166">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="69cab-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="69cab-167">Klicken **Sie auf Bedingung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="69cab-167">Click **Add a condition**.</span></span> <span data-ttu-id="69cab-168">Wählen Sie in der angezeigten Dropdownliste unter Angewendet eine **Bedingung aus, wenn**:</span><span class="sxs-lookup"><span data-stu-id="69cab-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="69cab-169">**Der Empfänger ist**: Gibt ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="69cab-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="69cab-170">**Der Empfänger ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="69cab-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="69cab-171">**Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="69cab-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="69cab-172">Nachdem Sie die Bedingung ausgewählt haben, wird ein entsprechendes Dropdownfeld mit einem **Beliebigen dieser Kontrollkästchen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69cab-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="69cab-173">Klicken Sie in das Feld, und scrollen Sie durch die Liste der auszuwählende Werte.</span><span class="sxs-lookup"><span data-stu-id="69cab-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="69cab-174">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="69cab-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="69cab-175">Klicken Sie auf einen leeren Bereich im Feld, um weitere Werte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="69cab-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="69cab-176">Klicken Sie zum Entfernen einzelner Einträge **auf Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für den Wert.</span><span class="sxs-lookup"><span data-stu-id="69cab-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="69cab-177">Klicken Sie zum Entfernen der gesamten Bedingung auf **Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für die Bedingung.</span><span class="sxs-lookup"><span data-stu-id="69cab-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="69cab-178">Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen,** und wählen Sie einen verbleibenden Wert unter **Angewendet wenn aus.**</span><span class="sxs-lookup"><span data-stu-id="69cab-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="69cab-179">Klicken Sie zum Hinzufügen von Ausnahmen auf **Bedingung hinzufügen,** und wählen Sie unter **Except if eine Ausnahme aus.**</span><span class="sxs-lookup"><span data-stu-id="69cab-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="69cab-180">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="69cab-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="69cab-181">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="69cab-181">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="69cab-182">Überprüfen Sie **auf der angezeigten** Seite Einstellungen überprüfen Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="69cab-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="69cab-183">Sie können **für** jede Einstellung auf Bearbeiten klicken, um sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="69cab-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="69cab-184">Klicken Sie nach Abschluss des Abschlusses auf **Diese Richtlinie erstellen.**</span><span class="sxs-lookup"><span data-stu-id="69cab-184">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="69cab-185">Klicken Sie im angezeigten Bestätigungsdialogfeld auf **OK.**</span><span class="sxs-lookup"><span data-stu-id="69cab-185">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="69cab-186">Nachdem Sie die Antiphishingrichtlinie mit diesen allgemeinen Richtlinieneinstellungen erstellt haben, verwenden Sie die Anweisungen im nächsten Abschnitt, um die Schutzeinstellungen in der Richtlinie zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="69cab-186">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="69cab-187">Verwenden des Security & Compliance Center zum Ändern von Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="69cab-187">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="69cab-188">Verwenden Sie die folgenden Verfahren, um Antiphishingrichtlinien zu ändern: eine neue Richtlinie, die Sie erstellt haben, oder vorhandene Richtlinien, die Sie bereits angepasst haben.</span><span class="sxs-lookup"><span data-stu-id="69cab-188">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="69cab-189">Wenn Sie noch nicht vorhanden sind, öffnen Sie das Security & Compliance Center, und wechseln Sie **zu** Richtlinie zur \>  \> **Bedrohungsverwaltung Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="69cab-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="69cab-190">Wählen Sie die benutzerdefinierte Antiphishingrichtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="69cab-190">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="69cab-191">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="69cab-191">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="69cab-192">Das **Flyout \<name\> "Richtlinie bearbeiten"** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69cab-192">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="69cab-193">Durch Klicken **auf Bearbeiten** in einem beliebigen Abschnitt erhalten Sie Zugriff auf die Einstellungen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="69cab-193">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="69cab-194">Die folgenden Schritte werden in der Reihenfolge dargestellt, in der die Abschnitte angezeigt werden, sie sind jedoch nicht sequenziell (Sie können die Abschnitte in beliebiger Reihenfolge auswählen und ändern).</span><span class="sxs-lookup"><span data-stu-id="69cab-194">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="69cab-195">Nachdem Sie **in** einem Abschnitt auf Bearbeiten geklickt haben, werden die verfügbaren Einstellungen in einem  Assistentenformat angezeigt, Sie  können jedoch in beliebiger Reihenfolge innerhalb der Seiten springen, und Sie können auf einer beliebigen Seite auf Speichern klicken (oder  ![ ](../../media/scc-remove-icon.png) **\<name\>** Abbrechen oder Schließen schließen, um zur Seite Richtlinie bearbeiten zurückzukehren (Sie müssen nicht die letzte Seite des Assistenten zum Speichern oder Verlassen des Assistenten besuchen).</span><span class="sxs-lookup"><span data-stu-id="69cab-195">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="69cab-196">**Richtlinieneinstellung**: Klicken Sie auf **Bearbeiten,** um dieselben Einstellungen zu ändern, die beim Erstellen der Richtlinie [im](#use-the-security--compliance-center-to-create-anti-phishing-policies) vorherigen Abschnitt verfügbar waren:</span><span class="sxs-lookup"><span data-stu-id="69cab-196">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="69cab-197">**Name**</span><span class="sxs-lookup"><span data-stu-id="69cab-197">**Name**</span></span>
   - <span data-ttu-id="69cab-198">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="69cab-198">**Description**</span></span>
   - <span data-ttu-id="69cab-199">**Angewendet auf**</span><span class="sxs-lookup"><span data-stu-id="69cab-199">**Applied to**</span></span>
   - <span data-ttu-id="69cab-200">**Überprüfen Der Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="69cab-200">**Review your settings**</span></span>

   <span data-ttu-id="69cab-201">Wenn Sie fertig sind, klicken Sie auf **einer beliebigen** Seite auf Speichern.</span><span class="sxs-lookup"><span data-stu-id="69cab-201">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="69cab-202">**Spoof**:  Klicken Sie auf Bearbeiten, um die Spoofintelligenz ein- oder auszuschalten, die Identifikation nicht authentifizierter Absender in Outlook ein- oder auszuschalten und die Aktion so zu konfigurieren, dass sie auf Nachrichten von blockierten spoofierten Absendern angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="69cab-202">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="69cab-203">Weitere Informationen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="69cab-203">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="69cab-204">Beachten Sie, dass diese Einstellungen auch in Antiphishingrichtlinien in Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="69cab-204">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="69cab-205">**Spoofing-Filtereinstellungen:** Der Standardwert ist **Ein**, und es wird empfohlen, ihn zu be lassen.</span><span class="sxs-lookup"><span data-stu-id="69cab-205">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="69cab-206">Um es zu deaktivieren, verschieben Sie den Umschalter auf **Aus**.</span><span class="sxs-lookup"><span data-stu-id="69cab-206">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="69cab-207">Weitere Informationen finden Sie unter [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="69cab-207">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="69cab-208">Sie müssen den Schutz vor Spoofing nicht deaktivieren, wenn Ihr #A0 nicht auf Microsoft 365. Stattdessen aktivieren Sie erweiterte Filterung für Connectors.</span><span class="sxs-lookup"><span data-stu-id="69cab-208">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="69cab-209">Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="69cab-209">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="69cab-210">**Feature Nicht authentifizierter Absender aktivieren:** Der Standardwert ist **Ein**.</span><span class="sxs-lookup"><span data-stu-id="69cab-210">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="69cab-211">Um es zu deaktivieren, verschieben Sie den Umschalter auf **Aus**.</span><span class="sxs-lookup"><span data-stu-id="69cab-211">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="69cab-212">**Aktionen**: Geben Sie die Aktion für Nachrichten an, bei der spoof intelligence fehlschlagen:</span><span class="sxs-lookup"><span data-stu-id="69cab-212">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="69cab-213">**Wenn E-Mails von einer Person** gesendet werden, die Ihre Domäne nicht spoofen darf:</span><span class="sxs-lookup"><span data-stu-id="69cab-213">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="69cab-214">**Verschieben von Nachrichten in die Junk-E-Mail-Ordner der Empfänger**</span><span class="sxs-lookup"><span data-stu-id="69cab-214">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="69cab-215">**Isolieren der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="69cab-215">**Quarantine the message**</span></span>

   - <span data-ttu-id="69cab-216">**Überprüfen Sie Ihre Einstellungen:** Anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69cab-216">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="69cab-217">Sie können in jedem **Abschnitt** auf Bearbeiten klicken, um zur relevanten Seite zurück zu springen.</span><span class="sxs-lookup"><span data-stu-id="69cab-217">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="69cab-218">Sie können die folgenden  Einstellungen  direkt auf dieser Seite ein- oder ausschalten:</span><span class="sxs-lookup"><span data-stu-id="69cab-218">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="69cab-219">**Aktivieren des Antispoofingschutzes**</span><span class="sxs-lookup"><span data-stu-id="69cab-219">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="69cab-220">**Aktivieren des Features "Nicht authentifizierter Absender"**</span><span class="sxs-lookup"><span data-stu-id="69cab-220">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="69cab-221">Wenn Sie fertig sind, klicken Sie auf **einer beliebigen** Seite auf Speichern.</span><span class="sxs-lookup"><span data-stu-id="69cab-221">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="69cab-222">Überprüfen Sie auf **der Seite \<Name\>** Richtlinie bearbeiten Ihre Einstellungen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="69cab-222">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="69cab-223">Ändern der standardmäßigen Antiphishingrichtlinie mithilfe des Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="69cab-223">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="69cab-224">Die Standardmäßige Antiphishingrichtlinie heißt Office365 AntiPhish Default und wird nicht in der Liste der Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69cab-224">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="69cab-225">Gehen Sie wie folgt vor, um die Standardmäßige Antiphishingrichtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="69cab-225">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="69cab-226">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="69cab-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="69cab-227">Klicken Sie **auf der Seite Antiphishing** auf **Standardrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="69cab-227">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="69cab-228">Die **Seite Office365 AntiPhish Default** bearbeiten wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69cab-228">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="69cab-229">Die folgenden Abschnitte sind verfügbar, die identische Einstellungen für das Ändern [einer benutzerdefinierten Richtlinie enthalten.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="69cab-229">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="69cab-230">**Impersonation**</span><span class="sxs-lookup"><span data-stu-id="69cab-230">**Impersonation**</span></span>
   - <span data-ttu-id="69cab-231">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="69cab-231">**Spoof**</span></span>
   - <span data-ttu-id="69cab-232">**Erweiterte Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="69cab-232">**Advanced settings**</span></span>

   <span data-ttu-id="69cab-233">Die folgenden Einstellungen sind nicht verfügbar, wenn Sie die Standardrichtlinie ändern:</span><span class="sxs-lookup"><span data-stu-id="69cab-233">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="69cab-234">Sie können  den Abschnitt Richtlinieneinstellung und -werte  anzeigen, es gibt jedoch keinen Link Bearbeiten, sodass Sie die Einstellungen nicht ändern können (Richtlinienname, Beschreibung und für wen die Richtlinie gilt (gilt für alle Empfänger)).</span><span class="sxs-lookup"><span data-stu-id="69cab-234">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="69cab-235">Die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="69cab-235">You can't delete the default policy.</span></span>
   - <span data-ttu-id="69cab-236">Sie können die Priorität der Standardrichtlinie nicht ändern (sie wird immer zuletzt angewendet).</span><span class="sxs-lookup"><span data-stu-id="69cab-236">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="69cab-237">Überprüfen Sie **auf der Seite Office365-Standardrichtlinie** bearbeiten Ihre Einstellungen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="69cab-237">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="69cab-238">Aktivieren oder Deaktivieren benutzerdefinierter Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="69cab-238">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="69cab-239">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="69cab-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="69cab-240">Beachten Sie den Wert in der **Spalte Status:**</span><span class="sxs-lookup"><span data-stu-id="69cab-240">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="69cab-241">Verschieben Sie den Umschalter auf **Aus,** um die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="69cab-241">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="69cab-242">Verschieben Sie den Umschalter auf **Ein,** um die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="69cab-242">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="69cab-243">Sie können die standardmäßige Antiphishingrichtlinie nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="69cab-243">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="69cab-244">Festlegen der Priorität von benutzerdefinierten Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="69cab-244">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="69cab-245">Standardmäßig erhalten Antiphishingrichtlinien eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="69cab-245">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="69cab-246">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="69cab-246">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="69cab-247">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="69cab-247">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="69cab-248">Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="69cab-248">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="69cab-249">Benutzerdefinierte Antiphishingrichtlinien werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0).</span><span class="sxs-lookup"><span data-stu-id="69cab-249">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="69cab-250">Die Standardmäßige Antiphishingrichtlinie mit dem Namen Office365 AntiPhish Default hat den benutzerdefinierten Prioritätswert **Lowest**, und Sie können sie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="69cab-250">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="69cab-251">**Hinweis:** Im Security & Compliance Center können Sie die Priorität der Antiphishingrichtlinie nur ändern, nachdem Sie sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="69cab-251">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="69cab-252">In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Antiphishregel erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="69cab-252">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="69cab-253">Um die Priorität einer Richtlinie  zu ändern, klicken Sie **in** den Eigenschaften der Richtlinie  auf Priorität erhöhen oder Priorität verringern (Sie können die Prioritätsnummer im Security & Compliance Center nicht direkt ändern).</span><span class="sxs-lookup"><span data-stu-id="69cab-253">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="69cab-254">Das Ändern der Priorität einer Richtlinie ist nur sinnvoll, wenn Sie über mehrere Richtlinien verfügen.</span><span class="sxs-lookup"><span data-stu-id="69cab-254">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="69cab-255">Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP-Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="69cab-255">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="69cab-256">Wählen Sie die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="69cab-256">Select the policy that you want to modify.</span></span> <span data-ttu-id="69cab-257">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="69cab-257">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="69cab-258">Das **Flyout \<name\> "Richtlinie bearbeiten"** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69cab-258">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="69cab-259">Die benutzerdefinierte Antiphishingrichtlinie mit dem **Prioritätswert** **0** verfügt nur über die **Schaltfläche Priorität** verringern.</span><span class="sxs-lookup"><span data-stu-id="69cab-259">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="69cab-260">Die benutzerdefinierte Antiphishingrichtlinie mit dem niedrigsten **Prioritätswert** (z. B. **3**) verfügt nur über die **Schaltfläche Priorität erhöhen.**</span><span class="sxs-lookup"><span data-stu-id="69cab-260">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="69cab-261">Wenn Sie über drei oder mehr benutzerdefinierte Antiphishingrichtlinien verfügen, stehen Richtlinien zwischen den höchsten und niedrigsten Prioritätswerten sowohl die Schaltflächen **Priorität** erhöhen als auch **Priorität** verringern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="69cab-261">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="69cab-262">Klicken **Sie auf Priorität erhöhen** oder Priorität **verringern,** um den **Prioritätswert zu** ändern.</span><span class="sxs-lookup"><span data-stu-id="69cab-262">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="69cab-263">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="69cab-263">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="69cab-264">Anzeigen von Antiphishingrichtlinien mithilfe & Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="69cab-264">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="69cab-265">Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="69cab-265">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="69cab-266">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="69cab-266">Do one of the following steps:</span></span>

   - <span data-ttu-id="69cab-267">Wählen Sie eine benutzerdefinierte Antiphishingrichtlinie aus, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="69cab-267">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="69cab-268">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="69cab-268">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="69cab-269">Klicken **Sie auf Standardrichtlinie,** um die Standardmäßige Antiphishingrichtlinie anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="69cab-269">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="69cab-270">Das **Flyout \<name\> "Richtlinie** bearbeiten" wird angezeigt, in dem Sie die Einstellungen und Werte anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="69cab-270">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="69cab-271">Entfernen von Antiphishingrichtlinien mithilfe des Security & Compliance Centers</span><span class="sxs-lookup"><span data-stu-id="69cab-271">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="69cab-272">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="69cab-272">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="69cab-273">Wählen Sie die Richtlinie aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="69cab-273">Select the policy that you want to remove.</span></span> <span data-ttu-id="69cab-274">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="69cab-274">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="69cab-275">Klicken Sie **im \<name\> angezeigten** Flyout Richtlinie bearbeiten auf Richtlinie **löschen,** und klicken Sie **dann** im angezeigten Warndialogfeld auf Ja.</span><span class="sxs-lookup"><span data-stu-id="69cab-275">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="69cab-276">Die Standardrichtlinie kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="69cab-276">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="69cab-277">Verwenden Exchange Online PowerShell zum Konfigurieren von Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="69cab-277">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="69cab-278">Wie bereits beschrieben, besteht eine Antiphishingrichtlinie aus einer Antiphishrichtlinie und einer Antiphishregel.</span><span class="sxs-lookup"><span data-stu-id="69cab-278">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="69cab-279">In Exchange Online PowerShell ist der Unterschied zwischen Antiphishrichtlinien und Antiphishregeln offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="69cab-279">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="69cab-280">Sie verwalten Antiphishrichtlinien mithilfe der **\* -AntiPhishPolicy-Cmdlets,** und Sie verwalten Antiphishregeln mithilfe der **\* -AntiPhishRule-Cmdlets.**</span><span class="sxs-lookup"><span data-stu-id="69cab-280">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="69cab-281">In PowerShell erstellen Sie zuerst die Antiphishrichtlinie, dann erstellen Sie die Antiphishregel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="69cab-281">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="69cab-282">In PowerShell ändern Sie die Einstellungen in der Antiphishrichtlinie und der Antiphishregel separat.</span><span class="sxs-lookup"><span data-stu-id="69cab-282">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="69cab-283">Wenn Sie eine Antiphishrichtlinie aus PowerShell entfernen, wird die entsprechende Antiphishregel nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="69cab-283">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="69cab-284">Die folgenden PowerShell-Verfahren sind in eigenständigen EOP-Organisationen nicht verfügbar, die Exchange Online Protection PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="69cab-284">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="69cab-285">Erstellen von Antiphishingrichtlinien mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="69cab-285">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="69cab-286">Das Erstellen einer Antiphishingrichtlinie in PowerShell besteht aus zwei Stufen:</span><span class="sxs-lookup"><span data-stu-id="69cab-286">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="69cab-287">Erstellen Sie die Antiphishrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="69cab-287">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="69cab-288">Erstellen Sie die Antiphishregel, die die Antiphishrichtlinie angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="69cab-288">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="69cab-289">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="69cab-289">**Notes**:</span></span>

- <span data-ttu-id="69cab-290">Sie können eine neue Antiphishregel erstellen und ihr eine vorhandene, nicht zugeordnete Antiphishrichtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="69cab-290">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="69cab-291">Eine Antiphishregel kann nicht mehr als einer Antiphishrichtlinie zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="69cab-291">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="69cab-292">Sie können die folgenden Einstellungen für neue Antiphishrichtlinien in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="69cab-292">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="69cab-293">Erstellen Sie die neue Richtlinie als deaktiviert (_Aktiviert_ `$false` im Cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="69cab-293">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="69cab-294">Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) für das Cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="69cab-294">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="69cab-295">Eine neue Antiphishrichtlinie, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Antiphishregel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="69cab-295">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="69cab-296">Schritt 1: Erstellen einer Antiphishrichtlinie mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="69cab-296">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="69cab-297">Verwenden Sie die folgende Syntax, um eine Antiphishrichtlinie zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="69cab-297">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="69cab-298">In diesem Beispiel wird eine Phishingrichtlinie mit dem Namen "Research Quarantine" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="69cab-298">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="69cab-299">Die Beschreibung ist: Research department policy.</span><span class="sxs-lookup"><span data-stu-id="69cab-299">The description is: Research department policy.</span></span>
- <span data-ttu-id="69cab-300">Ändert die Standardaktion für Spoofing in Quarantäne.</span><span class="sxs-lookup"><span data-stu-id="69cab-300">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="69cab-301">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="69cab-301">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="69cab-302">Schritt 2: Erstellen einer Antiphishregel mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="69cab-302">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="69cab-303">Verwenden Sie die folgende Syntax, um eine Antiphishregel zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="69cab-303">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="69cab-304">In diesem Beispiel wird eine Antiphishregel namens "Research Department" mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="69cab-304">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="69cab-305">Die Regel ist der Antiphishrichtlinie "Research Quarantine" zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="69cab-305">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="69cab-306">Die Regel gilt für Mitglieder der Gruppe „Research Department“.</span><span class="sxs-lookup"><span data-stu-id="69cab-306">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="69cab-307">Da wir den Parameter _Priority_ nicht verwenden, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="69cab-307">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="69cab-308">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="69cab-308">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="69cab-309">Anzeigen von Antiphishrichtlinien mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="69cab-309">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="69cab-310">Verwenden Sie die folgende Syntax, um vorhandene Antiphishrichtlinien anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="69cab-310">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="69cab-311">In diesem Beispiel wird eine Zusammenfassungsliste aller Antiphishrichtlinien zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="69cab-311">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="69cab-312">In diesem Beispiel werden alle Eigenschaftswerte für die Antiphishrichtlinie "Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="69cab-312">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="69cab-313">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="69cab-313">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="69cab-314">Anzeigen von Antiphishregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="69cab-314">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="69cab-315">Verwenden Sie die folgende Syntax, um vorhandene Antiphishregeln anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="69cab-315">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="69cab-316">In diesem Beispiel wird eine Zusammenfassungsliste aller Antiphishregeln zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="69cab-316">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="69cab-317">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="69cab-317">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="69cab-318">In diesem Beispiel werden alle Eigenschaftswerte für die Antiphishregel namens Contoso Executives zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="69cab-318">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="69cab-319">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="69cab-319">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="69cab-320">Verwenden von PowerShell zum Ändern von Antiphishrichtlinien</span><span class="sxs-lookup"><span data-stu-id="69cab-320">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="69cab-321">Neben den folgenden Elementen sind dieselben Einstellungen verfügbar, wenn Sie eine Antiphishrichtlinie in PowerShell ändern, als wenn Sie eine Richtlinie wie in [Schritt 1:](#step-1-use-powershell-to-create-an-anti-phish-policy) Verwenden von PowerShell beschrieben erstellen, um eine Antiphishrichtlinie weiter oben in diesem Artikel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="69cab-321">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="69cab-322">Die _MakeDefault-Option,_ die die angegebene Richtlinie in die  Standardrichtlinie umstellt (auf alle Benutzer angewendet, immer niedrigste Priorität, und Sie können sie nicht löschen) ist nur verfügbar, wenn Sie eine Antiphishrichtlinie in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="69cab-322">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="69cab-323">Sie können eine Antiphishrichtlinie nicht umbenennen (das **Cmdlet Set-AntiPhishPolicy** hat keinen _Name-Parameter)._</span><span class="sxs-lookup"><span data-stu-id="69cab-323">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="69cab-324">Wenn Sie eine Antiphishingrichtlinie im Security & Compliance Center umbenennen, benennen Sie nur die Antiphishingregel _um._</span><span class="sxs-lookup"><span data-stu-id="69cab-324">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="69cab-325">Verwenden Sie die folgende Syntax, um eine Antiphishrichtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="69cab-325">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="69cab-326">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="69cab-326">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="69cab-327">Verwenden von PowerShell zum Ändern von Antiphishregeln</span><span class="sxs-lookup"><span data-stu-id="69cab-327">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="69cab-328">Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine Antiphishregel in PowerShell ändern, ist der _Parameter Enabled,_ mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="69cab-328">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="69cab-329">Informationen zum Aktivieren oder Deaktivieren vorhandener Antiphishregeln finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="69cab-329">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="69cab-330">Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine Regel erstellen, wie im Abschnitt Schritt 2: Verwenden von PowerShell beschrieben, um eine [Antiphishregel](#step-2-use-powershell-to-create-an-anti-phish-rule) weiter oben in diesem Artikel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="69cab-330">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="69cab-331">Verwenden Sie die folgende Syntax, um eine Antiphishregel zu ändern:</span><span class="sxs-lookup"><span data-stu-id="69cab-331">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="69cab-332">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="69cab-332">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="69cab-333">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Antiphishregeln</span><span class="sxs-lookup"><span data-stu-id="69cab-333">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="69cab-334">Durch Aktivieren oder Deaktivieren einer Antiphishregel in PowerShell wird die gesamte Antiphishingrichtlinie (die Antiphishregel und die zugewiesene Antiphishingrichtlinie) aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="69cab-334">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="69cab-335">Sie können die standardmäßige Antiphishingrichtlinie nicht aktivieren oder deaktivieren (sie wird immer auf alle Empfänger angewendet).</span><span class="sxs-lookup"><span data-stu-id="69cab-335">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="69cab-336">Verwenden Sie die folgende Syntax, um eine #A0 in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="69cab-336">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="69cab-337">In diesem Beispiel wird die Antiphishregel "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="69cab-337">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="69cab-338">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="69cab-338">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="69cab-339">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) und [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="69cab-339">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="69cab-340">Festlegen der Priorität von Antiphishregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="69cab-340">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="69cab-341">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="69cab-341">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="69cab-342">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="69cab-342">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="69cab-343">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="69cab-343">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="69cab-344">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="69cab-344">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="69cab-345">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="69cab-345">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="69cab-346">Verwenden Sie die folgende Syntax, um die Priorität einer #A0 in PowerShell zu setzen:</span><span class="sxs-lookup"><span data-stu-id="69cab-346">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="69cab-p138">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="69cab-p138">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="69cab-349">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="69cab-349">**Notes**:</span></span>

- <span data-ttu-id="69cab-350">Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den _Parameter Priority_ im Cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="69cab-350">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="69cab-351">Die Standardmäßige Antiphishrichtlinie verfügt nicht über eine entsprechende Antiphishregel und hat immer den nicht veränderbaren Prioritätswert **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="69cab-351">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="69cab-352">Entfernen von Antiphishrichtlinien mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="69cab-352">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="69cab-353">Wenn Sie PowerShell verwenden, um eine Antiphishrichtlinie zu entfernen, wird die entsprechende Antiphishregel nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="69cab-353">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="69cab-354">Verwenden Sie die folgende Syntax, um eine #A0 in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="69cab-354">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="69cab-355">In diesem Beispiel wird die Antiphishrichtlinie "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="69cab-355">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="69cab-356">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="69cab-356">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="69cab-357">Entfernen von Antiphishregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="69cab-357">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="69cab-358">Wenn Sie PowerShell verwenden, um eine Antiphishregel zu entfernen, wird die entsprechende Antiphishrichtlinie nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="69cab-358">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="69cab-359">Verwenden Sie die folgende Syntax, um eine #A0 in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="69cab-359">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="69cab-360">In diesem Beispiel wird die Antiphishregel "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="69cab-360">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="69cab-361">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="69cab-361">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="69cab-362">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="69cab-362">How do you know these procedures worked?</span></span>

<span data-ttu-id="69cab-363">Gehen Sie wie folgt vor, um zu überprüfen, ob Sie die Antiphishingrichtlinien in Microsoft Defender for Office 365 erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="69cab-363">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="69cab-364">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.</span><span class="sxs-lookup"><span data-stu-id="69cab-364">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="69cab-365">Überprüfen Sie die Liste der Richtlinien, ihre **Statuswerte** und ihre **Priority-Werte.**</span><span class="sxs-lookup"><span data-stu-id="69cab-365">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="69cab-366">Gehen Sie wie folgt vor, um weitere Details anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="69cab-366">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="69cab-367">Wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="69cab-367">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="69cab-368">Klicken **Sie auf Standardrichtlinie,** und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="69cab-368">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="69cab-369">Ersetzen Exchange Online PowerShell durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie \<Name\> die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="69cab-369">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```