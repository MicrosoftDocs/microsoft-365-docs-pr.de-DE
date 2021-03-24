---
title: Legacyinformationen für die Office 365-Nachrichtenverschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Legacydateien zu Office 365 Message Encryption (OME) für Ihre Organisation überwechseln.
ms.openlocfilehash: eabf655b6fa92a6f502ebe1e071d41f394f78929
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051827"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Legacyinformationen für die Office 365-Nachrichtenverschlüsselung

Wenn Sie Ihre Organisation noch nicht in die neuen OME-Funktionen verschoben haben, aber bereits OME bereitgestellt haben, gelten die Informationen in diesem Artikel für Ihre Organisation. Microsoft empfiehlt, einen Plan für den Wechsel zu den neuen OME-Funktionen zu erstellen, sobald dies für Ihre Organisation sinnvoll ist. Anweisungen finden Sie [unter Einrichten neuer Office 365-Nachrichtenverschlüsselungsfunktionen,](set-up-new-message-encryption-capabilities.md)die auf Azure Information Protection aufgebaut sind. Weitere Informationen zur Funktionsweise der neuen Funktionen finden Sie unter [Office 365 Message Encryption](ome.md). Der Rest dieses Artikels bezieht sich auf das OME-Verhalten vor der Veröffentlichung der neuen OME-Funktionen.
  
Mit der Office 365-Nachrichtenverschlüsselung kann Ihre Organisation verschlüsselte E-Mail-Nachrichten von bzw. zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen. Die Office 365-Nachrichtenverschlüsselung funktioniert mit Outlook.com, Yahoo, Gmail und anderen E-Mail-Diensten. Die E-Mail-Nachrichtenverschlüsselung sorgt dafür, dass nur vorgesehene Empfänger verschlüsselte Nachrichten ansehen können.
  
Im Folgenden finden Sie einige Beispiele:
  
- Ein Bankangestellter sendet Kreditkartenauszüge an Kunden

- Ein Versicherungsunternehmensvertreter stellt Kunden Richtliniendetails zur Verfügung.

- Ein Hypothekenbroker fordert Finanzinformationen von einem Kunden für eine Kreditanwendung an.

- Ein Gesundheitsdienstleister sendet Gesundheitsinformationen an Patienten

- Ein Anwalt sendet vertrauliche Informationen an einen Kunden oder einen anderen Anwalt

## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Funktionsweise der Office 365-Nachrichtenverschlüsselung ohne die neuen Funktionen

Die Office 365-Nachrichtenverschlüsselung ist ein Onlinedienst, der auf Microsoft Azure Rights Management (Azure RMS) baut. Mit Azure RMS können Administratoren Nachrichtenflussregeln definieren, um die Bedingungen für die Verschlüsselung zu bestimmen. Eine Regel kann z. B. die Verschlüsselung aller Nachrichten erfordern, die an einen bestimmten Empfänger adressiert sind.
  
Wenn jemand eine E-Mail-Nachricht in Exchange Online sendet, die einer Verschlüsselungsregel entspricht, wird die Nachricht mit einer HTML-Anlage gesendet. Der Empfänger öffnet die HTML-Anlage und folgt Anweisungen zum Anzeigen der verschlüsselten Nachricht im Office 365-Nachrichtenverschlüsselungsportal. Der Empfänger kann die Nachricht anzeigen, indem er sich mit einem Microsoft-Konto oder einer mit Office 365 verknüpften Geschäfts-, Schul- oder Schulstelle oder mit einem einmal verwendeten Passcode einschreibt. Beide Optionen stellen sicher, dass die verschlüsselte Nachricht nur vom vorgesehenen Empfänger angezeigt werden kann. Dieser Prozess ist für die neuen OME-Funktionen sehr unterschiedlich.
  
Im folgenden Diagramm wird die Weitergabe einer E-Mail-Nachricht durch den Verschlüsselungs- und Entschlüsselungsvorgang zusammengefasst.
  
![Diagramm mit dem Pfad einer verschlüsselten E-Mail](../media/O365-Office365MessageEncryption-Concept.png)
  
