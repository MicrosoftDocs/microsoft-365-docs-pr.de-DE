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
description: Nachdem Sie die Einrichtung Office 365 Nachrichtenverschlüsselung (OM) abgeschlossen haben, können Sie die Konfiguration Ihrer Bereitstellung auf verschiedene Weise anpassen. Beispielsweise können Sie konfigurieren, ob Sie einmalige Pass Codes aktivieren möchten, die Schaltfläche Protect in Outlook im Internet anzeigen und vieles mehr. In den Aufgaben in diesem Artikel wird beschrieben, wie.
ms.openlocfilehash: c235205535b4871deb1963a9113a82429917b75e
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2020
ms.locfileid: "42605299"
---
# <a name="manage-office-365-message-encryption"></a>Verwalten der Office 365-Nachrichtenverschlüsselung

Nachdem Sie die Einrichtung Office 365 Nachrichtenverschlüsselung (OM) abgeschlossen haben, können Sie die Konfiguration Ihrer Bereitstellung auf verschiedene Weise anpassen. Beispielsweise können Sie konfigurieren, ob Sie einmalige Pass Codes aktivieren möchten, die Schaltfläche **verschlüsseln** in Outlook im Internet anzeigen und vieles mehr. In den Aufgaben in diesem Artikel wird beschrieben, wie.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Verwalten, ob sich Google-, Yahoo-und Microsoft-Konto Empfänger mit diesen Konten beim Office 365 Nachrichten Verschlüsselungs Portal anmelden können

Wenn Sie die neuen Office 365 Nachrichten Verschlüsselungsfunktionen einrichten, können Benutzer in Ihrer Organisation Nachrichten an Empfänger senden, die sich außerhalb Ihrer Office 365 Organisation befinden. Wenn der Empfänger eine *soziale ID* wie ein Google-Konto, ein Yahoo-Konto oder ein Microsoft-Konto verwendet, kann sich der Empfänger beim OM-Portal mit einer sozialen ID anmelden. Wenn Sie möchten, können Sie festlegen, dass Empfänger keine sozialen IDs für die Anmeldung beim OM-Portal verwenden dürfen.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>So verwalten Sie, ob Empfänger soziale IDs verwenden können, um sich beim OM-Portal anzumelden
  
1. Stellen [Sie mithilfe von Remote-PowerShell eine Verbindung zu Exchange Online her](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).

2. Führen Sie das Cmdlet "OMEConfiguration" mit dem Parameter "SocialIdSignIn" wie folgt aus:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Um beispielsweise soziale IDs zu deaktivieren:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   So aktivieren Sie soziale IDs:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Verwalten der Verwendung von einmaligen Pass Codes für das Office 365 Nachrichten Verschlüsselungs Portal

Wenn der Empfänger einer Nachricht, die von OM verschlüsselt wurde, Outlook nicht verwendet, unabhängig vom vom Empfänger verwendeten Konto, erhält der Empfänger einen Link zur zeitlich begrenzten Webansicht, mit dem Sie die Nachricht lesen können. Dieser Link enthält einen One-Time-Pass-Code. Als Administrator können Sie entscheiden, ob Empfänger die einmaligen Pass Codes verwenden können, um sich beim OM-Portal anzumelden.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>So verwalten Sie, ob OM einen einmal Durchlaufcode generiert
  
1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Führen Sie das Cmdlet "OMEConfiguration" mit dem Parameter "OTPEnabled" aus:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   Beispielsweise zum Deaktivieren von einmaligen Pass Codes:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   So aktivieren Sie einmalige Pass Codes:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Verwalten der Anzeige der Schaltfläche "verschlüsseln" in Outlook im Internet

Als Administrator können Sie steuern, ob diese Schaltfläche Endbenutzern angezeigt werden soll.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>So verwalten Sie, ob die Schaltfläche Verschlüsseln in Outlook im Internet angezeigt wird
  
1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Führen Sie das Cmdlet "IRMConfiguration" mit dem-SimplifiedClientAccessEnabled-Parameter aus:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   Um beispielsweise die Schaltfläche **verschlüsseln** zu deaktivieren:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   So aktivieren Sie die Schaltfläche **verschlüsseln** :

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Aktivieren der dienstseitigen Entschlüsselung von e-Mail-Nachrichten für Benutzer von IOS Mail App

