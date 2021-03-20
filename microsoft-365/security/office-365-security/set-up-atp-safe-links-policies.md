---
title: Einrichten von Richtlinien für sichere Links in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Administratoren erfahren, wie Sie Richtlinien für sichere Links und globale Sichere Links in Microsoft Defender für Office 365 anzeigen, erstellen, ändern und löschen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d23815ab0e6d4c9d98db41695b5dacec4c7a6d5a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918702"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Einrichten von Richtlinien für sichere Links in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](office-365-atp.md) verfügen. Informationen zu Safelinks in Outlook finden Sie unter [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Sichere Links ist ein Feature in [Microsoft Defender für Office 365,](office-365-atp.md) das die URL-Überprüfung eingehender E-Mail-Nachrichten im E-Mail-Fluss sowie die Zeit der Klicküberprüfung von URLs und Links in E-Mail-Nachrichten und an anderen Speicherorten ermöglicht. Weitere Informationen finden Sie unter [Sichere Links in Microsoft Defender für Office 365](atp-safe-links.md).

Es gibt keine integrierte oder standardmäßige Richtlinie für sichere Links. Um die Überprüfung von URLs für sichere Links zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere Links erstellen, wie in diesem Artikel beschrieben.

> [!NOTE]
> Sie konfigurieren die globalen Einstellungen für den Schutz sicherer Links **außerhalb** von Richtlinien für sichere Links. Anweisungen finden Sie unter [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).

Sie können Richtlinien für sichere Links im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständiges EOP PowerShell für Organisationen ohne Exchange &, aber mit Microsoft Defender für Office 365-Add-On-Abonnements) konfigurieren.

Die grundlegenden Elemente einer Richtlinie für sichere Links sind:

- Die Richtlinie für sichere **Links:** Aktivieren Sie den Schutz für sichere Links, aktivieren Sie die Echtzeit-URL-Überprüfung, geben Sie an, ob die Echtzeitprüfung abgeschlossen ist, bevor die Nachricht gesendet wird, aktivieren Sie die Überprüfung auf interne Nachrichten, geben Sie an, ob Benutzerklicks auf URLs nachverfolgt werden sollen, und geben Sie an, ob Benutzer auf die ursprüngliche URL klicken dürfen.
- **Die Regel für sichere Links**: Gibt die Prioritäts- und Empfängerfilter an (auf wen die Richtlinie angewendet wird).

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für sichere Links im Security & Compliance Center verwalten:

- Wenn Sie eine Richtlinie für sichere Links erstellen, erstellen Sie tatsächlich eine Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit demselben Namen für beide.
- Wenn Sie eine Richtlinie für sichere Links ändern, ändern Einstellungen im Zusammenhang mit name, priority, enabled oder disabled und Empfängerfiltern die Regel für sichere Links. Alle anderen Einstellungen ändern die zugeordnete Richtlinie für sichere Links.
- Wenn Sie eine Richtlinie für sichere Links entfernen, werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links entfernt.

