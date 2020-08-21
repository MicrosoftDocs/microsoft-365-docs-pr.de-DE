---
title: Konfigurieren der ausgehenden Spamfilterung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie ausgehende Spam Richtlinien in Exchange Online Protection (EoP) anzeigen, erstellen, ändern und löschen.
ms.openlocfilehash: 530c1af9b7802be6073f19331ce7f6a20bdb2668
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845978"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="4abe1-103">Konfigurieren der ausgehenden Spamfilterung in EoP</span><span class="sxs-lookup"><span data-stu-id="4abe1-103">Configure outbound spam filtering in EOP</span></span>

<span data-ttu-id="4abe1-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer werden ausgehende e-Mail-Nachrichten, die über EoP gesendet werden, automatisch auf Spam und ungewöhnliche Sendeaktivitäten überprüft.</span><span class="sxs-lookup"><span data-stu-id="4abe1-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="4abe1-105">Ausgehende Spamnachrichten von einem Benutzer in Ihrer Organisation weisen in der Regel auf ein kompromittiertes Konto hin.</span><span class="sxs-lookup"><span data-stu-id="4abe1-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="4abe1-106">Verdächtige ausgehende Nachrichten werden als Spam gekennzeichnet (unabhängig von der Spam Konfidenz Stufe oder der SCL-Bewertung) und werden über den [risikoreichen Zustellungs Pool](high-risk-delivery-pool-for-outbound-messages.md) weitergeleitet, um die Reputation des Diensts zu schützen (also Microsoft 365-Quell-e-Mail-Server nicht in IP-Sperrlisten aufbewahren).</span><span class="sxs-lookup"><span data-stu-id="4abe1-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="4abe1-107">Administratoren werden automatisch über verdächtige ausgehende e-Mail-Aktivitäten und blockierte Benutzer über [Warnungsrichtlinien](../../compliance/alert-policies.md)benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="4abe1-108">EoP verwendet ausgehende Spam Richtlinien als Teil der gesamten Abwehr von Spam in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="4abe1-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="4abe1-109">Weitere Informationen finden Sie unter [Antispamschutz](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="4abe1-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="4abe1-110">Administratoren können die standardmäßige ausgehende Spam Richtlinie anzeigen, bearbeiten und konfigurieren (jedoch nicht löschen).</span><span class="sxs-lookup"><span data-stu-id="4abe1-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="4abe1-111">Um eine höhere Granularität zu erzielen, können Sie auch benutzerdefinierte ausgehende Spam Richtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="4abe1-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="4abe1-112">Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="4abe1-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="4abe1-113">Sie können ausgehende Spam Richtlinien im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4abe1-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="4abe1-114">Die grundlegenden Elemente einer ausgehenden Spam Richtlinie in EoP sind:</span><span class="sxs-lookup"><span data-stu-id="4abe1-114">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="4abe1-115">**Die Richtlinie für ausgehende Spamfilter**: gibt die Aktionen für ausgehende Spamfilter Urteile und die Benachrichtigungsoptionen an.</span><span class="sxs-lookup"><span data-stu-id="4abe1-115">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="4abe1-116">**Die ausgehende Spamfilter Regel**: gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) für eine Richtlinie für ausgehende Spamfilter an.</span><span class="sxs-lookup"><span data-stu-id="4abe1-116">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="4abe1-117">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie ausgehende Spam Richtlinien im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="4abe1-117">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="4abe1-118">Wenn Sie eine Richtlinie erstellen, erstellen Sie tatsächlich eine ausgehende Spamfilter Regel und die zugehörige Filterrichtlinie für ausgehende Spam gleichzeitig unter Verwendung desselben Namens für beide.</span><span class="sxs-lookup"><span data-stu-id="4abe1-118">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="4abe1-119">Wenn Sie eine Richtlinie ändern, ändern die Einstellungen im Zusammenhang mit dem Namen, der Priorität, den aktivierten oder deaktivierten und den Empfänger filtern die ausgehende Spamfilter Regel.</span><span class="sxs-lookup"><span data-stu-id="4abe1-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="4abe1-120">Bei allen anderen Einstellungen wird die zugehörige Filterrichtlinie für ausgehende Spam geändert.</span><span class="sxs-lookup"><span data-stu-id="4abe1-120">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="4abe1-121">Wenn Sie eine Richtlinie entfernen, werden die ausgehende Spamfilter Regel und die zugehörige Filterrichtlinie für ausgehende Spam entfernt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-121">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="4abe1-122">In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="4abe1-123">Weitere Informationen finden Sie im Abschnitt [Verwenden von Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Konfigurieren von Richtlinien für ausgehende Spam Richtlinien](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="4abe1-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this topic.</span></span>

