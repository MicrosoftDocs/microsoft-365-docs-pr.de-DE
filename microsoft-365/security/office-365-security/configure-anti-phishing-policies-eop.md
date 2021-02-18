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
description: Administratoren können erfahren, wie Sie die Antiphishingrichtlinien erstellen, ändern und löschen, die in Exchange Online Protection (EOP)-Organisationen mit oder ohne Exchange Online-Postfächer verfügbar sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5bab5e791cb58c4e681a802179583471bb6ab165
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287913"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="0ff26-103">Konfigurieren von Anti-Phishing-Richtlinien in EOP</span><span class="sxs-lookup"><span data-stu-id="0ff26-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0ff26-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="0ff26-104">**Applies to**</span></span>
- [<span data-ttu-id="0ff26-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0ff26-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="0ff26-106">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer gibt es eine standardmäßige Antiphishingrichtlinie, die eine begrenzte Anzahl von Standardmäßig aktivierten Antis spoofing-Funktionen enthält.</span><span class="sxs-lookup"><span data-stu-id="0ff26-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="0ff26-107">Weitere Informationen finden Sie unter ["Spoofing"-Einstellungen in Antiphishingrichtlinien.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="0ff26-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="0ff26-108">Administratoren können die standardmäßige Antiphishingrichtlinie anzeigen, bearbeiten und konfigurieren (aber nicht löschen).</span><span class="sxs-lookup"><span data-stu-id="0ff26-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="0ff26-109">Für eine höhere Granularität können Sie auch benutzerdefinierte Antiphishingrichtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="0ff26-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="0ff26-110">Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="0ff26-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="0ff26-111">Organisationen mit Exchange Online-Postfächern können Antiphishingrichtlinien im Security & Compliance Center oder in Exchange Online PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0ff26-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="0ff26-112">Eigenständige EOP-Organisationen können nur das Security & Compliance Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ff26-112">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="0ff26-113">Informationen zum Erstellen und Ändern der erweiterten Antiphishingrichtlinien in Microsoft Defender für Office 365, die in Defender für Office 365 verfügbar sind, finden Sie unter Konfigurieren von [Antiphishingrichtlinien in Microsoft Defender für Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0ff26-113">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="0ff26-114">Die grundlegenden Elemente einer Antiphishingrichtlinie sind:</span><span class="sxs-lookup"><span data-stu-id="0ff26-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="0ff26-115">**Die Antiphishingrichtlinie:** Gibt die zu aktivierenden oder zu deaktivierenden Phishingschutzmaßnahmen sowie die Aktionen zum Anwenden von Optionen an.</span><span class="sxs-lookup"><span data-stu-id="0ff26-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="0ff26-116">**Die Antiphishregel:** Gibt die Prioritäts- und Empfängerfilter (für wen die Richtlinie gilt) für eine Anti-Phishing-Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="0ff26-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="0ff26-117">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Antiphishingrichtlinien im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="0ff26-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="0ff26-118">Wenn Sie eine Antiphishingrichtlinie erstellen, erstellen Sie tatsächlich eine Antiphishingregel und die zugeordnete Antiphishingrichtlinie gleichzeitig mit demselben Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="0ff26-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="0ff26-119">Wenn Sie eine Antiphishingrichtlinie ändern, ändern Einstellungen im Zusammenhang mit Name, Priorität, aktiviert oder deaktiviert und Empfängerfilter die Antiphishingregel.</span><span class="sxs-lookup"><span data-stu-id="0ff26-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="0ff26-120">Alle anderen Einstellungen ändern die zugeordnete Anti-Phishing-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="0ff26-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="0ff26-121">Wenn Sie eine Antiphishingrichtlinie entfernen, werden die Antiphishingregel und die zugehörige Antiphishingrichtlinie entfernt.</span><span class="sxs-lookup"><span data-stu-id="0ff26-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="0ff26-122">In Exchange Online PowerShell verwalten Sie die Richtlinie und die Regel separat.</span><span class="sxs-lookup"><span data-stu-id="0ff26-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="0ff26-123">Weitere Informationen finden Sie im Abschnitt "Verwenden von [Exchange Online PowerShell zum Konfigurieren von Antiphishingrichtlinien"](#use-exchange-online-powershell-to-configure-anti-phishing-policies) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="0ff26-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="0ff26-124">Jede Organisation verfügt über eine integrierte Antiphishingrichtlinie namens Office365 AntiPhish Default, die über die folgenden Eigenschaften verfügt:</span><span class="sxs-lookup"><span data-stu-id="0ff26-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="0ff26-125">Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine Anti-Phishing-Regel (Empfängerfilter) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0ff26-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="0ff26-126">Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet).</span><span class="sxs-lookup"><span data-stu-id="0ff26-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="0ff26-127">Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität.</span><span class="sxs-lookup"><span data-stu-id="0ff26-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="0ff26-128">Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="0ff26-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="0ff26-129">Um die Effektivität des Antiphishingschutzes zu erhöhen, können Sie benutzerdefinierte Antiphishingrichtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ff26-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0ff26-130">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="0ff26-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0ff26-131">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="0ff26-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0ff26-132">Um direkt zur **Antiphishingseite zu** wechseln, verwenden Sie <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="0ff26-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="0ff26-133">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0ff26-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="0ff26-134">Sie können keine Antiphishingrichtlinien in der eigenständigen EOP PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="0ff26-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="0ff26-135">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="0ff26-135">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="0ff26-136">Zum Hinzufügen, Ändern und Löschen von Antiphishingrichtlinien müssen Sie Mitglied der Rollengruppe **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.</span><span class="sxs-lookup"><span data-stu-id="0ff26-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="0ff26-137">Für den schreibgeschützten Zugriff auf Antiphishingrichtlinien müssen  Sie Mitglied der Rollengruppe "Globaler Leser" oder **"Sicherheitsleseprogramm"** <sup>\*</sup> sein.</span><span class="sxs-lookup"><span data-stu-id="0ff26-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="0ff26-138">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0ff26-138">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="0ff26-139">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="0ff26-139">**Notes**:</span></span>

  - <span data-ttu-id="0ff26-140">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0ff26-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0ff26-141">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0ff26-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="0ff26-142">Die **Rollengruppe "Organisationsverwaltung nur** anzeigen" in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) bietet auch schreibgeschützten Zugriff auf das <sup>\*</sup> Feature.</span><span class="sxs-lookup"><span data-stu-id="0ff26-142">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="0ff26-143"><sup>\*</sup> Im Security & Compliance Center können Benutzer mit schreibgeschützten Zugriff die Einstellungen benutzerdefinierter Antiphishingrichtlinien anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0ff26-143"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="0ff26-144">Schreibgeschützte Benutzer können die Einstellungen in der standardmäßigen Antiphishingrichtlinie nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="0ff26-144">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="0ff26-145">Um Antiphishingrichtlinien in EOP als eigenständige Lösung zu erstellen und zu ändern, müssen Sie etwas tun, das eine _Hydratation_ für Ihren Mandanten erfordert.</span><span class="sxs-lookup"><span data-stu-id="0ff26-145">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="0ff26-146">In der Exchange Admin Center (EAC) können  Sie beispielsweise zur Registerkarte "Berechtigungen" wechseln, eine vorhandene Rollengruppe auswählen, auf das Symbol "Bearbeiten" klicken und eine Rolle entfernen (die Sie letztendlich wieder  ![ ](../../media/ITPro-EAC-EditIcon.png) hinzufügen).</span><span class="sxs-lookup"><span data-stu-id="0ff26-146">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="0ff26-147">Wenn Ihr Mandant noch nie aktivieren wurde, erhalten Sie ein Dialogfeld namens "Organisationseinstellungen aktualisieren" mit einer Statusleiste, die erfolgreich abgeschlossen werden sollte. </span><span class="sxs-lookup"><span data-stu-id="0ff26-147">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="0ff26-148">Weitere Informationen zur Hydratation finden Sie im [Cmdlet "Enable-OrganizationCustomization"](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (das in der eigenständigen EOP PowerShell oder im Security & Compliance Center nicht verfügbar ist).</span><span class="sxs-lookup"><span data-stu-id="0ff26-148">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="0ff26-149">Die empfohlenen Einstellungen für Antiphishingrichtlinien finden Sie unter [EOP Default Anti-Phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="0ff26-149">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="0ff26-150">Es kann bis zu 30 Minuten dauern, bis die aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ff26-150">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="0ff26-151">Informationen dazu, wo Antiphishingrichtlinien in der Filterpipeline angewendet werden, finden Sie unter "Reihenfolge und [Rangfolge des E-Mail-Schutzes".](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="0ff26-151">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="0ff26-152">Verwenden des Security & Compliance Center zum Erstellen von Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0ff26-152">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="0ff26-153">Beim Erstellen einer benutzerdefinierten Antiphishingrichtlinie im Security & Compliance Center werden die Antiphishingregel und die zugeordnete Antiphishingrichtlinie gleichzeitig mit demselben Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="0ff26-153">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="0ff26-154">Wenn Sie eine Antiphishingrichtlinie erstellen, können Sie nur den Richtliniennamen, die Beschreibung und den Empfängerfilter angeben, der identifiziert, auf wen die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ff26-154">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="0ff26-155">Nachdem Sie die Richtlinie erstellt haben, können Sie die Richtlinie ändern, um die standardmäßigen Antiphishingeinstellungen zu ändern oder zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0ff26-155">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="0ff26-156">Wechseln Sie im Security & Compliance Center zu **"Bedrohungsverwaltungsrichtlinie** \>  \> **Antiphishing".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="0ff26-157">Klicken Sie **auf der Seite "Antiphishing"** auf **"Erstellen".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-157">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="0ff26-158">Der **Assistent zum Erstellen einer neuen Antiphishingrichtlinie wird** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="0ff26-158">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="0ff26-159">Konfigurieren Sie **auf der Seite "Ihre Richtlinie benennen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="0ff26-159">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="0ff26-160">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="0ff26-160">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="0ff26-161">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="0ff26-161">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="0ff26-162">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0ff26-162">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0ff26-163">Identifizieren Sie **auf der angezeigten** Seite "Angewendet auf" die internen Empfänger, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ff26-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="0ff26-164">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="0ff26-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="0ff26-165">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="0ff26-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="0ff26-166">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="0ff26-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="0ff26-167">Klicken **Sie auf Bedingung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0ff26-167">Click **Add a condition**.</span></span> <span data-ttu-id="0ff26-168">Wählen Sie in der angezeigten Dropdownliste eine Bedingung unter **"Angewendet" aus, wenn:**</span><span class="sxs-lookup"><span data-stu-id="0ff26-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="0ff26-169">**Der Empfänger ist:** Gibt ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="0ff26-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="0ff26-170">**Der Empfänger ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="0ff26-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="0ff26-171">**Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="0ff26-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="0ff26-172">Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **Beliebigen dieser Kontrollkästchen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0ff26-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="0ff26-173">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der werte aus.</span><span class="sxs-lookup"><span data-stu-id="0ff26-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="0ff26-174">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="0ff26-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="0ff26-175">Wenn Sie weitere Werte hinzufügen möchten, klicken Sie in einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="0ff26-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="0ff26-176">Klicken Sie zum Entfernen einzelner Einträge **auf** das Symbol ![ ](../../media/scc-remove-icon.png) "Entfernen" für den Wert.</span><span class="sxs-lookup"><span data-stu-id="0ff26-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="0ff26-177">Um die gesamte Bedingung zu entfernen, **klicken** Sie in der Bedingung ![ auf ](../../media/scc-remove-icon.png) "Entfernen".</span><span class="sxs-lookup"><span data-stu-id="0ff26-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="0ff26-178">Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf "Bedingung **hinzufügen",** und wählen Sie unter **"Angewendet"** einen verbleibenden Wert aus, wenn .</span><span class="sxs-lookup"><span data-stu-id="0ff26-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="0ff26-179">Klicken Sie zum Hinzufügen von Ausnahmen auf **"Bedingung hinzufügen",** und wählen Sie unter "Außer wenn" **eine Ausnahme aus.**</span><span class="sxs-lookup"><span data-stu-id="0ff26-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="0ff26-180">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="0ff26-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="0ff26-181">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0ff26-181">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0ff26-182">Überprüfen Sie **ihre Einstellungen auf** der angezeigten Seite "Einstellungen überprüfen".</span><span class="sxs-lookup"><span data-stu-id="0ff26-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="0ff26-183">Sie können **in** jeder Einstellung auf "Bearbeiten" klicken, um sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0ff26-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="0ff26-184">Klicken Sie nach Abschluss des Abschlusses auf **"Diese Richtlinie erstellen".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-184">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="0ff26-185">Klicken Sie im angezeigten Bestätigungsdialogfeld auf **"OK".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-185">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="0ff26-186">Nachdem Sie die Antiphishingrichtlinie mit diesen allgemeinen Richtlinieneinstellungen erstellt haben, konfigurieren Sie mithilfe der Anweisungen im nächsten Abschnitt die Schutzeinstellungen in der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="0ff26-186">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="0ff26-187">Verwenden des Security & Compliance Center zum Ändern von Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0ff26-187">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="0ff26-188">Verwenden Sie die folgenden Verfahren, um Antiphishingrichtlinien zu ändern: eine neue Richtlinie, die Sie erstellt haben, oder vorhandene Richtlinien, die Sie bereits angepasst haben.</span><span class="sxs-lookup"><span data-stu-id="0ff26-188">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="0ff26-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="0ff26-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="0ff26-190">Wählen Sie die benutzerdefinierte Antiphishingrichtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="0ff26-190">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="0ff26-191">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="0ff26-191">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0ff26-192">Das **Flyout \<name\> "Richtlinie bearbeiten"** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0ff26-192">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="0ff26-193">Wenn Sie in **einem** beliebigen Abschnitt auf "Bearbeiten" klicken, können Sie auf die Einstellungen in diesem Abschnitt zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0ff26-193">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="0ff26-194">Die folgenden Schritte werden in der Reihenfolge dargestellt, in der die Abschnitte angezeigt werden, sie sind jedoch nicht sequenziell (Sie können die Abschnitte in beliebiger Reihenfolge auswählen und ändern).</span><span class="sxs-lookup"><span data-stu-id="0ff26-194">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="0ff26-195">Nachdem Sie **in** einem Abschnitt auf "Bearbeiten" geklickt haben, werden die verfügbaren Einstellungen in  einem Assistentenformat angezeigt.  Sie können jedoch in beliebiger Reihenfolge innerhalb der Seiten wechseln, und Sie können auf einer beliebigen Seite auf "Speichern" klicken (oder  ![ ](../../media/scc-remove-icon.png) **\<name\>** auf das Symbol "Abbrechen" oder "Schließen" klicken, um zur Seite "Richtlinie bearbeiten" zurückzukehren (Sie müssen nicht die letzte Seite des Assistenten zum Speichern oder Verlassen besuchen).</span><span class="sxs-lookup"><span data-stu-id="0ff26-195">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="0ff26-196">**Richtlinieneinstellung:** Klicken Sie auf "Bearbeiten", um dieselben Einstellungen zu ändern, die beim Erstellen der Richtlinie [im](#use-the-security--compliance-center-to-create-anti-phishing-policies) vorherigen Abschnitt verfügbar waren: </span><span class="sxs-lookup"><span data-stu-id="0ff26-196">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="0ff26-197">**Name**</span><span class="sxs-lookup"><span data-stu-id="0ff26-197">**Name**</span></span>
   - <span data-ttu-id="0ff26-198">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0ff26-198">**Description**</span></span>
   - <span data-ttu-id="0ff26-199">**Angewendet auf**</span><span class="sxs-lookup"><span data-stu-id="0ff26-199">**Applied to**</span></span>
   - <span data-ttu-id="0ff26-200">**Überprüfen Ihrer Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="0ff26-200">**Review your settings**</span></span>

   <span data-ttu-id="0ff26-201">Wenn Sie fertig sind, klicken Sie auf einer **beliebigen** Seite auf "Speichern".</span><span class="sxs-lookup"><span data-stu-id="0ff26-201">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="0ff26-202">**Spoofing**  : Klicken Sie auf "Bearbeiten", um die Spoofintelligenz zu aktivieren oder zu deaktivieren, die Identifizierung nicht authentifizierter Absender in Outlook ein- oder auszuschalten und die Aktion so zu konfigurieren, dass sie auf Nachrichten von blockierten gefälschten Absendern angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ff26-202">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="0ff26-203">Weitere Informationen finden Sie unter ["Spoofing"-Einstellungen in Antiphishingrichtlinien.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="0ff26-203">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="0ff26-204">Beachten Sie, dass dieselben Einstellungen auch in Antiphishingrichtlinien in Defender für Office 365 verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0ff26-204">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="0ff26-205">**Spoofingfiltereinstellungen:** Der Standardwert ist **"Ein",** und es wird empfohlen, ihn zu be lassen.</span><span class="sxs-lookup"><span data-stu-id="0ff26-205">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="0ff26-206">Um sie zu deaktivieren, ziehen Sie den Umschalter auf **"Aus".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-206">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="0ff26-207">Weitere Informationen finden Sie unter [Konfigurieren der Spoofintelligenz in EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="0ff26-207">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="0ff26-208">Sie müssen den Antis spoofingschutz nicht deaktivieren, wenn Ihr #A0 nicht auf Microsoft 365 verweisen kann. stattdessen aktivieren Sie die erweiterte Filterung für Connectors.</span><span class="sxs-lookup"><span data-stu-id="0ff26-208">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="0ff26-209">Anweisungen finden Sie unter ["Erweiterte Filterung für Connectors in Exchange Online".](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="0ff26-209">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="0ff26-210">**Feature "Nicht authentifizierter Absender aktivieren":** Der Standardwert ist **"On".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-210">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="0ff26-211">Um sie zu deaktivieren, ziehen Sie den Umschalter auf **"Aus".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-211">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="0ff26-212">**Aktionen:** Geben Sie die Aktion an, die für Nachrichten mit Spoofingintelligenz ausführen soll:</span><span class="sxs-lookup"><span data-stu-id="0ff26-212">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="0ff26-213">Wenn eine E-Mail von einer Person gesendet wird, die nicht zum **Spoofing Ihrer Domäne zugelassen ist:**</span><span class="sxs-lookup"><span data-stu-id="0ff26-213">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="0ff26-214">**Nachricht in die Junk-E-Mail-Ordner der Empfänger verschieben**</span><span class="sxs-lookup"><span data-stu-id="0ff26-214">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="0ff26-215">**Isolieren der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="0ff26-215">**Quarantine the message**</span></span>

   - <span data-ttu-id="0ff26-216">**Überprüfen Sie Ihre Einstellungen:** Anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0ff26-216">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="0ff26-217">Sie können in jedem Abschnitt **auf** "Bearbeiten" klicken, um zur entsprechenden Seite zurück zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="0ff26-217">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="0ff26-218">Sie können die folgenden Einstellungen  **direkt** auf dieser Seite ein- oder ausschalten:</span><span class="sxs-lookup"><span data-stu-id="0ff26-218">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="0ff26-219">**Aktivieren des Antispoofingschutzes**</span><span class="sxs-lookup"><span data-stu-id="0ff26-219">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="0ff26-220">**Feature "Nicht authentifizierter Absender aktivieren"**</span><span class="sxs-lookup"><span data-stu-id="0ff26-220">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="0ff26-221">Wenn Sie fertig sind, klicken Sie auf einer **beliebigen** Seite auf "Speichern".</span><span class="sxs-lookup"><span data-stu-id="0ff26-221">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="0ff26-222">Überprüfen Sie auf **der Seite "Richtlinie bearbeiten" \<Name\>** Ihre Einstellungen, und klicken Sie dann auf **"Schließen".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-222">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="0ff26-223">Ändern der standardmäßigen Antiphishingrichtlinie mithilfe des Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="0ff26-223">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="0ff26-224">Die standardmäßige Antiphishingrichtlinie heißt Office365 AntiPhish Default und wird nicht in der Liste der Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0ff26-224">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="0ff26-225">Gehen Sie wie folgt vor, um die standardmäßige Antiphishingrichtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="0ff26-225">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="0ff26-226">Wechseln Sie im Security & Compliance Center zu **"Bedrohungsverwaltungsrichtlinie** \>  \> **Antiphishing".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="0ff26-227">Klicken Sie **auf der Seite "Antiphishing"** auf **"Standardrichtlinie".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-227">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="0ff26-228">Die **Seite "Office365-Antiphish-Standard** bearbeiten" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0ff26-228">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="0ff26-229">Die folgenden Abschnitte sind verfügbar, die identische Einstellungen für das Ändern [einer benutzerdefinierten Richtlinie enthalten.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="0ff26-229">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="0ff26-230">**Impersonation**</span><span class="sxs-lookup"><span data-stu-id="0ff26-230">**Impersonation**</span></span>
   - <span data-ttu-id="0ff26-231">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="0ff26-231">**Spoof**</span></span>
   - <span data-ttu-id="0ff26-232">**Erweiterte Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="0ff26-232">**Advanced settings**</span></span>

   <span data-ttu-id="0ff26-233">Die folgenden Einstellungen sind nicht verfügbar, wenn Sie die Standardrichtlinie ändern:</span><span class="sxs-lookup"><span data-stu-id="0ff26-233">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="0ff26-234">Sie können  den Abschnitt und die Werte der  Richtlinieneinstellung anzeigen, aber es gibt keinen Link "Bearbeiten", sodass Sie die Einstellungen (Richtlinienname, Beschreibung und Für wen die Richtlinie gilt (gilt für alle Empfänger) nicht ändern können.</span><span class="sxs-lookup"><span data-stu-id="0ff26-234">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="0ff26-235">Die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="0ff26-235">You can't delete the default policy.</span></span>
   - <span data-ttu-id="0ff26-236">Sie können die Priorität der Standardrichtlinie nicht ändern (sie wird immer zuletzt angewendet).</span><span class="sxs-lookup"><span data-stu-id="0ff26-236">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="0ff26-237">Überprüfen Sie **auf der Seite "Office365-Antiphish-Standardrichtlinie** bearbeiten" Ihre Einstellungen, und klicken Sie dann auf **"Schließen".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-237">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="0ff26-238">Aktivieren oder Deaktivieren von benutzerdefinierten Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0ff26-238">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="0ff26-239">Wechseln Sie im Security & Compliance Center zu **"Bedrohungsverwaltungsrichtlinie** \>  \> **Antiphishing".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="0ff26-240">Beachten Sie den  Wert in der Statusspalte:</span><span class="sxs-lookup"><span data-stu-id="0ff26-240">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="0ff26-241">Ziehen Sie den Umschalter **auf "Aus",** um die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0ff26-241">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="0ff26-242">Ziehen Sie den Umschalter auf **"Ein",** um die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0ff26-242">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="0ff26-243">Sie können die standardmäßige Antiphishingrichtlinie nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0ff26-243">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="0ff26-244">Festlegen der Priorität von benutzerdefinierten Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0ff26-244">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="0ff26-245">Standardmäßig erhalten Antiphishingrichtlinien eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="0ff26-245">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="0ff26-246">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="0ff26-246">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="0ff26-247">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="0ff26-247">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="0ff26-248">Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="0ff26-248">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="0ff26-249">Benutzerdefinierte Antiphishingrichtlinien werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0).</span><span class="sxs-lookup"><span data-stu-id="0ff26-249">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="0ff26-250">Die standardmäßige Antiphishingrichtlinie namens Office365 AntiPhish Default hat den benutzerdefinierten Prioritätswert **"Niedrigste",** und Sie können ihn nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="0ff26-250">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="0ff26-251">**Hinweis:** Im Security & Compliance Center können Sie die Priorität der Anti-Phishing-Richtlinie erst ändern, nachdem Sie sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="0ff26-251">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="0ff26-252">In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Antiphishregel erstellen (die sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="0ff26-252">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="0ff26-253">Um die Priorität einer Richtlinie  zu ändern, klicken Sie **in** den Eigenschaften der Richtlinie  auf "Priorität erhöhen" oder "Priorität verringern" (Sie können die Prioritätsnummer im Security & Compliance Center nicht direkt ändern).</span><span class="sxs-lookup"><span data-stu-id="0ff26-253">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="0ff26-254">Das Ändern der Priorität einer Richtlinie ist nur sinnvoll, wenn Sie über mehrere Richtlinien verfügen.</span><span class="sxs-lookup"><span data-stu-id="0ff26-254">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="0ff26-255">Wechseln Sie im Security & Compliance  Center zur \>  \> **Atp-Antiphishing-Richtlinie zur Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="0ff26-255">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0ff26-256">Wählen Sie die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="0ff26-256">Select the policy that you want to modify.</span></span> <span data-ttu-id="0ff26-257">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="0ff26-257">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0ff26-258">Das **Flyout \<name\> "Richtlinie bearbeiten"** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0ff26-258">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="0ff26-259">Für die benutzerdefinierte Antiphishingrichtlinie mit dem **Prioritätswert** **0** ist nur die Schaltfläche "Priorität **verringern"** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0ff26-259">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="0ff26-260">Für die benutzerdefinierte Antiphishingrichtlinie mit dem niedrigsten Prioritätswert (z. B. **3)** ist nur die Schaltfläche "Priorität  **erhöhen"** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0ff26-260">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="0ff26-261">Wenn Sie über drei oder mehr benutzerdefinierte Antiphishingrichtlinien verfügen, verfügen Richtlinien  zwischen dem höchsten und dem niedrigsten Prioritätswert über die Schaltflächen "Priorität erhöhen" und **"Priorität** verringern".</span><span class="sxs-lookup"><span data-stu-id="0ff26-261">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="0ff26-262">Klicken **Sie auf "Priorität erhöhen"** oder **"Priorität verringern",** um den **Prioritätswert zu** ändern.</span><span class="sxs-lookup"><span data-stu-id="0ff26-262">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="0ff26-263">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="0ff26-263">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="0ff26-264">Verwenden des Security & Compliance Center zum Anzeigen von Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0ff26-264">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="0ff26-265">Wechseln Sie im Security & Compliance Center zu "Threat **management** \> **Policy** \> **Anti-phishing".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-265">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="0ff26-266">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="0ff26-266">Do one of the following steps:</span></span>

   - <span data-ttu-id="0ff26-267">Wählen Sie eine benutzerdefinierte Antiphishingrichtlinie aus, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="0ff26-267">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="0ff26-268">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="0ff26-268">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="0ff26-269">Klicken **Sie auf "Standardrichtlinie",** um die standardmäßige Antiphishingrichtlinie anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0ff26-269">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="0ff26-270">Das **Flyout \<name\> "Richtlinie bearbeiten"** wird angezeigt, in dem Sie die Einstellungen und Werte anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="0ff26-270">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="0ff26-271">Verwenden des Security & Compliance Centers zum Entfernen von Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0ff26-271">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="0ff26-272">Wechseln Sie im Security & Compliance Center zu **"Bedrohungsverwaltungsrichtlinie** \>  \> **Antiphishing".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-272">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="0ff26-273">Wählen Sie die Richtlinie aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="0ff26-273">Select the policy that you want to remove.</span></span> <span data-ttu-id="0ff26-274">Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.</span><span class="sxs-lookup"><span data-stu-id="0ff26-274">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0ff26-275">Klicken Sie **im \<name\> angezeigten** Flyout "Richtlinie bearbeiten" auf "Richtlinie löschen", und klicken Sie dann **im** angezeigten Warndialogfeld auf "Ja".</span><span class="sxs-lookup"><span data-stu-id="0ff26-275">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="0ff26-276">Die Standardrichtlinie kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="0ff26-276">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="0ff26-277">Verwenden von Exchange Online PowerShell zum Konfigurieren von Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0ff26-277">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="0ff26-278">Wie zuvor beschrieben, besteht eine Antiphishingrichtlinie aus einer Antiphishingrichtlinie und einer Antiphishingregel.</span><span class="sxs-lookup"><span data-stu-id="0ff26-278">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="0ff26-279">In Exchange Online PowerShell ist der Unterschied zwischen Anti-Phish-Richtlinien und Anti-Phishing-Regeln offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="0ff26-279">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="0ff26-280">Sie verwalten Antiphiishrichtlinien mithilfe der **\* Cmdlets "-AntiPhishPolicy",** und Sie verwalten Antiphiishregeln mithilfe der **\* -AntiPhishRule-Cmdlets.**</span><span class="sxs-lookup"><span data-stu-id="0ff26-280">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="0ff26-281">In PowerShell erstellen Sie zuerst die Anti phish-Richtlinie, dann erstellen Sie die Anti-Phish-Regel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ff26-281">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="0ff26-282">In PowerShell ändern Sie die Einstellungen in der Anti-Phish-Richtlinie und der Anti-Phish-Regel separat.</span><span class="sxs-lookup"><span data-stu-id="0ff26-282">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="0ff26-283">Wenn Sie eine Anti-Phish-Richtlinie aus PowerShell entfernen, wird die entsprechende Antiphishregel nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="0ff26-283">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="0ff26-284">Die folgenden PowerShell-Verfahren sind in eigenständigen EOP-Organisationen, die Exchange Online Protection PowerShell verwenden, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0ff26-284">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="0ff26-285">Verwenden von PowerShell zum Erstellen von Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0ff26-285">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="0ff26-286">Das Erstellen einer Antiphishingrichtlinie in PowerShell besteht aus zwei Schritte:</span><span class="sxs-lookup"><span data-stu-id="0ff26-286">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="0ff26-287">Erstellen Sie die Anti-Phish-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="0ff26-287">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="0ff26-288">Erstellen Sie die Anti phish-Regel, die die Anti-Phish-Richtlinie angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ff26-288">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="0ff26-289">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="0ff26-289">**Notes**:</span></span>

- <span data-ttu-id="0ff26-290">Sie können eine neue Anti phish-Regel erstellen und ihr eine vorhandene, nicht zugeordnete Anti phish-Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0ff26-290">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="0ff26-291">Eine Anti-Phish-Regel kann nicht mehreren Anti-Phishing-Richtlinien zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="0ff26-291">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="0ff26-292">Sie können die folgenden Einstellungen für neue Anti-Phishing-Richtlinien in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="0ff26-292">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="0ff26-293">Erstellen Sie die neue Richtlinie als deaktiviert _(aktiviert_ `$false` im **Cmdlet "New-AntiPhishRule").**</span><span class="sxs-lookup"><span data-stu-id="0ff26-293">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="0ff26-294">Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ ) für das _\<Number\>_ **Cmdlet New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="0ff26-294">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="0ff26-295">Eine neue Anti-Phishing-Richtlinie, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Anti-Phishing-Regel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0ff26-295">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="0ff26-296">Schritt 1: Erstellen einer Anti-Phish-Richtlinie mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ff26-296">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="0ff26-297">Verwenden Sie die folgende Syntax, um eine #A0 zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="0ff26-297">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="0ff26-298">In diesem Beispiel wird eine Anti-Phishing-Richtlinie mit dem Namen "Research Quarantine" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="0ff26-298">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="0ff26-299">Die Beschreibung ist: Richtlinie der Forschungsabteilung.</span><span class="sxs-lookup"><span data-stu-id="0ff26-299">The description is: Research department policy.</span></span>
- <span data-ttu-id="0ff26-300">Ändert die Standardaktion für Spoofing in "Quarantäne".</span><span class="sxs-lookup"><span data-stu-id="0ff26-300">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="0ff26-301">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0ff26-301">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="0ff26-302">Schritt 2: Verwenden von PowerShell zum Erstellen einer Antiphishregel</span><span class="sxs-lookup"><span data-stu-id="0ff26-302">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="0ff26-303">Verwenden Sie die folgende Syntax, um eine Anti phish-Regel zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="0ff26-303">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="0ff26-304">In diesem Beispiel wird eine Antiphishregel namens "Research Department" mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="0ff26-304">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="0ff26-305">Die Regel ist der Anti-Phishing-Richtlinie "Research Quarantine" zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="0ff26-305">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="0ff26-306">Die Regel gilt für Mitglieder der Gruppe „Research Department“.</span><span class="sxs-lookup"><span data-stu-id="0ff26-306">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="0ff26-307">Da der Parameter _"Priority"_ nicht verwendet wird, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ff26-307">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="0ff26-308">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="0ff26-308">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="0ff26-309">Verwenden von PowerShell zum Anzeigen von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="0ff26-309">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="0ff26-310">Verwenden Sie die folgende Syntax, um vorhandene Anti-Phishing-Richtlinien anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="0ff26-310">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0ff26-311">In diesem Beispiel wird eine Übersichtsliste aller Anti-Phishing-Richtlinien zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0ff26-311">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="0ff26-312">In diesem Beispiel werden alle Eigenschaftswerte für die Phishingrichtlinie "Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0ff26-312">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="0ff26-313">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0ff26-313">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="0ff26-314">Verwenden von PowerShell zum Anzeigen von Anti-Phish-Regeln</span><span class="sxs-lookup"><span data-stu-id="0ff26-314">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="0ff26-315">Verwenden Sie die folgende Syntax, um vorhandene Antiphishregeln anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="0ff26-315">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0ff26-316">In diesem Beispiel wird eine Übersichtsliste aller Antiphishregeln zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0ff26-316">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="0ff26-317">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="0ff26-317">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="0ff26-318">In diesem Beispiel werden alle Eigenschaftswerte für die Phishingregel "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0ff26-318">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="0ff26-319">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="0ff26-319">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="0ff26-320">Verwenden von PowerShell zum Ändern von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="0ff26-320">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="0ff26-321">Neben den folgenden Elementen stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Anti-Phish-Richtlinie in PowerShell ändern, wie beim Erstellen einer Richtlinie, wie in Schritt 1 beschrieben: Verwenden von PowerShell zum Erstellen einer [Anti-Phishing-Richtlinie](#step-1-use-powershell-to-create-an-anti-phish-policy) weiter oben in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="0ff26-321">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="0ff26-322">Die _Option MakeDefault,_ die die angegebene Richtlinie in die  Standardrichtlinie umstellt (auf alle Benutzer angewendet, immer niedrigste Priorität, und Sie können sie nicht löschen), ist nur verfügbar, wenn Sie eine Antiphishrichtlinie in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="0ff26-322">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="0ff26-323">Sie können eine Antiphiishrichtlinie nicht umbenennen (das **Cmdlet "Set-AntiPhishPolicy"** hat keinen _Parameter "Name")._</span><span class="sxs-lookup"><span data-stu-id="0ff26-323">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="0ff26-324">Wenn Sie eine Antiphishingrichtlinie im Security & Compliance Center umbenennen, benennen Sie nur die Antiphishingregel _um._</span><span class="sxs-lookup"><span data-stu-id="0ff26-324">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="0ff26-325">Verwenden Sie folgende Syntax, um eine Anti-Phish-Richtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="0ff26-325">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="0ff26-326">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0ff26-326">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="0ff26-327">Verwenden von PowerShell zum Ändern von Anti-Phish-Regeln</span><span class="sxs-lookup"><span data-stu-id="0ff26-327">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="0ff26-328">Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine Anti-Phish-Regel in PowerShell ändern, ist der Parameter _"Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="0ff26-328">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="0ff26-329">Informationen zum Aktivieren oder Deaktivieren vorhandener Antiphishregeln finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="0ff26-329">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="0ff26-330">Andernfalls stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Regel erstellen, wie in Schritt 2 beschrieben: Verwenden von PowerShell zum Erstellen eines Abschnitts mit [Antiphishregel](#step-2-use-powershell-to-create-an-anti-phish-rule) weiter oben in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="0ff26-330">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="0ff26-331">Verwenden Sie die folgende Syntax, um eine Anti-Phish-Regel zu ändern:</span><span class="sxs-lookup"><span data-stu-id="0ff26-331">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="0ff26-332">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="0ff26-332">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="0ff26-333">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Anti-Phish-Regeln</span><span class="sxs-lookup"><span data-stu-id="0ff26-333">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="0ff26-334">Durch Aktivieren oder Deaktivieren einer Antiphishingregel in PowerShell wird die gesamte Antiphishingrichtlinie (die Antiphishingregel und die zugewiesene Antiphishingrichtlinie) aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0ff26-334">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="0ff26-335">Sie können die standardmäßige Antiphishingrichtlinie nicht aktivieren oder deaktivieren (sie wird immer auf alle Empfänger angewendet).</span><span class="sxs-lookup"><span data-stu-id="0ff26-335">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="0ff26-336">Verwenden Sie die folgende Syntax, um eine #A0 in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="0ff26-336">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="0ff26-337">In diesem Beispiel wird die Phishingregel "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0ff26-337">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0ff26-338">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0ff26-338">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0ff26-339">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Enable-AntiPhishRule"](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) und ["Disable-AntiPhishRule".](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="0ff26-339">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="0ff26-340">Verwenden von PowerShell zum Festlegen der Priorität von Anti-Phish-Regeln</span><span class="sxs-lookup"><span data-stu-id="0ff26-340">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="0ff26-341">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="0ff26-341">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="0ff26-342">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="0ff26-342">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="0ff26-343">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ff26-343">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="0ff26-344">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="0ff26-344">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="0ff26-345">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="0ff26-345">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="0ff26-346">Verwenden Sie die folgende Syntax, um die Priorität einer #A0 in PowerShell zu setzen:</span><span class="sxs-lookup"><span data-stu-id="0ff26-346">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="0ff26-p138">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="0ff26-p138">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="0ff26-349">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="0ff26-349">**Notes**:</span></span>

- <span data-ttu-id="0ff26-350">Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den Parameter _"Priority"_ im **Cmdlet "New-AntiPhishRule".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-350">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="0ff26-351">Die Standardmäßige Anti phish-Richtlinie verfügt nicht über eine entsprechende Anti-Phishing-Regel, und sie hat immer den nicht veränderbaren Prioritätswert **Niedrigste**.</span><span class="sxs-lookup"><span data-stu-id="0ff26-351">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="0ff26-352">Verwenden von PowerShell zum Entfernen von Anti-Phishing-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="0ff26-352">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="0ff26-353">Wenn Sie PowerShell verwenden, um eine Anti-Phish-Richtlinie zu entfernen, wird die entsprechende Anti phish-Regel nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="0ff26-353">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="0ff26-354">Verwenden Sie folgende Syntax, um eine #A0 in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="0ff26-354">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="0ff26-355">In diesem Beispiel wird die Phishingrichtlinie "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="0ff26-355">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="0ff26-356">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0ff26-356">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="0ff26-357">Verwenden von PowerShell zum Entfernen von Anti-Phishing-Regeln</span><span class="sxs-lookup"><span data-stu-id="0ff26-357">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="0ff26-358">Wenn Sie PowerShell verwenden, um eine Anti-Phish-Regel zu entfernen, wird die entsprechende Anti-Phishing-Richtlinie nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="0ff26-358">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="0ff26-359">Verwenden Sie die folgende Syntax, um eine Antiphishregel in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="0ff26-359">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="0ff26-360">In diesem Beispiel wird die Phishingregel "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="0ff26-360">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0ff26-361">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="0ff26-361">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0ff26-362">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="0ff26-362">How do you know these procedures worked?</span></span>

<span data-ttu-id="0ff26-363">Gehen Sie wie folgt vor, um die erfolgreiche Konfiguration von Antiphishingrichtlinien in Microsoft Defender für Office 365 zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="0ff26-363">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="0ff26-364">Wechseln Sie im Security & Compliance Center zu **"Bedrohungsverwaltungsrichtlinie** \>  \> **Antiphishing".**</span><span class="sxs-lookup"><span data-stu-id="0ff26-364">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="0ff26-365">Überprüfen Sie die Liste der Richtlinien, **deren Statuswerte** und ihre **Prioritätswerte.**</span><span class="sxs-lookup"><span data-stu-id="0ff26-365">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="0ff26-366">Gehen Sie wie folgt vor, um weitere Details anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="0ff26-366">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="0ff26-367">Wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="0ff26-367">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="0ff26-368">Klicken Sie **auf "Standardrichtlinie",** und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="0ff26-368">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="0ff26-369">Ersetzen Sie in Exchange Online PowerShell den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie \<Name\> die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="0ff26-369">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
