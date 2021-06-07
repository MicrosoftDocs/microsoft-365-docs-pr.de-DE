---
title: Konfigurieren der Filterung für ausgehende Spamnachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie ausgehende Spamrichtlinien in Exchange Online Protection (EOP) angezeigt, erstellt, geändert und gelöscht werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c2f68cac05f296771fc56d400e95d014811fe03a
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793004"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="a0440-103">Konfigurieren der ausgehenden Spamfilterung in EOP</span><span class="sxs-lookup"><span data-stu-id="a0440-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a0440-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="a0440-104">**Applies to**</span></span>
- [<span data-ttu-id="a0440-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a0440-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a0440-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="a0440-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a0440-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a0440-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a0440-108">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächern werden ausgehende E-Mail-Nachrichten, die über EOP gesendet werden, automatisch auf Spam und ungewöhnliche Sendeaktivitäten überprüft.</span><span class="sxs-lookup"><span data-stu-id="a0440-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="a0440-109">Ausgehende Spamnachrichten von einem Benutzer in Ihrer Organisation weisen in der Regel auf ein kompromittiertes Konto hin.</span><span class="sxs-lookup"><span data-stu-id="a0440-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="a0440-110">Verdächtige ausgehende Nachrichten werden als Spam gekennzeichnet (unabhängig von der Spam-Konfidenzstufe oder SCL) und werden über den [Übermittlungspool](high-risk-delivery-pool-for-outbound-messages.md) mit hohem Risiko weitergeleitet, um den Ruf des Diensts zu schützen (d. a. Microsoft 365 Quell-E-Mail-Server von IP-Sperrlisten fernzuhalten).</span><span class="sxs-lookup"><span data-stu-id="a0440-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="a0440-111">Administratoren werden automatisch über verdächtige ausgehende E-Mail-Aktivitäten benachrichtigt und Benutzer über [Warnungsrichtlinien](../../compliance/alert-policies.md)blockiert.</span><span class="sxs-lookup"><span data-stu-id="a0440-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="a0440-112">EOP verwendet ausgehende Spamrichtlinien als Teil des allgemeinen Schutzes Ihrer Organisation gegen Spam.</span><span class="sxs-lookup"><span data-stu-id="a0440-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="a0440-113">Weitere Informationen finden Sie unter [Antispamschutz](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="a0440-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="a0440-114">Administratoren können die standardmäßige richtlinie für ausgehende Spamnachrichten anzeigen, bearbeiten und konfigurieren (aber nicht löschen).</span><span class="sxs-lookup"><span data-stu-id="a0440-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="a0440-115">Für eine höhere Granularität können Sie auch benutzerdefinierte ausgehende Spamrichtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="a0440-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="a0440-116">Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="a0440-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="a0440-117">Sie können ausgehende Spamrichtlinien im Microsoft 365 Security Center oder in PowerShell konfigurieren (Exchange Online PowerShell für Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer).</span><span class="sxs-lookup"><span data-stu-id="a0440-117">You can configure outbound spam policies in the Microsoft 365 security center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="a0440-118">Die grundlegenden Elemente einer Richtlinie für ausgehende Spamnachrichten in EOP sind:</span><span class="sxs-lookup"><span data-stu-id="a0440-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="a0440-119">Die Richtlinie für **den ausgehenden Spamfilter:** Gibt die Aktionen für ausgehende Spamfilterbewertungen und die Benachrichtigungsoptionen an.</span><span class="sxs-lookup"><span data-stu-id="a0440-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="a0440-120">**Die Ausgehende Spamfilterregel:** Gibt die Prioritäts- und Empfängerfilter (für die die Richtlinie gilt) für eine richtlinie für ausgehende Spamfilter an.</span><span class="sxs-lookup"><span data-stu-id="a0440-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="a0440-121">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie ausgehende Spam-Richtlinien im Security Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="a0440-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the security center:</span></span>

- <span data-ttu-id="a0440-122">Wenn Sie eine Richtlinie erstellen, erstellen Sie tatsächlich eine ausgehende Spamfilterregel und die zugeordnete Richtlinie für den ausgehenden Spamfilter gleichzeitig mit demselben Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="a0440-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="a0440-123">Wenn Sie eine Richtlinie ändern, ändern Einstellungen, die sich auf den Namen, die Priorität, aktiviert oder deaktiviert beziehen, und Empfängerfilter die ausgehende Spamfilterregel.</span><span class="sxs-lookup"><span data-stu-id="a0440-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="a0440-124">Alle anderen Einstellungen ändern die zugeordnete Richtlinie für ausgehende Spamfilter.</span><span class="sxs-lookup"><span data-stu-id="a0440-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="a0440-125">Wenn Sie eine Richtlinie entfernen, werden die Filterregel für ausgehende Spamnachrichten und die zugeordnete Richtlinie für den ausgehenden Spamfilter entfernt.</span><span class="sxs-lookup"><span data-stu-id="a0440-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="a0440-126">In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt.</span><span class="sxs-lookup"><span data-stu-id="a0440-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="a0440-127">Weitere Informationen finden Sie im Abschnitt ["Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies"](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="a0440-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="a0440-128">Jede Organisation verfügt über eine integrierte richtlinie für ausgehende Spamnachrichten mit dem Namen "Standard", die über die folgenden Eigenschaften verfügt:</span><span class="sxs-lookup"><span data-stu-id="a0440-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="a0440-129">Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine ausgehende Spamfilterregel (Empfängerfilter) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a0440-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="a0440-130">Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet).</span><span class="sxs-lookup"><span data-stu-id="a0440-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="a0440-131">Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer Vorrang vor der Richtlinie „Standard“.</span><span class="sxs-lookup"><span data-stu-id="a0440-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="a0440-132">Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="a0440-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="a0440-133">Um die Effektivität der ausgehenden Spamfilterung zu erhöhen, können Sie benutzerdefinierte Richtlinien für ausgehende Spamnachrichten mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0440-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a0440-134">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="a0440-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a0440-135">Sie öffnen das Security Center über <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="a0440-135">You open the security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="a0440-136">Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://security.microsoft.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="a0440-136">To go directly to the **Anti-spam settings** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="a0440-137">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a0440-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a0440-138">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a0440-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a0440-139">Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:</span><span class="sxs-lookup"><span data-stu-id="a0440-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a0440-140">Um ausgehende Spamrichtlinien hinzuzufügen, zu ändern und zu löschen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.</span><span class="sxs-lookup"><span data-stu-id="a0440-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a0440-141">Für den schreibgeschützten Zugriff auf ausgehende Spamrichtlinien müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.</span><span class="sxs-lookup"><span data-stu-id="a0440-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a0440-142">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="a0440-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="a0440-143">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="a0440-143">**Notes**:</span></span>

  - <span data-ttu-id="a0440-144">Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a0440-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a0440-145">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a0440-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="a0440-146">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="a0440-146">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="a0440-147">Unsere empfohlenen Einstellungen für ausgehende Spamrichtlinien finden Sie unter [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="a0440-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="a0440-148">Die [Standardmäßige Warnungsrichtlinien](../../compliance/alert-policies.md) namens **"E-Mail-Sendegrenzwert" wurde überschritten,** **verdächtige E-Mail-Versandmuster erkannt,** und der Benutzer, dem das **Senden von E-Mails eingeschränkt** ist, sendet bereits E-Mail-Benachrichtigungen an Mitglieder der Gruppe **"TenantAdmins** (**Globale Administratoren)**" über ungewöhnliche ausgehende E-Mail-Aktivitäten und blockierte Benutzer aufgrund ausgehender Spamnachrichten.</span><span class="sxs-lookup"><span data-stu-id="a0440-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="a0440-149">Weitere Informationen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="a0440-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="a0440-150">Es wird empfohlen, diese Warnungsrichtlinien anstelle der Benachrichtigungsoptionen in ausgehenden Spamrichtlinien zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0440-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security-center-to-create-outbound-spam-policies"></a><span data-ttu-id="a0440-151">Verwenden des Sicherheitscenters zum Erstellen ausgehender Spamrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a0440-151">Use the security center to create outbound spam policies</span></span>

<span data-ttu-id="a0440-152">Beim Erstellen einer benutzerdefinierten Richtlinie für ausgehende Spamnachrichten im Security Center werden die Spamfilterregel und die zugeordnete Spamfilterrichtlinie gleichzeitig mit demselben Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="a0440-152">Creating a custom outbound spam policy in the security center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="a0440-153">Wechseln Sie im Security Center zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** \> **Richtlinien**\> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="a0440-153">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a0440-154">Klicken Sie auf der Seite **"Antispamrichtlinien"** auf ![ das Symbol ](../../media/m365-cc-sc-create-icon.png) **"Richtlinie erstellen",** und wählen Sie dann in der Dropdownliste **"Ausgehend"** aus.</span><span class="sxs-lookup"><span data-stu-id="a0440-154">On the **Anti-spam policies** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create policy** and then select **Outbound** from the drop down list.</span></span>

3. <span data-ttu-id="a0440-155">Der Richtlinienassistent wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a0440-155">The policy wizard opens.</span></span> <span data-ttu-id="a0440-156">Konfigurieren Sie auf der Seite **Benennen Sie Ihre Richtlinie** diese Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="a0440-156">On the **Name your policy page**, configure these settings:</span></span>
   - <span data-ttu-id="a0440-157">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="a0440-157">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="a0440-158">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="a0440-158">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="a0440-159">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a0440-159">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a0440-160">Auf der dann angezeigten Seite **Benutzer, Gruppen und Domänen** identifizieren Sie die internen Empfänger, für welche die Richtlinie gilt (Empfängerbedingungen):</span><span class="sxs-lookup"><span data-stu-id="a0440-160">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="a0440-161">**Benutzer**: Die angegebenen Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="a0440-161">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="a0440-162">**Gruppen**: Die angegebenen Verteilergruppen, E-Mail-aktivierten Sicherheitsgruppen oder Microsoft 365-Gruppen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="a0440-162">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="a0440-163">**Domänen**: Alle Empfänger in der angegebenen [akzeptierten Domäne](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="a0440-163">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="a0440-164">Klicken Sie auf das entsprechende Feld, beginnen Sie mit der Eingabe eines Wertes, und wählen Sie den gewünschten Wert aus den Ergebnissen aus.</span><span class="sxs-lookup"><span data-stu-id="a0440-164">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="a0440-165">Wiederholen Sie diesen Vorgang so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="a0440-165">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="a0440-166">Um einen vorhandenen Wert zu entfernen, klicken Sie auf das</span><span class="sxs-lookup"><span data-stu-id="a0440-166">To remove an existing value, click remove</span></span> ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a0440-168">neben dem Wert.</span><span class="sxs-lookup"><span data-stu-id="a0440-168">next to the value.</span></span>

   <span data-ttu-id="a0440-169">Für Benutzer oder Gruppen können Sie die meisten Bezeichner verwenden (Name, Anzeigename, Alias, E-Mail-Adresse, Kontoname usw.), aber in den Ergebnissen wird der entsprechende Anzeigename angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0440-169">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="a0440-170">Geben Sie für Benutzer einen einzelnen Stern (\*) ein, um alle verfügbaren Werte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a0440-170">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="a0440-171">Mehreren Werten in der gleichen Bedingung verwenden die „ODER“-Logik (z. B. _\<recipient1\>_ ODER _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="a0440-171">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="a0440-172">Unterschiedlichen Bedingungen verwenden die „UND“-Logik (z. B. _\<recipient1\>_ UND _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="a0440-172">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="a0440-173">**Ausschließen dieser Benutzer, Gruppen und Domänen**: Um Ausnahmen für die internen Empfänger hinzuzufügen, für welche die Richtlinie gilt (Empfängerausnahmen), wählen Sie diese Option und konfigurieren Sie die Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="a0440-173">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="a0440-174">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="a0440-174">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="a0440-175">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a0440-175">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a0440-176">Konfigurieren Sie auf der seite **"Schutzeinstellungen",** die geöffnet wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="a0440-176">On the **Protection settings** page that opens, configure the following settings:</span></span>
   - <span data-ttu-id="a0440-177">**Nachrichtengrenzwerte:** Die Einstellungen in diesem Abschnitt konfigurieren die Grenzwerte für ausgehende E-Mail-Nachrichten aus **Exchange Online** Postfächern:</span><span class="sxs-lookup"><span data-stu-id="a0440-177">**Message limits**: The settings in this section configure the limits for outbound email messages from **Exchange Online** mailboxes:</span></span>
     - <span data-ttu-id="a0440-178">**Festlegen eines Grenzwerts für externe Nachrichten:** Die maximale Anzahl externer Empfänger pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="a0440-178">**Set an external message limit**: The maximum number of external recipients per hour.</span></span>
     - <span data-ttu-id="a0440-179">**Legen Sie ein internes Nachrichtenlimit fest:** Die maximale Anzahl interner Empfänger pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="a0440-179">**Set an internal message limit**: The maximum number of internal recipients per hour.</span></span>
     - <span data-ttu-id="a0440-180">**Legen Sie ein tägliches Nachrichtenlimit fest:** Die maximale Gesamtanzahl von Empfängern pro Tag.</span><span class="sxs-lookup"><span data-stu-id="a0440-180">**Set a daily message limit**: The maximum total number of recipients per day.</span></span>

     <span data-ttu-id="a0440-181">Ein gültiger Wert ist 0 bis 10000.</span><span class="sxs-lookup"><span data-stu-id="a0440-181">A valid value is 0 to 10000.</span></span> <span data-ttu-id="a0440-182">Der Standardwert ist 0, was bedeutet, dass die Dienststandardwerte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0440-182">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="a0440-183">Weitere Informationen finden Sie unter [Senden von Grenzwerten.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)</span><span class="sxs-lookup"><span data-stu-id="a0440-183">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

    <span data-ttu-id="a0440-184">Geben Sie einen Wert in das Feld ein, oder verwenden Sie die Pfeile zum Vergrößern/Verkleinern des Felds.</span><span class="sxs-lookup"><span data-stu-id="a0440-184">Enter a value in the box, or use the increase/decrease arrows on the box.</span></span>

   - <span data-ttu-id="a0440-185">**Einschränkung für Benutzer, die das Nachrichtenlimit erreichen:** Wählen Sie eine Aktion aus der Dropdownliste aus, wenn eine der Grenzwerte im Abschnitt **"Schutzeinstellungen"** überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="a0440-185">**Restriction placed on users who reach the message limit**: Select an action from the drop down list when any of the limits in the **Protection settings** section are exceeded.</span></span>

     <span data-ttu-id="a0440-186">Für alle Aktionen erhalten die im Benutzer angegebenen Empfänger, die das **Senden von E-Mail-Warnungsrichtlinien eingeschränkt** haben (und in der jetzt redundanten **Benachrichtigung dieser Benutzer und Gruppen, wenn ein Absender aufgrund des Sendens ausgehender Spam-Einstellungen** später auf dieser Seite blockiert wird) E-Mail-Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="a0440-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify these users and groups if a sender is blocked due to sending outbound spam** setting later on this page) receive email notifications.</span></span>

     - <span data-ttu-id="a0440-187">**Beschränken Sie das Senden von E-Mails durch den Benutzer bis zum folgenden Tag:** Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="a0440-187">**Restrict the user from sending mail until the following day**: This is the default value.</span></span> <span data-ttu-id="a0440-188">E-Mail-Benachrichtigungen werden gesendet, und der Benutzer kann basierend auf der UTC-Zeit bis zum folgenden Tag keine weiteren Nachrichten mehr senden.</span><span class="sxs-lookup"><span data-stu-id="a0440-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="a0440-189">Es gibt keine Möglichkeit für den Administrator, diesen Block außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="a0440-189">There is no way for the admin to override this block.</span></span>
       - <span data-ttu-id="a0440-190">Die Aktivitätswarnung namens **"Benutzer, der das Senden von E-Mails eingeschränkt** hat" benachrichtigt Administratoren (per E-Mail und auf der Seite **"Warnungen anzeigen").**</span><span class="sxs-lookup"><span data-stu-id="a0440-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>
       - <span data-ttu-id="a0440-191">Alle Empfänger, die in der Richtlinie **"Bestimmte Personen benachrichtigen" angegeben sind, wenn ein Absender aufgrund des Sendens ausgehender Spam-Einstellungen** in der Richtlinie blockiert wird, werden ebenfalls benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="a0440-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>
       - <span data-ttu-id="a0440-192">Der Benutzer kann basierend auf der UTC-Zeit bis zum folgenden Tag keine weiteren Nachrichten mehr senden.</span><span class="sxs-lookup"><span data-stu-id="a0440-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="a0440-193">Es gibt keine Möglichkeit für den Administrator, diesen Block außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="a0440-193">There is no way for the admin to override this block.</span></span>
     - <span data-ttu-id="a0440-194">**Einschränken, dass der Benutzer E-Mails sendet:** E-Mail-Benachrichtigungen werden gesendet, der Benutzer wird **eingeschränkten Benutzern** im Security Center <https://security.microsoft.com/restrictedusers> hinzugefügt, und der Benutzer kann keine E-Mails senden, bis er von einem Administrator aus **eingeschränkten Benutzern** entfernt wird. Nachdem ein Administrator den Benutzer aus der Liste entfernt hat, wird der Benutzer für diesen Tag nicht erneut eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="a0440-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to **Restricted users** <https://security.microsoft.com/restrictedusers> in the security center, and the user can't send email until they're removed from **Restricted users** by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="a0440-195">Anweisungen finden Sie unter [Entfernen eines Benutzers aus dem Portal für eingeschränkte Benutzer nach dem Senden von Spam-E-Mails.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="a0440-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>
     - <span data-ttu-id="a0440-196">**Keine Aktion, nur Warnung:** E-Mail-Benachrichtigungen werden gesendet.</span><span class="sxs-lookup"><span data-stu-id="a0440-196">**No action, alert only**: Email notifications are sent.</span></span>

   - <span data-ttu-id="a0440-197">**Weiterleitungsregeln:** Verwenden Sie die Einstellungen in diesem Abschnitt, um die automatische E-Mail-Weiterleitung durch **Exchange Online Postfächer** an externe Absender zu steuern.</span><span class="sxs-lookup"><span data-stu-id="a0440-197">**Forwarding rules**: Use the settings in this section to control automatic email forwarding by **Exchange Online mailboxes** to external senders.</span></span> <span data-ttu-id="a0440-198">Weitere Informationen finden Sie unter [Steuerung der automatischen externen E-Mail-Weiterleitung in Microsoft 365](external-email-forwarding.md).</span><span class="sxs-lookup"><span data-stu-id="a0440-198">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="a0440-199">Wenn die automatische Weiterleitung deaktiviert ist, erhält der Empfänger einen Unzustellbarkeitsbericht (auch als Unzustellbarkeitsbericht oder Unzustellbarkeitsnachricht bezeichnet), wenn externe Absender E-Mails an ein Postfach senden, das über eine Weiterleitung verfügt.</span><span class="sxs-lookup"><span data-stu-id="a0440-199">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="a0440-200">Wenn die Nachricht von einem internen Absender gesendet wird **und** die Weiterleitungsmethode die [Postfachweiterleitung](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) ist (auch bekannt als _SMTP-Weiterleitung),_ erhält der interne Absender den NDR.</span><span class="sxs-lookup"><span data-stu-id="a0440-200">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="a0440-201">Der interne Absender erhält keinen NDR, wenn die Weiterleitung aufgrund einer Posteingangsregel erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="a0440-201">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

     <span data-ttu-id="a0440-202">Wählen Sie eine der folgenden Aktionen aus der Dropdownliste "Regeln für die **automatische Weiterleitung"** aus:</span><span class="sxs-lookup"><span data-stu-id="a0440-202">Select one of the following actions from the **Automatic forwarding rules** drop down list:</span></span>

     - <span data-ttu-id="a0440-203">**Automatisch – systemgesteuert:** Ermöglicht ausgehende Spamfilterung, um die automatische externe E-Mail-Weiterleitung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="a0440-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="a0440-204">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="a0440-204">This is the default value.</span></span>
     - <span data-ttu-id="a0440-205">**Aktiviert:** Die automatische externe E-Mail-Weiterleitung wird von der Richtlinie nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a0440-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
     - <span data-ttu-id="a0440-206">**Deaktiviert:** Alle automatischen externen E-Mail-Weiterleitungen werden von der Richtlinie deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a0440-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

   - <span data-ttu-id="a0440-207">**Benachrichtigungen:** Verwenden Sie die Einstellungen im Abschnitt, um zusätzliche Empfänger zu konfigurieren, die Kopien und Benachrichtigungen verdächtiger ausgehender E-Mail-Nachrichten erhalten sollen:</span><span class="sxs-lookup"><span data-stu-id="a0440-207">**Notifications**: Use the settings in the section to configure additional recipients who should receive copies and notifications of suspicious outbound email messages:</span></span>

     - <span data-ttu-id="a0440-208">**Senden Sie eine Kopie von verdächtigen ausgehenden Nachrichten, die diese Grenzwerte überschreiten, an diese Benutzer und Gruppen:** Diese Einstellung fügt die angegebenen Empfänger zum Bcc-Feld verdächtiger ausgehender Nachrichten hinzu.</span><span class="sxs-lookup"><span data-stu-id="a0440-208">**Send a copy of suspicious outbound that exceed these limits to these users and groups**: This setting adds the specified recipients to the Bcc field of suspicious outbound messages.</span></span>

       > [!NOTE]
       > <span data-ttu-id="a0440-209">Diese Einstellung funktioniert nur in der standardmäßigen Richtlinie für ausgehende Spamnachrichten.</span><span class="sxs-lookup"><span data-stu-id="a0440-209">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="a0440-210">Es funktioniert nicht in benutzerdefinierten ausgehenden Spamrichtlinien, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="a0440-210">It doesn't work in custom outbound spam policies that you create.</span></span>

       <span data-ttu-id="a0440-211">Aktivieren Sie das Kontrollkästchen, um diese Einstellung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a0440-211">To enable this setting, select the check box.</span></span> <span data-ttu-id="a0440-212">Klicken Sie in das angezeigte Feld, geben Sie eine gültige E-Mail-Adresse ein, und drücken Sie die EINGABETASTE, oder wählen Sie den vollständigen Wert aus, der unterhalb des Felds angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a0440-212">In the box that appears, click in the box, enter a valid email address, and then press Enter or select the complete value that's displayed below the box.</span></span>

       <span data-ttu-id="a0440-213">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="a0440-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a0440-214">Um einen vorhandenen Wert zu entfernen, klicken Sie auf das</span><span class="sxs-lookup"><span data-stu-id="a0440-214">To remove an existing value, click remove</span></span> ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a0440-216">neben dem Wert.</span><span class="sxs-lookup"><span data-stu-id="a0440-216">next to the value.</span></span>

   - <span data-ttu-id="a0440-217">**Diese Benutzer und Gruppen benachrichtigen, wenn ein Absender aufgrund des Sendens ausgehender Spamnachrichten blockiert wird**</span><span class="sxs-lookup"><span data-stu-id="a0440-217">**Notify these users and groups if a sender is blocked due to sending outbound spam**</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="a0440-218">Diese Einstellung ist dabei, von ausgehenden Spamrichtlinien veraltet zu sein.</span><span class="sxs-lookup"><span data-stu-id="a0440-218">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="a0440-219">Die [Standardbenachrichtigungsrichtlinie](../../compliance/alert-policies.md) mit dem Namen **"Benutzer, der das Senden von E-Mails eingeschränkt** hat" sendet bereits E-Mail-Benachrichtigungen an Mitglieder der Gruppe **TenantAdmins** (**Globale Administratoren**), wenn Benutzer aufgrund der Überschreitung der Grenzwerte im Abschnitt **"Empfängergrenzwerte"** blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="a0440-219">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="a0440-220">**Es wird dringend empfohlen, die Warnungsrichtlinie anstelle dieser Einstellung in der Richtlinie für ausgehende Spamnachrichten zu verwenden, um Administratoren und andere Benutzer zu benachrichtigen.**</span><span class="sxs-lookup"><span data-stu-id="a0440-220">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="a0440-221">Anweisungen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="a0440-221">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

   <span data-ttu-id="a0440-222">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a0440-222">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="a0440-223">Überprüfen Sie auf der angezeigten Seite **Überprüfung** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="a0440-223">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="a0440-224">Sie können in jedem Abschnitt **Bearbeiten** auswählen, um die Einstellungen in diesem Abschnitt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a0440-224">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="a0440-225">Sie können auch auf **"Zurück"** klicken oder die entsprechende Seite im Assistenten auswählen.</span><span class="sxs-lookup"><span data-stu-id="a0440-225">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="a0440-226">Wenn Sie den Vorgang abgeschlossen haben, klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a0440-226">When you're finished, click **Create**.</span></span>

7. <span data-ttu-id="a0440-227">Klicken Sie in der angezeigten Bestätigungsseite auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="a0440-227">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-outbound-spam-policies"></a><span data-ttu-id="a0440-228">Verwenden des Sicherheitscenters zum Anzeigen ausgehender Spamrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a0440-228">Use the security center to view outbound spam policies</span></span>

1. <span data-ttu-id="a0440-229">Wechseln Sie im Security Center zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** \> **Richtlinien**\> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="a0440-229">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a0440-230">Suchen Sie auf der Seite **Antispamrichtlinien** nach einem der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="a0440-230">On the **Anti-spam policies** page, look for one of the following values:</span></span>
   - <span data-ttu-id="a0440-231">Der **Typwert** ist **eine benutzerdefinierte Richtlinie für ausgehende Spamnachrichten.**</span><span class="sxs-lookup"><span data-stu-id="a0440-231">The **Type** value is **Custom outbound spam policy**</span></span>
   - <span data-ttu-id="a0440-232">Der **Name-Wert** ist **eine ausgehende Antispamrichtlinie (Standardeinstellung)**</span><span class="sxs-lookup"><span data-stu-id="a0440-232">The **Name** value is **Anti-spam outbound policy (Default)**</span></span>

   <span data-ttu-id="a0440-233">Die folgenden Eigenschaften werden in der Liste der Antispamrichtlinien angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a0440-233">The following properties are displayed in the list of anti-spam policies:</span></span>

   - <span data-ttu-id="a0440-234">**Name**</span><span class="sxs-lookup"><span data-stu-id="a0440-234">**Name**</span></span>
   - <span data-ttu-id="a0440-235">**Status**</span><span class="sxs-lookup"><span data-stu-id="a0440-235">**Status**</span></span>
   - <span data-ttu-id="a0440-236">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="a0440-236">**Priority**</span></span>
   - <span data-ttu-id="a0440-237">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a0440-237">**Type**</span></span>

3. <span data-ttu-id="a0440-238">Wenn Sie eine Richtlinie für ausgehende Spamnachrichten auswählen, indem Sie auf den Namen klicken, werden die Richtlinieneinstellungen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0440-238">When you select an outbound spam policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="a0440-239">Verwenden des Sicherheitscenters zum Ändern ausgehender Spamrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a0440-239">Use the security center to modify outbound spam policies</span></span>

1. <span data-ttu-id="a0440-240">Wechseln Sie im Security Center zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** \> **Richtlinien**\> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="a0440-240">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a0440-241">Wählen Sie auf der Seite **"Antispamrichtlinien"** eine ausgehende Spamrichtlinie aus der Liste aus, indem Sie auf den Namen klicken:</span><span class="sxs-lookup"><span data-stu-id="a0440-241">On the **Anti-spam policies** page, select an outbound spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="a0440-242">Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, bei der der Wert in der Spalte **"Typ"** **eine benutzerdefinierte Richtlinie für ausgehende Spamnachrichten** ist.</span><span class="sxs-lookup"><span data-stu-id="a0440-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>
   - <span data-ttu-id="a0440-243">Die Standardrichtlinie mit dem Namen **Antispam ausgehende Richtlinie (Standard).**</span><span class="sxs-lookup"><span data-stu-id="a0440-243">The default policy named **Anti-spam outbound policy (Default)**.</span></span>

3. <span data-ttu-id="a0440-244">Wählen Sie im angezeigten Flyout für die Richtliniendetails in jedem Abschnitt die Option **Bearbeiten** aus, um die Einstellungen innerhalb des Abschnitts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a0440-244">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="a0440-245">Weitere Informationen zu den Einstellungen finden Sie im abschnitt ["Verwenden des Sicherheitscenters zum Erstellen ausgehender Spamrichtlinien"](#use-the-security-center-to-create-outbound-spam-policies) in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="a0440-245">For more information about the settings, see the previous [Use the security center to create outbound spam policies](#use-the-security-center-to-create-outbound-spam-policies) section in this article.</span></span>

   <span data-ttu-id="a0440-246">Für die standardmäßige richtlinie für ausgehende Spamnachrichten ist der Abschnitt **"Angewendet auf"** nicht verfügbar (die Richtlinie gilt für alle), und Sie können die Richtlinie nicht umbenennen.</span><span class="sxs-lookup"><span data-stu-id="a0440-246">For the default outbound spam policy, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="a0440-247">Informationen zum Aktivieren oder Deaktivieren einer Richtlinie, zum Festlegen der Prioritätsreihenfolge der Richtlinien oder zum Konfigurieren der Quarantänebenachrichtigungen für Endbenutzer finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="a0440-247">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-custom-outbound-spam-policies"></a><span data-ttu-id="a0440-248">Aktivieren oder Deaktivieren von benutzerdefinierten ausgehenden Spamrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a0440-248">Enable or disable custom outbound spam policies</span></span>

<span data-ttu-id="a0440-249">Sie können die standardmäßige richtlinie für ausgehende Spamnachrichten nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a0440-249">You can't disable the default outbound spam policy.</span></span>

1. <span data-ttu-id="a0440-250">Wechseln Sie im Security Center zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** \> **Richtlinien**\> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="a0440-250">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a0440-251">Wählen Sie auf der Seite **"Antispamrichtlinien"** eine Richtlinie mit dem **Typwert** **"Benutzerdefinierte ausgehende Spamrichtlinie"** aus der Liste aus, indem Sie auf den Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="a0440-251">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom  outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="a0440-252">Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie einen der folgenden Werte sehen:</span><span class="sxs-lookup"><span data-stu-id="a0440-252">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="a0440-253">**Richtlinie deaktiviert**: Um die Richtlinie zu aktivieren, klicken Sie auf ![Symbol „Aktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="a0440-253">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="a0440-254">**Richtlinie aktiviert**: Um die Richtlinie zu deaktivieren, klicken Sie auf ![Symbol „Deaktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="a0440-254">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="a0440-255">Klicken Sie im angezeigten Bestätigungsdialog auf **Aktivieren** oder **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="a0440-255">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="a0440-256">Klicken Sie im Flyout der Richtliniendetails auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="a0440-256">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="a0440-257">Zurück auf der Richtlinien-Hauptseite wird der Wert **Status** der Richtlinie **Aktiviert** oder **Deaktiviert** sein.</span><span class="sxs-lookup"><span data-stu-id="a0440-257">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="a0440-258">Festlegen der Priorität von benutzerdefinierten ausgehenden Spamrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a0440-258">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="a0440-259">Standardmäßig erhalten ausgehende Spamrichtlinien eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="a0440-259">By default, outbound spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="a0440-260">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="a0440-260">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="a0440-261">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a0440-261">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="a0440-262">Um die Priorität einer Richtlinie zu ändern, klicken Sie in den Eigenschaften einer Richtlinie auf **Priorität erhöhen** oder **Priorität verringern** (Sie können den Zahlenwert der **Priorität** im Security Center nicht direkt modifizieren).</span><span class="sxs-lookup"><span data-stu-id="a0440-262">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="a0440-263">Die Priorität einer Richtlinie zu verändern macht nur Sinn, wenn Sie mehrere Richtlinien haben.</span><span class="sxs-lookup"><span data-stu-id="a0440-263">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="a0440-264">**Anmerkungen**:</span><span class="sxs-lookup"><span data-stu-id="a0440-264">**Notes**:</span></span>

- <span data-ttu-id="a0440-265">Im Security Center können Sie die Priorität der Richtlinie für ausgehende Spamnachrichten erst ändern, nachdem Sie sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a0440-265">In the security center, you can only change the priority of the outbound spam policy after you create it.</span></span> <span data-ttu-id="a0440-266">In PowerShell können Sie die standardmäßige Priorität bereits beim Erstellen der Spamfilterregel überschreiben (was sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="a0440-266">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="a0440-267">Ausgehende Spamrichtlinien werden in der Reihenfolge verarbeitet, in der sie angezeigt werden (die erste Richtlinie hat den **Prioritätswert** 0).</span><span class="sxs-lookup"><span data-stu-id="a0440-267">Outbound spam policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="a0440-268">Die standardmäßige richtlinie für ausgehende Spamnachrichten hat den Prioritätswert **Niedrigste**, und Sie können sie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="a0440-268">The default outbound spam policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="a0440-269">Wechseln Sie im Security Center zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** \> **Richtlinien**\> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="a0440-269">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a0440-270">Wählen Sie auf der Seite **"Antispamrichtlinien"** eine Richtlinie mit dem **Typwert** **"Benutzerdefinierte ausgehende Spamrichtlinie"** aus der Liste aus, indem Sie auf den Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="a0440-270">On the **Anti-spam policies** page, select a select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="a0440-271">Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie **Priorität erhöhen** oder **Priorität verringern** sehen, abhängig vom aktuellen Prioritätswert und der Anzahl der benutzerdefinierten Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="a0440-271">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="a0440-272">Für die Richtlinie für ausgehende Spamnachrichten mit dem **Prioritätswert** **0** ist nur die Option **"Priorität verringern"** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a0440-272">The outbound spam policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="a0440-273">Für die Richtlinie für ausgehende Spamnachrichten mit dem niedrigsten **Prioritätswert** (z. B. **3)** ist nur die Option **"Priorität erhöhen"** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a0440-273">The outbound spam policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="a0440-274">Wenn Sie über drei oder mehr ausgehende Spamrichtlinien verfügen, stehen richtlinien zwischen den Werten mit der höchsten und der niedrigsten Priorität sowohl die Optionen **"Priorität erhöhen"** als auch **"Verringern"** zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a0440-274">If you have three or more outbound spam policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="a0440-275">Klicken Sie auf ![Symbol „Priorität erhöhen“](../../media/m365-cc-sc-increase-icon.png) **Priorität erhöhen** oder ![Symbol „Priorität verringern“](../../media/m365-cc-sc-decrease-icon.png) **Priorität verringern**, um den **Prioritätswert** zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a0440-275">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="a0440-276">Wenn Sie den Vorgang abgeschlossen haben, klicken Sie im Flyout der Richtliniendetails auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="a0440-276">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-security-center-to-remove-custom-outbound-spam-policies"></a><span data-ttu-id="a0440-277">Verwenden des Sicherheitscenters zum Entfernen benutzerdefinierter ausgehender Spamrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a0440-277">Use the security center to remove custom outbound spam policies</span></span>

<span data-ttu-id="a0440-278">Wenn Sie das Sicherheitscenter verwenden, um eine benutzerdefinierte Richtlinie für ausgehende Spamnachrichten zu entfernen, werden die Spamfilterregel und die entsprechende Spamfilterrichtlinie gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a0440-278">When you use the security center to remove a custom outbound spam policy, the spam filter rule and the corresponding spam filter policy are both deleted.</span></span> <span data-ttu-id="a0440-279">Sie können die standardmäßige Richtlinie für ausgehende Spamnachrichten nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="a0440-279">You can't remove the default outbound spam policy.</span></span>

1. <span data-ttu-id="a0440-280">Wechseln Sie im Security Center zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** \> **Richtlinien**\> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="a0440-280">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a0440-281">Wählen Sie auf der Seite **"Antispamrichtlinien"** eine Richtlinie mit dem **Typwert** **"Benutzerdefinierte ausgehende Spamrichtlinie"** aus der Liste aus, indem Sie auf den Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="a0440-281">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span> <span data-ttu-id="a0440-282">Ganz oben auf dem angezeigten Flyout der Richtliniendetails klicken Sie auf ![Symbol „Weiter Aktionen“](../../media/m365-cc-sc-more-actions-icon.png) **Weitere Aktionen** \> ![Symbol „Richtlinie löschen“](../../media/m365-cc-sc-delete-icon.png) **Richtlinie löschen**.</span><span class="sxs-lookup"><span data-stu-id="a0440-282">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="a0440-283&quot;>Klicken Sie im angezeigten Bestätigungsdialog auf **Ja**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-283&quot;>In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name=&quot;use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies&quot;></a><span data-ttu-id=&quot;a0440-284&quot;>Verwenden Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren ausgehender Spamrichtlinien</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-284&quot;>Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id=&quot;a0440-285&quot;>Wie zuvor beschrieben besteht eine Richtlinie für ausgehende Spamnachrichten aus einer Richtlinie für ausgehende Spamfilter und einer ausgehenden Spamfilterregel.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-285&quot;>As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id=&quot;a0440-286&quot;>In Exchange Online PowerShell oder der eigenständigen EOP PowerShell ist der Unterschied zwischen ausgehenden Spamfilterrichtlinien und ausgehenden Spamfilterregeln offensichtlich.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-286&quot;>In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id=&quot;a0440-287&quot;>Sie verwalten ausgehende Spamfilterrichtlinien mithilfe der Cmdlets **\* &quot;-HostedOutboundSpamFilterPolicy&quot;** und ausgehende Spamfilterregeln mithilfe der Cmdlets **\* &quot;-HostedOutboundSpamFilterRule&quot;.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-287&quot;>You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id=&quot;a0440-288&quot;>In PowerShell erstellen Sie zuerst die Richtlinie für den ausgehenden Spamfilter und dann die Ausgehende Spamfilterregel, die die Richtlinie identifiziert, für die die Regel gilt.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-288&quot;>In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id=&quot;a0440-289&quot;>In PowerShell ändern Sie die Einstellungen in der Richtlinie für den ausgehenden Spamfilter und die Ausgehende Spamfilterregel separat.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-289&quot;>In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id=&quot;a0440-290&quot;>Wenn Sie eine Richtlinie für ausgehende Spamfilter aus PowerShell entfernen, wird die entsprechende ausgehende Spamfilterregel nicht automatisch entfernt und umgekehrt.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-290&quot;>When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name=&quot;use-powershell-to-create-outbound-spam-policies&quot;></a><span data-ttu-id=&quot;a0440-291&quot;>Verwenden von PowerShell zum Erstellen ausgehender Spamrichtlinien</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-291&quot;>Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id=&quot;a0440-292&quot;>Das Erstellen einer Richtlinie für ausgehende Spamnachrichten in PowerShell besteht aus zwei Schritten:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-292&quot;>Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id=&quot;a0440-293&quot;>Erstellen Sie die Richtlinie für den ausgehenden Spamfilter.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-293&quot;>Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id=&quot;a0440-294&quot;>Erstellen Sie die Filterregel für ausgehende Spamnachrichten, die die Richtlinie für den ausgehenden Spamfilter angibt, auf die die Regel angewendet wird.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-294&quot;>Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

   <span data-ttu-id=&quot;a0440-295&quot;>**Hinweise**:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-295&quot;>**Notes**:</span></span>

   - <span data-ttu-id=&quot;a0440-296&quot;>Sie können eine neue ausgehende Spamfilterregel erstellen und ihr eine vorhandene, nicht zugeordnete Richtlinie für ausgehende Spamfilter zuweisen.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-296&quot;>You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id=&quot;a0440-297&quot;>Eine Ausgehende Spamfilterregel kann nicht mehr als einer Richtlinie für ausgehende Spamfilter zugeordnet werden.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-297&quot;>An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>
   - <span data-ttu-id=&quot;a0440-298&quot;>Sie können die folgenden Einstellungen für neue Richtlinien für ausgehende Spamfilter in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Security Center verfügbar sind:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a0440-298&quot;>You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>
     - <span data-ttu-id=&quot;a0440-299&quot;>Erstellen Sie die neue Richtlinie als deaktiviert _(aktiviert_ `$false` für das Cmdlet **&quot;New-HostedOutboundSpamFilterRule").**</span><span class="sxs-lookup"><span data-stu-id="a0440-299">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
     - <span data-ttu-id="a0440-300">Legen Sie die Priorität der Richtlinie während der Erstellung _(Priorität)_ _\<Number\>_ für das Cmdlet **"New-HostedOutboundSpamFilterRule"** fest.</span><span class="sxs-lookup"><span data-stu-id="a0440-300">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
   - <span data-ttu-id="a0440-301">Eine neue richtlinie für ausgehende Spamfilter, die Sie in PowerShell erstellen, ist erst im Security Center sichtbar, wenn Sie die Richtlinie einer ausgehenden Spamfilterregel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a0440-301">A new outbound spam filter policy that you create in PowerShell isn't visible in the security center until you assign the policy to an outbound spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="a0440-302">Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für ausgehende Spamfilter</span><span class="sxs-lookup"><span data-stu-id="a0440-302">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="a0440-303">Verwenden Sie diese Syntax, um eine Richtlinie für ausgehende Spamfilter zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a0440-303">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="a0440-304">In diesem Beispiel wird eine neue Richtlinie für ausgehende Spamfilter mit dem Namen Contoso Executives mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="a0440-304">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="a0440-305">Die Empfängerratengrenzen sind auf kleinere Werte beschränkt, die standardmäßig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0440-305">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="a0440-306">Weitere Informationen finden Sie unter [Senden von Grenzwerten für Microsoft 365 Optionen.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="a0440-306">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="a0440-307">Nachdem einer der Grenzwerte erreicht wurde, wird der Benutzer am Senden von Nachrichten gehindert.</span><span class="sxs-lookup"><span data-stu-id="a0440-307">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="a0440-308">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="a0440-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="a0440-309">Schritt 2: Verwenden von PowerShell zum Erstellen einer ausgehenden Spamfilterregel</span><span class="sxs-lookup"><span data-stu-id="a0440-309">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="a0440-310">Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilterregel zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a0440-310">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="a0440-311">In diesem Beispiel wird eine neue ausgehende Spamfilterregel namens Contoso Executives mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="a0440-311">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="a0440-312">Die Richtlinie für ausgehende Spamfilter mit dem Namen Contoso Executives ist der Regel zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a0440-312">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="a0440-313">Die Regel gilt für Mitglieder der Gruppe mit dem Namen „Contoso Executive Group“.</span><span class="sxs-lookup"><span data-stu-id="a0440-313">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="a0440-314">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="a0440-314">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="a0440-315">Verwenden von PowerShell zum Anzeigen ausgehender Spamfilterrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a0440-315">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="a0440-316">Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller richtlinien für ausgehende Spamfilter zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="a0440-316">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="a0440-317">Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Richtlinie für ausgehende Spamfilter zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="a0440-317">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="a0440-318">In diesem Beispiel werden alle Eigenschaftswerte für die Richtlinie für ausgehende Spamfilter mit dem Namen "Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a0440-318">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="a0440-319">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-HostedOutboundSpamFilterPolicy".](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="a0440-319">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="a0440-320">Verwenden von PowerShell zum Anzeigen ausgehender Spamfilterregeln</span><span class="sxs-lookup"><span data-stu-id="a0440-320">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="a0440-321">Verwenden Sie die folgende Syntax, um vorhandene Regeln für ausgehende Spamfilter anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="a0440-321">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="a0440-322">Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller ausgehenden Spamfilterregeln zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="a0440-322">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="a0440-323">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="a0440-323">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="a0440-324">Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten ausgehenden Spamfilterregel zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="a0440-324">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="a0440-325">In diesem Beispiel werden alle Eigenschaftswerte für die Filterregel für ausgehende Spamnachrichten mit dem Namen "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a0440-325">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="a0440-326">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-HostedOutboundSpamFilterRule".](/powershell/module/exchange/get-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="a0440-326">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="a0440-327">Verwenden von PowerShell zum Ändern ausgehender Spamfilterrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a0440-327">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="a0440-328">Die gleichen Einstellungen sind verfügbar, wenn Sie eine Schadsoftwarefilterrichtlinie in PowerShell ändern, wie beim Erstellen der Richtlinie, wie in [Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für ausgehende Spamfilter](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a0440-328">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="a0440-329">Sie können eine Richtlinie für ausgehende Spamfilter nicht umbenennen (das Cmdlet **"Set-HostedOutboundSpamFilterPolicy"** hat keinen _Name-Parameter)._</span><span class="sxs-lookup"><span data-stu-id="a0440-329">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="a0440-330">Wenn Sie eine Richtlinie für ausgehende Spamnachrichten im Security Center umbenennen, benennen Sie nur die _Filterregel_ für ausgehende Spamnachrichten um.</span><span class="sxs-lookup"><span data-stu-id="a0440-330">When you rename an outbound spam policy in the security center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="a0440-331">Verwenden Sie die folgende Syntax, um eine Richtlinie für ausgehende Spamfilter zu ändern:</span><span class="sxs-lookup"><span data-stu-id="a0440-331">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="a0440-332">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-HostedOutboundSpamFilterPolicy".](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="a0440-332">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="a0440-333">Verwenden von PowerShell zum Ändern ausgehender Spamfilterregeln</span><span class="sxs-lookup"><span data-stu-id="a0440-333">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="a0440-334">Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine ausgehende Spamfilterregel in PowerShell ändern, ist der _Parameter "Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="a0440-334">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="a0440-335">Informationen zum Aktivieren oder Deaktivieren vorhandener ausgehender Spamfilterregeln finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a0440-335">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="a0440-336">Andernfalls sind keine zusätzlichen Einstellungen verfügbar, wenn Sie eine ausgehende Spamfilterregel in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="a0440-336">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="a0440-337">Die gleichen Einstellungen sind verfügbar, wenn Sie eine Regel erstellen, wie im [Abschnitt "Schritt 2: Verwenden von PowerShell zum Erstellen einer ausgehenden Spamfilterregel"](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a0440-337">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="a0440-338">Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilterregel zu ändern:</span><span class="sxs-lookup"><span data-stu-id="a0440-338">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="a0440-339">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-HostedOutboundSpamFilterRule".](/powershell/module/exchange/set-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="a0440-339">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="a0440-340">Verwenden von PowerShell zum Aktivieren oder Deaktivieren ausgehender Spamfilterregeln</span><span class="sxs-lookup"><span data-stu-id="a0440-340">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="a0440-341">Das Aktivieren oder Deaktivieren einer ausgehenden Spamfilterregel in PowerShell aktiviert oder deaktiviert die gesamte Richtlinie für ausgehende Spamnachrichten (die Filterregel für ausgehende Spamnachrichten und die zugewiesene Richtlinie für ausgehende Spamfilter).</span><span class="sxs-lookup"><span data-stu-id="a0440-341">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="a0440-342">Sie können die standardmäßige Richtlinie für ausgehende Spamnachrichten nicht aktivieren oder deaktivieren (sie wird immer auf alle Empfänger angewendet).</span><span class="sxs-lookup"><span data-stu-id="a0440-342">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="a0440-343">Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilterregel in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="a0440-343">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="a0440-344">In diesem Beispiel wird die ausgehende Spamfilterregel namens "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a0440-344">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="a0440-345">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a0440-345">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="a0440-346">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Enable-HostedOutboundSpamFilterRule"](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) und ["Disable-HostedOutboundSpamFilterRule".](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="a0440-346">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="a0440-347">Verwenden von PowerShell zum Festlegen der Priorität ausgehender Spamfilterregeln</span><span class="sxs-lookup"><span data-stu-id="a0440-347">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="a0440-p142">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="a0440-p142">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="a0440-353">Verwenden Sie die folgende Syntax, um die Priorität einer ausgehenden Spamfilterregel in PowerShell festzulegen:</span><span class="sxs-lookup"><span data-stu-id="a0440-353">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="a0440-p143">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="a0440-p143">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="a0440-356">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="a0440-356">**Notes**:</span></span>

- <span data-ttu-id="a0440-357">Um die Priorität einer neuen Regel beim Erstellen festzulegen, verwenden Sie stattdessen den Parameter _"Priority"_ im Cmdlet **"New-HostedOutboundSpamFilterRule".**</span><span class="sxs-lookup"><span data-stu-id="a0440-357">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
- <span data-ttu-id="a0440-358">Die ausgehende Standard-Spamfilterrichtlinie verfügt nicht über eine entsprechende Spamfilterregel, und sie hat immer den unveränderlichen Prioritätswert **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="a0440-358">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="a0440-359">Verwenden von PowerShell zum Entfernen ausgehender Spamfilterrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a0440-359">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="a0440-360">Wenn Sie PowerShell zum Entfernen einer Richtlinie für ausgehende Spamfilter verwenden, wird die entsprechende Ausgehende Spamfilterregel nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="a0440-360">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="a0440-361">Verwenden Sie die folgende Syntax, um eine richtlinie für ausgehende Spamfilter in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="a0440-361">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="a0440-362">In diesem Beispiel wird die Richtlinie für ausgehende Spamfilter mit dem Namen "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="a0440-362">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="a0440-363">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="a0440-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="a0440-364">Verwenden von PowerShell zum Entfernen ausgehender Spamfilterregeln</span><span class="sxs-lookup"><span data-stu-id="a0440-364">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="a0440-365">Wenn Sie PowerShell verwenden, um eine ausgehende Spamfilterregel zu entfernen, wird die entsprechende Richtlinie für den ausgehenden Spamfilter nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="a0440-365">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="a0440-366">Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilterregel in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="a0440-366">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="a0440-367">In diesem Beispiel wird die ausgehende Spamfilterregel namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="a0440-367">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="a0440-368">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="a0440-368">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="a0440-369">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0440-369">For more information</span></span>

[<span data-ttu-id="a0440-370">Entfernen von blockierten Benutzern aus dem Portal „Eingeschränkte Benutzer“</span><span class="sxs-lookup"><span data-stu-id="a0440-370">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="a0440-371">Pool für besonders riskante Zustellungen für ausgehende Nachrichten</span><span class="sxs-lookup"><span data-stu-id="a0440-371">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="a0440-372">Häufig gestellte Fragen zum Antispamschutz</span><span class="sxs-lookup"><span data-stu-id="a0440-372">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.yml)

[<span data-ttu-id="a0440-373">Bericht über automatisch weitergeleitete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="a0440-373">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
