---
title: Einrichten von Richtlinien für sichere Anlagen in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie Richtlinien für sichere Anlagen zum Schutz Ihrer Organisation vor bösartigen Dateien in e-Mails definieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca0bfb7ba91f86fee187cfe3445c0dd6c8d4ad56
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845492"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Einrichten von Richtlinien für sichere Anlagen in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die [Microsoft Defender für Office 365](office-365-atp.md)haben. Wenn Sie ein Privatbenutzer sind, der nach Informationen zum Anlagen Scan in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

"Sichere Anlagen" ist ein Feature in [Microsoft Defender für Office 365](office-365-atp.md) , das eine virtuelle Umgebung verwendet, um Anlagen in eingehenden e-Mail-Nachrichten zu überprüfen, nachdem diese durch den [Schutz vor Schadsoftware in Exchange Online Protection (EoP)](anti-malware-protection.md), jedoch vor der Zustellung an die Empfänger überprüft wurden. Weitere Informationen finden Sie unter [sichere Anlagen in Microsoft Defender für Office 365](atp-safe-attachments.md).

Es gibt keine Richtlinie für integrierte oder standardmäßige sichere Anlagen. Wenn Sie sichere Anlagen überprüfen von e-Mail-Nachrichtenanlagen erhalten möchten, müssen Sie eine oder mehrere Richtlinien für sichere Anlagen wie in diesem Artikel beschrieben erstellen.

Sie können Richtlinien für sichere Anlagen im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer, aber mit Defender für Office 365 Add-on-Abonnements) konfigurieren.

Die grundlegenden Elemente einer Richtlinie für sichere Anlagen sind:

- **Richtlinie für sichere Anlagen** : gibt die Aktionen für unbekannte Malwareerkennungen an, ob Nachrichten mit Schadsoftware-Anlagen an eine angegebene e-Mail-Adresse gesendet werden sollen und ob Nachrichten übermittelt werden können, wenn die Überprüfung durch sichere Anlagen nicht abgeschlossen werden kann
- **Die Regel für sichere Anlagen** : gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) an.

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für sichere Anlagen im Security & Compliance Center verwalten:

- Wenn Sie eine Richtlinie für sichere Anlagen erstellen, erstellen Sie tatsächlich eine Regel für sichere Anlagen und die zugehörige Richtlinie für sichere Anlagen gleichzeitig mit dem gleichen Namen für beide.
- Wenn Sie eine Richtlinie für sichere Anlagen ändern, ändern die Einstellungen im Zusammenhang mit dem Namen, der Priorität, den aktivierten oder deaktivierten und den Empfänger filtern die Regel für sichere Anlagen. Alle anderen Einstellungen ändern die zugehörige Richtlinie für sichere Anlagen.
- Wenn Sie eine Richtlinie für sichere Anlagen entfernen, werden die Regel für sichere Anlagen und die zugehörige Richtlinie für sichere Anlagen entfernt.

In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt. Weitere Informationen finden Sie im Abschnitt [Verwenden von Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Konfigurieren von Richtlinien für sichere Anlagen](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) weiter unten in diesem Artikel.

