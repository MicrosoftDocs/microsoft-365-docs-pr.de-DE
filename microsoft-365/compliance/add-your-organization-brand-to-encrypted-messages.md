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
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Erfahren Sie, wie Office 365 globale Administratoren das Branding Ihrer Organisation auf verschlüsselte e-Mail-Nachrichten & Inhalt des Verschlüsselungs Portals anwenden können.
ms.openlocfilehash: 77fd5e08afa1a4d8ae5f6386fa65b88b6ea2be4d
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663232"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>Hinzufügen der Marke Ihrer Organisation zu ihren verschlüsselten Nachrichten in Microsoft 365 for Business-Nachrichtenverschlüsselung

Sie können das Branding Ihres Unternehmens anwenden, um das Aussehen der e-Mail-Nachrichten Ihrer Organisation und des Verschlüsselungs Portals anzupassen. Sie müssen globale Administratorberechtigungen auf Ihr Arbeits-oder Schulkonto anwenden, bevor Sie mit dem ersten Einstieg beginnen können. Nachdem Sie über diese Berechtigungen verfügen, verwenden Sie die Cmdlets Get-OMEConfiguration und Set-OMEConfiguration Windows PowerShell, um diese Teile von verschlüsselten e-Mail-Nachrichten anzupassen:
  
- Einführungstext

- Disclaimer text

- URL für die Datenschutzerklärung Ihrer Organisation

- Text im OM-Portal

- Logo, das in der e-Mail-Nachricht und im OM-Portal angezeigt wird, oder ob ein Logo überhaupt verwendet werden soll

- Hintergrundfarbe in der e-Mail-Nachricht und im OM-Portal

Sie können auch jederzeit zum Standardaussehen und -verhalten zurückkehren.

Wenn Sie mehr Kontrolle wünschen, verwenden Sie Office 365 erweiterte Nachrichtenverschlüsselung, um mehrere Vorlagen für verschlüsselte e-Mails zu erstellen, die von Ihrer Organisation stammen. Verwenden Sie diese Vorlagen, um Teile der Benutzeroberfläche zu steuern. Geben Sie beispielsweise an, ob Empfänger Google-, Yahoo-und Microsoft-Konten verwenden können, um sich beim Verschlüsselungs Portal anzumelden. Verwenden Sie Vorlagen, um mehrere Anwendungsfälle zu erfüllen, beispielsweise:

- Einzelne Abteilungen wie Finanzen, Vertrieb usw.

- Verschiedene Produkte

- Unterschiedliche geographische Regionen oder Länder

- Ob Sie das Widerrufen von e-Mails zulassen möchten

- Ob e-Mail-Nachrichten, die an externe Empfänger gesendet werden sollen, nach einer festgelegten Anzahl von Tagen ablaufen.

Nachdem Sie die Vorlagen erstellt haben, können Sie Sie mithilfe von Exchange-Nachrichtenfluss Regeln auf verschlüsselte e-Mail-Nachrichten anwenden. Wenn Sie Office 365 erweiterte Nachrichtenverschlüsselung haben, können Sie jede e-Mail-Nachricht widerrufen, die Sie mit diesen Vorlagen gebrandmarkt haben.

## <a name="work-with-ome-branding-templates"></a>Arbeiten mit Branding-Vorlagen für OM

Sie können mehrere Features in einer Branding-Vorlage ändern. Sie können die Standardvorlage ändern, aber nicht entfernen. Wenn Sie erweiterte Nachrichtenverschlüsselung haben, können Sie auch benutzerdefinierte Vorlagen erstellen, ändern und entfernen. Verwenden Sie Windows PowerShell, um gleichzeitig mit einer Branding-Vorlage zu arbeiten.

- [Festlegen-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) -ändern Sie die standardmäßige Branding-Vorlage oder eine benutzerdefinierte Branding-Vorlage, die Sie erstellt haben.
- [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) -erstellen Sie eine neue Branding-Vorlage, nur erweiterte Nachrichtenverschlüsselung.
- [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) – Entfernen einer benutzerdefinierten Branding-Vorlage, nur erweiterte Nachrichtenverschlüsselung. Die standardmäßige Branding-Vorlage kann nicht gelöscht werden.
  
