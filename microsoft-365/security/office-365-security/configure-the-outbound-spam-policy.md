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
description: Administratoren erfahren, wie Sie ausgehende Spamrichtlinien in EOP Exchange Online Protection anzeigen, erstellen, ändern und löschen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ead8aa75c0218dd2c4cad96e50e37ed3ddc12815
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583193"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="91932-103">Konfigurieren der Filterung ausgehender Spamnachrichten in EOP</span><span class="sxs-lookup"><span data-stu-id="91932-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="91932-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="91932-104">**Applies to**</span></span>
- [<span data-ttu-id="91932-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="91932-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="91932-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="91932-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="91932-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91932-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="91932-108">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden ausgehende E-Mail-Nachrichten, die über EOP gesendet werden, automatisch auf Spam und ungewöhnliche Sendeaktivitäten überprüft.</span><span class="sxs-lookup"><span data-stu-id="91932-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="91932-109">Ausgehender Spam von einem Benutzer in Ihrer Organisation weist in der Regel auf ein gefährdetes Konto hin.</span><span class="sxs-lookup"><span data-stu-id="91932-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="91932-110">Verdächtige ausgehende Nachrichten werden als Spam gekennzeichnet (unabhängig von der Spamzuvertrauungsstufe oder SCL) und durch den Pool mit hohem Risiko für die Zustellung geroutet, um die Reputation des Diensts zu schützen (d. h., Microsoft 365 [Quell-E-Mail-Server](high-risk-delivery-pool-for-outbound-messages.md) von IP-Sperrlisten abzuschalten).</span><span class="sxs-lookup"><span data-stu-id="91932-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="91932-111">Administratoren werden automatisch über Benachrichtigungsrichtlinien über verdächtige ausgehende E-Mail-Aktivitäten und [blockierte Benutzer benachrichtigt.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="91932-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="91932-112">EOP verwendet ausgehende Spamrichtlinien als Teil der allgemeinen Verteidigung Ihrer Organisation gegen Spam.</span><span class="sxs-lookup"><span data-stu-id="91932-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="91932-113">Weitere Informationen finden Sie unter [Antispamschutz](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="91932-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="91932-114">Administratoren können die standardmäßige ausgehende Spamrichtlinie anzeigen, bearbeiten und konfigurieren (aber nicht löschen).</span><span class="sxs-lookup"><span data-stu-id="91932-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="91932-115">Für eine höhere Granularität können Sie auch benutzerdefinierte ausgehende Spamrichtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="91932-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="91932-116">Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="91932-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="91932-117">Sie können ausgehende Spamrichtlinien im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="91932-117">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="91932-118">Die grundlegenden Elemente einer ausgehenden Spamrichtlinie in EOP sind:</span><span class="sxs-lookup"><span data-stu-id="91932-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="91932-119">**Die Richtlinie für ausgehende Spamfilter**: Gibt die Aktionen für die Filterung ausgehender Spamfilter und die Benachrichtigungsoptionen an.</span><span class="sxs-lookup"><span data-stu-id="91932-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="91932-120">**Die Filterregel für ausgehende** Spamnachrichten : Gibt die Priorität und empfängerfilter (auf wen die Richtlinie angewendet wird) für eine Richtlinie für ausgehende Spamfilter an.</span><span class="sxs-lookup"><span data-stu-id="91932-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="91932-121">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie ausgehende Spamrichtlinien im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="91932-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="91932-122">Wenn Sie eine Richtlinie erstellen, erstellen Sie tatsächlich eine ausgehende Spamfilterregel und die zugeordnete Richtlinie für ausgehende Spamfilter gleichzeitig mit demselben Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="91932-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="91932-123">Wenn Sie eine Richtlinie ändern, ändern Einstellungen im Zusammenhang mit name, priority, enabled or disabled und empfängerfiltern die Filterregel für ausgehende Spamnachrichten.</span><span class="sxs-lookup"><span data-stu-id="91932-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="91932-124">Alle anderen Einstellungen ändern die zugeordnete Richtlinie für ausgehende Spamfilter.</span><span class="sxs-lookup"><span data-stu-id="91932-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="91932-125">Wenn Sie eine Richtlinie entfernen, werden die Filterregel für ausgehende Spamnachrichten und die zugehörige Richtlinie für ausgehende Spamfilter entfernt.</span><span class="sxs-lookup"><span data-stu-id="91932-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="91932-126">In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt.</span><span class="sxs-lookup"><span data-stu-id="91932-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="91932-127">Weitere Informationen finden Sie im Abschnitt Verwenden von [Exchange Online PowerShell oder eigenständiger EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) zum Konfigurieren ausgehender Spamrichtlinien weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="91932-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="91932-128">Jede Organisation verfügt über eine integrierte ausgehende Spamrichtlinie mit dem Namen Default, die über die folgenden Eigenschaften verfügt:</span><span class="sxs-lookup"><span data-stu-id="91932-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="91932-129">Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, auch wenn der Richtlinie keine ausgehende Spamfilterregel (Empfängerfilter) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="91932-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="91932-130">Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet).</span><span class="sxs-lookup"><span data-stu-id="91932-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="91932-131">Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer Vorrang vor der Richtlinie „Standard“.</span><span class="sxs-lookup"><span data-stu-id="91932-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="91932-132">Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="91932-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="91932-133">Um die Effektivität der Filterung ausgehender Spamnachrichten zu erhöhen, können Sie benutzerdefinierte ausgehende Spamrichtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="91932-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="91932-134">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="91932-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="91932-135">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="91932-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="91932-136">Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="91932-136">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="91932-137">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="91932-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="91932-138">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="91932-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="91932-139">Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:</span><span class="sxs-lookup"><span data-stu-id="91932-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="91932-140">Zum Hinzufügen, Ändern und Löschen ausgehender Spamrichtlinien müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung** oder **Sicherheitsadministrator** sein.</span><span class="sxs-lookup"><span data-stu-id="91932-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="91932-141">Für den schreibgeschützten Zugriff auf ausgehende Spamrichtlinien müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.</span><span class="sxs-lookup"><span data-stu-id="91932-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="91932-142">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="91932-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > - <span data-ttu-id="91932-143">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="91932-143">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="91932-144">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="91932-144">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > 
  > - <span data-ttu-id="91932-145">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="91932-145">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="91932-146">Die empfohlenen Einstellungen für ausgehende Spamrichtlinien finden Sie unter [EOP-Richtlinieneinstellungen für ausgehende Spamfilter](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="91932-146">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="91932-147">Die [](../../compliance/alert-policies.md) Standardbenachrichtigungsrichtlinien mit dem Namen E-Mail-Sendegrenzwert **überschritten,** verdächtige E-Mail-Sendemuster erkannt und Benutzer, der vom Senden von E-Mails eingeschränkt ist, sendet bereits E-Mail-Benachrichtigungen an Mitglieder der **Gruppe TenantAdmins** (**Globale** Administratoren ) über ungewöhnliche ausgehende E-Mail-Aktivitäten und blockierte Benutzer aufgrund ausgehender Spamnachrichten. </span><span class="sxs-lookup"><span data-stu-id="91932-147">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="91932-148">Weitere Informationen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="91932-148">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="91932-149">Es wird empfohlen, diese Warnungsrichtlinien anstelle der Benachrichtigungsoptionen in ausgehenden Spamrichtlinien zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="91932-149">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="91932-150">Verwenden des Security & Compliance Center zum Erstellen ausgehender Spamrichtlinien</span><span class="sxs-lookup"><span data-stu-id="91932-150">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="91932-151">Beim Erstellen einer benutzerdefinierten ausgehenden Spamrichtlinie im Security & Compliance Center werden die Spamfilterregel und die zugeordnete Spamfilterrichtlinie gleichzeitig mit demselben Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="91932-151">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="91932-152">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="91932-152">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="91932-153">Klicken Sie auf der Seite **Antispameinstellungen** auf **Ausgehende Richtlinie erstellen.**</span><span class="sxs-lookup"><span data-stu-id="91932-153">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="91932-154">Konfigurieren Sie **im geöffneten** Fly-Out der Richtlinie für ausgehende Spamfilter die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="91932-154">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="91932-155">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="91932-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="91932-156">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="91932-156">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="91932-157">(Optional) Erweitern Sie den **Abschnitt Benachrichtigungen,** um zusätzliche Benutzer zu konfigurieren, die Kopien und Benachrichtigungen über verdächtige ausgehende E-Mail-Nachrichten erhalten sollen:</span><span class="sxs-lookup"><span data-stu-id="91932-157">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="91932-158">**Senden einer Kopie verdächtiger** ausgehender E-Mail-Nachrichten an bestimmte Personen: Diese Einstellung fügt die angegebenen Benutzer als Bcc-Empfänger zu den verdächtigen ausgehenden Nachrichten hinzu.</span><span class="sxs-lookup"><span data-stu-id="91932-158">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="91932-159">Diese Einstellung funktioniert nur in der standardmäßigen ausgehenden Spamrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="91932-159">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="91932-160">Es funktioniert nicht in benutzerdefinierten ausgehenden Spamrichtlinien, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="91932-160">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="91932-161">So aktivieren Sie diese Einstellung:</span><span class="sxs-lookup"><span data-stu-id="91932-161">To enable this setting:</span></span>

     1. <span data-ttu-id="91932-162">Aktivieren Sie das Kontrollkästchen, um die Einstellung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="91932-162">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="91932-163">Klicken **Sie auf Personen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="91932-163">Click **Add people**.</span></span> <span data-ttu-id="91932-164">Im **Angezeigten Flyout** Empfänger hinzufügen oder entfernen:</span><span class="sxs-lookup"><span data-stu-id="91932-164">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="91932-165">Geben Sie die E-Mail-Adresse des Absenders ein.</span><span class="sxs-lookup"><span data-stu-id="91932-165">Enter the sender's email address.</span></span> <span data-ttu-id="91932-166">Sie können mehrere E-Mail-Adressen angeben, die durch Semikolons getrennt sind (;) oder ein Empfänger pro Zeile.</span><span class="sxs-lookup"><span data-stu-id="91932-166">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="91932-167">Click</span><span class="sxs-lookup"><span data-stu-id="91932-167">Click</span></span> ![Hinzufügen (Symbol)](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="91932-169">, um die Empfänger hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="91932-169">to add the recipients.</span></span>

        <span data-ttu-id="91932-170">Wiederholen Sie diese Schritte so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="91932-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="91932-171">Die hinzugefügten Empfänger werden im Abschnitt **Empfängerliste** des Flyouts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91932-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="91932-172">Klicken Sie zum Löschen eines Empfängers ![ auf Schaltfläche Entfernen ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="91932-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="91932-173">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="91932-173">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="91932-174">Deaktivieren Sie das Kontrollkästchen, um diese Einstellung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="91932-174">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="91932-175">**Benachrichtigen bestimmter Personen, wenn ein Absender aufgrund des Sendens von ausgehenden Spam blockiert wird:**</span><span class="sxs-lookup"><span data-stu-id="91932-175">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="91932-176">Diese Einstellung ist gerade dabei, ausgehende Spamrichtlinien als veraltet zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="91932-176">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="91932-177">Die [](../../compliance/alert-policies.md)  **Standardbenachrichtigungsrichtlinie**"Benutzer, der vom Senden von E-Mails eingeschränkt ist" sendet bereits E-Mail-Benachrichtigungen an Mitglieder der **Gruppe TenantAdmins** ( Globale Administratoren ), wenn Benutzer aufgrund der Überschreitung der Grenzwerte im Abschnitt Empfängerbeschränkungen blockiert **werden.**</span><span class="sxs-lookup"><span data-stu-id="91932-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="91932-178">**Es wird dringend empfohlen, die Warnungsrichtlinie** anstelle dieser Einstellung in der Richtlinie für ausgehende Spamnachrichten zu verwenden, um Administratoren und andere Benutzer zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="91932-178">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="91932-179">Anweisungen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="91932-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="91932-180">(Optional) Erweitern Sie den **Abschnitt Empfängerbeschränkungen,** um die Grenzwerte und Aktionen für verdächtige ausgehende E-Mail-Nachrichten zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="91932-180">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="91932-181">Diese Einstellungen gelten nur für cloudbasierte Postfächer.</span><span class="sxs-lookup"><span data-stu-id="91932-181">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="91932-182">**Maximale Anzahl von Empfängern pro Benutzer**</span><span class="sxs-lookup"><span data-stu-id="91932-182">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="91932-183">Ein gültiger Wert ist 0 bis 10000.</span><span class="sxs-lookup"><span data-stu-id="91932-183">A valid value is 0 to 10000.</span></span> <span data-ttu-id="91932-184">Der Standardwert ist 0, d. h. die Diensteinstellungen werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="91932-184">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="91932-185">Weitere Informationen finden Sie unter [Senden von Grenzwerten](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span><span class="sxs-lookup"><span data-stu-id="91932-185">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="91932-186">**Externe Stündlichgrenze:** Die maximale Anzahl externer Empfänger pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="91932-186">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="91932-187">**Interner Stundengrenzwert:** Die maximale Anzahl interner Empfänger pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="91932-187">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="91932-188">**Täglicher Grenzwert:** Die maximale Gesamtanzahl von Empfängern pro Tag.</span><span class="sxs-lookup"><span data-stu-id="91932-188">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="91932-189">**Aktion, wenn ein Benutzer die oben genannten Grenzwerte überschreitet:** Konfigurieren Sie die Aktion, die beim Überschreiten eines der **Empfängergrenzwerte** zu ergreifen ist.</span><span class="sxs-lookup"><span data-stu-id="91932-189">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="91932-190">Für alle Aktionen erhalten die  empfänger, die in der Richtlinie "Benutzer" das Senden von E-Mail-Benachrichtigungsrichtlinien eingeschränkt haben (und in der nun **redundanten** Benachrichtigung bestimmter Personen, wenn ein Absender aufgrund der Einstellung für ausgehende Spamnachrichten in der Richtlinie für ausgehende Spamnachrichten blockiert ist, E-Mail-Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="91932-190">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="91932-191">**Beschränken Sie den Benutzer am Senden von E-Mails** bis zum folgenden Tag : Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="91932-191">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="91932-192">E-Mail-Benachrichtigungen werden gesendet, und der Benutzer kann erst am folgenden Tag basierend auf der UTC-Zeit weitere Nachrichten senden.</span><span class="sxs-lookup"><span data-stu-id="91932-192">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="91932-193">Der Administrator kann diesen Block nicht überschreiben.</span><span class="sxs-lookup"><span data-stu-id="91932-193">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="91932-194">Die Aktivitätswarnung mit **dem Namen Benutzer,** der das Senden von E-Mails beschränkt hat, benachrichtigt Administratoren (per E-Mail und auf der Seite **Benachrichtigungen** anzeigen).</span><span class="sxs-lookup"><span data-stu-id="91932-194">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="91932-195">Alle empfänger, die in der **Richtlinie Bestimmte Personen** benachrichtigen angegeben werden, wenn ein Absender aufgrund des Sendens ausgehender Spameinstellungen in der Richtlinie blockiert wird, werden ebenfalls benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="91932-195">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="91932-196">Der Benutzer kann erst am folgenden Tag basierend auf der UTC-Zeit weitere Nachrichten senden.</span><span class="sxs-lookup"><span data-stu-id="91932-196">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="91932-197">Der Administrator kann diesen Block nicht überschreiben.</span><span class="sxs-lookup"><span data-stu-id="91932-197">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="91932-198">Benutzer vom Senden von E-Mails **einschränken:** E-Mail-Benachrichtigungen werden gesendet, der Benutzer wird dem **[Eingeschränkten Benutzer]-Portal <https://sip.protection.office.com/restrictedusers>** im  Security & Compliance Center hinzugefügt, und der Benutzer kann keine E-Mails senden, bis er vom Administrator aus dem Portal für eingeschränkte Benutzer entfernt wurde. Nachdem ein Administrator den Benutzer aus der Liste entfernt hat, wird der Benutzer für diesen Tag nicht mehr eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="91932-198">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="91932-199">Anweisungen finden Sie unter Entfernen eines Benutzers aus dem Portal für eingeschränkte Benutzer nach dem Senden [von Spam-E-Mails.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="91932-199">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="91932-200">**Keine Aktion, nur Warnung:** E-Mail-Benachrichtigungen werden gesendet.</span><span class="sxs-lookup"><span data-stu-id="91932-200">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="91932-201">(Optional) Erweitern Sie den Abschnitt Automatische **Weiterleitung,** um die automatische E-Mail-Weiterleitung durch Benutzer an externe Absender zu steuern.</span><span class="sxs-lookup"><span data-stu-id="91932-201">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="91932-202">Weitere Informationen finden Sie unter [Steuerung der automatischen externen E-Mail-Weiterleitung in Microsoft 365](external-email-forwarding.md).</span><span class="sxs-lookup"><span data-stu-id="91932-202">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="91932-203">Vor September 2020 sind diese Einstellungen verfügbar, werden jedoch nicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="91932-203">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="91932-204">Diese Einstellungen gelten nur für cloudbasierte Postfächer.</span><span class="sxs-lookup"><span data-stu-id="91932-204">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="91932-205">Wenn die automatische Weiterleitung deaktiviert ist, erhält der Empfänger einen Unzustellbarkeitsbericht (auch NDR oder Unzustellbarkeitsnachricht bezeichnet), wenn externe Absender E-Mails an ein Postfach senden, für das die Weiterleitung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="91932-205">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="91932-206">Wenn die Nachricht von einem  internen Absender gesendet wird und die Weiterleitungsmethode die Postfach-Weiterleitung [(auch](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) _als SMTP-Weiterleitung_ bezeichnet) ist, wird der interne Absender den NDR erhalten.</span><span class="sxs-lookup"><span data-stu-id="91932-206">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="91932-207">Der interne Absender bekommt keinen Unndr, wenn die Weiterleitung aufgrund einer Posteingangsregel erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="91932-207">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

   <span data-ttu-id="91932-208">Die verfügbaren Werte sind:</span><span class="sxs-lookup"><span data-stu-id="91932-208">The available values are:</span></span>

   - <span data-ttu-id="91932-209">Automatisch – Systemgesteuert: Ermöglicht die automatische externe **E-Mail-Weiterleitung** durch ausgehende Spamfilterung.</span><span class="sxs-lookup"><span data-stu-id="91932-209">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="91932-210">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="91932-210">This is the default value.</span></span>
   - <span data-ttu-id="91932-211">**On**: Die automatische externe E-Mail-Weiterleitung wird von der Richtlinie nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="91932-211">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
   - <span data-ttu-id="91932-212">**Off**: Die Richtlinie deaktiviert die automatische externe E-Mail-Weiterleitung.</span><span class="sxs-lookup"><span data-stu-id="91932-212">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="91932-213">(Erforderlich) Erweitern Sie den **Abschnitt Angewendet auf,** um die internen Absender zu identifizieren, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="91932-213">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="91932-214">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="91932-214">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="91932-215">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<sender1\>_ oder _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="91932-215">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="91932-216">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<sender1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="91932-216">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="91932-217">Um alle verfügbaren Bedingungen anzuzeigen, ist es am einfachsten, wenn Sie auf **Bedingung hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="91932-217">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="91932-218">Sie können auf ![Schaltfläche „Entfernen“](../../media/scc-remove-icon.png) klicken, um Bedingungen zu entfernen, die Sie nicht konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="91932-218">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="91932-219">**Die Absenderdomäne ist**: Gibt Absender in einer oder mehreren der konfigurierten akzeptierten Domänen in der Organisation an.</span><span class="sxs-lookup"><span data-stu-id="91932-219">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="91932-220">Klicken Sie in das Feld **Tag hinzufügen**, um eine Domäne anzuzeigen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="91932-220">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="91932-221">Klicken Sie erneut auf das Feld **Tag hinzufügen**, um weitere Domänen auszuwählen, falls mehrere Domänen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="91932-221">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="91932-222">**Absender ist**: Gibt einen oder mehrere Benutzer in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="91932-222">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="91932-223">Klicken Sie auf **Tag hinzufügen**, und beginnen Sie mit der Eingabe, um die Liste zu filtern.</span><span class="sxs-lookup"><span data-stu-id="91932-223">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="91932-224">Klicken Sie erneut auf **das Feld Tag hinzufügen,** um weitere Absender auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="91932-224">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="91932-225">**Sender ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="91932-225">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="91932-226">Klicken Sie auf **Tag hinzufügen**, und beginnen Sie mit der Eingabe, um die Liste zu filtern.</span><span class="sxs-lookup"><span data-stu-id="91932-226">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="91932-227">Klicken Sie erneut auf **das Feld Tag hinzufügen,** um weitere Absender auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="91932-227">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="91932-228">**Außer wenn**: Klicken Sie zum Angeben von Ausnahmen für die Regel dreimal auf **Bedingung hinzufügen**, um alle verfügbaren Ausnahmen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="91932-228">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="91932-229">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="91932-229">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="91932-230">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="91932-230">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="91932-231">Anzeigen ausgehender Spamrichtlinien mithilfe & Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="91932-231">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="91932-232">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="91932-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="91932-233">Klicken Sie auf der Seite **Antispameinstellungen** auf ![ Symbol erweitern, ](../../media/scc-expand-icon.png) um eine richtlinie für ausgehende Spamnachrichten zu erweitern:</span><span class="sxs-lookup"><span data-stu-id="91932-233">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="91932-234">Die Standardrichtlinie mit dem **Namen Ausgehende Spamfilterrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="91932-234">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="91932-235">Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei der Wert in der **Spalte Typ** **benutzerdefinierte ausgehende Spamrichtlinie ist.**</span><span class="sxs-lookup"><span data-stu-id="91932-235">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="91932-236">Die Richtlinieneinstellungen werden in den angezeigten erweiterten Richtliniendetails angezeigt, oder Sie können auf **Richtlinie bearbeiten klicken.**</span><span class="sxs-lookup"><span data-stu-id="91932-236">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="91932-237">Verwenden des Security & Compliance Center zum Ändern ausgehender Spamrichtlinien</span><span class="sxs-lookup"><span data-stu-id="91932-237">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="91932-238">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="91932-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="91932-239">Klicken Sie auf der Seite **Antispameinstellungen** auf ![ Symbol erweitern, ](../../media/scc-expand-icon.png) um eine richtlinie für ausgehende Spamnachrichten zu erweitern:</span><span class="sxs-lookup"><span data-stu-id="91932-239">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="91932-240">Die Standardrichtlinie mit dem **Namen Ausgehende Spamfilterrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="91932-240">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="91932-241">Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei der Wert in der **Spalte Typ** **benutzerdefinierte ausgehende Spamrichtlinie ist.**</span><span class="sxs-lookup"><span data-stu-id="91932-241">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="91932-242">Klicken Sie auf **Richtlinie bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="91932-242">Click **Edit policy**.</span></span>

<span data-ttu-id="91932-243">Für benutzerdefinierte ausgehende Spamrichtlinien sind die verfügbaren Einstellungen im angezeigten Flyout mit den im Abschnitt Verwenden des Security & Compliance Center zum Erstellen ausgehender [Spamrichtlinien](#use-the-security--compliance-center-to-create-outbound-spam-policies) beschriebenen Einstellungen identisch.</span><span class="sxs-lookup"><span data-stu-id="91932-243">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="91932-244">Für die standardmäßige ausgehende Spamrichtlinie  **mit** dem Namen Ausgehende Spamfilterrichtlinie ist der Abschnitt Angewendet auf nicht verfügbar (die Richtlinie gilt für alle), und Sie können die Richtlinie nicht umbenennen.</span><span class="sxs-lookup"><span data-stu-id="91932-244">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="91932-245">Informationen zum Aktivieren oder Deaktivieren einer Richtlinie, zum Festlegen der Prioritätsreihenfolge der Richtlinien oder zum Konfigurieren der Quarantänebenachrichtigungen für Endbenutzer finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="91932-245">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="91932-246">Aktivieren oder Deaktivieren ausgehender Spamrichtlinien</span><span class="sxs-lookup"><span data-stu-id="91932-246">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="91932-247">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="91932-247">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="91932-248">Klicken Sie auf der Seite **Antispameinstellungen** auf Symbol erweitern, um eine von Ihnen erstellte benutzerdefinierte Richtlinie zu erweitern (der Wert in der Spalte Typ ![ ist ](../../media/scc-expand-icon.png) **Benutzerdefinierte ausgehende Spamrichtlinie**). </span><span class="sxs-lookup"><span data-stu-id="91932-248">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="91932-249">Achten Sie in den angezeigten erweiterten Richtliniendetails auf den Wert in der Spalte **Ein**.</span><span class="sxs-lookup"><span data-stu-id="91932-249">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="91932-250">Schieben Sie die Umschaltfläche nach links, um die Richtlinie zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="91932-250">Move the toggle to the left to disable the policy:</span></span> ![Umschaltfläche aus](../../media/scc-toggle-off.png)

   <span data-ttu-id="91932-252">Schieben Sie die Umschaltfläche nach rechts, um die Richtlinie zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="91932-252">Move the toggle to the right to enable the policy:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)

<span data-ttu-id="91932-254">Sie können die standardmäßige richtlinie für ausgehende Spamnachrichten nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="91932-254">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="91932-255">Festlegen der Priorität von benutzerdefinierten ausgehenden Spamrichtlinien</span><span class="sxs-lookup"><span data-stu-id="91932-255">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="91932-256">Standardmäßig erhalten ausgehende Spamrichtlinien eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="91932-256">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="91932-257">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="91932-257">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="91932-258">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="91932-258">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="91932-259">Benutzerdefinierte ausgehende Spamrichtlinien werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0).</span><span class="sxs-lookup"><span data-stu-id="91932-259">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="91932-260">Die standardmäßige ausgehende Spamrichtlinie namens **Ausgehende Spamfilterrichtlinie** hat den Prioritätswert **Lowest**, und Sie können sie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="91932-260">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="91932-261">Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).</span><span class="sxs-lookup"><span data-stu-id="91932-261">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="91932-262">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="91932-262">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="91932-263">Suchen Sie auf der Seite **Antispameinstellungen** die Richtlinien, bei denen der Wert in der **Spalte Typ** benutzerdefinierte **ausgehende Spamrichtlinie ist.**</span><span class="sxs-lookup"><span data-stu-id="91932-263">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="91932-264">Beachten Sie die Werte in der Spalte **Priorität**:</span><span class="sxs-lookup"><span data-stu-id="91932-264">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="91932-265">Die benutzerdefinierte ausgehende Spamrichtlinie mit der höchsten Priorität hat den Wert ![ Nach-unten-Symbol ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="91932-265">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="91932-266">Die benutzerdefinierte ausgehende Spamrichtlinie mit der niedrigsten Priorität hat den Wert Nach-oben-Symbol n (z. B. ![ ](../../media/ITPro-EAC-UpArrowIcon.png)  ![ Nach-oben-Symbol ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="91932-266">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="91932-267">Wenn Sie über drei oder mehr benutzerdefinierte ausgehende Spamrichtlinien verfügen, haben die Richtlinien zwischen der höchsten und der niedrigsten Priorität werte Nach-oben-Symbol Nach-unten-Symbol n (z. B. Nach-oben-Symbol Nach-unten-Symbol ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="91932-267">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="91932-268">Klicken Sie auf</span><span class="sxs-lookup"><span data-stu-id="91932-268">Click</span></span> ![Pfeil-nach-oben-Symbol](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="91932-270">oder</span><span class="sxs-lookup"><span data-stu-id="91932-270">or</span></span> ![Pfeil-nach-unten-Symbol,](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="91932-272">, um die benutzerdefinierte ausgehende Spamrichtlinie in der Prioritätsliste nach oben oder unten zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="91932-272">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="91932-273">Verwenden des Security & Compliance Center zum Entfernen ausgehender Spamrichtlinien</span><span class="sxs-lookup"><span data-stu-id="91932-273">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="91932-274">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="91932-274">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="91932-275">Klicken Sie auf der Seite **Antispameinstellungen** auf Symbol erweitern, um die benutzerdefinierte Richtlinie zu erweitern, die Sie löschen möchten (die Spalte Typ ![ ist ](../../media/scc-expand-icon.png) **Benutzerdefinierte ausgehende Spamrichtlinie**). </span><span class="sxs-lookup"><span data-stu-id="91932-275">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="91932-276">Klicken Sie in den angezeigten erweiterten Richtliniendetails auf **Richtlinie löschen**.</span><span class="sxs-lookup"><span data-stu-id="91932-276">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="91932-277">Klicken Sie im angezeigten Dialogfeld mit der Warnung auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="91932-277">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="91932-278">Die Standardrichtlinie kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="91932-278">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="91932-279">Verwenden Exchange Online PowerShell oder eigenständiger EOP PowerShell zum Konfigurieren ausgehender Spamrichtlinien</span><span class="sxs-lookup"><span data-stu-id="91932-279">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="91932-280">Wie bereits beschrieben, besteht eine richtlinie für ausgehende Spamnachrichten aus einer Filterrichtlinie für ausgehende Spamnachrichten und einer Filterregel für ausgehende Spamnachrichten.</span><span class="sxs-lookup"><span data-stu-id="91932-280">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="91932-281">In Exchange Online PowerShell oder der eigenständigen EOP PowerShell ist der Unterschied zwischen ausgehenden Spamfilterrichtlinien und regeln für ausgehende Spamfilter offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="91932-281">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="91932-282">Sie verwalten ausgehende Spamfilterrichtlinien mithilfe der **\* -HostedOutboundSpamFilterPolicy-Cmdlets,** und Sie verwalten ausgehende Spamfilterregeln mithilfe der **\* Cmdlets -HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="91932-282">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="91932-283">In PowerShell erstellen Sie zuerst die Richtlinie für ausgehende Spamfilter und dann die Filterregel für ausgehende Spamnachrichten, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="91932-283">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="91932-284">In PowerShell ändern Sie die Einstellungen in der Richtlinie für ausgehende Spamfilter und die Filterregel für ausgehende Spamnachrichten separat.</span><span class="sxs-lookup"><span data-stu-id="91932-284">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="91932-285">Wenn Sie eine Richtlinie für ausgehende Spamfilter aus PowerShell entfernen, wird die entsprechende Filterregel für ausgehende Spamnachrichten nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="91932-285">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="91932-286">Erstellen ausgehender Spamrichtlinien mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="91932-286">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="91932-287">Das Erstellen einer ausgehenden Spamrichtlinie in PowerShell ist ein zweischrittiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="91932-287">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="91932-288">Erstellen Sie die Richtlinie für ausgehende Spamfilter.</span><span class="sxs-lookup"><span data-stu-id="91932-288">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="91932-289">Erstellen Sie die Filterregel für ausgehende Spamnachrichten, die die Richtlinie für ausgehende Spamfilter angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="91932-289">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

> [!NOTE]
> - <span data-ttu-id="91932-290">Sie können eine neue ausgehende Spamfilterregel erstellen und ihr eine vorhandene, nicht zugeordnete Richtlinie für ausgehende Spamfilter zuweisen.</span><span class="sxs-lookup"><span data-stu-id="91932-290">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="91932-291">Eine Filterregel für ausgehende Spamnachrichten kann nicht mehr als einer Filterrichtlinie für ausgehende Spamnachrichten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="91932-291">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>
> 
> - <span data-ttu-id="91932-292">Sie können die folgenden Einstellungen für neue ausgehende Spamfilterrichtlinien in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="91932-292">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="91932-293">Erstellen Sie die neue Richtlinie als deaktiviert (_Aktiviert_ `$false` im Cmdlet **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="91932-293">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
>   - <span data-ttu-id="91932-294">Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) für das Cmdlet **New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="91932-294">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="91932-295">Eine neue ausgehende Spamfilterrichtlinie, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Spamfilterregel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="91932-295">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="91932-296">Schritt 1: Erstellen einer Richtlinie für ausgehende Spamfilter mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="91932-296">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="91932-297">Verwenden Sie die folgende Syntax, um eine Richtlinie für ausgehende Spamfilter zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="91932-297">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="91932-298">In diesem Beispiel wird eine neue ausgehende Spamfilterrichtlinie namens Contoso Executives mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="91932-298">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="91932-299">Die Empfängerrategrenzwerte sind auf kleinere Werte beschränkt, die standardmäßig festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="91932-299">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="91932-300">Weitere Informationen finden Sie unter [Senden von Grenzwerten Microsoft 365 Optionen](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="91932-300">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="91932-301">Nachdem eine der Grenzwerte erreicht wurde, wird der Benutzer am Senden von Nachrichten gehindert.</span><span class="sxs-lookup"><span data-stu-id="91932-301">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="91932-302">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="91932-302">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="91932-303">Schritt 2: Verwenden von PowerShell zum Erstellen einer Filterregel für ausgehende Spamnachrichten</span><span class="sxs-lookup"><span data-stu-id="91932-303">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="91932-304">Verwenden Sie die folgende Syntax, um eine filterregel für ausgehende Spamnachrichten zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="91932-304">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="91932-305">In diesem Beispiel wird eine neue ausgehende Spamfilterregel namens Contoso Executives mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="91932-305">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="91932-306">Die Richtlinie für ausgehende Spamfilter namens Contoso Executives ist der Regel zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="91932-306">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="91932-307">Die Regel gilt für Mitglieder der Gruppe mit dem Namen „Contoso Executive Group“.</span><span class="sxs-lookup"><span data-stu-id="91932-307">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="91932-308">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="91932-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="91932-309">Anzeigen ausgehender Spamfilterrichtlinien mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="91932-309">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="91932-310">Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller ausgehenden Spamfilterrichtlinien zurückzukehren:</span><span class="sxs-lookup"><span data-stu-id="91932-310">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="91932-311">Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Richtlinie für ausgehende Spamfilter zurückzukehren:</span><span class="sxs-lookup"><span data-stu-id="91932-311">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="91932-312">In diesem Beispiel werden alle Eigenschaftswerte für die ausgehende Spamfilterrichtlinie "Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="91932-312">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="91932-313">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="91932-313">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="91932-314">Anzeigen ausgehender Spamfilterregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="91932-314">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="91932-315">Verwenden Sie die folgende Syntax, um vorhandene Regeln für ausgehende Spamfilter anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="91932-315">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="91932-316">Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller ausgehenden Spamfilterregeln zurückzukehren:</span><span class="sxs-lookup"><span data-stu-id="91932-316">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="91932-317">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="91932-317">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="91932-318">Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Filterregel für ausgehende Spamnachrichten zurückzukehren:</span><span class="sxs-lookup"><span data-stu-id="91932-318">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="91932-319">In diesem Beispiel werden alle Eigenschaftswerte für die ausgehende Spamfilterregel namens Contoso Executives zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="91932-319">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="91932-320">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="91932-320">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="91932-321">Verwenden von PowerShell zum Ändern ausgehender Spamfilterrichtlinien</span><span class="sxs-lookup"><span data-stu-id="91932-321">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="91932-322">Dieselben Einstellungen sind verfügbar, wenn Sie eine Richtlinie für Schadsoftwarefilter in PowerShell ändern, wie beim Erstellen der Richtlinie, wie im Abschnitt Schritt 1: Verwenden von [PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) beschrieben, um eine Richtlinie für ausgehende Spamfilter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="91932-322">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="91932-323">Sie können eine Richtlinie für ausgehende Spamfilter nicht umbenennen (das **Cmdlet Set-HostedOutboundSpamFilterPolicy** hat keinen _Name-Parameter)._</span><span class="sxs-lookup"><span data-stu-id="91932-323">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="91932-324">Wenn Sie eine ausgehende Spamrichtlinie im Security & Compliance Center umbenennen, wird nur die Filterregel für ausgehende Spamnachrichten _umbenannt._</span><span class="sxs-lookup"><span data-stu-id="91932-324">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="91932-325">Verwenden Sie die folgende Syntax, um eine Richtlinie für ausgehende Spamfilter zu ändern:</span><span class="sxs-lookup"><span data-stu-id="91932-325">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="91932-326">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="91932-326">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="91932-327">Verwenden von PowerShell zum Ändern ausgehender Spamfilterregeln</span><span class="sxs-lookup"><span data-stu-id="91932-327">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="91932-328">Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine ausgehende Spamfilterregel in PowerShell ändern, ist der _Parameter Enabled,_ mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="91932-328">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="91932-329">Informationen zum Aktivieren oder Deaktivieren vorhandener ausgehender Spamfilterregeln finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="91932-329">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="91932-330">Andernfalls sind keine zusätzlichen Einstellungen verfügbar, wenn Sie eine Filterregel für ausgehende Spamnachrichten in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="91932-330">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="91932-331">Die gleichen Einstellungen sind verfügbar, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2:](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) Verwenden von PowerShell zum Erstellen einer ausgehenden Spamfilterregel weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91932-331">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="91932-332">Verwenden Sie die folgende Syntax, um eine filterregel für ausgehende Spamnachrichten zu ändern:</span><span class="sxs-lookup"><span data-stu-id="91932-332">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="91932-333">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="91932-333">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="91932-334">Aktivieren oder Deaktivieren ausgehender Spamfilterregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="91932-334">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="91932-335">Durch Aktivieren oder Deaktivieren einer ausgehenden Spamfilterregel in PowerShell wird die gesamte richtlinie für ausgehende Spamnachrichten (die Filterregel für ausgehende Spamnachrichten und die zugewiesene Richtlinie für ausgehende Spamfilter) aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="91932-335">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="91932-336">Die standardmäßige richtlinie für ausgehende Spamnachrichten kann nicht aktiviert oder deaktiviert werden (sie wird immer auf alle Empfänger angewendet).</span><span class="sxs-lookup"><span data-stu-id="91932-336">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="91932-337">Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilterregel in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="91932-337">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="91932-338">In diesem Beispiel wird die Filterregel für ausgehende Spamnachrichten mit dem Namen Marketing Department deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="91932-338">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="91932-339">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="91932-339">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="91932-340">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) und [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="91932-340">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="91932-341">Festlegen der Priorität ausgehender Spamfilterregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="91932-341">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="91932-342">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="91932-342">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="91932-343">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="91932-343">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="91932-344">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="91932-344">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="91932-345">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="91932-345">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="91932-346">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="91932-346">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="91932-347">Verwenden Sie die folgende Syntax, um die Priorität einer ausgehenden Spamfilterregel in PowerShell zu setzen:</span><span class="sxs-lookup"><span data-stu-id="91932-347">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="91932-p141">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="91932-p141">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="91932-350">Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den _Parameter Priority_ im Cmdlet **New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="91932-350">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="91932-351">Die ausgehende Standardmäßige Spamfilterrichtlinie verfügt nicht über eine entsprechende Spamfilterregel und hat immer den nicht veränderbaren Prioritätswert **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="91932-351">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="91932-352">Verwenden von PowerShell zum Entfernen ausgehender Spamfilterrichtlinien</span><span class="sxs-lookup"><span data-stu-id="91932-352">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="91932-353">Wenn Sie PowerShell verwenden, um eine Richtlinie für ausgehende Spamfilter zu entfernen, wird die entsprechende Filterregel für ausgehende Spamnachrichten nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="91932-353">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="91932-354">Verwenden Sie die folgende Syntax, um eine richtlinie für ausgehende Spamfilter in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="91932-354">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="91932-355">In diesem Beispiel wird die Richtlinie für ausgehende Spamfilter mit dem Namen Marketing Department entfernt.</span><span class="sxs-lookup"><span data-stu-id="91932-355">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="91932-356">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="91932-356">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="91932-357">Verwenden von PowerShell zum Entfernen ausgehender Spamfilterregeln</span><span class="sxs-lookup"><span data-stu-id="91932-357">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="91932-358">Wenn Sie PowerShell verwenden, um eine Filterregel für ausgehende Spamnachrichten zu entfernen, wird die entsprechende Richtlinie für ausgehende Spamfilter nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="91932-358">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="91932-359">Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilterregel in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="91932-359">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="91932-360">In diesem Beispiel wird die filterregel für ausgehende Spamnachrichten mit dem Namen Marketing Department entfernt.</span><span class="sxs-lookup"><span data-stu-id="91932-360">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="91932-361">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="91932-361">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="91932-362">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91932-362">For more information</span></span>

[<span data-ttu-id="91932-363">Entfernen von blockierten Benutzern aus dem Portal "Eingeschränkte Benutzer"</span><span class="sxs-lookup"><span data-stu-id="91932-363">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="91932-364">Pool für besonders riskante Zustellungen für ausgehende Nachrichten</span><span class="sxs-lookup"><span data-stu-id="91932-364">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="91932-365">Häufig gestellte Fragen zum Antispamschutz</span><span class="sxs-lookup"><span data-stu-id="91932-365">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.yml)

[<span data-ttu-id="91932-366">Bericht über automatisch weitergeleitete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="91932-366">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)