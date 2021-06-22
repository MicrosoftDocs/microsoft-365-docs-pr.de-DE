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
description: Administratoren können erfahren, wie Sie die Antiphishingrichtlinien erstellen, ändern und löschen, die in Exchange Online Protection (EOP)-Organisationen mit oder ohne Exchange Online Postfächern verfügbar sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8633644ab0380cf2adcf30c006a7d6d141a6040a
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054572"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="de92b-103">Konfigurieren von Anti-Phishing-Richtlinien in EOP</span><span class="sxs-lookup"><span data-stu-id="de92b-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="de92b-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="de92b-104">**Applies to**</span></span>
- [<span data-ttu-id="de92b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="de92b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="de92b-106">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer gibt es eine Standardmäßige Antiphishingrichtlinie, die eine begrenzte Anzahl von Antispoofingfunktionen enthält, die standardmäßig aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="de92b-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="de92b-107">Weitere Informationen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="de92b-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="de92b-108">Administratoren können die standardmäßige Antiphishingrichtlinie anzeigen, bearbeiten und konfigurieren (aber nicht löschen).</span><span class="sxs-lookup"><span data-stu-id="de92b-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="de92b-109">Für eine höhere Granularität können Sie auch benutzerdefinierte Antiphishingrichtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="de92b-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="de92b-110">Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="de92b-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="de92b-111">Organisationen mit Exchange Online Postfächern können Antiphishingrichtlinien im Microsoft 365 Defender Portal oder in Exchange Online PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="de92b-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span> <span data-ttu-id="de92b-112">Eigenständige EOP-Organisationen können nur das Microsoft 365 Defender-Portal verwenden.</span><span class="sxs-lookup"><span data-stu-id="de92b-112">Standalone EOP organizations can only use the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="de92b-113">Informationen zum Erstellen und Ändern der erweiterten Antiphishingrichtlinien, die in Microsoft Defender für Office 365 verfügbar sind, finden Sie unter [Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365.](configure-mdo-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="de92b-113">For information about creating and modifying the more advanced anti-phishing policies that are available in Microsoft Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

<span data-ttu-id="de92b-114">Die grundlegenden Elemente einer Antiphishingrichtlinie sind:</span><span class="sxs-lookup"><span data-stu-id="de92b-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="de92b-115">**Die Antiphishingrichtlinie:** Gibt die zu aktivierenden oder zu deaktivierenden Phishing-Schutzmaßnahmen und die Aktionen zum Anwenden von Optionen an.</span><span class="sxs-lookup"><span data-stu-id="de92b-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="de92b-116">**Die Antiphishingregel:** Gibt die Prioritäts- und Empfängerfilter (für die die Richtlinie gilt) für eine Antiphishingrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="de92b-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="de92b-117">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Antiphishingrichtlinien im Microsoft 365 Defender Portal verwalten:</span><span class="sxs-lookup"><span data-stu-id="de92b-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="de92b-118">Wenn Sie eine Antiphishingrichtlinie erstellen, erstellen Sie tatsächlich eine Antiphishingregel und die zugehörige Antiphishingrichtlinie gleichzeitig mit demselben Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="de92b-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="de92b-119">Wenn Sie eine Antiphishingrichtlinie ändern, ändern Einstellungen im Zusammenhang mit Dem Namen, Priorität, aktiviert oder deaktiviert und Empfängerfilter die Antiphishingregel.</span><span class="sxs-lookup"><span data-stu-id="de92b-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="de92b-120">Alle anderen Einstellungen ändern die zugeordnete Antiphishingrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="de92b-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="de92b-121">Wenn Sie eine Antiphishingrichtlinie entfernen, werden die Antiphishingregel und die zugehörige Antiphishingrichtlinie entfernt.</span><span class="sxs-lookup"><span data-stu-id="de92b-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="de92b-122">In Exchange Online PowerShell verwalten Sie die Richtlinie und die Regel separat.</span><span class="sxs-lookup"><span data-stu-id="de92b-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="de92b-123">Weitere Informationen finden Sie im Abschnitt ["Verwenden von Exchange Online PowerShell zum Konfigurieren von Antiphishingrichtlinien"](#use-exchange-online-powershell-to-configure-anti-phishing-policies) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="de92b-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="de92b-124">Jede Organisation verfügt über eine integrierte Antiphishingrichtlinie namens Office365 AntiPhish Default, die über die folgenden Eigenschaften verfügt:</span><span class="sxs-lookup"><span data-stu-id="de92b-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="de92b-125">Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine Antiphishingregel (Empfängerfilter) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="de92b-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="de92b-126">Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet).</span><span class="sxs-lookup"><span data-stu-id="de92b-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="de92b-127">Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität.</span><span class="sxs-lookup"><span data-stu-id="de92b-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="de92b-128">Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="de92b-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="de92b-129">Um die Effektivität des Antiphishingschutzes zu erhöhen, können Sie benutzerdefinierte Antiphishingrichtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="de92b-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="de92b-130">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="de92b-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="de92b-131">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="de92b-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="de92b-132">Um direkt zur **Antiphishingseite** zu wechseln, verwenden Sie <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="de92b-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="de92b-133">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="de92b-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="de92b-134">Antiphishingrichtlinien können nicht in EOP PowerShell als eigenständige Lösung verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="de92b-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="de92b-135">Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:</span><span class="sxs-lookup"><span data-stu-id="de92b-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="de92b-136">Um Antiphishingrichtlinien hinzuzufügen, zu ändern und zu löschen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.</span><span class="sxs-lookup"><span data-stu-id="de92b-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="de92b-137">Für den schreibgeschützten Zugriff auf Antiphishingrichtlinien müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.</span><span class="sxs-lookup"><span data-stu-id="de92b-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="de92b-138">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="de92b-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="de92b-139">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="de92b-139">**Notes**:</span></span>

  - <span data-ttu-id="de92b-140">Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de92b-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="de92b-141">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="de92b-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="de92b-142">Die Rollengruppe **"Organisationsverwaltung nur anzeigen"** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) bietet auch schreibgeschützten Zugriff auf das <sup>\*</sup> Feature.</span><span class="sxs-lookup"><span data-stu-id="de92b-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>

- <span data-ttu-id="de92b-143">Unsere empfohlenen Einstellungen für Antiphishingrichtlinien finden Sie unter [EOP-Antiphishingrichtlinieneinstellungen.](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="de92b-143">For our recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="de92b-144">Es kann bis zu 30 Minuten dauern, bis die aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="de92b-144">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="de92b-145">Informationen dazu, wo Antiphishingrichtlinien in der Filterpipeline angewendet werden, finden Sie unter [Reihenfolge und Rangfolge des E-Mail-Schutzes.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="de92b-145">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="de92b-146">Verwenden des Microsoft 365 Defender Portals zum Erstellen von Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="de92b-146">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="de92b-147">Beim Erstellen einer benutzerdefinierten Antiphishingrichtlinie im Microsoft 365 Defender Portal werden die Antiphishingregel und die zugeordnete Antiphishingrichtlinie gleichzeitig mit demselben Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="de92b-147">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="de92b-148">Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="de92b-148">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="de92b-149">Klicken Sie auf der **Seite "Antiphishing"** auf ![ das Symbol ](../../media/m365-cc-sc-create-icon.png) **"Erstellen".**</span><span class="sxs-lookup"><span data-stu-id="de92b-149">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="de92b-150">Der Richtlinienassistent wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="de92b-150">The policy wizard opens.</span></span> <span data-ttu-id="de92b-151">Konfigurieren Sie auf der Seite **"Richtlinienname"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="de92b-151">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="de92b-152">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="de92b-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="de92b-153">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="de92b-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="de92b-154">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="de92b-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="de92b-155">Auf der dann angezeigten Seite **Benutzer, Gruppen und Domänen** identifizieren Sie die internen Empfänger, für welche die Richtlinie gilt (Empfängerbedingungen):</span><span class="sxs-lookup"><span data-stu-id="de92b-155">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="de92b-156">**Benutzer**: Die angegebenen Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="de92b-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="de92b-157">**Gruppen**: Die angegebenen Verteilergruppen, E-Mail-aktivierten Sicherheitsgruppen oder Microsoft 365-Gruppen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="de92b-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="de92b-158">**Domänen**: Alle Empfänger in der angegebenen [akzeptierten Domäne](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="de92b-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="de92b-159">Klicken Sie auf das entsprechende Feld, beginnen Sie mit der Eingabe eines Wertes, und wählen Sie den gewünschten Wert aus den Ergebnissen aus.</span><span class="sxs-lookup"><span data-stu-id="de92b-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="de92b-160">Wiederholen Sie diesen Vorgang so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="de92b-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="de92b-161">Um einen vorhandenen Wert zu entfernen, klicken Sie auf das</span><span class="sxs-lookup"><span data-stu-id="de92b-161">To remove an existing value, click remove</span></span> ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="de92b-163">neben dem Wert.</span><span class="sxs-lookup"><span data-stu-id="de92b-163">next to the value.</span></span>

   <span data-ttu-id="de92b-164">Für Benutzer oder Gruppen können Sie die meisten Bezeichner verwenden (Name, Anzeigename, Alias, E-Mail-Adresse, Kontoname usw.), aber in den Ergebnissen wird der entsprechende Anzeigename angezeigt.</span><span class="sxs-lookup"><span data-stu-id="de92b-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="de92b-165">Geben Sie für Benutzer einen einzelnen Stern (\*) ein, um alle verfügbaren Werte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="de92b-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="de92b-166">Mehreren Werten in der gleichen Bedingung verwenden die „ODER“-Logik (z. B. _\<recipient1\>_ ODER _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="de92b-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="de92b-167">Unterschiedlichen Bedingungen verwenden die „UND“-Logik (z. B. _\<recipient1\>_ UND _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="de92b-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="de92b-168">**Ausschließen dieser Benutzer, Gruppen und Domänen**: Um Ausnahmen für die internen Empfänger hinzuzufügen, für welche die Richtlinie gilt (Empfängerausnahmen), wählen Sie diese Option und konfigurieren Sie die Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="de92b-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="de92b-169">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="de92b-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="de92b-170">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="de92b-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="de92b-171">Verwenden Sie auf dem angezeigten **Phishingschwellenwert & angezeigten Schutzseite** das Kontrollkästchen **Spoofintelligenz aktivieren,** um spoofintelligenz zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="de92b-171">On the **Phishing threshold & protection** page that appears, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="de92b-172">Der Standardwert ist aktiviert (ausgewählt), und es wird empfohlen, ihn einzugeben.</span><span class="sxs-lookup"><span data-stu-id="de92b-172">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="de92b-173">Sie konfigurieren die Aktion für blockierte gefälschte Nachrichten auf der nächsten Seite.</span><span class="sxs-lookup"><span data-stu-id="de92b-173">You configure the action to take on blocked spoofed messages on the next page.</span></span>

   <span data-ttu-id="de92b-174">Deaktivieren Sie das Kontrollkästchen, um die Spoofintelligenz zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="de92b-174">To turn off spoof intelligence, clear the check box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="de92b-175">Sie müssen den Antispoofingschutz nicht deaktivieren, wenn Ihr MX-Eintrag nicht auf Microsoft 365 verweist. Aktivieren Sie stattdessen die erweiterte Filterung für Connectors.</span><span class="sxs-lookup"><span data-stu-id="de92b-175">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="de92b-176">Anweisungen finden Sie unter ["Erweiterte Filterung für Connectors" in Exchange Online.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="de92b-176">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="de92b-177">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="de92b-177">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="de92b-178">Konfigurieren Sie auf der angezeigten Seite **Aktionen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="de92b-178">On the **Actions** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="de92b-179">**Wenn die Nachricht als Spoofing erkannt wird:** Diese Einstellung ist nur verfügbar, wenn Sie **spoofintelligenz** auf der vorherigen Seite aktivieren ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="de92b-179">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="de92b-180">Wählen Sie eine der folgenden Aktionen in der Dropdownliste für Nachrichten von blockierten gefälschten Absendern aus:</span><span class="sxs-lookup"><span data-stu-id="de92b-180">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
     - <span data-ttu-id="de92b-181">**Verschieben der Nachricht in die Junk-E-Mail-Ordner des Empfängers**</span><span class="sxs-lookup"><span data-stu-id="de92b-181">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="de92b-182">**Quarantäne der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="de92b-182">**Quarantine the message**</span></span>

   - <span data-ttu-id="de92b-183">**Sicherheitstipps & Indikatoren:** Diese Einstellung ist nur verfügbar, wenn Sie **spoofintelligenz** auf der vorherigen Seite aktivieren ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="de92b-183">**Safety tips & indicators**: This setting is available only if you selected **Enable spoof intelligence** on the previous page:</span></span>
     - <span data-ttu-id="de92b-184">**Show (?) for unauthenticated senders for spoof:** Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span><span class="sxs-lookup"><span data-stu-id="de92b-184">**Show (?) for unauthenticated senders for spoof**: Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="de92b-185">**Show "via" tag:** Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span><span class="sxs-lookup"><span data-stu-id="de92b-185">**Show "via" tag**: Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span>

     <span data-ttu-id="de92b-186">Aktivieren Sie das Kontrollkästchen, um eine Einstellung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="de92b-186">To turn on a setting, select the check box.</span></span> <span data-ttu-id="de92b-187">Deaktivieren Sie das Kontrollkästchen, um es zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="de92b-187">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="de92b-188">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="de92b-188">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="de92b-189">Überprüfen Sie auf der angezeigten Seite **Überprüfung** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="de92b-189">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="de92b-190">Sie können in jedem Abschnitt **Bearbeiten** auswählen, um die Einstellungen in diesem Abschnitt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="de92b-190">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="de92b-191">Alternativ können Sie auf **Zurück** klicken oder die entsprechende Seite im Assistenten auswählen.</span><span class="sxs-lookup"><span data-stu-id="de92b-191">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="de92b-192">Wenn Sie fertig sind, klicken Sie auf **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="de92b-192">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="de92b-193">Klicken Sie in der angezeigten Bestätigungsseite auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="de92b-193">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="de92b-194">Verwenden des Microsoft 365 Defender Portals zum Anzeigen von Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="de92b-194">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="de92b-195">Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="de92b-195">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="de92b-196">Auf der **Seite "Antiphishing"** werden die folgenden Eigenschaften in der Liste der Richtlinien angezeigt:</span><span class="sxs-lookup"><span data-stu-id="de92b-196">On the **Anti-phishing** page, the following properties are displayed in the list of policies:</span></span>

   - <span data-ttu-id="de92b-197">**Name**</span><span class="sxs-lookup"><span data-stu-id="de92b-197">**Name**</span></span>
   - <span data-ttu-id="de92b-198">**Status**</span><span class="sxs-lookup"><span data-stu-id="de92b-198">**Status**</span></span>
   - <span data-ttu-id="de92b-199">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="de92b-199">**Priority**</span></span>
   - <span data-ttu-id="de92b-200">**Zuletzt geändert**</span><span class="sxs-lookup"><span data-stu-id="de92b-200">**Last modified**</span></span>

3. <span data-ttu-id="de92b-201">Wenn Sie eine Richtlinie auswählen, indem Sie auf den Namen klicken, werden die Richtlinieneinstellungen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="de92b-201">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="de92b-202">Verwenden des Microsoft 365 Defender Portals zum Ändern von Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="de92b-202">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="de92b-203">Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="de92b-203">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="de92b-204">Wählen Sie auf der **Seite "Antiphishing"** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="de92b-204">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="de92b-205">Wählen Sie im angezeigten Flyout für die Richtliniendetails in jedem Abschnitt die Option **Bearbeiten** aus, um die Einstellungen innerhalb des Abschnitts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="de92b-205">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="de92b-206">Weitere Informationen zu den Einstellungen finden Sie im Abschnitt ["Verwenden des Microsoft 365 Defender Portals zum Erstellen von Antiphishingrichtlinien"](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) weiter oben in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="de92b-206">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="de92b-207">Für die standardmäßige Antiphishingrichtlinie ist der Abschnitt **"Benutzer", "Gruppen" und "Domänen"** nicht verfügbar (die Richtlinie gilt für alle), und Sie können die Richtlinie nicht umbenennen.</span><span class="sxs-lookup"><span data-stu-id="de92b-207">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="de92b-208">Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Reihenfolge der Richtlinienpriorität finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="de92b-208">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="de92b-209">Aktivieren oder Deaktivieren von benutzerdefinierten Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="de92b-209">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="de92b-210">Sie können die standardmäßige Antiphishingrichtlinie nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="de92b-210">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="de92b-211">Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="de92b-211">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="de92b-212">Wählen Sie auf der **Seite "Antiphishing"** eine benutzerdefinierte Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="de92b-212">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="de92b-213">Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie einen der folgenden Werte sehen:</span><span class="sxs-lookup"><span data-stu-id="de92b-213">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="de92b-214">**Richtlinie deaktiviert**: Um die Richtlinie zu aktivieren, klicken Sie auf ![Symbol „Aktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="de92b-214">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="de92b-215">**Richtlinie aktiviert**: Um die Richtlinie zu deaktivieren, klicken Sie auf ![Symbol „Deaktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="de92b-215">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="de92b-216">Klicken Sie im angezeigten Bestätigungsdialog auf **Aktivieren** oder **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="de92b-216">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="de92b-217">Klicken Sie im Flyout der Richtliniendetails auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="de92b-217">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="de92b-218">Zurück auf der Richtlinien-Hauptseite wird der Wert **Status** der Richtlinie **Aktiviert** oder **Deaktiviert** sein.</span><span class="sxs-lookup"><span data-stu-id="de92b-218">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="de92b-219">Festlegen der Priorität von benutzerdefinierten Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="de92b-219">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="de92b-220">Standardmäßig erhalten Antiphishingrichtlinien eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="de92b-220">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="de92b-221">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="de92b-221">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="de92b-222">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="de92b-222">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="de92b-223">Um die Priorität einer Richtlinie zu ändern, klicken Sie in den Eigenschaften einer Richtlinie auf **Priorität erhöhen** oder **Priorität verringern** (Sie können den Zahlenwert der **Priorität** im Microsoft 365 Defender-Portal nicht direkt modifizieren).</span><span class="sxs-lookup"><span data-stu-id="de92b-223">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="de92b-224">Die Priorität einer Richtlinie zu verändern macht nur Sinn, wenn Sie mehrere Richtlinien haben.</span><span class="sxs-lookup"><span data-stu-id="de92b-224">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="de92b-225">**Anmerkungen**:</span><span class="sxs-lookup"><span data-stu-id="de92b-225">**Notes**:</span></span>

- <span data-ttu-id="de92b-226">Im Microsoft 365 Defender Portal können Sie die Priorität der Antiphishingrichtlinie erst ändern, nachdem Sie sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="de92b-226">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="de92b-227">In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Antiphishingregel erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="de92b-227">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="de92b-228">Antiphishingrichtlinien werden in der Reihenfolge verarbeitet, in der sie angezeigt werden (die erste Richtlinie hat den **Prioritätswert** 0).</span><span class="sxs-lookup"><span data-stu-id="de92b-228">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="de92b-229">Die Standardmäßige Antiphishingrichtlinie hat den Prioritätswert **Niedrigste**, und Sie können sie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="de92b-229">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="de92b-230">Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="de92b-230">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="de92b-231">Wählen Sie auf der **Seite "Antiphishing"** eine benutzerdefinierte Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="de92b-231">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="de92b-232">Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie **Priorität erhöhen** oder **Priorität verringern** sehen, abhängig vom aktuellen Prioritätswert und der Anzahl der benutzerdefinierten Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="de92b-232">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="de92b-233">Für die Richtlinie mit dem **Prioritätswert** **0** ist nur die Option **"Priorität verringern"** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="de92b-233">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="de92b-234">Für die Richtlinie mit dem niedrigsten **Prioritätswert** (z. B. **3)** ist nur die Option **"Priorität erhöhen"** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="de92b-234">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="de92b-235">Wenn Sie über drei oder mehr Richtlinien verfügen, stehen für die Richtlinien zwischen den Werten mit der höchsten und der niedrigsten Priorität die Optionen **"Priorität erhöhen"** und **"Verringern"** zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="de92b-235">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="de92b-236">Klicken Sie auf ![Symbol „Priorität erhöhen“](../../media/m365-cc-sc-increase-icon.png) **Priorität erhöhen** oder ![Symbol „Priorität verringern“](../../media/m365-cc-sc-decrease-icon.png) **Priorität verringern**, um den **Prioritätswert** zu ändern.</span><span class="sxs-lookup"><span data-stu-id="de92b-236">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="de92b-237">Wenn Sie den Vorgang abgeschlossen haben, klicken Sie im Flyout der Richtliniendetails auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="de92b-237">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="de92b-238">Verwenden des Microsoft 365 Defender Portals zum Entfernen von benutzerdefinierten Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="de92b-238">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="de92b-239">Wenn Sie das Microsoft 365 Defender Portal verwenden, um eine benutzerdefinierte Antiphishingrichtlinie zu entfernen, werden die Antiphishingregel und die entsprechende Antiphishingrichtlinie gelöscht.</span><span class="sxs-lookup"><span data-stu-id="de92b-239">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="de92b-240">Sie können die standardmäßige Antiphishingrichtlinie nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="de92b-240">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="de92b-241">Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="de92b-241">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="de92b-242">Wählen Sie auf der **Seite "Antiphishing"** eine benutzerdefinierte Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="de92b-242">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="de92b-243">Ganz oben auf dem angezeigten Flyout der Richtliniendetails klicken Sie auf ![Symbol „Weiter Aktionen“](../../media/m365-cc-sc-more-actions-icon.png) **Weitere Aktionen** \> ![Symbol „Richtlinie löschen“](../../media/m365-cc-sc-delete-icon.png) **Richtlinie löschen**.</span><span class="sxs-lookup"><span data-stu-id="de92b-243">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="de92b-244&quot;>Klicken Sie im angezeigten Bestätigungsdialog auf **Ja**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-244&quot;>In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name=&quot;use-exchange-online-powershell-to-configure-anti-phishing-policies&quot;></a><span data-ttu-id=&quot;de92b-245&quot;>Verwenden von Exchange Online PowerShell zum Konfigurieren von Antiphishingrichtlinien</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-245&quot;>Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id=&quot;de92b-246&quot;>Wie zuvor beschrieben besteht eine Antiphishingrichtlinie aus einer Antiphishingrichtlinie und einer Antiphishingregel.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-246&quot;>As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id=&quot;de92b-247&quot;>In Exchange Online PowerShell ist der Unterschied zwischen Antiphishingrichtlinien und Antiphishingregeln offensichtlich.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-247&quot;>In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id=&quot;de92b-248&quot;>Sie verwalten Antiphishingrichtlinien mithilfe der **\* -AntiPhishPolicy-Cmdlets,** und Sie verwalten Antiphishingregeln mithilfe der **\* -AntiPhishRule-Cmdlets.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-248&quot;>You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id=&quot;de92b-249&quot;>In PowerShell erstellen Sie zuerst die Antiphishingrichtlinie und dann die Antiphishingregel, die die Richtlinie identifiziert, für die die Regel gilt.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-249&quot;>In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id=&quot;de92b-250&quot;>In PowerShell ändern Sie die Einstellungen in der Antiphishingrichtlinie und der Antiphishingregel separat.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-250&quot;>In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id=&quot;de92b-251&quot;>Wenn Sie eine Antiphishingrichtlinie aus PowerShell entfernen, wird die entsprechende Antiphishingregel nicht automatisch entfernt und umgekehrt.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-251&quot;>When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id=&quot;de92b-252&quot;>Die folgenden PowerShell-Verfahren sind in eigenständigen EOP-Organisationen, die Exchange Online Protection PowerShell verwenden, nicht verfügbar.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-252&quot;>The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name=&quot;use-powershell-to-create-anti-phishing-policies&quot;></a><span data-ttu-id=&quot;de92b-253&quot;>Verwenden von PowerShell zum Erstellen von Antiphishingrichtlinien</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-253&quot;>Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id=&quot;de92b-254&quot;>Das Erstellen einer Antiphishingrichtlinie in PowerShell besteht aus zwei Schritten:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-254&quot;>Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id=&quot;de92b-255&quot;>Erstellen Sie die Antiphishingrichtlinie.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-255&quot;>Create the anti-phish policy.</span></span>
2. <span data-ttu-id=&quot;de92b-256&quot;>Erstellen Sie die Antiphishingregel, die die Antiphishingrichtlinie angibt, auf die die Regel angewendet wird.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-256&quot;>Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id=&quot;de92b-257&quot;>**Hinweise**:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-257&quot;>**Notes**:</span></span>

- <span data-ttu-id=&quot;de92b-258&quot;>Sie können eine neue Antiphishingregel erstellen und ihr eine vorhandene, nicht zugeordnete Antiphishingrichtlinie zuweisen.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-258&quot;>You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id=&quot;de92b-259&quot;>Eine Antiphishingregel kann nicht mehr als einer Antiphishingrichtlinie zugeordnet werden.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-259&quot;>An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id=&quot;de92b-260&quot;>Sie können die folgenden Einstellungen für neue Antiphishingrichtlinien in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Microsoft 365 Defender-Portal verfügbar sind:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;de92b-260&quot;>You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>

  - <span data-ttu-id=&quot;de92b-261&quot;>Erstellen Sie die neue Richtlinie als deaktiviert _(aktiviert_ `$false` im Cmdlet **&quot;New-AntiPhishRule").**</span><span class="sxs-lookup"><span data-stu-id="de92b-261">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="de92b-262">Legen Sie die Priorität der Richtlinie während der Erstellung _(Priorität)_ _\<Number\>_ im Cmdlet **"New-AntiPhishRule"** fest.</span><span class="sxs-lookup"><span data-stu-id="de92b-262">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="de92b-263">Eine neue Antiphishingrichtlinie, die Sie in PowerShell erstellen, ist erst im Microsoft 365 Defender Portal sichtbar, wenn Sie die Richtlinie einer Antiphishingregel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="de92b-263">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="de92b-264">Schritt 1: Verwenden von PowerShell zum Erstellen einer Antiphishingrichtlinie</span><span class="sxs-lookup"><span data-stu-id="de92b-264">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="de92b-265">Verwenden Sie die folgende Syntax, um eine Antiphishingrichtlinie zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="de92b-265">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="de92b-266">In diesem Beispiel wird eine Antiphishingrichtlinie namens Research Quarantine mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="de92b-266">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="de92b-267">Die Beschreibung lautet: Abteilungsrichtlinie für Die Forschung.</span><span class="sxs-lookup"><span data-stu-id="de92b-267">The description is: Research department policy.</span></span>
- <span data-ttu-id="de92b-268">Ändert die Standardaktion für Spoofing in Quarantäne.</span><span class="sxs-lookup"><span data-stu-id="de92b-268">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="de92b-269">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="de92b-269">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="de92b-270">Schritt 2: Verwenden von PowerShell zum Erstellen einer Antiphishingregel</span><span class="sxs-lookup"><span data-stu-id="de92b-270">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="de92b-271">Verwenden Sie diese Syntax, um eine Antiphishingregel zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="de92b-271">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="de92b-272">In diesem Beispiel wird eine Antiphishingregel namens Research Department mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="de92b-272">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="de92b-273">Die Regel ist der Antiphishingrichtlinie namens Research Quarantine zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="de92b-273">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="de92b-274">Die Regel gilt für Mitglieder der Gruppe „Research Department“.</span><span class="sxs-lookup"><span data-stu-id="de92b-274">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="de92b-275">Da der Parameter _"Priority"_ nicht verwendet wird, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="de92b-275">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="de92b-276">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="de92b-276">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="de92b-277">Verwenden von PowerShell zum Anzeigen von Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="de92b-277">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="de92b-278">Verwenden Sie die folgende Syntax, um vorhandene Antiphishingrichtlinien anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="de92b-278">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="de92b-279">In diesem Beispiel wird eine Zusammenfassungsliste aller Antiphishingrichtlinien zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="de92b-279">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="de92b-280">In diesem Beispiel werden alle Eigenschaftswerte für die Antiphishingrichtlinie Executives zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="de92b-280">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="de92b-281">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-AntiPhishPolicy".](/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="de92b-281">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="de92b-282">Verwenden von PowerShell zum Anzeigen von Antiphishingregeln</span><span class="sxs-lookup"><span data-stu-id="de92b-282">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="de92b-283">Verwenden Sie die folgende Syntax, um vorhandene Antiphishingregeln anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="de92b-283">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="de92b-284">In diesem Beispiel wird eine Zusammenfassungsliste aller Antiphishingregeln zusammen mit den angegebenen Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="de92b-284">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="de92b-285">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="de92b-285">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="de92b-286">In diesem Beispiel werden alle Eigenschaftswerte für die Antiphishingregel namens Contoso Executives zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="de92b-286">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="de92b-287">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="de92b-287">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="de92b-288">Verwenden von PowerShell zum Ändern von Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="de92b-288">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="de92b-289">Abgesehen von den folgenden Elementen sind die gleichen Einstellungen verfügbar, wenn Sie eine Antiphishingrichtlinie in PowerShell ändern, wie beim Erstellen einer Richtlinie, wie in [Schritt 1 beschrieben: Verwenden von PowerShell zum Erstellen einer Antiphishingrichtlinie](#step-1-use-powershell-to-create-an-anti-phish-policy) weiter oben in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="de92b-289">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="de92b-290">Der _MakeDefault-Switch,_ der die angegebene Richtlinie in die Standardrichtlinie umschaltet (angewendet auf alle, immer **niedrigste** Priorität, und Sie können sie nicht löschen), ist nur verfügbar, wenn Sie eine Antiphishingrichtlinie in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="de92b-290">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>
- <span data-ttu-id="de92b-291">Sie können eine Antiphishingrichtlinie nicht umbenennen (das Cmdlet **"Set-AntiPhishPolicy"** hat keinen _Name-Parameter)._</span><span class="sxs-lookup"><span data-stu-id="de92b-291">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="de92b-292">Wenn Sie eine Antiphishingrichtlinie im Microsoft 365 Defender-Portal umbenennen, benennen Sie nur die Antiphishingregel um.</span><span class="sxs-lookup"><span data-stu-id="de92b-292">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="de92b-293">Verwenden Sie die folgende Syntax, um eine Antiphishingrichtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="de92b-293">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="de92b-294">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-AntiPhishPolicy".](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="de92b-294">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="de92b-295">Verwenden von PowerShell zum Ändern von Antiphishingregeln</span><span class="sxs-lookup"><span data-stu-id="de92b-295">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="de92b-296">Die einzige Einstellung, die beim Ändern einer Antiphishingregel in PowerShell nicht verfügbar ist, ist der _Parameter "Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="de92b-296">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="de92b-297">Informationen zum Aktivieren oder Deaktivieren vorhandener Antiphishingregeln finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="de92b-297">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="de92b-298">Andernfalls sind die gleichen Einstellungen verfügbar, wenn Sie eine Regel erstellen, wie im [Abschnitt "Schritt 2: Verwenden von PowerShell zum Erstellen einer Antiphishingregel"](#step-2-use-powershell-to-create-an-anti-phish-rule) weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="de92b-298">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="de92b-299">Verwenden Sie die folgende Syntax, um eine Antiphishingregel zu ändern:</span><span class="sxs-lookup"><span data-stu-id="de92b-299">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="de92b-300">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-AntiPhishRule".](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="de92b-300">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="de92b-301">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Antiphishingregeln</span><span class="sxs-lookup"><span data-stu-id="de92b-301">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="de92b-302">Das Aktivieren oder Deaktivieren einer Antiphishingregel in PowerShell aktiviert oder deaktiviert die gesamte Antiphishingrichtlinie (die Antiphishingregel und die zugewiesene Antiphishingrichtlinie).</span><span class="sxs-lookup"><span data-stu-id="de92b-302">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="de92b-303">Sie können die standardmäßige Antiphishingrichtlinie nicht aktivieren oder deaktivieren (sie wird immer auf alle Empfänger angewendet).</span><span class="sxs-lookup"><span data-stu-id="de92b-303">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="de92b-304">Verwenden Sie die folgende Syntax, um eine Antiphishingregel in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="de92b-304">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="de92b-305">In diesem Beispiel wird die Antiphishingregel Marketing Department deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="de92b-305">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="de92b-306">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="de92b-306">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="de92b-307">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) und [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="de92b-307">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="de92b-308">Verwenden von PowerShell zum Festlegen der Priorität von Antiphishingregeln</span><span class="sxs-lookup"><span data-stu-id="de92b-308">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="de92b-p130">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="de92b-p130">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="de92b-314">Verwenden Sie die folgende Syntax, um die Priorität einer Antiphishingregel in PowerShell festzulegen:</span><span class="sxs-lookup"><span data-stu-id="de92b-314">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="de92b-p131">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="de92b-p131">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="de92b-317">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="de92b-317">**Notes**:</span></span>

- <span data-ttu-id="de92b-318">Um die Priorität einer neuen Regel beim Erstellen festzulegen, verwenden Sie stattdessen den Parameter _"Priority"_ im Cmdlet **"New-AntiPhishRule".**</span><span class="sxs-lookup"><span data-stu-id="de92b-318">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>
- <span data-ttu-id="de92b-319">Die Standardmäßige Antiphishingrichtlinie verfügt nicht über eine entsprechende Antiphishingregel und hat immer den unveränderlichen Prioritätswert **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="de92b-319">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="de92b-320">Verwenden von PowerShell zum Entfernen von Antiphishingrichtlinien</span><span class="sxs-lookup"><span data-stu-id="de92b-320">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="de92b-321">Wenn Sie PowerShell zum Entfernen einer Antiphishingrichtlinie verwenden, wird die entsprechende Antiphishingregel nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="de92b-321">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="de92b-322">Verwenden Sie die folgende Syntax, um eine Antiphishingrichtlinie in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="de92b-322">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="de92b-323">In diesem Beispiel wird die Antiphishingrichtlinie Marketing Department entfernt.</span><span class="sxs-lookup"><span data-stu-id="de92b-323">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="de92b-324">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="de92b-324">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="de92b-325">Verwenden von PowerShell zum Entfernen von Antiphishingregeln</span><span class="sxs-lookup"><span data-stu-id="de92b-325">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="de92b-326">Wenn Sie PowerShell zum Entfernen einer Antiphishingregel verwenden, wird die entsprechende Antiphishingrichtlinie nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="de92b-326">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="de92b-327">Verwenden Sie die folgende Syntax, um eine Antiphishingregel in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="de92b-327">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="de92b-328">In diesem Beispiel wird die Antiphishingregel Marketing Department entfernt.</span><span class="sxs-lookup"><span data-stu-id="de92b-328">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="de92b-329">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="de92b-329">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="de92b-330">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="de92b-330">How do you know these procedures worked?</span></span>

<span data-ttu-id="de92b-331">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Antiphishingrichtlinien in EOP erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="de92b-331">To verify that you've successfully configured anti-phishing policies in EOP, do any of the following steps:</span></span>

- <span data-ttu-id="de92b-332">Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Antiphishing.**</span><span class="sxs-lookup"><span data-stu-id="de92b-332">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="de92b-333">Überprüfen Sie die Liste der Richtlinien, ihre **Statuswerte** und ihre **Prioritätswerte.**</span><span class="sxs-lookup"><span data-stu-id="de92b-333">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="de92b-334">Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, indem Sie auf den Namen klicken und die Details im angezeigten Flyout anzeigen.</span><span class="sxs-lookup"><span data-stu-id="de92b-334">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="de92b-335">Ersetzen Sie in Exchange Online PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="de92b-335">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
