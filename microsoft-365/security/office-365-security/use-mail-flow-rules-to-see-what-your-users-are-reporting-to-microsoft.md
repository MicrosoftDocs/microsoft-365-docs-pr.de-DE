---
title: Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden
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
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Nachrichtenfluss Regeln (auch bekannt als Transportregeln) verwenden, um Kopien von Nachrichten zu erhalten, die Benutzer an Microsoft melden.
ms.openlocfilehash: 0f3046c9d1962366ffd75353347b6cf7b72afd14
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659850"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="4e71e-103">Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden</span><span class="sxs-lookup"><span data-stu-id="4e71e-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4e71e-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer gibt es mehrere Möglichkeiten für Benutzer, Nachrichten an Microsoft zur Analyse zu melden, wie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4e71e-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="4e71e-105">Sie können eine e-Mail-Fluss Regel (auch als Transportregel bezeichnet) erstellen, die nach Nachrichten sucht, die Benutzer an Microsoft melden, und Sie können Bcc-Empfänger so konfigurieren, dass Kopien dieser gemeldeten Nachrichten empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="4e71e-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="4e71e-106">Sie können die Nachrichtenfluss Regel in der Exchange-Verwaltungskonsole (EAC) und in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer) erstellen.</span><span class="sxs-lookup"><span data-stu-id="4e71e-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4e71e-107">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="4e71e-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4e71e-108">Sie müssen Berechtigungen in Exchange Online oder Exchange Online Schutz zugewiesen werden, bevor Sie die Verfahren in diesem Artikel ausführen können.</span><span class="sxs-lookup"><span data-stu-id="4e71e-108">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="4e71e-109">Insbesondere benötigen Sie die **Transport Regel** Rolle, die standardmäßig der Rollengruppe **"Organisationsverwaltung**", " **Compliance-Verwaltung** " (globale Administratoren) und der Rolle " **Datensatzverwaltung** " zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="4e71e-109">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="4e71e-110">Weitere Informationen hierzu finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="4e71e-110">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="4e71e-111">Berechtigungen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4e71e-111">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="4e71e-112">Berechtigungen in EOP als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="4e71e-112">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="4e71e-113">Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen</span><span class="sxs-lookup"><span data-stu-id="4e71e-113">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="4e71e-114">Informationen zum Öffnen des EAC in Exchange Online finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="4e71e-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="4e71e-115">Informationen zum Öffnen der Exchange-Verwaltungskonsole in eigenständigen EoP finden Sie unter [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4e71e-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="4e71e-116">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4e71e-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="4e71e-117">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="4e71e-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4e71e-118">Weitere Informationen zu Nachrichtenfluss Regeln in Exchange Online und eigenständigen EoP finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="4e71e-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="4e71e-119">Nachrichtenflussregeln (Transportregeln) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4e71e-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="4e71e-120">Nachrichtenflussregel-Bedingungen und -Ausnahmen (Prädikate) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4e71e-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="4e71e-121">Aktionen für Nachrichtenflussregeln in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4e71e-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="4e71e-122">Erstellen einer e-Mail-Fluss Regel zum Empfangen von Kopien gemeldeter Nachrichten mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="4e71e-122">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="4e71e-123">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.</span><span class="sxs-lookup"><span data-stu-id="4e71e-123">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="4e71e-124">Klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) , und wählen Sie dann **neue Regel erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="4e71e-124">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="4e71e-125">Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="4e71e-125">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="4e71e-126">**Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="4e71e-126">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="4e71e-127">Beispielsweise Bcc-Nachrichten, die an Microsoft gemeldet wurden.</span><span class="sxs-lookup"><span data-stu-id="4e71e-127">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="4e71e-128">Klicken Sie auf **Weitere Optionen**.</span><span class="sxs-lookup"><span data-stu-id="4e71e-128">Click **More Options**.</span></span>

   - <span data-ttu-id="4e71e-129">**Diese Regel anwenden, wenn**: Wählen Sie **die Empfänger** \> **Adresse enthält eines dieser Wörter** aus: Geben Sie im angezeigten Dialogfeld **Wörter oder Ausdrücke angeben** einen der folgenden Werte ein, klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) , und wiederholen Sie diese Schritte, bis Sie alle Werte eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="4e71e-129">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="4e71e-130">Um einen Eintrag zu bearbeiten, wählen Sie ihn aus, und klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4e71e-130">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="4e71e-131">Um einen Eintrag zu entfernen, wählen Sie ihn aus, und klicken Sie auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4e71e-131">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="4e71e-132">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e71e-132">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="4e71e-133">**Gehen Sie wie folgt** vor: Wählen Sie Empfänger  \> **zum Feld Bcc** hinzufügen aus.</span><span class="sxs-lookup"><span data-stu-id="4e71e-133">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="4e71e-134">Suchen Sie im angezeigten Dialogfeld die Empfänger, die Sie hinzufügen möchten, und wählen Sie Sie aus.</span><span class="sxs-lookup"><span data-stu-id="4e71e-134">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="4e71e-135">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e71e-135">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="4e71e-136">Sie können eine weitere Auswahl treffen, um die Regel zu überwachen, die Regel zu testen, die Regel während eines bestimmten Zeitraums zu aktivieren und andere Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="4e71e-136">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="4e71e-137">Es wird empfohlen, die Regel zu testen, bevor Sie Sie erzwingen.</span><span class="sxs-lookup"><span data-stu-id="4e71e-137">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="4e71e-138">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4e71e-138">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="4e71e-139">Verwenden von PowerShell zum Erstellen einer e-Mail-Fluss Regel zum Empfangen von Kopien gemeldeter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="4e71e-139">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="4e71e-140">In diesem Beispiel wird eine neue e-Mail-Fluss Regel namens "Bcc Messages" an Microsoft erstellt, die nach e-Mail-Nachrichten sucht, die mithilfe der in diesem Artikel beschriebenen Methoden an Microsoft gemeldet werden, und fügt die Benutzer Laura@contoso.com und Julia@contoso.com als Bcc-Empfänger hinzu.</span><span class="sxs-lookup"><span data-stu-id="4e71e-140">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="4e71e-141">Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="4e71e-141">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="4e71e-142">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="4e71e-142">How do you know this worked?</span></span>

<span data-ttu-id="4e71e-143">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie eine Nachrichtenfluss Regel für den Empfang von Kopien gemeldeter Nachrichten konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="4e71e-143">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="4e71e-144">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** \> Wählen Sie die Regel \> Klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-EditIcon.png) , und überprüfen Sie die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="4e71e-144">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="4e71e-145">Führen Sie in PowerShell den folgenden Befehl aus, um die Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="4e71e-145">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="4e71e-146">Senden Sie eine Testnachricht an eine der Berichts-e-Mail-Adressen, und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="4e71e-146">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