<span data-ttu-id="4abe1-124">Jede Organisation verfügt über eine integrierte ausgehende Spam Richtlinie mit dem Namen Default, die die folgenden Eigenschaften aufweist:</span><span class="sxs-lookup"><span data-stu-id="4abe1-124">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="4abe1-125">Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine ausgehende Spamfilter Regel (Empfängerfilter) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4abe1-125">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="4abe1-126">Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet).</span><span class="sxs-lookup"><span data-stu-id="4abe1-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="4abe1-127">Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer Vorrang vor der Richtlinie „Standard“.</span><span class="sxs-lookup"><span data-stu-id="4abe1-127">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="4abe1-128">Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="4abe1-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="4abe1-129">Um die Effektivität der ausgehenden Spamfilterung zu verbessern, können Sie benutzerdefinierte ausgehende Spam Richtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="4abe1-129">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4abe1-130">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="4abe1-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4abe1-131">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="4abe1-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4abe1-132">Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="4abe1-132">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="4abe1-133">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4abe1-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="4abe1-134">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="4abe1-134">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4abe1-135">Bevor Sie die in diesem Artikel besprochenen Verfahren ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="4abe1-135">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="4abe1-136">Zum Hinzufügen, ändern und Löschen von ausgehenden Spam Richtlinien müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="4abe1-136">To add, modify, and delete outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="4abe1-137">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4abe1-137">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="4abe1-138">**Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="4abe1-138">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="4abe1-139">Für den schreibgeschützten Zugriff auf ausgehende Spam Richtlinien müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="4abe1-139">For read-only access to outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="4abe1-140">**Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4abe1-140">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="4abe1-141">**Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="4abe1-141">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="4abe1-142">Unsere empfohlenen Einstellungen für ausgehende Spam Richtlinien finden Sie unter [EoP Outbound Spamfilter Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="4abe1-142">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="4abe1-143">Die standardmäßigen [Warnungsrichtlinien](../../compliance/alert-policies.md) mit dem Namen " **e-Mail-Sende Grenzwert**" überschritten, **verdächtige e-Mail-Sende Muster wurden erkannt**und Benutzer, die **von e-Mails eingeschränkt** sind, senden bereits e-Mail-Benachrichtigungen an Mitglieder der Gruppe der **TenantAdmins** (**globale Administratoren**) über ungewöhnliche ausgehende e-Mail-Aktivitäten und blockierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="4abe1-143">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="4abe1-144">Weitere Informationen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="4abe1-144">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="4abe1-145">Es wird empfohlen, diese Warnungsrichtlinien anstelle der Benachrichtigungsoptionen in ausgehenden Spam Richtlinien zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4abe1-145">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="4abe1-146">Verwenden des Security & Compliance Center zum Erstellen von ausgehenden Spam Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4abe1-146">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="4abe1-147">Durch das Erstellen einer benutzerdefinierten ausgehenden Spam Richtlinie im Security & Compliance Center werden die Spamfilter Regel und die zugehörige Spamfilter Richtlinie gleichzeitig mit dem gleichen Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-147">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="4abe1-148">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="4abe1-149">Klicken Sie auf der Seite **Anti-Spam-Einstellungen** auf **ausgehende Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-149">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="4abe1-150">Konfigurieren Sie in der geöffneten **ausgehenden Spamfilter Richtlinie** , die geöffnet wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="4abe1-150">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="4abe1-151">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="4abe1-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="4abe1-152">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="4abe1-152">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="4abe1-153">Optional Erweitern Sie den Abschnitt **Benachrichtigungen** , um weitere Benutzer zu konfigurieren, die Kopien und Benachrichtigungen von verdächtigen ausgehenden e-Mail-Nachrichten erhalten sollen:</span><span class="sxs-lookup"><span data-stu-id="4abe1-153">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="4abe1-154">**Senden einer Kopie verdächtiger ausgehender e-Mail-Nachrichten an bestimmte Personen**: mit dieser Einstellung werden den Verdächtigen ausgehenden Nachrichten die angegebenen Benutzer als Bcc-Empfänger hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-154">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="4abe1-155">Diese Einstellung funktioniert nur in der standardmäßigen ausgehenden Spam Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="4abe1-155">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="4abe1-156">Es funktioniert nicht in benutzerdefinierten ausgehenden Spam Richtlinien, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-156">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="4abe1-157">So aktivieren Sie diese Einstellung:</span><span class="sxs-lookup"><span data-stu-id="4abe1-157">To enable this setting:</span></span>

     1. <span data-ttu-id="4abe1-158">Aktivieren Sie das Kontrollkästchen, um die Einstellung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4abe1-158">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="4abe1-159">Klicken Sie auf **Personen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-159">Click **Add people**.</span></span> <span data-ttu-id="4abe1-160">Im Flyout **Empfänger hinzufügen oder entfernen** :</span><span class="sxs-lookup"><span data-stu-id="4abe1-160">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="4abe1-161">Geben Sie die E-Mail-Adresse des Absenders ein.</span><span class="sxs-lookup"><span data-stu-id="4abe1-161">Enter the sender's email address.</span></span> <span data-ttu-id="4abe1-162">Sie können mehrere e-Mail-Adressen durch Semikolons getrennt angeben (;) oder ein Empfänger pro Reihe.</span><span class="sxs-lookup"><span data-stu-id="4abe1-162">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="4abe1-163">Click</span><span class="sxs-lookup"><span data-stu-id="4abe1-163">Click</span></span> ![Hinzufügen (Symbol)](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="4abe1-165">zum Hinzufügen der Empfänger.</span><span class="sxs-lookup"><span data-stu-id="4abe1-165">to add the recipients.</span></span>

        <span data-ttu-id="4abe1-166">Wiederholen Sie diese Schritte so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="4abe1-166">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="4abe1-167">Die Empfänger, die Sie hinzugefügt haben, werden im Flyout im Abschnitt **Empfängerliste** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-167">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="4abe1-168">Klicken Sie auf die Schaltfläche entfernen, um einen Empfänger zu löschen ![ ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="4abe1-168">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="4abe1-169">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-169">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="4abe1-170">Deaktivieren Sie das Kontrollkästchen, um diese Einstellung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4abe1-170">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="4abe1-171">**Benachrichtigen bestimmter Personen, wenn ein Absender aufgrund des Sendens von ausgehenden Spam blockiert wird**:</span><span class="sxs-lookup"><span data-stu-id="4abe1-171">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="4abe1-172">Diese Einstellung wird derzeit von ausgehenden Spam Richtlinien veraltet.</span><span class="sxs-lookup"><span data-stu-id="4abe1-172">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="4abe1-173">Die standardmäßige [Warnungs Richtlinie](../../compliance/alert-policies.md) mit dem Namen " **Benutzer vom Senden von e-Mails eingeschränkt** " sendet bereits e-Mail-Benachrichtigungen an Mitglieder der Gruppe **TenantAdmins** (**globale Administratoren**), wenn Benutzer aufgrund der Überschreitung der Grenzwerte im Abschnitt **Empfänger Grenzwerte** blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="4abe1-173">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="4abe1-174">**Es wird dringend empfohlen, dass Sie die Warnungs Richtlinie anstelle dieser Einstellung in der ausgehenden Spam Richtlinie verwenden, um Administratoren und andere Benutzer zu benachrichtigen**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-174">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="4abe1-175">Anweisungen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="4abe1-175">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="4abe1-176">Optional Erweitern Sie den Abschnitt **Empfänger Grenzwerte** , um die Grenzwerte und Aktionen für verdächtige ausgehende e-Mail-Nachrichten zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="4abe1-176">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="4abe1-177">Diese Einstellungen gelten nur für Cloud-basierte Postfächer.</span><span class="sxs-lookup"><span data-stu-id="4abe1-177">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="4abe1-178">**Maximale Anzahl von Empfängern pro Benutzer**</span><span class="sxs-lookup"><span data-stu-id="4abe1-178">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="4abe1-179">Ein gültiger Wert ist 0 bis 10000.</span><span class="sxs-lookup"><span data-stu-id="4abe1-179">A valid value is 0 to 10000.</span></span> <span data-ttu-id="4abe1-180">Der Standardwert ist 0, was bedeutet, dass die Dienst Standardwerte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4abe1-180">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="4abe1-181">Weitere Informationen finden Sie unter [sending Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span><span class="sxs-lookup"><span data-stu-id="4abe1-181">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="4abe1-182">**Externer stündlicher Grenzwert**: die maximale Anzahl externer Empfänger pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="4abe1-182">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="4abe1-183">**Interner stündlicher Grenzwert**: die maximale Anzahl interner Empfänger pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="4abe1-183">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="4abe1-184">**Daily Limit**: die maximale Gesamtzahl der Empfänger pro Tag.</span><span class="sxs-lookup"><span data-stu-id="4abe1-184">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="4abe1-185">**Aktion, wenn ein Benutzer die oben genannten Grenzwerte überschreitet**: Konfigurieren Sie die Aktion, die ausgeführt werden soll, wenn eine der **Empfänger Grenzwerte** überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="4abe1-185">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="4abe1-186">Für alle Aktionen werden die im Benutzer angegebenen Empfänger **vom Senden von e-Mail-** Warnungsrichtlinien eingeschränkt (und im jetzt redundante **Benachrichtigen bestimmter Personen, wenn ein Absender aufgrund des Sendens von ausgehenden Spam** -Einstellungen in der ausgehenden Spam Richtlinie blockiert wird, e-Mail-Benachrichtigungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="4abe1-187">**Beschränken Sie den Benutzer am Senden von e-Mails bis zum folgenden Tag**: Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="4abe1-187">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="4abe1-188">E-Mail-Benachrichtigungen werden gesendet, und der Benutzer kann keine weiteren Nachrichten auf der Grundlage der UTC-Zeit bis zum nächsten Tag senden.</span><span class="sxs-lookup"><span data-stu-id="4abe1-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="4abe1-189">Es gibt keine Möglichkeit für den Administrator, diesen Block außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-189">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="4abe1-190">Die Aktivitäts Benachrichtigung mit dem Namen " **Benutzer vom Senden von e-Mails eingeschränkt** " benachrichtigt Administratoren (per e-Mail und auf der Seite **Benachrichtigungen anzeigen** ).</span><span class="sxs-lookup"><span data-stu-id="4abe1-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="4abe1-191">Alle Empfänger, die in der Richtlinie in den Einstellungen " **bestimmte Personen Benachrichtigen, wenn ein Absender aufgrund des Sendens ausgehenden Spam blockiert ist** " angegeben werden, werden ebenfalls benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="4abe1-192">Der Benutzer kann bis zum nächsten Tag keine weiteren Nachrichten senden, basierend auf UTC-Zeit.</span><span class="sxs-lookup"><span data-stu-id="4abe1-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="4abe1-193">Es gibt keine Möglichkeit für den Administrator, diesen Block außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-193">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="4abe1-194">**Einschränken des Benutzers beim Senden von e-Mails**: e-Mail-Benachrichtigungen werden gesendet, der Benutzer wird dem Portal **[ <https://sip.protection.office.com/restrictedusers> restricted users]** im Security & Compliance Center hinzugefügt, und der Benutzer kann keine e-Mails senden, bevor er von einem Administrator aus dem Portal für **eingeschränkte Benutzer** entfernt wird. Nachdem der Benutzer von einem Administrator aus der Liste entfernt wurde, wird der Benutzer für diesen Tag nicht mehr eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="4abe1-195">Anweisungen hierzu finden Sie unter [Entfernen eines Benutzers aus dem Portal für eingeschränkte Benutzer nach dem Senden von Spam-e-Mails](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="4abe1-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="4abe1-196">**Keine Aktion, nur Warnung**: e-Mail-Benachrichtigungen werden gesendet.</span><span class="sxs-lookup"><span data-stu-id="4abe1-196">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="4abe1-197">Optional Erweitern Sie den Abschnitt **automatische Weiterleitung** , um die automatische e-Mail-Weiterleitung von Benutzern an externe Absender zu steuern.</span><span class="sxs-lookup"><span data-stu-id="4abe1-197">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="4abe1-198">Weitere Informationen zur automatischen Weiterleitung finden Sie unter [Konfigurieren der e-Mail-Weiterleitung](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="4abe1-198">For more information about automatic forwarding, see [Configure email forwarding](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="4abe1-199">Vor September 2020 sind diese Einstellungen verfügbar, werden jedoch nicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-199">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="4abe1-200">Diese Einstellungen gelten nur für Cloud-basierte Postfächer.</span><span class="sxs-lookup"><span data-stu-id="4abe1-200">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="4abe1-201">Die automatische Weiterleitung an interne Empfänger ist von diesen Einstellungen nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-201">Automatic forwarding to internal recipients is not affected by these setting.</span></span>

   <span data-ttu-id="4abe1-202">Die verfügbaren Werte sind:</span><span class="sxs-lookup"><span data-stu-id="4abe1-202">The available values are:</span></span>

   - <span data-ttu-id="4abe1-203">**Automatisch System gesteuert**: ermöglicht das Filtern von ausgehenden Spam Funktionen zur Steuerung der automatischen externen e-Mail-Weiterleitung.</span><span class="sxs-lookup"><span data-stu-id="4abe1-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="4abe1-204">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="4abe1-204">This is the default value.</span></span>

   - <span data-ttu-id="4abe1-205">**On**: automatische externe e-Mail-Weiterleitung wird von der Richtlinie nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4abe1-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>

   - <span data-ttu-id="4abe1-206">**Off**: alle automatischen externen e-Mail-Weiterleitungen werden durch die Richtlinie deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4abe1-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="4abe1-207">Erforderlich Erweitern Sie den Abschnitt **angewendet für** , um die internen Absender zu identifizieren, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4abe1-207">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="4abe1-208">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="4abe1-208">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="4abe1-209">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<sender1\>_ oder _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="4abe1-209">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="4abe1-210">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<sender1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="4abe1-210">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="4abe1-211">Um alle verfügbaren Bedingungen anzuzeigen, ist es am einfachsten, wenn Sie auf **Bedingung hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="4abe1-211">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="4abe1-212">Sie können auf ![Schaltfläche „Entfernen“](../../media/scc-remove-icon.png) klicken, um Bedingungen zu entfernen, die Sie nicht konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4abe1-212">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="4abe1-213">**Die Absenderdomäne lautet**: gibt Absender in einer oder mehreren der konfigurierten akzeptierten Domänen in der Organisation an.</span><span class="sxs-lookup"><span data-stu-id="4abe1-213">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="4abe1-214">Klicken Sie in das Feld **Tag hinzufügen**, um eine Domäne anzuzeigen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-214">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="4abe1-215">Klicken Sie erneut auf das Feld **Tag hinzufügen**, um weitere Domänen auszuwählen, falls mehrere Domänen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4abe1-215">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="4abe1-216">**Absender lautet**: gibt einen oder mehrere Benutzer in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="4abe1-216">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="4abe1-217">Klicken Sie auf **Tag hinzufügen**, und beginnen Sie mit der Eingabe, um die Liste zu filtern.</span><span class="sxs-lookup"><span data-stu-id="4abe1-217">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="4abe1-218">Klicken Sie erneut auf das Feld **Tag hinzufügen** , um weitere Absender auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-218">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="4abe1-219">**Der Absender ist Mitglied von**: gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="4abe1-219">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="4abe1-220">Klicken Sie auf **Tag hinzufügen**, und beginnen Sie mit der Eingabe, um die Liste zu filtern.</span><span class="sxs-lookup"><span data-stu-id="4abe1-220">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="4abe1-221">Klicken Sie erneut auf das Feld **Tag hinzufügen** , um weitere Absender auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-221">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="4abe1-222">**Außer wenn**: Klicken Sie zum Angeben von Ausnahmen für die Regel dreimal auf **Bedingung hinzufügen**, um alle verfügbaren Ausnahmen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-222">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="4abe1-223">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-223">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="4abe1-224">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-224">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="4abe1-225">Verwenden des Security & Compliance Center zum Anzeigen von ausgehenden Spam Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4abe1-225">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="4abe1-226">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="4abe1-227">Klicken Sie auf der Seite **Anti-Spam-Einstellungen** auf ![ Symbol erweitern ](../../media/scc-expand-icon.png) , um eine ausgehende Spam Richtlinie zu erweitern:</span><span class="sxs-lookup"><span data-stu-id="4abe1-227">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="4abe1-228">Die Standardrichtlinie mit dem Namen " **Outbound Spamfilter Policy**".</span><span class="sxs-lookup"><span data-stu-id="4abe1-228">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="4abe1-229">Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei der Wert in der Spalte **Typ** eine **benutzerdefinierte ausgehende Spam Richtlinie**ist.</span><span class="sxs-lookup"><span data-stu-id="4abe1-229">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="4abe1-230">Die Richtlinieneinstellungen werden in den erweiterten Richtliniendetails angezeigt, die angezeigt werden, oder Sie können auf **Richtlinie bearbeiten**klicken.</span><span class="sxs-lookup"><span data-stu-id="4abe1-230">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="4abe1-231">Verwenden des Security & Compliance Center zum Ändern von Richtlinien für ausgehende Spamnachrichten</span><span class="sxs-lookup"><span data-stu-id="4abe1-231">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="4abe1-232">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="4abe1-233">Klicken Sie auf der Seite **Anti-Spam-Einstellungen** auf ![ Symbol erweitern ](../../media/scc-expand-icon.png) , um eine ausgehende Spam Richtlinie zu erweitern:</span><span class="sxs-lookup"><span data-stu-id="4abe1-233">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="4abe1-234">Die Standardrichtlinie mit dem Namen " **Outbound Spamfilter Policy**".</span><span class="sxs-lookup"><span data-stu-id="4abe1-234">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="4abe1-235">Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei der Wert in der Spalte **Typ** eine **benutzerdefinierte ausgehende Spam Richtlinie**ist.</span><span class="sxs-lookup"><span data-stu-id="4abe1-235">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="4abe1-236">Klicken Sie auf **Richtlinie bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-236">Click **Edit policy**.</span></span>

<span data-ttu-id="4abe1-237">Bei benutzerdefinierten ausgehenden Spam Richtlinien sind die verfügbaren Einstellungen im Flyout, die angezeigt werden, mit denen im Abschnitt [Verwenden der Sicherheits & Compliance Center zum Erstellen von ausgehenden Spam Richtlinien](#use-the-security--compliance-center-to-create-outbound-spam-policies) beschrieben identisch.</span><span class="sxs-lookup"><span data-stu-id="4abe1-237">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="4abe1-238">Für die standardmäßige ausgehende Spam Richtlinie mit dem Namen " **ausgehende Spamfilter Richtlinie**" ist der Abschnitt " **angewendet für** " nicht verfügbar (die Richtlinie gilt für alle), und Sie können die Richtlinie nicht umbenennen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-238">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="4abe1-239">Informationen zum Aktivieren oder Deaktivieren einer Richtlinie, zum Festlegen der Prioritätsreihenfolge der Richtlinien oder zum Konfigurieren der Quarantänebenachrichtigungen für Endbenutzer finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="4abe1-239">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="4abe1-240">Aktivieren oder Deaktivieren von ausgehenden Spam Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4abe1-240">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="4abe1-241">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-241">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="4abe1-242">Klicken Sie auf der Seite **Anti-Spam-Einstellungen** auf ![ Symbol erweitern, ](../../media/scc-expand-icon.png) um eine benutzerdefinierte Richtlinie zu erweitern, die Sie erstellt haben (der Wert in der Spalte **Typ** ist eine **benutzerdefinierte ausgehende Spam Richtlinie**).</span><span class="sxs-lookup"><span data-stu-id="4abe1-242">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="4abe1-243">Achten Sie in den angezeigten erweiterten Richtliniendetails auf den Wert in der Spalte **Ein**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-243">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="4abe1-244">Schieben Sie die Umschaltfläche nach links, um die Richtlinie zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="4abe1-244">Move the toggle to the left to disable the policy:</span></span> ![Umschaltfläche aus](../../media/scc-toggle-off.png)

   <span data-ttu-id="4abe1-246">Schieben Sie die Umschaltfläche nach rechts, um die Richtlinie zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="4abe1-246">Move the toggle to the right to enable the policy:</span></span> ![Umschaltfläche ein](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="4abe1-248">Sie können die standardmäßige ausgehende Spam Richtlinie nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4abe1-248">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="4abe1-249">Festlegen der Priorität von benutzerdefinierten ausgehenden Spam Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4abe1-249">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="4abe1-250">Standardmäßig erhalten ausgehende Spam Richtlinien eine Priorität, die auf der Reihenfolge basiert, in der Sie erstellt wurden (neuere Policen haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="4abe1-250">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="4abe1-251">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="4abe1-251">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="4abe1-252">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4abe1-252">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="4abe1-253">Benutzerdefinierte ausgehende Spam Richtlinien werden in der Reihenfolge angezeigt, in der Sie verarbeitet werden (die erste Richtlinie hat den **Prioritäts** Wert 0).</span><span class="sxs-lookup"><span data-stu-id="4abe1-253">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="4abe1-254">Bei der standardmäßigen ausgehenden Spam Richtlinie mit dem Namen " **ausgehende Spamfilter Richtlinie** " ist der Prioritätswert **niedrig**und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4abe1-254">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="4abe1-255">Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).</span><span class="sxs-lookup"><span data-stu-id="4abe1-255">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="4abe1-256">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-256">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="4abe1-257">Suchen Sie auf der Seite **Antispameinstellungen** nach den Richtlinien, bei denen es sich bei dem Wert in der Spalte **Typ** um eine **benutzerdefinierte ausgehende Spam Richtlinie**handelt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-257">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="4abe1-258">Beachten Sie die Werte in der Spalte **Priorität**:</span><span class="sxs-lookup"><span data-stu-id="4abe1-258">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="4abe1-259">Die benutzerdefinierte Richtlinie für ausgehende Spam mit der höchsten Priorität hat den ![ Abwärtspfeil-Symbolwert ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-259">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="4abe1-260">Die benutzerdefinierte Richtlinie für ausgehende Spam mit der niedrigsten Priorität hat den Wert ![ nach oben Pfeilsymbol ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (beispielsweise nach ![ oben Pfeilsymbol ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="4abe1-260">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="4abe1-261">Wenn Sie drei oder mehr benutzerdefinierte ausgehende Spam Richtlinien haben, haben die Richtlinien zwischen der höchsten und der niedrigsten Priorität Werte ![ nach oben Pfeilsymbol ](../../media/ITPro-EAC-UpArrowIcon.png)![ nach unten Pfeilsymbol ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (beispielsweise ![ nach oben Pfeilsymbol ](../../media/ITPro-EAC-UpArrowIcon.png)![ nach unten Pfeilsymbol ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="4abe1-261">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="4abe1-262">Klicken Sie auf</span><span class="sxs-lookup"><span data-stu-id="4abe1-262">Click</span></span> ![Pfeil-nach-oben-Symbol](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="4abe1-264">oder</span><span class="sxs-lookup"><span data-stu-id="4abe1-264">or</span></span> ![Pfeil-nach-unten-Symbol,](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="4abe1-266">um die benutzerdefinierte Richtlinie für ausgehende Spam in der Liste Priorität nach oben oder nach unten zu verlagern.</span><span class="sxs-lookup"><span data-stu-id="4abe1-266">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="4abe1-267">Verwenden des Security & Compliance Center zum Entfernen von ausgehenden Spam Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4abe1-267">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="4abe1-268">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="4abe1-269">Klicken Sie auf der Seite **Anti-Spam-Einstellungen** auf ![ Symbol erweitern, ](../../media/scc-expand-icon.png) um die benutzerdefinierte Richtlinie zu erweitern, die Sie löschen möchten (die Spalte **Typ** ist eine **benutzerdefinierte ausgehende Spam Richtlinie**).</span><span class="sxs-lookup"><span data-stu-id="4abe1-269">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="4abe1-270">Klicken Sie in den angezeigten erweiterten Richtliniendetails auf **Richtlinie löschen**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-270">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="4abe1-271">Klicken Sie im angezeigten Dialogfeld mit der Warnung auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="4abe1-271">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="4abe1-272">Die Standardrichtlinie kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="4abe1-272">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="4abe1-273">Verwenden von Exchange Online PowerShell oder eigenständigen EoP PowerShell zum Konfigurieren von ausgehenden Spam Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4abe1-273">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="4abe1-274">Wie bereits beschrieben, besteht eine ausgehende Spam-Richtlinie aus einer ausgehenden Spamfilter Richtlinie und einer ausgehenden Spamfilter Regel.</span><span class="sxs-lookup"><span data-stu-id="4abe1-274">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="4abe1-275">In Exchange Online PowerShell oder eigenständigen EoP PowerShell ist der Unterschied zwischen ausgehenden Spamfilter-Richtlinien und ausgehenden spamfilterregeln erkennbar.</span><span class="sxs-lookup"><span data-stu-id="4abe1-275">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="4abe1-276">Sie verwalten Richtlinien für ausgehende Spamfilter mithilfe der Cmdlets \*\* \* -HostedOutboundSpamFilterPolicy\*\* , und Sie verwalten Filterregeln für ausgehende Spam mithilfe der Cmdlets \*\* \* -HostedOutboundSpamFilterRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="4abe1-276">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="4abe1-277">In PowerShell erstellen Sie zuerst die Richtlinie für ausgehende Spamfilter, dann erstellen Sie die ausgehende Spamfilter Regel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4abe1-277">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="4abe1-278">In PowerShell ändern Sie die Einstellungen in der Richtlinie für ausgehende Spamfilter und der ausgehenden Spamfilter Regel separat.</span><span class="sxs-lookup"><span data-stu-id="4abe1-278">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="4abe1-279">Wenn Sie eine ausgehende Spamfilter Richtlinie aus PowerShell entfernen, wird die entsprechende Filterregel für ausgehende Spam nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-279">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="4abe1-280">Verwenden von PowerShell zum Erstellen von ausgehenden Spam Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4abe1-280">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="4abe1-281">Das Erstellen einer ausgehenden Spam Richtlinie in PowerShell erfolgt in einem zweistufigen Prozess:</span><span class="sxs-lookup"><span data-stu-id="4abe1-281">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="4abe1-282">Erstellen Sie die Richtlinie für ausgehende Spamfilter.</span><span class="sxs-lookup"><span data-stu-id="4abe1-282">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="4abe1-283">Erstellen Sie die Filterregel für ausgehende Spam, die die Richtlinie für ausgehende Spamfilter angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4abe1-283">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="4abe1-284">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="4abe1-284">**Notes**:</span></span>

- <span data-ttu-id="4abe1-285">Sie können eine neue Filterregel für ausgehende Spam erstellen und ihr eine vorhandene, nicht zugeordnete Filterrichtlinie für ausgehende Spam zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-285">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="4abe1-286">Eine ausgehende Spamfilter Regel kann nicht mehr als einer ausgehenden Spamfilter Richtlinie zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="4abe1-286">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="4abe1-287">Sie können die folgenden Einstellungen für neue Richtlinien für ausgehende Spamfilter in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Security & Compliance Center verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="4abe1-287">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="4abe1-288">Erstellen Sie die neue Richtlinie als deaktiviert (_aktiviert_ im `$false` Cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="4abe1-288">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="4abe1-289">Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) für das Cmdlet **New-HostedOutboundSpamFilterRule** fest).</span><span class="sxs-lookup"><span data-stu-id="4abe1-289">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="4abe1-290">Eine neue Richtlinie für ausgehende Spamfilter, die Sie in PowerShell erstellen, ist erst im Security & Compliance Center sichtbar, wenn Sie die Richtlinie einer Spamfilter Regel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-290">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="4abe1-291">Schritt 1: Erstellen einer ausgehenden Spamfilter Richtlinie mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4abe1-291">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="4abe1-292">Verwenden Sie die folgende Syntax, um eine Filterrichtlinie für ausgehende Spam zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="4abe1-292">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="4abe1-293">In diesem Beispiel wird eine neue Richtlinie für ausgehende Spamfilter namens "Contoso Executives" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="4abe1-293">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="4abe1-294">Die Empfänger Raten Begrenzungen sind auf kleinere Werte beschränkt, die von den Standardeinstellungen abweichen.</span><span class="sxs-lookup"><span data-stu-id="4abe1-294">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="4abe1-295">Weitere Informationen finden Sie unter [sending Limits Across Microsoft 365 Options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="4abe1-295">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="4abe1-296">Nachdem eine der Grenzwerte erreicht wurde, wird verhindert, dass der Benutzer Nachrichten sendet.</span><span class="sxs-lookup"><span data-stu-id="4abe1-296">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="4abe1-297">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="4abe1-297">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="4abe1-298">Schritt 2: Erstellen einer ausgehenden Spamfilter Regel mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4abe1-298">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="4abe1-299">Verwenden Sie die folgende Syntax, um eine Filterregel für ausgehende Spam zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="4abe1-299">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="4abe1-300">In diesem Beispiel wird eine neue ausgehende Spamfilter Regel namens "Contoso Executives" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="4abe1-300">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="4abe1-301">Die Richtlinie für ausgehende Spamfilter mit dem Namen "Contoso Executives" ist der Regel zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4abe1-301">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="4abe1-302">Die Regel gilt für Mitglieder der Gruppe mit dem Namen „Contoso Executive Group“.</span><span class="sxs-lookup"><span data-stu-id="4abe1-302">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="4abe1-303">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="4abe1-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="4abe1-304">Verwenden von PowerShell zum Anzeigen von Richtlinien für ausgehende Spamfilter</span><span class="sxs-lookup"><span data-stu-id="4abe1-304">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="4abe1-305">Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller ausgehenden Spamfilter Richtlinien zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="4abe1-305">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="4abe1-306">Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Richtlinie für ausgehende Spamfilter zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="4abe1-306">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="4abe1-307">In diesem Beispiel werden alle Eigenschaftswerte für die ausgehende Spamfilter Richtlinie "Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4abe1-307">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="4abe1-308">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="4abe1-308">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="4abe1-309">Verwenden von PowerShell zum Anzeigen von Regeln für ausgehende Spamfilter</span><span class="sxs-lookup"><span data-stu-id="4abe1-309">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="4abe1-310">Verwenden Sie die folgende Syntax, um vorhandene Filterregeln für ausgehende Spam anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="4abe1-310">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="4abe1-311">Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller ausgehenden spamfilterregeln zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="4abe1-311">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="4abe1-312">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="4abe1-312">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="4abe1-313">Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Filterregel für ausgehende Spam Daten zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="4abe1-313">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="4abe1-314">In diesem Beispiel werden alle Eigenschaftswerte für die ausgehende Spamfilter Regel namens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4abe1-314">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="4abe1-315">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="4abe1-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="4abe1-316">Verwenden von PowerShell zum Ändern von Richtlinien für ausgehende Spamfilter</span><span class="sxs-lookup"><span data-stu-id="4abe1-316">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="4abe1-317">Die gleichen Einstellungen stehen zur Verfügung, wenn Sie eine Filterrichtlinie für Schadsoftware in PowerShell wie beim Erstellen der Richtlinie wie im Abschnitt [Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für ausgehende Spamfilter](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) weiter oben in diesem Thema beschrieben ändern.</span><span class="sxs-lookup"><span data-stu-id="4abe1-317">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="4abe1-318">Sie können keine ausgehende Spamfilter Richtlinie umbenennen (das Cmdlet " **HostedOutboundSpamFilterPolicy** " hat keinen Parameter " _Name_ ").</span><span class="sxs-lookup"><span data-stu-id="4abe1-318">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="4abe1-319">Wenn Sie eine ausgehende Spam Richtlinie im Security & Compliance Center umbenennen, benennen Sie die ausgehende Spamfilter _Regel_nur um.</span><span class="sxs-lookup"><span data-stu-id="4abe1-319">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="4abe1-320">Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilter Richtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="4abe1-320">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="4abe1-321">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="4abe1-321">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="4abe1-322">Verwenden von PowerShell zum Ändern von Regeln für ausgehende Spamfilter</span><span class="sxs-lookup"><span data-stu-id="4abe1-322">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="4abe1-323">Die einzige Einstellung, die beim Ändern einer ausgehenden Spamfilter Regel in PowerShell nicht verfügbar ist, ist der Parameter _Enabled_ , mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="4abe1-323">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="4abe1-324">Informationen zum Aktivieren oder Deaktivieren vorhandener Filterregeln für ausgehende Spamfilter finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-324">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="4abe1-325">Andernfalls stehen keine zusätzlichen Einstellungen zur Verfügung, wenn Sie eine ausgehende Spamfilter Regel in PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="4abe1-325">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="4abe1-326">Die gleichen Einstellungen sind verfügbar, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen eines Filters für ausgehende Spamfilter](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) weiter oben in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4abe1-326">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="4abe1-327">Verwenden Sie die folgende Syntax, um eine Filterregel für ausgehende Spam zu ändern:</span><span class="sxs-lookup"><span data-stu-id="4abe1-327">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="4abe1-328">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="4abe1-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="4abe1-329">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für ausgehende Spamfilter</span><span class="sxs-lookup"><span data-stu-id="4abe1-329">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="4abe1-330">Durch Aktivieren oder Deaktivieren einer ausgehenden Spamfilter Regel in PowerShell wird die gesamte ausgehende Spam Richtlinie (die ausgehende Spamfilter Regel und die zugewiesene Richtlinie für ausgehende Spamfilter) aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4abe1-330">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="4abe1-331">Sie können die standardmäßige ausgehende Spam Richtlinie nicht aktivieren oder deaktivieren (Sie wird immer auf alle Empfänger angewendet).</span><span class="sxs-lookup"><span data-stu-id="4abe1-331">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="4abe1-332">Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilter Regel in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="4abe1-332">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="4abe1-333">In diesem Beispiel wird die ausgehende Spamfilter Regel namens "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4abe1-333">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="4abe1-334">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4abe1-334">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="4abe1-335">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) und [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="4abe1-335">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="4abe1-336">Verwenden von PowerShell zum Festlegen der Priorität von ausgehenden spamfilterregeln</span><span class="sxs-lookup"><span data-stu-id="4abe1-336">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="4abe1-337">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="4abe1-337">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="4abe1-338">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="4abe1-338">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="4abe1-339">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="4abe1-339">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="4abe1-340">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="4abe1-340">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="4abe1-341">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="4abe1-341">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="4abe1-342">Verwenden Sie die folgende Syntax, um die Priorität einer ausgehenden Spamfilter Regel in PowerShell festzulegen:</span><span class="sxs-lookup"><span data-stu-id="4abe1-342">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="4abe1-p139">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="4abe1-p139">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="4abe1-345">Wenn Sie die Priorität einer neuen Regel beim Erstellen festlegen möchten, verwenden Sie stattdessen den Parameter _Priority_ für das Cmdlet **New-HostedOutboundSpamFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="4abe1-345">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="4abe1-346">Die ausgehende standardmäßige Spamfilter Richtlinie verfügt nicht über eine entsprechende Spamfilter Regel, und Sie hat immer den **niedrigsten**Wert für die unveränderbare Priorität.</span><span class="sxs-lookup"><span data-stu-id="4abe1-346">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="4abe1-347">Verwenden von PowerShell zum Entfernen von ausgehenden Spamfilter Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4abe1-347">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="4abe1-348">Wenn Sie PowerShell zum Entfernen einer ausgehenden Spamfilter Richtlinie verwenden, wird die entsprechende Filterregel für ausgehende Spam nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-348">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="4abe1-349">Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilter Richtlinie in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="4abe1-349">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="4abe1-350">In diesem Beispiel wird die Richtlinie für ausgehende Spamfilter namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-350">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="4abe1-351">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="4abe1-351">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="4abe1-352">Verwenden von PowerShell zum Entfernen von Filterregeln für ausgehende Spam</span><span class="sxs-lookup"><span data-stu-id="4abe1-352">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="4abe1-353">Wenn Sie mithilfe von PowerShell eine ausgehende Spamfilter Regel entfernen, wird die entsprechende Filterrichtlinie für ausgehende Spam nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-353">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="4abe1-354">Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilter Regel in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="4abe1-354">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="4abe1-355">In diesem Beispiel wird die ausgehende Spamfilter Regel namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="4abe1-355">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="4abe1-356">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="4abe1-356">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="4abe1-357">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4abe1-357">For more information</span></span>

[<span data-ttu-id="4abe1-358">Entfernen von blockierten Benutzern aus dem Portal „eingeschränkte Benutzer“</span><span class="sxs-lookup"><span data-stu-id="4abe1-358">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="4abe1-359">Pool für besonders riskante Zustellungen für ausgehende Nachrichten</span><span class="sxs-lookup"><span data-stu-id="4abe1-359">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="4abe1-360">Häufig gestellte Fragen zum Antispamschutz</span><span class="sxs-lookup"><span data-stu-id="4abe1-360">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="4abe1-361">Bericht über automatisch weitergeleitete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="4abe1-361">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
