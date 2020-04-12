---
title: Konfigurieren der ausgehenden Spamfilterung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: Die Filterung ausgehender Spamnachrichten ist immer aktiviert, wenn Sie den Dienst für das Senden ausgehender E-Mails verwenden und dadurch Organisationen, die den Dienst nutzen, und ihre jeweiligen Empfänger schützen.
ms.openlocfilehash: 3ac85776db5d990d46b858294acf8ef66c7f26bc
ms.sourcegitcommit: c876d58b34454f211b50ae5d06f193c1a1e5c4ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2020
ms.locfileid: "43231004"
---
# <a name="configure-outbound-spam-filtering-in-office-365"></a><span data-ttu-id="23553-103">Konfigurieren der ausgehenden Spamfilterung in Office 365</span><span class="sxs-lookup"><span data-stu-id="23553-103">Configure outbound spam filtering in Office 365</span></span>

<span data-ttu-id="23553-104">Wenn Sie ein Office 365 Kunde mit Postfächern in Exchange Online oder einem eigenständigen Exchange Online Schutz-Kunden (EoP) ohne Exchange Online Postfächer sind, werden ausgehende e-Mail-Nachrichten, die über EoP gesendet werden, automatisch auf Spam und ungewöhnliche Sendeaktivitäten überprüft.</span><span class="sxs-lookup"><span data-stu-id="23553-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="23553-105">Ausgehende Spamnachrichten von einem Benutzer in Ihrer Organisation weisen in der Regel auf ein kompromittiertes Konto hin.</span><span class="sxs-lookup"><span data-stu-id="23553-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="23553-106">Verdächtige ausgehende Nachrichten werden als Spam gekennzeichnet (unabhängig von der Spam Konfidenz Stufe oder der SCL-Bewertung) und werden über den [risikoreichen Zustellungs Pool](high-risk-delivery-pool-for-outbound-messages.md) weitergeleitet, um die Reputation des Diensts zu schützen (also Office 365 Quell-e-Mail-Server von IP-Sperrlisten fernzuhalten).</span><span class="sxs-lookup"><span data-stu-id="23553-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Office 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="23553-107">Administratoren werden automatisch über verdächtige ausgehende e-Mail-Aktivitäten und blockierte Benutzer über [Warnungsrichtlinien](../../compliance/alert-policies.md)benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="23553-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="23553-108">EoP verwendet ausgehende Spam Richtlinien als Teil der gesamten Abwehr von Spam in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="23553-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="23553-109">Weitere Informationen finden Sie unter [Antispamschutz in Office 365](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="23553-109">For more information, see [Anti-spam protection in Office 365](anti-spam-protection.md).</span></span>

<span data-ttu-id="23553-110">Administratoren können die standardmäßige ausgehende Spam Richtlinie anzeigen, bearbeiten und konfigurieren (jedoch nicht löschen).</span><span class="sxs-lookup"><span data-stu-id="23553-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="23553-111">Um eine höhere Granularität zu erzielen, können Sie auch benutzerdefinierte ausgehende Spam Richtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="23553-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="23553-112">Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="23553-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="23553-113">Sie können ausgehende Spam Richtlinien im Office 365 Security & Compliance Center oder in PowerShell konfigurieren (Exchange Online PowerShell für Office 365 Kunden; Exchange Online Protection PowerShell für eigenständige EoP-Kunden).</span><span class="sxs-lookup"><span data-stu-id="23553-113">You can configure outbound spam policies in the Office 365 Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="outbound-spam-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="23553-114">Ausgehende Spam Richtlinien im Office 365 Security & Compliance Center vs Exchange Online PowerShell oder Exchange Online Protection PowerShell</span><span class="sxs-lookup"><span data-stu-id="23553-114">Outbound spam policies in the Office 365 Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="23553-115">Die grundlegenden Elemente einer ausgehenden Spam Richtlinie in EoP sind:</span><span class="sxs-lookup"><span data-stu-id="23553-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="23553-116">**Die Richtlinie für ausgehende Spamfilter**: gibt die Aktionen für ausgehende Spamfilter Urteile und die Benachrichtigungsoptionen an.</span><span class="sxs-lookup"><span data-stu-id="23553-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="23553-117">**Die ausgehende Spamfilter Regel**: gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) für eine Richtlinie für ausgehende Spamfilter an.</span><span class="sxs-lookup"><span data-stu-id="23553-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="23553-118">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie ausgehende Spam Richtlinien im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="23553-118">The difference between these two elements isn't obvious when you manage outbound spam policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="23553-119">Wenn Sie eine ausgehende Spam Richtlinie im Security & Compliance Center erstellen, erstellen Sie tatsächlich eine ausgehende Spamfilter Regel und die zugehörige Filterrichtlinie für ausgehende Spam gleichzeitig unter Verwendung desselben Namens für beide.</span><span class="sxs-lookup"><span data-stu-id="23553-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="23553-120">Wenn Sie eine ausgehende Spam Richtlinie im Security & Compliance Center ändern, ändern die Einstellungen im Zusammenhang mit dem Namen, der Priorität, den aktivierten oder deaktivierten und den Empfänger filtern die ausgehende Spamfilter Regel.</span><span class="sxs-lookup"><span data-stu-id="23553-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="23553-121">Bei allen anderen Einstellungen wird die zugehörige Filterrichtlinie für ausgehende Spam geändert.</span><span class="sxs-lookup"><span data-stu-id="23553-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="23553-122">Wenn Sie eine ausgehende Spam Richtlinie aus dem Security & Compliance Center entfernen, werden die ausgehende Spamfilter Regel und die zugehörige Filterrichtlinie für ausgehende Spam entfernt.</span><span class="sxs-lookup"><span data-stu-id="23553-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="23553-123">In Exchange Online PowerShell oder eigenständigen Exchange Online Protection-PowerShell wird der Unterschied zwischen ausgehenden Spamfilter Richtlinien und ausgehenden spamfilterregeln deutlich.</span><span class="sxs-lookup"><span data-stu-id="23553-123">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="23553-124">Sie verwalten Richtlinien für ausgehende Spamfilter \*\* \*\*\* mithilfe der Cmdlets-hostedcontentfilterpolicy dient zum, und Sie verwalten Filterregeln für ausgehende Spam mithilfe der \*\* \*Cmdlets-HostedContentFilterRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="23553-124">You manage outbound spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="23553-125">In PowerShell erstellen Sie zuerst die Richtlinie für ausgehende Spamfilter, dann erstellen Sie die ausgehende Spamfilter Regel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="23553-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="23553-126">In PowerShell ändern Sie die Einstellungen in der Richtlinie für ausgehende Spamfilter und der ausgehenden Spamfilter Regel separat.</span><span class="sxs-lookup"><span data-stu-id="23553-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="23553-127">Wenn Sie eine ausgehende Spamfilter Richtlinie aus PowerShell entfernen, wird die entsprechende Filterregel für ausgehende Spam nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="23553-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="23553-128">Standardrichtlinie für ausgehende Spamnachrichten</span><span class="sxs-lookup"><span data-stu-id="23553-128">Default outbound spam policy</span></span>

