---
title: Konfigurieren von EoP für Junk-Spam in Hybrid Umgebungen
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Spam an Benutzer-Junk-e-Mail-Ordner in einer Exchange Online Protection Hybrid-Umgebung weiterleiten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 14193fecf90a6f2ddde05fbfdaded0ff2bcb5875
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036572"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="674f3-103">Konfigurieren von eigenständigen EoP zur Zustellung von Spam an den Junk-e-Mail-Ordner in Hybrid Umgebungen</span><span class="sxs-lookup"><span data-stu-id="674f3-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

> [!IMPORTANT]
> <span data-ttu-id="674f3-104">Dieses Thema ist nur für eigenständige EoP-Kunden in Hybrid Umgebungen geeignet.</span><span class="sxs-lookup"><span data-stu-id="674f3-104">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="674f3-105">Dieses Thema gilt nicht für Microsoft 365-Kunden mit Exchange Online Postfächern.</span><span class="sxs-lookup"><span data-stu-id="674f3-105">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="674f3-106">Wenn Sie ein eigenständiger Exchange Online Schutz-Kunde (EoP) in einer Hybridumgebung sind, müssen Sie Ihre lokale Exchange-Organisation so konfigurieren, dass Sie die Spamfilter Urteile von EoP erkennt und übersetzt, sodass die Junk-e-Mail-Regel im lokalen Postfach Nachrichten in den Junk-e-Mail-Ordner verschieben kann.</span><span class="sxs-lookup"><span data-stu-id="674f3-106">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="674f3-107">Insbesondere müssen Sie Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) in Ihrer lokalen Exchange-Organisation mit Bedingungen erstellen, die Nachrichten mit einem der folgenden EoP-Antispam-Header und-Werte und Aktionen, die die SCL-Bewertung (Spam Confidence Level) dieser Nachrichten festlegen, auf 6 finden:</span><span class="sxs-lookup"><span data-stu-id="674f3-107">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="674f3-108">`X-Forefront-Antispam-Report: SFV:SPM`(Nachricht als Spam durch Spamfilterung gekennzeichnet)</span><span class="sxs-lookup"><span data-stu-id="674f3-108">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="674f3-109">`X-Forefront-Antispam-Report: SFV:SKS`(Nachricht als Spam durch Nachrichtenfluss Regeln in EoP vor Spamfilterung markiert)</span><span class="sxs-lookup"><span data-stu-id="674f3-109">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="674f3-110">`X-Forefront-Antispam-Report: SFV:SKB`(Nachricht als Spam durch Spamfilterung gekennzeichnet, da sich die e-Mail-Adresse des Absenders oder die e-Mail-Domäne in der Liste blockierter Absender oder in der Liste der blockierten Domänen in EoP befindet)</span><span class="sxs-lookup"><span data-stu-id="674f3-110">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="674f3-111">Weitere Informationen zu diesen Headerwerten finden Sie unter [Anti-Spam Message Headers](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="674f3-111">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="674f3-112">In diesem Thema wird beschrieben, wie Sie diese Nachrichtenfluss Regeln in der Exchange-Verwaltungskonsole und in der Exchange-Verwaltungsshell (Exchange PowerShell) in der lokalen Exchange-Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="674f3-112">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="674f3-113">Anstatt die Nachrichten an den Junk-e-Mail-Ordner des lokalen Benutzers zu übermitteln, können Sie in EoP Antispam-Richtlinien konfigurieren, um Spamnachrichten in EoP zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="674f3-113">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="674f3-114">Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="674f3-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="674f3-115">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="674f3-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="674f3-116">Sie müssen Berechtigungen in der lokalen Exchange-Umgebung zugewiesen werden, bevor Sie diese Verfahren ausführen können.</span><span class="sxs-lookup"><span data-stu-id="674f3-116">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="674f3-117">Insbesondere müssen Sie die Rolle " **Transport Rules** " erhalten, die standardmäßig der Rollen " **Organisationsverwaltung**", " **Richtlinientreue Verwaltung**" und " **Datensatzverwaltung** " zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="674f3-117">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="674f3-118">Weitere Informationen finden Sie unter [Hinzufügen von Mitgliedern zu einer Rollengruppe](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span><span class="sxs-lookup"><span data-stu-id="674f3-118">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="674f3-119">Wenn eine Nachricht an den Junk-e-Mail-Ordner in einer lokalen Exchange-Organisation übermittelt wird, wird durch eine Kombination der folgenden Einstellungen gesteuert:</span><span class="sxs-lookup"><span data-stu-id="674f3-119">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="674f3-120">Der Wert des _SCLJunkThreshold_ -Parameters im Cmdlet " [OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) " in der Exchange-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="674f3-120">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="674f3-121">Der Standardwert ist 4, was bedeutet, dass ein SCL von 5 oder höher die Nachricht an den Junk-e-Mail-Ordner des Benutzers übermitteln soll.</span><span class="sxs-lookup"><span data-stu-id="674f3-121">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="674f3-122">Der Wert des _SCLJunkThreshold_ -Parameters im Cmdlet "Set [-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) " im Exchange-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="674f3-122">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="674f3-123">Der Standardwert ist leer ($null), was bedeutet, dass die Organisations Einstellung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="674f3-123">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="674f3-124">Ausführliche Informationen finden Sie unter [Exchange Spam Confidence Level (SCL) Schwellenwerte](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span><span class="sxs-lookup"><span data-stu-id="674f3-124">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="674f3-125">Gibt an, ob die Junk-e-Mail-Regel für das Postfach aktiviert ist (der Parameterwert _Enabled_ ist $true im Cmdlet " [MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) " im Exchange-Verwaltungsshell).</span><span class="sxs-lookup"><span data-stu-id="674f3-125">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="674f3-126">Es handelt sich um die Junk-e-Mail-Regel, die die Nachricht nach der Zustellung in den Junk-e-Mail-Ordner verschiebt.</span><span class="sxs-lookup"><span data-stu-id="674f3-126">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="674f3-127">Standardmäßig ist die Junk-e-Mail-Regel für Postfächer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="674f3-127">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="674f3-128">Weitere Informationen finden Sie unter [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span><span class="sxs-lookup"><span data-stu-id="674f3-128">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>
  
- <span data-ttu-id="674f3-129">Informationen zum Öffnen des EAC auf einem Exchange Server finden Sie unter [Exchange Admin Center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="674f3-129">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="674f3-130">Informationen zum Öffnen des Exchange-Verwaltungsshell finden [https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)Sie unter.</span><span class="sxs-lookup"><span data-stu-id="674f3-130">To open the Exchange Management Shell, see [https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="674f3-131">Weitere Informationen zu Nachrichtenfluss Regeln in lokalen Exchange finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="674f3-131">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="674f3-132">Nachrichtenfluss Regeln in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="674f3-132">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="674f3-133">Nachrichtenfluss Regel-Bedingungen und-Ausnahmen (Prädikate) in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="674f3-133">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="674f3-134">Aktionen für Nachrichtenfluss Regeln in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="674f3-134">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="674f3-135">Verwenden der Exchange-Verwaltungskonsole zum Erstellen von Nachrichtenfluss Regeln zum Festlegen der SCL-Bewertung von EoP-Spamnachrichten</span><span class="sxs-lookup"><span data-stu-id="674f3-135">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="674f3-136">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.</span><span class="sxs-lookup"><span data-stu-id="674f3-136">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="674f3-137">Klicken Sie auf Add](../../media/ITPro-EAC-AddIcon.png) -Symbol **Hinzufügen** ![, und wählen Sie in der angezeigten Dropdownliste **neue Regel erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="674f3-137">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="674f3-138">Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="674f3-138">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="674f3-139">**Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="674f3-139">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="674f3-140">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="674f3-140">For example:</span></span>

     - <span data-ttu-id="674f3-141">EoP SFV: SPM zu SCL-Bewertung 6</span><span class="sxs-lookup"><span data-stu-id="674f3-141">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="674f3-142">EoP SFV: SKS zu SCL-Bewertung 6</span><span class="sxs-lookup"><span data-stu-id="674f3-142">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="674f3-143">EoP SFV: SKB to SCL 6</span><span class="sxs-lookup"><span data-stu-id="674f3-143">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="674f3-144">Klicken Sie auf **Weitere Optionen**.</span><span class="sxs-lookup"><span data-stu-id="674f3-144">Click **More Options**.</span></span>

   - <span data-ttu-id="674f3-145">**Diese Regel anwenden, wenn**: Wählen Sie **einen Nachrichtenkopf** \> **mit einem beliebigen dieser Wörter**aus.</span><span class="sxs-lookup"><span data-stu-id="674f3-145">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="674f3-146">Führen Sie in der **Kopfzeile Text eingeben** die folgenden Schritte aus, um Wörter Satz eingeben, der angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="674f3-146">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="674f3-147">Klicken Sie auf **Text eingeben**.</span><span class="sxs-lookup"><span data-stu-id="674f3-147">Click **Enter text**.</span></span> <span data-ttu-id="674f3-148">Geben Sie im angezeigten Dialogfeld **Kopfzeile angeben** den Namen **X-Forefront-Antispam-Report** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="674f3-148">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="674f3-149">Klicken Sie auf **Wörter eingeben**.</span><span class="sxs-lookup"><span data-stu-id="674f3-149">Click  **Enter words**.</span></span> <span data-ttu-id="674f3-150">Geben Sie im daraufhin angezeigten Dialogfeld **Wörter oder Ausdrücke angeben** einen der EoP-Spam Headerwerte ein **(SFV: SPM**, **SFV: SKS**oder **SFV: SKB**), klicken Sie auf Add](../../media/ITPro-EAC-AddIcon.png)-Symbol **Hinzufügen** ![, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="674f3-150">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="674f3-151">**Gehen Sie folgen**dermaßen vor: Wählen Sie **ändern die Nachrichteneigenschaften** \> **Festlegen der SCL-Bewertung (Spam Confidence Level)**.</span><span class="sxs-lookup"><span data-stu-id="674f3-151">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="674f3-152">Wählen Sie im angezeigten **SCL** -Dialogfeld die Option **6** (der Standardwert ist **5**) aus.</span><span class="sxs-lookup"><span data-stu-id="674f3-152">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="674f3-153">Wenn Sie fertig sind, klicken Sie auf **Speichern**</span><span class="sxs-lookup"><span data-stu-id="674f3-153">When you're finished, click **Save**</span></span>

<span data-ttu-id="674f3-154">Wiederholen Sie diese Schritte für die restlichen EoP-Spam Urteils Werte (**SFV: SPM**, **SFV: SKS**oder **SFV: SKB**).</span><span class="sxs-lookup"><span data-stu-id="674f3-154">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="674f3-155">Verwenden der Exchange-Verwaltungsshell zum Erstellen von Nachrichtenfluss Regeln, die die SCL-Bewertung von EoP-Spamnachrichten festlegen</span><span class="sxs-lookup"><span data-stu-id="674f3-155">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="674f3-156">Verwenden Sie die folgende Syntax, um die drei Nachrichtenfluss Regeln zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="674f3-156">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="674f3-157">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="674f3-157">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="674f3-158">Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="674f3-158">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="674f3-159">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="674f3-159">How do you know this worked?</span></span>

<span data-ttu-id="674f3-160">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie den eigenständigen EoP erfolgreich für die Zustellung von Spam an den Junk-e-Mail-Ordner in einer Hybridumgebung konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="674f3-160">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="674f3-161">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**, wählen Sie die Regel aus, und](../../media/ITPro-EAC-EditIcon.png) klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![, um die Einstellungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="674f3-161">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="674f3-162">Ersetzen \<Sie in der Exchange-Verwaltungsshell Regelname\> durch den Namen der Nachrichtenfluss Regel, und Regel Sie den folgenden Befehl, um die Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="674f3-162">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="674f3-163">Senden Sie in einem externen e-Mail-System **, das ausgehende Nachrichten nicht nach Spam scannt**, einen generischen Test für unangeforderte Massen-e-Mail (GTUBE) an einen betroffenen Empfänger, und vergewissern Sie sich, dass er an den Junk-e-Mail-Ordner gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="674f3-163">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="674f3-164">Eine GTUBE-Nachricht ähnelt der EICAR-Textdatei (European Institute for Computer Antivirus Research) zum Testen der Schadsoftwareeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="674f3-164">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="674f3-165">Um eine GTUBE-Nachricht zu senden, fügen Sie den folgenden Text in den Textkörper einer e-Mail-Nachricht in einer einzelnen Zeile ohne Leerzeichen oder Zeilenumbrüche ein:</span><span class="sxs-lookup"><span data-stu-id="674f3-165">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