> [!NOTE]
> Im Bereich Globale Einstellungen der Einstellungen für sichere Anlagen konfigurieren Sie Features, die nicht von Richtlinien für sichere Anlagen abhängig sind. Anweisungen finden Sie unter [Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) und [sichere Dokumente in Microsoft 365 E5](safe-docs.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Wenn Sie direkt zur Seite **sichere Anlagen** wechseln möchten, verwenden Sie <https://protection.office.com/safeattachmentv2> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Zum Anzeigen, erstellen, ändern und Löschen von Richtlinien für sichere Anlagen müssen Sie Mitglied einer der folgenden Rollengruppen sein:

  - **Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
  - **Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Unsere empfohlenen Einstellungen für Richtlinien zu sicheren Anlagen finden Sie unter [Safe Attachments Settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

- Erlauben Sie bis zu 30 Minuten, bis eine neue oder aktualisierte Richtlinie angewendet wird.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für sichere Anlagen

Durch das Erstellen einer benutzerdefinierten Richtlinie für sichere Anlagen im Security & Compliance Center werden die Regel für sichere Anlagen und die zugeordnete Richtlinie für sichere Anlagen gleichzeitig mit dem gleichen Namen für beide erstellt.

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.

2. Klicken Sie auf der Seite **sichere Anlagen** auf **Erstellen**.

3. Der Assistent für **neue Richtlinien für sichere Anlagen** wird geöffnet. Konfigurieren Sie auf der Seite **Ihre Richtlinie benennen** die folgenden Einstellungen:

   - **Name** : Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.

   - **Beschreibung** : Geben Sie eine optionale Beschreibung für die Richtlinie ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Konfigurieren Sie auf der angezeigten Seite **Einstellungen** die folgenden Einstellungen:

   - **Sichere Anlagen unbekannte Malware Antwort** : Wählen Sie einen der folgenden Werte aus:

     - **Off** : Normalerweise wird dieser Wert nicht empfohlen.
     - **Überwachen**
     - **Block** : Dies ist der Standardwert und der empfohlene Wert in standardmäßigen und streng [voreingestellten Sicherheitsrichtlinien](preset-security-policies.md).
     - **Replace**
     - **Dynamische Zustellung (Vorschau-Feature)**

     Diese Werte werden unter [Richtlinieneinstellungen für sichere Anlagen](atp-safe-attachments.md#safe-attachments-policy-settings)erläutert.

   - **Senden Sie die Anlage an die folgende e-Mail-Adresse** : für die Aktionswerte **blockieren** , **überwachen** oder **ersetzen** können Sie die Option **Umleitung aktivieren** auswählen, um Nachrichten mit Schadsoftware-Anlagen zur Analyse und Untersuchung an die angegebene interne oder externe e-Mail-Adresse zu senden.

     Die Empfehlung für Standard mäßige und strenge Richtlinieneinstellungen besteht darin, die Umleitung zu aktivieren. Weitere Informationen finden Sie unter [Einstellungen für sichere Anlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

   - **Wenden Sie die obige Auswahl an, wenn bei der Malwareüberprüfung für Anlagen ein Timeout auftritt oder ein Fehler auftritt** : die durch **sichere Anlagen unbekannte Schadsoftware-Antwort** angegebene Aktion wird auf Nachrichten angewendet, auch wenn der sichere Anlagen Scan nicht abgeschlossen werden kann. Wählen Sie diese Option immer aus, wenn Sie **aktivierte Umleitung** auswählen. Andernfalls gehen möglicherweise Nachrichten verloren.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Identifizieren Sie auf der Seite **angewendet auf** , die angezeigt wird, die internen Empfänger, auf die die Richtlinie angewendet wird.

   Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_ ). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_ ).

   Klicken Sie auf **Bedingung hinzufügen**. Wählen Sie in der Dropdownliste, die angezeigt wird, eine Bedingung unter **angewendet, wenn** :

   - **Der Empfänger lautet** : gibt ein oder mehrere Postfächer, e-Mail-Benutzer oder e-Mail-Kontakte in Ihrer Organisation an.
   - **Der Empfänger ist Mitglied von** : gibt eine oder mehrere Gruppen in Ihrer Organisation an.
   - **Die Empfängerdomäne ist** : Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.

   Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **der folgenden** Felder angezeigt.

   - Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der zu markierende Werte durch.
   - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.
   - Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.
   - Wenn Sie einzelne Einträge entfernen möchten **Remove** , klicken Sie auf Entfernen- ![ Symbol ](../../media/scc-remove-icon.png) für den Wert entfernen.
   - Wenn Sie die gesamte Bedingung entfernen möchten **, klicken Sie** ![ in der Bedingung auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) .

   Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen** , und wählen Sie einen verbleibenden Wert unter **angewendet bei** aus.

   Wenn Sie Ausnahmen hinzufügen möchten, klicken Sie auf **Bedingung hinzufügen** , und wählen Sie unter **außer if** eine Ausnahme aus. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

6. Überprüfen Sie auf der angezeigten Seite **Ihre Einstellungen überprüfen** Ihre Einstellungen. Sie können auf jeder Einstellung auf **Bearbeiten** klicken, um Sie zu ändern.

   Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien für sichere Anlagen

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.

2. Wählen Sie auf der Seite **sichere Anlagen** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).

   Die Richtliniendetails werden in einem Fly Out angezeigt.

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>Verwenden des Security & Compliance Center zum Ändern von Richtlinien für sichere Anlagen

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.

2. Wählen Sie auf der Seite **sichere Anlagen** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).

