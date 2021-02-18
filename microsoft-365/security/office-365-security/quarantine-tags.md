---
title: Quarantänetags
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Administratoren können erfahren, wie Sie mithilfe von Quarantänetags steuern, was Benutzer mit ihren isolierten Nachrichten tun können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 207f22c9acaa183e195f5a2ee33be65cdf4991dd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289413"
---
# <a name="quarantine-tags"></a>Quarantänetags

> [!NOTE]
> Die in diesem Artikel beschriebenen Features befinden sich derzeit in der Vorschau, sind nicht für alle verfügbar und können geändert werden.

Mit Quarantänetags in Exchange Online Protection (EOP) können Administratoren steuern, was Benutzer mit ihren isolierten Nachrichten tun können, basierend darauf, wie die Nachricht in Quarantäne angekommen ist.

EOP hat traditionell bestimmte Interaktivitätsstufen für Nachrichten [in](find-and-release-quarantined-messages-as-a-user.md) Quarantäne und in [Spambenachrichtigungen](use-spam-notifications-to-release-and-report-quarantined-messages.md)für Endbenutzer zugelassen oder verhindert. Endbenutzer können z. B. Nachrichten, die von der Antispamfilterung isoliert wurden, als Spam oder Massensendung anzeigen und frei geben, aber sie können nachrichten, die in Quarantäne gestellt wurden, nicht als Phishing mit hoher Sicherheit anzeigen oder frei geben.

