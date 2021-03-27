---
title: Hinzufügen Ihrer Unternehmensmarke zu Ihren verschlüsselten Nachrichten
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
description: Erfahren Sie, wie globale Office 365-Administratoren das Branding Ihrer Organisation auf verschlüsselte E-Mail-Nachrichten & Des Verschlüsselungsportals anwenden können.
ms.openlocfilehash: 2898e12ad00d11cd9eb2f3be5d817ef113607e79
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394713"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>Hinzufügen der Marke Ihrer Organisation zu verschlüsselten Nachrichtenverschlüsselungsnachrichten in Microsoft 365 Business

Sie können Ihr Unternehmensbranding anwenden, um das Erscheinungsbild der E-Mail-Nachrichten Ihrer Organisation und des Verschlüsselungsportals anzupassen. Sie müssen globale Administratorberechtigungen auf Ihr Arbeits- oder Schulkonto anwenden, bevor Sie beginnen können. Nachdem Sie über diese Berechtigungen verfügen, verwenden Sie die cmdlets Get-OMEConfiguration und Set-OMEConfiguration Windows PowerShell, um diese Teile verschlüsselter E-Mail-Nachrichten anzupassen:
  
- Einführungstext

- Disclaimer text

- URL für die Datenschutzbestimmungen Ihrer Organisation

- Text im OME-Portal

- Logo, das in der E-Mail-Nachricht und im OME-Portal angezeigt wird oder ob überhaupt ein Logo verwendet werden soll

- Hintergrundfarbe im E-Mail-Nachrichten- und OME-Portal

Sie können auch jederzeit zum Standardaussehen und -verhalten zurückkehren.

Wenn Sie mehr Kontrolle haben möchten, verwenden Sie die erweiterte Office 365-Nachrichtenverschlüsselung, um mehrere Vorlagen für verschlüsselte E-Mails zu erstellen, die aus Ihrer Organisation stammen. Verwenden Sie diese Vorlagen, um Teile der Endbenutzererfahrung zu steuern. Geben Sie beispielsweise an, ob Empfänger Google-, Yahoo- und Microsoft-Konten zum Anmelden beim Verschlüsselungsportal verwenden können. Verwenden Sie Vorlagen, um mehrere Verwendungsfälle zu erfüllen, z. B.:

- Einzelne Abteilungen, z. B. Finance, Sales, und so weiter.

- Verschiedene Produkte

- Unterschiedliche geografische Regionen oder Länder

- Gibt an, ob E-Mails widerrufen werden sollen

- Gibt an, ob E-Mails, die an externe Empfänger gesendet werden, nach einer bestimmten Anzahl von Tagen ablaufen sollen.

Nachdem Sie die Vorlagen erstellt haben, können Sie sie mithilfe von Exchange-Nachrichtenflussregeln auf verschlüsselte E-Mails anwenden. Wenn Sie office 365 Advanced Message Encryption verwenden, können Sie alle E-Mails widerrufen, die Sie mit diesen Vorlagen gebrandet haben.

## <a name="work-with-ome-branding-templates"></a>Arbeiten mit OME-Brandingvorlagen

Sie können mehrere Features in einer Brandingvorlage ändern. Sie können die Standardvorlage ändern, aber nicht entfernen. Wenn Sie über erweiterte Nachrichtenverschlüsselung verfügen, können Sie auch benutzerdefinierte Vorlagen erstellen, ändern und entfernen. Verwenden Windows PowerShell, um mit einer Brandingvorlage gleichzeitig zu arbeiten.

- [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) – Ändern Sie die von Ihnen erstellte Standardbrandingvorlage oder eine benutzerdefinierte Brandingvorlage.
- [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) – Erstellen Sie eine neue Brandingvorlage, nur Erweiterte Nachrichtenverschlüsselung.
- [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) – Entfernen einer benutzerdefinierten Brandingvorlage, nur Erweiterte Nachrichtenverschlüsselung. Die Standardbrandingvorlage kann nicht gelöscht werden.
  
## <a name="modify-an-ome-branding-template"></a>Ändern einer OME-Brandingvorlage

Verwenden Windows PowerShell, um eine Brandingvorlage gleichzeitig zu ändern. Wenn Sie über erweiterte Nachrichtenverschlüsselung verfügen, können Sie auch benutzerdefinierte Vorlagen erstellen, ändern und entfernen.

1. Starten Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Windows PowerShell und stellen Sie eine Verbindung mit Exchange Online ein. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Verwenden Sie Set-OMEConfiguration cmdlet, wie unter [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) beschrieben, oder verwenden Sie die folgende Grafik und Tabelle als Anleitung.

![Anpassbare E-Mail-Teile](../media/ome-template-breakout.png)

