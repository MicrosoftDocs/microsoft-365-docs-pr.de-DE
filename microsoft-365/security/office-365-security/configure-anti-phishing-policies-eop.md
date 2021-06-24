---
title: Konfigurieren von Anti-Phishing-Richtlinien in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie die Antiphishingrichtlinien erstellen, ändern und löschen, die in Exchange Online Protection (EOP)-Organisationen mit oder ohne Exchange Online Postfächern verfügbar sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e56e1b5d91b74d2ffcf9cccc897962b915c6e83c
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108067"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Konfigurieren von Anti-Phishing-Richtlinien in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)

In Microsoft 365 Organisationen mit Postfächern in Exchange Online- oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer gibt es eine Standardmäßige Antiphishingrichtlinie, die eine begrenzte Anzahl von Antispoofingfunktionen enthält, die standardmäßig aktiviert sind. Weitere Informationen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).

Administratoren können die standardmäßige Antiphishingrichtlinie anzeigen, bearbeiten und konfigurieren (aber nicht löschen). Für eine höhere Granularität können Sie auch benutzerdefinierte Antiphishingrichtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten. Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.

Organisationen mit Exchange Online Postfächern können Antiphishingrichtlinien im Microsoft 365 Defender-Portal oder in Exchange Online PowerShell konfigurieren. Eigenständige EOP-Organisationen können nur das Microsoft 365 Defender-Portal verwenden.

Informationen zum Erstellen und Ändern der erweiterten Antiphishingrichtlinien, die in Microsoft Defender für Office 365 verfügbar sind, finden Sie unter [Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365.](configure-mdo-anti-phishing-policies.md)

Die grundlegenden Elemente einer Antiphishingrichtlinie sind:

- **Die Antiphishingrichtlinie:** Gibt die zu aktivierenden oder zu deaktivierenden Phishing-Schutzmaßnahmen und die Aktionen zum Anwenden von Optionen an.
- **Die Antiphishingregel:** Gibt die Prioritäts- und Empfängerfilter (für die die Richtlinie gilt) für eine Antiphishingrichtlinie an.

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Antiphishingrichtlinien im Microsoft 365 Defender Portal verwalten:

- Wenn Sie eine Antiphishingrichtlinie erstellen, erstellen Sie tatsächlich eine Antiphishingregel und die zugehörige Antiphishingrichtlinie gleichzeitig mit demselben Namen für beide.
- Wenn Sie eine Antiphishingrichtlinie ändern, ändern Einstellungen im Zusammenhang mit Dem Namen, Priorität, aktiviert oder deaktiviert und Empfängerfilter die Antiphishingregel. Alle anderen Einstellungen ändern die zugeordnete Antiphishingrichtlinie.
- Wenn Sie eine Antiphishingrichtlinie entfernen, werden die Antiphishingregel und die zugehörige Antiphishingrichtlinie entfernt.

In Exchange Online PowerShell verwalten Sie die Richtlinie und die Regel separat. Weitere Informationen finden Sie im Abschnitt ["Verwenden von Exchange Online PowerShell zum Konfigurieren von Antiphishingrichtlinien"](#use-exchange-online-powershell-to-configure-anti-phishing-policies) weiter unten in diesem Artikel.

Jede Organisation verfügt über eine integrierte Antiphishingrichtlinie namens Office365 AntiPhish Default, die über die folgenden Eigenschaften verfügt:

- Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine Antiphishingregel (Empfängerfilter) zugeordnet ist.
- Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet). Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität.
- Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.

Um die Effektivität des Antiphishingschutzes zu erhöhen, können Sie benutzerdefinierte Antiphishingrichtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>. Um direkt zur **Antiphishingseite** zu wechseln, verwenden Sie <https://security.microsoft.com/antiphishing> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

  Antiphishingrichtlinien können nicht in EOP PowerShell als eigenständige Lösung verwaltet werden.

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen in **Exchange Online** Berechtigungen zugewiesen werden:
  - Um Antiphishingrichtlinien hinzuzufügen, zu ändern und zu löschen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Für den schreibgeschützten Zugriff auf Antiphishingrichtlinien müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweise**:

  - Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **"Organisationsverwaltung nur anzeigen"** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) bietet auch schreibgeschützten Zugriff auf das <sup>\*</sup> Feature.

