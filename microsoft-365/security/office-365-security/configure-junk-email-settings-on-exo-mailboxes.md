---
title: Konfigurieren der Junk-E-Mail-Einstellungen für Exchange Online-Postfächer
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie die Junk-e-Mail-Einstellungen in Exchange Online Postfächern konfigurieren. Viele dieser Einstellungen stehen Benutzern in Outlook oder Outlook im Internet zur Verfügung.
ms.openlocfilehash: 4e40e3fa2186022a64c8ccdf66f62db24b9f9794
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755260"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Konfigurieren der Junk-E-Mail-Einstellungen für Exchange Online-Postfächer

In Microsoft 365-Organisationen mit Postfächern in Exchange Online werden die Einstellungen für die Antispam-Organisation durch Exchange Online Protection (EoP) gesteuert. Weitere Informationen finden Sie unter [Anti-Spam Protection in EoP](anti-spam-protection.md).

Es gibt aber auch spezifische Antispam-Einstellungen, die Administratoren für einzelne Postfächer in Exchange Online konfigurieren können:

- **Aktivieren oder Deaktivieren der Junk-e-Mail-** Regel: die Junk-e-Mail-Regel ist eine verborgene Posteingangsregel namens Junk-e-Mail-Regel, die in jedem Postfach standardmäßig aktiviert ist. Die Junk-e-Mail-Regel steuert die folgenden Funktionen:

  - **Verschieben von Nachrichten in den Junk-e-Mail-Ordner auf der Grundlage von Anti-Spam-Richtlinien**: Wenn eine Antispampolitik mit dem Vorgang **Nachricht in Junk-e-Mail verschieben** für ein Spamfilter Urteil konfiguriert ist, verschiebt die Junk-e-Mail-Filterregel die Nachricht in den Junk-e-Mail-Ordner, nachdem die Nachricht an das Postfach gesendet wurde. Weitere Informationen zu Spamfilter Urteilen in Anti-Spam-Richtlinien finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md). Ebenso verschiebt die Junk-e-Mail-Filterregel die Nachricht in den Ordner Junk-e-Mail-Nachricht **in Junk-e** -Mail-Spamfilter-Urteils Aktionen, wenn Zero-Hour Auto Purge (zap) feststellt, dass eine zugestellte Nachricht Spam oder Phishing ist. Weitere Informationen zu zap finden Sie unter [Zero-Hour Auto Purge (zap) in Exchange Online](zero-hour-auto-purge.md).

  - **Junk-e-Mail-Einstellungen, die Benutzer in Outlook oder Outlook im Internet für sich selbst konfigurieren**: die _Sammlung_ von Listen sicherer Adressen ist die Liste sicherer Absender, die Liste Sichere Empfänger und die Liste Absender blockieren für jedes Postfach. Die Einträge in diesen Listen bestimmen, ob die Junk-e-Mail-Regel die Nachricht in den Posteingang oder in den Junk-e-Mail-Ordner verschiebt. Benutzer können die Sammlung von Listen sicherer Adressen für Ihr eigenes Postfach in Outlook oder Outlook im Internet (früher bekannt als Outlook Web App) konfigurieren. Administratoren können die Sammlung von Listen sicherer Adressen für das Postfach eines beliebigen Benutzers konfigurieren.