3. Klicken Sie in der angezeigten Richtlinie Details ausfliegen, die angezeigt wird, auf **Richtlinie bearbeiten**.

Die verfügbaren Einstellungen im angezeigten ausfliegen sind mit denen identisch, die im Abschnitt [Verwenden der Sicherheits & Compliance Center zum Erstellen von Richtlinien für sichere Anlagen](#use-the-security--compliance-center-to-create-safe-attachments-policies) beschrieben sind.

Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Reihenfolge der Richtlinien Priorität finden Sie in den folgenden Abschnitten.

### <a name="enable-or-disable-safe-attachments-policies"></a>Aktivieren oder Deaktivieren von Richtlinien für sichere Anlagen

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.

2. Beachten Sie den Wert in der Spalte **Status** :

   - Bewegen der Umschaltfläche nach links ![Deaktivieren der Richtlinie](../../media/scc-toggle-off.png) , um die Richtlinie zu deaktivieren.

   - Bewegen der Umschaltfläche nach rechts ![Richtlinie aktivieren](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) , um die Richtlinie zu aktivieren.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Festlegen der Priorität von Richtlinien für sichere Anlagen

Standardmäßig erhalten Richtlinien für sichere Anlagen eine Priorität, die auf der Reihenfolge basiert, in der Sie erstellt wurden (neuere Policen haben eine niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

Richtlinien für sichere Anlagen werden in der Reihenfolge angezeigt, in der Sie verarbeitet werden (die erste Richtlinie hat den **Prioritäts** Wert 0).

**Hinweis** : im Security & Compliance Center können Sie die Priorität der Richtlinie für sichere Anlagen nur ändern, nachdem Sie Sie erstellt haben. In PowerShell können Sie die Standardpriorität außer Kraft setzen, wenn Sie die Regel für sichere Anlagen erstellen (die sich auf die Priorität vorhandener Regeln auswirken kann).

Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität** -Wert im Security & Compliance Center nicht direkt ändern).

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.

2. Wählen Sie auf der Seite **sichere Anlagen** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).

3. Klicken Sie im daraufhin angezeigten Richtliniendetails-Steuerelement auf die Schaltfläche verfügbare Priorität.

   - Für die Richtlinie für sichere Anlagen mit dem **Prioritäts** Wert **0** ist nur die Schaltfläche **Priorität verringern** verfügbar.

   - Die Richtlinie für sichere Anlagen mit dem niedrigsten **Prioritäts** Wert (beispielsweise **3** ) verfügt nur über die Schaltfläche **Priorität verlängern** .

   - Wenn Sie drei oder mehr Richtlinien für sichere Anlagen haben, haben Richtlinien zwischen den Werten der höchsten und der niedrigsten Priorität **sowohl die Prioritätsschaltflächen "Priorität"** als auch " **Priorität verringern** " zur Verfügung.

4. Klicken Sie auf Priorität Verb **Essern** oder **Priorität verringern** , um den **Prioritäts** Wert zu ändern.

5. Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>Verwenden des Security & Compliance Center zum Entfernen von Richtlinien für sichere Anlagen

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.

2. Wählen Sie auf der Seite **sichere Anlagen** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).

3. Klicken Sie im daraufhin angezeigten Richtliniendetails-Steuerelement auf **Richtlinie löschen** , und klicken Sie dann im angezeigten Warndialogfeld auf **Ja** .

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Verwenden von Exchange Online PowerShell oder eigenständigen EoP PowerShell zum Konfigurieren von Richtlinien für sichere Anlagen