- Unsere empfohlenen Einstellungen für Antiphishingrichtlinien finden Sie unter [EOP-Antiphishingrichtlinieneinstellungen.](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)

- Es kann bis zu 30 Minuten dauern, bis die aktualisierte Richtlinie angewendet wird.

- Informationen dazu, wo Antiphishingrichtlinien in der Filterpipeline angewendet werden, finden Sie unter [Reihenfolge und Rangfolge des E-Mail-Schutzes.](how-policies-and-protections-are-combined.md)

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a>Verwenden des Microsoft 365 Defender Portals zum Erstellen von Antiphishingrichtlinien

Beim Erstellen einer benutzerdefinierten Antiphishingrichtlinie im Microsoft 365 Defender Portal werden die Antiphishingregel und die zugeordnete Antiphishingrichtlinie gleichzeitig mit demselben Namen für beide erstellt.

1. Wechseln Sie im Microsoft 365 Defender Portal zur Seite "Richtlinien für **E-Mail-& Zusammenarbeit** & Richtlinien für \>  \> **Bedrohungsregeln"** \>  im Abschnitt \> **"Antiphishing".**

2. Klicken Sie auf der **Seite "Antiphishing"** auf ![ das Symbol ](../../media/m365-cc-sc-create-icon.png) **"Erstellen".**

3. Der Richtlinienassistent wird geöffnet. Konfigurieren Sie auf der Seite **"Richtlinienname"** die folgenden Einstellungen:
   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.
   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