Wenn die Junk-e-Mail-Regel für das Postfach aktiviert ist, kann EoP Nachrichten in den Junk-e-Mail-Ordner basierend auf der Spam Filterungs Entscheidungs Aktion Nachrichten **in den Junk-e-Mail-Ordner** oder in die Liste blockierter Absender im Postfach migrieren und verhindern, dass Nachrichten an den Junk-e-Mail-Ordner übermittelt werden (basierend auf

 Wenn die Junk-e-Mail-Regel für das Postfach deaktiviert ist, kann EoP Nachrichten nicht in den Junk-e-Mail-Ordner basierend auf der Spam Filterungs **Entscheidungs Aktion "Nachricht in Junk-e-Mail-Ordner"** oder "Sammlung von Listen sicherer Adressen" im Postfach

Administratoren können Exchange Online PowerShell verwenden, um den Status der Junk-e-Mail-Regel für Postfächer zu deaktivieren, zu aktivieren und anzuzeigen. Administratoren können auch Exchange Online PowerShell zum Konfigurieren von Einträgen in der Sammlung von Listen sicherer Adressen für Postfächer verwenden (die Liste sicherer Absender, die Liste sicherer Empfänger und die Liste Absender blockieren).

> [!NOTE]
> Nachrichten von Absendern, die Benutzer ihren eigenen Listen sicherer Absender hinzugefügt haben, überspringen die Verbindungsfilterung als Teil von EoP (der SCL-Wert ist-1). Wenn Sie verhindern möchten, dass Benutzer Ihrer Liste sicherer Absender in Outlook Einträge hinzufügen, verwenden Sie Gruppenrichtlinien wie im Abschnitt [Informationen zu Junk-e-Mail-Einstellungen in Outlook](#about-junk-email-settings-in-outlook) weiter unten in diesem Thema beschrieben. Die Richtlinienfilterung, Inhaltsfilterung und ATP-Prüfungen (Advanced Threat Protection) werden weiterhin auf die Nachrichten angewendet.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie können nur Exchange Online PowerShell verwenden, um diese Verfahren auszuführen. Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Sie müssen Berechtigungen zugewiesen haben, bevor Sie diese Verfahren ausführen können. Insbesondere benötigen Sie die Rolle **"e-Mail-Empfänger** " (die standardmäßig der Rollengruppe " **Organisationsverwaltung**", " **Empfängerverwaltung**" und " **benutzerdefinierte e-Mail-Empfänger** " zugewiesen ist) oder die Rolle " **Benutzeroptionen** " (die standardmäßig der Rollengruppe " **Organisationsverwaltung** " und " **Helpdesk** " zugewiesen ist). Informationen zum Hinzufügen von Benutzern zu Rollengruppen in Exchange Online finden Sie unter [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups). Beachten Sie, dass ein Benutzer mit Standardberechtigungen dieselben Verfahren in seinem eigenen Postfach ausführen kann, solange Sie [Zugriff auf Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)haben.

- In Umgebungen mit eigenständigem EOP, in denen EOP lokale Exchange-Postfächer schützt, müssen Sie im lokalen Exchange Nachrichtenflussregeln zur Übersetzung der EOP-Spamfilterbewertung konfigurieren (auch als Transportregeln bezeichnet), damit die Junk-E-Mail-Regel die Nachricht in den Junk-E-Mail-Ordner verschieben kann. Ausführliche Informationen finden Sie unter [Konfigurieren eigenständiger EOP zur Zustellung von Spam in den Junk-E-Mail-Ordner in Hybridumgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- Sichere Absender für freigegebene Postfächer werden nicht mit Azure AD und EOP durch Entwurf synchronisiert.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Verwenden Exchange Online PowerShell zum Aktivieren oder Deaktivieren der Junk-e-Mail-Regel in einem Postfach

> [!NOTE]
> Sie können nur das **Set-MailboxJunkEmailConfiguration** -Cmdlet zum Deaktivieren der Junk-E-Mail-Regel in einem Postfach verwenden, das in Outlook (im Exchange-Cachemodus) oder Outlook im Web geöffnet wurde. Wenn das Postfach nicht geöffnet wurde, wird die folgende Fehlermeldung angezeigt: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` Wenn Sie diesen Fehler für Massenvorgänge unterdrücken möchten, können Sie `-ErrorAction SlientlyContinue` den Befehl " **MailboxJunkEmailConfiguration** " hinzufügen.

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
> 
> - Wenn der Benutzer sein Postfach nie geöffnet hat, wird möglicherweise eine Fehlermeldung angezeigt, wenn Sie den vorherigen Befehl ausführen. Um diesen Fehler für Massenvorgänge zu unterdrücken, fügen Sie `-ErrorAction SlientlyContinue` den Befehl " **MailboxJunkEmailConfiguration** " hinzu.
> 
> - Selbst wenn Sie die Junk-e-Mail-Regel deaktivieren, kann der Outlook-Junk-e-Mail-Filter (je nach Konfiguration) auch bestimmen, ob es sich bei einer Nachricht um Spam handelt, und Nachrichten in den Posteingang oder den Junk-e-Mail-Ordner basierend auf dem eigenen Spam Urteil und der Sammlung "Listen sicherer Adressen" im Postfach verschieben können. Weitere Informationen finden Sie im Abschnitt [Grundlegendes zu Junk-E-Mail-Einstellungen in Outlook](#about-junk-email-settings-in-outlook) in diesem Thema.

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Befolgen Sie einen der folgenden Schritte, um zu überprüfen, ob die Junk-E-Mail-Regel für ein Postfach erfolgreich aktiviert bzw. deaktiviert wurde:

- Ersetzen _\<MailboxIdentity\>_ Sie durch den Namen, den Alias oder die e-Mail-Adresse des Postfachs, und führen Sie den folgenden Befehl zum Überprüfen des **Enabled** -Eigenschaftswerts aus:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Verwenden Exchange Online PowerShell zum Konfigurieren der Sammlung von Listen sicherer Adressen für ein Postfach

Die Sammlung von Listen sicherer Adressen für ein Postfach umfasst die Liste sicherer Absender, die Liste sicherer Empfänger und die Liste blockierter Absender. Standardmäßig können Benutzer die Sammlung von Listen sicherer Adressen in Ihrem eigenen Postfach in Outlook oder Outlook im Internet konfigurieren. Administratoren können die entsprechenden Parameter im **Set-MailboxJunkEmailConfiguration** -Cmdlet zum Konfigurieren der Sammlung von Listen sicherer Adressen für ein Benutzerpostfach verwenden. Diese Parameter werden in der folgenden Tabelle beschrieben.

|||
|---|---|
|**Parameter für die Gruppe "MailboxJunkEmailConfiguration"**|**Einstellung für Outlook im Internet**|
|_BlockedSendersAndDomains_|**E-Mails von diesen Absendern und Domänen in Junk-E-Mail-Ordner verschieben.**|
|_ContactsTrusted_|**Meine Kontakte sind vertrauenswürdige Absender**|
|_TrustedListsOnly_|**Nur vertrauenswürdige e-Mails von Adressen in der Liste "sichere Absender und Domänen" und sichere Mailinglisten**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**Keine e-Mails von diesen Absendern in meinen Junk-e-Mail-Ordner bewegen**|
|

<sup>\*</sup>**Hinweise**:

- In Exchange Online werden **Domäneneinträge** in der Liste sicherer Absender oder _TrustedSendersAndDomains_ nicht erkannt, daher werden nur e-Mail-Adressen verwendet. In eigenständigen EoP mit Verzeichnissynchronisierung werden Domäneneinträge nicht standardmäßig synchronisiert, Sie können jedoch die Synchronisierung für Domänen aktivieren. Weitere Informationen finden Sie unter [KB3019657](https://support.microsoft.com/help/3019657).

- Sie können die Liste sicherer Empfänger nicht direkt mithilfe des Cmdlets " **MailboxJunkEmailConfiguration** " ändern (der Parameter " _TrustedRecipientsAndDomains_ " funktioniert nicht). Sie ändern die Liste sicherer Absender, und diese Änderungen werden mit der Liste sicherer Empfänger synchronisiert.

Verwenden Sie zum Konfigurieren der Sammlung von Listen sicherer Adressen in einem Postfach die folgende Syntax:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Verwenden Sie die folgende Syntax, um mehrere Werte einzugeben und vorhandene Einträge für die Parameter _BlockedSendersAndDomains_ und _TrustedSendersAndDomains_ zu überschreiben: `"<Value1>","<Value2>"...` . Verwenden Sie die folgende Syntax, um einen oder mehrere Werte hinzuzufügen oder zu entfernen, ohne andere vorhandene Einträge zu beeinflussen:`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

In diesem Beispiel werden die folgenden Einstellungen für die Sammlung von Listen sicherer Adressen für das Postfach von Ori Epstein konfiguriert:

- Fügen Sie den Wert Shopping@fabrikam.com der Liste blockierter Absender hinzu.

- Entfernen Sie den Wert Chris@fourthcoffee.com aus der Liste sicherer Absender und der Liste sicherer Empfänger.

- Die Kontakte in dem Ordner „Kontakte" werden als vertrauenswürdige Absender konfiguriert.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

In diesem Beispiel wird die Domäne „contoso.com" aus der Liste blockierter Absender in allen Benutzerpostfächern in der Organisation entfernt.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
> 
> - Wenn der Benutzer sein Postfach nie geöffnet hat, wird möglicherweise eine Fehlermeldung angezeigt, wenn Sie die vorherigen Befehle ausführen. Um diesen Fehler für Massenvorgänge zu unterdrücken, fügen Sie `-ErrorAction SlientlyContinue` den Befehl " **MailboxJunkEmailConfiguration** " hinzu.
> 
> - Selbst wenn die Junk-e-Mail-Regel für das Postfach deaktiviert ist, können Sie die Sammlung von Listen sicherer Adressen weiterhin konfigurieren, und der Outlook-Junk-e-Mail-Filter kann Nachrichten in den Posteingang oder den Junk-e-Mail-Ordner verschieben. Weitere Informationen finden Sie im Abschnitt [Grundlegendes zu Junk-E-Mail-Einstellungen in Outlook](#about-junk-email-settings-in-outlook) in diesem Thema.
> 
> - Der Outlook-Junk-e-Mail-Filter verfügt über zusätzliche Einstellungen für die Sammlung von Listen sicherer Adressen (beispielsweise **automatisch Personen I-e-Mails zur Liste sicherer Absender hinzufügen**). Weitere Informationen finden Sie unter [Verwenden von Junk-e-Mail-Filter, um zu steuern, welche Nachrichten angezeigt](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)werden.

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Verwenden Sie eine der folgenden Vorgehensweisen, um sicherzustellen, dass die Sammlung von Listen sicherer Adressen für ein Postfach erfolgreich konfiguriert wurde:

- Ersetzen _\<MailboxIdentity\>_ Sie durch den Namen, den Alias oder die e-Mail-Adresse des Postfachs, und führen Sie den folgenden Befehl aus, um die Eigenschaftswerte zu überprüfen:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Wenn die Liste der Werte zu lang ist, verwenden Sie die folgende Syntax:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Grundlegendes zu Junk-E-Mail-Einstellungen in Outlook

Verwenden Sie Gruppenrichtlinien zum Aktivieren, Deaktivieren und Konfigurieren der clientseitigen Junk-E-Mail-Filtereinstellungen, die in Outlook verfügbar sind. Weitere Informationen finden Sie unter [Administrative Vorlagendateien (ADMX/ADML) und Office-Anpassungs Tool für Microsoft 365-Apps für Unternehmen, Office 2019 und Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) und [Bereitstellen von Junk-e-Mail-Einstellungen wie der Liste sicherer Absender mithilfe von Gruppenrichtlinien](https://support.microsoft.com/help/2252421).

Wenn der Outlook-Junk-e-Mail-Filter auf den Standardwert **No Automatic Filtering** in **Home** \> **Junk** \> **Junk e-Mail-Optionen** \> **Optionen**festgelegt ist, versucht Outlook nicht, Massagen als Spam zu klassifizieren, verwendet jedoch weiterhin die Sammlung von Listen sicherer Adressen (Liste sicherer Absender, Liste sicherer Empfänger und blockierte Absender), um Nachrichten nach der Zustellung in den Junk-e-Mail- Weitere Informationen zu diesen Einstellungen finden Sie unter [Übersicht über den Junk-e-Mail-Filter](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

Wenn der Outlook-Junk-E-Mail-Filter auf **Niedrig** oder **Hoch** gesetzt ist, verwendet der Outlook-Junk-E-Mail-Filter eine eigene SmartScreen-Filtertechnologie zum Identifizieren und Verschieben von Spam in den Junk-E-Mail-Ordner. Diese Spam Klassifizierung unterscheidet sich von der SCL-Bewertung (Spam Confidence Level), die von EoP bestimmt wird. In der Tat ignoriert Outlook die SCL-Bewertung von EoP (es sei denn, EoP markiert die Nachricht zum Überspringen der Spamfilterung) und verwendet eigene Kriterien, um zu ermitteln, ob es sich bei der Nachricht um Spam handelt. Natürlich ist es möglich, dass das Spam Urteil von EoP und Outlook identisch sein könnte. Weitere Informationen zu diesen Einstellungen finden Sie unter [Ändern der Schutzebene im Junk-e-Mail-Filter](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b).

> [!NOTE]
> Im November 2016 hörte Microsoft auf, Spamdefinitionsupdates für die SmartScreen-Filter in Exchange und Outlook zu erstellen. Die vorhandenen SmartScreen-Spamdefinitionen wurden beibehalten, aber ihre Effektivität wird sich im Laufe der Zeit wahrscheinlich vermindern. Weitere Informationen finden Sie unter [Support für SmartScreen in Outlook und Exchange eingestellt](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Der Outlook-Junk-e-Mail-Filter kann also die Sammlung von Listen sicherer Adressen des Postfachs und seine eigene Spam Klassifizierung verwenden, um Nachrichten in den Junk-e-Mail-Ordner zu migrieren, auch wenn die Junk-e-Mail-Regel im Postfach deaktiviert ist.

Die Sammlung von Listen sicherer Adressen wird sowohl in Outlook als auch in Outlook im Web unterstützt. Die Sammlung von Listen sicherer Adressen wird im Exchange Online Postfach gespeichert, sodass Änderungen an der Sammlung von Listen sicherer Adressen in Outlook im Internet und umgekehrt angezeigt werden.

## <a name="limits-for-junk-email-settings"></a>Einschränkungen für Junk-e-Mail-Einstellungen

Die Sammlung von Listen sicherer Adressen (die Liste sicherer Absender, Liste sicherer Empfänger und blockierte Absender), die im Postfach des Benutzers gespeichert ist, wird ebenfalls mit EoP synchronisiert. Bei der Verzeichnissynchronisierung wird die Sammlung von Listen sicherer Adressen mit Azure AD synchronisiert.

- Die Sammlung von Listen sicherer Adressen im Postfach des Benutzers hat einen Grenzwert von 510 KB, einschließlich aller Listen sowie zusätzlicher Einstellungen für Junk-e-Mail-Filter. Wenn ein Benutzer diesen Grenzwert überschreitet, erhält er einen Outlook-Fehler, der wie folgt aussieht:

  > Die Junk-e-Mail-Listen von Servern konnten nicht/nicht hinzugefügt werden. Sie haben die auf dem Server zulässige Größe überstiegen. Der Junk-e-Mail-Filter auf dem Server wird deaktiviert, bis Ihre Junk-e-Mail-Listen auf die vom Server zugelassene Größe reduziert wurden.

  Weitere Informationen zu diesem Grenzwert und zum Ändern des Werts finden Sie unter [KB2669081](https://support.microsoft.com/help/2669081).

- Die synchronisierte Sammlung von Listen sicherer Adressen in EoP weist die folgenden Synchronisierungs Grenzwerte auf:

  - 1024 Gesamteinträge in der Liste "sichere Absender", "sichere Empfänger" und "externe Kontakte", wenn " **Vertrauenswürdige e-Mails von" meine Kontakte** "aktiviert ist.
  - 500 Gesamteinträge in der Liste Blockierte Absender und Blockierte Domänen.

  Wenn der Grenzwert für die 1024-Eingabe erreicht wird, treten folgende Vorgänge auf:

  - In der Liste werden keine Einträge in PowerShell und Outlook im Internet akzeptiert, aber es wird kein Fehler angezeigt.

    Outlook-Benutzer können weiterhin mehr als 1024 Einträge hinzufügen, bis Sie den Outlook-Grenzwert von 510 KB erreichen. Outlook kann diese zusätzlichen Einträge verwenden, solange ein EoP-Filter die Nachricht nicht blockiert, bevor die Zustellung an das Postfach erfolgt (Nachrichtenfluss Regeln, Antispoofing usw.).

- Bei der Verzeichnissynchronisierung werden die Einträge in der folgenden Reihenfolge mit Azure AD synchronisiert:

  1. E-Mail-Kontakte, wenn **Vertrauenswürdige e-Mails aus meinen Kontakten** aktiviert sind.
  2. Die Liste sicherer Absender und die Liste sicherer Empfänger werden kombiniert, dedupliziert und alphabetisch sortiert, wenn für die ersten 1024-Einträge eine Änderung vorgenommen wird.

  Die ersten 1024-Einträge werden verwendet, und relevante Informationen werden in den Nachrichtenkopfzeilen gestempelt.

  Einträge über 1024, die nicht mit Azure AD synchronisiert wurden, werden von Outlook (nicht von Outlook im Internet) verarbeitet, und in den Nachrichtenkopfzeilen werden keine Informationen gestempelt.

Wie Sie sehen können, wird durch Aktivieren der Einstellung **e-Mail aus meinen Kontakten Vertrauen** die Anzahl der sicheren Absender und der sicheren Empfänger reduziert, die synchronisiert werden können. Wenn dies ein Problem ist, empfehlen wir die Verwendung von Gruppenrichtlinien, um diese Funktion zu deaktivieren:

- Dateiname: outlk16. OPAX
- Richtlinieneinstellung: **e-Mail von Kontakten Vertrauen**
