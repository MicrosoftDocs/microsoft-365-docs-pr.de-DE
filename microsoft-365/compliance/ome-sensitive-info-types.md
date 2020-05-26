---
title: Erstellen einer Richtlinie für vertrauliche Informationstypen für Ihre Organisation mithilfe der Nachrichtenverschlüsselung
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
description: Hier erfahren Sie, wie Sie mit Office 365 Nachrichtenverschlüsselung eine Richtlinie für vertrauliche Informationstypen für Ihre Organisation erstellen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: da459ab5e92592f86bc32d7dd9d648de24b9a3ed
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352068"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>Erstellen einer Richtlinie für vertrauliche Informationstypen für Ihre Organisation mithilfe der Nachrichtenverschlüsselung

Sie können entweder Exchange-Nachrichtenfluss Regeln oder DLP (Data Loss Prevention) verwenden, um eine Richtlinie für vertrauliche Informationstypen mit Office 365 Nachrichtenverschlüsselung zu erstellen. Zum Erstellen einer Exchange-Nachrichtenfluss Regel können Sie entweder die Exchange-Verwaltungskonsole (EAC) oder die PowerShell verwenden.

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>So erstellen Sie die Richtlinie mithilfe von Nachrichtenfluss Regeln in der Exchange-Verwaltungskonsole

Melden Sie sich bei der Exchange-Verwaltungskonsole an, und wechseln Sie zu **Nachrichtenfluss**  >  **Regeln**. Erstellen Sie auf der Seite Regeln eine Regel, die Office 365 Nachrichtenverschlüsselung zutrifft. Sie können eine Regel basierend auf Bedingungen wie dem vorhanden sein bestimmter Schlüsselwörter oder vertraulicher Informationstypen in der Nachricht oder Anlage erstellen.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>So erstellen Sie die Richtlinie mithilfe von Nachrichtenfluss Regeln in PowerShell

Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell). Verwenden Sie die Cmdlets Sets-IRMConfiguration und New-TransportRule, um die Richtlinie zu erstellen.

## <a name="example-mail-flow-rule-created-with-powershell"></a>Beispiel für Nachrichtenfluss Regel, die mit PowerShell erstellt wurde

Führen Sie die folgenden Befehle in PowerShell aus, um eine Exchange-Nachrichtenfluss Regel zu erstellen, die e-Mails, die außerhalb Ihrer Organisation gesendet werden, automatisch mit der *verschlüsselten* Richtlinie verschlüsselt, wenn die e-Mails oder deren Anlagen die folgenden Typen vertraulicher Informationen enthalten:

- ABA-Routingnummer
- Kreditkartennummer
- Drug Enforcement Agency (DEA)-Nummer
- USA/U.K. passport number
- US-Bank Kontonummer
- US-Steueridentifikationsnummer (ITIN)
- US-Sozialversicherungsnummer

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

Weitere Informationen finden Sie unter [Sets-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration?view=exchange-ps) und [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule?view=exchange-ps).

## <a name="how-recipients-access-attachments"></a>Zugriff auf Anlagen durch Empfänger

Nachdem Microsoft eine Nachricht verschlüsselt hat, haben die Empfänger uneingeschränkten Zugriff auf Anlagen, wenn Sie auf Ihre verschlüsselte e-Mail zugreifen und diese öffnen.

## <a name="to-prepare-for-this-change"></a>So bereiten Sie diese Änderung vor

Möglicherweise möchten Sie alle anwendbaren Endbenutzer Dokumentationen und Schulungsunterlagen aktualisieren, um Personen in Ihrer Organisation für diese Änderung vorzubereiten. Geben Sie diese Office 365 Nachrichten Verschlüsselungs Ressourcen für Ihre Benutzer frei, je nach Bedarf:

- [Senden, anzeigen und beantworten von verschlüsselten Nachrichten in Outlook für PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Microsoft 365 Essentials-Video: Office-Nachrichtenverschlüsselung](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Anzeigen dieser Änderungen im Überwachungsprotokoll

Microsoft 365 überwacht diese Aktivität und stellt Sie Administratoren zur Verfügung. Der Vorgang ist "New-TransportRule" und ein Ausschnitt eines Beispiel Überwachungseintrags aus der Überwachungsprotokoll Suche im Security & Compliance Center ist unten:

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>So deaktivieren oder ändern Sie die Richtlinie für vertrauliche Informationstypen

Nachdem Sie die Exchange-Nachrichtenfluss Regel erstellt haben, können Sie [die Regel deaktivieren oder bearbeiten](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) , indem Sie im Exchange Admin Center (EAC) zu **Nachrichtenfluss**  >  **Regeln** wechseln und die Regel "*ausgehende vertrauliche e-Mails verschlüsseln (Out-of-Box-Regel)*" deaktivieren.