4. Auf der dann angezeigten Seite **Benutzer, Gruppen und Domänen** identifizieren Sie die internen Empfänger, für welche die Richtlinie gilt (Empfängerbedingungen):
   - **Benutzer**: Die angegebenen Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.
   - **Gruppen**: Die angegebenen Verteilergruppen, E-Mail-aktivierten Sicherheitsgruppen oder Microsoft 365-Gruppen in Ihrer Organisation.
   - **Domänen**: Alle Empfänger in der angegebenen [akzeptierten Domäne](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in Ihrer Organisation.

   Klicken Sie auf das entsprechende Feld, beginnen Sie mit der Eingabe eines Wertes, und wählen Sie den gewünschten Wert aus den Ergebnissen aus. Wiederholen Sie diesen Vorgang so oft wie nötig. Um einen vorhandenen Wert zu entfernen, klicken Sie auf das ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

   Für Benutzer oder Gruppen können Sie die meisten Bezeichner verwenden (Name, Anzeigename, Alias, E-Mail-Adresse, Kontoname usw.), aber in den Ergebnissen wird der entsprechende Anzeigename angezeigt. Geben Sie für Benutzer einen einzelnen Stern (\*) ein, um alle verfügbaren Werte anzuzeigen.

   Mehreren Werten in der gleichen Bedingung verwenden die „ODER“-Logik (z. B. _\<recipient1\>_ ODER _\<recipient2\>_). Unterschiedlichen Bedingungen verwenden die „UND“-Logik (z. B. _\<recipient1\>_ UND _\<member of group 1\>_).

   - **Ausschließen dieser Benutzer, Gruppen und Domänen**: Um Ausnahmen für die internen Empfänger hinzuzufügen, für welche die Richtlinie gilt (Empfängerausnahmen), wählen Sie diese Option und konfigurieren Sie die Ausnahmen. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

5. Verwenden Sie auf dem angezeigten **Phishingschwellenwert & Angezeigten Schutzseite** das Kontrollkästchen **Spoofintelligenz aktivieren,** um spoofintelligenz zu aktivieren oder zu deaktivieren. Der Standardwert ist aktiviert (ausgewählt), und es wird empfohlen, ihn einzugeben. Sie konfigurieren die Aktion für blockierte gefälschte Nachrichten auf der nächsten Seite.

   Deaktivieren Sie das Kontrollkästchen, um die Spoofintelligenz zu deaktivieren.

   > [!NOTE]
   > Sie müssen den Antispoofingschutz nicht deaktivieren, wenn Ihr MX-Eintrag nicht auf Microsoft 365 verweist. Aktivieren Sie stattdessen die erweiterte Filterung für Connectors. Anweisungen finden Sie unter ["Erweiterte Filterung für Connectors" in Exchange Online.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

6. Konfigurieren Sie auf der angezeigten Seite **Aktionen** die folgenden Einstellungen:
   - **Wenn die Nachricht als Spoofing erkannt wird:** Diese Einstellung ist nur verfügbar, wenn Sie **spoofintelligenz** auf der vorherigen Seite aktivieren ausgewählt haben. Wählen Sie eine der folgenden Aktionen in der Dropdownliste für Nachrichten von blockierten gefälschten Absendern aus:
     - **Verschieben der Nachricht in die Junk-E-Mail-Ordner des Empfängers**
     - **Quarantäne der Nachricht**

   - **Sicherheitstipps & Indikatoren:**
     - **Anzeigen des ersten Kontakts Sicherheitstipp:** Weitere Informationen finden Sie unter ["Erster Kontakt Sicherheitstipp."](set-up-anti-phishing-policies.md#first-contact-safety-tip)
     - **Show (?) for unauthenticated senders for spoof:** <sup>\*</sup> Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).
     - **Show "via" tag:** <sup>\*</sup> Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the MAIL **FROM** address.

     Aktivieren Sie das Kontrollkästchen, um eine Einstellung zu aktivieren. Deaktivieren Sie das Kontrollkästchen, um es zu deaktivieren.

     <sup>\*</sup> Diese Einstellung ist nur verfügbar, wenn Sie **spoofintelligenz** auf der vorherigen Seite aktivieren ausgewählt haben. Weitere Informationen finden Sie unter ["Nicht authentifizierter Absender".](set-up-anti-phishing-policies.md#unauthenticated-sender)

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

7. Überprüfen Sie auf der angezeigten Seite **Überprüfung** Ihre Einstellungen. Sie können in jedem Abschnitt **Bearbeiten** auswählen, um die Einstellungen in diesem Abschnitt zu ändern. Alternativ können Sie auf **Zurück** klicken oder die entsprechende Seite im Assistenten auswählen.

   Klicken Sie nach Abschluss des Vorgangs auf **Senden**.

8. Klicken Sie in der angezeigten Bestätigungsseite auf **Fertig**.

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a>Verwenden des Microsoft 365 Defender Portals zum Anzeigen von Antiphishingrichtlinien

1. Wechseln Sie im Microsoft 365 Defender Portal zur Seite "Richtlinien für **E-Mail-& Zusammenarbeit** & Richtlinien für \>  \> **Bedrohungsregeln"** \>  im Abschnitt \> **"Antiphishing".**

2. Auf der **Seite "Antiphishing"** werden die folgenden Eigenschaften in der Liste der Richtlinien angezeigt:

   - **Name**
   - **Status**
   - **Priorität**
   - **Zuletzt geändert**

3. Wenn Sie eine Richtlinie auswählen, indem Sie auf den Namen klicken, werden die Richtlinieneinstellungen in einem Flyout angezeigt.

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a>Verwenden des Microsoft 365 Defender Portals zum Ändern von Antiphishingrichtlinien

1. Wechseln Sie im Microsoft 365 Defender Portal zur Seite "Richtlinien für **E-Mail-& Zusammenarbeit** & Richtlinien für \>  \> **Bedrohungsregeln"** \>  im Abschnitt \> **"Antiphishing".**

2. Wählen Sie auf der **Seite "Antiphishing"** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.

3. Wählen Sie im angezeigten Flyout für die Richtliniendetails in jedem Abschnitt die Option **Bearbeiten** aus, um die Einstellungen innerhalb des Abschnitts zu ändern. Weitere Informationen zu den Einstellungen finden Sie im Abschnitt ["Verwenden des Microsoft 365 Defender Portals zum Erstellen von Antiphishingrichtlinien"](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) weiter oben in diesem Artikel.  

   Für die standardmäßige Antiphishingrichtlinie ist der Abschnitt **"Benutzer", "Gruppen" und "Domänen"** nicht verfügbar (die Richtlinie gilt für alle), und Sie können die Richtlinie nicht umbenennen.

Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Reihenfolge der Richtlinienpriorität finden Sie in den folgenden Abschnitten.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Aktivieren oder Deaktivieren von benutzerdefinierten Antiphishingrichtlinien

Sie können die standardmäßige Antiphishingrichtlinie nicht deaktivieren.

1. Wechseln Sie im Microsoft 365 Defender Portal zur Seite "Richtlinien für **E-Mail-& Zusammenarbeit** & Richtlinien für \>  \> **Bedrohungsregeln"** \>  im Abschnitt \> **"Antiphishing".**

2. Wählen Sie auf der **Seite "Antiphishing"** eine benutzerdefinierte Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.

3. Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie einen der folgenden Werte sehen:
   - **Richtlinie deaktiviert**: Um die Richtlinie zu aktivieren, klicken Sie auf ![Symbol „Aktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivieren**.
   - **Richtlinie aktiviert**: Um die Richtlinie zu deaktivieren, klicken Sie auf ![Symbol „Deaktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Deaktivieren**.

4. Klicken Sie im angezeigten Bestätigungsdialog auf **Aktivieren** oder **Deaktivieren**.

5. Klicken Sie im Flyout der Richtliniendetails auf **Schließen**.

Zurück auf der Richtlinien-Hauptseite wird der Wert **Status** der Richtlinie **Aktiviert** oder **Deaktiviert** sein.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Festlegen der Priorität von benutzerdefinierten Antiphishingrichtlinien

Standardmäßig erhalten Antiphishingrichtlinien eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Um die Priorität einer Richtlinie zu ändern, klicken Sie in den Eigenschaften einer Richtlinie auf **Priorität erhöhen** oder **Priorität verringern** (Sie können den Zahlenwert der **Priorität** im Microsoft 365 Defender-Portal nicht direkt modifizieren). Die Priorität einer Richtlinie zu verändern macht nur Sinn, wenn Sie mehrere Richtlinien haben.

 **Anmerkungen**:

- Im Microsoft 365 Defender Portal können Sie die Priorität der Antiphishingrichtlinie erst ändern, nachdem Sie sie erstellt haben. In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Antiphishingregel erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).
- Antiphishingrichtlinien werden in der Reihenfolge verarbeitet, in der sie angezeigt werden (die erste Richtlinie hat den **Prioritätswert** 0). Die Standardmäßige Antiphishingrichtlinie hat den Prioritätswert **Niedrigste**, und Sie können sie nicht ändern.

1. Wechseln Sie im Microsoft 365 Defender Portal zur Seite "Richtlinien für **E-Mail-& Zusammenarbeit** & Richtlinien für \>  \> **Bedrohungsregeln"** \>  im Abschnitt \> **"Antiphishing".**

2. Wählen Sie auf der **Seite "Antiphishing"** eine benutzerdefinierte Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.

3. Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie **Priorität erhöhen** oder **Priorität verringern** sehen, abhängig vom aktuellen Prioritätswert und der Anzahl der benutzerdefinierten Richtlinien:
   - Für die Richtlinie mit dem **Prioritätswert** **0** ist nur die Option **"Priorität verringern"** verfügbar.
   - Für die Richtlinie mit dem niedrigsten **Prioritätswert** (z. B. **3)** ist nur die Option **"Priorität erhöhen"** verfügbar.
   - Wenn Sie über drei oder mehr Richtlinien verfügen, stehen für die Richtlinien zwischen den Werten mit der höchsten und der niedrigsten Priorität die Optionen **"Priorität erhöhen"** und **"Verringern"** zur Verfügung.

   Klicken Sie auf ![Symbol „Priorität erhöhen“](../../media/m365-cc-sc-increase-icon.png) **Priorität erhöhen** oder ![Symbol „Priorität verringern“](../../media/m365-cc-sc-decrease-icon.png) **Priorität verringern**, um den **Prioritätswert** zu ändern.

4. Wenn Sie den Vorgang abgeschlossen haben, klicken Sie im Flyout der Richtliniendetails auf **Schließen**.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a>Verwenden des Microsoft 365 Defender Portals zum Entfernen benutzerdefinierter Antiphishingrichtlinien

Wenn Sie das Microsoft 365 Defender Portal verwenden, um eine benutzerdefinierte Antiphishingrichtlinie zu entfernen, werden die Antiphishingregel und die entsprechende Antiphishingrichtlinie gelöscht. Sie können die standardmäßige Antiphishingrichtlinie nicht entfernen.

1. Wechseln Sie im Microsoft 365 Defender Portal zur Seite "Richtlinien für **E-Mail-& Zusammenarbeit** & Richtlinien für \>  \> **Bedrohungsregeln"** \>  im Abschnitt \> **"Antiphishing".**

2. Wählen Sie auf der **Seite "Antiphishing"** eine benutzerdefinierte Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.

3. Ganz oben auf dem angezeigten Flyout der Richtliniendetails klicken Sie auf ![Symbol „Weiter Aktionen“](../../media/m365-cc-sc-more-actions-icon.png) **Weitere Aktionen** \> ![Symbol „Richtlinie löschen“](../../media/m365-cc-sc-delete-icon.png) **Richtlinie löschen**.

4. Klicken Sie im angezeigten Bestätigungsdialog auf **Ja**.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies&quot;></a>Verwenden von Exchange Online PowerShell zum Konfigurieren von Antiphishingrichtlinien

Wie zuvor beschrieben besteht eine Antiphishingrichtlinie aus einer Antiphishingrichtlinie und einer Antiphishingregel.

In Exchange Online PowerShell ist der Unterschied zwischen Antiphishingrichtlinien und Antiphishingregeln offensichtlich. Sie verwalten Antiphishingrichtlinien mithilfe der **\* -AntiPhishPolicy-Cmdlets,** und Sie verwalten Antiphishingregeln mithilfe der **\* -AntiPhishRule-Cmdlets.**

- In PowerShell erstellen Sie zuerst die Antiphishingrichtlinie und dann die Antiphishingregel, die die Richtlinie identifiziert, für die die Regel gilt.
- In PowerShell ändern Sie die Einstellungen in der Antiphishingrichtlinie und der Antiphishingregel separat.
- Wenn Sie eine Antiphishingrichtlinie aus PowerShell entfernen, wird die entsprechende Antiphishingregel nicht automatisch entfernt und umgekehrt.

> [!NOTE]
> Die folgenden PowerShell-Verfahren sind in eigenständigen EOP-Organisationen, die Exchange Online Protection PowerShell verwenden, nicht verfügbar.

### <a name=&quot;use-powershell-to-create-anti-phishing-policies&quot;></a>Verwenden von PowerShell zum Erstellen von Antiphishingrichtlinien

Das Erstellen einer Antiphishingrichtlinie in PowerShell besteht aus zwei Schritten:

1. Erstellen Sie die Antiphishingrichtlinie.
2. Erstellen Sie die Antiphishingregel, die die Antiphishingrichtlinie angibt, auf die die Regel angewendet wird.

 **Hinweise**:

- Sie können eine neue Antiphishingregel erstellen und ihr eine vorhandene, nicht zugeordnete Antiphishingrichtlinie zuweisen. Eine Antiphishingregel kann nicht mehr als einer Antiphishingrichtlinie zugeordnet werden.

- Sie können die folgenden Einstellungen für neue Antiphishingrichtlinien in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Microsoft 365 Defender Portal verfügbar sind:

  - Erstellen Sie die neue Richtlinie als deaktiviert _(aktiviert_ `$false` im Cmdlet **&quot;New-AntiPhishRule").**
  - Legen Sie die Priorität der Richtlinie während der Erstellung _(Priorität)_ _\<Number\>_ im Cmdlet **"New-AntiPhishRule"** fest.

- Eine neue Antiphishingrichtlinie, die Sie in PowerShell erstellen, ist erst im Microsoft 365 Defender-Portal sichtbar, wenn Sie die Richtlinie einer Antiphishingregel zuweisen.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Schritt 1: Verwenden von PowerShell zum Erstellen einer Antiphishingrichtlinie

Verwenden Sie die folgende Syntax, um eine Antiphishingrichtlinie zu erstellen:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

In diesem Beispiel wird eine Antiphishingrichtlinie namens Research Quarantine mit den folgenden Einstellungen erstellt:

- Die Beschreibung lautet: Abteilungsrichtlinie für Die Forschung.
- Ändert die Standardaktion für Spoofing in Quarantäne.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Schritt 2: Verwenden von PowerShell zum Erstellen einer Antiphishingregel

Verwenden Sie diese Syntax, um eine Antiphishingregel zu erstellen:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In diesem Beispiel wird eine Antiphishingregel namens Research Department mit den folgenden Bedingungen erstellt:

- Die Regel ist der Antiphishingrichtlinie namens Research Quarantine zugeordnet.
- Die Regel gilt für Mitglieder der Gruppe „Research Department“.
- Da der Parameter _"Priority"_ nicht verwendet wird, wird die Standardpriorität verwendet.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).

### <a name="use-powershell-to-view-anti-phish-policies"></a>Verwenden von PowerShell zum Anzeigen von Antiphishingrichtlinien

Verwenden Sie die folgende Syntax, um vorhandene Antiphishingrichtlinien anzuzeigen:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Antiphishingrichtlinien zusammen mit den angegebenen Eigenschaften zurückgegeben.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

In diesem Beispiel werden alle Eigenschaftswerte für die Antiphishingrichtlinie Executives zurückgegeben.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-AntiPhishPolicy".](/powershell/module/exchange/Get-AntiPhishPolicy)

### <a name="use-powershell-to-view-anti-phish-rules"></a>Verwenden von PowerShell zum Anzeigen von Antiphishingregeln

Verwenden Sie die folgende Syntax, um vorhandene Antiphishingregeln anzuzeigen:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Antiphishingregeln zusammen mit den angegebenen Eigenschaften zurückgegeben.

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

In diesem Beispiel werden alle Eigenschaftswerte für die Antiphishingregel namens Contoso Executives zurückgegeben.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Verwenden von PowerShell zum Ändern von Antiphishingrichtlinien

Abgesehen von den folgenden Elementen sind die gleichen Einstellungen verfügbar, wenn Sie eine Antiphishingrichtlinie in PowerShell ändern, wie beim Erstellen einer Richtlinie, wie in [Schritt 1 beschrieben: Verwenden von PowerShell zum Erstellen einer Antiphishingrichtlinie](#step-1-use-powershell-to-create-an-anti-phish-policy) weiter oben in diesem Artikel.

- Der _MakeDefault-Switch,_ der die angegebene Richtlinie in die Standardrichtlinie umschaltet (angewendet auf alle, immer **niedrigste** Priorität, und Sie können sie nicht löschen), ist nur verfügbar, wenn Sie eine Antiphishingrichtlinie in PowerShell ändern.
- Sie können eine Antiphishingrichtlinie nicht umbenennen (das Cmdlet **"Set-AntiPhishPolicy"** hat keinen _Name-Parameter)._ Wenn Sie eine Antiphishingrichtlinie im Microsoft 365 Defender-Portal umbenennen, benennen Sie nur die Antiphishingregel um.

Verwenden Sie die folgende Syntax, um eine Antiphishingrichtlinie zu ändern:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-AntiPhishPolicy".](/powershell/module/exchange/Set-AntiPhishPolicy)

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Verwenden von PowerShell zum Ändern von Antiphishingregeln

Die einzige Einstellung, die beim Ändern einer Antiphishingregel in PowerShell nicht verfügbar ist, ist der _Parameter "Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Antiphishingregeln finden Sie im nächsten Abschnitt.

Andernfalls sind die gleichen Einstellungen verfügbar, wenn Sie eine Regel erstellen, wie im [Abschnitt "Schritt 2: Verwenden von PowerShell zum Erstellen einer Antiphishingregel"](#step-2-use-powershell-to-create-an-anti-phish-rule) weiter oben in diesem Artikel beschrieben.

Verwenden Sie die folgende Syntax, um eine Antiphishingregel zu ändern:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-AntiPhishRule".](/powershell/module/exchange/set-antiphishrule)

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Antiphishingregeln

Das Aktivieren oder Deaktivieren einer Antiphishingregel in PowerShell aktiviert oder deaktiviert die gesamte Antiphishingrichtlinie (die Antiphishingregel und die zugewiesene Antiphishingrichtlinie). Sie können die standardmäßige Antiphishingrichtlinie nicht aktivieren oder deaktivieren (sie wird immer auf alle Empfänger angewendet).

Verwenden Sie die folgende Syntax, um eine Antiphishingregel in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die Antiphishingregel Marketing Department deaktiviert.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) und [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Verwenden von PowerShell zum Festlegen der Priorität von Antiphishingregeln

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie die folgende Syntax, um die Priorität einer Antiphishingregel in PowerShell festzulegen:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Hinweise**:

- Um die Priorität einer neuen Regel beim Erstellen festzulegen, verwenden Sie stattdessen den Parameter _"Priority"_ im Cmdlet **"New-AntiPhishRule".**
- Die Standardmäßige Antiphishingrichtlinie verfügt nicht über eine entsprechende Antiphishingregel und hat immer den unveränderlichen Prioritätswert **Lowest**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Verwenden von PowerShell zum Entfernen von Antiphishingrichtlinien

Wenn Sie PowerShell zum Entfernen einer Antiphishingrichtlinie verwenden, wird die entsprechende Antiphishingregel nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Antiphishingrichtlinie in PowerShell zu entfernen:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Antiphishingrichtlinie Marketing Department entfernt.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Verwenden von PowerShell zum Entfernen von Antiphishingregeln

Wenn Sie PowerShell zum Entfernen einer Antiphishingregel verwenden, wird die entsprechende Antiphishingrichtlinie nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Antiphishingregel in PowerShell zu entfernen:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die Antiphishingregel Marketing Department entfernt.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Antiphishingrichtlinien in EOP erfolgreich konfiguriert haben:

- Wechseln Sie im Microsoft 365 Defender Portal zur Seite "Richtlinien für **E-Mail-& Zusammenarbeit** & Richtlinien für \>  \> **Bedrohungsregeln"** \>  im Abschnitt \> **"Antiphishing".** Überprüfen Sie die Liste der Richtlinien, ihre **Statuswerte** und ihre **Prioritätswerte.** Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, indem Sie auf den Namen klicken und die Details im angezeigten Flyout anzeigen.

- Ersetzen Sie in Exchange Online PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