<span data-ttu-id="23553-129">Jede Organisation verfügt über eine integrierte ausgehende Spam Richtlinie mit dem Namen Default, die die folgenden Eigenschaften aufweist:</span><span class="sxs-lookup"><span data-stu-id="23553-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="23553-130">Die Richtlinie für ausgehende Spamfilter mit dem Namen Default wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine ausgehende Spamfilter Regel (Empfängerfilter) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="23553-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="23553-131">Die Richtlinie namens „Standard“ weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet).</span><span class="sxs-lookup"><span data-stu-id="23553-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="23553-132">Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer Vorrang vor der Richtlinie „Standard“.</span><span class="sxs-lookup"><span data-stu-id="23553-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="23553-133">Die Richtlinie namens „Standard“ ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="23553-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="23553-134">Um die Effektivität der ausgehenden Spamfilterung zu verbessern, können Sie benutzerdefinierte ausgehende Spam Richtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="23553-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="23553-135">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="23553-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="23553-136">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="23553-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="23553-137">Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="23553-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="23553-138">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="23553-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="23553-139">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="23553-139">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="23553-140">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="23553-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="23553-141">Zum Hinzufügen, ändern und Löschen von ausgehenden Spam Richtlinien müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.</span><span class="sxs-lookup"><span data-stu-id="23553-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="23553-142">Für den schreibgeschützten Zugriff auf ausgehende Spam Richtlinien müssen Sie Mitglied der Rollengruppe **Sicherheits Leser** sein.</span><span class="sxs-lookup"><span data-stu-id="23553-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="23553-143">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="23553-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="23553-144">Unsere empfohlenen Einstellungen für ausgehende Spam Richtlinien finden Sie unter [EoP Outbound Spamfilter Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="23553-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="23553-145">Die standardmäßigen [Warnungsrichtlinien](../../compliance/alert-policies.md) mit dem Namen " **e-Mail-Sende Grenzwert**" überschritten, **verdächtige e-Mail-Sende Muster wurden erkannt**und Benutzer, die **von e-Mails eingeschränkt** sind, senden bereits e-Mail-Benachrichtigungen an Mitglieder der Gruppe der **TenantAdmins** (**globale Administratoren**) über ungewöhnliche ausgehende e-Mail-Aktivitäten und blockierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="23553-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="23553-146">Weitere Informationen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="23553-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="23553-147">Es wird empfohlen, diese Warnungsrichtlinien anstelle der Benachrichtigungsoptionen in ausgehenden Spam Richtlinien zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="23553-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="23553-148">Verwenden des Security & Compliance Center zum Erstellen von ausgehenden Spam Richtlinien</span><span class="sxs-lookup"><span data-stu-id="23553-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="23553-149">Durch das Erstellen einer benutzerdefinierten ausgehenden Spam Richtlinie im Security & Compliance Center werden die Spamfilter Regel und die zugehörige Spamfilter Richtlinie gleichzeitig mit dem gleichen Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="23553-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="23553-150">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="23553-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="23553-151">Klicken Sie auf der Seite **Anti-Spam-Einstellungen** auf **ausgehende Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="23553-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="23553-152">Konfigurieren Sie in der geöffneten **ausgehenden Spamfilter Richtlinie** , die geöffnet wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="23553-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="23553-153">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="23553-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="23553-154">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="23553-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="23553-155">Optional Erweitern Sie den Abschnitt **Benachrichtigungen** , um weitere Benutzer zu konfigurieren, die Kopien und Benachrichtigungen von verdächtigen ausgehenden e-Mail-Nachrichten erhalten sollen:</span><span class="sxs-lookup"><span data-stu-id="23553-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="23553-156">**Senden einer Kopie verdächtiger ausgehender e-Mail-Nachrichten an bestimmte Personen**: mit dieser Einstellung werden den Verdächtigen ausgehenden Nachrichten die angegebenen Benutzer als Bcc-Empfänger hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23553-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span> <span data-ttu-id="23553-157">So aktivieren Sie diese Einstellung:</span><span class="sxs-lookup"><span data-stu-id="23553-157">To enable this setting:</span></span>

     <span data-ttu-id="23553-158">a.</span><span class="sxs-lookup"><span data-stu-id="23553-158">a.</span></span> <span data-ttu-id="23553-159">Aktivieren Sie das Kontrollkästchen, um die Einstellung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="23553-159">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="23553-160">b.</span><span class="sxs-lookup"><span data-stu-id="23553-160">b.</span></span> <span data-ttu-id="23553-161">Klicken Sie auf **Personen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="23553-161">Click **Add people**.</span></span> <span data-ttu-id="23553-162">Im Flyout **Empfänger hinzufügen oder entfernen** :</span><span class="sxs-lookup"><span data-stu-id="23553-162">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="23553-163">c.</span><span class="sxs-lookup"><span data-stu-id="23553-163">c.</span></span> <span data-ttu-id="23553-164">Geben Sie die E-Mail-Adresse des Absenders ein.</span><span class="sxs-lookup"><span data-stu-id="23553-164">Enter the sender's email address.</span></span> <span data-ttu-id="23553-165">Sie können mehrere e-Mail-Adressen durch Semikolons getrennt angeben (;) oder ein Empfänger pro Reihe.</span><span class="sxs-lookup"><span data-stu-id="23553-165">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="23553-166">d.</span><span class="sxs-lookup"><span data-stu-id="23553-166">d.</span></span> <span data-ttu-id="23553-167">Click</span><span class="sxs-lookup"><span data-stu-id="23553-167">Click</span></span> ![Hinzufügen (Symbol)](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="23553-169">zum Hinzufügen der Empfänger.</span><span class="sxs-lookup"><span data-stu-id="23553-169">to add the recipients.</span></span>

        <span data-ttu-id="23553-170">Wiederholen Sie diese Schritte so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="23553-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="23553-171">Die Empfänger, die Sie hinzugefügt haben, werden im Flyout im Abschnitt **Empfängerliste** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23553-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="23553-172">Klicken Sie ![auf die Schaltfläche](../../media/scc-remove-icon.png)entfernen, um einen Empfänger zu löschen.</span><span class="sxs-lookup"><span data-stu-id="23553-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="23553-173">e.</span><span class="sxs-lookup"><span data-stu-id="23553-173">e.</span></span> <span data-ttu-id="23553-174">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="23553-174">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="23553-175">Deaktivieren Sie das Kontrollkästchen, um diese Einstellung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="23553-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="23553-176">**Benachrichtigen bestimmter Personen, wenn ein Absender aufgrund des Sendens von ausgehenden Spam blockiert wird**:</span><span class="sxs-lookup"><span data-stu-id="23553-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="23553-177">Die standardmäßige [Warnungs Richtlinie](../../compliance/alert-policies.md) mit dem Namen " **Benutzer vom Senden von e-Mails eingeschränkt** " sendet bereits e-Mail-Benachrichtigungen an Mitglieder der Gruppe **TenantAdmins** (**globale Administratoren**), wenn Benutzer aufgrund der Überschreitung der Grenzwerte im Abschnitt **Empfänger Grenzwerte** blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="23553-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="23553-178">Es wird empfohlen, dass Sie die Warnungs Richtlinie anstelle dieser Einstellung in der ausgehenden Spam Richtlinie verwenden, um Administratoren und andere Benutzer zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="23553-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="23553-179">Anweisungen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="23553-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

     <span data-ttu-id="23553-180">So aktivieren Sie diese Einstellung:</span><span class="sxs-lookup"><span data-stu-id="23553-180">To enable this setting:</span></span>

     <span data-ttu-id="23553-181">a.</span><span class="sxs-lookup"><span data-stu-id="23553-181">a.</span></span> <span data-ttu-id="23553-182">Aktivieren Sie das Kontrollkästchen, um die Einstellung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="23553-182">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="23553-183">b.</span><span class="sxs-lookup"><span data-stu-id="23553-183">b.</span></span> <span data-ttu-id="23553-184">Klicken Sie auf **Personen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="23553-184">Click **Add people**.</span></span> <span data-ttu-id="23553-185">Im Flyout **Empfänger hinzufügen oder entfernen** :</span><span class="sxs-lookup"><span data-stu-id="23553-185">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="23553-186">c.</span><span class="sxs-lookup"><span data-stu-id="23553-186">c.</span></span> <span data-ttu-id="23553-187">Geben Sie die E-Mail-Adresse des Absenders ein.</span><span class="sxs-lookup"><span data-stu-id="23553-187">Enter the sender's email address.</span></span> <span data-ttu-id="23553-188">Sie können mehrere e-Mail-Adressen durch Semikolons getrennt angeben (;) oder ein Empfänger pro Reihe.</span><span class="sxs-lookup"><span data-stu-id="23553-188">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="23553-189">d.</span><span class="sxs-lookup"><span data-stu-id="23553-189">d.</span></span> <span data-ttu-id="23553-190">Click</span><span class="sxs-lookup"><span data-stu-id="23553-190">Click</span></span> ![Hinzufügen (Symbol)](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="23553-192">zum Hinzufügen der Empfänger.</span><span class="sxs-lookup"><span data-stu-id="23553-192">to add the recipients.</span></span>

        <span data-ttu-id="23553-193">Wiederholen Sie diese Schritte so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="23553-193">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="23553-194">Die Empfänger, die Sie hinzugefügt haben, werden im Flyout im Abschnitt **Empfängerliste** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23553-194">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="23553-195">Klicken Sie ![auf die Schaltfläche](../../media/scc-remove-icon.png)entfernen, um einen Empfänger zu löschen.</span><span class="sxs-lookup"><span data-stu-id="23553-195">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="23553-196">e.</span><span class="sxs-lookup"><span data-stu-id="23553-196">e.</span></span> <span data-ttu-id="23553-197">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="23553-197">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="23553-198">Deaktivieren Sie das Kontrollkästchen, um diese Einstellung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="23553-198">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="23553-199">Optional Erweitern Sie den Abschnitt **Empfänger Grenzwerte** , um die Grenzwerte und Aktionen für verdächtige ausgehende e-Mail-Nachrichten zu konfigurieren:]</span><span class="sxs-lookup"><span data-stu-id="23553-199">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages: ]</span></span>
   - <span data-ttu-id="23553-200">**Maximale Anzahl von Empfängern pro Benutzer**</span><span class="sxs-lookup"><span data-stu-id="23553-200">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="23553-201">Ein gültiger Wert ist 0 bis 10000.</span><span class="sxs-lookup"><span data-stu-id="23553-201">A valid value is 0 to 10000.</span></span> <span data-ttu-id="23553-202">Der Standardwert ist 0, was bedeutet, dass die Dienst Standardwerte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="23553-202">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="23553-203">Weitere Informationen finden Sie unter [sending Limits Across Office 365 Options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="23553-203">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="23553-204">**Externer stündlicher Grenzwert**: die maximale Anzahl externer Empfänger pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="23553-204">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="23553-205">**Interner stündlicher Grenzwert**: die maximale Anzahl interner Empfänger pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="23553-205">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="23553-206">**Daily Limit**: die maximale Gesamtzahl der Empfänger pro Tag.</span><span class="sxs-lookup"><span data-stu-id="23553-206">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="23553-207">**Aktion, wenn ein Benutzer die oben genannten Grenzwerte überschreitet**: Konfigurieren Sie die Aktion, die ausgeführt werden soll, wenn eine der **Empfänger Grenzwerte** überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="23553-207">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="23553-208">Für alle Aktionen werden die im Benutzer angegebenen Empfänger **vom Senden von e-Mail-** Warnungsrichtlinien eingeschränkt (und im jetzt redundante **Benachrichtigen bestimmter Personen, wenn ein Absender aufgrund des Sendens von ausgehenden Spam** -Einstellungen in der ausgehenden Spam Richtlinie blockiert wird, e-Mail-Benachrichtigungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="23553-208">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="23553-209">**Beschränken Sie den Benutzer am Senden von e-Mails bis zum folgenden Tag**: Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="23553-209">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="23553-210">E-Mail-Benachrichtigungen werden gesendet, und der Benutzer kann keine weiteren Nachrichten auf der Grundlage der UTC-Zeit bis zum nächsten Tag senden.</span><span class="sxs-lookup"><span data-stu-id="23553-210">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="23553-211">Es gibt keine Möglichkeit für den Administrator, diesen Block außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="23553-211">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="23553-212">Die Aktivitäts Benachrichtigung mit dem Namen " **Benutzer vom Senden von e-Mails eingeschränkt** " benachrichtigt Administratoren (per e-Mail und auf der Seite **Benachrichtigungen anzeigen** ).</span><span class="sxs-lookup"><span data-stu-id="23553-212">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="23553-213">Alle Empfänger, die in der Richtlinie in den Einstellungen " **bestimmte Personen Benachrichtigen, wenn ein Absender aufgrund des Sendens ausgehenden Spam blockiert ist** " angegeben werden, werden ebenfalls benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="23553-213">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="23553-214">Der Benutzer kann bis zum nächsten Tag keine weiteren Nachrichten senden, basierend auf UTC-Zeit.</span><span class="sxs-lookup"><span data-stu-id="23553-214">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="23553-215">Es gibt keine Möglichkeit für den Administrator, diesen Block außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="23553-215">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="23553-216">**Einschränken des Benutzers beim Senden von e-Mails**: e-Mail-Benachrichtigungen werden gesendet, der Benutzer wird dem Portal **[<https://sip.protection.office.com/restrictedusers> restricted users]** im Security & Compliance Center hinzugefügt, und der Benutzer kann keine e-Mails senden, bevor er von einem Administrator aus dem Portal für **eingeschränkte Benutzer** entfernt wird. Nachdem der Benutzer von einem Administrator aus der Liste entfernt wurde, wird der Benutzer für diesen Tag nicht mehr eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="23553-216">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="23553-217">Anweisungen hierzu finden Sie unter [Entfernen eines Benutzers aus dem Portal für eingeschränkte Benutzer nach dem Senden von Spam-e-Mails](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="23553-217">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="23553-218">**Keine Aktion, nur Warnung**: e-Mail-Benachrichtigungen werden gesendet.</span><span class="sxs-lookup"><span data-stu-id="23553-218">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="23553-219">Erforderlich Erweitern Sie den Abschnitt **angewendet für** , um die internen Absender zu identifizieren, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="23553-219">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="23553-220">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="23553-220">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="23553-221">Mehrere Werte der gleichen Bedingung oder Ausnahme Verwendung oder Logik (beispielsweise _ \<sender1\> _ oder _ \<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="23553-221">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="23553-222">Unterschiedliche Bedingungen oder Ausnahmen: Verwendung und Logik (Beispiels _ \<Weise\> sender1_ und _ \<Mitglied von Gruppe\>1_).</span><span class="sxs-lookup"><span data-stu-id="23553-222">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="23553-223">Um alle verfügbaren Bedingungen anzuzeigen, ist es am einfachsten, wenn Sie auf **Bedingung hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="23553-223">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="23553-224">Sie können auf ![Schaltfläche „Entfernen“](../../media/scc-remove-icon.png) klicken, um Bedingungen zu entfernen, die Sie nicht konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="23553-224">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="23553-225">**Die Absenderdomäne lautet**: gibt Absender in einer oder mehreren konfigurierten akzeptierten Domänen in Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="23553-225">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in Office 365.</span></span> <span data-ttu-id="23553-226">Klicken Sie in das Feld **Tag hinzufügen**, um eine Domäne anzuzeigen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="23553-226">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="23553-227">Klicken Sie erneut auf das Feld **Tag hinzufügen**, um weitere Domänen auszuwählen, falls mehrere Domänen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="23553-227">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="23553-228">**Absender lautet**: gibt einen oder mehrere Benutzer in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="23553-228">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="23553-229">Klicken Sie auf **Tag hinzufügen**, und beginnen Sie mit der Eingabe, um die Liste zu filtern.</span><span class="sxs-lookup"><span data-stu-id="23553-229">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="23553-230">Klicken Sie erneut auf das Feld **Tag hinzufügen** , um weitere Absender auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="23553-230">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="23553-231">**Der Absender ist Mitglied von**: gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="23553-231">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="23553-232">Klicken Sie auf **Tag hinzufügen**, und beginnen Sie mit der Eingabe, um die Liste zu filtern.</span><span class="sxs-lookup"><span data-stu-id="23553-232">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="23553-233">Klicken Sie erneut auf das Feld **Tag hinzufügen** , um weitere Absender auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="23553-233">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="23553-234">**Außer wenn**: Klicken Sie zum Angeben von Ausnahmen für die Regel dreimal auf **Bedingung hinzufügen**, um alle verfügbaren Ausnahmen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="23553-234">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="23553-235">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="23553-235">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="23553-236">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="23553-236">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="23553-237">Verwenden des Security & Compliance Center zum Anzeigen von ausgehenden Spam Richtlinien</span><span class="sxs-lookup"><span data-stu-id="23553-237">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="23553-238">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="23553-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="23553-239">Klicken Sie ![auf der Seite **Anti-Spam-Einstellungen** auf](../../media/scc-expand-icon.png) Symbol erweitern, um eine ausgehende Spam Richtlinie zu erweitern:</span><span class="sxs-lookup"><span data-stu-id="23553-239">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="23553-240">Die Standardrichtlinie mit dem Namen " **Outbound Spamfilter Policy**".</span><span class="sxs-lookup"><span data-stu-id="23553-240">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="23553-241">Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei der Wert in der Spalte **Typ** eine **benutzerdefinierte ausgehende Spam Richtlinie**ist.</span><span class="sxs-lookup"><span data-stu-id="23553-241">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="23553-242">Die Richtlinieneinstellungen werden in den erweiterten Richtliniendetails angezeigt, die angezeigt werden, oder Sie können auf **Richtlinie bearbeiten**klicken.</span><span class="sxs-lookup"><span data-stu-id="23553-242">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="23553-243">Verwenden des Security & Compliance Center zum Ändern von Richtlinien für ausgehende Spamnachrichten</span><span class="sxs-lookup"><span data-stu-id="23553-243">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="23553-244">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="23553-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="23553-245">Klicken Sie ![auf der Seite **Anti-Spam-Einstellungen** auf](../../media/scc-expand-icon.png) Symbol erweitern, um eine ausgehende Spam Richtlinie zu erweitern:</span><span class="sxs-lookup"><span data-stu-id="23553-245">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="23553-246">Die Standardrichtlinie mit dem Namen " **Outbound Spamfilter Policy**".</span><span class="sxs-lookup"><span data-stu-id="23553-246">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="23553-247">Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei der Wert in der Spalte **Typ** eine **benutzerdefinierte ausgehende Spam Richtlinie**ist.</span><span class="sxs-lookup"><span data-stu-id="23553-247">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="23553-248">Klicken Sie auf **Richtlinie bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="23553-248">Click **Edit policy**.</span></span>

<span data-ttu-id="23553-249">Bei benutzerdefinierten ausgehenden Spam Richtlinien sind die verfügbaren Einstellungen im Flyout, die angezeigt werden, mit denen im Abschnitt [Verwenden der Sicherheits & Compliance Center zum Erstellen von ausgehenden Spam Richtlinien](#use-the-security--compliance-center-to-create-outbound-spam-policies) beschrieben identisch.</span><span class="sxs-lookup"><span data-stu-id="23553-249">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="23553-250">Für die standardmäßige ausgehende Spam Richtlinie mit dem Namen " **ausgehende Spamfilter Richtlinie**" ist der Abschnitt " **angewendet für** " nicht verfügbar (die Richtlinie gilt für alle), und Sie können die Richtlinie nicht umbenennen.</span><span class="sxs-lookup"><span data-stu-id="23553-250">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="23553-251">Informationen zum Aktivieren oder Deaktivieren einer Richtlinie, zum Festlegen der Prioritätsreihenfolge der Richtlinien oder zum Konfigurieren der Quarantänebenachrichtigungen für Endbenutzer finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="23553-251">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="23553-252">Aktivieren oder Deaktivieren von ausgehenden Spam Richtlinien</span><span class="sxs-lookup"><span data-stu-id="23553-252">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="23553-253">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="23553-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="23553-254">Klicken Sie ![auf der Seite **Anti-Spam-Einstellungen** auf](../../media/scc-expand-icon.png) Symbol erweitern, um eine benutzerdefinierte Richtlinie zu erweitern, die Sie erstellt haben (der Wert in der Spalte **Typ** ist eine **benutzerdefinierte ausgehende Spam Richtlinie**).</span><span class="sxs-lookup"><span data-stu-id="23553-254">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="23553-255">Achten Sie in den angezeigten erweiterten Richtliniendetails auf den Wert in der Spalte **Ein**.</span><span class="sxs-lookup"><span data-stu-id="23553-255">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="23553-256">Schieben Sie die Umschaltfläche nach links, um die Richtlinie zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="23553-256">Move the toggle to the left to disable the policy:</span></span> ![Umschaltfläche aus](../../media/scc-toggle-off.png)

   <span data-ttu-id="23553-258">Schieben Sie die Umschaltfläche nach rechts, um die Richtlinie zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="23553-258">Move the toggle to the right to enable the policy:</span></span> ![Umschaltfläche ein](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="23553-260">Sie können die standardmäßige ausgehende Spam Richtlinie nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="23553-260">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="23553-261">Festlegen der Priorität von benutzerdefinierten ausgehenden Spam Richtlinien</span><span class="sxs-lookup"><span data-stu-id="23553-261">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="23553-262">Standardmäßig erhalten ausgehende Spam Richtlinien eine Priorität, die auf der Reihenfolge basiert, in der Sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="23553-262">By default, outbound spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="23553-263">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="23553-263">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="23553-264">Zwei Richtlinien können nicht dieselbe Priorität haben.</span><span class="sxs-lookup"><span data-stu-id="23553-264">No two policies can have the same priority.</span></span>

<span data-ttu-id="23553-265">Benutzerdefinierte ausgehende Spam Richtlinien werden in der Reihenfolge angezeigt, in der Sie verarbeitet werden (die erste Richtlinie hat den **Prioritäts** Wert 0).</span><span class="sxs-lookup"><span data-stu-id="23553-265">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="23553-266">Bei der standardmäßigen ausgehenden Spam Richtlinie mit dem Namen " **ausgehende Spamfilter Richtlinie** " ist der Prioritätswert **niedrig**und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="23553-266">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="23553-267">Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).</span><span class="sxs-lookup"><span data-stu-id="23553-267">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="23553-268">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="23553-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="23553-269">Suchen Sie auf der Seite **Antispameinstellungen** nach den Richtlinien, bei denen es sich bei dem Wert in der Spalte **Typ** um eine **benutzerdefinierte ausgehende Spam Richtlinie**handelt.</span><span class="sxs-lookup"><span data-stu-id="23553-269">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="23553-270">Beachten Sie die Werte in der Spalte **Priorität**:</span><span class="sxs-lookup"><span data-stu-id="23553-270">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="23553-271">Die benutzerdefinierte Richtlinie für ausgehende Spam mit der höchsten ![Priorität hat den](../../media/ITPro-EAC-DownArrowIcon.png) Abwärtspfeil-Symbolwert **0**.</span><span class="sxs-lookup"><span data-stu-id="23553-271">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="23553-272">Die benutzerdefinierte Richtlinie für ausgehende Spam mit der niedrigsten ![Priorität hat den](../../media/ITPro-EAC-UpArrowIcon.png) Wert nach oben Pfeilsymbol ![ **n** (beispielsweise nach oben Pfeilsymbol](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="23553-272">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="23553-273">Wenn Sie drei oder mehr benutzerdefinierte ausgehende Spam Richtlinien haben, haben die Richtlinien zwischen der höchsten und ![der niedrigsten Priorität](../../media/ITPro-EAC-UpArrowIcon.png)![Werte nach oben](../../media/ITPro-EAC-DownArrowIcon.png) Pfeilsymbol nach unten Pfeil ![Symbol **n** (](../../media/ITPro-EAC-UpArrowIcon.png)![beispielsweise nach](../../media/ITPro-EAC-DownArrowIcon.png) oben Pfeilsymbol nach unten Pfeilsymbol **2**).</span><span class="sxs-lookup"><span data-stu-id="23553-273">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="23553-274">Klicken Sie auf</span><span class="sxs-lookup"><span data-stu-id="23553-274">Click</span></span> ![Pfeil-nach-oben-Symbol](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="23553-276">oder</span><span class="sxs-lookup"><span data-stu-id="23553-276">or</span></span> ![Pfeil-nach-unten-Symbol,](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="23553-278">um die benutzerdefinierte Richtlinie für ausgehende Spam in der Liste Priorität nach oben oder nach unten zu verlagern.</span><span class="sxs-lookup"><span data-stu-id="23553-278">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="23553-279">Verwenden des Security & Compliance Center zum Entfernen von ausgehenden Spam Richtlinien</span><span class="sxs-lookup"><span data-stu-id="23553-279">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="23553-280">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="23553-280">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="23553-281">Klicken Sie ![auf der Seite **Anti-Spam-Einstellungen** auf](../../media/scc-expand-icon.png) Symbol erweitern, um die benutzerdefinierte Richtlinie zu erweitern, die Sie löschen möchten (die Spalte **Typ** ist eine **benutzerdefinierte ausgehende Spam Richtlinie**).</span><span class="sxs-lookup"><span data-stu-id="23553-281">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="23553-282">Klicken Sie in den angezeigten erweiterten Richtliniendetails auf **Richtlinie löschen**.</span><span class="sxs-lookup"><span data-stu-id="23553-282">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="23553-283">Klicken Sie im angezeigten Dialogfeld mit der Warnung auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="23553-283">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="23553-284">Die Standardrichtlinie kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="23553-284">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="23553-285">Verwenden von Exchange Online PowerShell oder Exchange Online Protection PowerShell zum Konfigurieren von ausgehenden Spam Richtlinien</span><span class="sxs-lookup"><span data-stu-id="23553-285">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="23553-286">Verwenden von PowerShell zum Erstellen von ausgehenden Spam Richtlinien</span><span class="sxs-lookup"><span data-stu-id="23553-286">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="23553-287">Das Erstellen einer ausgehenden Spam Richtlinie in PowerShell erfolgt in einem zweistufigen Prozess:</span><span class="sxs-lookup"><span data-stu-id="23553-287">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="23553-288">Erstellen Sie die Richtlinie für ausgehende Spamfilter.</span><span class="sxs-lookup"><span data-stu-id="23553-288">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="23553-289">Erstellen Sie die Filterregel für ausgehende Spam, die die Richtlinie für ausgehende Spamfilter angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="23553-289">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="23553-290">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="23553-290">**Notes**:</span></span>

- <span data-ttu-id="23553-291">Sie können eine neue Filterregel für ausgehende Spam erstellen und ihr eine vorhandene, nicht zugeordnete Filterrichtlinie für ausgehende Spam zuweisen.</span><span class="sxs-lookup"><span data-stu-id="23553-291">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="23553-292">Eine ausgehende Spamfilter Regel kann nicht mehr als einer ausgehenden Spamfilter Richtlinie zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="23553-292">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="23553-293">Sie können die folgenden Einstellungen für neue Richtlinien für ausgehende Spamfilter in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Security & Compliance Center verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="23553-293">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="23553-294">Erstellen Sie die neue Richtlinie als deaktiviert (_aktiviert_ `$false` im Cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="23553-294">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="23553-295">Legen Sie die Priorität der Richtlinie während der Erstellung (_Prioritäts_ _ \<Nummer\>_) für das Cmdlet **New-HostedOutboundSpamFilterRule** fest.</span><span class="sxs-lookup"><span data-stu-id="23553-295">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="23553-296">Eine neue Richtlinie für ausgehende Spamfilter, die Sie in PowerShell erstellen, ist erst im Security & Compliance Center sichtbar, wenn Sie die Richtlinie einer Spamfilter Regel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="23553-296">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="23553-297">Schritt 1: Erstellen einer ausgehenden Spamfilter Richtlinie mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="23553-297">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="23553-298">Verwenden Sie die folgende Syntax, um eine Filterrichtlinie für ausgehende Spam zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="23553-298">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="23553-299">In diesem Beispiel wird eine neue Richtlinie für ausgehende Spamfilter namens "Contoso Executives" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="23553-299">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="23553-300">Die Empfänger Raten Begrenzungen sind auf kleinere Werte beschränkt, die von den Standardeinstellungen abweichen.</span><span class="sxs-lookup"><span data-stu-id="23553-300">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="23553-301">Weitere Informationen finden Sie unter [sending Limits Across Office 365 Options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="23553-301">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="23553-302">Nachdem eine der Grenzwerte erreicht wurde, wird verhindert, dass der Benutzer Nachrichten sendet.</span><span class="sxs-lookup"><span data-stu-id="23553-302">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="23553-303">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="23553-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="23553-304">Schritt 2: Erstellen einer ausgehenden Spamfilter Regel mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="23553-304">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="23553-305">Verwenden Sie die folgende Syntax, um eine Filterregel für ausgehende Spam zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="23553-305">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="23553-306">In diesem Beispiel wird eine neue ausgehende Spamfilter Regel namens "Contoso Executives" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="23553-306">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="23553-307">Die Richtlinie für ausgehende Spamfilter mit dem Namen "Contoso Executives" ist der Regel zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="23553-307">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="23553-308">Die Regel gilt für Mitglieder der Gruppe mit dem Namen „Contoso Executive Group“.</span><span class="sxs-lookup"><span data-stu-id="23553-308">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="23553-309">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="23553-309">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="23553-310">Verwenden von PowerShell zum Anzeigen von Richtlinien für ausgehende Spamfilter</span><span class="sxs-lookup"><span data-stu-id="23553-310">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="23553-311">Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller ausgehenden Spamfilter Richtlinien zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="23553-311">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="23553-312">Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Richtlinie für ausgehende Spamfilter zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="23553-312">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="23553-313">In diesem Beispiel werden alle Eigenschaftswerte für die ausgehende Spamfilter Richtlinie "Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="23553-313">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="23553-314">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="23553-314">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="23553-315">Verwenden von PowerShell zum Anzeigen von Regeln für ausgehende Spamfilter</span><span class="sxs-lookup"><span data-stu-id="23553-315">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="23553-316">Verwenden Sie die folgende Syntax, um vorhandene Filterregeln für ausgehende Spam anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="23553-316">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="23553-317">Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller ausgehenden spamfilterregeln zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="23553-317">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="23553-318">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="23553-318">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="23553-319">Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Filterregel für ausgehende Spam Daten zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="23553-319">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="23553-320">In diesem Beispiel werden alle Eigenschaftswerte für die ausgehende Spamfilter Regel namens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="23553-320">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="23553-321">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="23553-321">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="23553-322">Verwenden von PowerShell zum Ändern von Richtlinien für ausgehende Spamfilter</span><span class="sxs-lookup"><span data-stu-id="23553-322">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="23553-323">Die gleichen Einstellungen stehen zur Verfügung, wenn Sie eine Filterrichtlinie für Schadsoftware in PowerShell wie beim Erstellen der Richtlinie wie im Abschnitt [Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für ausgehende Spamfilter](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) weiter oben in diesem Thema beschrieben ändern.</span><span class="sxs-lookup"><span data-stu-id="23553-323">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="23553-324">**Hinweis**: Es ist nicht möglich, eine ausgehende Spamfilter Richtlinie umzubenennen (das Cmdlet " **HostedOutboundSpamFilterPolicy** " hat keinen Parameter " _Name_ ").</span><span class="sxs-lookup"><span data-stu-id="23553-324">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="23553-325">Wenn Sie eine ausgehende Spam Richtlinie im Security & Compliance Center umbenennen, benennen Sie die ausgehende Spamfilter _Regel_nur um.</span><span class="sxs-lookup"><span data-stu-id="23553-325">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="23553-326">Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilter Richtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="23553-326">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="23553-327">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="23553-327">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="23553-328">Verwenden von PowerShell zum Ändern von Regeln für ausgehende Spamfilter</span><span class="sxs-lookup"><span data-stu-id="23553-328">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="23553-329">Die einzige Einstellung, die beim Ändern einer ausgehenden Spamfilter Regel in PowerShell nicht verfügbar ist, ist der Parameter _Enabled_ , mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="23553-329">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="23553-330">Informationen zum Aktivieren oder Deaktivieren vorhandener Filterregeln für ausgehende Spamfilter finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="23553-330">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="23553-331">Andernfalls stehen keine zusätzlichen Einstellungen zur Verfügung, wenn Sie eine ausgehende Spamfilter Regel in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="23553-331">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="23553-332">Die gleichen Einstellungen sind verfügbar, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen eines Filters für ausgehende Spamfilter](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) weiter oben in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="23553-332">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="23553-333">Verwenden Sie die folgende Syntax, um eine Filterregel für ausgehende Spam zu ändern:</span><span class="sxs-lookup"><span data-stu-id="23553-333">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="23553-334">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="23553-334">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="23553-335">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für ausgehende Spamfilter</span><span class="sxs-lookup"><span data-stu-id="23553-335">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="23553-336">Durch Aktivieren oder Deaktivieren einer ausgehenden Spamfilter Regel in PowerShell wird die gesamte ausgehende Spam Richtlinie (die ausgehende Spamfilter Regel und die zugewiesene Richtlinie für ausgehende Spamfilter) aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="23553-336">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="23553-337">Sie können die standardmäßige ausgehende Spam Richtlinie nicht aktivieren oder deaktivieren (Sie wird immer auf alle Empfänger angewendet).</span><span class="sxs-lookup"><span data-stu-id="23553-337">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="23553-338">Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilter Regel in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="23553-338">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="23553-339">In diesem Beispiel wird die ausgehende Spamfilter Regel namens "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="23553-339">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="23553-340">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="23553-340">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="23553-341">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) und [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="23553-341">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="23553-342">Verwenden von PowerShell zum Festlegen der Priorität von ausgehenden spamfilterregeln</span><span class="sxs-lookup"><span data-stu-id="23553-342">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="23553-343">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="23553-343">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="23553-344">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="23553-344">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="23553-345">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="23553-345">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="23553-346">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="23553-346">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="23553-347">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="23553-347">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="23553-348">Verwenden Sie die folgende Syntax, um die Priorität einer ausgehenden Spamfilter Regel in PowerShell festzulegen:</span><span class="sxs-lookup"><span data-stu-id="23553-348">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="23553-p146">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="23553-p146">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="23553-351">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="23553-351">**Notes**:</span></span>

- <span data-ttu-id="23553-352">Wenn Sie die Priorität einer neuen Regel beim Erstellen festlegen möchten, verwenden Sie stattdessen den Parameter _Priority_ für das Cmdlet **New-HostedOutboundSpamFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="23553-352">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="23553-353">Die ausgehende standardmäßige Spamfilter Richtlinie verfügt nicht über eine entsprechende Spamfilter Regel, und Sie hat immer den **niedrigsten**Wert für die unveränderbare Priorität.</span><span class="sxs-lookup"><span data-stu-id="23553-353">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="23553-354">Verwenden von PowerShell zum Entfernen von ausgehenden Spamfilter Richtlinien</span><span class="sxs-lookup"><span data-stu-id="23553-354">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="23553-355">Wenn Sie PowerShell zum Entfernen einer ausgehenden Spamfilter Richtlinie verwenden, wird die entsprechende Filterregel für ausgehende Spam nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="23553-355">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="23553-356">Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilter Richtlinie in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="23553-356">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="23553-357">In diesem Beispiel wird die Richtlinie für ausgehende Spamfilter namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="23553-357">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="23553-358">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="23553-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="23553-359">Verwenden von PowerShell zum Entfernen von Filterregeln für ausgehende Spam</span><span class="sxs-lookup"><span data-stu-id="23553-359">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="23553-360">Wenn Sie mithilfe von PowerShell eine ausgehende Spamfilter Regel entfernen, wird die entsprechende Filterrichtlinie für ausgehende Spam nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="23553-360">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="23553-361">Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilter Regel in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="23553-361">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="23553-362">In diesem Beispiel wird die ausgehende Spamfilter Regel namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="23553-362">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="23553-363">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="23553-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="23553-364">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23553-364">For more information</span></span>

[<span data-ttu-id="23553-365">Entfernen von blockierten Benutzern aus dem Portal "Eingeschränkte Benutzer" in Office 365</span><span class="sxs-lookup"><span data-stu-id="23553-365">Remove blocked users from the Restricted Users portal in Office 365</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="23553-366">Pool für besonders riskante Zustellungen für ausgehende Nachrichten</span><span class="sxs-lookup"><span data-stu-id="23553-366">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="23553-367">Häufig gestellte Fragen zum Antispamschutz</span><span class="sxs-lookup"><span data-stu-id="23553-367">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