Wie bereits beschrieben, besteht eine Richtlinie für sichere Anlagen aus einer Richtlinie zu sicheren Anlagen und einer Regel für sichere Anlagen.

In PowerShell ist der Unterschied zwischen Richtlinien für sichere Anlagen und Regeln für sichere Anlagen offensichtlich. Sie verwalten Richtlinien für sichere Anlagen mithilfe der **\* -SafeAttachmentPolicy-** Cmdlets und verwalten sichere Anlagenregeln mithilfe der **\* -SafeAttachmentRule-** Cmdlets.

- In PowerShell erstellen Sie zuerst die Richtlinie für sichere Anlagen, dann erstellen Sie die Regel für sichere Anlagen, die die Richtlinie identifiziert, auf die die Regel angewendet wird.
- In PowerShell ändern Sie die Einstellungen in der Richtlinie zu sicheren Anlagen und der Regel für die sichere Anlage separat.
- Wenn Sie eine Richtlinie für sichere Anlagen aus PowerShell entfernen, wird die entsprechende Regel für sichere Anlagen nicht automatisch entfernt und umgekehrt.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Verwenden von PowerShell zum Erstellen von Richtlinien für sichere Anlagen

Das Erstellen einer Richtlinie für sichere Anlagen in PowerShell ist ein zweistufiger Prozess:

1. Erstellen Sie die Richtlinie für sichere Anlagen.
2. Erstellen Sie die Regel für sichere Anlagen, die die Richtlinie für sichere Anlagen angibt, auf die die Regel angewendet wird.

 **Hinweise** :

- Sie können eine neue Regel für sichere Anlagen erstellen und ihr eine vorhandene, nicht zugeordnete Richtlinie für sichere Anlagen zuweisen. Eine Regel für sichere Anlagen kann nicht mehr als einer Richtlinie für sichere Anlagen zugeordnet werden.

- Sie können die folgenden Einstellungen für neue Richtlinien für sichere Anlagen in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Security & Compliance Center verfügbar sind:
  - Erstellen Sie die neue Richtlinie als deaktiviert ( _aktiviert_ im `$false` Cmdlet **New-SafeAttachmentRule** ).
  - Legen Sie die Priorität der Richtlinie während der Erstellung ( _Priorität_ _\<Number\>_ ) für das Cmdlet **New-SafeAttachmentRule** fest).

- Eine neue Richtlinie für sichere Anlagen, die Sie in PowerShell erstellen, ist erst im Security & Compliance Center sichtbar, wenn Sie die Richtlinie einer sicheren Anlage Regel zuweisen.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Schritt 1: Erstellen einer Richtlinie für sichere Anlagen mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Anlagen zu erstellen:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

In diesem Beispiel wird eine Richtlinie für sichere Anlagennamens "Contoso all" mit den folgenden Werten erstellt:

- Blockieren von Nachrichten, die festgestellt werden, dass Malware durch Scannen sicherer Dokumente enthalten ist (der Parameter _Action_ wird nicht verwendet, und der Standardwert ist `Block` ).
- Die Umleitung ist aktiviert, und Nachrichten, die Schadsoftware enthalten, werden zur Analyse und Untersuchung an sec-OPS@contoso.com gesendet.
- Wenn das Scannen sicherer Anlagen nicht verfügbar ist oder Fehler auftritt, übermittelt die Nachricht nicht (wir verwenden den Parameter _ActionOnError_ nicht, und der Standardwert ist `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel für sichere Anlagen

Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel zu erstellen:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In diesem Beispiel wird eine sichere Anlagenregel namens "Contoso all" mit den folgenden Bedingungen erstellt:

- Die Regel ist mit der Richtlinie für sichere Anlagennamens "Contoso all" verknüpft.
- Die Regel gilt für alle Empfänger in der contoso.com-Domäne.
- Da wir den _Priority_ -Parameter nicht verwenden, wird die Standardpriorität verwendet.
- Die Regel ist aktiviert (der Parameter _Enabled_ wird nicht verwendet, und der Standardwert ist `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Verwenden von PowerShell zum Anzeigen von Richtlinien für sichere Anlagen

Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Anlagen anzuzeigen:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Richtlinien für sichere Anlagen zurückgegeben.

```PowerShell
Get-SafeAttachmentPolicy
```

In diesem Beispiel werden detaillierte Informationen für die Richtlinie für sichere Anlagennamens "Contoso Executives" zurückgegeben.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).

