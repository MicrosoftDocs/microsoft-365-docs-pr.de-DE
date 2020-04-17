---
title: Konfigurieren der standardmäßigen Antiphishing-Richtlinie in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren erfahren, wie Sie die Antispoofing-Einstellungen ändern können, die in der standardmäßigen Anti-Phishing-Richtlinie in Office 365 Organisationen mit Exchange Online Postfächern verfügbar sind.
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537533"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a><span data-ttu-id="d0c1d-103">Konfigurieren der standardmäßigen Antiphishing-Richtlinie in EOP</span><span class="sxs-lookup"><span data-stu-id="d0c1d-103">Configure the default anti-phishing policy in EOP</span></span>

<span data-ttu-id="d0c1d-104">Office 365 Organisationen mit Exchange Online Postfächern und eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer verfügen über eine Standard-Anti-Phishing-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have a default anti-phishing policy.</span></span> <span data-ttu-id="d0c1d-105">Diese Richtlinie enthält eine beschränkte Anzahl von Anti-Spoofing-Features, die standardmäßig aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-105">This policy contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="d0c1d-106">Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="d0c1d-106">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="d0c1d-107">Office 365 Organisationen mit Exchange Online Postfächern können die standardmäßige Anti-Phishing-Richtlinie im Office 365 Security & Compliance Center oder in Exchange Online PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-107">Office 365 organizations with Exchange Online mailboxes can modify the default anti-phishing policy in the Office 365 Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="d0c1d-108">Eigenständige EoP-Organisationen ohne Exchange Online Postfächer können Ihre standardmäßige Anti-Phishing-Richtlinie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-108">Standalone EOP organizations without Exchange Online mailboxes can't modify their default anti-phishing policy.</span></span>

