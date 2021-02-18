---
title: Filtern von Massen-E-Mails mithilfe von Nachrichtenflussregeln
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Nachrichtenflussregeln (Transportregeln) verwenden, um Massen-E-Mails (graue E-Mails) in Exchange Online Protection (EOP) zu identifizieren und zu filtern.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8030d21d414cb38769a6831391262fa3798a8838
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287293"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="06c54-103">Verwenden von Regeln zum Filtern von Massen-E-Mails in EOP</span><span class="sxs-lookup"><span data-stu-id="06c54-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="06c54-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="06c54-104">**Applies to**</span></span>
- [<span data-ttu-id="06c54-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="06c54-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="06c54-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="06c54-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="06c54-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06c54-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="06c54-108">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer verwendet EOP Antispamrichtlinien (auch als Spamfilterrichtlinien oder Inhaltsfilterrichtlinien bekannt), um eingehende Nachrichten auf Spam und Massen-E-Mails (auch als graue E-Mails bekannt) zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="06c54-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="06c54-109">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="06c54-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="06c54-110">Wenn Sie weitere Optionen zum Filtern von Massen-E-Mails wünschen, können Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet) erstellen, um nach Textmustern oder Ausdrücken zu suchen, die häufig in Massen-E-Mails gefunden werden, und diese Nachrichten als Spam markieren.</span><span class="sxs-lookup"><span data-stu-id="06c54-110">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="06c54-111">Weitere Informationen zu Massen-E-Mails finden Sie unter ["Worin](what-s-the-difference-between-junk-email-and-bulk-email.md) besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?" und ["Bulk Complaint Level" (BCL) in EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="06c54-111">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="06c54-112">In diesem Thema wird erläutert, wie diese Nachrichtenflussregeln im Exchange Admin Center (EAC) und in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange #A0 ) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="06c54-112">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="06c54-113">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="06c54-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="06c54-114">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen die entsprechenden Berechtigungen in Exchange Online oder Exchange Online Protection zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="06c54-114">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="06c54-115">Insbesondere benötigen Sie die Rolle **"Transportregeln",** die standardmäßig den Rollengruppen  **Organisationsverwaltung,** **Complianceverwaltung** (globale Administratoren) und Datensatzverwaltung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="06c54-115">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="06c54-116">Weitere Informationen hierzu finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="06c54-116">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="06c54-117">Berechtigungen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="06c54-117">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="06c54-118">Berechtigungen in EOP als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="06c54-118">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="06c54-119">Ändern der Mitgliederliste in Rollengruppen mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="06c54-119">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="06c54-120">Informationen zum Öffnen der EAC in Exchange Online finden Sie im [Exchange Admin Center in Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="06c54-120">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="06c54-121">Informationen zum Öffnen der EAC im eigenständigen EOP finden Sie im [Exchange Admin Center in EOP als eigenständige Lösung.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="06c54-121">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="06c54-122">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="06c54-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="06c54-123">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="06c54-123">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="06c54-124">Weitere Informationen zu Nachrichtenflussregeln in Exchange Online und EOP als eigenständige Lösung finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="06c54-124">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="06c54-125">Nachrichtenflussregeln (Transportregeln) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="06c54-125">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="06c54-126">Nachrichtenflussregel-Bedingungen und -Ausnahmen (Prädikate) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="06c54-126">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="06c54-127">Aktionen für Nachrichtenflussregeln in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="06c54-127">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="06c54-128">Die Liste der Wörter und Textmuster, die zum Identifizieren von Massen-E-Mails in den Beispielen verwendet werden, ist nicht vollständig. Sie können Einträge nach Bedarf hinzufügen und entfernen.</span><span class="sxs-lookup"><span data-stu-id="06c54-128">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="06c54-129">Sie sind jedoch ein guter Ausgangspunkt.</span><span class="sxs-lookup"><span data-stu-id="06c54-129">However, they are a good starting point.</span></span>

- <span data-ttu-id="06c54-p107">Die Suche nach Wörtern oder Textmustern im Betreff oder anderen Kopfzeilenfeldern in der Nachricht tritt *nach* der Decodierung der Nachricht aus der MIME-Inhaltsübertragungscodierungsmethode ein, die für die Übermittlung der binären Nachricht zwischen SMTP-Servern im ASCII-Text verwendet wurde. Sie können keine Bedingungen oder Ausnahmen für die Suche nach Rohwerten (in der Regel Base64-codiert) im Betreff oder in anderen Kopfzeilenfeldern in Nachrichten verwenden.</span><span class="sxs-lookup"><span data-stu-id="06c54-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="06c54-132">Mit den folgenden Verfahren wird eine Massennachricht für Ihre gesamte Organisation als Spam markiert.</span><span class="sxs-lookup"><span data-stu-id="06c54-132">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="06c54-133">Sie können jedoch eine weitere Bedingung hinzufügen, um diese Regeln nur auf bestimmte Empfänger anzuwenden, sodass Sie aggressive Filterung für einige wenige benutzer mit hohem Ziel verwenden können, während die restlichen Benutzer (die hauptsächlich die Massen-E-Mails erhalten, für die sie sich angemeldet haben) nicht betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="06c54-133">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="06c54-134">Erstellen von Nachrichtenflussregeln zum Filtern von Massen-E-Mails mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="06c54-134">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="06c54-135">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.</span><span class="sxs-lookup"><span data-stu-id="06c54-135">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="06c54-136">Klicken **Sie auf das** Symbol ![ ](../../media/ITPro-EAC-AddIcon.png) "Hinzufügen", und wählen Sie dann **"Neue Regel erstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="06c54-136">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="06c54-137">Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="06c54-137">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="06c54-138">**Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="06c54-138">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="06c54-139">Klicken Sie auf **Weitere Optionen**.</span><span class="sxs-lookup"><span data-stu-id="06c54-139">Click **More Options**.</span></span>

   - <span data-ttu-id="06c54-140">**Wenden Sie diese Regel an,** wenn : Konfigurieren Sie eine der folgenden Einstellungen, um mithilfe regulärer Ausdrücke (RegEx) oder Wörter oder Ausdrücke nach Inhalten in Nachrichten zu suchen:</span><span class="sxs-lookup"><span data-stu-id="06c54-140">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="06c54-141">**Betreff oder Textkörper** \> **Betreff oder** Text entspricht diesen  Textmustern: Geben Sie im angezeigten Dialogfeld "Wörter oder Ausdrücke angeben" einen der folgenden Werte ein, klicken Sie auf "Hinzufügen" (Symbol) und wiederholen Sie diesen Vorgang, bis Sie alle Werte eingegeben  ![ ](../../media/ITPro-EAC-AddIcon.png) haben.</span><span class="sxs-lookup"><span data-stu-id="06c54-141">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="06c54-142">Um einen Eintrag zu bearbeiten, wählen Sie ihn aus, und klicken Sie auf das  ![ ](../../media/ITPro-EAC-EditIcon.png) Bearbeitungssymbol.</span><span class="sxs-lookup"><span data-stu-id="06c54-142">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="06c54-143">Um einen Eintrag zu entfernen, wählen Sie ihn aus, und klicken **Sie auf "Entfernen"** ![ ](../../media/ITPro-EAC-DeleteIcon.png) (Symbol).</span><span class="sxs-lookup"><span data-stu-id="06c54-143">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="06c54-144">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="06c54-144">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="06c54-145">**Betreff oder Textkörper** \> **Betreff** oder Text enthält eines der  folgenden Wörter: Geben Sie im angezeigten Dialogfeld  "Wörter oder Ausdrücke angeben" einen der folgenden Werte ein, klicken Sie auf "Hinzufügen" (Symbol) und wiederholen Sie diesen Vorgang, bis Sie alle Werte eingegeben ![ ](../../media/ITPro-EAC-AddIcon.png) haben.</span><span class="sxs-lookup"><span data-stu-id="06c54-145">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="06c54-146">Um einen Eintrag zu bearbeiten, wählen Sie ihn aus, und klicken Sie auf das  ![ ](../../media/ITPro-EAC-EditIcon.png) Bearbeitungssymbol.</span><span class="sxs-lookup"><span data-stu-id="06c54-146">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="06c54-147">Um einen Eintrag zu entfernen, wählen Sie ihn aus, und klicken **Sie auf "Entfernen"** ![ ](../../media/ITPro-EAC-DeleteIcon.png) (Symbol).</span><span class="sxs-lookup"><span data-stu-id="06c54-147">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="06c54-148">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="06c54-148">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="06c54-149">**Gehen Sie wie folgt vor:** Wählen **Sie "Nachrichteneigenschaften** \> **ändern" aus, um die SCL (Spam Confidence Level) zu setzen.**</span><span class="sxs-lookup"><span data-stu-id="06c54-149">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="06c54-150">Konfigurieren Sie im angezeigten Dialogfeld **"SCL** angeben" eine der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="06c54-150">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="06c54-151">Wählen Sie 6 aus, um Nachrichten als **Spam** **zu markieren.**</span><span class="sxs-lookup"><span data-stu-id="06c54-151">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="06c54-152">Die Aktion, die Sie  in Ihren Antispamrichtlinien für Spamfilterungen konfiguriert haben, wird auf die Nachrichten angewendet (der Standardwert ist "Nachricht in Junk-E-Mail-Ordner **verschieben").**</span><span class="sxs-lookup"><span data-stu-id="06c54-152">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="06c54-153">Wählen Sie 9 **aus,** um Nachrichten als Spam mit hoher **Spamsicherheit zu markieren.**</span><span class="sxs-lookup"><span data-stu-id="06c54-153">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="06c54-154">Die Aktion, die Sie  für Spamfilterungen mit hoher Confidence in Ihren Antispamrichtlinien konfiguriert haben, wird auf die Nachrichten angewendet (der Standardwert ist "Nachricht in Junk-E-Mail-Ordner **verschieben").**</span><span class="sxs-lookup"><span data-stu-id="06c54-154">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="06c54-155">Weitere Informationen zu den SCL-Werten finden Sie unter [SCL (Spam Confidence Level) in EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="06c54-155">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="06c54-156">Wenn Sie fertig sind, klicken Sie auf **"Speichern".**</span><span class="sxs-lookup"><span data-stu-id="06c54-156">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="06c54-157">Verwenden von PowerShell zum Erstellen von Nachrichtenflussregeln, die Massen-E-Mails filtern</span><span class="sxs-lookup"><span data-stu-id="06c54-157">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="06c54-158">Verwenden Sie die folgende Syntax, um eine oder beide der Nachrichtenflussregeln (reguläre Ausdrücke im Vergleich zu Wörtern) zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="06c54-158">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="06c54-159">In diesem Beispiel wird eine neue Regel mit dem Namen "Massen-E-Mail-Filterung - RegEx" erstellt, die dieselbe Liste regulärer Ausdrücke aus früheren Themen verwendet, um Nachrichten als **Spam zu setzen.**</span><span class="sxs-lookup"><span data-stu-id="06c54-159">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="06c54-160">In diesem Beispiel wird eine neue Regel namens "Bulk email filtering - Words" erstellt, die dieselbe Liste von Wörtern aus früheren Themen verwendet, um Nachrichten als Spam mit hoher Confidence **zu setzen.**</span><span class="sxs-lookup"><span data-stu-id="06c54-160">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="06c54-161">Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="06c54-161">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="06c54-162">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="06c54-162">How do you know this worked?</span></span>

<span data-ttu-id="06c54-163">Gehen Sie wie folgt vor, um sicherzustellen, dass Sie Nachrichtenflussregeln zum Filtern von Massen-E-Mails konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="06c54-163">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="06c54-164">Wechseln Sie in der EAC zu **"Nachrichtenflussregeln",** wählen Sie die Regel aus, klicken Sie auf "Bearbeitungssymbol", \>  \> und überprüfen \> Sie die  ![ ](../../media/ITPro-EAC-EditIcon.png) Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="06c54-164">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="06c54-165">Ersetzen Sie in PowerShell den Namen der Regel, und führen Sie den folgenden Befehl \<Rule Name\> aus, um die Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="06c54-165">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="06c54-166">Senden Sie von einem externen Konto eine Testnachrichten an einen betroffenen Empfänger, der eines der Ausdrücke oder Textmuster enthält, und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="06c54-166">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
