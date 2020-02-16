---
title: Hinzufügen Ihrer Unternehmensmarke zu verschlüsselten Nachrichten
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Als Office 365 globaler Administrator können Sie das Branding Ihrer Organisation auf die verschlüsselten e-Mail-Nachrichten Ihrer Organisation und auf den Inhalt des Verschlüsselungs Portals anwenden.
ms.openlocfilehash: 23b6cd205c4ae3a0ca08aab2209e0152a3f78b63
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079977"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>Hinzufügen der Marke Ihres Unternehmens zu Ihren verschlüsselten Nachrichten

Als Exchange Online-oder Exchange Online Protection-Administrator können Sie Ihr Firmenbranding anwenden, um das Aussehen der e-Mail-Nachrichten der Office 365 Nachrichtenverschlüsselung Ihrer Organisation und den Inhalt des Verschlüsselungs Portals anzupassen. Mithilfe der Cmdlets "Get-OMEConfiguration" und "OMEConfiguration Windows PowerShell" können Sie die folgenden Aspekte der Anzeige Erfahrung für Empfänger von verschlüsselten e-Mail-Nachrichten anpassen:
  
- Einleitender Text der E-Mail, die die verschlüsselte Nachricht enthält

- Text des Haftungsausschlusses der E-Mail, die die verschlüsselte Nachricht enthält

- Text, der im OM-Portal angezeigt wird

- Logo, das in der e-Mail-Nachricht und im OM-Portal angezeigt wird, oder ob ein Logo überhaupt verwendet werden soll

- Hintergrundfarbe in der e-Mail-Nachricht und im OM-Portal

Sie können auch jederzeit zum Standardaussehen und -verhalten zurückkehren.

Wenn Sie mehr Kontrolle wünschen, können Sie Office 365 erweiterte Nachrichtenverschlüsselung verwenden und mehrere Vorlagen für verschlüsselte e-Mails erstellen, die von Ihrer Organisation stammen. Mithilfe dieser Vorlagen können Sie mehr als nur das Aussehen und Verhalten der e-Mail-Nachrichten steuern, aber auch Teile der Endbenutzeroberfläche steuern. Sie können beispielsweise angeben, ob Empfänger von e-Mails, auf die diese Vorlage angewendet wird, und wer Google, Yahoo und Microsoft-Konten verwendet, diese Konten zum Anmelden beim Office 365 Nachrichten Verschlüsselungs Portal verwenden können. Sie können Vorlagen verwenden, um mehrere Anwendungsfälle zu erfüllen, beispielsweise:

- Vorlagen für jede Abteilung, beispielsweise Finanzen, Vertrieb usw.

- Vorlagen für verschiedene Produkte

- Vorlagen für unterschiedliche geographische Regionen oder Länder

- Ob Sie das Widerrufen von e-Mails zulassen möchten

- Ob e-Mail-Nachrichten, die an externe Empfänger gesendet werden sollen, nach einer festgelegten Anzahl von Tagen ablaufen.

Nachdem Sie die Vorlagen erstellt haben, können Sie Sie mithilfe von Exchange-Nachrichtenfluss Regeln auf verschlüsselte e-Mail-Nachrichten anwenden. Wenn Sie Office 365 erweiterte Nachrichtenverschlüsselung haben, können Sie jede e-Mail-Nachricht widerrufen, die Sie mit diesen Vorlagen gebrandmarkt haben.

## <a name="work-with-ome-branding-templates"></a>Arbeiten mit Branding-Vorlagen für OM

Sie können mehrere Features in einer Branding-Vorlage ändern. Sie können die Standardvorlage ändern, aber nicht entfernen. Wenn Sie erweiterte Nachrichtenverschlüsselung haben, können Sie auch benutzerdefinierte Vorlagen erstellen, ändern und entfernen. Verwenden Sie Windows PowerShell, um gleichzeitig mit einer Branding-Vorlage zu arbeiten. Sie benötigen ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, um diese Cmdlets zu verwenden.

- [Festlegen-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-omeconfiguration) -ändern Sie die standardmäßige Branding-Vorlage oder eine benutzerdefinierte Branding-Vorlage, die Sie erstellt haben.
- [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) -erstellen Sie eine neue Branding-Vorlage, nur erweiterte Nachrichtenverschlüsselung.
- [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/remove-omeconfiguration) – Entfernen einer benutzerdefinierten Branding-Vorlage, nur erweiterte Nachrichtenverschlüsselung. Die standardmäßige Branding-Vorlage kann nicht gelöscht werden.
  
## <a name="modify-an-ome-branding-template"></a>Ändern einer OM-Branding-Vorlage

