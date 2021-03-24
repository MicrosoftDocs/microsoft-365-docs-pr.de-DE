---
title: Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden
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
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, um Kopien von Nachrichten zu empfangen, die Benutzer an Microsoft melden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e6428a228ae64562f0b529f6aa90ddc3be46fdc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061896"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="82f4c-103">Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden</span><span class="sxs-lookup"><span data-stu-id="82f4c-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="82f4c-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="82f4c-104">**Applies to**</span></span>
- [<span data-ttu-id="82f4c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="82f4c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="82f4c-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="82f4c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="82f4c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82f4c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="82f4c-108">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer gibt es mehrere Möglichkeiten für Benutzer, Nachrichten an Microsoft zur Analyse zu melden, wie unter Melden von Nachrichten und Dateien an [Microsoft beschrieben.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="82f4c-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="82f4c-109">Sie können eine Nachrichtenflussregel (auch als Transportregel bezeichnet) erstellen, die nach Nachrichten sucht, die Benutzer an Microsoft melden, und Sie können Bcc-Empfänger für den Empfang von Kopien dieser gemeldeten Nachrichten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="82f4c-109">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="82f4c-110">Sie können die Nachrichtenflussregel im Exchange Admin Center (EAC) und in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange #A0) erstellen.</span><span class="sxs-lookup"><span data-stu-id="82f4c-110">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="82f4c-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="82f4c-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="82f4c-112">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online oder Exchange Online Protection berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="82f4c-112">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="82f4c-113">Insbesondere benötigen Sie die Rolle **Transportregeln,** die standardmäßig den Rollengruppen **Organisationsverwaltung,** **Complianceverwaltung** (globale Administratoren) und **Datensatzverwaltung** zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="82f4c-113">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="82f4c-114">Weitere Informationen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="82f4c-114">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="82f4c-115">Berechtigungen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="82f4c-115">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="82f4c-116">Berechtigungen in EOP als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="82f4c-116">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="82f4c-117">Ändern der Liste der Mitglieder in Rollengruppen mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="82f4c-117">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="82f4c-118">Informationen zum Öffnen der EAC in Exchange Online finden Sie unter [Exchange Admin Center in Exchange Online](/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="82f4c-118">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="82f4c-119">Informationen zum Öffnen der EAC im eigenständigen EOP finden Sie unter [Exchange Admin Center im eigenständigen EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="82f4c-119">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="82f4c-120">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="82f4c-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="82f4c-121">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="82f4c-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="82f4c-122">Weitere Informationen zu Nachrichtenflussregeln in Exchange Online und eigenständigem EOP finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="82f4c-122">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="82f4c-123">Nachrichtenflussregeln (Transportregeln) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="82f4c-123">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="82f4c-124">Nachrichtenflussregel-Bedingungen und -Ausnahmen (Prädikate) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="82f4c-124">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="82f4c-125">Aktionen für Nachrichtenflussregeln in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="82f4c-125">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="82f4c-126">Erstellen einer Nachrichtenflussregel mithilfe der EAC zum Empfangen von Kopien gemeldeter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="82f4c-126">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="82f4c-127">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.</span><span class="sxs-lookup"><span data-stu-id="82f4c-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="82f4c-128">Klicken **Sie auf** Hinzufügen ![ ](../../media/ITPro-EAC-AddIcon.png) (Symbol) und wählen Sie **dann Neue Regel erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="82f4c-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="82f4c-129">Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="82f4c-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="82f4c-130">**Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="82f4c-130">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="82f4c-131">Beispiel: An Microsoft gemeldete Bcc-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="82f4c-131">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="82f4c-132">Klicken Sie auf **Weitere Optionen**.</span><span class="sxs-lookup"><span data-stu-id="82f4c-132">Click **More Options**.</span></span>

   - <span data-ttu-id="82f4c-133">Wenden Sie diese Regel an, wenn **:** Select **The recipient** address includes any of these words : In the Specify words or phrases dialog that \> appears, enter one of the following values, click **Add** Icon , and repeat until  ![ ](../../media/ITPro-EAC-AddIcon.png) you've entered all the values.</span><span class="sxs-lookup"><span data-stu-id="82f4c-133">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     <span data-ttu-id="82f4c-134">Um einen Eintrag zu bearbeiten, wählen Sie ihn aus, und klicken Sie **auf Bearbeiten** ![ (Symbol). ](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="82f4c-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="82f4c-135">Um einen Eintrag zu entfernen, wählen Sie ihn aus, und klicken **Sie auf Entfernen** ![ ](../../media/ITPro-EAC-DeleteIcon.png) (Symbol).</span><span class="sxs-lookup"><span data-stu-id="82f4c-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="82f4c-136">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="82f4c-136">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="82f4c-137">**Gehen Sie wie folgt vor:** Wählen **Sie Empfänger zum** Feld \> **Bcc hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="82f4c-137">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="82f4c-138">Suchen Und wählen Sie im angezeigten Dialogfeld die Empfänger aus, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="82f4c-138">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="82f4c-139">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="82f4c-139">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="82f4c-140">Sie können zusätzliche Auswahlen treffen, um die Regel zu überwachen, die Regel zu testen, die Regel während eines bestimmten Zeitraums zu aktivieren und andere Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="82f4c-140">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="82f4c-141">Es wird empfohlen, die Regel zu testen, bevor Sie sie erzwingen.</span><span class="sxs-lookup"><span data-stu-id="82f4c-141">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="82f4c-142">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="82f4c-142">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="82f4c-143">Verwenden von PowerShell zum Erstellen einer Nachrichtenflussregel zum Empfangen von Kopien gemeldeter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="82f4c-143">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="82f4c-144">In diesem Beispiel wird eine neue Nachrichtenflussregel namens "Bcc Messages Reported to Microsoft" erstellt, die mithilfe der in diesem Artikel beschriebenen Methoden nach E-Mail-Nachrichten sucht und die Benutzer laura@contoso.com und julia@contoso.com als Bcc-Empfänger hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="82f4c-144">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="82f4c-145">Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="82f4c-145">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="82f4c-146">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="82f4c-146">How do you know this worked?</span></span>

<span data-ttu-id="82f4c-147">Gehen Sie wie folgt vor, um zu überprüfen, ob Sie eine Nachrichtenflussregeln für den Empfang von Kopien gemeldeter Nachrichten konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="82f4c-147">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="82f4c-148">Wechseln Sie in der EAC zu **Nachrichtenfluss** Regeln wählen Sie die Regel auf Bearbeiten (Symbol bearbeiten) \>  \> \>  ![ ](../../media/ITPro-EAC-EditIcon.png) aus, und überprüfen Sie die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="82f4c-148">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="82f4c-149">Führen Sie in PowerShell den folgenden Befehl aus, um die Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="82f4c-149">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="82f4c-150">Senden Sie eine Testnachrichten an eine der E-Mail-Adressen des Berichts, und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="82f4c-150">Send a test messages to one of the reporting email addresses and verify the results.</span></span>