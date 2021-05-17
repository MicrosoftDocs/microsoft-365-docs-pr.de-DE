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
description: Administratoren erfahren, wie Sie die Junk-E-Mail-Einstellungen in Exchange Online konfigurieren. Viele dieser Einstellungen stehen Benutzern in Outlook oder Outlook im Web zur Verfügung.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7e5d99198e539a46c240fadd2a7a8201236026f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203946"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Konfigurieren der Junk-E-Mail-Einstellungen für Exchange Online-Postfächer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Postfächern in Exchange Online werden die Antispameinstellungen der Organisation durch EOP (EOP Exchange Online Protection gesteuert. Weitere Informationen finden Sie unter [Antispamschutz in EOP](anti-spam-protection.md).

Es gibt jedoch auch bestimmte Antispameinstellungen, die Administratoren für einzelne Postfächer in der Exchange Online:

- **Aktivieren oder Deaktivieren der** Junk-E-Mail-Regel: Die Junk-E-Mail-Regel ist eine ausgeblendete Posteingangsregel namens Junk-E-Mail-Regel, die standardmäßig in jedem Postfach aktiviert ist. Die Junk-E-Mail-Regel steuert die folgenden Features:

  - Verschieben von Nachrichten in den Junk-E-Mail-Ordner basierend auf Antispamrichtlinien: Wenn eine Antispamrichtlinie mit der Aktion Nachricht in Junk-E-Mail-Ordner verschieben für ein Spamfilter-Urteil konfiguriert ist, verschiebt die Junk-E-Mail-Filterregel die Nachricht in den Junk-E-Mail-Ordner, nachdem die Nachricht an das Postfach zugestellt wurde.   Weitere Informationen zu Spamfilterungen in Antispamrichtlinien finden Sie unter [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md). In ähnlicher Weise wird die Nachricht von der Junk-E-Mail-Filterregel in den Junk-E-Mail-Ordner  verschoben, wenn die automatische Reinigung (Zero-Hour Auto Purge, ZAP) feststellt, dass eine zugestellte Nachricht Spam oder Phishing ist. Weitere Informationen zu ZAP finden Sie unter [Zero-Hour Auto Purge (ZAP) in Exchange Online](zero-hour-auto-purge.md).

  - Junk-E-Mail-Einstellungen, die Benutzer **in Outlook** oder Outlook im  Web für sich selbst konfigurieren: Die Sammlung sicherer Adressen ist die Liste sicherer Absender, die Liste sicherer Empfänger und die Liste der blockierten Absender in jedem Postfach. Die Einträge in diesen Listen bestimmen, ob die Junk-E-Mail-Regel die Nachricht in den Posteingang oder den Junk-E-Mail-Ordner verschiebt. Benutzer können die Sammlung sicherer Listen für ihr eigenes Postfach in Outlook oder Outlook im Web konfigurieren (früher als Outlook Web App). Administratoren können die Sammlung sicherer Listen für das Postfach eines beliebigen Benutzers konfigurieren.

Wenn die Junk-E-Mail-Regel für das Postfach aktiviert ist, kann EOP Nachrichten in  den Junk-E-Mail-Ordner verschieben, basierend auf der Spamfilterungsverknungsaktion Nachricht in Junk-E-Mail-Ordner oder die Liste blockierter Absender im Postfach verschieben und verhindern, dass Nachrichten an den Junk-E-Mail-Ordner zugestellt werden (basierend auf der Liste sicherer Absender im Postfach).

 Wenn die Junk-E-Mail-Regel für das Postfach deaktiviert ist, kann EOP Nachrichten nicht in den Junk-E-Mail-Ordner verschieben, basierend auf der Spamfilterungs-Verdict-Aktion **Nachricht** in Junk-E-Mail-Ordner oder die Sammlung sicherer Adressen im Postfach verschieben.

Administratoren können mithilfe Exchange Online PowerShell den Status der Junk-E-Mail-Regel für Postfächer deaktivieren, aktivieren und anzeigen. Administratoren können auch Exchange Online PowerShell verwenden, um Einträge in der Sammlung sicherer Listen für Postfächer zu konfigurieren (die Liste sicherer Absender, die Liste sicherer Empfänger und die Liste blockierter Absender).