Die IOS Mail-App kann Nachrichten, die mit Office 365 Nachrichtenverschlüsselung geschützt sind, nicht entschlüsseln. Als Office 365 Administrator können Sie die dienstseitige Entschlüsselung für Nachrichten anwenden, die an die IOS-Mail-App übermittelt werden. Wenn Sie sich für die Verwendung der dienstseitigen Entschlüsselung entscheiden, sendet der Dienst eine entschlüsselte Kopie der Nachricht an das IOS-Gerät. Das Clientgerät speichert eine entschlüsselte Kopie der Nachricht. Die Nachricht behält auch Informationen zu Nutzungsrechten bei, obwohl die IOS-Mail-App keine clientseitigen Nutzungsrechte für den Benutzer anwendet. Der Benutzer kann die Nachricht auch dann kopieren oder ausdrucken, wenn er ursprünglich nicht über die Rechte dazu verfügt. Wenn der Benutzer jedoch versucht, eine Aktion abzuschließen, für die der Office 365-e-Mail-Server erforderlich ist, beispielsweise das Weiterleiten der Nachricht, wird die Aktion vom Server nicht zugelassen, wenn der Benutzer ursprünglich nicht über das Recht zum Verwenden des Benutzers verfügt. Endbenutzer können jedoch die Verwendungseinschränkung "nicht weiterleiten" umgehen, indem Sie die Nachricht von einem anderen Konto innerhalb der IOS-Mail-App weiterleiten. Unabhängig davon, ob Sie die dienstseitige Entschlüsselung von e-Mails einrichten, können Anlagen für verschlüsselte und Rechte geschützte Nachrichten nicht in der IOS-Mail-App angezeigt werden.
  
Wenn Sie nicht zulassen, dass entschlüsselte Nachrichten an Benutzer von IOS-Mail-apps gesendet werden, erhalten Benutzer eine Nachricht, die besagt, dass Sie nicht über die Berechtigung zum Anzeigen der Nachricht verfügen. Standardmäßig ist die dienstseitige Entschlüsselung von e-Mail-Nachrichten nicht aktiviert.
  