Verwenden Sie Windows PowerShell, um eine Branding-Vorlage gleichzeitig zu ändern. Wenn Sie erweiterte Nachrichtenverschlüsselung haben, können Sie auch benutzerdefinierte Vorlagen erstellen, ändern und entfernen.

1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ändern Sie die Vorlage mithilfe des Cmdlets "OMEConfiguration", wie unter " [festlegen-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration) " beschrieben, oder verwenden Sie die folgende Grafik und Tabelle, um Anleitungen zu geben.

![Anpassbare e-Mail-Teile](../media/ome-template-breakout.png)

|**So passen Sie dieses Verschlüsselungsfeature an**|**Verwenden Sie diese Befehle**|
|:-----|:-----|
|Hintergrundfarbe|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|Logo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Unterstützte Dateiformate: .png, .jpg, .bmp oder .tiff  <br/> Optimale Größe der Logodatei: weniger als 40 KB  <br/> Optimale Größe des Logo Bilds: 170 Pixel. Wenn Ihr Bild diese Dimensionen überschreitet, ändert der Dienst Ihr Logo so, dass es im Portal angezeigt wird. Der Dienst ändert die Grafikdatei selbst nicht. Um optimale Ergebnisse zu erzielen, verwenden Sie die optimale Größe.|
|Text neben dem Namen und der e-Mail-Adresse des Absenders|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Text, der auf der Schaltfläche "Nachricht lesen" angezeigt wird|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Text, der oberhalb der Schaltfläche "Nachricht lesen" angezeigt wird|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|Haftungsausschluss in der E-Mail, die die verschlüsselte Nachricht enthält|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Der Text wird oben im Anzeigeportal für verschlüsselte E-Mails angezeigt|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|So aktivieren oder deaktivieren Sie die Authentifizierung mithilfe eines einmaligen Pass Codes für diese benutzerdefinierte Vorlage|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **Beispiele:** <br/>So aktivieren Sie einmalige Kennwörter für diese benutzerdefinierte Vorlage <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> So deaktivieren Sie einmalige Kennwörter für diese benutzerdefinierte Vorlage <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|So aktivieren oder deaktivieren Sie die Authentifizierung mit Microsoft-, Google-oder Yahoo-Identitäten für diese benutzerdefinierte Vorlage|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **Beispiele:** <br/>So aktivieren Sie soziale IDs für diese benutzerdefinierte Vorlage <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> So deaktivieren Sie soziale IDs für diese benutzerdefinierte Vorlage <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Erstellen einer OM-Branding-Vorlage (Erweiterte Nachrichtenverschlüsselung)

