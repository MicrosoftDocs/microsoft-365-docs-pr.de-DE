---
title: Erstellen einer Richtlinie für vertrauliche Informationstypen mithilfe der Office 365-Nachrichtenverschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Erfahren Sie, wie Sie mithilfe der Office 365-Nachrichtenverschlüsselung eine Richtlinie für vertrauliche Informationstypen für Ihre Organisation erstellen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 22aec87b149c58b2537f6921fb7c37552ef72f98
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741378"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a><span data-ttu-id="e4139-103">Erstellen einer Richtlinie für vertrauliche Informationstypen für Ihre Organisation mithilfe der Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="e4139-103">Create a sensitive information type policy for your organization using Message Encryption</span></span>

<span data-ttu-id="e4139-104">Sie können entweder Exchange-Nachrichtenflussregeln oder Die Verhinderung von Datenverlust (Data Loss Prevention, DLP) verwenden, um eine Richtlinie für vertrauliche Informationstypen mit office 365-Nachrichtenverschlüsselung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e4139-104">You can use either Exchange mail flow rules or Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="e4139-105">Zum Erstellen einer Exchange-Nachrichtenflussregel können Sie entweder das Exchange Admin Center (EAC) oder PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4139-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="e4139-106">So erstellen Sie die Richtlinie mithilfe von Nachrichtenflussregeln in der EAC</span><span class="sxs-lookup"><span data-stu-id="e4139-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="e4139-107">Melden Sie sich beim Exchange Admin Center (EAC) an, und wechseln Sie zu **Nachrichtenflussregeln**  >  .</span><span class="sxs-lookup"><span data-stu-id="e4139-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="e4139-108">Erstellen Sie auf der Seite Regeln eine Regel, die die Office 365-Nachrichtenverschlüsselung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4139-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="e4139-109">Sie können eine Regel basierend auf Bedingungen wie dem Vorhandensein bestimmter Schlüsselwörter oder vertraulicher Informationstypen in der Nachricht oder Anlage erstellen.</span><span class="sxs-lookup"><span data-stu-id="e4139-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="e4139-110">So erstellen Sie die Richtlinie mithilfe von Nachrichtenflussregeln in PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4139-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="e4139-111">Verwenden Sie ein Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, starten Sie eine Windows PowerShell und stellen Sie eine Verbindung zu Exchange Online ein.</span><span class="sxs-lookup"><span data-stu-id="e4139-111">Use a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e4139-112">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="e4139-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="e4139-113">Verwenden Sie die Set-IRMConfiguration und New-TransportRule cmdlets, um die Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e4139-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="e4139-114">Beispiel für mit PowerShell erstellte Nachrichtenflussregel</span><span class="sxs-lookup"><span data-stu-id="e4139-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="e4139-115">Führen Sie die folgenden Befehle in PowerShell aus, um eine Exchange-Nachrichtenflussregel zu erstellen, die E-Mails, die außerhalb Ihrer Organisation gesendet werden, automatisch mit der Option zum Verschlüsseln verschlüsselt, wenn die E-Mails oder ihre Anlagen die folgenden vertraulichen Informationstypen enthalten:</span><span class="sxs-lookup"><span data-stu-id="e4139-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the encrypt-only option if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="e4139-116">ABA-Routingnummer</span><span class="sxs-lookup"><span data-stu-id="e4139-116">ABA routing number</span></span>
- <span data-ttu-id="e4139-117">Kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="e4139-117">Credit card Number</span></span>
- <span data-ttu-id="e4139-118">Nummer der Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="e4139-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="e4139-119">USA/Vereinigtes Königreich</span><span class="sxs-lookup"><span data-stu-id="e4139-119">U.S. / U.K.</span></span> <span data-ttu-id="e4139-120">passport number</span><span class="sxs-lookup"><span data-stu-id="e4139-120">passport number</span></span>
- <span data-ttu-id="e4139-121">US-Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="e4139-121">U.S. bank account number</span></span>
- <span data-ttu-id="e4139-122">US-Steueridentifikationsnummer (ITIN)</span><span class="sxs-lookup"><span data-stu-id="e4139-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="e4139-123">US-Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="e4139-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="e4139-124">Weitere Informationen finden Sie unter [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) und [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="e4139-124">For more information, see [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) and [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="e4139-125">Zugreifen von Empfängern auf Anlagen</span><span class="sxs-lookup"><span data-stu-id="e4139-125">How recipients access attachments</span></span>

<span data-ttu-id="e4139-126">Nachdem Microsoft eine Nachricht verschlüsselt hat, haben Empfänger uneingeschränkten Zugriff auf Anlagen, wenn sie auf ihre verschlüsselten E-Mails zugreifen und diese öffnen.</span><span class="sxs-lookup"><span data-stu-id="e4139-126">After Microsoft encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="e4139-127">So bereiten Sie sich auf diese Änderung vor</span><span class="sxs-lookup"><span data-stu-id="e4139-127">To prepare for this change</span></span>

<span data-ttu-id="e4139-128">Möglicherweise möchten Sie alle anwendbaren Dokumentationen und Schulungsmaterialien für Endbenutzer aktualisieren, um Die Mitarbeiter in Ihrer Organisation auf diese Änderung vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="e4139-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="e4139-129">Geben Sie diese Office 365-Nachrichtenverschlüsselungsressourcen für Ihre Benutzer entsprechend an:</span><span class="sxs-lookup"><span data-stu-id="e4139-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="e4139-130">Senden, Anzeigen und Antworten auf verschlüsselte Nachrichten in Outlook für PC</span><span class="sxs-lookup"><span data-stu-id="e4139-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="e4139-131">Microsoft 365 Essentials Video: Office-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="e4139-131">Microsoft 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="e4139-132">Anzeigen dieser Änderungen im Überwachungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="e4139-132">View these changes in the audit log</span></span>

<span data-ttu-id="e4139-133">Microsoft 365 überwacht diese Aktivität und stellt sie Administratoren zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e4139-133">Microsoft 365 audits this activity and makes it available to administrators.</span></span> <span data-ttu-id="e4139-134">Der Vorgang ist "New-TransportRule" und ein Codeausschnitt eines Beispiel-Überwachungseintrags aus der Überwachungsprotokollsuche im Security & Compliance Center ist unten aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="e4139-134">The operation is 'New-TransportRule' and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="e4139-135">So deaktivieren oder anpassen Sie die Richtlinie für vertrauliche Informationstypen</span><span class="sxs-lookup"><span data-stu-id="e4139-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="e4139-136">Nachdem Sie die Exchange-Nachrichtenflussregel erstellt [](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) haben, können Sie die Regel deaktivieren oder bearbeiten, indem Sie zu Nachrichtenflussregeln im Exchange Admin Center (EAC) gehen und die Regel " Verschlüsseln ausgehender vertraulicher E-Mails  >   *(Out-of-Box-Regel) "* deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e4139-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule "*Encrypt outbound sensitive emails (out of box rule)*".</span></span>