## <a name="modify-an-ome-branding-template"></a>Ändern einer OM-Branding-Vorlage

Verwenden Sie Windows PowerShell, um eine Branding-Vorlage gleichzeitig zu ändern. Wenn Sie erweiterte Nachrichtenverschlüsselung haben, können Sie auch benutzerdefinierte Vorlagen erstellen, ändern und entfernen.

1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Verwenden Sie das Set-OMEConfiguration-Cmdlet wie in "OMEConfiguration" beschrieben, oder verwenden Sie die folgende Grafik und Tabelle, um Anleitungen zu [geben](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) .

![Anpassbare e-Mail-Teile](../media/ome-template-breakout.png)

|**So passen Sie dieses Verschlüsselungsfeature an**|**Verwenden Sie diese Befehle**|
|:-----|:-----|
|Hintergrundfarbe|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> Weitere Informationen zu Hintergrundfarben finden Sie im Abschnitt [Hintergrundfarben](#background-color-reference) weiter unten in diesem Artikel.|
|Logo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Unterstützte Dateiformate: .png, .jpg, .bmp oder .tiff  <br/> Optimale Größe der Logodatei: weniger als 40 KB  <br/> Optimale Größe des Logo Bilds: 170 Pixel. Wenn Ihr Bild diese Dimensionen überschreitet, ändert der Dienst Ihr Logo so, dass es im Portal angezeigt wird. Der Dienst ändert die Grafikdatei selbst nicht. Um optimale Ergebnisse zu erzielen, verwenden Sie die optimale Größe.|
|Text neben dem Namen und der e-Mail-Adresse des Absenders|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Text, der auf der Schaltfläche "Nachricht lesen" angezeigt wird|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Text, der unter der Schaltfläche "Nachricht lesen" angezeigt wird|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|URL für den Link zur Datenschutzerklärung|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|Haftungsausschluss in der E-Mail, die die verschlüsselte Nachricht enthält|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Der Text wird oben im Anzeigeportal für verschlüsselte E-Mails angezeigt|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|So aktivieren oder deaktivieren Sie die Authentifizierung mithilfe eines einmaligen Pass Codes für diese benutzerdefinierte Vorlage|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **Beispiele:** <br/>So aktivieren Sie einmalige Kennwörter für diese benutzerdefinierte Vorlage <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> So deaktivieren Sie einmalige Kennwörter für diese benutzerdefinierte Vorlage <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|So aktivieren oder deaktivieren Sie die Authentifizierung mit Microsoft-, Google-oder Yahoo-Identitäten für diese benutzerdefinierte Vorlage|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **Beispiele:** <br/>So aktivieren Sie soziale IDs für diese benutzerdefinierte Vorlage <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> So deaktivieren Sie soziale IDs für diese benutzerdefinierte Vorlage <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Erstellen einer OM-Branding-Vorlage (Erweiterte Nachrichtenverschlüsselung)

Wenn Sie Office 365 erweiterte Nachrichtenverschlüsselung haben, können Sie mithilfe des Cmdlets [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) benutzerdefinierte Branding-Vorlagen für Ihre Organisation erstellen. Nachdem Sie die Vorlage erstellt haben, ändern Sie die Vorlage mithilfe des Set-OMEConfiguration-Cmdlets wie unter [Modify a OM Branding Template](#modify-an-ome-branding-template)beschrieben. Sie können mehrere Vorlagen erstellen.

So erstellen Sie eine neue benutzerdefinierte Branding-Vorlage:

1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Verwenden Sie das Cmdlet [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) , um eine neue Vorlage zu erstellen.

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   Beispiel:

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>Zurückgeben der standardmäßigen Branding-Vorlage auf die ursprünglichen Werte

Führen Sie die folgenden Schritte aus, um alle Änderungen aus der Standardvorlage, einschließlich Marken Anpassungen usw., zu entfernen:
  
1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Verwenden Sie das Cmdlet " **OMEConfiguration** " wie unter " [festlegen-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration)" beschrieben. Wenn Sie die Marken Anpassungen ihrer Organisation aus den DisclaimerText-, EmailText-und Portal Text-Werten entfernen möchten, legen Sie den Wert auf eine leere Zeichenfolge fest `""` . Legen Sie für alle Bild Werte wie Logo den Wert auf fest  `"$null"` .

   In der folgenden Tabelle werden die Standardeinstellungen für die Verschlüsselungs Anpassungsoption beschrieben.

   **Dieses Feature der Verschlüsselungserfahrung zu Standardtext und -bild zurücksetzen**|**Verwenden Sie diese Befehle**|
   |:-----|:-----|
   |Standardtext im Lieferumfang von verschlüsselten e-Mail-Nachrichten  <br/> Der Standardtext wird über den Anweisungen zum Betrachten von verschlüsselten Nachrichten angezeigt|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |Haftungsausschluss in der E-Mail, die die verschlüsselte Nachricht enthält|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |Der Text wird oben im Anzeigeportal für verschlüsselte E-Mails angezeigt|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **Beispiel Zurücksetzen auf Standard:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Logo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **Beispiel Zurücksetzen auf Standard:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Hintergrundfarbe|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **Beispiel Zurücksetzen auf Standard:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Entfernen einer benutzerdefinierten Branding-Vorlage (Erweiterte Nachrichtenverschlüsselung)

Sie können nur Branding-Vorlagen entfernen oder löschen, die Sie erstellt haben. Sie können die standardmäßige Branding-Vorlage nicht entfernen.

So entfernen Sie eine benutzerdefinierte Branding-Vorlage:
  
1. Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Verwenden Sie das Cmdlet **Remove-OMEConfiguration** wie folgt:

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   Beispiel:

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Weitere Informationen finden Sie unter [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration).

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Erstellen einer Exchange-Nachrichtenfluss Regel, die Ihr benutzerdefiniertes Branding auf verschlüsselte e-Mails anwendet

Nachdem Sie entweder die Standardvorlage geändert oder neue Branding-Vorlagen erstellt haben, können Sie Exchange-Nachrichtenfluss Regeln erstellen, um Ihr benutzerdefiniertes Branding basierend auf bestimmten Bedingungen anzuwenden. In den folgenden Szenarien wird eine solche Regel benutzerdefiniertes Branding anwenden:

- Wenn die e-Mail manuell vom Endbenutzer mit Outlook oder Outlook im Internet verschlüsselt wurde, früher Outlook Web App

- Wenn die e-Mail von einer Exchange-Nachrichtenfluss Regel oder einer Richtlinie zur Verhinderung von Datenverlusten automatisch verschlüsselt wurde

Informationen zum Erstellen einer Exchange-Nachrichtenfluss Regel, die Verschlüsselung zutrifft, finden Sie unter [define Mail Flow Rules to encrypt Email Messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. Melden Sie sich in einem Webbrowser mit einem Arbeits-oder Schulkonto, dem globale Administratorberechtigungen erteilt wurden, bei [Office 365 an](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Wählen Sie die Kachel **Admin** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin** Center \> **Exchange** aus.

4. Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** , und wählen Sie **Neues** ![ Neues Symbol neue ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Regel erstellen** aus. Weitere Informationen zur Verwendung der Exchange-Verwaltungskonsole finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. Geben Sie unter **Name** einen Namen für die Regel ein, beispielsweise Branding für die Vertriebsabteilung.

6. Wählen Sie unter **diese Regel anwenden, wenn** aus der Liste der verfügbaren Bedingungen die Bedingung aus, in der sich **der Absender innerhalb der Organisation befindet** , und andere Bedingungen aus. Beispielsweise können Sie eine bestimmte Branding-Vorlage auf Folgendes anwenden:

   - Alle verschlüsselten e-Mails, die von Mitgliedern der Finanzabteilung gesendet wurden
   - Verschlüsselte e-Mails, die mit einem bestimmten Schlüsselwort wie "extern" oder "Partner" gesendet werden
   - Verschlüsselte e-Mails, die an eine bestimmte Domäne gesendet werden

7. Wählen Sie unter **gehen Sie wie folgt** vor die Option **Nachrichtensicherheit** \> **anwenden benutzerdefiniertes Branding auf OM-Nachrichten** ändern aus. Wählen Sie dann in der Dropdownliste eine Branding-Vorlage aus.

8. Optional Sie können die Nachrichtenfluss Regel so konfigurieren, dass Verschlüsselung und benutzerdefiniertes Branding angewendet werden. Wählen Sie unter **Folgendes ausführen die** Option **Nachrichtensicherheit ändern** aus, und wählen Sie dann **Office 365 Nachrichtenverschlüsselung und Rechte Schutz anwenden** aus. Wählen Sie in der Liste eine RMS-Vorlage aus, wählen Sie **Speichern** aus, und klicken Sie dann auf **OK**.
  
   Die Liste der Vorlagen enthält Standardvorlagen und-Optionen sowie benutzerdefinierte Vorlagen, die Sie erstellen. Wenn die Liste leer ist, stellen Sie sicher, dass Sie Office 365 Nachrichtenverschlüsselung mit den neuen Funktionen eingerichtet haben. Anweisungen finden Sie unter [Einrichten neuer Office 365 Nachrichten Verschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md). Informationen zu den Standardvorlagen finden Sie unter [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Informationen zur Option " **nicht weiterleiten** " finden Sie unter [do not Forward Option for Emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Informationen zur Option **nur verschlüsseln** finden Sie unter [verschlüsseln nur Option for Emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Wählen Sie **Aktion hinzufügen** aus, wenn Sie eine andere Aktion angeben möchten.

## <a name="background-color-reference"></a>Hintergrund Farbreferenz

Die Farb Namen, die Sie für die Hintergrundfarbe verwenden können, sind limitiert. Anstelle eines Farbnamens können Sie einen Hex-Codewert (#RRGGBB) verwenden. Sie können einen Hex-Codewert verwenden, der einem Farb Namen entspricht, oder einen benutzerdefinierten HEX-Codewert verwenden. Achten Sie darauf, den Hex-Codewert in Anführungszeichen (beispielsweise) einzuschließen `"#f0f8ff"` .

In der folgenden Tabelle werden die verfügbaren Namen der Hintergrundfarbe und die zugehörigen Hex-Codewerte beschrieben.

|||
|---|---|
|**Farbname**|**Farb Code**|
|`aliceblue`|#f0f8ff|
|`antiquewhite`|#faebd7|
|`aqua`|#00ffff|
|`aquamarine`|#7fffd4|
|`azure`|#f0ffff|
|`beige`|#f5f5dc|
|`bisque`|#ffe4c4|
|`black`|#000000|
|`blanchedalmond`|#ffebcd|
|`blue`|#0000ff|
|`blueviolet`|#8a2be2|
|`brown`|#a52a2a|
|`burlywood`|#deb887|
|`cadetblue`|#5f9ea0|
|`chartreuse`|#7fff00|
|`chocolate`|#d2691e|
|`coral`|#ff7f50|
|`cornflowerblue`|#6495ed|
|`cornsilk`|#fff8dc|
|`crimson`|#dc143c|
|`cyan`|#00ffff|
|`darkblue`|#00008b|
|`darkcyan`|#008b8b|
|`darkgoldenrod`|#b8860b|
|`darkgray`|#a9a9a9|
|`darkgreen`|#006400|
|`darkkhaki`|#bdb76b|
|`darkmagenta`|#8b008b|
|`darkolivegreen`|#556b2f|
|`darkorange`|#ff8c00|
|`darkorchid`|#9932cc|
|`darkred`|#8b0000|
|`darksalmon`|#e9967a|
|`darkseagreen`|#8fbc8f|
|`darkslateblue`|#483d8b|
|`darkslategray`|#2f4f4f|
|`darkturquoise`|#00ced1|
|`darkviolet`|#9400d3|
|`deeppink`|#ff1493|
|`deepskyblue`|#00bfff|
|`dimgray`|#696969|
|`dodgerblue`|#1e90ff|
|`firebrick`|#b22222|
|`floralwhite`|#fffaf0|
|`forestgreen`|#228b22|
|`fuchsia`|#ff00ff|
|`gainsboro`|#dcdcdc|
|`ghostwhite`|#f8f8ff|
|`gold`|#ffd700|
|`goldenrod`|#daa520|
|`gray`|#808080|
|`green`|#008000|
|`greenyellow`|#adff2f|
|`honeydew`|#f0fff0|
|`hotpink`|#ff69b4|
|`indianred`|#cd5c5c|
|`indigo`|#4b0082|
|`ivory`|#fffff0|
|`khaki`|#f0e68c|
|`lavender`|#e6e6fa|
|`lavenderblush`|#fff0f5|
|`lawngreen`|#7cfc00|
|`lemonchiffon`|#fffacd|
|`lightblue`|#add8e6|
|`lightcoral`|#f08080|
|`lightcyan`|#e0ffff|
|`lightgoldenrodyellow`|#fafad2|
|`lightgray`|#d3d3d3|
|`lightgrey`|#d3d3d3|
|`lightgreen`|#90ee90|
|`lightpink`|#ffb6c1|
|`lightsalmon`|#ffa07a|
|`lightseagreen`|#20b2aa|
|`lightskyblue`|#87cefa|
|`lightslategray`|#778899|
|`lightsteelblue`|#b0c4de|
|`lightyellow`|#ffffe0|
|`lime`|#00ff00|
|`limegreen`|#32cd32|
|`linen`|#faf0e6|
|`magenta`|#ff00ff|
|`maroon`|#800000|
|`mediumaquamarine`|#66cdaa|
|`mediumblue`|#0000cd|
|`mediumorchid`|#ba55d3|
|`mediumpurple`|#9370db|
|`mediumseagreen`|#3cb371|
|`mediumslateblue`|#7b68ee|
|`mediumspringgreen`|#00fa9a|
|`mediumturquoise`|#48d1cc|
|`mediumvioletred`|#c71585|
|`midnightblue`|#191970|
|`mintcream`|#f5fffa|
|`mistyrose`|#ffe4e1|
|`moccasin`|#ffe4b5|
|`navajowhite`|#ffdead|
|`navy`|#000080|
|`oldlace`|#fdf5e6|
|`olive`|#808000|
|`olivedrab`|#6b8e23|
|`orange`|#ffa500|
|`orangered`|#ff4500|
|`orchid`|#da70d6|
|`palegoldenrod`|#eee8aa|
|`palegreen`|#98fb98|
|`paleturquoise`|#afeeee|
|`palevioletred`|#db7093|
|`papayawhip`|#ffefd5|
|`peachpuff`|#ffdab9|
|`peru`|#cd853f|
|`pink`|#ffc0cb|
|`plum`|#dda0dd|
|`powderblue`|#b0e0e6|
|`purple`|#800080|
|`red`|#ff0000|
|`rosybrown`|#bc8f8f|
|`royalblue`|#4169e1|
|`saddlebrown`|#8b4513|
|`salmon`|#fa8072|
|`sandybrown`|#f4a460|
|`seagreen`|#00ff00|
|`seashell`|#fff5ee|
|`sienna`|#a0522d|
|`silver`|#c0c0c0|
|`skyblue`|#87ceeb|
|`slateblue`|#6a5acd|
|`slategray`|#708090|
|`snow`|#fffafa|
|`springgreen`|#00ff7f|
|`steelblue`|#4682b4|
|`tan`|#d2b48c|
|`teal`|#008080|
|`thistle`|#d8bfd8|
|`tomato`|#ff6347|
|`turquoise`|#40e0d0|
|`violet`|#ee82ee|
|`wheat`|#f5deb3|
|`white`|#ffffff|
|`whitesmoke`|#f5f5f5|
|`yellow`|#ffff00|
|`yellowgreen`|#9acd32|
