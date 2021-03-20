---
title: Einrichten von Richtlinien für sichere Anlagen in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie Richtlinien für sichere Anlagen definieren, um Ihre Organisation vor schädlichen Dateien in E-Mails zu schützen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d48e373dc95aaa65d0f436f99208d926477aacd6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918714"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Einrichten von Richtlinien für sichere Anlagen in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](office-365-atp.md) verfügen. Wenn Sie ein Heimbenutzer sind, der Informationen zur Anlagenprüfung in Outlook sucht, lesen Sie [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Sichere Anlagen ist ein Feature in [Microsoft Defender für Office 365,](office-365-atp.md) das eine virtuelle Umgebung verwendet, um Anlagen in eingehenden [E-Mail-Nachrichten](anti-malware-protection.md)zu überprüfen, nachdem sie vom Schutz vor Schadsoftware in Exchange Online Protection (EOP) überprüft wurden, jedoch vor der Zustellung an Empfänger. Weitere Informationen finden Sie unter [Sichere Anlagen in Microsoft Defender für Office 365](atp-safe-attachments.md).

Es gibt keine integrierte oder standardmäßige Richtlinie für sichere Anlagen. Um die Überprüfung sicherer Anlagen von E-Mail-Nachrichtenanlagen zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere Anlagen erstellen, wie in diesem Artikel beschrieben.

Sie können Richtlinien für sichere Anlagen im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige eOP PowerShell für Organisationen ohne Exchange &, aber mit Defender for Office 365-Add-On-Abonnements) konfigurieren.

Die grundlegenden Elemente einer Richtlinie für sichere Anlagen sind:

- **Die Richtlinie** für sichere Anlagen: Gibt die Aktionen für unbekannte Schadsoftwareerkennungen an, ob Nachrichten mit Schadsoftwareanlagen an eine angegebene E-Mail-Adresse gesendet werden sollen und ob Nachrichten zu senden sind, wenn die Überprüfung sicherer Anlagen nicht abgeschlossen werden kann.
- **Die Regel für sichere Anlagen:** Gibt die Prioritäts- und Empfängerfilter an (auf wen die Richtlinie angewendet wird).

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für sichere Anlagen im Security & Compliance Center verwalten:

- Wenn Sie eine Richtlinie für sichere Anlagen erstellen, erstellen Sie tatsächlich eine sichere Anlagenregel und die zugeordnete richtlinie für sichere Anlagen gleichzeitig mit demselben Namen für beide.
- Wenn Sie eine Richtlinie für sichere Anlagen ändern, ändern Einstellungen im Zusammenhang mit dem Namen, der Priorität, aktiviert oder deaktiviert sowie Empfängerfilter die Regel für sichere Anlagen. Alle anderen Einstellungen ändern die zugeordnete Richtlinie für sichere Anlagen.
- Wenn Sie eine Richtlinie für sichere Anlagen entfernen, werden die Regel für sichere Anlagen und die zugehörige Richtlinie für sichere Anlagen entfernt.

In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt. Weitere Informationen finden Sie im Abschnitt Verwenden von [Exchange Online PowerShell oder eigenständiger EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) zum Konfigurieren von Richtlinien für sichere Anlagen weiter unten in diesem Artikel.

