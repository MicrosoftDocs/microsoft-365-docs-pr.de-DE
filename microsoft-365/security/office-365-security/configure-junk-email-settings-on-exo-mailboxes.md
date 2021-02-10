---
title: Konfigurieren der Junk-E-Mail-Einstellungen für Exchange Online-Postfächer
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie die Junk-E-Mail-Einstellungen in Exchange Online-Postfächern konfigurieren. Viele dieser Einstellungen sind für Benutzer in Outlook oder Outlook im Web verfügbar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2aa75376a431ded5abf44ad17ddad4f0ac731fa8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165691"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Konfigurieren der Junk-E-Mail-Einstellungen für Exchange Online-Postfächer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online werden die Antispameinstellungen der Organisation durch Exchange Online Protection (EOP) gesteuert. Weitere Informationen finden Sie unter [Antispamschutz in EOP](anti-spam-protection.md).

Es gibt jedoch auch bestimmte Antispameinstellungen, die Administratoren für einzelne Postfächer in Exchange Online konfigurieren können:

- **Aktivieren oder Deaktivieren der** Junk-E-Mail-Regel: Die Junk-E-Mail-Regel ist eine ausgeblendete Posteingangsregel namens "Junk-E-Mail-Regel", die standardmäßig in jedem Postfach aktiviert ist. Die Junk-E-Mail-Regel steuert die folgenden Features:

  - Verschieben von Nachrichten in den Junk-E-Mail-Ordner basierend auf Antispamrichtlinien: Wenn eine Antispamrichtlinie mit der Aktion "Nachricht in Junk-E-Mail-Ordner verschieben" für eine Spamfilterungs-Filterung konfiguriert ist, verschiebt die **Junk-E-Mail-Filterregel** die Nachricht in den Junk-E-Mail-Ordner, nachdem die Nachricht an das Postfach zugestellt wurde.  Weitere Informationen zu Spamfilterungen in Antispamrichtlinien finden Sie unter ["Konfigurieren von Antispamrichtlinien in EOP".](configure-your-spam-filter-policies.md) Wenn ZAP (Zero-Hour Auto Purge) feststellt, dass es sich bei einer zugestellten Nachricht um Spam  oder Phishing handelt, verschiebt die Junk-E-Mail-Filterregel die Nachricht in den Junk-E-Mail-Ordner, um nachrichten in Spamfilteraktionen des Junk-E-Mail-Ordners zu verschieben. Weitere Informationen zu ZAP finden Sie unter "Automatische Bereinigung zur [Nullstunde" (ZAP) in Exchange Online.](zero-hour-auto-purge.md)

  - **Junk-E-Mail-Einstellungen,** die Benutzer in Outlook  oder Outlook im Web für sich selbst konfigurieren: Die Sammlung von Listen sicherer Adressen ist die Liste sicherer Absender, die Liste sicherer Empfänger und die Liste blockierter Absender in jedem Postfach. Die Einträge in diesen Listen bestimmen, ob die Junk-E-Mail-Regel die Nachricht in den Posteingang oder den Junk-E-Mail-Ordner verschiebt. Benutzer können die Sammlung von Listen sicherer Listen für ihr eigenes Postfach in Outlook oder Outlook im Web (früher als Outlook Web App bekannt) konfigurieren. Administratoren können die Sammlung von Listen sicherer Listen für das Postfach eines beliebigen Benutzers konfigurieren.

Wenn die Junk-E-Mail-Regel für das Postfach aktiviert ist, kann EOP Nachrichten basierend  auf der Spamfilterungsaktion "Nachricht in Junk-E-Mail-Ordner oder Liste blockierter Absender für das Postfach verschieben" in den Junk-E-Mail-Ordner verschieben und verhindern, dass Nachrichten an den Junk-E-Mail-Ordner zugestellt werden (basierend auf der Liste sicherer Absender im Postfach).

 Wenn die Junk-E-Mail-Regel für das Postfach deaktiviert ist, kann EOP Nachrichten nicht  basierend auf der Spamfilterungsaktion "Nachricht in Junk-E-Mail-Ordner oder die Sammlung von Listen sicherer Adressen für das Postfach verschieben" in den Junk-E-Mail-Ordner verschieben.

Administratoren können Exchange Online PowerShell verwenden, um den Status der Junk-E-Mail-Regel für Postfächer zu deaktivieren, zu aktivieren und anzeigen. Administratoren können auch Exchange Online PowerShell verwenden, um Einträge in der Sammlung von Listen sicherer Listen für Postfächer zu konfigurieren (Liste sicherer Absender, Liste sicherer Empfänger und Liste blockierter Absender).

