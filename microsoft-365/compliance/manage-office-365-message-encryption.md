---
title: Verwalten der Office 365-Nachrichtenverschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Nachdem Sie die Einrichtung von Office 365-Nachrichtenverschlüsselung (OME) abgeschlossen haben, erfahren Sie, wie Sie Ihre Bereitstellung auf verschiedene Weise anpassen.
ms.openlocfilehash: 06e9d22d51c05fe9f7bc4c1a014607feafbf2dba
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908185"
---
# <a name="manage-office-365-message-encryption"></a>Verwalten der Office 365-Nachrichtenverschlüsselung

Nachdem Sie die Einrichtung von Office 365-Nachrichtenverschlüsselung (OME) abgeschlossen haben, können Sie die Konfiguration Ihrer Bereitstellung auf verschiedene Weise anpassen. Sie können z. B. konfigurieren, ob Einmalpasscodes aktiviert, die Schaltfläche Verschlüsseln in Outlook im Web angezeigt werden soll und vieles mehr.  Die Aufgaben in diesem Artikel beschreiben, wie.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Verwalten, ob Google-, Yahoo- und Microsoft-Kontoempfänger diese Konten verwenden können, um sich beim Office 365-Nachrichtenverschlüsselung anmelden

Wenn Sie die neuen Office 365-Nachrichtenverschlüsselung einrichten, können Benutzer in Ihrer Organisation Nachrichten an Empfänger senden, die sich außerhalb Ihrer Organisation befinden. Wenn der Empfänger eine soziale *ID* wie ein Google-, Yahoo- oder Microsoft-Konto verwendet, kann sich der Empfänger mit einer sozialen ID beim OME-Portal anmelden. Wenn Sie möchten, können Sie festlegen, dass Empfänger keine sozialen IDs für die Anmeldung beim OME-Portal verwenden dürfen.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>So verwalten Sie, ob Empfänger soziale IDs zum Anmelden beim OME-Portal verwenden können
  
