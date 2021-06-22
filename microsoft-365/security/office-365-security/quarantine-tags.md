---
title: Quarantänerichtlinien
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
description: Administratoren können erfahren, wie Sie Quarantänerichtlinien verwenden, um zu steuern, was Benutzer mit ihren isolierten Nachrichten tun können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96dc1e2158787457884ca6a3c6f27bf76e83a369
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055178"
---
# <a name="quarantine-policies"></a>Quarantänerichtlinien

> [!NOTE]
> Die in diesem Artikel beschriebenen Features befinden sich derzeit in der Vorschau, sind nicht für alle verfügbar und können geändert werden.

Quarantänerichtlinien (früher als Quarantänetags bezeichnet) in Exchange Online Protection (EOP) ermöglichen Es Administratoren, zu steuern, was Benutzer mit ihren isolierten Nachrichten tun können, basierend darauf, wie die Nachricht in Quarantäne gelangt ist.

EOP hat traditionell bestimmte Interaktivitätsstufen für Nachrichten in [Quarantäne](find-and-release-quarantined-messages-as-a-user.md) und in [Spambenachrichtigungen](use-spam-notifications-to-release-and-report-quarantined-messages.md)von Endbenutzern zugelassen oder verhindert. Beispielsweise können Benutzer Nachrichten anzeigen und freigeben, die durch Antispamfilterung in Quarantäne gestellt wurden, als Spam oder massenweise, aber sie können nachrichten, die als Phishing mit hohem Vertrauen unter Quarantäne gestellt wurden, nicht anzeigen oder freigeben (nur Administratoren können dies tun).