Weitere Informationen finden Sie unter Service information for legacy Office 365 Message Encryption vor der Veröffentlichung der [neuen OME-Funktionen.](legacy-information-for-message-encryption.md#LegacyServiceInfo)
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>Definieren von Nachrichtenflussregeln für die Office 365-Nachrichtenverschlüsselung, die die neuen OME-Funktionen nicht verwenden

Zum Aktivieren der Office 365-Nachrichtenverschlüsselung ohne die neuen Funktionen definieren Exchange Online- und Exchange Online Protection-Administratoren Exchange-Nachrichtenflussregeln. Diese Regeln bestimmen, unter welchen Bedingungen E-Mail-Nachrichten verschlüsselt werden sollen, sowie Bedingungen zum Entfernen der Nachrichtenverschlüsselung. Wenn eine Verschlüsselungsaktion für eine Regel festgelegt ist, führt der Dienst die Aktion für alle Nachrichten aus, die den Regelbedingungen entsprechen, bevor die Nachrichten gesendet werden.

Nachrichtenflussregeln sind flexibel, sodass Sie Bedingungen kombinieren können, damit Sie bestimmte Sicherheitsanforderungen in einer einzigen Regel erfüllen können. Sie können beispielsweise eine Regel zum Verschlüsseln aller Nachrichten definieren, die bestimmte Schlüsselwörter enthalten und an externe Empfänger adressiert sind. Die Office 365-Nachrichtenverschlüsselung verschlüsselt auch Antworten der Empfänger von verschlüsselten E-Mails und Sie können eine Regel erstellen, die diese Antworten bereits bequem für Ihre E-Mail-Benutzer entschlüsselt. Auf diese Weise müssen sich Benutzer in Ihrer Organisation nicht beim Verschlüsselungsportal anmelden, um Antworten anzeigen zu können.
  
Weitere Informationen zum Erstellen von Exchange-Nachrichtenflussregeln finden Sie unter [Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md).
  
### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Verwenden der EAC zum Erstellen einer Nachrichtenflussregel zum Verschlüsseln von E-Mail-Nachrichten ohne die neuen OME-Funktionen

1. Melden Sie sich in einem Webbrowser mit einem Geschäfts- oder Schulkonto an, dem globale Administratorberechtigungen erteilt wurden, [bei Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Wählen Sie die **Kachel Admin** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin Centers** \> **Exchange** aus.

4. Wechseln Sie in der EAC zu **Nachrichtenflussregeln,** \>  und wählen **Sie Neues** Symbol Neue Regel ![ erstellen ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **aus.** Weitere Informationen zur Verwendung der EAC finden Sie unter [Exchange Admin Center in Exchange Online](/exchange/exchange-admin-center).

5. Geben Sie unter **Name** einen Namen für die Regel ein, z. B. Verschlüsseln von E-Mails für DrToniRamos@hotmail.com.

6. Wählen Sie unter **Diese Regel anwenden, wenn** eine Bedingung aus, und geben Sie ggf. einen Wert ein. Geben Sie beispielsweise Folgendes ein, um Nachrichten an "DrToniRamos@hotmail.com" zu verschlüsseln:

   1. Wählen Sie unter **Diese Regel anwenden, wenn****the recipient is** (Der Empfänger ist) aus.

   2. Wählen Sie in der Kontaktliste einen vorhandenen Namen aus, oder geben Sie im Feld **Namen prüfen** eine neue E-Mail-Adresse ein.

      - Um einen vorhandenen Namen auszuwählen, wählen Sie ihn in der Liste aus, und klicken Sie dann auf **OK**.

      - Geben Sie zum Eingeben eines neuen Namens eine E-Mail-Adresse in **das** Kontrollkästchen Namen ein, und wählen Sie dann **Namen überprüfen** \> **OK aus.**

7. Wenn Sie weitere Bedingungen hinzufügen möchten, wählen Sie **Weitere Optionen** aus, und wählen Sie dann Bedingung **hinzufügen aus,** und wählen Sie aus der Liste aus.

   Um die Regel beispielsweise nur anzuwenden, wenn sich der Empfänger außerhalb Ihrer Organisation befindet, wählen Sie **Bedingung** hinzufügen aus, und wählen Sie dann Der Empfänger ist **extern/intern** Außerhalb der \> **Organisation** \> **OK aus.**

8. Um die Verschlüsselung ohne Verwendung der neuen  OME-Funktionen zu aktivieren, wählen Sie in **Gehen** Sie wie folgt aus Ändern der Nachrichtensicherheit Anwenden der vorherigen Version von \> **OME** aus, und wählen Sie dann Speichern **aus.**

   Wenn Sie eine Fehlermeldung erhalten, dass die IRM-Lizenzierung nicht aktiviert ist, verwenden Sie keine ältere OME.

9. (Optional) Wählen **Sie Aktion hinzufügen aus,** um eine weitere Aktion anzugeben.

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Verwenden von Exchange Online PowerShell zum Erstellen einer Nachrichtenflussregel zum Verschlüsseln von E-Mail-Nachrichten ohne die neuen OME-Funktionen

1. Stellen Sie eine Verbindung mit Exchange Online PowerShell her. Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Erstellen Sie eine Regel mithilfe des **Cmdlets New-TransportRule,** und legen Sie den _ApplyOME-Parameter_ auf `$true` .

   In diesem Beispiel müssen alle E-Mail-Nachrichten, die an DrToniRamos@hotmail.com gesendet werden, verschlüsselt werden.

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   Dabei gilt:

   - Der eindeutige Name der neuen Regel ist "Regel verschlüsseln für Dr. Toni Ramos".
   - Der _Parameter SentTo_ gibt die Nachrichtenempfänger an (identifiziert nach Name, E-Mail-Adresse, Distinguished Name usw.). In diesem Beispiel wird der Empfänger durch die E-Mail-Adresse "DrToniRamos@hotmail.com" identifiziert.
   - Der _Parameter SentToScope_ gibt den Speicherort der Nachrichtenempfänger an. In diesem Beispiel befindet sich das Postfach des Empfängers in Hotmail und ist nicht Teil der Organisation, daher wird `NotInOrganization` der Wert verwendet.

   Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](/powershell/module/exchange/New-TransportRule).

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Entfernen der Verschlüsselung aus verschlüsselten E-Mail-Antworten ohne die neuen OME-Funktionen

Wenn Ihre E-Mail-Benutzer verschlüsselte Nachrichten senden, können Empfänger dieser Nachrichten verschlüsselte Antworten senden. Sie können Nachrichtenflussregeln erstellen, um die Verschlüsselung automatisch aus Antworten zu entfernen, damit sich E-Mail-Benutzer in Ihrer Organisation nicht beim Verschlüsselungsportal anmelden müssen, um sie anzeigen zu können. Sie können die EAC oder Windows PowerShell cmdlets verwenden, um diese Regeln zu definieren. Sie können Nachrichten entschlüsseln, die aus Ihrer Organisation gesendet werden, oder Nachrichten, die Antworten auf Nachrichten sind, die aus Ihrer Organisation gesendet werden. Verschlüsselte Nachrichten, die von außerhalb Ihrer Organisation stammen, können nicht entschlüsselt werden.

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Verwenden der EAC zum Erstellen einer Regel zum Entfernen der Verschlüsselung aus verschlüsselten E-Mail-Antworten ohne die neuen OME-Funktionen

1. Melden Sie sich in einem Webbrowser mit einem Geschäfts- oder Schulkonto an, dem Administratorberechtigungen erteilt wurden, [bei Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Wählen Sie die **Kachel Admin** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin Centers** \> **Exchange** aus.

4. Wechseln Sie in der EAC zu **Nachrichtenflussregeln,** \>  und wählen **Sie Neues** Symbol Neue Regel ![ erstellen ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **aus.** Weitere Informationen zur Verwendung der EAC finden Sie unter [Exchange Admin Center in Exchange Online](/exchange/exchange-admin-center).

5. Geben **Sie unter Name** einen Namen für die Regel ein, z. B. Verschlüsselung aus eingehenden E-Mails entfernen.

6. Wählen **Sie unter Diese Regel anwenden** die Bedingungen aus, unter denen die Verschlüsselung aus Nachrichten entfernt werden soll, z. B. Der Empfänger **befindet** sich innerhalb \> **der Organisation**.

7. Wählen **Sie in Gehen Sie wie folgt** aus Ändern der **Nachrichtensicherheit** \> **Entfernen der vorherigen Version von OME** aus.

8. Klicken Sie auf **Speichern**.

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Verwenden von Exchange Online PowerShell zum Erstellen einer Regel zum Entfernen der Verschlüsselung aus verschlüsselten E-Mail-Antworten ohne die neuen OME-Funktionen

1. Stellen Sie eine Verbindung mit Exchange Online PowerShell her. Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Erstellen Sie eine Regel mithilfe des **Cmdlets New-TransportRule,** und legen Sie den _RemoveOME-Parameter_ auf `$true` .

   In diesem Beispiel wird die Verschlüsselung aus allen E-Mails entfernt, die an Empfänger in der Organisation gesendet werden.

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   Dabei gilt:

   - Der eindeutige Name der neuen Regel ist "Verschlüsselung aus eingehenden E-Mails entfernen".
   - Der _Parameter SentToScope_ gibt den Speicherort der Nachrichtenempfänger an. In diesem Beispiel wird der Wert verwendet, der einen der `InOrganization` folgenden Werte angibt:
     - Der Empfänger ist ein Postfach, ein E-Mail-Benutzer, eine Gruppe oder ein E-Mail-aktivierter öffentlicher Ordner in Ihrer Organisation.
     - Die E-Mail-Adresse des Empfängers befindet sich in einer akzeptierten Domäne, die als autorisierende Domäne oder interne Relaydomäne in Ihrer Organisation konfiguriert _ist,_ und die Nachricht wurde über eine authentifizierte Verbindung gesendet oder empfangen.

Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](/powershell/module/exchange/New-TransportRule).

## <a name="sending-viewing-and-replying-to-messages-encrypted-without-the-new-capabilities"></a>Senden, Anzeigen und Antworten auf Nachrichten, die ohne die neuen Funktionen verschlüsselt sind

Bei der Office 365-Nachrichtenverschlüsselung werden E-Mail-Nachrichten basierend auf vom Administrator definierten Regeln automatisch verschlüsselt. Eine E-Mail mit einer verschlüsselten Nachricht wird mit einer angefügten HTML-Datei im Posteingang des Empfängers eintreffen.
  
Empfänger folgen anweisungen in der Nachricht, um die Anlage zu öffnen und sich mithilfe eines Microsoft-Kontos oder einer Mit Office 365 verknüpften Arbeit oder Schule zu authentifizieren. Wenn Empfänger nicht über ein konto verfügen, werden sie dazu geleitet, ein Microsoft-Konto zu erstellen, mit dem sie sich anmelden können, um die verschlüsselte Nachricht anzeigen zu können. Alternativ können Empfänger einen einmal übergebenen Code zum Anzeigen der Nachricht erhalten. Nach der Anmeldung oder Verwendung eines einmal übergebenen Codes können Empfänger die entschlüsselte Nachricht anzeigen und eine verschlüsselte Antwort senden.
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>Anpassen verschlüsselter Nachrichten mit Office 365-Nachrichtenverschlüsselung

Als Exchange Online- und Exchange Online Protection-Administrator können Sie Ihre verschlüsselten Nachrichten anpassen. Sie können beispielsweise die Marke und das Logo Ihres Unternehmens hinzufügen, eine Einführung angeben und Haftungsausschlusstext in verschlüsselten Nachrichten und im Portal hinzufügen, in dem Empfänger Ihre verschlüsselten Nachrichten anzeigen. Mit Windows PowerShell-Cmdlets passen Sie die folgenden Aspekte im Erscheinungsbild für Epfänger von verschlüsselten E-Mails an:

- Einleitender Text der E-Mail, die die verschlüsselte Nachricht enthält

- Text des Haftungsausschlusses der E-Mail, die die verschlüsselte Nachricht enthält

- Portaltext, der im Meldungsanzeigeportal angezeigt wird

- Logo, das in der E-Mail-Nachricht und im Anzeigeportal erscheint

Sie können auch jederzeit zum Standardaussehen und -verhalten zurückkehren.
  
Im folgenden Beispiel wird ein benutzerdefiniertes ContosoPharma-Logo im E-Mail-Anhang gezeigt:

> [!div class="mx-imgBorder"]
> ![Beispiel für die Seite mit verschlüsselten Nachrichten anzeigen](../media/TA-OME-3attachment2.jpg)
  
**So passen Sie Verschlüsselungs-E-Mail-Nachrichten und das Verschlüsselungsportal mit der Marke Ihrer Organisation an**
  
1. Stellen Sie eine Verbindung mit Exchange Online mithilfe von Remote PowerShell wie unter [Connect to Exchange Online Using Remote PowerShell beschrieben.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Verwenden Sie Set-OMEConfiguration cmdlet wie hier beschrieben: [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) oder verwenden Sie die folgende Tabelle als Anleitung.

   **Anpassungsoptionen für Verschlüsselung**

   | So passen Sie dieses Verschlüsselungsfeature an | Verwenden Sie diese Befehle von Windows PowerShell |
   |:-----|:-----|
   |Standardtext, der verschlüsselten E-Mail-Nachrichten beigefügt ist  <br/> Der Standardtext wird über den Anweisungen zum Betrachten von verschlüsselten Nachrichten angezeigt  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **Beispiel:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
   |Haftungsausschluss in der E-Mail, die die verschlüsselte Nachricht enthält  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **Beispiel:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
   |Der Text wird oben im Anzeigeportal für verschlüsselte E-Mails angezeigt  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **Beispiel:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
   |Logo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Beispiel:** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Unterstützte Dateiformate: .png, .jpg, .bmp oder .tiff  <br/> Optimale Größe der Logodatei: weniger als 40 KB  <br/> Optimale Abmessungen des Logobilds: 170 x 70 Pixel  <br/> |

**So entfernen Sie Markenanpassungen aus Verschlüsselungs-E-Mail-Nachrichten und dem Verschlüsselungsportal**
  
1. Stellen Sie eine Verbindung mit Exchange Online mithilfe von Remote PowerShell wie unter [Connect to Exchange Online Using Remote PowerShell beschrieben.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Verwenden Sie Set-OMEConfiguration cmdlet wie hier beschrieben: [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration). Wenn Sie die Markenanpassungen Ihrer Organisation aus den Werten Haftungsausschlusstext, EmailText und PortalText entfernen möchten, legen Sie den Wert auf eine leere  `""` Zeichenfolge, . Legen Sie für alle Bildwerte, z. B. Logo, den Wert auf  `"$null"` .

   **Anpassungsoptionen für Verschlüsselung**

   | Dieses Feature der Verschlüsselungserfahrung zu Standardtext und -bild zurücksetzen | Verwenden Sie diese Befehle von Windows PowerShell |
   |:-----|:-----|
   |Standardtext, der verschlüsselten E-Mail-Nachrichten beigefügt ist  <br/> Der Standardtext wird über den Anweisungen zum Betrachten von verschlüsselten Nachrichten angezeigt  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Beispiel:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
   |Haftungsausschluss in der E-Mail, die die verschlüsselte Nachricht enthält  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Beispiel:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
   |Der Text wird oben im Anzeigeportal für verschlüsselte E-Mails angezeigt  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Beispiel für die wiederhergestellte Standardeinstellung:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
   |Logo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Beispiel für die wiederhergestellte Standardeinstellung:**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |

## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>Dienstinformationen für die Office 365-Nachrichtenverschlüsselung vor der Veröffentlichung der neuen OME-Funktionen
<a name="LegacyServiceInfo"> </a>

Die folgende Tabelle enthält technische Details für den Office 365-Nachrichtenverschlüsselungsdienst vor der Veröffentlichung der neuen OME-Funktionen.
  
| Service-Informationen | Beschreibung |
|:-----|:-----|
|Anforderungen an die Client-Geräte  <br/> |Verschlüsselte Nachrichten können auf einem Client-Gerät angezeigt werden, solange der HTML-Anhang in einem modernen Browser geöffnet werden kann, der Form Post unterstützt.  <br/> |
|Verschlüsselungsalgorithmus und Compliance Federal Information Processing Standards (FIPS)  <br/> |Die Office 365 Nachrichtenverschlüsselung verwendet dieselbe Verschlüsselung wie Windows Azure Information Rights Management (IRM) und unterstützt Kryptografiemodus 2 (2K Schlüssel für RSA und 256 Bit Schlüssel für SHA-1-Systeme). Weitere Informationen zu den zugrunde liegenden IRM-Kryptografiemodi finden Sie unter [AD RMS Cryptographic Modes](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)).  <br/> |
|Unterstützte Nachrichtentypen  <br/> |Die Office 365-Nachrichtenverschlüsselung wird nur für Elemente mit der Nachrichtenklassen-ID **IPM.Note** unterstützt. Weitere Informationen finden Sie unter [Elementtypen und Nachrichtenklassen](/office/vba/outlook/Concepts/Forms/item-types-and-message-classes).  <br/> |
|Beschränkungen der Nachrichtengröße  <br/> |Die Office 365 Nachrichtenverschlüsselung kann Nachrichten bis zu 25 MB verschlüsseln. Weitere Informationen zu Nachrichtengrößenbeschränkungen finden Sie unter [Exchange Online Limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).  <br/> |
|Exchange Online-E-Mail-Aufbewahrungsrichtlinien  <br/> |In Exchange Online werden die verschlüsselten Nachrichten nicht gespeichert.  <br/> |
|Die Sprachunterstützung für Office 365 Nachrichtenverschlüsselung  <br/> | Die Office 365-Nachrichtenverschlüsselung unterstützt Microsoft 365-Sprachen wie folgt:  <br/>  Eingehende E-Mail-Nachrichten und angefügte HTML-Dateien werden basierend auf den Spracheinstellungen des Absenders lokalisiert.  <br/>  Das Anzeigeportal wird basierend auf den Browsereinstellungen des Empfängers lokalisiert.  <br/>  Der Nachrichtentext (Inhalt) der verschlüsselten Nachricht ist nicht lokalisiert.  <br/> |
|Datenschutzinformationen für OME-Portal und OME-Viewer-App  <br/> |Die [Office 365 Messaging Encryption Portal privacy statement](https://privacy.microsoft.com/privacystatement) enthalten ausführliche Informationen darüber, wofür Microsoft Ihre vertraulichen Informationen verwendet.  <br/> |

## <a name="frequently-asked-questions-about-legacy-ome"></a>Häufig gestellte Fragen zu Legacy-OME
<a name="LegacyServiceInfo"> </a>

Haben Sie Fragen zur Office 365-Nachrichtenverschlüsselung? Hier finden Sie einige Antworten. Wenn Sie nicht finden können, was Sie benötigen, lesen Sie die [Microsoft Tech Community-Foren für Office 365](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365).
  
 **F. Meine Benutzer senden verschlüsselte E-Mail-Nachrichten an Empfänger außerhalb unserer Organisation. Gibt es etwas, was externe Empfänger tun müssen, um E-Mail-Nachrichten zu lesen und zu beantworten, die mit der Office 365-Nachrichtenverschlüsselung verschlüsselt sind?**
  
Empfänger außerhalb Ihrer Organisation, die verschlüsselte Microsoft 365-Nachrichten empfangen, können sie auf eine von zwei Arten anzeigen:
  
- Durch Die Anmeldung mit einem Microsoft-Konto oder einem Geschäfts- oder Schulkonto, das Office 365 zugeordnet ist.

- Mithilfe eines einmal verwendeten Passcodes.

 **F. Werden microsoft 365-verschlüsselte Nachrichten in der Cloud oder auf Microsoft-Servern gespeichert?**
  
Nein, die verschlüsselten Nachrichten werden im E-Mail-System des Empfängers gespeichert, und wenn der Empfänger die Nachricht öffnet, wird sie vorübergehend zur Anzeige auf Microsoft-Servern bereitgestellt. Die Nachrichten werden dort nicht gespeichert.
  
 **F. Kann ich meine Marke in verschlüsselte E-Mail-Nachrichten einbinden?**
  
Ja. Sie können Windows PowerShell-Cmdlets verwenden, um den Standardtext, der oben in verschlüsselten E-Mail-Nachrichten angezeigt wird, sowie den Haftungsausschlusstext und das Logo, das Sie für E-Mail-Nachrichten und das Verschlüsselungsportal verwenden möchten, anpassen. Dieses Feature ist jetzt in OMEv2 verfügbar. Weitere Informationen finden Sie unter [Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md).
  
 **F. Ist für den Dienst eine Lizenz für jeden Benutzer in meiner Organisation erforderlich?**
  
Jeder Benutzer in der Organisation benötigt eine Lizenz, der verschlüsselte E-Mails versendet.
  
 **Q. Benötigen externe Empfänger Abonnements?**
  
Nein, externe Empfänger benötigen kein Abonnement zum Lesen oder Beantworten verschlüsselter Nachrichten.
  
 **F. Wie unterscheiden sich Office 365-Nachrichtenverschlüsselung und Rights Management Services (RMS)?**
  
RMS bietet Funktionen zum Schutz von Informationsrechten für interne E-Mails einer Organisation, indem integrierte Vorlagen wie: Nicht weiterleiten und Unternehmensvertraut zur Verfügung stehen. Die Office 365-Nachrichtenverschlüsselung unterstützt die E-Mail-Nachrichtenverschlüsselung für Nachrichten, die an externe Empfänger sowie interne Empfänger gesendet werden.
  
 **F. Wie unterscheiden sich Office 365-Nachrichtenverschlüsselung und S/MIME?**
  
S/MIME ist im Grunde eine clientseitige Verschlüsselungstechnologie, für die eine komplizierte Zertifikatverwaltung und Veröffentlichungsinfrastruktur erforderlich ist. Die Office 365-Nachrichtenverschlüsselung verwendet Nachrichtenflussregeln (auch als Transportregeln bezeichnet) und ist nicht von der Veröffentlichung von Zertifikaten abhängig.
  
 **F. Kann ich über mobile Geräte verschlüsselten Nachrichten lesen?**
  
Ja, Sie können Nachrichten unter Android und iOS anzeigen, indem Sie die OME Viewer-Apps aus dem Google Play Store und dem Apple App Store herunterladen. Öffnen Sie die HTML-Anlage in der OME Viewer-App, und befolgen Sie dann die Anweisungen, um die verschlüsselte Nachricht zu öffnen. Andere mobile Geräte können den HTML-Anhang öffnen, solange der E-Mail-Client Form Post unterstützt.
  
 **F. Sind Antworten und weitergeleitete Nachrichten verschlüsselt?**
  
Ja. Antworten werden während des gesamten Nachrichtenverlaufs weiterhin verschlüsselt.
  
 **F. Bietet die Office 365-Nachrichtenverschlüsselung Eine Lokalisierung?**
  
Eingehende E-Mails und HTML-Inhalte werden basierend auf den E-Maileinstellungen des Absenders lokalisiert. Das Anzeigeportal wird basierend auf den Browsereinstellungen des Empfängers lokalisiert. Allerdings wird der eigentliche Text (Inhalt) der verschlüsselten Nachricht nicht lokalisiert.
  
 **F. Welche Verschlüsselungsmethode wird für die Office 365-Nachrichtenverschlüsselung verwendet?**
  
Die Office 365-Nachrichtenverschlüsselung verwendet Rights Management Services (RMS) als Verschlüsselungsinfrastruktur. Die verwendete Verschlüsselungsmethode hängt davon ab, woher Sie die RMS-Schlüssel zum Verschlüsseln und Entschlüsseln von Nachrichten erhalten.
  
- Wenn Sie Microsoft Azure RMS zum Abrufen der Schlüssel verwenden, wird der Kryptografiemodus 2 verwendet. Kryptografiemodus 2 ist eine aktualisierte und weiterentwickelte Kryptografieimplementierung für AD RMS. Er bietet Unterstützung für RSA 2048 für Signatur und Verschlüsselung sowie Unterstützung für SHA-256 für die Signatur.

- Wenn Sie Active Directory (AD) RMS verwenden, um die Schlüssel abzurufen, wird entweder Kryptografiemodus 1 oder 2 verwendet. Die verwendete Methode hängt von Ihrer lokalen AD RMS-Bereitstellung ab. Kryptografiemodus 1 ist die ursprüngliche Kryptografieimplementierung für AD RMS. Er bietet Unterstützung für RSA 1024 für Signatur und Verschlüsselung sowie Unterstützung für SHA-1 für die Signatur. Dieser Modus wird durch alle aktuellen Versionen von RMS weiter unterstützt.

Weitere Informationen finden Sie unter [AD RMS Cryptographic Modes](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)).
  
**F. Warum geben einige verschlüsselte Nachrichten an, dass sie von Office365@messaging.microsoft.com?**
  
Wenn eine verschlüsselte Antwort aus dem Verschlüsselungsportal oder über die OME Viewer-App gesendet wird, wird die Absender-E-Mail-Adresse auf Office365@messaging.microsoft.com festgelegt, da die verschlüsselte Nachricht über einen Microsoft-Endpunkt gesendet wird. Dadurch wird verhindert, dass verschlüsselte Nachrichten als Spam markiert werden. Der angezeigte Name in der E-Mail und die Adresse im Verschlüsselungsportal werden durch diese Bezeichnung nicht geändert. Außerdem gilt diese Bezeichnung nur für über das Portal gesendete Nachrichten und nicht für Nachrichten, die über einen anderen E-Mail-Client gesendet werden.
  
 **F. Ich bin ein Exchange Hosted Encryption (EHE)-Abonnent. Wo kann ich mehr über das Upgrade auf Office 365-Nachrichtenverschlüsselung erfahren?**
  
Bei allen EHE-Kunden wurde ein Upgrade auf Office 365-Nachrichtenverschlüsselung durchgeführt. Weitere Informationen finden Sie im [Exchange Hosted Encryption Upgrade Center](../security/defender-365-security/exchange-online-protection-overview.md).
  
 **F. Muss ich URLs, IP-Adressen oder Ports in der Firewall meiner Organisation öffnen, um die Office 365-Nachrichtenverschlüsselung zu unterstützen?**
  
Ja. Sie müssen URLs für Exchange Online zur Liste "Zulassen" für Ihre Organisation hinzufügen, damit Nachrichten, die mit der Office 365-Nachrichtenverschlüsselung verschlüsselt wurden, authentifiziert werden können. Eine Liste der Exchange Online-URLs finden Sie unter [Microsoft 365-URLs und IP-Adressbereiche](../enterprise/urls-and-ip-address-ranges.md).
  
 **F. An wie viele Empfänger kann ich eine verschlüsselte Microsoft 365-Nachricht senden?**
  
Der Empfängergrenzwert beträgt 500 Empfänger pro Nachricht oder, wenn er nach der Erweiterung der Verteilerliste kombiniert wird, 11.980 Zeichen im Feld An der Nachricht, je nachdem, was zuerst kommt. 
  
 **F: Ist es möglich, eine Nachricht an einen bestimmten Empfänger zu sperren?**
  
Nein. Sie können eine Nachricht nach dem Senden nicht an eine bestimmte Person widerrufen.
  
 **F: Kann ich einen Bericht über verschlüsselte Nachrichten anzeigen, die empfangen und gelesen wurden?**
  
Es gibt keinen Bericht, der zeigt, ob eine verschlüsselte Nachricht angezeigt wurde, es sind jedoch Microsoft 365-Berichte verfügbar, die Sie verwenden können, um die Anzahl der Nachrichten zu ermitteln, die einer bestimmten Nachrichtenflussregel (auch als Transportregel bezeichnet) entsprechen.
  
 **F. Wofür verwendet Microsoft die von mir über das OME-Portal und die OME-Viewer-App eingegebenen Informationen?**
  
Die [Office 365 Messaging Encryption Portal-Datenschutzbestimmungen](https://privacy.microsoft.com/privacystatement) enthalten detaillierte Informationen dazu, was Microsoft mit Ihren privaten Informationen macht und was nicht.

**F. Was kann ich tun, wenn ich den einmal übergebenen Code nicht erhalte, nachdem ich ihn angefordert habe?**

Überprüfen Sie zunächst den Junk- oder Spamordner in Ihrem E-Mail-Client. DKIM- und DMARC-Einstellungen für Ihre Organisation können dazu führen, dass diese E-Mails als Spam gefiltert werden.

Überprüfen Sie als Nächstes die Quarantäne im Security & Compliance Center. Nachrichten, die einen einmal übergebenen Code enthalten, insbesondere die ersten Nachrichten, die Ihre Organisation empfängt, landen häufig in Quarantäne.