1. [Verbinden, Exchange Online Remote PowerShell zu verwenden.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Führen Sie Set-OMEConfiguration cmdlet mit dem Parameter SocialIdSignIn wie folgt aus:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   So deaktivieren Sie beispielsweise soziale IDs:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   So aktivieren Sie soziale IDs:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Verwalten der Verwendung von Einmalpasscodes für das Office 365-Nachrichtenverschlüsselung

Wenn der Empfänger einer von OME verschlüsselten Nachricht Outlook nicht verwendet, empfängt der Empfänger unabhängig vom vom Empfänger verwendeten Konto einen zeitlich begrenzten Webansichtslink, über den er die Nachricht lesen kann. Dieser Link enthält einen einmal übergebenen Code. Als Administrator können Sie entscheiden, ob Empfänger Einmalpasscodes verwenden können, um sich beim OME-Portal zu anmelden.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>So verwalten Sie, ob OME Einmalpasscodes generiert
  
1. Verwenden Sie ein Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie Set-OMEConfiguration cmdlet mit dem PARAMETER OTPEnabled aus:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   So deaktivieren Sie beispielsweise einmal bestandene Codes:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   So aktivieren Sie einmal bestandene Codes:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Verwalten der Anzeige der Schaltfläche Verschlüsseln in Outlook im Web

Als Administrator können Sie verwalten, ob diese Schaltfläche endbenutzern angezeigt werden soll.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>So verwalten Sie, ob die Schaltfläche Verschlüsseln im Outlook im Web angezeigt wird
  
1. Verwenden Sie ein Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie Set-IRMConfiguration cmdlet mit dem Parameter -SimplifiedClientAccessEnabled aus:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   So deaktivieren Sie beispielsweise die Schaltfläche **Verschlüsseln:**

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   So aktivieren Sie die **Schaltfläche** Verschlüsseln:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Aktivieren der dienstseitigen Entschlüsselung von E-Mail-Nachrichten für iOS-E-Mail-App-Benutzer

Die iOS-E-Mail-App kann Nachrichten, die mit nachrichtengeschützt sind, nicht Office 365-Nachrichtenverschlüsselung. Als Microsoft 365 können Sie die dienstseitige Entschlüsselung für Nachrichten anwenden, die an die iOS-Mail-App übermittelt werden. Wenn Sie die dienstseitige Entschlüsselung verwenden, sendet der Dienst eine entschlüsselte Kopie der Nachricht an das iOS-Gerät. Das Clientgerät speichert eine entschlüsselte Kopie der Nachricht. Die Nachricht behält auch Informationen zu Nutzungsrechten bei, auch wenn die iOS-Mail-App keine clientseitigen Nutzungsrechte auf den Benutzer angewendet hat. Der Benutzer kann die Nachricht auch dann kopieren oder drucken, wenn er ursprünglich nicht die Rechte dazu hatte. Wenn der Benutzer jedoch versucht, eine Aktion zu vollenden, die den Microsoft 365-E-Mail-Server erfordert, z. B. das Weiterleiten der Nachricht, erlaubt der Server die Aktion nicht, wenn der Benutzer ursprünglich nicht das Nutzungsrecht dazu hatte. Endbenutzer können die Verwendungseinschränkung "Do Not Forward" jedoch umgehen, indem sie die Nachricht von einem anderen Konto in der iOS-Mail-App weiterleiten. Unabhängig davon, ob Sie die dienstseitige Entschlüsselung von E-Mails einrichten, können Anlagen für verschlüsselte und rechtegeschützte E-Mails nicht in der iOS-Mail-App angezeigt werden.
  
Wenn Sie das Senden entschlüsselter Nachrichten an iOS-E-Mail-App-Benutzer nicht zulassen möchten, erhalten Benutzer eine Meldung, die besagt, dass sie nicht über die Rechte zum Anzeigen der Nachricht verfügen. Standardmäßig ist die dienstseitige Entschlüsselung von E-Mail-Nachrichten nicht aktiviert.
  
Weitere Informationen und eine Ansicht der Clienterfahrung finden Sie unter Anzeigen verschlüsselter Nachrichten auf Ihrem iPhone [oder iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>So verwalten Sie, ob iOS-E-Mail-App-Benutzer Nachrichten anzeigen können, die durch Office 365-Nachrichtenverschlüsselung
  
1. Verwenden Sie ein Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie Set-ActiveSyncOrganizations cmdlet mit dem Parameter AllowRMSSupportForUnenlightenedApps aus:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   So konfigurieren Sie den Dienst beispielsweise so, dass Nachrichten entschlüsselt werden, bevor sie an nicht aufleuchtete Apps wie die iOS-Mail-App gesendet werden:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   Oder, um den Dienst so zu konfigurieren, dass entschlüsselte Nachrichten nicht an nicht entschlüsselte Apps gesendet werden:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> Einzelne Postfachrichtlinien (OWA/ActiveSync) überschreiben diese Einstellungen (d. h., wenn -IRMEnabled in der entsprechenden OWA-Postfachrichtlinie auf False festgelegt ist, oder ActiveSync-Postfachrichtlinie, dann würden diese Konfigurationen nicht angewendet werden).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Aktivieren der dienstseitigen Entschlüsselung von E-Mail-Anlagen für Webbrowser-E-Mail-Clients

Normalerweise werden Anlagen automatisch verschlüsselt, Office 365 nachrichtenverschlüsselung verwenden. Als Administrator können Sie die dienstseitige Entschlüsselung für E-Mail-Anlagen anwenden, die Benutzer aus einem Webbrowser herunterladen.
  
Wenn Sie die dienstseitige Entschlüsselung verwenden, sendet der Dienst eine entschlüsselte Kopie der Datei an das Gerät. Die Nachricht ist weiterhin verschlüsselt. Die E-Mail-Anlage speichert auch Informationen zu Nutzungsrechten, auch wenn der Browser keine clientseitigen Nutzungsrechte auf den Benutzer angewendet hat. Der Benutzer kann die E-Mail-Anlage auch dann kopieren oder drucken, wenn er ursprünglich nicht die Rechte dazu hatte. Wenn der Benutzer jedoch versucht, eine Aktion zu vollenden, die den Microsoft 365-E-Mail-Server erfordert, z. B. das Weiterleiten der Anlage, erlaubt der Server die Aktion nicht, wenn der Benutzer ursprünglich nicht das Nutzungsrecht dazu hatte.
  
Unabhängig davon, ob Sie die dienstseitige Entschlüsselung von Anlagen einrichten, können Benutzer keine Anlagen für verschlüsselte und rechtegeschützte E-Mails in der iOS-Mail-App anzeigen.
  
Wenn Sie entschlüsselte E-Mail-Anlagen nicht zulassen möchten, was die Standardeinstellung ist, erhalten Benutzer eine Meldung, die besagt, dass sie nicht über die Rechte zum Anzeigen der Anlage verfügen.
  
Weitere Informationen dazu, wie Microsoft 365 verschlüsselung für [E-Mails und E-Mail-Anlagen](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails) mit der Option Encrypt-Only implementieren, finden Sie unter Encrypt-Only option for emails.
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>So verwalten Sie, ob E-Mail-Anlagen beim Herunterladen aus einem Webbrowser entschlüsselt werden
  
1. Verwenden Sie ein Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie Set-IRMConfiguration cmdlet mit dem Parameter DecryptAttachmentForEncryptOnly aus:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   So konfigurieren Sie den Dienst beispielsweise so, dass E-Mail-Anlagen entschlüsselt werden, wenn ein Benutzer sie aus einem Webbrowser herunterlädt:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   So konfigurieren Sie den Dienst so, dass verschlüsselte E-Mail-Anlagen beim Download hinterlassen werden:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>Sicherstellen, dass alle externen Empfänger das OME-Portal zum Lesen verschlüsselter E-Mails verwenden

Sie können benutzerdefinierte Brandingvorlagen verwenden, um empfängern den Empfang einer Wrapper-E-Mail zu erzwingen, die sie zum Lesen verschlüsselter E-Mails im OME-Portal anstatt Outlook oder Outlook im Web leitet. Sie können dies tun, wenn Sie eine bessere Kontrolle darüber wünschen, wie Empfänger die empfangenen E-Mails verwenden. Wenn externe Empfänger beispielsweise E-Mails im Webportal anzeigen, können Sie ein Ablaufdatum für die E-Mail festlegen und die E-Mail widerrufen. Diese Features werden nur über das OME-Portal unterstützt. Sie können die Option Verschlüsseln und die Option Nicht weiterleiten verwenden, wenn Sie die Nachrichtenflussregeln erstellen.

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>Verwenden einer benutzerdefinierten Vorlage, um alle externen Empfänger zur Verwendung des OME-Portals und für verschlüsselte E-Mails zu zwingen

1. Verwenden Sie ein Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie New-TransportRule cmdlet aus:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    Dabei gilt:

   - `mail flow rule name` ist der Name, den Sie für die neue Nachrichtenflussregel verwenden möchten.

   - `option name` ist entweder `Encrypt` oder `Do Not Forward` .

   - `template name` ist der Name, den Sie der benutzerdefinierten Brandingvorlage gegeben haben, z. B. `OME Configuration` .

   So verschlüsseln Sie alle externen E-Mails mit der Vorlage "OME-Konfiguration", und wenden Sie die Encrypt-Only an:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   So verschlüsseln Sie alle externen E-Mails mit der Vorlage "OME-Konfiguration", und wenden Sie die Option Nicht weiterleiten an:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Anpassen der Darstellung von E-Mail-Nachrichten und des OME-Portals

Ausführliche Informationen dazu, wie Sie OME für Ihre Organisation anpassen können, finden Sie unter [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).
  
## <a name="disable-the-new-capabilities-for-ome"></a>Deaktivieren der neuen Funktionen für OME

We hope it doesn't come to it, but if you need, disabling the new capabilities for OME is very straightforward. Zunächst müssen Sie alle von Ihnen erstellten Nachrichtenflussregeln entfernen, die die neuen OME-Funktionen verwenden. Informationen zum Entfernen von Nachrichtenflussregeln finden Sie unter [Verwalten von Nachrichtenflussregeln](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules). Führen Sie dann die folgenden Schritte in Exchange Online PowerShell aus.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>So deaktivieren Sie die neuen Funktionen für OME
  
1. Starten Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Windows PowerShell und stellen Sie eine Verbindung mit Exchange Online. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Wenn Sie die Schaltfläche **Verschlüsseln** im Outlook aktiviert haben, deaktivieren Sie sie, indem Sie das cmdlet Set-IRMConfiguration mit dem Parameter SimplifiedClientAccessEnabled ausführen. Überspringen Sie andernfalls diesen Schritt.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Deaktivieren Sie die neuen Funktionen für OME, indem Sie das cmdlet Set-IRMConfiguration ausführen, für das der Parameter AzureRMSLicensingEnabled auf false festgelegt ist:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```