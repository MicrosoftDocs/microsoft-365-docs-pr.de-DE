---
title: Konfigurieren von EOP für Junk-Spam in Hybridumgebungen
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Spam an Junk-E-Mail-Ordner von Benutzern in einer Exchange Online Protection-Hybridumgebung um routen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b8fbc1b065e348f759806d80fd85421eb9d66098
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288873"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="fe826-103">Konfigurieren von EOP für die Bereitstellung von Spam an den Junk-E-Mail-Ordner in Hybridumgebungen</span><span class="sxs-lookup"><span data-stu-id="fe826-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fe826-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="fe826-104">**Applies to**</span></span>
-  [<span data-ttu-id="fe826-105">Exchange Online Protection als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="fe826-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

> [!IMPORTANT]
> <span data-ttu-id="fe826-106">Dieses Thema ist nur für Kunden mit eigenständigem EOP in Hybridumgebungen geeignet.</span><span class="sxs-lookup"><span data-stu-id="fe826-106">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="fe826-107">Dieses Thema gilt nicht für Microsoft 365-Kunden mit Exchange Online-Postfächern.</span><span class="sxs-lookup"><span data-stu-id="fe826-107">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="fe826-108">Wenn Sie ein eigenständiger Exchange Online Protection (EOP)-Kunde in einer Hybridumgebung sind, müssen Sie Ihre lokale Exchange-Organisation so konfigurieren, dass die Spamfilterbewertungen von EOP erkannt und übersetzt werden, damit die Junk-E-Mail-Regel im lokalen Postfach Nachrichten in den Junk-E-Mail-Ordner verschieben kann.</span><span class="sxs-lookup"><span data-stu-id="fe826-108">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="fe826-109">Insbesondere müssen Sie Nachrichtenflussregeln (auch als Transportregeln bekannt) in Ihrer lokalen Exchange-Organisation mit Bedingungen erstellen, die Nachrichten mit einem der folgenden EOP-Antispamheader und -Werte finden, und Aktionen, die den SCL (Spam Confidence Level) dieser Nachrichten auf 6 festlegen:</span><span class="sxs-lookup"><span data-stu-id="fe826-109">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="fe826-110">`X-Forefront-Antispam-Report: SFV:SPM` (Nachricht, die von der Spamfilterung als Spam gekennzeichnet wurde)</span><span class="sxs-lookup"><span data-stu-id="fe826-110">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="fe826-111">`X-Forefront-Antispam-Report: SFV:SKS` (nachricht marked as spam by mail flow rules in EOP before spam filtering)</span><span class="sxs-lookup"><span data-stu-id="fe826-111">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="fe826-112">`X-Forefront-Antispam-Report: SFV:SKB` (Nachricht, die von der Spamfilterung als Spam gekennzeichnet wurde, weil die E-Mail-Adresse oder E-Mail-Domäne des Absenders in der Liste blockierter Absender oder der Liste blockierter Domänen in EOP enthalten ist)</span><span class="sxs-lookup"><span data-stu-id="fe826-112">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="fe826-113">Weitere Informationen zu diesen Kopfzeilenwerten finden Sie unter ["Antispam-Nachrichtenkopfzeilen".](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="fe826-113">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="fe826-114">In diesem Thema wird beschrieben, wie Sie diese Nachrichtenflussregeln im Exchange Admin Center (EAC) und in der Exchange-Verwaltungsshell (Exchange PowerShell) in der lokalen Exchange-Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="fe826-114">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="fe826-115">Anstatt die Nachrichten an den Junk-E-Mail-Ordner des lokalen Benutzers zu senden, können Sie Antispamrichtlinien in EOP konfigurieren, um Spamnachrichten in EOP zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="fe826-115">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="fe826-116">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fe826-116">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fe826-117">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="fe826-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fe826-118">Bevor Sie diese Verfahren verwenden können, müssen Ihnen in der lokalen Exchange-Umgebung Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="fe826-118">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="fe826-119">Insbesondere muss Ihnen die Rolle **"Transportregeln"** zugewiesen werden, die standardmäßig  den Rollen **"Organisationsverwaltung",** **"Kompatibilitätsverwaltung"** und "Datensatzverwaltung" zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="fe826-119">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="fe826-120">Weitere Informationen finden Sie unter [Hinzufügen von Mitgliedern zu einer Rollengruppe.](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group)</span><span class="sxs-lookup"><span data-stu-id="fe826-120">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="fe826-121">Ob und wann eine Nachricht an den Junk-E-Mail-Ordner in einer lokalen Exchange-Organisation zugestellt wird, wird durch eine Kombination der folgenden Einstellungen gesteuert:</span><span class="sxs-lookup"><span data-stu-id="fe826-121">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="fe826-122">Der _Wert des Parameters "SCLJunkThreshold"_ im Cmdlet ["Set-OrganizationConfig"](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) in der Exchange-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="fe826-122">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="fe826-123">Der Standardwert ist 4, was bedeutet, dass ein SCL von 5 oder höher die Nachricht an den Junk-E-Mail-Ordner des Benutzers senden sollte.</span><span class="sxs-lookup"><span data-stu-id="fe826-123">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="fe826-124">Der _Wert des Parameters "SCLJunkThreshold"_ im Cmdlet ["Set-Mailbox"](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) in der Exchange-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="fe826-124">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="fe826-125">Der Standardwert ist leer ($null), was bedeutet, dass die Organisationseinstellung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fe826-125">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="fe826-126">Weitere Informationen finden Sie unter [SCL (Spam Confidence Level) Schwellenwerte](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)für Exchange.</span><span class="sxs-lookup"><span data-stu-id="fe826-126">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="fe826-127">Gibt an, ob die Junk-E-Mail-Regel für das Postfach aktiviert ist (der Wert des Parameters _"Enabled"_ $true im Cmdlet ["Set-MailboxJunkEmailConfiguration"](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) in der Exchange-Verwaltungsshell).</span><span class="sxs-lookup"><span data-stu-id="fe826-127">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="fe826-128">Es ist die Junk-E-Mail-Regel, die die Nachricht nach der Zustellung tatsächlich in den Junk-E-Mail-Ordner verschiebt.</span><span class="sxs-lookup"><span data-stu-id="fe826-128">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="fe826-129">Standardmäßig ist die Junk-E-Mail-Regel für Postfächer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fe826-129">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="fe826-130">Weitere Informationen finden Sie unter [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span><span class="sxs-lookup"><span data-stu-id="fe826-130">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="fe826-131">Informationen zum Öffnen der EAC auf einem Exchange Server finden Sie im [Exchange Admin Center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="fe826-131">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="fe826-132">Informationen zum Öffnen der Exchange-Verwaltungsshell finden Sie unter [Öffnen der Exchange-Verwaltungsshell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span><span class="sxs-lookup"><span data-stu-id="fe826-132">To open the Exchange Management Shell, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="fe826-133">Weitere Informationen zu Nachrichtenflussregeln im lokalen Exchange finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="fe826-133">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="fe826-134">Nachrichtenflussregeln in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="fe826-134">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="fe826-135">Nachrichtenflussregelbedingungen und -ausnahmen (Prädikate) in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="fe826-135">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="fe826-136">Nachrichtenflussregelaktionen in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="fe826-136">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="fe826-137">Erstellen von Nachrichtenflussregeln, die den SCL von EOP-Spamnachrichten festlegen, mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="fe826-137">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="fe826-138">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.</span><span class="sxs-lookup"><span data-stu-id="fe826-138">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="fe826-139">Klicken **Sie auf das** Symbol ![ "Hinzufügen", und wählen Sie in der angezeigten Dropdownliste "Neue Regel ](../../media/ITPro-EAC-AddIcon.png) erstellen" aus. </span><span class="sxs-lookup"><span data-stu-id="fe826-139">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="fe826-140">Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="fe826-140">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="fe826-141">**Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="fe826-141">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="fe826-142">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fe826-142">For example:</span></span>

     - <span data-ttu-id="fe826-143">EOP SFV:SPM zu SCL 6</span><span class="sxs-lookup"><span data-stu-id="fe826-143">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="fe826-144">EOP SFV:SKS zu SCL 6</span><span class="sxs-lookup"><span data-stu-id="fe826-144">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="fe826-145">EOP SFV:SKB zu SCL 6</span><span class="sxs-lookup"><span data-stu-id="fe826-145">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="fe826-146">Klicken Sie auf **Weitere Optionen**.</span><span class="sxs-lookup"><span data-stu-id="fe826-146">Click **More Options**.</span></span>

   - <span data-ttu-id="fe826-147">**Wenden Sie diese Regel an, wenn**: Select **A message header** includes any of these \> **words**.</span><span class="sxs-lookup"><span data-stu-id="fe826-147">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="fe826-148">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span><span class="sxs-lookup"><span data-stu-id="fe826-148">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="fe826-149">Klicken Sie **auf "Text eingeben".**</span><span class="sxs-lookup"><span data-stu-id="fe826-149">Click **Enter text**.</span></span> <span data-ttu-id="fe826-150">Geben Sie **im angezeigten** Dialogfeld "Kopfzeilennamen angeben" **X-Forefront-Antispam-Report** ein, und klicken Sie dann auf **OK.**</span><span class="sxs-lookup"><span data-stu-id="fe826-150">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="fe826-151">Klicken **Sie auf "Wörter eingeben".**</span><span class="sxs-lookup"><span data-stu-id="fe826-151">Click  **Enter words**.</span></span> <span data-ttu-id="fe826-152">Geben  Sie im angezeigten Dialogfeld "Wörter oder Ausdrücke angeben" einen der EOP-Spamheaderwerte (**SFV:SPM**, **SFV:SKS** oder **SFV:SKB)** ein, klicken Sie auf "Hinzufügen" (Symbol) und dann auf  ![ ](../../media/ITPro-EAC-AddIcon.png) **"OK".**</span><span class="sxs-lookup"><span data-stu-id="fe826-152">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="fe826-153">**Gehen Sie wie folgt vor:** Wählen **Sie "Nachrichteneigenschaften** \> **ändern" aus, um die SCL (Spam Confidence Level) zu festlegen.**</span><span class="sxs-lookup"><span data-stu-id="fe826-153">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="fe826-154">Wählen Sie **im angezeigten Dialogfeld "SCL** angeben" **die Option 6** aus (der Standardwert ist **5**).</span><span class="sxs-lookup"><span data-stu-id="fe826-154">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="fe826-155">Wenn Sie fertig sind, klicken Sie auf **"Speichern".**</span><span class="sxs-lookup"><span data-stu-id="fe826-155">When you're finished, click **Save**</span></span>

<span data-ttu-id="fe826-156">Wiederholen Sie diese Schritte für die verbleibenden EOP-Spam-Werte (**SFV:SPM**, **SFV:SKS** oder **SFV:SKB**).</span><span class="sxs-lookup"><span data-stu-id="fe826-156">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="fe826-157">Verwenden der Exchange-Verwaltungsshell, um Nachrichtenflussregeln zu erstellen, die den SCL von EOP-Spamnachrichten festlegen</span><span class="sxs-lookup"><span data-stu-id="fe826-157">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="fe826-158">Verwenden Sie die folgende Syntax, um die drei Nachrichtenflussregeln zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="fe826-158">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="fe826-159">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fe826-159">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="fe826-160">Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="fe826-160">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="fe826-161">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="fe826-161">How do you know this worked?</span></span>

<span data-ttu-id="fe826-162">Gehen Sie wie folgt vor, um sicherzustellen, dass Sie EOP für die Bereitstellung von Spam an den Junk-E-Mail-Ordner in einer Hybridumgebung erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="fe826-162">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="fe826-163">Wechseln Sie in der EAC zu **"Nachrichtenflussregeln",** wählen Sie die Regel aus, und klicken Sie dann auf "Bearbeiten", um \> die Einstellungen  ![ zu ](../../media/ITPro-EAC-EditIcon.png) überprüfen.</span><span class="sxs-lookup"><span data-stu-id="fe826-163">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="fe826-164">Ersetzen Sie in der Exchange-Verwaltungsshell den Namen der Nachrichtenflussregel, und ruln Sie den folgenden Befehl, \<RuleName\> um die Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="fe826-164">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="fe826-165">Senden Sie in einem externen E-Mail-System, das ausgehende Nachrichten nicht auf Spam scannt, einen generischen Test auf junk-E-Mail (Junk-E-Mail) an einen betroffenen Empfänger, und vergewissern Sie sich, dass sie an ihren Junk-E-Mail-Ordner zugestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fe826-165">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="fe826-166">Eine GTUBE-Nachricht ähnelt der EICAR-Textdatei (European Institute for Computer Antivirus Research) zum Testen der Schadsoftwareeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="fe826-166">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="fe826-167">Um eine GTUBE-Nachricht zu senden, fügen Sie den folgenden Text in den Text einer E-Mail-Nachricht in einer zeile ohne Leerzeichen oder Zeilenumbrüche ein:</span><span class="sxs-lookup"><span data-stu-id="fe826-167">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