Weitere Informationen und eine Übersicht über die Clientumgebung finden Sie unter Anzeigen von [verschlüsselten Nachrichten auf Ihrem iPhone oder iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>So verwalten Sie, ob Benutzer von IOS-Mail-apps Nachrichten anzeigen können, die durch Office 365 Nachrichtenverschlüsselung geschützt sind
  
1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Führen Sie das Cmdlet "ActiveSyncOrganizations" mit dem Parameter "AllowRMSSupportForUnenlightenedApps" aus:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Beispielsweise zum Konfigurieren des Diensts zum Entschlüsseln von Nachrichten, bevor Sie an nicht aufgeklärte apps wie die IOS-Mail-App gesendet werden:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   Oder, um den Dienst so zu konfigurieren, dass entschlüsselte Nachrichten nicht an nicht aufgeklärte apps gesendet werden:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> Einzelne Postfachrichtlinien (OWA/ActiveSync) setzen diese Einstellungen außer Kraft (d. h., wenn-den IRMEnabled in der jeweiligen OWA-Postfachrichtlinie oder in der ActiveSync-Postfachrichtlinie auf false festgelegt ist, werden diese Konfigurationen nicht angewendet).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Aktivieren der dienstseitigen Entschlüsselung von e-Mail-Anlagen für Webbrowser-e-Mail-Clients

Normalerweise werden Anlagen automatisch verschlüsselt, wenn Sie Office 365 Nachrichtenverschlüsselung verwenden. Als Office 365 Administrator können Sie die dienstseitige Entschlüsselung für e-Mail-Anlagen anwenden, die von Benutzern aus einem Webbrowser heruntergeladen werden.
  
Wenn Sie die dienstseitige Entschlüsselung verwenden, sendet der Dienst eine entschlüsselte Kopie der Datei an das Gerät. Die Nachricht ist weiterhin verschlüsselt. Die e-Mail-Anlage behält auch Informationen zu Nutzungsrechten, obwohl der Browser keine clientseitigen Nutzungsrechte für den Benutzer anwendet. Der Benutzer kann die e-Mail-Anlage auch dann kopieren oder ausdrucken, wenn er ursprünglich nicht über die Rechte dazu verfügt. Wenn der Benutzer jedoch versucht, eine Aktion abzuschließen, für die der Office 365-e-Mail-Server erforderlich ist, beispielsweise das Weiterleiten der Anlage, wird die Aktion vom Server nicht zugelassen, wenn der Benutzer ursprünglich nicht über das Recht zum Verwenden verfügt.
  
Unabhängig davon, ob Sie die dienstseitige Entschlüsselung von Anlagen einrichten, können Benutzer keine Anlagen in verschlüsselter und mit rechten geschützter e-Mail in der IOS Mail-App anzeigen.
  
Wenn Sie entschlüsselte e-Mail-Anlagen nicht zulassen (Standardeinstellung), erhalten Benutzer eine Meldung, die besagt, dass Sie nicht über die Berechtigung zum Anzeigen der Anlage verfügen.
  
Weitere Informationen dazu, wie Office 365 die Verschlüsselung für e-Mails und e-Mail-Anlagen mit der Option "nur verschlüsseln" implementiert, finden Sie unter [verschlüsseln-only-Option für e-Mails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>So verwalten Sie, ob e-Mail-Anlagen beim Herunterladen aus einem Webbrowser entschlüsselt werden
  
1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Führen Sie das Cmdlet "IRMConfiguration" mit dem Parameter "DecryptAttachmentForEncryptOnly" aus:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   Um beispielsweise den Dienst so zu konfigurieren, dass e-Mail-Anlagen entschlüsselt werden, wenn ein Benutzer Sie von einem Webbrowser herunterlädt:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   So konfigurieren Sie den Dienst so, dass verschlüsselte e-Mail-Anlagen beim Herunterladen verlassen werden:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>Sicherstellen, dass alle externen Empfänger das OM-Portal zum Lesen verschlüsselter e-Mails verwenden

Sie können benutzerdefinierte Branding-Vorlagen verwenden, um zu erzwingen, dass Empfänger eine Wrapper-e-Mail erhalten, die Sie dazu leitet, verschlüsselte e-Mails im OM-Portal zu lesen, anstatt Outlook oder Outlook im Web zu verwenden. Dies empfiehlt sich, wenn Sie mehr Kontrolle über die Verwendung von e-Mails erhalten möchten, die von Empfängern verwendet werden. Wenn beispielsweise externe Empfänger e-Mails im Webportal anzeigen, können Sie ein Ablaufdatum für die e-Mail festlegen, und Sie können die e-Mail widerrufen. Diese Features werden nur über das OM-Portal unterstützt. Sie können die Option Verschlüsseln und die Option nicht weiterleiten beim Erstellen der Nachrichtenfluss Regeln verwenden.

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>Verwenden einer benutzerdefinierten Vorlage, um zu erzwingen, dass alle externen Empfänger das OM-Portal und für verschlüsselte e-Mails verwenden

1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Führen Sie das Cmdlet New-TransportRule aus:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    Dabei gilt:

   - `mail flow rule name`ist der Name, den Sie für die neue Nachrichtenfluss Regel verwenden möchten.

   - `option name`ist entweder `Encrypt` oder `Do Not Forward`.

   - `template name`ist der Name, den Sie beispielsweise `OME Configuration`der benutzerdefinierten Branding-Vorlage gegeben haben.

   So verschlüsseln Sie alle externen e-Mails mit der Vorlage "OM-Konfiguration" und wenden die Option "nur verschlüsseln" an:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   So verschlüsseln Sie alle externen e-Mails mit der Vorlage "OM-Konfiguration" und wenden die Option "nicht weiterleiten" an:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Anpassen der Darstellung von e-Mail-Nachrichten und des OM-Portals

Ausführliche Informationen dazu, wie Sie OM für Ihre Organisation anpassen können, finden Sie unter [Hinzufügen der Marke Ihrer Organisation zu ihren verschlüsselten Nachrichten](add-your-organization-brand-to-encrypted-messages.md).
  
## <a name="disable-the-new-capabilities-for-ome"></a>Deaktivieren der neuen Funktionen für OM

Wir hoffen, dass es nicht dazu kommt, aber wenn Sie dies benötigen, ist die Deaktivierung der neuen Funktionen für OM sehr einfach. Zunächst müssen Sie alle e-Mail-Flussregeln, die Sie erstellt haben, mit den neuen OM-Funktionen entfernen. Informationen zum Entfernen von Nachrichtenfluss Regeln finden Sie unter [Manage Mail Flow Rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Führen Sie dann die folgenden Schritte in Exchange Online PowerShell aus.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>So deaktivieren Sie die neuen Funktionen für OM
  
1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Wenn Sie die Schaltfläche **verschlüsseln** in Outlook im Internet aktiviert haben, deaktivieren Sie Sie, indem Sie das CmdletSet-IRMConfiguration mit dem Parameter SimplifiedClientAccessEnabled ausführen. Andernfalls können Sie diesen Schritt überspringen.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Deaktivieren Sie die neuen Funktionen für OM, indem Sie das Cmdlet "IRMConfiguration" ausführen, wobei der Parameter "AzureRMSLicensingEnabled" auf "false" festgelegt ist:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