Wenn Sie Office 365 erweiterte Nachrichtenverschlüsselung haben, können Sie mithilfe des Cmdlets [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) benutzerdefinierte Branding-Vorlagen für Ihre Organisation erstellen. Nachdem Sie die Vorlage erstellt haben, ändern Sie die Vorlage mit dem Cmdlet "OMEConfiguration", wie unter [Modify a OM Branding Template](#modify-an-ome-branding-template)beschrieben. Sie können mehrere Vorlagen erstellen.

So erstellen Sie eine neue benutzerdefinierte Branding-Vorlage:

1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Verwenden Sie das Cmdlet [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) , um eine neue Vorlage zu erstellen.

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```

   Beispiele:

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>Zurückgeben der standardmäßigen Branding-Vorlage auf die ursprünglichen Werte

Führen Sie die folgenden Schritte aus, um alle Änderungen aus der Standardvorlage, einschließlich Marken Anpassungen usw., zu entfernen:
  
1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Verwenden Sie das Cmdlet " **OMEConfiguration** " wie unter " [festlegen-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)" beschrieben. Wenn Sie die Marken Anpassungen ihrer Organisation aus den DisclaimerText-, EmailText-und Portal Text-Werten entfernen möchten, legen Sie den Wert auf eine `""`leere Zeichenfolge fest. Legen Sie für alle Bild Werte wie Logo den Wert auf `"$null"`fest.

   In der folgenden Tabelle werden die Standardeinstellungen für die Verschlüsselungs Anpassungsoption beschrieben.

   **Dieses Feature der Verschlüsselungserfahrung zu Standardtext und -bild zurücksetzen**|**Verwenden Sie diese Befehle**|
   |:-----|:-----|
   |Standardtext, der verschlüsselten E-Mail-Nachrichten beigefügt ist  <br/> Der Standardtext wird über den Anweisungen zum Betrachten von verschlüsselten Nachrichten angezeigt|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |Haftungsausschluss in der E-Mail, die die verschlüsselte Nachricht enthält|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |Der Text wird oben im Anzeigeportal für verschlüsselte E-Mails angezeigt|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Beispiel Zurücksetzen auf Standard:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Logo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Beispiel Zurücksetzen auf Standard:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Hintergrundfarbe|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **Beispiel Zurücksetzen auf Standard:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Entfernen einer benutzerdefinierten Branding-Vorlage (Erweiterte Nachrichtenverschlüsselung)

Sie können nur Branding-Vorlagen entfernen oder löschen, die Sie erstellt haben. Sie können die standardmäßige Branding-Vorlage nicht entfernen.

So entfernen Sie eine benutzerdefinierte Branding-Vorlage:
  
1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Verwenden Sie das Cmdlet **Remove-OMEConfiguration** wie folgt:

   ```powershell
   Remove-OMEConfiguration -Identity "<OMEConfigurationIdParameter>
   ```

   Beispiele:

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Weitere Informationen finden Sie unter [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/remove-omeconfiguration).

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Erstellen einer Exchange-Nachrichtenfluss Regel, die Ihr benutzerdefiniertes Branding auf verschlüsselte e-Mails anwendet

Nachdem Sie entweder die Standardvorlage geändert oder neue Branding-Vorlagen erstellt haben, können Sie Exchange-Nachrichtenfluss Regeln erstellen, um Ihr benutzerdefiniertes Branding basierend auf bestimmten Bedingungen anzuwenden. In den folgenden Szenarien wird eine solche Regel benutzerdefiniertes Branding anwenden:

- Wenn die e-Mail manuell vom Endbenutzer aus dem Outlook oder Outlook im Internet (früher als Outlook Web App bezeichnet)-Clients verschlüsselt wurde

- Wenn die e-Mail-Nachricht automatisch von einer Exchange-Nachrichtenfluss Regel oder Office 365 Richtlinie zur Verhinderung von Datenverlusten verschlüsselt wurde

Informationen zum Erstellen einer Exchange-Nachrichtenfluss Regel, die Verschlüsselung zutrifft, finden Sie unter [define Mail Flow Rules to encrypt Email Messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. Melden Sie sich in einem Webbrowser mit einem Arbeits-oder Schulkonto, dem globale Administratorberechtigungen erteilt wurden, bei [Office 365 an](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Wählen Sie die Kachel **Admin** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin** \> Center **Exchange**aus.

4. Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** , und](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> wählen Sie **Neues** ![neues Symbol neue **Regel erstellen**aus. Weitere Informationen zur Verwendung der Exchange-Verwaltungskonsole finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. Geben Sie unter **Name**einen Namen für die Regel ein, beispielsweise Branding für die Vertriebsabteilung.

6. Wählen Sie unter **diese Regel anwenden, wenn**aus der Liste der verfügbaren Bedingungen die Bedingung aus, in der sich **der Absender innerhalb der Organisation befindet** , sowie weitere gewünschte Bedingungen aus. Beispielsweise können Sie eine bestimmte Branding-Vorlage auf Folgendes anwenden:

   - Alle verschlüsselten e-Mails, die von Mitgliedern der Finanzabteilung gesendet wurden
   - Verschlüsselte e-Mails, die mit einem bestimmten Schlüsselwort wie "extern" oder "Partner" gesendet werden
   - Verschlüsselte e-Mails, die an eine bestimmte Domäne gesendet werden

7. Wählen Sie unter **gehen Sie wie folgt**vor die Option **Nachrichtensicherheit** > **anwenden benutzerdefiniertes Branding auf OM-Nachrichten**ändern aus. Wählen Sie dann in der Dropdownliste eine Branding-Vorlage aus den von Ihnen erstellten oder geänderten.

8. Optional Wenn die e-Mail-Fluss Regel zusätzlich zum benutzerdefinierten Branding Verschlüsselung angewendet werden soll, wählen **Sie die Option** **Nachrichtensicherheit ändern**aus, und wählen Sie dann **Office 365 Nachrichtenverschlüsselung und Rechte Schutz anwenden**aus. Wählen Sie in der Liste eine RMS-Vorlage aus, wählen Sie **Speichern**aus, und klicken Sie dann auf **OK**.
  
   Die Liste der Vorlagen enthält alle Standardvorlagen und-Optionen sowie benutzerdefinierte Vorlagen, die Sie zur Verwendung durch Office 365 erstellt haben. Wenn die Liste leer ist, stellen Sie sicher, dass Sie Office 365 Nachrichtenverschlüsselung mit den neuen Funktionen eingerichtet haben, wie unter [Einrichten neuer Office 365 Nachrichten Verschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md)beschrieben. Informationen zu den Standardvorlagen finden Sie unter [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Informationen zur Option " **nicht weiterleiten** " finden Sie unter [do not Forward Option for Emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Informationen zur Option **nur verschlüsseln** finden Sie unter [verschlüsseln nur Option for Emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Wählen Sie **Aktion hinzufügen** aus, wenn Sie eine andere Aktion angeben möchten.