> [!NOTE]
> Nachrichten von Absendern, die Benutzer ihren eigenen Listen sicherer Absender hinzugefügt haben, überspringen die Verbindungsfilterung im Rahmen von EOP (die SCL ist -1). Um zu verhindern, dass Benutzer ihrer Liste sicherer Absender in Outlook Einträge hinzufügen, verwenden Sie Gruppenrichtlinien, wie weiter unten in diesem Artikel im Abschnitt Informationen zu Junk-E-Mail-Einstellungen [in Outlook](#about-junk-email-settings-in-outlook) erwähnt. Richtlinienfilterung, Inhaltsfilterung und Defender für Office 365 werden weiterhin auf die Nachrichten angewendet.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie können powerShell Exchange Online verwenden, um die Verfahren in diesem Artikel zu tun. Wie Sie eine Verbindung mit Exchange Online-PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel Exchange Online, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Rolle E-Mail-Empfänger (die standardmäßig  den Rollengruppen Organisationsverwaltung, Empfängerverwaltung und benutzerdefinierte E-Mail-Empfänger zugewiesen ist) oder die Rolle Benutzeroptionen (die standardmäßig den Rollengruppen Organisationsverwaltung und  **Helpdesk** zugewiesen ist).     Informationen zum Hinzufügen von Benutzern zu Rollengruppen in Exchange Online finden Sie unter [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups). Beachten Sie, dass Benutzer mit Standardberechtigungen dieselben Verfahren für ihr eigenes Postfach verwenden können, solange sie Zugriff auf [Exchange Online PowerShell haben.](/powershell/exchange/disable-access-to-exchange-online-powershell)

- In Umgebungen mit eigenständigem EOP, in denen EOP lokale Exchange-Postfächer schützt, müssen Sie im lokalen Exchange Nachrichtenflussregeln zur Übersetzung der EOP-Spamfilterbewertung konfigurieren (auch als Transportregeln bezeichnet), damit die Junk-E-Mail-Regel die Nachricht in den Junk-E-Mail-Ordner verschieben kann. Ausführliche Informationen finden Sie unter [Konfigurieren eigenständiger EOP zum Verschieben von Spam in den Junk-E-Mail-Ordner in Hybridumgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- Sichere Absender für freigegebene Postfächer werden nicht entwurfsweise mit Azure AD und EOP synchronisiert.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Verwenden Exchange Online PowerShell zum Aktivieren oder Deaktivieren der Junk-E-Mail-Regel in einem Postfach

> [!NOTE]
> Sie können nur das **Set-MailboxJunkEmailConfiguration** -Cmdlet zum Deaktivieren der Junk-E-Mail-Regel in einem Postfach verwenden, das in Outlook (im Exchange-Cachemodus) oder Outlook im Web geöffnet wurde. Wenn das Postfach nicht geöffnet wurde, wird die Fehlermeldung angezeigt: Wenn Sie diesen Fehler für Massenvorgänge unterdrücken möchten, können Sie dem Befehl `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration** hinzufügen.

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Wenn der Benutzer sein Postfach nie geöffnet hat, wird möglicherweise eine Fehlermeldung angezeigt, wenn Sie den vorherigen Befehl ausführen. Um diesen Fehler für Massenvorgänge zu unterdrücken, fügen Sie `-ErrorAction SilentlyContinue` dem **Befehl Set-MailboxJunkEmailConfiguration** hinzu.
>
> - Selbst wenn Sie die Junk-E-Mail-Regel deaktivieren, kann der junk-E-Mail-Filter von Outlook (je nach Konfiguration) auch bestimmen, ob es sich bei einer Nachricht um Spam handelt, und nachrichten basierend auf seinem eigenen Spam-Urteil und der Sammlung sicherer Adressen im Postfach in den Posteingang oder junk-E-Mail-Ordner verschieben. Weitere Informationen finden Sie im Abschnitt Informationen zu [Junk-E-Mail-Outlook](#about-junk-email-settings-in-outlook) in diesem Artikel.

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Befolgen Sie einen der folgenden Schritte, um zu überprüfen, ob die Junk-E-Mail-Regel für ein Postfach erfolgreich aktiviert bzw. deaktiviert wurde:

- Ersetzen Sie durch den Namen, alias oder die E-Mail-Adresse des Postfachs, und führen Sie den folgenden Befehl aus, um den _\<MailboxIdentity\>_ Wert der **Enabled-Eigenschaft** zu überprüfen:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Verwenden Exchange Online PowerShell zum Konfigurieren der Sammlung sicherer Listen in einem Postfach

Die Sammlung von Listen sicherer Adressen für ein Postfach umfasst die Liste sicherer Absender, die Liste sicherer Empfänger und die Liste blockierter Absender. Standardmäßig können Benutzer die Sammlung sicherer Listen für ihr eigenes Postfach in Outlook oder Outlook im Web konfigurieren. Administratoren können die entsprechenden Parameter im **Set-MailboxJunkEmailConfiguration** -Cmdlet zum Konfigurieren der Sammlung von Listen sicherer Adressen für ein Benutzerpostfach verwenden. Diese Parameter werden in der folgenden Tabelle beschrieben.

****

|Parameter für Set-MailboxJunkEmailConfiguration|Outlook im Web|
|---|---|
|_BlockedSendersAndDomains_|**E-Mails von diesen Absendern und Domänen in Junk-E-Mail-Ordner verschieben.**|
|_ContactsTrusted_|**Meine Kontakte sind vertrauenswürdige Absender**|
|_TrustedListsOnly_|**Nur E-Mails von Adressen in der Liste sicherer Absender und Domänen sowie sichere Mailinglisten vertrauenswürdig**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**E-Mails von diesen Absendern nicht in meinen Junk-E-Mail-Ordner verschieben**|
|

<sup>\*</sup>**Hinweise**:

- In Exchange Online werden **Domäneneinträge** in der Liste sicherer Absender oder _des Parameters TrustedSendersAndDomains_ nicht erkannt. Verwenden Sie daher nur E-Mail-Adressen. In eigenständigem EOP mit Verzeichnissynchronisierung werden Domäneneinträge standardmäßig nicht synchronisiert, Aber Sie können die Synchronisierung für Domänen aktivieren. Weitere Informationen finden Sie unter [KB3019657](https://support.microsoft.com/help/3019657).

- Sie können die Liste sicherer Empfänger nicht direkt mithilfe des **Cmdlets Set-MailboxJunkEmailConfiguration** ändern (der _Parameter TrustedRecipientsAndDomains_ funktioniert nicht). Sie ändern die Liste sicherer Absender, und diese Änderungen werden mit der Liste sicherer Empfänger synchronisiert.

Verwenden Sie zum Konfigurieren der Sammlung von Listen sicherer Adressen in einem Postfach die folgende Syntax:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Verwenden Sie die folgende Syntax, um mehrere Werte ein- und alle vorhandenen Einträge für die _Parameter BlockedSendersAndDomains_ und _TrustedSendersAndDomains_ zu überschreiben: `"<Value1>","<Value2>"...` . Verwenden Sie die folgende Syntax, um einen oder mehrere Werte hinzuzufügen oder zu entfernen, ohne andere vorhandene Einträge zu beeinträchtigen: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

In diesem Beispiel werden die folgenden Einstellungen für die Sammlung von Listen sicherer Adressen für das Postfach von Ori Epstein konfiguriert:

- Fügen Sie den Wert shopping@fabrikam.com der Liste blockierter Absender hinzu.

- Entfernen Sie den wert chris@fourthcoffee.com aus der Liste sicherer Absender und der Liste sicherer Empfänger.

- Die Kontakte in dem Ordner „Kontakte" werden als vertrauenswürdige Absender konfiguriert.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

In diesem Beispiel wird die Domäne „contoso.com" aus der Liste blockierter Absender in allen Benutzerpostfächern in der Organisation entfernt.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Wenn der Benutzer sein Postfach nie geöffnet hat, wird möglicherweise eine Fehlermeldung angezeigt, wenn Sie die vorherigen Befehle ausführen. Um diesen Fehler für Massenvorgänge zu unterdrücken, fügen Sie `-ErrorAction SilentlyContinue` dem **Befehl Set-MailboxJunkEmailConfiguration** hinzu.
>
> - Auch wenn die Junk-E-Mail-Regel für das Postfach deaktiviert ist, können Sie dennoch die Sammlung sicherer Adressen konfigurieren, und der junk-E-Mail-Filter Outlook kann Nachrichten in den Posteingang oder den Junk-E-Mail-Ordner verschieben. Weitere Informationen finden Sie im Abschnitt Informationen zu [Junk-E-Mail-Outlook](#about-junk-email-settings-in-outlook) in diesem Artikel.
>
> - Der Outlook Junk-E-Mail-Filter verfügt über zusätzliche Einstellungen für die Sammlung von Listen sicherer Adressen (z. B. Automatisches Hinzufügen von E-Mails zur Liste sicherer **Absender).** Weitere Informationen finden Sie unter [Verwenden von Junk-E-Mail-Filtern, um zu steuern, welche Nachrichten angezeigt werden.](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Verwenden Sie eine der folgenden Vorgehensweisen, um sicherzustellen, dass die Sammlung von Listen sicherer Adressen für ein Postfach erfolgreich konfiguriert wurde:

- Ersetzen Sie durch den Namen, alias oder die E-Mail-Adresse des Postfachs, und führen Sie den folgenden Befehl aus, um _\<MailboxIdentity\>_ die Eigenschaftswerte zu überprüfen:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Wenn die Liste der Werte zu lang ist, verwenden Sie die folgende Syntax:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Grundlegendes zu Junk-E-Mail-Einstellungen in Outlook

Verwenden Sie Gruppenrichtlinien zum Aktivieren, Deaktivieren und Konfigurieren der clientseitigen Junk-E-Mail-Filtereinstellungen, die in Outlook verfügbar sind. Weitere Informationen finden Sie unter [Administrative Vorlagendateien (ADMX/ADML) und Office-Anpassungstool für Microsoft 365 Apps for Enterprise, Office 2019 und Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) und Bereitstellen von Junk-E-Mail-Einstellungen wie der Liste sicherer Absender mithilfe von [Gruppenrichtlinien](https://support.microsoft.com/help/2252421).

Wenn der Outlook-Junk-E-Mail-Filter auf den Standardwert No automatic **filtering** in **Home** \> **Junk** E-Mail Options Options festgelegt ist, versucht Outlook nicht, Die Spams als Spam zu klassifizieren, verwendet jedoch weiterhin die Sammlung sicherer Adressen (liste sicherer Absender, Liste sicherer Empfänger und blockierte Absender), um Nachrichten nach der Zustellung in den Junk-E-Mail-Ordner zu \>  \> verschieben. Weitere Informationen zu diesen Einstellungen finden Sie [unter Übersicht über den Junk-E-Mail-Filter](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

Wenn der Outlook-Junk-E-Mail-Filter auf **Niedrig** oder **Hoch** gesetzt ist, verwendet der Outlook-Junk-E-Mail-Filter eine eigene SmartScreen-Filtertechnologie zum Identifizieren und Verschieben von Spam in den Junk-E-Mail-Ordner. Diese Spamklassifizierung ist von der Spamsicherheitsstufe (Spam Confidence Level, SCL) getrennt, die von EOP bestimmt wird. Tatsächlich ignoriert Outlook die SCL von EOP (es sei denn, EOP hat die Nachricht zum Überspringen der Spamfilterung markiert) und verwendet eigene Kriterien, um zu bestimmen, ob es sich bei der Nachricht um Spam handelt. Natürlich ist es möglich, dass das Spam-Urteil von EOP und Outlook identisch ist. Weitere Informationen zu diesen Einstellungen finden Sie unter [Ändern des Schutzniveaus im Junk-E-Mail-Filter](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b).

> [!NOTE]
> Im November 2016 hat Microsoft die Erstellung von Spamdefinitionsupdates für die SmartScreen-Filter in Exchange und Outlook. Die vorhandenen SmartScreen-Spamdefinitionen wurden zwar noch vorhanden, aber ihre Effektivität wird im Laufe der Zeit wahrscheinlich beeinträchtigt. Weitere Informationen finden Sie unter [Support für SmartScreen in Outlook und Exchange eingestellt](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Daher kann Outlook Junk-E-Mail-Filter die Sammlung sicherer Adressen des Postfachs und eine eigene Spamklassifizierung verwenden, um Nachrichten in den Junk-E-Mail-Ordner zu verschieben, auch wenn die Junk-E-Mail-Regel im Postfach deaktiviert ist.

Die Sammlung von Listen sicherer Adressen wird sowohl in Outlook als auch in Outlook im Web unterstützt. Die Sammlung sicherer Listen wird im postfach Exchange Online gespeichert, sodass Änderungen an der Sammlung sicherer Listen in Outlook in Outlook im Web angezeigt werden und umgekehrt.

## <a name="limits-for-junk-email-settings"></a>Grenzwerte für Junk-E-Mail-Einstellungen

Die Im Postfach des Benutzers gespeicherte Sammlung sicherer Absender (Liste sicherer Absender, Liste sicherer Empfänger und blockierter Absender) wird ebenfalls mit EOP synchronisiert. Bei der Verzeichnissynchronisierung wird die Sammlung sicherer Listen mit Azure AD synchronisiert.

- Die Sammlung von Listen sicherer Adressen im Postfach des Benutzers hat einen Grenzwert von 510 KB, der alle Listen sowie zusätzliche Junk-E-Mail-Filtereinstellungen umfasst. Wenn ein Benutzer diesen Grenzwert überschreitet, erhält er Outlook, der wie dies aussieht:

  > Junk-E-Mail-Listen des Servers können nicht hinzugefügt werden. Sie sind über der auf dem Server zulässigen Größe. Der Junk-E-Mail-Filter auf dem Server wird deaktiviert, bis Ihre Junk-E-Mail-Listen auf die vom Server zulässige Größe reduziert wurden.

  Weitere Informationen zu diesem Grenzwert und zur Änderung finden Sie unter [KB2669081](https://support.microsoft.com/help/2669081).

- Die synchronisierte Sammlung sicherer Listen in EOP hat die folgenden Synchronisierungsgrenzwerte:

  - Insgesamt 1024 Einträge in der Liste sicherer Absender, der Liste sicherer Empfänger und externer Kontakte, wenn **E-Mail** von meinen Kontakten vertrauen aktiviert ist.
  - 500 Einträge insgesamt in der Liste blockierter Absender und blockierter Domänen.

  Wenn der Grenzwert von 1024 erreicht ist, geschieht Folgendes:

  - Die Liste akzeptiert keine Einträge in PowerShell und Outlook im Web, es wird jedoch kein Fehler angezeigt.

    Outlook benutzer können weiterhin mehr als 1024 Einträge hinzufügen, bis sie die Outlook von 510 KB erreichen. Outlook können diese zusätzlichen Einträge verwenden, solange ein EOP-Filter die Nachricht vor der Zustellung an das Postfach nicht blockiert (Nachrichtenflussregeln, Antis spoofing usw.).

- Bei der Verzeichnissynchronisierung werden die Einträge in der folgenden Reihenfolge mit Azure AD synchronisiert:

  1. E-Mail-Kontakte, **wenn E-Mail von meinen Kontakten vertrauen** aktiviert ist.
  2. Die Liste sicherer Absender und die Liste sicherer Empfänger werden bei jeder Änderung der ersten 1024-Einträge kombiniert, dedupliziert und alphabetisch sortiert.

  Die ersten 1024 Einträge werden verwendet, und relevante Informationen werden in den Nachrichtenkopfzeilen gestempelt.

  Einträge über 1024, die nicht mit Azure AD synchronisiert wurden, werden von Outlook verarbeitet (nicht Outlook im Web), und es werden keine Informationen in den Nachrichtenkopfzeilen gestempelt.

Wie Sie sehen können, reduziert das Aktivieren der Einstellung E-Mail von **meinen** Kontakten vertrauen die Anzahl sicherer Absender und sicherer Empfänger, die synchronisiert werden können. Wenn dies ein Problem ist, empfehlen wir die Verwendung von Gruppenrichtlinien, um dieses Feature zu deaktivieren:

- Dateiname: outlk16.opax
- Richtlinieneinstellung: **E-Mail von Kontakten vertrauen**