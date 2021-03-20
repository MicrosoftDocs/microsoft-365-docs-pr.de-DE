---
title: Konfigurieren von EOP für Junkspam in Hybridumgebungen
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
description: Administratoren erfahren, wie Sie Spam an Junk-E-Mail-Ordner von Benutzern in einer Exchange Online Protection-Hybridumgebung weiterrouten.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae6ee551d04b242891c9638d6d99d79240480d27
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910858"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="75a28-103">Konfigurieren von eigenständigem EOP zum Senden von Spam an den Junk-E-Mail-Ordner in Hybridumgebungen</span><span class="sxs-lookup"><span data-stu-id="75a28-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="75a28-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="75a28-104">**Applies to**</span></span>
-  [<span data-ttu-id="75a28-105">Exchange Online Protection eigenständig</span><span class="sxs-lookup"><span data-stu-id="75a28-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

> [!IMPORTANT]
> <span data-ttu-id="75a28-106">Dieses Thema gilt nur für eigenständige EOP-Kunden in Hybridumgebungen.</span><span class="sxs-lookup"><span data-stu-id="75a28-106">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="75a28-107">Dieses Thema gilt nicht für Microsoft 365-Kunden mit Exchange Online-Postfächern.</span><span class="sxs-lookup"><span data-stu-id="75a28-107">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="75a28-108">Wenn Sie ein eigenständiger Exchange Online Protection (EOP)-Kunde in einer Hybridumgebung sind, müssen Sie Ihre lokale Exchange-Organisation so konfigurieren, dass die Spamfilterungsbewertungen von EOP erkannt und übersetzt werden, damit die Junk-E-Mail-Regel im lokalen Postfach Nachrichten in den Junk-E-Mail-Ordner verschieben kann.</span><span class="sxs-lookup"><span data-stu-id="75a28-108">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="75a28-109">Insbesondere müssen Sie Nachrichtenflussregeln (auch als Transportregeln bekannt) in Ihrer lokalen Exchange-Organisation mit Bedingungen erstellen, die Nachrichten mit einem der folgenden EOP-Antispamkopfzeilen und -Werte finden, und Aktionen, die die Spamsicherheitsstufe (Spam Confidence Level, SCL) dieser Nachrichten auf 6 festlegen:</span><span class="sxs-lookup"><span data-stu-id="75a28-109">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="75a28-110">`X-Forefront-Antispam-Report: SFV:SPM` (Durch Spamfilterung als Spam markierte Nachricht)</span><span class="sxs-lookup"><span data-stu-id="75a28-110">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="75a28-111">`X-Forefront-Antispam-Report: SFV:SKS` (nachricht marked as spam by mail flow rules in EOP before spam filtering)</span><span class="sxs-lookup"><span data-stu-id="75a28-111">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="75a28-112">`X-Forefront-Antispam-Report: SFV:SKB` (nachricht marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span><span class="sxs-lookup"><span data-stu-id="75a28-112">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="75a28-113">Weitere Informationen zu diesen Headerwerten finden Sie unter [Antispamnachrichtenkopfzeilen](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="75a28-113">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="75a28-114">In diesem Thema wird beschrieben, wie Sie diese Nachrichtenflussregeln im Exchange Admin Center (EAC) und in der Exchange-Verwaltungsshell (Exchange PowerShell) in der lokalen Exchange-Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="75a28-114">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="75a28-115">Anstatt die Nachrichten an den Junk-E-Mail-Ordner des lokalen Benutzers zu senden, können Sie Antispamrichtlinien in EOP konfigurieren, um Spamnachrichten in EOP zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="75a28-115">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="75a28-116">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="75a28-116">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="75a28-117">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="75a28-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="75a28-118">Bevor Sie diese Verfahren tun können, müssen Ihnen in der lokalen Exchange-Umgebung berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="75a28-118">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="75a28-119">Insbesondere muss Ihnen die Rolle **Transportregeln** zugewiesen werden, die standardmäßig den Rollen **Organisationsverwaltung,** **Complianceverwaltung** und **Datensatzverwaltung** zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="75a28-119">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="75a28-120">Weitere Informationen finden Sie unter [Hinzufügen von Mitgliedern zu einer Rollengruppe](/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span><span class="sxs-lookup"><span data-stu-id="75a28-120">For more information, see [Add members to a role group](/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="75a28-121">Ob und wann eine Nachricht an den Junk-E-Mail-Ordner in einer lokalen Exchange-Organisation übermittelt wird, wird durch eine Kombination der folgenden Einstellungen gesteuert:</span><span class="sxs-lookup"><span data-stu-id="75a28-121">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="75a28-122">Der _SCLJunkThreshold-Parameterwert_ im [Cmdlet Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) in der Exchange-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="75a28-122">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="75a28-123">Der Standardwert ist 4, was bedeutet, dass eine SCL von 5 oder höher die Nachricht an den Junk-E-Mail-Ordner des Benutzers senden sollte.</span><span class="sxs-lookup"><span data-stu-id="75a28-123">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="75a28-124">Der _SCLJunkThreshold-Parameterwert_ im [Cmdlet Set-Mailbox](/powershell/module/exchange/set-mailbox) in der Exchange-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="75a28-124">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="75a28-125">Der Standardwert ist leer ($null), was bedeutet, dass die Organisationseinstellung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="75a28-125">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="75a28-126">Weitere Informationen finden Sie unter [Exchange Spam Confidence Level (SCL) thresholds](/Exchange/antispam-and-antimalware/antispam-protection/scl).</span><span class="sxs-lookup"><span data-stu-id="75a28-126">For details, see [Exchange spam confidence level (SCL) thresholds](/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="75a28-127">Gibt an, ob die Junk-E-Mail-Regel für das Postfach aktiviert ist (der Wert des Parameters _Enabled_ $true im [Cmdlet Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) in der Exchange-Verwaltungsshell).</span><span class="sxs-lookup"><span data-stu-id="75a28-127">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="75a28-128">Es ist die Junk-E-Mail-Regel, die die Nachricht nach der Zustellung in den Junk-E-Mail-Ordner verschiebt.</span><span class="sxs-lookup"><span data-stu-id="75a28-128">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="75a28-129">Standardmäßig ist die Junk-E-Mail-Regel für Postfächer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="75a28-129">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="75a28-130">Weitere Informationen finden Sie unter [Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span><span class="sxs-lookup"><span data-stu-id="75a28-130">For more information, see [Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="75a28-131">Informationen zum Öffnen der EAC auf einem Exchange Server finden Sie unter [Exchange Admin Center in Exchange Server](/Exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="75a28-131">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="75a28-132">Informationen zum Öffnen der Exchange-Verwaltungsshell finden Sie unter [Öffnen der Exchange-Verwaltungsshell](/powershell/exchange/open-the-exchange-management-shell).</span><span class="sxs-lookup"><span data-stu-id="75a28-132">To open the Exchange Management Shell, see [Open the Exchange Management Shell](/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="75a28-133">Weitere Informationen zu Nachrichtenflussregeln in lokalen Exchange finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="75a28-133">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="75a28-134">E-Mail-Flussregeln in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="75a28-134">Mail flow rules in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="75a28-135">Nachrichtenflussregelbedingungen und Ausnahmen (Prädikate) in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="75a28-135">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="75a28-136">Nachrichtenflussregelaktionen in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="75a28-136">Mail flow rule actions in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="75a28-137">Erstellen von Nachrichtenflussregeln, die die SCL von EOP-Spamnachrichten festlegen, mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="75a28-137">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="75a28-138">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.</span><span class="sxs-lookup"><span data-stu-id="75a28-138">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="75a28-139">Klicken **Sie auf** Hinzufügen ![ (Symbol) und wählen Sie in der ](../../media/ITPro-EAC-AddIcon.png) **angezeigten** Dropdownliste Neue Regel erstellen aus.</span><span class="sxs-lookup"><span data-stu-id="75a28-139">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="75a28-140">Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="75a28-140">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="75a28-141">**Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="75a28-141">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="75a28-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="75a28-142">For example:</span></span>

     - <span data-ttu-id="75a28-143">EOP SFV:SPM zu SCL 6</span><span class="sxs-lookup"><span data-stu-id="75a28-143">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="75a28-144">EOP SFV:SKS zu SCL 6</span><span class="sxs-lookup"><span data-stu-id="75a28-144">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="75a28-145">EOP SFV:SKB zu SCL 6</span><span class="sxs-lookup"><span data-stu-id="75a28-145">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="75a28-146">Klicken Sie auf **Weitere Optionen**.</span><span class="sxs-lookup"><span data-stu-id="75a28-146">Click **More Options**.</span></span>

   - <span data-ttu-id="75a28-147">**Wenden Sie diese Regel an,** wenn : Select **A message header** eines der folgenden Wörter \> **enthält.**</span><span class="sxs-lookup"><span data-stu-id="75a28-147">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="75a28-148">Gehen Sie **in der Eingabetextkopfzeile mit dem angezeigten** Satz "Wörter eingeben" wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="75a28-148">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="75a28-149">Klicken Sie **auf Text eingeben.**</span><span class="sxs-lookup"><span data-stu-id="75a28-149">Click **Enter text**.</span></span> <span data-ttu-id="75a28-150">Geben Sie **im angezeigten** Dialogfeld Kopfzeilennamen angeben **X-Forefront-Antispam-Report** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="75a28-150">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="75a28-151">Klicken  **Sie auf Wörter eingeben**.</span><span class="sxs-lookup"><span data-stu-id="75a28-151">Click  **Enter words**.</span></span> <span data-ttu-id="75a28-152">Geben  Sie im angezeigten Dialogfeld Wörter oder Ausdrücke angeben einen der EOP-Spamheaderwerte ein (**SFV:SPM**, **SFV:SKS** oder **SFV:SKB**), klicken Sie auf Hinzufügen  ![ (Symbol) und dann ](../../media/ITPro-EAC-AddIcon.png) auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="75a28-152">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="75a28-153">**Gehen Sie wie folgt** vor: Wählen Sie **Nachrichteneigenschaften ändern Festlegen** der Spamsicherheitsstufe \> **(Spam Confidence Level, SCL) aus.**</span><span class="sxs-lookup"><span data-stu-id="75a28-153">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="75a28-154">Wählen Sie **im angezeigten** Dialogfeld SCL angeben die Option **6** aus (der Standardwert ist **5**).</span><span class="sxs-lookup"><span data-stu-id="75a28-154">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="75a28-155">Klicken Sie nach Abschluss des Abschlusses auf **Speichern.**</span><span class="sxs-lookup"><span data-stu-id="75a28-155">When you're finished, click **Save**</span></span>

<span data-ttu-id="75a28-156">Wiederholen Sie diese Schritte für die verbleibenden EOP-Spam-Verdict-Werte (**SFV:SPM**, **SFV:SKS** oder **SFV:SKB**).</span><span class="sxs-lookup"><span data-stu-id="75a28-156">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="75a28-157">Verwenden der Exchange-Verwaltungsshell zum Erstellen von Nachrichtenflussregeln, die die SCL von EOP-Spamnachrichten festlegen</span><span class="sxs-lookup"><span data-stu-id="75a28-157">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="75a28-158">Verwenden Sie die folgende Syntax, um die drei Nachrichtenflussregeln zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="75a28-158">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="75a28-159">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="75a28-159">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="75a28-160">Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="75a28-160">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="75a28-161">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="75a28-161">How do you know this worked?</span></span>

<span data-ttu-id="75a28-162">Gehen Sie wie folgt vor, um zu überprüfen, ob Sie die eigenständige EOP erfolgreich konfiguriert haben, um Spam an den Junk-E-Mail-Ordner in der Hybridumgebung zu senden:</span><span class="sxs-lookup"><span data-stu-id="75a28-162">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="75a28-163">Wechseln Sie in der EAC zu **Nachrichtenflussregeln,** wählen Sie die Regel aus, und klicken Sie dann auf Bearbeiten (Symbol bearbeiten), \> um die Einstellungen  ![ zu ](../../media/ITPro-EAC-EditIcon.png) überprüfen.</span><span class="sxs-lookup"><span data-stu-id="75a28-163">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="75a28-164">Ersetzen Sie in der Exchange-Verwaltungsshell durch den Namen der Nachrichtenflussregel, und geben Sie den folgenden Befehl zurück, um \<RuleName\> die Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="75a28-164">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="75a28-165">Senden Sie in einem externen E-Mail-System, das ausgehende Nachrichten nicht auf Spam scannt, eine allgemeine Testnachricht für unaufgeforderte Massen-E-Mails (GTUBE) an einen betroffenen Empfänger, und vergewissern Sie sich, dass sie an ihren Junk-E-Mail-Ordner zugestellt wird.</span><span class="sxs-lookup"><span data-stu-id="75a28-165">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="75a28-166">Eine GTUBE-Nachricht ähnelt der EICAR-Textdatei (European Institute for Computer Antivirus Research) zum Testen der Schadsoftwareeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="75a28-166">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="75a28-167">Um eine GTUBE-Nachricht zu senden, fügen Sie den folgenden Text in den Textkörper einer E-Mail-Nachricht in einer einzigen Zeile ein, ohne Leerzeichen oder Zeilenumbrüche:</span><span class="sxs-lookup"><span data-stu-id="75a28-167">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```