### <a name="use-powershell-to-view-safe-attachment-rules"></a>Verwenden von PowerShell zum Anzeigen von Regeln für sichere Anlagen

Verwenden Sie die folgende Syntax, um vorhandene Regeln für sichere Anlagen anzuzeigen:

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Regeln für sichere Anlagen zurückgegeben.

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

In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Anlagennamens "Contoso Executives" zurückgegeben.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Verwenden von PowerShell zum Ändern von Richtlinien für sichere Anlagen

Sie können keine Richtlinie für sichere Anlagen in PowerShell umbenennen (das Cmdlet " **setSafeAttachmentPolicy** " verfügt über keinen Parameter " _Name_ "). Wenn Sie eine Richtlinie für sichere Anlagen im Security & Compliance Center umbenennen, benennen Sie die _Regel_ für sichere Anlagen nur um.

Andernfalls stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Richtlinie zu sicheren Anlagen erstellen, wie im Abschnitt [Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie zu sicheren Anlagen](#step-1-use-powershell-to-create-a-safe-attachment-policy) weiter oben in diesem Artikel beschrieben.

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Anlagen zu ändern:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Verwenden von PowerShell zum Ändern von Regeln für sichere Anlagen

Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine sichere Anlagenregel in PowerShell ändern, ist der Parameter _Enabled_ , mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Anlagen finden Sie im nächsten Abschnitt.

Andernfalls stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen einer Richtlinie zu sicheren Anlagen](#step-2-use-powershell-to-create-a-safe-attachment-rule) weiter oben in diesem Artikel beschrieben.

Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel zu ändern:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für sichere Anlagen

Das Aktivieren oder Deaktivieren einer Regel für sichere Anlagen in PowerShell aktiviert oder deaktiviert die gesamte Richtlinie für sichere Anlagen (die sichere Anlage Regel und die zugewiesene Richtlinie für sichere Anlagen).

Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die Richtlinie für sichere Anlagennamens "Marketing Department" deaktiviert.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) und [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>Verwenden von PowerShell zum Festlegen der Priorität von Regeln für sichere Anlagen

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie die folgende Syntax, um die Priorität einer Regel für sichere Anlagen in PowerShell festzulegen:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Hinweis** : Wenn Sie die Priorität einer neuen Regel beim Erstellen festlegen möchten, verwenden Sie stattdessen den Parameter _Priority_ für das Cmdlet **New-SafeAttachmentRule** .

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>Verwenden von PowerShell zum Entfernen von Richtlinien für sichere Anlagen

Wenn Sie mithilfe von PowerShell eine Richtlinie für sichere Anlagen entfernen, wird die entsprechende Regel für sichere Anlagen nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Anlagen in PowerShell zu entfernen:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Richtlinie für sichere Anlagennamens "Marketing Department" entfernt.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>Verwenden von PowerShell zum Entfernen von Regeln für sichere Anlagen

Wenn Sie mithilfe von PowerShell eine Regel für sichere Anlagen entfernen, wird die entsprechende Richtlinie für sichere Anlagen nicht entfernt.

Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel in PowerShell zu entfernen:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die Regel für sichere Anlagennamens "Marketing Department" entfernt.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Richtlinien für sichere Anlagen erfolgreich erstellt, geändert oder entfernt haben:

- Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**. Überprüfen Sie die Liste der Richtlinien, deren **Status** Werte und deren **Prioritäts** Werte. Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im verfliegt an.

- Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Um zu überprüfen, ob sichere Anlagen Nachrichten scannen, überprüfen Sie den verfügbaren Defender für Office 365 Berichte. Weitere Informationen finden Sie unter [Anzeigen von Berichten für Defender für Office 365](view-reports-for-atp.md) und [Verwenden von Explorer im Security & Compliance Center](threat-explorer.md).