> [!NOTE]
> Im Bereich "Globale Einstellungen" der Einstellungen für sichere Anlagen konfigurieren Sie Features, die nicht von Richtlinien für sichere Anlagen abhängig sind. Anweisungen finden [Sie unter Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and Safe Documents in Microsoft [365 E5](safe-docs.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite Sichere **Anlagen zu** wechseln, verwenden Sie <https://protection.office.com/safeattachmentv2> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden:
  - Zum Erstellen, Ändern und Löschen von Richtlinien für sichere Anlagen müssen  Sie Mitglied der Rollengruppen Organisationsverwaltung oder Sicherheitsadministrator  im Security & Compliance **Center** und Mitglied der Rollengruppe Organisationsverwaltung in Exchange Online sein. 
  - Für den schreibgeschützten Zugriff auf Richtlinien für sichere Anlagen müssen  Sie Mitglied der Rollengruppen **"Globaler** Leser" oder "Sicherheitsleser" im Security & Compliance Center sein.

  Weitere Informationen finden Sie unter [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and Permissions in Exchange [Online](/exchange/permissions-exo/permissions-exo).

  **Hinweise**:

  - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Unsere empfohlenen Einstellungen für Richtlinien für sichere Anlagen finden Sie unter [Einstellungen für sichere Anlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

- Es ist bis zu 30 Minuten zulässig, bis eine neue oder aktualisierte Richtlinie angewendet wird.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>Erstellen von Richtlinien für & Anlagen mithilfe des Security & Compliance Centers

Beim Erstellen einer benutzerdefinierten Richtlinie für sichere Anlagen im Security & Compliance Center werden die Regel für sichere Anlagen und die zugeordnete richtlinie für sichere Anlagen gleichzeitig mit demselben Namen für beide erstellt.

1. Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **ATP Sichere Anlagen**.

2. Klicken Sie **auf der** Seite Sichere Anlagen auf **Erstellen**.

3. Der **Richtlinien-Assistent für neue sichere** Anlagen wird geöffnet. Konfigurieren Sie **auf der Seite** Ihre Richtlinie benennen die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.

   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Konfigurieren Sie **auf** der angezeigten Seite Einstellungen die folgenden Einstellungen:

   - **Sichere Anlagen unbekannte Schadsoftwareantwort:** Wählen Sie einen der folgenden Werte aus:

     - **Off**: In der Regel wird dieser Wert nicht empfohlen.
     - **Überwachen**
     - **Block**: Dies ist der Standardwert und der empfohlene Wert in standard und Strict [voreingestellte Sicherheitsrichtlinien](preset-security-policies.md).
     - **Replace**
     - **Dynamische Übermittlung (Vorschaufeature)**

     Diese Werte werden unter Richtlinieneinstellungen für sichere [Anlagen erläutert.](atp-safe-attachments.md#safe-attachments-policy-settings)

   - Senden Sie die Anlage an die folgende E-Mail-Adresse: Für  die Aktionswerte **Block,** **Monitor** oder **Replace** können Sie Umleitung aktivieren auswählen, um Nachrichten mit Schadsoftwareanlagen zur Analyse und Untersuchung an die angegebene interne oder externe E-Mail-Adresse zu senden. 

     Die Empfehlung für Standard- und Strict-Richtlinieneinstellungen besteht in der Aktivierung der Umleitung. Weitere Informationen finden Sie unter [Einstellungen für sichere Anlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

   - **Wenden Sie die oben** aufgeführte Auswahl an, wenn die  Schadsoftwareprüfung auf Anlagen ein Zeit- oder Fehlerfehler auftritt: Die durch die unbekannte Schadsoftwareantwort für sichere Anlagen angegebene Aktion wird für Nachrichten ausgeführt, auch wenn die Überprüfung sicherer Anlagen nicht abgeschlossen werden kann. Wenn Sie diese Option ausgewählt haben, wählen Sie immer **Umleitung aktiviert aus.** Andernfalls gehen Nachrichten möglicherweise verloren.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Identifizieren Sie **auf der angezeigten** Seite Angewendet auf die internen Empfänger, auf die die Richtlinie angewendet wird.

   Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

   Klicken **Sie auf Bedingung hinzufügen**. Wählen Sie in der angezeigten Dropdownliste unter Angewendet eine **Bedingung aus, wenn**:

   - **Der Empfänger ist**: Gibt ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation an.
   - **Der Empfänger ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an.
   - **Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.

   Nachdem Sie die Bedingung ausgewählt haben, wird ein entsprechendes Dropdownfeld mit einem **Beliebigen dieser Kontrollkästchen** angezeigt.

   - Klicken Sie in das Feld, und scrollen Sie durch die Liste der auszuwählende Werte.
   - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.
   - Klicken Sie auf einen leeren Bereich im Feld, um weitere Werte hinzuzufügen.
   - Klicken Sie zum Entfernen einzelner Einträge **auf Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für den Wert.
   - Klicken Sie zum Entfernen der gesamten Bedingung auf **Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für die Bedingung.

   Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen,** und wählen Sie einen verbleibenden Wert unter **Angewendet wenn aus.**

   Klicken Sie zum Hinzufügen von Ausnahmen auf **Bedingung hinzufügen,** und wählen Sie unter **Except if eine Ausnahme aus.** Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

6. Überprüfen Sie **auf der angezeigten** Seite Einstellungen überprüfen Ihre Einstellungen. Sie können **für** jede Einstellung auf Bearbeiten klicken, um sie zu ändern.

   Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien für sichere Anlagen

1. Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **ATP Sichere Anlagen**.

2. Wählen Sie **auf** der Seite Sichere Anlagen eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

   Die Richtliniendetails werden in einem Fly-Out angezeigt.

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>Verwenden des Security & Compliance Center zum Ändern von Richtlinien für sichere Anlagen

1. Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **ATP Sichere Anlagen**.

2. Wählen Sie **auf** der Seite Sichere Anlagen eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

3. Klicken Sie in den angezeigten Richtliniendetails auf **Richtlinie bearbeiten.**

Die verfügbaren Einstellungen im fly-out, die angezeigt werden, sind mit denen identisch, die im Abschnitt Verwenden des Security [& Compliance Center](#use-the-security--compliance-center-to-create-safe-attachments-policies) zum Erstellen von Richtlinien für sichere Anlagen beschrieben werden.

Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Richtlinienprioritätsreihenfolge finden Sie in den folgenden Abschnitten.

### <a name="enable-or-disable-safe-attachments-policies"></a>Aktivieren oder Deaktivieren von Richtlinien für sichere Anlagen

1. Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **ATP Sichere Anlagen**.

2. Beachten Sie den Wert in der **Spalte Status:**

   - Verschieben des Umschalters nach links ![Deaktivieren der Richtlinie](../../media/scc-toggle-off.png) , um die Richtlinie zu deaktivieren.

   - Verschieben des Umschalters nach rechts ![Aktivieren der Richtlinie](../../media/scc-toggle-on.png) , um die Richtlinie zu aktivieren.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Festlegen der Priorität von Richtlinien für sichere Anlagen

Standardmäßig erhalten Richtlinien für sichere Anlagen eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

Richtlinien für sichere Anlagen werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0).

**Hinweis:** Im Security & Compliance Center können Sie die Priorität der Richtlinie für sichere Anlagen nur ändern, nachdem Sie sie erstellt haben. In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Regel für sichere Anlagen erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).

Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).

1. Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **ATP Sichere Anlagen**.

2. Wählen Sie **auf** der Seite Sichere Anlagen eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

3. Klicken Sie in den angezeigten Richtliniendetails auf die Schaltfläche verfügbare Priorität.

   - Die Richtlinie Für sichere Anlagen mit dem **Prioritätswert** **0** ist nur die Schaltfläche Priorität **verringern** verfügbar.

   - Die Richtlinie für sichere Anlagen mit dem niedrigsten **Prioritätswert** (z. B. **3**) verfügt nur über die **Schaltfläche Priorität erhöhen.**

   - Wenn Sie über drei oder mehr Richtlinien für sichere Anlagen verfügen, stehen Richtlinien zwischen den höchsten und niedrigsten Prioritätswerten sowohl die Schaltflächen **Priorität** erhöhen als auch **Priorität verringern** zur Verfügung.

4. Klicken **Sie auf Priorität erhöhen** oder Priorität **verringern,** um den **Prioritätswert zu** ändern.

5. Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>Verwenden des Security & Compliance Center zum Entfernen von Richtlinien für sichere Anlagen

1. Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **ATP Sichere Anlagen**.

2. Wählen Sie **auf** der Seite Sichere Anlagen eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

3. Klicken Sie in den angezeigten Richtliniendetails auf Richtlinie **löschen,** und klicken Sie **dann** im angezeigten Warndialogfeld auf Ja.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Konfigurieren von Richtlinien für sichere Anlagen mithilfe von Exchange Online PowerShell oder eigenständiger EOP PowerShell

Wie bereits beschrieben, besteht eine Richtlinie für sichere Anlagen aus einer sicheren Anlagenrichtlinie und einer sicheren Anlagenregel.

In PowerShell ist der Unterschied zwischen sicheren Anlagenrichtlinien und regeln für sichere Anlagen offensichtlich. Sie verwalten sichere Anlagenrichtlinien mithilfe der **\* -SafeAttachmentPolicy-Cmdlets,** und Sie verwalten sichere Anlagenregeln mithilfe der **\* -SafeAttachmentRule-Cmdlets.**

- In PowerShell erstellen Sie zuerst die Richtlinie für sichere Anlagen und dann die Regel für sichere Anlagen, die die Richtlinie identifiziert, auf die die Regel angewendet wird.
- In PowerShell ändern Sie die Einstellungen in der Richtlinie für sichere Anlagen und die Regel für sichere Anlagen separat.
- Wenn Sie eine richtlinie für sichere Anlagen aus PowerShell entfernen, wird die entsprechende Regel für sichere Anlagen nicht automatisch entfernt und umgekehrt.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Erstellen von Richtlinien für sichere Anlagen mithilfe von PowerShell

Das Erstellen einer Richtlinie für sichere Anlagen in PowerShell besteht aus zwei Stufen:

1. Erstellen Sie die Richtlinie für sichere Anlagen.
2. Erstellen Sie die Regel für sichere Anlagen, die die richtlinie für sichere Anlagen angibt, auf die die Regel angewendet wird.

 **Hinweise**:

- Sie können eine neue Regel für sichere Anlagen erstellen und ihr eine vorhandene, nicht zugeordnete richtlinie für sichere Anlagen zuweisen. Eine sichere Anlagenregel kann nicht mehr als einer sicheren Anlagenrichtlinie zugeordnet werden.

- Sie können die folgenden Einstellungen für neue Richtlinien für sichere Anlagen in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:
  - Erstellen Sie die neue Richtlinie als deaktiviert (_Aktiviert_ `$false` im Cmdlet **New-SafeAttachmentRule).**
  - Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) im Cmdlet **New-SafeAttachmentRule.**

- Eine neue richtlinie für sichere Anlagen, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Regel für sichere Anlagen zuweisen.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Schritt 1: Erstellen einer sicheren Anlagenrichtlinie mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um eine sichere Anlagenrichtlinie zu erstellen:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

In diesem Beispiel wird eine sichere Anlagenrichtlinie namens Contoso All mit den folgenden Werten erstellt:

- Blockieren von Nachrichten, die bei der Überprüfung sicherer Dokumente Schadsoftware enthalten (wir verwenden den _Action-Parameter_ nicht, und der Standardwert ist `Block` ).
- Die Umleitung ist aktiviert, und Nachrichten, die Schadsoftware enthalten, werden an sec-ops@contoso.com Analyse und Untersuchung gesendet.
- Wenn die Überprüfung sicherer Anlagen nicht verfügbar ist oder Fehler auftreten, senden Sie die Nachricht nicht (wir verwenden den _ActionOnError-Parameter_ nicht, und der Standardwert ist `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Schritt 2: Erstellen einer sicheren Anlagenregel mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel zu erstellen:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In diesem Beispiel wird eine sichere Anlagenregel namens Contoso All mit den folgenden Bedingungen erstellt:

- Die Regel ist der Richtlinie für sichere Anlagen namens Contoso All zugeordnet.
- Die Regel gilt für alle Empfänger in der contoso.com Domäne.
- Da wir den Parameter _Priority_ nicht verwenden, wird die Standardpriorität verwendet.
- Die Regel ist aktiviert (der Parameter _Enabled_ wird nicht verwendet, und der Standardwert ist `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Anzeigen sicherer Anlagenrichtlinien mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Anlagen anzeigen zu können:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Richtlinien für sichere Anlagen zurückgegeben.

```PowerShell
Get-SafeAttachmentPolicy
```

In diesem Beispiel werden detaillierte Informationen für die Richtlinie für sichere Anlagen namens Contoso Executives zurückgegeben.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).

### <a name="use-powershell-to-view-safe-attachment-rules"></a>Anzeigen sicherer Anlagenregeln mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um vorhandene regeln für sichere Anlagen anzeigen zu können:

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller regeln für sichere Anlagen zurückgegeben.

```PowerShell
Get-SafeAttachmentRule
```

Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Anlagen namens Contoso Executives zurückgegeben.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Verwenden von PowerShell zum Ändern sicherer Anlagenrichtlinien

Sie können eine sichere Anlagenrichtlinie in PowerShell nicht umbenennen (das **Cmdlet Set-SafeAttachmentPolicy** hat keinen _Name-Parameter)._ Wenn Sie eine Richtlinie für sichere Anlagen im Security & Compliance Center umbenennen, benennen Sie nur die Regel für sichere Anlagen _um._

Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine sichere Anlagenrichtlinie erstellen, wie im Abschnitt [Schritt 1:](#step-1-use-powershell-to-create-a-safe-attachment-policy) Verwenden von PowerShell beschrieben, um eine sichere Anlagenrichtlinie weiter oben in diesem Artikel zu erstellen.

Verwenden Sie die folgende Syntax, um eine richtlinie für sichere Anlagen zu ändern:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Verwenden von PowerShell zum Ändern sicherer Anlagenregeln

Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine sichere Anlagenregel in PowerShell ändern, ist der _Parameter Enabled,_ mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Anlagen finden Sie im nächsten Abschnitt.

Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine Regel wie im Abschnitt [Schritt 2:](#step-2-use-powershell-to-create-a-safe-attachment-rule) Verwenden von PowerShell beschrieben erstellen, um eine sichere Anlagenregel weiter oben in diesem Artikel zu erstellen.

Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel zu ändern:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Aktivieren oder Deaktivieren sicherer Anlagenregeln mithilfe von PowerShell

Durch Aktivieren oder Deaktivieren einer Regel für sichere Anlagen in PowerShell wird die gesamte Richtlinie für sichere Anlagen (die Regel für sichere Anlagen und die zugewiesene Richtlinie für sichere Anlagen) aktiviert oder deaktiviert.

Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die Regel für sichere Anlagen mit dem Namen Marketing Department deaktiviert.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) und [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>Festlegen der Priorität sicherer Anlagenregeln mithilfe von PowerShell

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie die folgende Syntax, um die Priorität einer sicheren Anlagenregel in PowerShell zu setzen:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Hinweis**: Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den _Parameter Priority_ im Cmdlet **New-SafeAttachmentRule.**

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>Verwenden von PowerShell zum Entfernen sicherer Anlagenrichtlinien

Wenn Sie PowerShell verwenden, um eine sichere Anlagenrichtlinie zu entfernen, wird die entsprechende Regel für sichere Anlagen nicht entfernt.

Verwenden Sie die folgende Syntax, um eine sichere Anlagenrichtlinie in PowerShell zu entfernen:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Richtlinie für sichere Anlagen mit dem Namen Marketing Department entfernt.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>Verwenden von PowerShell zum Entfernen sicherer Anlagenregeln

Wenn Sie PowerShell verwenden, um eine sichere Anlagenregel zu entfernen, wird die entsprechende Richtlinie für sichere Anlagen nicht entfernt.

Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel in PowerShell zu entfernen:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die Regel für sichere Anlagen mit dem Namen Marketing Department entfernt.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Gehen Sie wie folgt vor, um zu überprüfen, ob Richtlinien für sichere Anlagen erfolgreich erstellt, geändert oder entfernt wurden:

- Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **ATP Sichere Anlagen**. Überprüfen Sie die Liste der Richtlinien, ihre **Statuswerte** und ihre **Priority-Werte.** Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Fly-Out an.

- Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie \<Name\> die Einstellungen:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Überprüfen Sie die verfügbaren Defender for Office 365-Berichte, um zu überprüfen, ob nachrichtensichere Anlagen überprüft werden. Weitere Informationen finden Sie unter Anzeigen von Berichten [für Defender für Office 365](view-reports-for-atp.md) und Verwenden von Explorer im Security & Compliance [Center](threat-explorer.md).