In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt. Weitere Informationen finden Sie im Abschnitt Verwenden von [Exchange Online PowerShell oder eigenständiger EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) zum Konfigurieren von Richtlinien für sichere Links weiter unten in diesem Artikel.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **"Sichere Links" zu** wechseln, verwenden Sie <https://protection.office.com/safelinksv2> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden:
  - Zum Erstellen, Ändern und Löschen von Richtlinien für sichere  Links müssen  Sie Mitglied der Rollengruppen Organisationsverwaltung oder Sicherheitsadministrator  im Security & Compliance **Center** und Mitglied der Rollengruppe Organisationsverwaltung in Exchange Online sein.
  - Für den schreibgeschützten Zugriff auf Richtlinien für sichere Links müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.

  Weitere Informationen finden Sie unter [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and Permissions in Exchange [Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > 
  > - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  . – Die **Rollengruppe "Nur-Ansichtsorganisationsverwaltung"** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) bietet auch schreibgeschützten Zugriff auf das Feature.

- Unsere empfohlenen Einstellungen für Richtlinien für sichere Links finden Sie unter [Richtlinieneinstellungen](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)für sichere Links .

- Es ist bis zu 30 Minuten zulässig, bis eine neue oder aktualisierte Richtlinie angewendet wird.

- [Microsoft Defender für Office 365 werden](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)ständig neue Features hinzugefügt. Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren vorhandenen Richtlinien für sichere Links vornehmen.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für sichere Links

Beim Erstellen einer benutzerdefinierten Richtlinie für sichere Links im Security & Compliance Center werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit demselben Namen für beide erstellt.

1. Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP Safe Links**.

2. Klicken Sie auf der Seite **Sichere Links** auf **Erstellen**.

3. Der **Richtlinien-Assistent für neue sichere** Links wird geöffnet. Konfigurieren Sie **auf der Seite** Ihre Richtlinie benennen die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.

   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Konfigurieren Sie **auf** der angezeigten Seite Einstellungen die folgenden Einstellungen:

   - **Wählen Sie die Aktion für unbekannte potenziell** schädliche URLs in Nachrichten aus: Wählen Sie **Ein** aus, um den Schutz sicherer Links für Links in E-Mail-Nachrichten zu aktivieren.

   - **Wählen Sie die Aktion für unbekannte oder potenziell** schädliche URLs in Microsoft Teams aus: Wählen Sie **Ein** aus, um den Schutz sicherer Links für Links in Teams zu aktivieren.

   - **Anwenden der Echtzeit-URL-Überprüfung** auf verdächtige Links und Links, die auf Dateien verweisen: Wählen Sie diese Einstellung aus, um die Echtzeitprüfung von Links in E-Mail-Nachrichten zu aktivieren.

   - **Warten Sie, bis die URL-Überprüfung** abgeschlossen ist, bevor sie die Nachricht zustellt: Wählen Sie diese Einstellung aus, um auf den Abschluss der Echtzeit-URL-Überprüfung zu warten, bevor sie die Nachricht zustellt.

   - **Anwenden sicherer Links** auf E-Mail-Nachrichten, die innerhalb der Organisation gesendet werden: Wählen Sie diese Einstellung aus, um die Richtlinie für sichere Links auf Nachrichten zwischen internen Absendern und internen Empfängern anzuwenden.

   - **Benutzerklicks nicht nachverfolgen:** Lassen Sie diese Einstellung deaktiviert, damit der Nachverfolgungsbenutzer in E-Mail-Nachrichten auf URLs klickt.

   - **Benutzer dürfen nicht zur** ursprünglichen URL klicken: Wählen Sie diese Einstellung aus, um zu blockieren, dass Benutzer in Warnseiten zur ursprünglichen URL [klicken.](atp-safe-links.md#warning-pages-from-safe-links)

   - **Schreiben Sie die folgenden URLs** nicht neu: Ermöglicht den Zugriff auf die angegebenen URLs, die andernfalls durch sichere Links blockiert würden.

     Geben Sie in das Feld die url oder den wert ein, die Sie möchten, und klicken Sie dann auf ![Schaltflächensymbol hinzufügen](../../media/ITPro-EAC-AddIcon.png).

     Um einen vorhandenen Eintrag zu entfernen, wählen Sie ihn aus, und klicken Sie dann auf ![Schaltflächensymbol löschen](../../media/ITPro-EAC-DeleteIcon.png).

     Eine Eintragssyntax finden Sie [unter Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).

   Ausführliche Informationen zu diesen Einstellungen finden Sie unter [Einstellungen](atp-safe-links.md#safe-links-settings-for-email-messages) für sichere Links für E-Mail-Nachrichten und Einstellungen für sichere [Links für Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).

   Weitere Informationen zu den empfohlenen Werten für Standard- und Strict-Richtlinieneinstellungen finden Sie unter [Richtlinieneinstellungen](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)für sichere Links .

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

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien für sichere Links

1. Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP Safe Links**.

2. Wählen Sie **auf der** Seite Sichere Links eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

   Die Richtliniendetails werden in einem Fly-Out angezeigt.

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Verwenden des Security & Compliance Center zum Ändern von Richtlinien für sichere Links

1. Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP Safe Links**.

2. Wählen Sie **auf der** Seite Sichere Links eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

3. Klicken Sie in den angezeigten Richtliniendetails auf **Richtlinie bearbeiten.**

Die verfügbaren Einstellungen im fly-out, die angezeigt werden, sind mit denen identisch, die im Abschnitt Verwenden des Security [& Compliance Center](#use-the-security--compliance-center-to-create-safe-links-policies) zum Erstellen von Richtlinien für sichere Links beschrieben werden.

Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Richtlinienprioritätsreihenfolge finden Sie in den folgenden Abschnitten.

### <a name="enable-or-disable-safe-links-policies"></a>Aktivieren oder Deaktivieren von Richtlinien für sichere Links

1. Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP Safe Links**.

2. Beachten Sie den Wert in der **Spalte Status:**

   - Schieben Sie die Umschaltfläche nach links, um die Richtlinie zu deaktivieren: ![Deaktivieren der Richtlinie](../../media/scc-toggle-off.png).

   - Schieben Sie die Umschaltfläche nach rechts, um die Richtlinie zu aktivieren: ![Aktivieren der Richtlinie](../../media/scc-toggle-on.png).

### <a name="set-the-priority-of-safe-links-policies"></a>Festlegen der Priorität von Richtlinien für sichere Links

Richtlinien für sichere Links erhalten standardmäßig eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

Richtlinien für sichere Links werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0).

> [!NOTE]
> Im Security & Compliance Center können Sie die Priorität der Richtlinie für sichere Links nur ändern, nachdem Sie sie erstellt haben. In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Regel für sichere Links erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).

Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).

1. Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP Safe Links**.

2. Wählen Sie **auf der** Seite Sichere Links eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

3. Klicken Sie in den angezeigten Richtliniendetails auf die verfügbare Prioritätsschaltfläche:

   - Die Richtlinie für sichere Links mit dem **Prioritätswert** **0** verfügt nur über **die** Schaltfläche Priorität verringern.

   - Die Richtlinie für sichere Links mit dem niedrigsten **Prioritätswert** (z. B. **3**) verfügt nur über die **Schaltfläche Priorität erhöhen.**

   - Wenn Sie über drei oder mehr Richtlinien für sichere Links verfügen, stehen Richtlinien zwischen den höchsten und niedrigsten Prioritätswerten sowohl die Schaltflächen **Priorität** erhöhen als auch **Priorität verringern** zur Verfügung.

4. Klicken **Sie auf Priorität erhöhen** oder Priorität **verringern,** um den **Prioritätswert zu** ändern.

5. Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Verwenden des Security & Compliance Center zum Entfernen von Richtlinien für sichere Links

1. Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP Safe Links**.

2. Wählen Sie **auf der** Seite Sichere Links eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

3. Klicken Sie in den angezeigten Richtliniendetails auf Richtlinie **löschen,** und klicken Sie **dann** im angezeigten Warndialogfeld auf Ja.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Konfigurieren von Richtlinien für sichere Links mithilfe von Exchange Online PowerShell oder eigenständiger EOP PowerShell

Wie bereits beschrieben, besteht eine Richtlinie für sichere Links aus einer Richtlinie für sichere Links und einer Regel für sichere Links.

In PowerShell ist der Unterschied zwischen Richtlinien für sichere Links und Regeln für sichere Links offensichtlich. Sie verwalten Richtlinien für sichere Links mithilfe der **\* -SafeLinksPolicy-Cmdlets,** und Sie verwalten Regeln für sichere Links mithilfe der **\* -SafeLinksRule-Cmdlets.**

- In PowerShell erstellen Sie zuerst die Richtlinie für sichere Links, dann erstellen Sie die Regel für sichere Links, die die Richtlinie identifiziert, auf die die Regel angewendet wird.
- In PowerShell ändern Sie die Einstellungen in der Richtlinie für sichere Links und die Regel für sichere Links separat.
- Wenn Sie eine Richtlinie für sichere Links aus PowerShell entfernen, wird die entsprechende Regel für sichere Links nicht automatisch entfernt und umgekehrt.

### <a name="use-powershell-to-create-safe-links-policies"></a>Erstellen von Richtlinien für sichere Links mithilfe von PowerShell

Das Erstellen einer Richtlinie für sichere Links in PowerShell besteht aus zwei Stufen:

1. Erstellen Sie die Richtlinie für sichere Links.
2. Erstellen Sie die Regel für sichere Links, die die Richtlinie für sichere Links angibt, auf die die Regel angewendet wird.

> [!NOTE]
> 
> - Sie können eine neue Regel für sichere Links erstellen und ihr eine vorhandene Richtlinie für nicht zugeordnete sichere Links zuweisen. Eine Regel für sichere Links kann nicht mehr als einer Richtlinie für sichere Links zugeordnet werden.
> 
> - Sie können die folgenden Einstellungen für neue Richtlinien für sichere Links in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:
> 
>   - Erstellen Sie die neue Richtlinie als deaktiviert (_Aktiviert_ `$false` im Cmdlet **New-SafeLinksRule).**
>   - Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) im Cmdlet **New-SafeLinksRule.**
> 
> - Eine neue Richtlinie für sichere Links, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Regel für sichere Links zuweisen.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Schritt 1: Erstellen einer Richtlinie für sichere Links mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links zu erstellen:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - Details zur Eintragssyntax, die für den _Parameter DoNotRewriteUrls_ verwendet werden soll, finden Sie unter [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).
> 
> - Weitere Syntax, die Sie für den _Parameter DoNotRewriteUrls_ verwenden können, wenn Sie vorhandene Richtlinien für sichere Links mithilfe des **Cmdlets Set-SafeLinksPolicy** ändern, finden Sie im Abschnitt Verwenden von [PowerShell](#use-powershell-to-modify-safe-links-policies) zum Ändern von Richtlinien für sichere Links weiter unten in diesem Artikel.

In diesem Beispiel wird eine Richtlinie für sichere Links namens Contoso All mit den folgenden Werten erstellt:

- Aktivieren Sie die URL-Überprüfung und -Umschreibung in E-Mail-Nachrichten.
- Aktivieren sie die URL-Überprüfung in Teams (nur TAP Preview).
- Aktivieren Sie die Echtzeitprüfung von geklickten URLs, einschließlich geklickter Links, die auf Dateien verweisen.
- Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht senden.
- Aktivieren Sie die URL-Überprüfung und das Umschreiben für interne Nachrichten.
- Nachverfolgen von Benutzerklicks im Zusammenhang mit dem Schutz sicherer Links (wir verwenden den _Parameter DoNotTrackUserClicks_ nicht, und der Standardwert ist $false, d. h. Benutzerklicks werden nachverfolgt).
- Benutzer dürfen nicht zur ursprünglichen URL klicken.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Schritt 2: Erstellen einer Regel für sichere Links mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um eine Regel für sichere Links zu erstellen:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In diesem Beispiel wird eine Regel für sichere Links namens Contoso All mit den folgenden Bedingungen erstellt:

- Die Regel ist der Richtlinie für sichere Links namens Contoso All zugeordnet.
- Die Regel gilt für alle Empfänger in der contoso.com Domäne.
- Da wir den Parameter _Priority_ nicht verwenden, wird die Standardpriorität verwendet.
- Die Regel ist aktiviert (der Parameter _Enabled_ wird nicht verwendet, und der Standardwert ist `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).

### <a name="use-powershell-to-view-safe-links-policies"></a>Anzeigen von Richtlinien für sichere Links mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Links anzeigen zu können:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Richtlinien für sichere Links zurückgegeben.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

In diesem Beispiel werden detaillierte Informationen für die Richtlinie für sichere Links namens Contoso Executives zurückgegeben.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).

### <a name="use-powershell-to-view-safe-links-rules"></a>Anzeigen von Regeln für sichere Links mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um vorhandene Regeln für sichere Links anzeigen zu können:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Regeln für sichere Links zurückgegeben.

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Links namens Contoso Executives zurückgegeben.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).

### <a name="use-powershell-to-modify-safe-links-policies"></a>Verwenden von PowerShell zum Ändern von Richtlinien für sichere Links

Sie können eine Richtlinie für sichere Links in PowerShell nicht umbenennen (das **Cmdlet Set-SafeLinksPolicy** hat keinen _Name-Parameter)._ Wenn Sie eine Richtlinie für sichere Links im Security & Compliance Center umbenennen, benennen Sie nur die Regel für sichere Links _um._

Die einzige zusätzliche Überlegung zum Ändern von Richtlinien für sichere Links in PowerShell ist die verfügbare Syntax für den _DoNotRewriteUrls-Parameter_ (die [Liste "Die](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)folgenden URLs nicht umschreiben"):

- Verwenden Sie die folgende Syntax, um Werte hinzuzufügen, die vorhandene Einträge ersetzen: `"Entry1","Entry2,..."EntryN"` .
- Verwenden Sie die folgende Syntax, um Werte hinzuzufügen oder zu entfernen, ohne sich auf andere vorhandene Einträge zu beeinflussen: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine Richtlinie für sichere Links erstellen, wie im Abschnitt [Schritt 1:](#step-1-use-powershell-to-create-a-safe-links-policy) Verwenden von PowerShell beschrieben, um eine Richtlinie für sichere Links weiter oben in diesem Artikel zu erstellen.

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links zu ändern:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).

### <a name="use-powershell-to-modify-safe-links-rules"></a>Verwenden von PowerShell zum Ändern von Regeln für sichere Links

Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine Regel für sichere Links in PowerShell ändern, ist der _Parameter Enabled,_ mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Links finden Sie im nächsten Abschnitt.

Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine Regel wie im Abschnitt [Schritt 2:](#step-2-use-powershell-to-create-a-safe-links-rule) Verwenden von PowerShell beschrieben erstellen, um eine Regel für sichere Links weiter oben in diesem Artikel zu erstellen.

Verwenden Sie die folgende Syntax, um eine Regel für sichere Links zu ändern:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für sichere Links

Durch Aktivieren oder Deaktivieren einer Regel für sichere Links in PowerShell wird die gesamte Richtlinie für sichere Links (die Regel für sichere Links und die zugewiesene Richtlinie für sichere Links) aktiviert oder deaktiviert.

Verwenden Sie die folgende Syntax, um eine Regel für sichere Links in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die Regel für sichere Links mit dem Namen Marketing Department deaktiviert.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) und [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Festlegen der Priorität von Regeln für sichere Links mithilfe von PowerShell

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie die folgende Syntax, um die Priorität einer Regel für sichere Links in PowerShell zu setzen:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den _Parameter Priority_ im Cmdlet **New-SafeLinksRule.**

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-remove-safe-links-policies"></a>Verwenden von PowerShell zum Entfernen von Richtlinien für sichere Links

Wenn Sie PowerShell verwenden, um eine Richtlinie für sichere Links zu entfernen, wird die entsprechende Regel für sichere Links nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links in PowerShell zu entfernen:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Richtlinie für sichere Links mit dem Namen Marketing Department entfernt.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).

### <a name="use-powershell-to-remove-safe-links-rules"></a>Verwenden von PowerShell zum Entfernen von Regeln für sichere Links

Wenn Sie PowerShell verwenden, um eine Regel für sichere Links zu entfernen, wird die entsprechende Richtlinie für sichere Links nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Regel für sichere Links in PowerShell zu entfernen:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die Regel für sichere Links mit dem Namen Marketing Department entfernt.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).

Überprüfen Sie die verfügbaren Microsoft Defender for Office 365-Berichte, um zu überprüfen, ob nachrichtensichere Links überprüft werden. Weitere Informationen finden Sie unter Anzeigen von Berichten [für Defender für Office 365](view-reports-for-atp.md) und Verwenden von Explorer im Security & Compliance [Center](threat-explorer.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Gehen Sie wie folgt vor, um zu überprüfen, ob Richtlinien für sichere Links erfolgreich erstellt, geändert oder entfernt wurden:

- Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP Safe Links**. Überprüfen Sie die Liste der Richtlinien, ihre **Statuswerte** und ihre **Priority-Werte.** Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Fly-Out an.

- Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie \<Name\> die Einstellungen:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```