<span data-ttu-id="d0c1d-109">Informationen zum Erstellen und Ändern der erweiterten ATP-Richtlinien für die Anti-Phishing, die in Office 365 Advanced Threat Protection verfügbar sind, finden Sie unter [configure ATP Anti-Phishing Policies in Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d0c1d-109">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d0c1d-110">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="d0c1d-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d0c1d-111">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d0c1d-112">Wenn Sie direkt zur Seite **Anti-Phishing** wechseln möchten, verwenden <https://protection.office.com/antiphishing>Sie.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-112">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="d0c1d-113">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d0c1d-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="d0c1d-114">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="d0c1d-115">Zum Hinzufügen, ändern und Löschen von Anti-Phishing-Richtlinien müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-115">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="d0c1d-116">Für den schreibgeschützten Zugriff auf Anti-Phishing-Richtlinien müssen Sie Mitglied der Rollengruppe **Sicherheits Leser** sein.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-116">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="d0c1d-117">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d0c1d-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="d0c1d-118">Unsere empfohlenen Einstellungen für die standardmäßige Anti-Phishing-Richtlinie finden Sie unter [EoP default Anti-Phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="d0c1d-118">For our recommended settings for the default anti-phishing policy, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="d0c1d-119">Lassen Sie bis zu 30 Minuten für die Anwendung der aktualisierten Richtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-119">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="d0c1d-120">Informationen dazu, wo Anti-Phishing-Richtlinien in der Filter Pipeline angewendet werden, finden Sie unter [Order and Ranges of Email Protection in Office 365](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="d0c1d-120">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="d0c1d-121">Verwenden des Security & Compliance Center zum Ändern der standardmäßigen Anti-Phishing-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="d0c1d-121">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="d0c1d-122">Die standardmäßige Anti-Phishing-Richtlinie heißt Office365 AntiPhishing Default, und Sie wird nicht in der Liste der Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-122">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="d0c1d-123">Führen Sie die folgenden Schritte aus, um die standardmäßige Anti-Phishing-Richtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="d0c1d-123">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="d0c1d-124">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d0c1d-125">Klicken Sie auf der Seite **Anti-Phishing** auf **Standardrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-125">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="d0c1d-126">Die **Standardseite Ihre Richtlinie Office365 AntiPhishing bearbeiten** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-126">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="d0c1d-127">Klicken Sie im Abschnitt **Spoof** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-127">In the **Spoof** section, click **Edit**.</span></span>

   <span data-ttu-id="d0c1d-128">Beachten Sie, dass diese Einstellungen mit den spoofeinstellungen identisch sind, die in den ATP-Richtlinien zum Schutz vor Phishing verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-128">Note that these settings are identical to the spoof settings that are available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="d0c1d-129">**Spoofing-Filtereinstellungen**: der Standardwert ist " **on**", und es wird empfohlen, dass Sie die Einstellung aktiviert lassen.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-129">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="d0c1d-130">Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus**.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-130">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="d0c1d-131">Weitere Informationen finden Sie unter [configure Spoof Intelligence in Office 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="d0c1d-131">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="d0c1d-132">Sie müssen den Schutz vor Spoofing nicht deaktivieren, wenn Ihr MX-Eintrag nicht auf Office 365 verweist; Stattdessen aktivieren Sie die erweiterte Filterung für Connectors.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-132">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="d0c1d-133">Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="d0c1d-133">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="d0c1d-134">Nicht **authentifizierte Absender Funktion aktivieren**: Fügt dem Foto des Absenders ein Fragezeichen hinzu, wenn die Nachricht e-Mail-Authentifizierungsprüfungen fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-134">**Enable Unauthenticated Sender feature**: Adds a question mark to the sender's photo if the message fails email authentication checks.</span></span> <span data-ttu-id="d0c1d-135">Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="d0c1d-135">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span> <span data-ttu-id="d0c1d-136">Der Standardwert ist **Aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-136">The default value is **On**.</span></span> <span data-ttu-id="d0c1d-137">Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus**.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-137">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="d0c1d-138">**Actions: geben**Sie die Aktion an, die für Nachrichten ausgeführt werden soll, die Spoof Intelligence nicht ausführen:</span><span class="sxs-lookup"><span data-stu-id="d0c1d-138">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="d0c1d-139">**Wenn e-Mails von Benutzern gesendet werden, die Ihre Domäne nicht spoofen dürfen**:</span><span class="sxs-lookup"><span data-stu-id="d0c1d-139">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="d0c1d-140">**Nachricht in die Junk-e-Mail-Ordner der Empfänger über** tragen (Dies ist der Standardwert).</span><span class="sxs-lookup"><span data-stu-id="d0c1d-140">**Move message to the recipients' Junk Email folders** (This is the default value.)</span></span>
     - <span data-ttu-id="d0c1d-141">**Nachricht isolieren**</span><span class="sxs-lookup"><span data-stu-id="d0c1d-141">**Quarantine the message**</span></span>

   - <span data-ttu-id="d0c1d-142">**Überprüfen Sie Ihre Einstellungen**: anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-142">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="d0c1d-143">Sie können in jedem Abschnitt auf **Bearbeiten** klicken, um zurück zur entsprechenden Seite zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-143">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="d0c1d-144">Sie können die **folgenden Einstellungen direkt auf dieser** Seite aktivieren oder **Deaktivieren** :</span><span class="sxs-lookup"><span data-stu-id="d0c1d-144">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="d0c1d-145">**Aktivieren von Schutz vor Spoofing**</span><span class="sxs-lookup"><span data-stu-id="d0c1d-145">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="d0c1d-146">**Nicht authentifizierte Absender Funktion aktivieren**</span><span class="sxs-lookup"><span data-stu-id="d0c1d-146">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="d0c1d-147">Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="d0c1d-147">When you're finished, click **Save** on any page.</span></span>

4. <span data-ttu-id="d0c1d-148">Überprüfen Sie die Einstellungen auf der **Standardseite Richtlinie Office365 bearbeiten** , und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-148">Back on the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a><span data-ttu-id="d0c1d-149">Verwenden des Security & Compliance Center zum Anzeigen der standardmäßigen Anti-Phishing-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="d0c1d-149">Use the Security & Compliance Center to view the default anti-phishing policy</span></span>

1. <span data-ttu-id="d0c1d-150">Im Security & Compliance Center und wechseln Sie zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-150">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="d0c1d-151">Klicken Sie auf **Standardrichtlinie** , um die standardmäßige Anti-Phishing-Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-151">Click **Default policy** to view the default anti-phishing policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a><span data-ttu-id="d0c1d-152">Konfigurieren der standardmäßigen Anti-Phishing-Richtlinie mithilfe Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0c1d-152">Use Exchange Online PowerShell to configure the default anti-phishing policy</span></span>

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a><span data-ttu-id="d0c1d-153">Verwenden von PowerShell zum Anzeigen der standardmäßigen Anti-Phishing-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="d0c1d-153">Use PowerShell to view the default anti-phish policy</span></span>

<span data-ttu-id="d0c1d-154">Führen Sie den folgenden Befehl aus, um die standardmäßige Anti-Phishing-Richtlinie anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="d0c1d-154">To view the default anti-phish policy, run the following command:</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

<span data-ttu-id="d0c1d-155">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="d0c1d-155">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a><span data-ttu-id="d0c1d-156">Verwenden von PowerShell zum Ändern der standardmäßigen Anti-Phishing-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="d0c1d-156">Use PowerShell to modify the default anti-phish policy</span></span>

<span data-ttu-id="d0c1d-157">Verwenden Sie die folgende Syntax, um die standardmäßige Anti-Phishing-Richtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="d0c1d-157">To modify the default anti-phish policy, use the following syntax:</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="d0c1d-158">In diesem Beispiel wird die Aktion für gefälschte Nachrichten geändert, bei denen die Authentifizierung nicht in Quarantäne überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-158">This example changes the action for spoofed messages that fail authentication checks to quarantine.</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="d0c1d-159">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="d0c1d-159">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d0c1d-160">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="d0c1d-160">How do you know these procedures worked?</span></span>

<span data-ttu-id="d0c1d-161">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie die standardmäßige Anti-Phishing-Richtlinie erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="d0c1d-161">To verify that you've successfully configured the default anti-phishing policy, do any of the following steps:</span></span>

- <span data-ttu-id="d0c1d-162">Wechseln \> Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing** klicken Sie auf **Standardrichtlinie** , und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-162">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="d0c1d-163">Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, und überprüfen Sie die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="d0c1d-163">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