Für [unterstützte Schutzfunktionen](#step-2-assign-a-quarantine-tag-to-supported-features)geben Quarantänetags an, was Benutzer in Spambenachrichtigungen für Endbenutzer und in ihren isolierten Nachrichten in Quarantäne tun dürfen (Nachrichten, bei denen der Benutzer ein Empfänger ist). Standardquarantänetags werden automatisch zugewiesen, um die historischen Funktionen für Endbenutzer für isolierte Nachrichten zu erzwingen. Sie können auch benutzerdefinierte Quarantänetags erstellen und zuweisen, um Endbenutzern das Ausführen bestimmter Aktionen für isolierte Nachrichten zu ermöglichen oder zu verhindern.

Die einzelnen Berechtigungen werden in den folgenden voreingestellten Berechtigungsgruppen kombiniert:

- Kein Zugriff
- Eingeschränkter Zugriff
- Vollzugriff

Die verfügbaren einzelnen Berechtigungen und was in den vordefinierten Berechtigungsgruppen enthalten ist oder nicht, werden in der folgenden Tabelle beschrieben:

|Berechtigung|Kein Zugriff|Eingeschränkter Zugriff|Vollzugriff|
|---|:---:|:---:|:---:|
|**Absender zulassen** (_PermissionToAllowSender_)|||![Häkchen](../../media/checkmark.png)|
|**Absender blockieren** (_PermissionToBlockSender_)||![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|**Delete** (_PermissionToDelete_)||![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|**Vorschau** (_PermissionToPreview_)||![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|**Zulassen, dass Empfänger eine Nachricht aus der Quarantäne freisen** (_PermissionToRelease_)|||![Häkchen](../../media/checkmark.png)|
|**Empfänger dürfen anfordern, dass eine Nachricht aus der Quarantäne** freigegeben wird (_PermissionToRequestRelease_)||![Häkchen](../../media/checkmark.png)||
|

Wenn Sie die Standardberechtigungen in den voreingestellten Berechtigungsgruppen nicht verwenden möchten, können Sie benutzerdefinierte Berechtigungen verwenden, wenn Sie benutzerdefinierte Quarantänetags erstellen oder ändern. Weitere Informationen dazu, was jede Berechtigung macht, finden Sie im Abschnitt ["Quarantänetag-Berechtigungsdetails"](#quarantine-tag-permission-details) weiter unten in diesem Artikel.

Sie erstellen und weisen Quarantänetags im Security & Compliance Center oder in PowerShell zu (Exchange Online PowerShell für Microsoft 365-Organisationen mit Exchange Online-Postfächern; eigenständige EOP PowerShell in & ohne Exchange Online-Postfächer).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **"Quarantänetags" zu** wechseln, öffnen Sie <https://protection.office.com/quarantineTags> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Zum Anzeigen, Erstellen, Ändern oder Entfernen von Quarantänetags müssen  Sie  Mitglied der Rollen "Organisationsverwaltung" oder "Sicherheitsadministrator" im [Security & Compliance Center sein.](permissions-in-the-security-and-compliance-center.md)

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a>Schritt 1: Erstellen von Quarantänetags im Security & Compliance Center

1. Wechseln Sie im Security & Compliance  Center zu "Bedrohungsverwaltungsrichtlinie", und wählen Sie \>  dann **"Quarantänetags" aus.**

2. Wählen Sie **auf der Seite "Quarantänetags"** die Option **"Benutzerdefiniertes Tag hinzufügen" aus.**

3. Der **Assistent für neue Tags** wird geöffnet. Geben Sie auf der Seite **"Tagname"** einen kurzen, aber eindeutigen Namen in das Feld **"Tag-Name"** ein. Sie müssen das Tag in den nächsten Schritten nach Namen identifizieren und auswählen. Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Wählen Sie **auf der Seite "Zugriff** auf Empfängernachrichten" einen der folgenden Werte aus:
   - **Kein Zugriff**
   - **Eingeschränkter Zugriff**
   - **Vollzugriff**

   Die einzelnen Berechtigungen, die in diesen Berechtigungsgruppen enthalten sind, werden weiter oben in diesem Artikel beschrieben.

   Um benutzerdefinierte Berechtigungen anzugeben, wählen **Sie "Bestimmten Zugriff festlegen (Erweitert) aus,** und konfigurieren Sie die folgenden Einstellungen:

     - **Wählen Sie die Einstellung für die Freigabeaktion** aus: Wählen Sie einen der folgenden Werte aus:
       - **Keine Freigabeaktion:** Dies ist der Standardwert.
       - **Empfängern erlauben, eine Nachricht aus der Quarantäne frei zu lassen**
       - **Zulassen, dass Empfänger die Isolierung einer Nachricht anfordern**

     - **Wählen Sie zusätzliche Aktionen aus, die** Empfänger für isolierte Nachrichten ausführen können: Wählen Sie einige, alle oder keine der folgenden Werte aus:
       - **Löschen**
       - **Preview**
       - **Absender zulassen**
       - **Absender blockieren**

   Diese Berechtigungen und ihre Auswirkungen auf isolierte Nachrichten und Spambenachrichtigungen für Endbenutzer werden im Abschnitt mit den Berechtigungsdetails des Quarantänetags weiter unten in diesem Artikel beschrieben. [](#quarantine-tag-permission-details)

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Überprüfen Sie **auf der** angezeigten Zusammenfassungsseite Ihre Einstellungen. Sie können **in** jeder Einstellung auf "Bearbeiten" klicken, um sie zu ändern.

   Klicken Sie nach Abschluss des Abschlusses auf **"Absenden".**

6. Klicken **Sie auf der** angezeigten Bestätigungsseite auf "Fertig".

Jetzt können Sie das Quarantänetag einem Quarantänefeature zuweisen, wie im Abschnitt Schritt [2](#step-2-assign-a-quarantine-tag-to-supported-features) beschrieben.

### <a name="create-quarantine-tags-in-powershell"></a>Erstellen von Quarantänetags in PowerShell

Wenn Sie lieber PowerShell zum Erstellen von Quarantänetags verwenden möchten, stellen Sie eine Verbindung mit Exchange Online PowerShell oder Exchange Online Protection PowerShell auf, und verwenden Sie das **Cmdlet New-QuarantineTag.** Sie haben zwei unterschiedliche Methoden zur Auswahl:

- Verwenden Sie den _Parameter "EndUserQuarantinePermissionsValue"._
- Verwenden Sie den _Parameter "EndUserQuarantinePermissions"._

Diese Methoden werden in den folgenden Abschnitten beschrieben.

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>Verwenden des Parameters "EndUserQuarantinePermissionsValue"

Verwenden Sie die folgende Syntax, um ein Quarantänetag mit dem Parameter _"EndUserQuarantinePermissionsValue"_ zu erstellen:

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

Der _Parameter "EndUserQuarantinePermissionsValue"_ verwendet einen Dezimalwert, der aus einem binären Wert konvertiert wird. Der binäre Wert entspricht den verfügbaren Quarantäneberechtigungen für Endbenutzer in einer bestimmten Reihenfolge. Für jede Berechtigung ist der Wert "1" gleich "True", und der Wert "0" ist "False".

Die erforderliche Reihenfolge und die Werte für jede einzelne Berechtigung in vordefinierten Berechtigungsgruppen werden in der folgenden Tabelle beschrieben:

****

|Berechtigung|Kein Zugriff|Eingeschränkter Zugriff|Vollzugriff|
|---|:---:|:---:|:---:|
|PermissionToAllowSender|0|0|1 |
|PermissionToBlockSender|0|1 |1 |
|PermissionToDelete|0|1 |1 |
|PermissionToDownload<sup>\*</sup>|0|0|0|
|PermissionToPreview|0|1 |1 |
|PermissionToRelease<sup>\*\*</sup>|0|0|1 |
|PermissionToRequestRelease<sup>\*\*</sup>|0|1 |0|
|PermissionToViewHeader<sup>\*</sup>|0|0|0|
|Binärwert|00000000|01101010|11101100|
|Zu verwendende Dezimalwert|0|106|236|

<sup>\*</sup> Derzeit ist dieser Wert immer 0. Bei PermissionToViewHeader blendet der Wert 0 die Schaltfläche "Nachrichtenkopf anzeigen" nicht in den Details der isolierten Nachricht aus (die Schaltfläche ist immer verfügbar). 

<sup>\*\*</sup> Legen Sie nicht beide Werte auf 1. Legen Sie einen auf 1 und den anderen auf 0 oder beide auf 0.

In diesem Beispiel wird ein neuer Quarantänetagnamen namens "NoAccess" erstellt, der die Zugriffsberechtigungen "No" wie in der vorherigen Tabelle beschrieben zu weist.

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

Verwenden Sie für Eingeschränkte Zugriffsberechtigungen den Wert 106. Verwenden Sie für Vollzugriffsberechtigungen den Wert 236.

Verwenden Sie für benutzerdefinierte Berechtigungen die vorherige Tabelle, um den binären Wert zu erhalten, der den von Ihnen benötigten Berechtigungen entspricht. Konvertieren Sie den binären Wert in einen Dezimalwert, und verwenden Sie den Dezimalwert für den _Parameter "EndUserQuarantinePermissionsValue"._

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).

#### <a name="use-the-enduserquarantinepermissions-parameter"></a>Verwenden des Parameters "EndUserQuarantinePermissions"

Gehen Sie wie folgt vor, um mithilfe des Parameters _"EndUserQuarantinePermissionsValue"_ ein Quarantänetag zu erstellen:

A. Speichern Sie ein Quarantäneberechtigungsobjekt mithilfe des **Cmdlets "New-QuarantinePermissions"** in einer Variablen.

<p>

B. Verwenden Sie die Variable als _EndUserQuarantinePermissions-Wert_ im **Befehl "New-QuarantineTag".**

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a>Schritt A: Speichern eines Quarantäneberechtigungsobjekts in einer Variablen

Verwenden Sie die folgende Syntax:

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

Der Standardwert für alle nicht verwendeten Parameter ist , daher müssen Sie nur die Parameter verwenden, auf die Sie `$false` den Wert festlegen `$true` möchten.

Die folgenden Beispiele zeigen, wie Berechtigungsobjekte erstellt werden, die den vordefinierten Berechtigungsgruppen entsprechen:

- **Kein Zugriff:**

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- **Eingeschränkter Zugriff:**

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- **Vollzugriff:**

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

Um die festgelegten Werte zu sehen, führen Sie den Variablennamen als Befehl aus (führen Sie z. B. den Befehl `$NoAccess` aus).

Legen Sie für benutzerdefinierte Berechtigungen die Parameter _"PermissionToRelease"_ und _"PermissionToRequestRelease" nicht_ auf " `$true` fest. Legen Sie eins auf und lassen Sie die andere als `$true` , oder lassen Sie beide als `$false` `$false` .

Sie können auch eine vorhandene Berechtigungsobjektvariable ändern, nachdem Sie sie erstellt haben, aber bevor Sie sie mit dem **Cmdlet "Set-QuarantinePermissions"** verwenden.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["New-QuarantinePermissions"](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) und ["Set-QuarantinePermissions".](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions)

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a>Schritt B: Verwenden der Variablen im befehl New-QuarantineTag

Nachdem Sie das Berechtigungsobjekt in einer Variablen erstellt und gespeichert haben, verwenden Sie die Variable für den Parameterwert _"EndUserQuarantinePermission"_ im folgenden **New-QuarantineTag-Befehl:**

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

In diesem Beispiel wird mithilfe des Berechtigungsobjekts, das im vorherigen Schritt beschrieben und erstellt wurde, ein neues Quarantänetag namens "LimitedAccess" `$LimitedAccess` erstellt.

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a>Schritt 2: Zuweisen eines Quarantänetags zu unterstützten Features

In _unterstützten_ Schutzfunktionen, die Nachrichten oder Dateien isolieren (automatisch oder als konfigurierbare Aktion), können Sie den verfügbaren Quarantäneaktionen ein Quarantänetag zuweisen. Features zum Isolieren von Nachrichten und die Verfügbarkeit von Quarantänetags werden in der folgenden Tabelle beschrieben:

****

|Feature|Werden Quarantänetags unterstützt?|Verwendete Standardquarantänetags|
|---|:---:|---|
|[Antispamrichtlinien:](configure-your-spam-filter-policies.md) <ul><li>**Spam** (_SpamAction_)</li><li>**Spam mit hoher Confidence** (_HighConfidenceSpamAction_)</li><li>**Phishing-E-Mail** (_PhishSpamAction_)</li><li>**High Confidence phishing email** (_HighConfidencePhishAction_)</li><li>**Massen-E-Mail** (_BulkSpamAction_)</li></ul>|Ja|<ul><li>DefaultSpamTag (Vollzugriff)</li><li>DefaultHighConfSpamTag (Vollzugriff)</li><li>DefaultPhishTag (Vollzugriff)</li><li>DefaultHighConfPhishTag (Kein Zugriff)</li><li>DefaultBulkTag (Vollzugriff)</li></ul>
|Antiphishingrichtlinien: <ul><li>[Spoofing Intelligence Protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</li><li>[Identitätswechselschutz:](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)<sup>\*</sup> <ul><li>**Wenn E-Mails von einem imitierten Benutzer** gesendet werden (_TargetedUserProtectionAction_)</li><li>**Wenn E-Mails von einer imitierten Domäne** gesendet werden (_TargetedDomainProtectionAction_)</li><li>**Postfachintelligenz** \> **Wenn E-Mails von einem imitierten** Benutzer gesendet werden (_MailboxIntelligenceProtectionAction_)</li></ul></li></ul></ul>|Nein|n/v|
|[An malware policies:](configure-anti-malware-policies.md)All detected messages are always quarantined.|Nein|n/v|
|[Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md)|Nein|n/v|
|[Nachrichtenflussregeln](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch als Transportregeln bekannt) mit der Aktion: **Nachricht in** die gehostete Quarantäne isolieren (_Quarantäne_).|Nein|n/v|
|

<sup>\*</sup> Einstellungen zum Schutz vor Identitätswechsel sind nur in Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügbar.

Wenn Sie mit den Endbenutzerberechtigungen zufrieden sind, die von den standardmäßigen Quarantänetags bereitgestellt werden, müssen Sie nichts weiter tun. Wenn Sie die Endbenutzerfunktionen (verfügbare Schaltflächen) in Spambenachrichtigungen für Endbenutzer oder In-Quarantäne-Nachrichtendetails anpassen möchten, können Sie ein benutzerdefiniertes Quarantänetag zuweisen.

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a>Zuweisen von Quarantänetags in Antispamrichtlinien im Security & Compliance Center

Vollständige Anweisungen zum Erstellen und Ändern von Antispamrichtlinien finden Sie unter ["Konfigurieren von Antispamrichtlinien in EOP".](configure-your-spam-filter-policies.md)

1. Wechseln Sie im Security & Compliance  Center zu "Bedrohungsverwaltungsrichtlinie", und wählen Sie \>  \> dann **"Antispam" aus.** Oder öffnen Sie <https://protection.office.com/antispam> .

2. Suchen und Auswählen einer vorhandenen Antispamrichtlinie, die bearbeitet werden soll, oder erstellen Sie eine neue Antispamrichtlinie.

3. Erweitern Sie im Flyout "Richtliniendetails" den Abschnitt **"Spam- und Massenaktionen".**

4. Wenn Sie "Nachricht isolieren" für die Aktion einer  verfügbaren Spamfilterungs-Entscheidung ausgewählt haben, können Sie im Tagfeld "Quarantänerichtlinie anwenden" das Quarantänetag für diese Entscheidung auswählen. 

   **Hinweis:** Wenn Sie eine neue Richtlinie erstellen, gibt ein leerer Quarantänetagwert für eine Spamfilterung an, dass das Standardquarantänetag für diese Entscheidung verwendet wird. Wenn Sie die Richtlinie später bearbeiten, werden die leeren Werte durch die tatsächlichen Standardmäßigen Quarantänetagnamen ersetzt, wie in der vorherigen Tabelle beschrieben.

   ![Quarantänetagauswahl in einer Antispamrichtlinie](../../media/quarantine-tags-in-anti-spam-policies.png)

5. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a>Zuweisen von Quarantänetags in Antispamrichtlinien in PowerShell

Wenn Sie powerShell lieber zum Zuweisen von Quarantänetags in Antispamrichtlinien verwenden möchten, stellen Sie eine Verbindung mit Exchange Online PowerShell oder Exchange Online Protection PowerShell auf, und verwenden Sie die folgende Syntax:

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**Hinweise**:

- Der Standardwert für den Parameter _"HighConfidencePhishAction"_ ist "Quarantine", sodass Sie die Quarantäneaktion für Phishingerkennungen mit hoher Confidence in neuen Antispamrichtlinien nicht festlegen müssen. Bei allen anderen Spamfilterungsverdingungen in neuen oder vorhandenen Antispamrichtlinien ist das Quarantänetag nur wirksam, wenn der Aktionswert "Quarantine" lautet. Führen Sie den folgenden Befehl aus, um die Aktionswerte in vorhandenen Antispamrichtlinien zu sehen:

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  Informationen zu den Standardaktionswerten und den empfohlenen Aktionswerten für Standard und Strict finden Sie unter [EOP Antispamrichtlinieneinstellungen.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

- Eine Spamfilterungsverkündung ohne einen entsprechenden Quarantänetagparameter bedeutet, dass das [Standardquarantänetag](#step-2-assign-a-quarantine-tag-to-supported-features) für diese Nachricht verwendet wird.

  Sie müssen ein Standardquarantänetag nur durch ein benutzerdefiniertes Quarantänetag ersetzen, wenn Sie die Standardfunktionen für Endbenutzer für isolierte Nachrichten ändern möchten.

- Eine neue Antispamrichtlinie in PowerShell erfordert eine Spamfilterrichtlinie (Einstellungen) mithilfe des **Cmdlets "New-HostedContentFilterPolicy"** und eine neue Spamfilterregel (Empfängerfilter) mithilfe des **Cmdlets "New-HostedContentFilterRule".** Anweisungen finden Sie unter [Verwenden von PowerShell zum Erstellen von Antispamrichtlinien.](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)

In diesem Beispiel wird eine neue Spamfilterrichtlinie namens "Research Department" mit den folgenden Einstellungen erstellt:

- Die Aktion für alle Spamfilterungen ist auf "Quarantäne" festgelegt.
- Das benutzerdefinierte Quarantänetag namens  NoAccess, das Keine Zugriffsberechtigungen zu weist, ersetzt standardmäßige Quarantänetags, die standardmäßig noch keine Zugriffsberechtigungen zuweisen. 

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).

In diesem Beispiel wird die vorhandene Spamfilterrichtlinie "Human Resources" geändert. Die Aktion für die Spamquarantäne wird auf "Quarantäne" festgelegt, und das benutzerdefinierte Quarantänetag namens "NoAccess" wird zugewiesen.

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a>Konfigurieren der globalen Quarantänebenachrichtigungseinstellungen im Security & Compliance Center

Mit den globalen Einstellungen für Quarantänetags können Sie die Spambenachrichtigungen für Endbenutzer anpassen, die an Empfänger von Nachrichten gesendet werden, die unter Quarantäne gestellt wurden. Weitere Informationen zu diesen Benachrichtigungen finden Sie unter [Spambenachrichtigungen für Endbenutzer.](use-spam-notifications-to-release-and-report-quarantined-messages.md)

1. Wechseln Sie im Security & Compliance  Center zu "Bedrohungsverwaltungsrichtlinie", und wählen Sie \>  dann **"Quarantänetags" aus.**

2. Wählen Sie **auf der Seite "Quarantänetags"** die **globalen Einstellungen aus.**

3. Konfigurieren Sie **im flyout für** Quarantänebenachrichtigungseinstellungen, das geöffnet wird, einige oder alle der folgenden Einstellungen:

   - **Firmenlogo verwenden:** Wählen Sie diese Option aus, um das standardmäßige Microsoft-Logo zu ersetzen, das oben in Spambenachrichtigungen für Endbenutzer verwendet wird. Bevor Sie dies tun, müssen Sie die Anweisungen unter Anpassen des [Microsoft 365-Designs](../../admin/setup/customize-your-organization-theme.md) für Ihre Organisation befolgen, um Ihr benutzerdefiniertes Logo hochzuladen.

     Der folgende Screenshot zeigt ein benutzerdefiniertes Logo in einer Spambenachrichtigung für Endbenutzer:

     ![Ein benutzerdefiniertes Logo in einer Spambenachrichtigung für Endbenutzer](../../media/quarantine-tags-esn-customization-logo.png)

   - **Sprache auswählen:** Spambenachrichtigungen für Endbenutzer wurden bereits basierend auf den Spracheinstellungen des Empfängers lokalisiert. Sie können angepassten Text für den Anzeigenamen und den Haftungsausschluss in **verschiedenen** Sprachen **angeben.**

     Wählen Sie im ersten Sprachfeld mindestens eine Sprache aus, und klicken Sie dann auf **"Hinzufügen".** Sie können mehrere Sprachen auswählen, indem Sie **nach** jeder auf "Hinzufügen" klicken. In einem Abschnittssprachenfeld werden alle ausgewählten Sprachen angezeigt:

     ![Ausgewählte Sprachen im zweiten Sprachfeld in den globalen Quarantänebenachrichtigungseinstellungen von Quarantänetags](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - **Anzeigename:** Passen Sie den Anzeigenamen des Absenders an, der in Spambenachrichtigungen für Endbenutzer verwendet wird.

     Wählen Sie für jede hinzugefügte Sprache die Sprache im zweiten Sprachfeld aus (klicken Sie nicht auf das X), und geben Sie den textwert in das Feld **"Anzeigename"** ein.

     Der folgende Screenshot zeigt den angepassten Anzeigenamen in einer Spambenachrichtigung für Endbenutzer:

     ![Ein benutzerdefinierter Absenderanzeigename in einer Spambenachrichtigung für Endbenutzer](../../media/quarantine-tags-esn-customization-display-name.png)

   - Haftungsausschluss: Fügen Sie am Ende der Spambenachrichtigungen für Endbenutzer einen benutzerdefinierten Haftungsausschluss hinzu. Der lokalisierte Text, **ein Haftungsausschluss aus Ihrer Organisation:** ist immer zuerst enthalten, gefolgt von dem von Ihnen angegebenen Text.

     Wählen Sie für jede hinzugefügte Sprache die Sprache im zweiten Sprachfeld aus (klicken Sie nicht auf  das X), und geben Sie den textwert in das Feld "Haftungsausschluss" ein.

     Der folgende Screenshot zeigt den angepassten Haftungsausschluss in einer Spambenachrichtigung für Endbenutzer:

     ![Ein benutzerdefinierter Haftungsausschluss am Ende einer Spambenachrichtigung für Endbenutzer](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a>Anzeigen von Quarantänetags im Security & Compliance Center

1. Wechseln Sie im Security & Compliance  Center zu "Bedrohungsverwaltungsrichtlinie", und wählen Sie \>  dann **"Quarantänetags" aus.**

- Wenn Sie die Einstellungen von integrierten oder benutzerdefinierten Quarantänetags anzeigen möchten, wählen Sie das Quarantänetag aus der Liste aus (aktivieren Sie nicht das Kontrollkästchen).

- Um die globalen Einstellungen anzeigen zu können, wählen Sie **"Globale Einstellungen" aus.**

### <a name="view-quarantine-tags-in-powershell"></a>Anzeigen von Quarantänetags in PowerShell

Wenn Sie lieber PowerShell zum Anzeigen von Quarantänetags verwenden möchten, gehen Sie wie folgt vor:

- Führen Sie zum Anzeigen einer Zusammenfassungsliste aller integrierten oder benutzerdefinierten Tags den folgenden Befehl aus:

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- Ersetzen Sie zum Anzeigen der Einstellungen von integrierten oder benutzerdefinierten Quarantänetags den Namen des Quarantänetags, und führen Sie \<TagName\> den folgenden Befehl aus:

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- Führen Sie zum Anzeigen der globalen Einstellungen den folgenden Befehl aus:

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a>Entfernen von Quarantänetags im Security & Compliance Center

**Hinweise**:

- Sie können keine integrierten Quarantänetags entfernen.

- Vergewissern Sie sich vor dem Entfernen eines benutzerdefinierten Quarantänetags, dass es nicht verwendet wird. Führen Sie beispielsweise den folgenden Befehl in PowerShell aus:

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  Wenn das Quarantänetag verwendet wird, ersetzen Sie das [zugewiesene Quarantänetag,](#step-2-assign-a-quarantine-tag-to-supported-features) bevor Sie es entfernen.

1. Wechseln Sie im Security & Compliance  Center zu "Bedrohungsverwaltungsrichtlinie", und wählen Sie \>  dann **"Quarantänetags" aus.**

2. Wählen Sie **auf der Seite "Quarantänetags"** das benutzerdefinierte Quarantänetag aus, das Sie entfernen möchten, und klicken Sie auf **"Tag löschen".**

3. Klicken **Sie im angezeigten** Bestätigungsdialogfeld auf "Tag entfernen".

### <a name="remove-quarantine-tags-in-powershell"></a>Entfernen von Quarantänetags in PowerShell

Wenn Sie powerShell verwenden möchten, um ein benutzerdefiniertes Quarantänetag zu entfernen, ersetzen Sie es durch den Namen des Quarantänetags, und führen Sie \<TagName\> den folgenden Befehl aus:

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).

## <a name="quarantine-tag-permission-details"></a>Berechtigungsdetails für Quarantänetags

In den folgenden Abschnitten werden die Auswirkungen vordefinierter Berechtigungsgruppen und einzelner Berechtigungen in den Details von Nachrichten in Quarantäne und in Spambenachrichtigungen für Endbenutzer beschrieben.

### <a name="preset-permissions-groups"></a>Voreingestellte Berechtigungsgruppen

Die einzelnen Berechtigungen, die in vordefinierten Berechtigungsgruppen enthalten sind, sind in der Tabelle am Anfang dieses Artikels aufgeführt.

#### <a name="no-access"></a>Kein Zugriff

Wenn das Quarantänetag die Berechtigung **"Kein Zugriff"** (keine Berechtigungen) zu weist, erhalten Benutzer dennoch einige grundlegende Funktionen:

- **Nachrichtendetails in Quarantäne:** Die Schaltfläche **"Nachrichtenkopf** anzeigen" ist immer verfügbar.

  ![Verfügbare Schaltflächen in den Details der isolierten Nachricht, wenn das Quarantänetag dem Benutzer keine Zugriffsberechtigungen erteilt](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- **Spambenachrichtigungen für Endbenutzer:** **Die** Schaltfläche "Überprüfen", die den Benutzer zu der Nachricht in Quarantäne bringt, ist immer verfügbar.

  ![Verfügbare Schaltflächen in der Spambenachrichtigung für Endbenutzer, wenn das Quarantänetag dem Benutzer keine Zugriffsberechtigungen erteilt](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a>Eingeschränkter Zugriff

Wenn das Quarantänetag die Berechtigungen für eingeschränkten **Zugriff** zu weist, erhalten Benutzer die folgenden Funktionen:

- **Details zu isolierten Nachrichten:** Die folgenden Schaltflächen sind verfügbar:
  - **Anforderungsfreigabe**
  - **Nachrichtenkopfzeile anzeigen**
  - **Vorschaunachricht**
  - **Absender blockieren**
  - **Aus Quarantäne entfernen**

  ![Verfügbare Schaltflächen in den Details der isolierten Nachricht, wenn das Quarantänetag dem Benutzer eingeschränkte Zugriffsberechtigungen erteilt](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- **Spambenachrichtigungen für Endbenutzer:** Die folgenden Schaltflächen sind verfügbar:
  - **Absender blockieren**
  - **Überprüfung**

  ![Verfügbare Schaltflächen in der Spambenachrichtigung für Endbenutzer, wenn das Quarantänetag dem Benutzer eingeschränkte Zugriffsberechtigungen erteilt](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a>Vollzugriff

Wenn das Quarantänetag die Berechtigung **"Vollzugriff"** (alle verfügbaren Berechtigungen) zu weist, erhalten Benutzer die folgenden Funktionen:

- **Details zu isolierten Nachrichten:** Die folgenden Schaltflächen sind verfügbar:
  - **Veröffentlichungsnachricht**
  - **Nachrichtenkopfzeile anzeigen**
  - **Vorschaunachricht**
  - **Absender blockieren**
  - **Absender zulassen**
  - **Aus Quarantäne entfernen**

  ![Verfügbare Schaltflächen in den Details der isolierten Nachricht, wenn das Quarantänetag dem Benutzer Vollzugriff gewährt](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- **Spambenachrichtigungen für Endbenutzer:** Die folgenden Schaltflächen sind verfügbar:
  - **Absender blockieren**
  - **Freigabe**
  - **Überprüfung**

  ![Verfügbare Schaltflächen in der Spambenachrichtigung für Endbenutzer, wenn das Quarantänetag dem Benutzer Vollzugriff gewährt](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a>Einzelne Berechtigungen

> [!NOTE]
> Denken Sie daran, dass Benutzer immer die im Abschnitt "Kein [Zugriff" beschriebenen Schaltflächen](#no-access) erhalten. Diese Schaltflächen sind nicht in den einzelnen Berechtigungsbeschreibungen enthalten.

#### <a name="allow-sender-permission"></a>Absenderberechtigung zulassen

Die Berechtigung "Absender **zulassen"** (_PermissionToAllowSender_) steuert den Zugriff auf die Schaltfläche, mit der Benutzer den absender in Quarantäne verschobenen Nachrichten bequem zur Liste sicherer Absender hinzufügen können.

- **Nachrichtendetails in Quarantäne:**
  - **Berechtigung "Absender zulassen"** aktiviert: Die Schaltfläche **"Absender zulassen"** ist verfügbar.
  - **Absenderberechtigung** zulassen deaktiviert: Die Schaltfläche **"Absender zulassen"** ist nicht verfügbar.

- **Spambenachrichtigungen für Endbenutzer:** Keine Auswirkung.

Weitere Informationen zur Liste sicherer Absender [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) finden Sie unter "Blockieren vertrauenswürdiger Absender verhindern" und "Verwenden von [Exchange Online PowerShell](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)zum Konfigurieren der Sammlung von Listen sicherer Absender für ein Postfach".

#### <a name="block-sender-permission"></a>Berechtigung "Absender blockieren"

Die **Berechtigung "Absender blockieren"** (_PermissionToBlockSender_) steuert den Zugriff auf die Schaltfläche, mit der Benutzer den absender in Quarantäne verschobenen Nachrichten bequem zur Liste blockierter Absender hinzufügen können.

- **Nachrichtendetails in Quarantäne:**
  - **Berechtigung "Absender blockieren"** aktiviert: Die Schaltfläche **"Absender blockieren"** ist verfügbar.
  - **Berechtigung "Absender blockieren"** deaktiviert: Die Schaltfläche **"Absender blockieren"** ist nicht verfügbar.

- **Spambenachrichtigungen für Endbenutzer:**
  - **Berechtigung "Absender blockieren"** deaktiviert: Die Schaltfläche **"Absender blockieren"** ist nicht verfügbar.
  - **Berechtigung "Absender blockieren"** aktiviert: Die Schaltfläche **"Absender blockieren"** ist verfügbar.

Weitere Informationen zur Liste blockierter [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) Absender finden Sie unter "Blockieren von Nachrichten von einer Person" und "Verwenden von [Exchange Online PowerShell](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)zum Konfigurieren der Sammlung von Listen sicherer Absender für ein Postfach".

#### <a name="delete-permission"></a>Löschen

Die **Berechtigung "Löschen"** (_PermissionToDelete_) steuert die Fähigkeit von Benutzern, ihre Nachrichten (Nachrichten, bei denen der Benutzer ein Empfänger ist) aus der Quarantäne zu löschen.

- **Nachrichtendetails in Quarantäne:**
  - **Berechtigung** "Löschen" aktiviert: Die Schaltfläche **"Aus Quarantäne entfernen"** ist verfügbar.
  - **Berechtigung** löschen deaktiviert: Die Schaltfläche **"Aus Quarantäne entfernen"** ist nicht verfügbar.

- **Spambenachrichtigungen für Endbenutzer:** Keine Auswirkung.

#### <a name="preview-permission"></a>Vorschauberechtigung

Die **Vorschauberechtigung** (_PermissionToPreview_) steuert die Möglichkeit, dass Benutzer eine Vorschau ihrer Nachrichten in Quarantäne anzeigen können.

- **Nachrichtendetails in Quarantäne:**
  - **Vorschauberechtigung** aktiviert: Die Schaltfläche **"Vorschaunachricht"** ist verfügbar.
  - **Vorschauberechtigung** deaktiviert: Die Schaltfläche **"Vorschaunachricht"** ist nicht verfügbar.

- **Spambenachrichtigungen für Endbenutzer:** Keine Auswirkung.

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>Empfängern erlauben, eine Nachricht aus der Quarantäneberechtigung frei zu lassen

Die **Berechtigung "Empfängern die** Freigabe einer Nachricht aus der Quarantäne gestatten" (_PermissionToRelease_) steuert die Fähigkeit von Benutzern, ihre isolierten Nachrichten direkt und ohne Genehmigung eines Administrator freizusenken.

- **Nachrichtendetails in Quarantäne:**
  - Berechtigung aktiviert: Die Schaltfläche **"Nachricht veröffentlichen"** ist verfügbar.
  - Berechtigung deaktiviert: Die Schaltfläche **"Nachricht veröffentlichen"** ist nicht verfügbar.

- **Spambenachrichtigungen für Endbenutzer:**
  - Berechtigung aktiviert: Die **Schaltfläche "Release"** ist verfügbar.
  - Berechtigung deaktiviert: Die **Schaltfläche "Release"** ist nicht verfügbar.

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>Zulassen, dass Empfänger die Isolierberechtigung für eine Nachricht anfordern

Die Berechtigung "Empfängern das Zulassen, dass eine Nachricht aus der Quarantäne freigegeben wird" (_PermissionToRequestRelease_) steuert, ob Benutzer die Freigabe ihrer isolierten Nachrichten anfordern können.   Die Nachricht wird erst freigegeben, nachdem ein Administrator die Anforderung genehmigt hat.

- **Nachrichtendetails in Quarantäne:**
  - Berechtigung aktiviert: Die **Schaltfläche "Freigabe anfordern"** ist verfügbar.
  - Berechtigung deaktiviert: Die **Schaltfläche "Freigabe** anfordern" ist nicht verfügbar.

- **Spambenachrichtigungen für Endbenutzer:** Die **Schaltfläche "Freigabe"** ist nicht verfügbar.