Für [unterstützte Schutzfeatures](#step-2-assign-a-quarantine-policy-to-supported-features)geben Quarantänerichtlinien an, was Benutzer in Spambenachrichtigungsnachrichten von Endbenutzern und in ihren isolierten Nachrichten in Quarantäne (Nachrichten, in denen der Benutzer ein Empfänger ist) tun dürfen. Standardmäßige Quarantänerichtlinien werden automatisch zugewiesen, um die verlaufsbezogenen Funktionen für Benutzer für isolierte Nachrichten zu erzwingen. Sie können auch benutzerdefinierte Quarantänerichtlinien erstellen und zuweisen, um Endbenutzern das Ausführen bestimmter Aktionen für isolierte Nachrichten zu erlauben oder zu verhindern.

Die einzelnen Berechtigungen werden in den folgenden vordefinierten Berechtigungsgruppen kombiniert:

- Kein Zugriff
- Eingeschränkter Zugriff
- Vollzugriff

Die verfügbaren einzelnen Berechtigungen und was in den voreingestellten Berechtigungsgruppen enthalten ist oder nicht, werden in der folgenden Tabelle beschrieben:

<br>

****

|Berechtigung|Kein Zugriff|Eingeschränkter Zugriff|Vollzugriff|
|---|:---:|:---:|:---:|
|**Allow sender** (_PermissionToAllowSender_)|||![Häkchen](../../media/checkmark.png)|
|**Absender blockieren** (_PermissionToBlockSender_)||![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|**Delete** (_PermissionToDelete_)||![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|**Vorschau** (_PermissionToPreview_)||![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|**Zulassen, dass Empfänger eine Nachricht aus der Quarantäne freigeben** (_PermissionToRelease_)|||![Häkchen](../../media/checkmark.png)|
|**Zulassen, dass Empfänger anfordern, dass eine Nachricht aus der Quarantäne freigegeben wird** (_PermissionToRequestRelease_)||![Häkchen](../../media/checkmark.png)||
|

Wenn Ihnen die Standardberechtigungen in den voreingestellten Berechtigungsgruppen nicht gefallen, können Sie benutzerdefinierte Berechtigungen verwenden, wenn Sie benutzerdefinierte Quarantänerichtlinien erstellen oder ändern. Weitere Informationen zur Funktionsweise der einzelnen Berechtigungen finden Sie im Abschnitt mit den Details zu den [Quarantänerichtlinienberechtigungen](#quarantine-policy-permission-details) weiter unten in diesem Artikel.

Sie erstellen und weisen Quarantänerichtlinien im Microsoft 365 Defender Portal oder in PowerShell (Exchange Online PowerShell für Microsoft 365 Organisationen mit Exchange Online Postfächern; eigenständige EOP PowerShell in EOP-Organisationen ohne Exchange Online Postfächer) zu.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>. Oder um direkt zur Seite **"Quarantänerichtlinien"** zu wechseln, öffnen Sie <https://security.microsoft.com/quarantineTags> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Um Quarantänerichtlinien anzuzeigen, zu erstellen, zu ändern oder zu entfernen, müssen Sie Mitglied der Rollen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** im Microsoft 365 Defender Portal sein. Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md).

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Schritt 1: Erstellen von Quarantänerichtlinien im Microsoft 365 Defender-Portal

1. Wechseln Sie im Microsoft 365 Defender Portal zu **E-Mail &** \> Abschnitt "Richtlinien für **Bedrohungsrichtlinien** \> **für** die Zusammenarbeit", und wählen Sie dann \>  **"Quarantänerichtlinien"** aus.

2. Klicken Sie auf der Seite **"Quarantänerichtlinie"** auf ![ das Symbol ](../../media/m365-cc-sc-create-icon.png) **"Benutzerdefinierte Richtlinie hinzufügen".**

3. Der Assistent **für neue Richtlinien** wird geöffnet. Geben Sie auf der Seite **"Richtlinienname"** einen kurzen, aber eindeutigen Namen in das **Feld "Richtlinienname"** ein. In den nächsten Schritten müssen Sie die Quarantänerichtlinie anhand des Namens identifizieren und auswählen. Wenn Sie fertig sind, klicken Sie auf **Weiter**.

4. Wählen Sie auf der Seite **"Empfängernachrichtzugriff"** einen der folgenden Werte aus:
   - **Kein Zugriff**
   - **Beschränkter Zugriff**
   - **Vollzugriff**

   Die einzelnen Berechtigungen, die in diesen Berechtigungsgruppen enthalten sind, werden weiter oben in diesem Artikel beschrieben.

   Um benutzerdefinierte Berechtigungen anzugeben, wählen Sie **"Bestimmten Zugriff festlegen" (Erweitert)** aus, und konfigurieren Sie die folgenden angezeigten Einstellungen:

     - Auswählen der **Einstellung für Veröffentlichungsaktionen:** Wählen Sie einen der folgenden Werte aus:
       - **Keine Freigabeaktion:** Dies ist der Standardwert.
       - **Zulassen, dass Empfänger eine Nachricht aus der Quarantäne freigeben**
       - **Zulassen, dass Empfänger anfordern, dass eine Nachricht aus der Quarantäne freigegeben wird**
     - Wählen Sie zusätzliche Aktionen aus, **die Empfänger für isolierte Nachrichten ausführen können:** Wählen Sie einige, alle oder keinen der folgenden Werte aus:
       - **Delete**
       - **Preview**
       - **Absender blockieren**

   Diese Berechtigungen und ihre Auswirkungen auf isolierte Nachrichten und in Spambenachrichtigungen von Endbenutzern werden im Abschnitt mit den [Berechtigungsdetails](#quarantine-policy-permission-details) für Quarantänerichtlinien weiter unten in diesem Artikel beschrieben.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

5. Überprüfen Sie auf der daraufhin angezeigten Seite **"Richtlinie überprüfen"** Ihre Einstellungen. Sie können in jedem Abschnitt **Bearbeiten** auswählen, um die Einstellungen in diesem Abschnitt zu ändern. Alternativ können Sie auf **Zurück** klicken oder die entsprechende Seite im Assistenten auswählen.

   Wenn Sie fertig sind, klicken Sie auf **"Absenden".**

6. Klicken Sie in der angezeigten Bestätigungsseite auf **Fertig**.

Jetzt können Sie die Quarantänerichtlinie einem Quarantänefeature zuweisen, wie im Abschnitt ["Schritt 2"](#step-2-assign-a-quarantine-policy-to-supported-features) beschrieben.

### <a name="create-quarantine-policies-in-powershell"></a>Erstellen von Quarantänerichtlinien in PowerShell

Wenn Sie stattdessen PowerShell zum Erstellen von Quarantänerichtlinien verwenden möchten, stellen Sie eine Verbindung mit Exchange Online PowerShell oder Exchange Online Protection PowerShell her, und verwenden Sie das Cmdlet **"New-QuarantineTag".** Sie haben zwei verschiedene Methoden zur Auswahl:

- Verwenden Sie den _Parameter "EndUserQuarantinePermissionsValue"._
- Verwenden Sie den _EndUserQuarantinePermissions-Parameter._

Diese Methoden werden in den folgenden Abschnitten beschrieben.

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>Verwenden des Parameters "EndUserQuarantinePermissionsValue"

Verwenden Sie die folgende Syntax, um eine Quarantänerichtlinie mithilfe des _Parameters "EndUserQuarantinePermissionsValue"_ zu erstellen:

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

Der _EndUserQuarantinePermissionsValue-Parameter_ verwendet einen Dezimalwert, der aus einem binären Wert konvertiert wird. Der binäre Wert entspricht den verfügbaren Quarantäneberechtigungen für Endbenutzer in einer bestimmten Reihenfolge. Für jede Berechtigung entspricht der Wert 1 "True" und der Wert 0 "False".

Die erforderliche Reihenfolge und die Werte für jede einzelne Berechtigung in vordefinierten Berechtigungsgruppen werden in der folgenden Tabelle beschrieben:

<br>

****

|Berechtigung|Kein Zugriff|Eingeschränkter Zugriff|Vollzugriff|
|---|:---:|:---:|:---:|
|PermissionToAllowSender|0|0|1|
|PermissionToBlockSender|0|1|1|
|PermissionToDelete|0|1|1|
|PermissionToDownload<sup>\*</sup>|0|0|0|
|PermissionToPreview|0|1|1|
|PermissionToRelease<sup>\*\*</sup>|0|0|1|
|PermissionToRequestRelease<sup>\*\*</sup>|0|1|0|
|PermissionToViewHeader<sup>\*</sup>|0|0|0|
|Binärer Wert|00000000|01101010|11101100|
|Zu verwendende Dezimalwerte|0|106|236|
|

<sup>\*</sup> Derzeit ist dieser Wert immer 0. Bei PermissionToViewHeader blendet der Wert 0 die Schaltfläche **"Nachrichtenkopf anzeigen"** nicht in den Details der isolierten Nachricht aus (die Schaltfläche ist immer verfügbar).

<sup>\*\*</sup> Legen Sie nicht beide Werte auf 1 fest. Legen Sie eins auf 1 und das andere auf 0 oder beide auf 0 fest.

In diesem Beispiel wird ein neuer Quarantänerichtlinienname "NoAccess" erstellt, der die Berechtigungen "Kein Zugriff" wie in der vorherigen Tabelle beschrieben zuweist.

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

Verwenden Sie für eingeschränkte Zugriffsberechtigungen den Wert 106. Verwenden Sie für Vollzugriffsberechtigungen den Wert 236.

Verwenden Sie für benutzerdefinierte Berechtigungen die vorherige Tabelle, um den binären Wert abzurufen, der den gewünschten Berechtigungen entspricht. Konvertieren Sie den binären Wert in einen Dezimalwert, und verwenden Sie den Dezimalwert für den _Parameter "EndUserQuarantinePermissionsValue"._

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).

#### <a name="use-the-enduserquarantinepermissions-parameter"></a>Verwenden des EndUserQuarantinePermissions-Parameters

Führen Sie die folgenden Schritte aus, um eine Quarantänerichtlinie mithilfe des _Parameters "EndUserQuarantinePermissionsValue"_ zu erstellen:

A: Store ein Quarantäneberechtigungsobjekt in einer Variablen mithilfe des **Cmdlets "New-QuarantinePermissions" an.**

<p>

B. Verwenden Sie die Variable als _EndUserQuarantinePermissions-Wert_ im Befehl **"New-QuarantineTag".**

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a>Schritt A: Store eines Quarantäneberechtigungsobjekts in einer Variablen

Verwenden Sie die folgende Syntax:

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

Der Standardwert für alle nicht verwendeten Parameter ist `$false` , daher müssen Sie nur die Parameter verwenden, für die Sie den Wert festlegen `$true` möchten.

Die folgenden Beispiele zeigen, wie Berechtigungsobjekte erstellt werden, die den vordefinierten Berechtigungsgruppen entsprechen:

- **Kein Zugriff:**

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- **Beschränkter Zugriff:**

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- **Vollzugriff:**

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

Um die von Ihnen festgelegten Werte anzuzeigen, führen Sie den Variablennamen als Befehl aus (führen Sie z. B. den Befehl `$NoAccess` aus).

Legen Sie für benutzerdefinierte Berechtigungen nicht sowohl die _Parameter PermissionToRelease_ als auch _PermissionToRequestRelease_ auf `$true` . Legen Sie eine `$true` fest, und lassen Sie die andere als `$false` , oder lassen Sie beide als `$false` .

Sie können auch eine vorhandene Berechtigungsobjektvariable ändern, nachdem Sie sie erstellt haben, aber bevor Sie sie verwenden, indem Sie das Cmdlet **"Set-QuarantinePermissions"** verwenden.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["New-QuarantinePermissions"](/powershell/module/exchange/new-quarantinepermissions) und ["Set-QuarantinePermissions".](/powershell/module/exchange/set-quarantinepermissions)

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a>Schritt B: Verwenden der Variablen im Befehl New-QuarantineTag

Nachdem Sie das Berechtigungsobjekt in einer Variablen erstellt und gespeichert haben, verwenden Sie die Variable für den _EndUserQuarantinePermission-Parameterwert_ im folgenden **New-QuarantineTag-Befehl:**

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

In diesem Beispiel wird eine neue Quarantänerichtlinie namens LimitedAccess mithilfe des `$LimitedAccess` Berechtigungsobjekts erstellt, das im vorherigen Schritt beschrieben und erstellt wurde.

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a>Schritt 2: Zuweisen einer Quarantänerichtlinie zu unterstützten Features

In _unterstützten_ Schutzfeatures, die Nachrichten oder Dateien unter Quarantäne stellen (automatisch oder als konfigurierbare Aktion), können Sie den verfügbaren Quarantäneaktionen eine Quarantänerichtlinie zuweisen. Features, die Nachrichten unter Quarantäne stellen, und die Verfügbarkeit von Quarantänerichtlinien werden in der folgenden Tabelle beschrieben:

<br>

****

|Feature|Unterstützte Quarantänerichtlinien?|Verwendete Standardquarantänerichtlinien|
|---|:---:|---|
|[Antispamrichtlinien:](configure-your-spam-filter-policies.md) <ul><li>**Spam** (_SpamAction_)</li><li>**Spam mit hoher Konfidenz** (_HighConfidenceSpamAction_)</li><li>**Phishing** (_PhishSpamAction_)</li><li>Phishing mit **hoher Konfidenz** (_HighConfidencePhishAction_)</li><li>**Bulk** (_BulkSpamAction_)</li></ul>|Ja|<ul><li>DefaultSpamTag (Vollzugriff)</li><li>DefaultHighConfSpamTag (Vollzugriff)</li><li>DefaultPhishTag (Vollzugriff)</li><li>DefaultHighConfPhishTag (Kein Zugriff)</li><li>DefaultBulkTag (Vollzugriff)</li></ul>
|Antiphishingrichtlinien: <ul><li>[Schutz vor Spoofintelligenz](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</li><li>[Identitätswechselschutz:](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)<sup>\*</sup> <ul><li>**Wenn eine Nachricht als angenommener Benutzer erkannt wird** (_TargetedUserProtectionAction_)</li><li>**Wenn eine Nachricht als imitierte Domäne erkannt wird** (_TargetedDomainProtectionAction_)</li><li>**Wenn die Postfachintelligenz einen Benutzer erkennt und imitiert** (_MailboxIntelligenceProtectionAction_)</li></ul></li></ul></ul>|Nein|n/v|
|[Antischadsoftwarerichtlinien:](configure-anti-malware-policies.md)Alle erkannten Nachrichten werden immer unter Quarantäne gestellt.|Nein|n/v|
|[Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)|Nein|n/v|
|[Nachrichtenflussregeln](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch als Transportregeln bezeichnet) mit der Aktion: **Übermitteln der Nachricht an die gehostete Quarantäne** (_Quarantäne_).|Nein|n/v|
|

<sup>\*</sup>Einstellungen für den Identitätswechselschutz sind nur in Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügbar.

Wenn Sie mit den Endbenutzerberechtigungen zufrieden sind, die von den Standardquarantänerichtlinien bereitgestellt werden, müssen Sie nichts unternehmen. Wenn Sie die Endbenutzerfunktionen (verfügbare Schaltflächen) in Spambenachrichtigungen von Endbenutzern oder In-Quarantäne-Nachrichtendetails anpassen möchten, können Sie eine benutzerdefinierte Quarantänerichtlinie zuweisen.

### <a name="assign-quarantine-policies-in-anti-spam-policies-in-the-microsoft-365-defender-portal"></a>Zuweisen von Quarantänerichtlinien in Antispamrichtlinien im Microsoft 365 Defender Portal

Vollständige Anweisungen zum Erstellen und Ändern von Antispamrichtlinien werden unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)beschrieben.

1. Wechseln Sie im portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit \> **&** \> **Regelrichtlinien** Abschnitt \> **Antispam**. Oder öffnen <https://security.microsoft.com/antispam> Sie .

2. Führen Sie auf der Seite **"Antispamrichtlinien"** einen der folgenden Schritte aus:
   - Suchen und Auswählen einer vorhandenen **eingehenden** Antispamrichtlinie.
   - Erstellen Sie eine neue **Eingehende Antispamrichtlinie.**

3. Führen Sie einen der folgenden Schritte aus:
   - **Vorhandene Antispamrichtlinie bearbeiten:** Wechseln Sie im Richtliniendetails-Flyout zum Abschnitt **"Aktionen",** und klicken Sie dann auf **"Aktionen bearbeiten".**
   - **Erstellen Sie eine neue Antispamrichtlinie:** Wechseln Sie im Assistenten für neue Richtlinien zur Seite **"Aktionen".**

4. Auf der Seite **"Aktionen".** Für jedes Diktat mit der **Quarantäne-Nachrichtenaktion** wird auch das **Feld "Quarantänerichtlinie** auswählen" angezeigt, in dem Sie eine entsprechende Quarantänerichtlinie auswählen können.

   **Hinweis:** Wenn Sie eine neue Richtlinie erstellen, gibt ein leerer **Select-Quarantänerichtlinienwert** die Standardquarantänerichtlinie für diese Bewertung an. Wenn Sie die Richtlinie später bearbeiten, werden die leeren Werte durch die tatsächlichen Standardmäßige Quarantänerichtliniennamen ersetzt, wie in der vorherigen Tabelle beschrieben.

   ![Auswahl von Quarantänerichtlinien in einer Antispamrichtlinie](../../media/quarantine-tags-in-anti-spam-policies.png)

5. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

#### <a name="assign-quarantine-policies-in-anti-spam-policies-in-powershell"></a>Zuweisen von Quarantänerichtlinien in Antispamrichtlinien in PowerShell

Wenn Sie PowerShell lieber zum Zuweisen von Quarantänerichtlinien in Antispamrichtlinien verwenden möchten, stellen Sie eine Verbindung mit Exchange Online PowerShell her oder Exchange Online Protection PowerShell, und verwenden Sie die folgende Syntax:

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**Hinweise**:

- Der Standardwert für den _Parameter "HighConfidencePhishAction"_ lautet "Quarantine", sodass Sie die Quarantäneaktion für Phishing-Erkennungen mit hohem Vertrauen in neuen Antispamrichtlinien nicht festlegen müssen. Für alle anderen Spamfilterbewertungen in neuen oder vorhandenen Antispamrichtlinien ist die Quarantänerichtlinie nur wirksam, wenn der Aktionswert "Quarantäne" lautet. Führen Sie den folgenden Befehl aus, um die Aktionswerte in vorhandenen Antispamrichtlinien anzuzeigen:

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  Informationen zu den Standardaktionswerten und den empfohlenen Aktionswerten für Standard und Strict finden Sie unter [EOP Antispamrichtlinieneinstellungen.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

- Ein Spamfilter-Bewertung ohne entsprechenden Quarantänerichtlinienparameter bedeutet, dass die [Standardquarantänerichtlinie](#step-2-assign-a-quarantine-policy-to-supported-features) für dieses Diktat verwendet wird.

  Sie müssen eine Standardquarantänerichtlinie nur durch eine benutzerdefinierte Quarantänerichtlinie ersetzen, wenn Sie die Standardmäßigen Endbenutzerfunktionen für isolierte Nachrichten ändern möchten.

- Eine neue Antispamrichtlinie in PowerShell erfordert eine Spamfilterrichtlinie (Einstellungen) mit dem Cmdlet **"New-HostedContentFilterPolicy"** und eine neue Spamfilterregel (Empfängerfilter) mit dem Cmdlet **"New-HostedContentFilterRule".** Anweisungen finden Sie unter [Verwenden von PowerShell zum Erstellen von Antispamrichtlinien.](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)

In diesem Beispiel wird eine neue Spamfilterrichtlinie namens Research Department mit den folgenden Einstellungen erstellt:

- Die Aktion für alle Spamfilterbewertungen ist auf "Quarantäne" festgelegt.
- Die benutzerdefinierte Quarantänerichtlinie mit dem Namen "NoAccess", die **Keine Zugriffsberechtigungen** zuweist, ersetzt standardmäßige Quarantänerichtlinien, denen standardmäßig noch keine **Zugriffsberechtigungen** zugewiesen wurden.

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).

In diesem Beispiel wird die vorhandene Spamfilterrichtlinie mit dem Namen "Personalwesen" geändert. Die Aktion für die Spamquarantänebewertung ist auf "Quarantäne" festgelegt, und die benutzerdefinierte Quarantänerichtlinie "NoAccess" wird zugewiesen.

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a>Konfigurieren der Einstellungen für globale Quarantänebenachrichtigungen im Microsoft 365 Defender Portal

Mit den globalen Einstellungen für Quarantänerichtlinien können Sie die Spambenachrichtigungen der Endbenutzer anpassen, die an Empfänger von Nachrichten gesendet werden, die in Quarantäne gestellt wurden. Weitere Informationen zu diesen Benachrichtigungen finden Sie unter [Spambenachrichtigungen für Endbenutzer.](use-spam-notifications-to-release-and-report-quarantined-messages.md)

1. Wechseln Sie im portal Microsoft 365 Defender zu **E-Mail &** \> Abschnitt "Richtlinien für **Bedrohungsrichtlinien** \> **für** die Zusammenarbeit" im Abschnitt \> **"Quarantänerichtlinien",** und wählen Sie dann **"Quarantänerichtlinien"** aus.

2. Wählen Sie auf der Seite **"Quarantänerichtlinie"** die Option **"Globale Einstellungen" aus.**

3. Konfigurieren Sie im flyout **"Quarantänebenachrichtigungseinstellungen",** das geöffnet wird, einige oder alle der folgenden Einstellungen:

   - **Anzeigename:** Passen Sie den Anzeigenamen des Absenders an, der in Spambenachrichtigungen für Endbenutzer verwendet wird.

     Wählen Sie für jede Sprache, die Sie hinzugefügt haben, die Sprache im Feld "Zweite Sprache" aus (klicken Sie nicht auf das X), und geben Sie den gewünschten Textwert in das **Feld "Anzeigename"** ein.

     Der folgende Screenshot zeigt den angepassten Anzeigenamen in einer Spambenachrichtigung für Endbenutzer:

     ![Ein angepasster Absenderanzeigename in einer Spambenachrichtigung des Endbenutzers](../../media/quarantine-tags-esn-customization-display-name.png)

   - **Haftungsausschluss:** Fügen Sie am Ende von Spambenachrichtigungen für Endbenutzer einen benutzerdefinierten Haftungsausschluss hinzu. Der lokalisierte Text, **ein Haftungsausschluss aus Ihrer Organisation:** wird immer zuerst einbezogen, gefolgt von dem von Ihnen angegebenen Text.

     Wählen Sie für jede Sprache, die Sie hinzugefügt haben, die Sprache im feld "Zweite Sprache" aus (klicken Sie nicht auf das X), und geben Sie den gewünschten Textwert in das **Feld "Haftungsausschluss"** ein.

     Der folgende Screenshot zeigt den angepassten Haftungsausschluss in einer Spambenachrichtigung für Endbenutzer:

     ![Ein benutzerdefinierter Haftungsausschluss am Ende einer Spambenachrichtigung für Endbenutzer](../../media/quarantine-tags-esn-customization-disclaimer.png)

   - **Sprache auswählen:** Spambenachrichtigungen von Endbenutzern sind bereits basierend auf den Spracheinstellungen des Empfängers lokalisiert. Sie können benutzerdefinierten Text in verschiedenen Sprachen für den **Anzeigenamen** und **den Haftungsausschluss** angeben.

     Wählen Sie im Feld "Erste Sprache" mindestens eine Sprache aus, und klicken Sie dann auf **"Hinzufügen".** Sie können mehrere Sprachen auswählen, indem Sie nacheinander auf **"Hinzufügen"** klicken. In einem Abschnittssprachenfeld werden alle sprachen angezeigt, die Sie ausgewählt haben:

     ![Ausgewählte Sprachen im Feld "Zweite Sprache" in den globalen Quarantänebenachrichtigungseinstellungen für Quarantänerichtlinien](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - **Verwenden Sie mein Firmenlogo:** Wählen Sie diese Option aus, um das standardmäßige Microsoft-Logo zu ersetzen, das oben in Spambenachrichtigungen von Endbenutzern verwendet wird. Bevor Sie dies tun, müssen Sie die Anweisungen in ["Anpassen des Microsoft 365 Designs für Ihre Organisation"](../../admin/setup/customize-your-organization-theme.md) befolgen, um Ihr benutzerdefiniertes Logo hochzuladen.

     Der folgende Screenshot zeigt ein benutzerdefiniertes Logo in einer Spambenachrichtigung für Endbenutzer:

     ![Ein benutzerdefiniertes Logo in einer Spambenachrichtigung für Endbenutzer](../../media/quarantine-tags-esn-customization-logo.png)

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Anzeigen von Quarantänerichtlinien im Microsoft 365 Defender-Portal

1. Wechseln Sie im portal Microsoft 365 Defender zu **E-Mail &** \> Abschnitt "Richtlinien für **Bedrohungsrichtlinien** \> **für** die Zusammenarbeit" im Abschnitt \> **"Quarantänerichtlinien",** und wählen Sie dann **"Quarantänerichtlinien"** aus.

2. Auf der Seite **"Quarantänerichtlinie"** wird die Liste der Richtlinien nach **Name** und Datum der **letzten Aktualisierung** angezeigt.

3. Um die Einstellungen der integrierten oder benutzerdefinierten Quarantänerichtlinien anzuzeigen, wählen Sie die Quarantänerichtlinie aus der Liste aus, indem Sie auf den Namen klicken.

4. Klicken Sie auf **"Globale Einstellungen",** um die globalen Einstellungen anzuzeigen.

### <a name="view-quarantine-policies-in-powershell"></a>Anzeigen von Quarantänerichtlinien in PowerShell

Wenn Sie PowerShell lieber zum Anzeigen von Quarantänerichtlinien verwenden möchten, führen Sie einen der folgenden Schritte aus:

- Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller integrierten oder benutzerdefinierten Richtlinien anzuzeigen:

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- Um die Einstellungen der integrierten oder benutzerdefinierten Quarantänerichtlinien anzuzeigen, ersetzen Sie \<QuarantinePolicyName\> durch den Namen der Quarantänerichtlinie, und führen Sie den folgenden Befehl aus:

  ```powershell
  Get-QuarantineTag -Identity "<QuarantinePolicyName>"
  ```

- Führen Sie den folgenden Befehl aus, um die globalen Einstellungen anzuzeigen:

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Ändern von Quarantänerichtlinien im Microsoft 365 Defender-Portal

1. Wechseln Sie im portal Microsoft 365 Defender zu **E-Mail &** \> Abschnitt "Richtlinien für **Bedrohungsrichtlinien** \> **für** die Zusammenarbeit" im Abschnitt \> **"Quarantänerichtlinien",** und wählen Sie dann **"Quarantänerichtlinien"** aus.

2. Wählen Sie auf der Seite **"Quarantänerichtlinien"** die Richtlinie aus, indem Sie auf den Namen klicken.

3. Nachdem Sie die Richtlinie ausgewählt haben, klicken Sie auf das ![ symbol ](../../media/m365-cc-sc-edit-icon.png) **"Richtlinie bearbeiten",** das angezeigt wird.

4. Der Assistent zum Bearbeiten von **Richtlinien,** der geöffnet wird, ist nahezu identisch mit dem Assistenten für **neue Richtlinien,** wie im Abschnitt "Erstellen von [Quarantänerichtlinien im Abschnitt Microsoft 365 Defender Portal"](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) weiter oben in diesem Artikel beschrieben.

   Der Hauptunterschied besteht darin, dass Sie eine vorhandene Richtlinie nicht umbenennen können.

5. Wenn Sie die Richtlinie geändert haben, wechseln Sie zur Seite **"Zusammenfassung",** und klicken Sie auf **"Übermitteln".**

### <a name="modify-quarantine-policies-in-powershell"></a>Ändern von Quarantänerichtlinien in PowerShell

Wenn Sie PowerShell lieber zum Ändern einer benutzerdefinierten Quarantänerichtlinie verwenden möchten, ersetzen Sie \<QuarantinePolicyName\> diese durch den Namen der Quarantänerichtlinie, und verwenden Sie die folgende Syntax:

```powershell
Set-QuarantineTag -Identity "<QuarantinePolicyName>" [Settings]
```

Die verfügbaren Einstellungen sind die gleichen wie bei der Erstellung von Quarantänerichtlinien weiter oben in diesem Artikel beschrieben.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-QuarantineTag".](/powershell/module/exchange/set-quarantinetag)

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Entfernen von Quarantänerichtlinien im Microsoft 365 Defender-Portal

**Hinweise**:

- Integrierte Quarantänerichtlinien können nicht entfernt werden.
- Bevor Sie eine benutzerdefinierte Quarantänerichtlinie entfernen, stellen Sie sicher, dass sie nicht verwendet wird. Führen Sie beispielsweise den folgenden Befehl in PowerShell aus:

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  Wenn die Quarantänerichtlinie verwendet wird, ersetzen Sie [die zugewiesene Quarantänerichtlinie,](#step-2-assign-a-quarantine-policy-to-supported-features) bevor Sie sie entfernen.

1. Wechseln Sie im portal Microsoft 365 Defender zu **E-Mail &** \> Abschnitt "Richtlinien für **Bedrohungsrichtlinien** \> **für** die Zusammenarbeit" im Abschnitt \> **"Quarantänerichtlinien",** und wählen Sie dann **"Quarantänerichtlinien"** aus.

2. Wählen Sie auf der Seite **"Quarantänerichtlinie"** die benutzerdefinierte Quarantänerichtlinie aus, die Sie entfernen möchten, indem Sie auf den Namen klicken.

3. Nachdem Sie die Richtlinie ausgewählt haben, klicken Sie auf das ![ Symbol ](../../media/m365-cc-sc-delete-icon.png) **"Richtlinie löschen",** das angezeigt wird.

4. Klicken Sie im daraufhin angezeigten Bestätigungsdialogfeld auf **"Richtlinie entfernen".**

### <a name="remove-quarantine-policies-in-powershell"></a>Entfernen von Quarantänerichtlinien in PowerShell

Wenn Sie PowerShell lieber zum Entfernen einer benutzerdefinierten Quarantänerichtlinie verwenden möchten, ersetzen Sie \<QuarantinePolicyName\> diese durch den Namen der Quarantänerichtlinie, und führen Sie den folgenden Befehl aus:

```powershell
Remove-QuarantineTag -Identity "<QuarantinePolicyName>"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).

## <a name="quarantine-policy-permission-details"></a>Details zu Den Berechtigungen für Quarantänerichtlinien

In den folgenden Abschnitten werden die Auswirkungen voreingestellter Berechtigungsgruppen und einzelner Berechtigungen in den Details von isolierten Nachrichten und in Spambenachrichtigungen für Endbenutzer beschrieben.

### <a name="preset-permissions-groups"></a>Vordefinierte Berechtigungsgruppen

Die einzelnen Berechtigungen, die in vordefinierten Berechtigungsgruppen enthalten sind, sind in der Tabelle am Anfang dieses Artikels aufgeführt.

#### <a name="no-access"></a>Kein Zugriff

Wenn die Quarantänerichtlinie die Berechtigungen **"Kein Zugriff"** (keine Berechtigungen) zuweist, erhalten Die Benutzer dennoch einige grundlegende Funktionen:

- **Details zu isolierten Nachrichten:** Die Schaltfläche **"Nachrichtenkopf anzeigen"** ist immer verfügbar.

  ![Verfügbare Schaltflächen in den Details der isolierten Nachricht, wenn die Quarantänerichtlinie dem Benutzer keine Zugriffsberechtigungen erteilt](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- **Spambenachrichtigungen** für Endbenutzer: Die Schaltfläche **"Überprüfen",** die den Benutzer zur Nachricht in Quarantäne bringt, ist immer verfügbar.

  ![Verfügbare Schaltflächen in der Spambenachrichtigung des Endbenutzers, wenn die Quarantänerichtlinie dem Benutzer keine Zugriffsberechtigungen gewährt](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a>Eingeschränkter Zugriff

Wenn die Quarantänerichtlinie die Berechtigungen für **den eingeschränkten Zugriff** zuweist, erhalten Benutzer die folgenden Funktionen:

- **Details zu isolierten Nachrichten:** Die folgenden Schaltflächen sind verfügbar:
  - **Anforderungsfreigabe**
  - **Nachrichtenkopfzeile anzeigen**
  - **Vorschaunachricht**
  - **Absender blockieren**
  - **Aus Quarantäne entfernen**

  ![Verfügbare Schaltflächen in den Details der isolierten Nachricht, wenn die Quarantänerichtlinie dem Benutzer eingeschränkte Zugriffsberechtigungen erteilt](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- **Spambenachrichtigungen für Endbenutzer:** Die folgenden Schaltflächen sind verfügbar:
  - **Absender blockieren**
  - **Überprüfung**

  ![Verfügbare Schaltflächen in der Spambenachrichtigung des Endbenutzers, wenn die Quarantänerichtlinie dem Benutzer eingeschränkte Zugriffsberechtigungen erteilt](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a>Vollzugriff

Wenn die Quarantänerichtlinie die **Vollzugriffsberechtigungen** (alle verfügbaren Berechtigungen) zuweist, erhalten Benutzer die folgenden Funktionen:

- **Details zu isolierten Nachrichten:** Die folgenden Schaltflächen sind verfügbar:
  - **Veröffentlichungsnachricht**
  - **Nachrichtenkopfzeile anzeigen**
  - **Vorschaunachricht**
  - **Absender blockieren**
  - **Absender zulassen**
  - **Aus Quarantäne entfernen**

  ![Verfügbare Schaltflächen in den Details der isolierten Nachricht, wenn die Quarantänerichtlinie dem Benutzer Vollzugriffsberechtigungen erteilt](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- **Spambenachrichtigungen für Endbenutzer:** Die folgenden Schaltflächen sind verfügbar:
  - **Absender blockieren**
  - **Freigabe**
  - **Überprüfung**

  ![Verfügbare Schaltflächen in der Spambenachrichtigung des Endbenutzers, wenn die Quarantänerichtlinie dem Benutzer Vollzugriff gewährt](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a>Einzelne Berechtigungen

> [!NOTE]
> Denken Sie daran, dass Benutzer immer die im Abschnitt ["Kein Zugriff"](#no-access) beschriebenen Schaltflächen erhalten. Diese Schaltflächen sind nicht in den einzelnen Berechtigungsbeschreibungen enthalten.

#### <a name="allow-sender-permission"></a>Absenderberechtigung zulassen

Die Berechtigung **"Absender zulassen"** (_PermissionToAllowSender_) steuert den Zugriff auf die Schaltfläche, mit der Benutzer den in Quarantäne befindlichen Nachrichtensender bequem zur Liste der Tresor Absender hinzufügen können.

- **Details zu isolierten Nachrichten:**
  - **Absenderberechtigung** zulassen aktiviert: Die Schaltfläche **"Absender zulassen"** ist verfügbar.
  - **Absenderberechtigung** zulassen deaktiviert: Die Schaltfläche **"Absender zulassen"** ist nicht verfügbar.

- **Spambenachrichtigungen für Endbenutzer:** Keine Auswirkung.

Weitere Informationen zur Liste der Tresor Absender finden Sie unter [Verhindern, dass vertrauenswürdige Absender blockiert werden,](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) und [verwenden Sie Exchange Online PowerShell, um die Sammlung](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)sicherer Listen in einem Postfach zu konfigurieren.

#### <a name="block-sender-permission"></a>Absenderberechtigung blockieren

Die Berechtigung **"Absender blockieren"** (_PermissionToBlockSender_) steuert den Zugriff auf die Schaltfläche, mit der Benutzer den in Quarantäne befindlichen Nachrichtensender bequem zur Liste der blockierten Absender hinzufügen können.

- **Details zu isolierten Nachrichten:**
  - **Absenderberechtigung blockieren** aktiviert: Die Schaltfläche **"Absender blockieren"** ist verfügbar.
  - **Absenderberechtigung** blockieren deaktiviert: Die Schaltfläche **"Absender blockieren"** ist nicht verfügbar.

- **Spambenachrichtigungen für Endbenutzer:**
  - **Absenderberechtigung** blockieren deaktiviert: Die Schaltfläche **"Absender blockieren"** ist nicht verfügbar.
  - **Absenderberechtigung blockieren** aktiviert: Die Schaltfläche **"Absender blockieren"** ist verfügbar.

Weitere Informationen zur Liste blockierter Absender finden Sie unter [Blockieren von Nachrichten von einer Person](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) und Verwenden von Exchange Online [PowerShell zum Konfigurieren der Sammlung sicherer Listen in einem Postfach.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)

#### <a name="delete-permission"></a>Löschen

Die **Berechtigung "Löschen"** (_PermissionToDelete_) steuert die Möglichkeit, dass Benutzer ihre Nachrichten (Nachrichten, in denen der Benutzer ein Empfänger ist) aus der Quarantäne löschen können.

- **Details zu isolierten Nachrichten:**
  - **Berechtigung löschen** aktiviert: Die Schaltfläche **"Aus Quarantäne entfernen"** ist verfügbar.
  - **Berechtigung löschen** deaktiviert: Die Schaltfläche **"Aus Quarantäne entfernen"** ist nicht verfügbar.

- **Spambenachrichtigungen für Endbenutzer:** Keine Auswirkung.

#### <a name="preview-permission"></a>Vorschauberechtigung

Die **Vorschauberechtigung** (_PermissionToPreview_) steuert die Möglichkeit für Benutzer, eine Vorschau ihrer Nachrichten in Quarantäne anzuzeigen.

- **Details zu isolierten Nachrichten:**
  - **Vorschauberechtigung** aktiviert: Die Schaltfläche **"Vorschaunachricht"** ist verfügbar.
  - **Vorschauberechtigung** deaktiviert: Die Schaltfläche **"Vorschaunachricht"** ist nicht verfügbar.

- **Spambenachrichtigungen für Endbenutzer:** Keine Auswirkung.

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>Zulassen, dass Empfänger eine Nachricht aus der Quarantäneberechtigung freigeben

Die **Berechtigung "Empfängern** das Freigeben einer Nachricht aus der Quarantäneberechtigung (_PermissionToRelease_) erlauben" steuert die Möglichkeit, dass Benutzer ihre isolierten Nachrichten direkt und ohne Genehmigung eines Administrators freigeben können.

- **Details zu isolierten Nachrichten:**
  - Berechtigung aktiviert: Die Schaltfläche **"Nachricht freigeben"** ist verfügbar.
  - Berechtigung deaktiviert: Die Schaltfläche **"Nachricht freigeben"** ist nicht verfügbar.

- **Spambenachrichtigungen für Endbenutzer:**
  - Berechtigung aktiviert: Die Schaltfläche **"Freigeben"** ist verfügbar.
  - Berechtigung deaktiviert: Die Schaltfläche **"Freigeben"** ist nicht verfügbar.

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>Zulassen, dass Empfänger anfordern, dass eine Nachricht aus der Quarantäneberechtigung freigegeben wird

Die **Einstellung "Empfängern** das Anfordern der Freigabe einer Nachricht aus der Quarantäneberechtigung "_PermissionToRequestRelease_" erlaubt die Möglichkeit von Benutzern, die Freigabe ihrer isolierten Nachrichten _anzufordern._ Die Nachricht wird erst freigegeben, nachdem ein Administrator die Anforderung genehmigt hat.

- **Details zu isolierten Nachrichten:**
  - Berechtigung aktiviert: Die Schaltfläche **"Freigabe anfordern"** ist verfügbar.
  - Berechtigung deaktiviert: Die Schaltfläche **"Freigabe anfordern"** ist nicht verfügbar.

- **Spambenachrichtigungen für Endbenutzer:** Die Schaltfläche **"Freigeben"** ist nicht verfügbar.
