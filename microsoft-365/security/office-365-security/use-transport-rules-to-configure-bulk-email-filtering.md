---
title: Verwenden von Nachrichtenfluss Regeln zum Filtern von Massen-e-Mails in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Nachrichtenfluss Regeln in Exchange Online Protection (EoP) für die Massen-e-Mail-Filterung verwenden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 43a10951a24ac76108fb0531f9e2c205c3fc9047
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034974"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a><span data-ttu-id="03adb-103">Verwenden von Nachrichtenfluss Regeln zum Filtern von Massen-e-Mails in Office 365</span><span class="sxs-lookup"><span data-stu-id="03adb-103">Use mail flow rules to filter bulk email in Office 365</span></span>

<span data-ttu-id="03adb-104">Wenn Sie ein Microsoft 365-Kunde mit Postfächern in Exchange Online oder einem eigenständigen Exchange Online Schutz-Kunden (EoP) ohne Exchange Online Postfächer sind, verwendet EoP Antispam-Richtlinien (auch bekannt als Spamfilter-oder Inhaltsfilter Richtlinien), um eingehende Nachrichten für Spam und Massen-e-Mails zu scannen (auch als graue e-Mail bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="03adb-104">If you're an Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="03adb-105">Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="03adb-105">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="03adb-106">Wenn Sie weitere Optionen zum Filtern von Massen-e-Mails wünschen, können Sie Nachrichtenfluss Regeln (auch bekannt als Transportregeln) erstellen, um nach Textmustern oder Ausdrücken zu suchen, die häufig in Massen-e-Mails gefunden werden, und diese Nachrichten als Spam markieren.</span><span class="sxs-lookup"><span data-stu-id="03adb-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="03adb-107">Weitere Informationen zu Massen-e-Mails finden Sie unter [Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mail? und der](what-s-the-difference-between-junk-email-and-bulk-email.md) [Massen Reklamations Stufe (BCL) in Office 365](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="03adb-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="03adb-108">In diesem Thema wird erläutert, wie diese Nachrichtenfluss Regeln in der Exchange-Verwaltungskonsole (EAC) und PowerShell (Exchange Online PowerShell für Microsoft 365-Kunden erstellt werden; Exchange Online Protection PowerShell für eigenständige EoP-Kunden).</span><span class="sxs-lookup"><span data-stu-id="03adb-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="03adb-109">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="03adb-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="03adb-110">Sie müssen Berechtigungen in Exchange Online zugewiesen werden, bevor Sie diese Verfahren ausführen können.</span><span class="sxs-lookup"><span data-stu-id="03adb-110">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="03adb-111">Insbesondere müssen Sie die Rolle " **Transport Rules** " erhalten, die standardmäßig der Rollen " **Organisationsverwaltung**", " **Richtlinientreue Verwaltung**" und " **Datensatzverwaltung** " zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="03adb-111">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="03adb-112">Weitere Informationen finden Sie unter [Verwalten von Rollengruppen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="03adb-112">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="03adb-113">Informationen zum Öffnen des EAC in Exchange Online finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="03adb-113">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="03adb-114">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="03adb-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="03adb-115">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="03adb-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="03adb-116">Weitere Informationen zu Nachrichtenfluss Regeln in Exchange Online und eigenständigen EoP finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="03adb-116">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="03adb-117">Nachrichtenflussregeln (Transportregeln) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="03adb-117">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="03adb-118">Nachrichtenflussregel-Bedingungen und -Ausnahmen (Prädikate) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="03adb-118">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="03adb-119">Aktionen für Nachrichtenflussregeln in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="03adb-119">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="03adb-120">Die Liste der Wörter und Textmuster, die zum Identifizieren von Massennachrichten in den Beispielen verwendet werden, sind nicht erschöpfend; Sie können Einträge bei Bedarf hinzufügen und entfernen.</span><span class="sxs-lookup"><span data-stu-id="03adb-120">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="03adb-121">Sie sind jedoch ein guter Ausgangspunkt.</span><span class="sxs-lookup"><span data-stu-id="03adb-121">However, they are a good starting point.</span></span>

- <span data-ttu-id="03adb-p106">Die Suche nach Wörtern oder Textmustern im Betreff oder anderen Kopfzeilenfeldern in der Nachricht tritt *nach* der Decodierung der Nachricht aus der MIME-Inhaltsübertragungscodierungsmethode ein, die für die Übermittlung der binären Nachricht zwischen SMTP-Servern im ASCII-Text verwendet wurde. Sie können keine Bedingungen oder Ausnahmen für die Suche nach Rohwerten (in der Regel Base64-codiert) im Betreff oder in anderen Kopfzeilenfeldern in Nachrichten verwenden.</span><span class="sxs-lookup"><span data-stu-id="03adb-p106">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="03adb-124">Die folgenden Verfahren kennzeichnen eine Massen Nachricht als Spam für Ihre gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="03adb-124">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="03adb-125">Sie können jedoch eine weitere Bedingung hinzufügen, um diese Regeln nur auf bestimmte Empfänger anzuwenden, sodass Sie eine aggressive Filterung für einige wenige, sehr gezielte Benutzer verwenden können, während die restlichen Benutzer (die meistens die Massen-e-Mails erhalten, für die Sie sich angemeldet haben) nicht betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="03adb-125">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="03adb-126">Verwenden der Exchange-Verwaltungskonsole zum Erstellen von Nachrichtenfluss Regeln zum Filtern von Massen-e-Mails</span><span class="sxs-lookup"><span data-stu-id="03adb-126">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="03adb-127">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.</span><span class="sxs-lookup"><span data-stu-id="03adb-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="03adb-128">Klicken Sie auf Add](../../media/ITPro-EAC-AddIcon.png) -Symbol **Hinzufügen** ![, und wählen Sie dann **neue Regel erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="03adb-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="03adb-129">Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="03adb-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="03adb-130">**Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="03adb-130">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="03adb-131">Klicken Sie auf **Weitere Optionen**.</span><span class="sxs-lookup"><span data-stu-id="03adb-131">Click **More Options**.</span></span>

   - <span data-ttu-id="03adb-132">**Diese Regel anwenden, wenn**: eine der folgenden Einstellungen zum Suchen nach Inhalten in Nachrichten mithilfe regulärer Ausdrücke (Regex) oder Wörtern oder Ausdrücken konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="03adb-132">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="03adb-133">**Der Betreff oder** \> Textkörper des Unternehmens **entspricht diesen Textmustern**: Geben Sie im angezeigten Dialogfeld **Wörter oder Ausdrücke angeben** einen der folgenden Werte ein, klicken Sie](../../media/ITPro-EAC-AddIcon.png)auf Add-Symbol **Hinzufügen** ![, und wiederholen Sie diese Schritte, bis Sie alle Werte eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="03adb-133">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`

       - `\>(safe )?unsubscribe( here)?\</a\>`

       - `If you do not wish to receive further communications like this\, please`

       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`

       - `To stop receiving these+emails\:http\://`

       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`

       - `no longer (wish )?(to )?(be sent|receive) w+ email`

       - `If you are unable to view the content of this email\, please click here`

       - `To ensure you receive (your daily deals|our e-?mails)\, add`

       - `If you no longer wish to receive these emails`

       - `to change your (subscription preferences|preferences or unsubscribe)`

       - `click (here to|the) unsubscribe`

      <span data-ttu-id="03adb-134">Um einen Eintrag zu bearbeiten, wählen Sie ihn **Edit** ![aus, und](../../media/ITPro-EAC-EditIcon.png)klicken Sie auf Bearbeitungssymbol bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="03adb-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="03adb-135">Um einen Eintrag zu entfernen, wählen Sie ihn **Remove** ![aus, und](../../media/ITPro-EAC-DeleteIcon.png)klicken Sie auf entfernen-Symbol entfernen.</span><span class="sxs-lookup"><span data-stu-id="03adb-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="03adb-136">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="03adb-136">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="03adb-137">**Das Subjekt oder der Text** \> Körper des Betreffs oder Text **Körpers enthält eines dieser Wörter**: Geben Sie im angezeigten Dialogfeld **Wörter oder Ausdrücke angeben** einen der folgenden Werte ein, klicken](../../media/ITPro-EAC-AddIcon.png)Sie auf Add-Symbol **Hinzufügen** ![, und wiederholen Sie diese Schritte, bis Sie alle Werte eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="03adb-137">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `to change your preferences or unsubscribe`

       - `Modify email preferences or unsubscribe`

       - `This is a promotional email`

       - `You are receiving this email because you requested a subscription`

       - `click here to unsubscribe`

       - `You have received this email because you are subscribed`

       - `If you no longer wish to receive our email newsletter`

       - `to unsubscribe from this newsletter`

       - `If you have trouble viewing this email`

       - `This is an advertisement`

       - `you would like to unsubscribe or change your`

       - `view this email as a webpage`

       - `You are receiving this email because you are subscribed`

      <span data-ttu-id="03adb-138">Um einen Eintrag zu bearbeiten, wählen Sie ihn **Edit** ![aus, und](../../media/ITPro-EAC-EditIcon.png)klicken Sie auf Bearbeitungssymbol bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="03adb-138">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="03adb-139">Um einen Eintrag zu entfernen, wählen Sie ihn **Remove** ![aus, und](../../media/ITPro-EAC-DeleteIcon.png)klicken Sie auf entfernen-Symbol entfernen.</span><span class="sxs-lookup"><span data-stu-id="03adb-139">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="03adb-140">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="03adb-140">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="03adb-141">**Gehen Sie folgen**dermaßen vor: Wählen Sie **ändern die Nachrichteneigenschaften** \> **Festlegen der SCL-Bewertung (Spam Confidence Level)**.</span><span class="sxs-lookup"><span data-stu-id="03adb-141">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="03adb-142">Konfigurieren Sie im angezeigten **SCL** -Dialogfeld eine der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="03adb-142">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="03adb-143">Um Nachrichten als **Spam**zu markieren, wählen Sie **6**aus.</span><span class="sxs-lookup"><span data-stu-id="03adb-143">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="03adb-144">Die Aktion, die Sie für **Spam** Filterungs Urteile in ihren Anti-Spam-Richtlinien konfiguriert haben, wird auf die Nachrichten angewendet (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).</span><span class="sxs-lookup"><span data-stu-id="03adb-144">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="03adb-145">So markieren Sie Nachrichten als **Spam mit hoher Zuverlässigkeit** wählen Sie **9**aus.</span><span class="sxs-lookup"><span data-stu-id="03adb-145">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="03adb-146">Die Aktion, die Sie für Spam Filterungs Urteile mit **hoher Vertrauens** Würdigkeit in ihren Anti-Spam-Richtlinien konfiguriert haben, wird auf die Nachrichten angewendet (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).</span><span class="sxs-lookup"><span data-stu-id="03adb-146">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="03adb-147">Weitere Informationen zu SCL-Werten finden Sie unter [Spam Confidence Level (SCL) in Office 365](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="03adb-147">For more information about SCL values, see [Spam confidence level (SCL) in Office 365](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="03adb-148">Wenn Sie fertig sind, klicken Sie auf **Speichern**</span><span class="sxs-lookup"><span data-stu-id="03adb-148">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="03adb-149">Verwenden von PowerShell zum Erstellen von Nachrichtenfluss Regeln zum Filtern von Massen-e-Mails</span><span class="sxs-lookup"><span data-stu-id="03adb-149">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="03adb-150">Verwenden Sie die folgende Syntax, um eine oder beide Nachrichtenfluss Regeln (reguläre Ausdrücke Vs. Wörter) zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="03adb-150">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="03adb-151">In diesem Beispiel wird eine neue Regel mit dem Namen "Massen-e-Mail-Filterung-Regex" erstellt, die die gleiche Liste regulärer Ausdrücke aus der früheren Version des Themas verwendet, um Nachrichten als **Spam**festzulegen.</span><span class="sxs-lookup"><span data-stu-id="03adb-151">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="03adb-152">In diesem Beispiel wird eine neue Regel mit dem Namen "Massen-e-Mail-Filterung-Wörter" erstellt, die die gleiche Liste von Wörtern wie oben im Thema verwendet, um Nachrichten als **Spam mit hoher Vertrauens**Würdigkeit festzulegen.</span><span class="sxs-lookup"><span data-stu-id="03adb-152">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="03adb-153">Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="03adb-153">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="03adb-154">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="03adb-154">How do you know this worked?</span></span>

<span data-ttu-id="03adb-155">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob e-Mail-Flussregeln zum Filtern von Massen-e-Mails konfiguriert wurden:</span><span class="sxs-lookup"><span data-stu-id="03adb-155">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="03adb-156">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** \> \> wählen Sie die Regel](../../media/ITPro-EAC-EditIcon.png)klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![, und überprüfen Sie die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="03adb-156">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="03adb-157">Ersetzen \<Sie in PowerShell den Regel\> Namen durch den Namen der Regel, und führen Sie den folgenden Befehl aus, um die Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="03adb-157">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="03adb-158">Senden Sie von einem externen Konto eine Testnachricht an einen betroffenen Empfänger, der eines der Ausdrücke oder Textmuster enthält, und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="03adb-158">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