|**So passen Sie dieses Verschlüsselungsfeature an**|**Verwenden dieser Befehle**|
|:-----|:-----|
|Hintergrundfarbe|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> Weitere Informationen zu Hintergrundfarben finden Sie im Abschnitt [Hintergrundfarben](#background-color-reference) weiter unten in diesem Artikel.|
|Logo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Unterstützte Dateiformate: .png, .jpg, .bmp oder .tiff  <br/> Optimale Größe der Logodatei: weniger als 40 KB  <br/> Optimale Größe des Logobilds: 170 x 70 Pixel. Wenn Ihr Bild diese Dimensionen überschreitet, ändert der Dienst die Größe Ihres Logos für die Anzeige im Portal. Der Dienst ändert die Grafikdatei selbst nicht. Verwenden Sie die optimale Größe, um optimale Ergebnisse zu erzielen.|
|Text neben dem Namen und der E-Mail-Adresse des Absenders|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Text, der auf der Schaltfläche "Nachricht lesen" angezeigt wird|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Text, der unterhalb der Schaltfläche "Nachricht lesen" angezeigt wird|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|URL für den Link "Datenschutzbestimmungen"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|Haftungsausschluss in der E-Mail, die die verschlüsselte Nachricht enthält|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Der Text wird oben im Anzeigeportal für verschlüsselte E-Mails angezeigt|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|So aktivieren oder deaktivieren Sie die Authentifizierung mit einem einmal verwendeten Passcode für diese benutzerdefinierte Vorlage|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **Beispiele:** <br/>So aktivieren Sie die einmal verwendeten Passcodes für diese benutzerdefinierte Vorlage <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> So deaktivieren Sie die einmal verwendeten Passcodes für diese benutzerdefinierte Vorlage <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|So aktivieren oder deaktivieren Sie die Authentifizierung mit Microsoft-, Google- oder Yahoo-Identitäten für diese benutzerdefinierte Vorlage|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **Beispiele:** <br/>So aktivieren Sie IDs für soziale Netzwerke für diese benutzerdefinierte Vorlage <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> So deaktivieren Sie soziale IDs für diese benutzerdefinierte Vorlage <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Erstellen einer OME-Brandingvorlage (Erweiterte Nachrichtenverschlüsselung)

Wenn Sie office 365 Advanced Message Encryption verwenden, können Sie mit dem [Cmdlet New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) benutzerdefinierte Brandingvorlagen für Ihre Organisation erstellen. Nachdem Sie die Vorlage erstellt haben, ändern Sie die Vorlage mithilfe des cmdlets Set-OMEConfiguration, wie unter Ändern einer [OME-Brandingvorlage beschrieben.](#modify-an-ome-branding-template) Sie können mehrere Vorlagen erstellen.

So erstellen Sie eine neue benutzerdefinierte Brandingvorlage:

1. Starten Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Windows PowerShell und stellen Sie eine Verbindung mit Exchange Online ein. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Verwenden Sie [das Cmdlet New-OMEConfiguration,](/powershell/module/exchange/new-omeconfiguration) um eine neue Vorlage zu erstellen.

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   Beispiel:

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>Zurückgeben der Standardbrandingvorlage zu den ursprünglichen Werten

Führen Sie die folgenden Schritte aus, um alle Änderungen aus der Standardvorlage, einschließlich Markenanpassungen, zu entfernen:
  
1. Starten Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Windows PowerShell und stellen Sie eine Verbindung mit Exchange Online ein. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Verwenden Sie **das Cmdlet Set-OMEConfiguration,** wie unter [Set-OMEConfiguration beschrieben.](/powershell/module/exchange/Set-OMEConfiguration) Wenn Sie die Markenanpassungen Ihrer Organisation aus den Werten Haftungsausschlusstext, EmailText und PortalText entfernen möchten, legen Sie den Wert auf eine leere `""` Zeichenfolge, . Legen Sie für alle Bildwerte, z. B. Logo, den Wert auf  `"$null"` .

   In der folgenden Tabelle werden die Standardeinstellungen für die Verschlüsselungsanpassung beschrieben.

   |Dieses Feature der Verschlüsselungserfahrung zu Standardtext und -bild zurücksetzen|Verwenden dieser Befehle|
   |:-----|:-----|
   |Standardtext, der mit verschlüsselten E-Mail-Nachrichten enthalten ist.  Der Standardtext wird über den Anweisungen zum Betrachten von verschlüsselten Nachrichten angezeigt|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |Haftungsausschluss in der E-Mail, die die verschlüsselte Nachricht enthält|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **Beispiel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |Der Text wird oben im Anzeigeportal für verschlüsselte E-Mails angezeigt|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **Beispiel für die wiederhergestellte Standardeinstellung:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Logo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **Beispiel für die wiederhergestellte Standardeinstellung:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Hintergrundfarbe|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **Beispiel für die wiederhergestellte Standardeinstellung:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Entfernen einer benutzerdefinierten Brandingvorlage (Erweiterte Nachrichtenverschlüsselung)

Sie können brandingvorlagen, die Sie erstellt haben, nur entfernen oder löschen. Die Standardbrandingvorlage kann nicht entfernt werden.

So entfernen Sie eine benutzerdefinierte Brandingvorlage:
  
1. Starten Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Windows PowerShell und stellen Sie eine Verbindung mit Exchange Online ein. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Verwenden Sie **das Cmdlet Remove-OMEConfiguration** wie folgt:

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   Beispiel:

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Weitere Informationen finden Sie unter [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Erstellen einer Exchange-Nachrichtenflussregel, mit der Ihr benutzerdefiniertes Branding auf verschlüsselte E-Mails angewendet wird

Nachdem Sie die Standardvorlage geändert oder neue Brandingvorlagen erstellt haben, können Sie Exchange-Nachrichtenflussregeln erstellen, um Ihr benutzerdefiniertes Branding basierend auf bestimmten Bedingungen anzuwenden. Eine solche Regel wird benutzerdefiniertes Branding in den folgenden Szenarien anwenden:

- Wenn die E-Mail manuell vom Endbenutzer mithilfe von Outlook oder Outlook im Web verschlüsselt wurde, früher Outlook Web App

- Wenn die E-Mail automatisch von einer Exchange-Nachrichtenflussregel oder einer Richtlinie zur Verhinderung von Datenverlust verschlüsselt wurde

Informationen zum Erstellen einer Exchange-Nachrichtenflussregel mit Verschlüsselung finden Sie unter [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. Melden Sie sich in einem Webbrowser mit einem Geschäfts- oder Schulkonto an, dem globale Administratorberechtigungen erteilt wurden, [bei Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Wählen Sie die **Kachel Admin** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin Centers** \> **Exchange** aus.

4. Wechseln Sie in der EAC zu **Nachrichtenflussregeln,** \>  und wählen **Sie Neues** Symbol Neue Regel ![ erstellen ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **aus.** Weitere Informationen zur Verwendung der EAC finden Sie unter [Exchange Admin Center in Exchange Online](/exchange/exchange-admin-center).

5. Geben **Sie unter Name** einen Namen für die Regel ein, z. B. Branding für vertriebsabteilung.

6. Wählen **Sie unter Diese Regel anwenden if** die Bedingung Der Absender befindet sich **innerhalb** der Organisation und andere Bedingungen, die Sie wünschen, in der Liste der verfügbaren Bedingungen aus. Sie können z. B. eine bestimmte Brandingvorlage auf folgende Bedingungen anwenden:

   - Alle verschlüsselten E-Mails, die von Mitgliedern der Finanzabteilung gesendet werden
   - Verschlüsselte E-Mails, die mit einem bestimmten Schlüsselwort wie "Extern" oder "Partner" gesendet werden
   - Verschlüsselte E-Mails, die an eine bestimmte Domäne gesendet werden

7. Wählen **Sie unter Gehen Sie wie folgt** vor, die Option **Nachrichtensicherheit ändern** \> **Benutzerdefiniertes Branding auf OME-Nachrichten anwenden aus.** Wählen Sie als Nächstes in der Dropdownliste eine Brandingvorlage aus.

8. (Optional) Sie können die Nachrichtenflussregel so konfigurieren, dass Verschlüsselung und benutzerdefiniertes Branding angewendet werden. Wählen **Sie unter Gehen Sie wie folgt** vor, die Option **Nachrichtensicherheit ändern** aus, und wählen Sie dann Office **365-Nachrichtenverschlüsselung und Rechteschutz anwenden aus.** Wählen Sie in der Liste eine RMS-Vorlage aus, wählen Sie **Speichern** und dann **OK aus.**
  
   Die Liste der Vorlagen enthält Standardvorlagen und -optionen sowie alle benutzerdefinierten Vorlagen, die Sie erstellen. Wenn die Liste leer ist, stellen Sie sicher, dass Sie die Office 365-Nachrichtenverschlüsselung mit den neuen Funktionen eingerichtet haben. Anweisungen finden Sie unter [Einrichten neuer Office 365-Nachrichtenverschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md). Informationen zu den Standardvorlagen finden Sie unter [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates). Weitere Informationen zur Option **Nicht** weiterleiten finden Sie unter [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Informationen zur Option **nur** verschlüsseln finden Sie unter Encrypt Only option for [emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Wählen **Sie Aktion hinzufügen** aus, wenn Sie eine andere Aktion angeben möchten.

## <a name="background-color-reference"></a>Hintergrundfarbreferenz

Die Farbnamen, die Sie für die Hintergrundfarbe verwenden können, sind begrenzt. Anstelle eines Farbnamens können Sie einen Hexcodewert (#RRGGBB). Sie können einen Hexcodewert verwenden, der einem Farbnamen entspricht, oder Sie können einen benutzerdefinierten Hexcodewert verwenden. Achten Sie darauf, den Hexcodewert in Anführungszeichen (z. B. ) zu `"#f0f8ff"` setzen.

Die verfügbaren Hintergrundfarbnamen und die entsprechenden Hexadezimalcodewerte werden in der folgenden Tabelle beschrieben.

|**Farbname**|**Farbcode**|
|---|---|
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