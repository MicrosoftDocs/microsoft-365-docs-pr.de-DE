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
ms.openlocfilehash: ad570f64122aecd245b912b1b6545a5950e838cc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927743"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>Erstellen einer Richtlinie für vertrauliche Informationstypen für Ihre Organisation mithilfe der Nachrichtenverschlüsselung

Sie können entweder Exchange-Nachrichtenflussregeln oder Die Verhinderung von Datenverlust (Data Loss Prevention, DLP) verwenden, um eine Richtlinie für vertrauliche Informationstypen mit office 365-Nachrichtenverschlüsselung zu erstellen. Zum Erstellen einer Exchange-Nachrichtenflussregel können Sie entweder das Exchange Admin Center (EAC) oder PowerShell verwenden.

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>So erstellen Sie die Richtlinie mithilfe von Nachrichtenflussregeln in der EAC

Melden Sie sich beim Exchange Admin Center (EAC) an, und wechseln Sie zu **Nachrichtenflussregeln**  >  . Erstellen Sie auf der Seite Regeln eine Regel, die die Office 365-Nachrichtenverschlüsselung verwendet. Sie können eine Regel basierend auf Bedingungen wie dem Vorhandensein bestimmter Schlüsselwörter oder vertraulicher Informationstypen in der Nachricht oder Anlage erstellen.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>So erstellen Sie die Richtlinie mithilfe von Nachrichtenflussregeln in PowerShell

Verwenden Sie ein Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, starten Sie eine Windows PowerShell und stellen Sie eine Verbindung zu Exchange Online ein. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Verwenden Sie die Set-IRMConfiguration und New-TransportRule cmdlets, um die Richtlinie zu erstellen.

## <a name="example-mail-flow-rule-created-with-powershell"></a>Beispiel für mit PowerShell erstellte Nachrichtenflussregel

Führen Sie die folgenden Befehle in PowerShell aus, um eine Exchange-Nachrichtenflussregel zu erstellen, die E-Mails, die außerhalb Ihrer Organisation gesendet werden, automatisch mit der Option zum Verschlüsseln verschlüsselt, wenn die E-Mails oder ihre Anlagen die folgenden vertraulichen Informationstypen enthalten:

- ABA-Routingnummer
- Kreditkartennummer
- Nummer der Drug Enforcement Agency (DEA)
- USA/Vereinigtes Königreich passport number
- US-Bankkontonummer
- US-Steueridentifikationsnummer (ITIN)
- US-Sozialversicherungsnummer

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

Weitere Informationen finden Sie unter [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) und [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-recipients-access-attachments"></a>Zugreifen von Empfängern auf Anlagen

Nachdem Microsoft eine Nachricht verschlüsselt hat, haben Empfänger uneingeschränkten Zugriff auf Anlagen, wenn sie auf ihre verschlüsselten E-Mails zugreifen und diese öffnen.

## <a name="to-prepare-for-this-change"></a>So bereiten Sie sich auf diese Änderung vor

Möglicherweise möchten Sie alle anwendbaren Dokumentationen und Schulungsmaterialien für Endbenutzer aktualisieren, um Die Mitarbeiter in Ihrer Organisation auf diese Änderung vorzubereiten. Geben Sie diese Office 365-Nachrichtenverschlüsselungsressourcen für Ihre Benutzer entsprechend an:

- [Senden, Anzeigen und Antworten auf verschlüsselte Nachrichten in Outlook für PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Microsoft 365 Essentials Video: Office-Nachrichtenverschlüsselung](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Anzeigen dieser Änderungen im Überwachungsprotokoll

Microsoft 365 überwacht diese Aktivität und stellt sie Administratoren zur Verfügung. Der Vorgang ist "New-TransportRule" und ein Codeausschnitt eines Beispiel-Überwachungseintrags aus der Überwachungsprotokollsuche im Security & Compliance Center ist unten aufgeführt:

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>So deaktivieren oder anpassen Sie die Richtlinie für vertrauliche Informationstypen

Nachdem Sie die Exchange-Nachrichtenflussregel erstellt [](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) haben, können Sie die Regel deaktivieren oder bearbeiten, indem Sie zu Nachrichtenflussregeln im Exchange Admin Center (EAC) gehen und die Regel " Verschlüsseln ausgehender vertraulicher E-Mails  >   *(Out-of-Box-Regel) "* deaktivieren.