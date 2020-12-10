---
title: Verwenden von Nachrichtenfluss Regeln zum Filtern von Massen-e-Mails
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Nachrichtenfluss Regeln (Transportregeln) verwenden, um Massen-e-Mails (Gray Mail) in Exchange Online Protection (EoP) zu identifizieren und zu filtern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1f88358973648846d650700bb5939c052851c789
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615636"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="9ef41-103">Verwenden von Regeln zum Filtern von Massen-E-Mails in EOP</span><span class="sxs-lookup"><span data-stu-id="9ef41-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9ef41-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer verwendet EoP Antispam-Richtlinien (auch als Spamfilter Richtlinien oder Inhaltsfilter Richtlinien bezeichnet), um eingehende Nachrichten für Spam und Massen-e-Mails zu scannen (auch als graue e-Mail bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="9ef41-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="9ef41-105">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9ef41-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="9ef41-106">Wenn Sie weitere Optionen zum Filtern von Massen-e-Mails wünschen, können Sie Nachrichtenfluss Regeln (auch bekannt als Transportregeln) erstellen, um nach Textmustern oder Ausdrücken zu suchen, die häufig in Massen-e-Mails gefunden werden, und diese Nachrichten als Spam markieren.</span><span class="sxs-lookup"><span data-stu-id="9ef41-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="9ef41-107">Weitere Informationen zu Massen-e-Mails finden Sie unter [Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mail? und der](what-s-the-difference-between-junk-email-and-bulk-email.md) [Massen Reklamations Stufe (BCL) in EoP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="9ef41-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="9ef41-108">In diesem Thema wird erläutert, wie Sie diese Nachrichtenfluss Regeln in der Exchange-Verwaltungskonsole (EAC) und PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer) erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ef41-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9ef41-109">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="9ef41-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9ef41-110">Sie müssen Berechtigungen zugewiesen haben, bevor Sie diese Verfahren ausführen können:</span><span class="sxs-lookup"><span data-stu-id="9ef41-110">You need to be assigned permissions before you can do these procedures:</span></span>

  - <span data-ttu-id="9ef41-111">Lesen Sie in Exchange Online den Eintrag "Nachrichtenfluss" unter [Feature Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span><span class="sxs-lookup"><span data-stu-id="9ef41-111">In Exchange Online, see the "Mail flow" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span></span>

  - <span data-ttu-id="9ef41-112">In eigenständigen EoP benötigen Sie die Transport Regel Rolle, die standardmäßig den Rollenmitglied, ComplianceManagement und RecordsManagement zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="9ef41-112">In standalone EOP, you need the Transport Rules role, which is assigned to the OrganizationManagement, ComplianceManagement, and RecordsManagement roles by default.</span></span> <span data-ttu-id="9ef41-113">Weitere Informationen finden Sie unter [Berechtigungen in eigenständigen EoP](feature-permissions-in-eop.md) und [Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="9ef41-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="9ef41-114">Informationen zum Öffnen des EAC in Exchange Online finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="9ef41-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="9ef41-115">Informationen zum Öffnen der Exchange-Verwaltungskonsole in eigenständigen EoP finden Sie unter [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="9ef41-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="9ef41-116">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9ef41-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9ef41-117">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9ef41-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9ef41-118">Weitere Informationen zu Nachrichtenfluss Regeln in Exchange Online und eigenständigen EoP finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="9ef41-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="9ef41-119">Nachrichtenflussregeln (Transportregeln) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9ef41-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="9ef41-120">Nachrichtenflussregel-Bedingungen und -Ausnahmen (Prädikate) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9ef41-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="9ef41-121">Aktionen für Nachrichtenflussregeln in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9ef41-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="9ef41-122">Die Liste der Wörter und Textmuster, die zum Identifizieren von Massennachrichten in den Beispielen verwendet werden, sind nicht erschöpfend; Sie können Einträge bei Bedarf hinzufügen und entfernen.</span><span class="sxs-lookup"><span data-stu-id="9ef41-122">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="9ef41-123">Sie sind jedoch ein guter Ausgangspunkt.</span><span class="sxs-lookup"><span data-stu-id="9ef41-123">However, they are a good starting point.</span></span>

- <span data-ttu-id="9ef41-p107">Die Suche nach Wörtern oder Textmustern im Betreff oder anderen Kopfzeilenfeldern in der Nachricht tritt *nach* der Decodierung der Nachricht aus der MIME-Inhaltsübertragungscodierungsmethode ein, die für die Übermittlung der binären Nachricht zwischen SMTP-Servern im ASCII-Text verwendet wurde. Sie können keine Bedingungen oder Ausnahmen für die Suche nach Rohwerten (in der Regel Base64-codiert) im Betreff oder in anderen Kopfzeilenfeldern in Nachrichten verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ef41-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="9ef41-126">Die folgenden Verfahren kennzeichnen eine Massen Nachricht als Spam für Ihre gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="9ef41-126">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="9ef41-127">Sie können jedoch eine weitere Bedingung hinzufügen, um diese Regeln nur auf bestimmte Empfänger anzuwenden, sodass Sie eine aggressive Filterung für einige wenige, sehr gezielte Benutzer verwenden können, während die restlichen Benutzer (die meistens die Massen-e-Mails erhalten, für die Sie sich angemeldet haben) nicht betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="9ef41-127">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="9ef41-128">Verwenden der Exchange-Verwaltungskonsole zum Erstellen von Nachrichtenfluss Regeln zum Filtern von Massen-e-Mails</span><span class="sxs-lookup"><span data-stu-id="9ef41-128">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="9ef41-129">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.</span><span class="sxs-lookup"><span data-stu-id="9ef41-129">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="9ef41-130">Klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) , und wählen Sie dann **neue Regel erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="9ef41-130">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="9ef41-131">Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="9ef41-131">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="9ef41-132">**Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="9ef41-132">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="9ef41-133">Klicken Sie auf **Weitere Optionen**.</span><span class="sxs-lookup"><span data-stu-id="9ef41-133">Click **More Options**.</span></span>

   - <span data-ttu-id="9ef41-134">**Diese Regel anwenden, wenn**: eine der folgenden Einstellungen zum Suchen nach Inhalten in Nachrichten mithilfe regulärer Ausdrücke (Regex) oder Wörtern oder Ausdrücken konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="9ef41-134">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="9ef41-135">**Der Betreff oder Textkörper** \> **Betreff oder Text entspricht diesen Textmustern**: Geben Sie im angezeigten Dialogfeld **Wörter oder Ausdrücke angeben** einen der folgenden Werte ein, klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) , und wiederholen Sie diese Schritte, bis Sie alle Werte eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="9ef41-135">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="9ef41-136">Um einen Eintrag zu bearbeiten, wählen Sie ihn aus, und klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9ef41-136">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="9ef41-137">Um einen Eintrag zu entfernen, wählen Sie ihn aus, und klicken Sie auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9ef41-137">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="9ef41-138">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ef41-138">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="9ef41-139">**Der Betreff oder Textkörper** \> **Betreff oder Textkörper enthält eines dieser Wörter**: Geben Sie im angezeigten Dialogfeld **Wörter oder Ausdrücke angeben** einen der folgenden Werte ein, klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) , und wiederholen Sie diese Schritte, bis Sie alle Werte eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="9ef41-139">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="9ef41-140">Um einen Eintrag zu bearbeiten, wählen Sie ihn aus, und klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9ef41-140">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="9ef41-141">Um einen Eintrag zu entfernen, wählen Sie ihn aus, und klicken Sie auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9ef41-141">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="9ef41-142">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ef41-142">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="9ef41-143">**Gehen Sie folgen** dermaßen vor: Wählen Sie **ändern die Nachrichteneigenschaften** \> **Festlegen der SCL-Bewertung (Spam Confidence Level)**.</span><span class="sxs-lookup"><span data-stu-id="9ef41-143">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="9ef41-144">Konfigurieren Sie im angezeigten **SCL** -Dialogfeld eine der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="9ef41-144">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="9ef41-145">Um Nachrichten als **Spam** zu markieren, wählen Sie **6** aus.</span><span class="sxs-lookup"><span data-stu-id="9ef41-145">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="9ef41-146">Die Aktion, die Sie für **Spam** Filterungs Urteile in ihren Anti-Spam-Richtlinien konfiguriert haben, wird auf die Nachrichten angewendet (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).</span><span class="sxs-lookup"><span data-stu-id="9ef41-146">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="9ef41-147">So markieren Sie Nachrichten als **Spam mit hoher Zuverlässigkeit** wählen Sie **9** aus.</span><span class="sxs-lookup"><span data-stu-id="9ef41-147">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="9ef41-148">Die Aktion, die Sie für Spam Filterungs Urteile mit **hoher Vertrauens** Würdigkeit in ihren Anti-Spam-Richtlinien konfiguriert haben, wird auf die Nachrichten angewendet (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).</span><span class="sxs-lookup"><span data-stu-id="9ef41-148">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="9ef41-149">Weitere Informationen zu SCL-Werten finden Sie unter [Spam Confidence Level (SCL) in EoP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9ef41-149">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="9ef41-150">Wenn Sie fertig sind, klicken Sie auf **Speichern**</span><span class="sxs-lookup"><span data-stu-id="9ef41-150">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="9ef41-151">Verwenden von PowerShell zum Erstellen von Nachrichtenfluss Regeln zum Filtern von Massen-e-Mails</span><span class="sxs-lookup"><span data-stu-id="9ef41-151">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="9ef41-152">Verwenden Sie die folgende Syntax, um eine oder beide Nachrichtenfluss Regeln (reguläre Ausdrücke Vs. Wörter) zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="9ef41-152">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="9ef41-153">In diesem Beispiel wird eine neue Regel mit dem Namen "Massen-e-Mail-Filterung-Regex" erstellt, die die gleiche Liste regulärer Ausdrücke aus der früheren Version des Themas verwendet, um Nachrichten als **Spam** festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9ef41-153">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="9ef41-154">In diesem Beispiel wird eine neue Regel mit dem Namen "Massen-e-Mail-Filterung-Wörter" erstellt, die die gleiche Liste von Wörtern wie oben im Thema verwendet, um Nachrichten als **Spam mit hoher Vertrauens** Würdigkeit festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9ef41-154">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="9ef41-155">Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="9ef41-155">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="9ef41-156">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="9ef41-156">How do you know this worked?</span></span>

<span data-ttu-id="9ef41-157">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob e-Mail-Flussregeln zum Filtern von Massen-e-Mails konfiguriert wurden:</span><span class="sxs-lookup"><span data-stu-id="9ef41-157">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="9ef41-158">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** \> Wählen Sie die Regel \> Klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-EditIcon.png) , und überprüfen Sie die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="9ef41-158">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="9ef41-159">Ersetzen Sie in PowerShell \<Rule Name\> durch den Namen der Regel, und führen Sie den folgenden Befehl aus, um die Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="9ef41-159">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="9ef41-160">Senden Sie von einem externen Konto eine Testnachricht an einen betroffenen Empfänger, der eines der Ausdrücke oder Textmuster enthält, und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="9ef41-160">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