> [!NOTE]
> Nachrichten von Absendern, die Benutzer ihren eigenen Listen sicherer Absender hinzugefügt haben, überspringen die Verbindungsfilterung als Teil von EOP (der SCL ist -1). Um zu verhindern, dass Benutzer Einträge zur Liste sicherer Absender in [](#about-junk-email-settings-in-outlook) Outlook hinzufügen, verwenden Sie Gruppenrichtlinien, wie im Abschnitt "Informationen zu Junk-E-Mail-Einstellungen" weiter unten in diesem Artikel im Abschnitt "Informationen zu Junk-E-Mail". Richtlinienfilterung, Inhaltsfilterung und Überprüfungen von Defender für Office 365 werden weiterhin auf die Nachrichten angewendet.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie können nur Exchange Online PowerShell verwenden, um die Verfahren in diesem Artikel zu tun. Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Rolle "E-Mail-Empfänger" (die  standardmäßig den Rollengruppen    **"Organisationsverwaltung",**"Empfängerverwaltung" und "Benutzerdefinierte E-Mail-Empfänger" zugewiesen ist) oder die Rolle "Benutzeroptionen" (die standardmäßig den Rollengruppen "Organisationsverwaltung" und **"Helpdesk"** zugewiesen ist).  Informationen zum Hinzufügen von Benutzern zu Rollengruppen in Exchange Online finden Sie unter ["Ändern von Rollengruppen in Exchange Online".](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) Beachten Sie, dass Benutzer mit Standardberechtigungen dieselben Verfahren für ihr eigenes Postfach verwenden können, solange sie Zugriff auf [Exchange Online PowerShell haben.](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)

- In Umgebungen mit eigenständigem EOP, in denen EOP lokale Exchange-Postfächer schützt, müssen Sie im lokalen Exchange Nachrichtenflussregeln zur Übersetzung der EOP-Spamfilterbewertung konfigurieren (auch als Transportregeln bezeichnet), damit die Junk-E-Mail-Regel die Nachricht in den Junk-E-Mail-Ordner verschieben kann. Ausführliche Informationen finden Sie unter [Konfigurieren eigenständiger EOP zum Verschieben von Spam in den Junk-E-Mail-Ordner in Hybridumgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- Sichere Absender für freigegebene Postfächer werden nicht standardmäßig mit Azure AD und EOP synchronisiert.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Verwenden von Exchange Online PowerShell zum Aktivieren oder Deaktivieren der Junk-E-Mail-Regel in einem Postfach

> [!NOTE]
> Sie können nur das **Set-MailboxJunkEmailConfiguration** -Cmdlet zum Deaktivieren der Junk-E-Mail-Regel in einem Postfach verwenden, das in Outlook (im Exchange-Cachemodus) oder Outlook im Web geöffnet wurde. Wenn das Postfach nicht geöffnet wurde, wird die Fehlermeldung angezeigt: Wenn Sie diesen Fehler für Massenvorgänge unterdrücken möchten, können Sie ihn dem Befehl `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **"Set-MailboxJunkEmailConfiguration"** hinzufügen.

Verwenden Sie zum Aktivieren oder Deaktivieren der Junk-E-Mail-Regel in einem Postfach die folgende Syntax:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

In diesem Beispiel wird die Junk-E-Mail-Regel im Postfach von Ori Epstein deaktiviert.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

In diesem Beispiel wird die Junk-E-Regel in den Postfächern aller Benutzer in der Organisation deaktiviert.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Wenn der Benutzer sein Postfach noch nie geöffnet hat, wird beim Ausführen des vorherigen Befehls möglicherweise eine Fehlermeldung angezeigt. Um diesen Fehler bei Massenvorgängen zu unterdrücken, fügen Sie den Befehl `-ErrorAction SilentlyContinue` **"Set-MailboxJunkEmailConfiguration"** hinzu.
>
> - Auch wenn Sie die Junk-E-Mail-Regel deaktivieren, kann der Outlook-Junk-E-Mail-Filter (je nach Konfiguration) auch bestimmen, ob es sich bei einer Nachricht um Spam handelt, und Nachrichten basierend auf seiner eigenen Spam-E-Mail-Bestimmung und der Sammlung von Listen sicherer Adressen für das Postfach in den Posteingang oder Junk-E-Mail-Ordner verschieben. Weitere Informationen finden Sie im Abschnitt "Informationen zu [Junk-E-Mail-Einstellungen in Outlook"](#about-junk-email-settings-in-outlook) in diesem Artikel.

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Befolgen Sie einen der folgenden Schritte, um zu überprüfen, ob die Junk-E-Mail-Regel für ein Postfach erfolgreich aktiviert bzw. deaktiviert wurde:

- Ersetzen Sie den Namen, alias oder die E-Mail-Adresse des Postfachs, und führen Sie den folgenden Befehl aus, um den Wert der _\<MailboxIdentity\>_ Eigenschaft **"Enabled"** zu überprüfen:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Konfigurieren der Sammlung von Listen sicherer Listen für ein Postfach mithilfe von Exchange Online PowerShell

Die Sammlung von Listen sicherer Adressen für ein Postfach umfasst die Liste sicherer Absender, die Liste sicherer Empfänger und die Liste blockierter Absender. Standardmäßig können Benutzer die Sammlung von Listen sicherer Listen für ihr eigenes Postfach in Outlook oder Outlook im Web konfigurieren. Administratoren können die entsprechenden Parameter im **Set-MailboxJunkEmailConfiguration** -Cmdlet zum Konfigurieren der Sammlung von Listen sicherer Adressen für ein Benutzerpostfach verwenden. Diese Parameter werden in der folgenden Tabelle beschrieben.

****

|Parameter für Set-MailboxJunkEmailConfiguration|Outlook im Web-Einstellung|
|---|---|
|_BlockedSendersAndDomains_|**E-Mails von diesen Absendern und Domänen in Junk-E-Mail-Ordner verschieben.**|
|_ContactsTrusted_|**Meine Kontakte sind vertrauenswürdige Absender**|
|_TrustedListsOnly_|**Vertrauenswürdige E-Mails von Adressen in der Liste sicherer Absender und Domänen und sicherer Adressen**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**E-Mails von diesen Absendern nicht in meinen Junk-E-Mail-Ordner verschieben**|
|

<sup>\*</sup>**Hinweise:**

- In Exchange Online werden **Domäneneinträge** in der Liste sicherer Absender oder der Parameter _"TrustedSendersAndDomains"_ nicht erkannt. Verwenden Sie daher nur E-Mail-Adressen. In eigenständigem EOP mit Verzeichnissynchronisierung werden Domäneneinträge nicht standardmäßig synchronisiert, Aber Sie können die Synchronisierung für Domänen aktivieren. Weitere Informationen finden Sie unter [KB3019657](https://support.microsoft.com/help/3019657).

- Sie können die Liste sicherer Empfänger nicht direkt mithilfe des Cmdlets **"Set-MailboxJunkEmailConfiguration"** ändern (der Parameter _"TrustedRecipientsAndDomains"_ funktioniert nicht). Sie ändern die Liste sicherer Absender, und diese Änderungen werden mit der Liste sicherer Empfänger synchronisiert.

Verwenden Sie zum Konfigurieren der Sammlung von Listen sicherer Adressen in einem Postfach die folgende Syntax:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Verwenden Sie die folgende Syntax, um mehrere Werte ein- und vorhandene Einträge für die Parameter _"BlockedSendersAndDomains"_ und _"TrustedSendersAndDomains"_ zu `"<Value1>","<Value2>"...` überschreiben: Verwenden Sie die folgende Syntax, um einen oder mehrere Werte ohne Auswirkungen auf andere Einträge hinzuzufügen oder zu entfernen: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

In diesem Beispiel werden die folgenden Einstellungen für die Sammlung von Listen sicherer Adressen für das Postfach von Ori Epstein konfiguriert:

- Fügen Sie den wert shopping@fabrikam.com der Liste blockierter Absender hinzu.

- Entfernen Sie den wert chris@fourthcoffee.com aus der Liste sicherer Absender und der Liste sicherer Empfänger.

- Die Kontakte in dem Ordner „Kontakte" werden als vertrauenswürdige Absender konfiguriert.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

In diesem Beispiel wird die Domäne „contoso.com" aus der Liste blockierter Absender in allen Benutzerpostfächern in der Organisation entfernt.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Wenn der Benutzer sein Postfach noch nie geöffnet hat, erhalten Sie möglicherweise eine Fehlermeldung, wenn Sie die vorherigen Befehle ausführen. Um diesen Fehler bei Massenvorgängen zu unterdrücken, fügen Sie den Befehl `-ErrorAction SilentlyContinue` **"Set-MailboxJunkEmailConfiguration"** hinzu.
>
> - Auch wenn die Junk-E-Mail-Regel für das Postfach deaktiviert ist, können Sie dennoch die Sammlung von Listen sicherer Adressen konfigurieren, und der Outlook-Junk-E-Mail-Filter kann Nachrichten in den Posteingang oder den Junk-E-Mail-Ordner verschieben. Weitere Informationen finden Sie im Abschnitt "Informationen zu [Junk-E-Mail-Einstellungen in Outlook"](#about-junk-email-settings-in-outlook) in diesem Artikel.
>
> - Der Outlook-Junk-E-Mail-Filter verfügt über zusätzliche Einstellungen für die Sammlung von Listen sicherer Adressen (z. B. "Automatisch Personen, die ich E-Mail zur Liste sicherer **Absender hinzufügen kann").** Weitere Informationen finden Sie unter [Verwenden von Junk-E-Mail-Filtern, um zu steuern, welche Nachrichten angezeigt werden.](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Verwenden Sie eine der folgenden Vorgehensweisen, um sicherzustellen, dass die Sammlung von Listen sicherer Adressen für ein Postfach erfolgreich konfiguriert wurde:

- Ersetzen Sie den Namen, alias oder die E-Mail-Adresse des Postfachs, und führen Sie den folgenden Befehl _\<MailboxIdentity\>_ aus, um die Eigenschaftswerte zu überprüfen:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Verwenden Sie folgende Syntax, wenn die Liste der Werte zu lang ist:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Grundlegendes zu Junk-E-Mail-Einstellungen in Outlook

Verwenden Sie Gruppenrichtlinien zum Aktivieren, Deaktivieren und Konfigurieren der clientseitigen Junk-E-Mail-Filtereinstellungen, die in Outlook verfügbar sind. Weitere Informationen finden Sie unter [Administrative Vorlagendateien (ADMX/ADML) und im Office-Anpassungstool für Microsoft 365 Apps for Enterprise, Office 2019 und Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) sowie unter Bereitstellen von Junk-E-Mail-Einstellungen, z. B. der Liste sicherer Absender, mithilfe von [Gruppenrichtlinien.](https://support.microsoft.com/help/2252421)

Wenn der Outlook-Junk-E-Mail-Filter auf den Standardwert "Keine automatische **Filterung"** **in** den Optionen für \>  \> **Junk-E-Mail-Start** festgelegt ist, versucht Outlook nicht, Junk-E-Mail-Nachrichten als Spam zu klassifizieren, sondern verwendet weiterhin die Sammlung von Listen sicherer Adressen (Liste sicherer Absender, Liste sicherer Empfänger und blockierter Absender), um Nachrichten nach der Zustellung in den Junk-E-Mail-Ordner zu \> verschieben. Weitere Informationen zu diesen Einstellungen finden Sie unter [Übersicht über den Junk-E-Mail-Filter.](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)

Wenn der Outlook-Junk-E-Mail-Filter auf **Niedrig** oder **Hoch** gesetzt ist, verwendet der Outlook-Junk-E-Mail-Filter eine eigene SmartScreen-Filtertechnologie zum Identifizieren und Verschieben von Spam in den Junk-E-Mail-Ordner. Diese Spamklassifikation ist von der SCL (Spam Confidence Level) getrennt, die von EOP bestimmt wird. Tatsächlich ignoriert Outlook den SCL von EOP (es sei denn, EOP hat die Nachricht zum Überspringen der Spamfilterung markiert) und verwendet eigene Kriterien, um festzustellen, ob es sich bei der Nachricht um Spam handelt. Natürlich ist es möglich, dass die Spam-EOP- und Outlook-Spam-Beknung identisch ist. Weitere Informationen zu diesen Einstellungen finden Sie unter ["Ändern des Schutzniveaus im Junk-E-Mail-Filter".](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)

> [!NOTE]
> Im November 2016 stoppte Microsoft die Erstellung von Spamdefinitionsupdates für die SmartScreen-Filter in Exchange und Outlook. Die vorhandenen SmartScreen-Spamdefinitionen wurden noch vorhanden, aber ihre Effektivität wird im Laufe der Zeit wahrscheinlich beeinträchtigt werden. Weitere Informationen finden Sie unter [Support für SmartScreen in Outlook und Exchange eingestellt](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Der Outlook-Junk-E-Mail-Filter kann also die Sammlung von Listen sicherer Adressen und seine eigene Spamklassifikation verwenden, um Nachrichten in den Junk-E-Mail-Ordner zu verschieben, auch wenn die Junk-E-Mail-Regel im Postfach deaktiviert ist.

Die Sammlung von Listen sicherer Adressen wird sowohl in Outlook als auch in Outlook im Web unterstützt. Die Sammlung von Listen sicherer Listen wird im Exchange Online-Postfach gespeichert, sodass Änderungen an der Sammlung von Listen sicherer Listen in Outlook in Outlook im Web angezeigt werden und umgekehrt.

## <a name="limits-for-junk-email-settings"></a>Grenzwerte für Junk-E-Mail-Einstellungen

Die Sammlung von Listen sicherer Absender (Liste sicherer Absender, Liste sicherer Empfänger und blockierter Absender), die im Postfach des Benutzers gespeichert ist, wird ebenfalls mit EOP synchronisiert. Bei der Verzeichnissynchronisierung wird die Sammlung von Listen sicherer Listen mit Azure AD synchronisiert.

- Die Sammlung von Listen sicherer Adressen im Postfach des Benutzers hat einen Grenzwert von 510 KB, einschließlich aller Listen sowie zusätzlicher Junk-E-Mail-Filtereinstellungen. Wenn ein Benutzer diesen Grenzwert überschreitet, erhält er eine Outlook-Fehlermeldung, die wie dies aussieht:

  > Die Junk-E-Mail-Listen des Servers können nicht hinzugefügt werden. Sie sind über der auf dem Server zulässigen Größe. Der Junk-E-Mail-Filter auf dem Server wird deaktiviert, bis ihre Junk-E-Mail-Listen auf die vom Server zulässige Größe reduziert wurden.

  Weitere Informationen zu diesem Grenzwert und zur Änderung finden Sie unter [KB2669081](https://support.microsoft.com/help/2669081).

- Die synchronisierte Sammlung von Listen sicherer Listen in EOP hat die folgenden Synchronisierungsgrenzwerte:

  - 1024 Einträge insgesamt in der Liste sicherer Absender, der Liste sicherer Empfänger und externer Kontakte, wenn E-Mails mit Vertrauensstellung von meinen **Kontakten** aktiviert sind.
  - 500 Einträge insgesamt in der Liste blockierter Absender und blockierter Domänen.

  Wenn der Grenzwert von 1024 erreicht ist, geschieht Folgendes:

  - Die Liste akzeptiert keine Einträge mehr in PowerShell und Outlook im Web, es wird jedoch kein Fehler angezeigt.

    Benutzer von Outlook können weiterhin mehr als 1024 Einträge hinzufügen, bis sie den Grenzwert für Outlook von 510 KB erreichen. Outlook kann diese zusätzlichen Einträge verwenden, solange ein EOP-Filter die Nachricht vor der Zustellung an das Postfach nicht blockiert (Nachrichtenflussregeln, Antis spoofing usw.).

- Bei der Verzeichnissynchronisierung werden die Einträge in der folgenden Reihenfolge mit Azure AD synchronisiert:

  1. E-Mail-Kontakte, **wenn "E-Mail-Vertrauensstellung von meinen Kontakten"** aktiviert ist.
  2. Die Liste sicherer Absender und die Liste sicherer Empfänger werden kombiniert, dedupliziert und alphabetisch sortiert, wenn eine Änderung für die ersten 1024 Einträge vorgenommen wird.

  Die ersten 1024 Einträge werden verwendet, und relevante Informationen werden in den Nachrichtenkopfzeilen gestempelt.

  Einträge über 1024, die nicht mit Azure AD synchronisiert wurden, werden von Outlook verarbeitet (nicht von Outlook im Web), und es werden keine Informationen in den Nachrichtenkopfzeilen gestempelt.

Wie Sie sehen können, reduziert das Aktivieren der Einstellung "E-Mail-Vertrauensstellung aus meinen Kontakten" die Anzahl der sicheren Absender und sicheren Empfänger, die synchronisiert werden können.  Wenn dies ein Problem ist, empfehlen wir die Verwendung von Gruppenrichtlinien, um dieses Feature zu deaktivieren:

- Dateiname: outlk16.opax
- Richtlinieneinstellung: **E-Mail von Kontakten vertrauen**
