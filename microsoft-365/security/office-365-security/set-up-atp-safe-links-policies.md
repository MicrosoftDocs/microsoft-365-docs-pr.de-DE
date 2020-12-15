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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Richtlinien für sichere Links und globale Einstellungen für sichere Links in Microsoft Defender für Office 365 anzeigen, erstellen, ändern und löschen.
ms.openlocfilehash: 8a6d8a7ad567b658f04cb0b28800d4edbc33ec67
ms.sourcegitcommit: f81ca61f74f11a7436a6172538c3bda81b484d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675241"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Einrichten von Richtlinien für sichere Links in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](office-365-atp.md) verfügen. Wenn Sie ein Privatbenutzer sind, der nach Informationen zu Safelinks in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

"Sichere Links" ist ein Feature in [Microsoft Defender für Office 365](office-365-atp.md) , das die URL-Überprüfung eingehender e-Mail-Nachrichten im Nachrichtenfluss und die Zeit der Klick Überprüfung von URLs und Links in e-Mail-Nachrichten und an anderen Speicherorten bereitstellt. Weitere Informationen finden Sie unter [sichere Links in Microsoft Defender für Office 365](atp-safe-links.md).

Es gibt keine integrierte oder standardmäßige Richtlinie für sichere Links. Um sichere Links beim Scannen von URLs zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere Links erstellen, wie in diesem Artikel beschrieben.

> [!NOTE]
> Sie konfigurieren die globalen Einstellungen für den Schutz von sicheren Links **außerhalb** der Richtlinien für sichere Links. Anweisungen finden Sie unter [Configure Global Settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).

Sie können Richtlinien für sichere Links im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer, aber mit Microsoft Defender für Office 365 Add-on-Abonnements) konfigurieren.

Die grundlegenden Elemente einer Richtlinie zu sicheren Links sind:

- **Richtlinie zu sicheren Links**: Aktivieren Sie den Schutz für sichere Links, aktivieren Sie den Echt Zeit-URL-Scan, geben Sie an, ob der Abschluss der Echtzeitüberprüfung vor dem Senden der Nachricht gewartet werden soll, aktivieren Sie die Überprüfung interner Nachrichten, geben Sie an, ob Benutzerklicks auf URLs nachverfolgt werden sollen, und geben Sie an, ob Benutzer auf die ursprüngliche URL klicken können
- **Die Regel für sichere Links**: gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) an.

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für sichere Links im Security & Compliance Center verwalten:

- Wenn Sie eine Richtlinie für sichere Links erstellen, erstellen Sie tatsächlich eine Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit dem gleichen Namen für beide.
- Wenn Sie eine Richtlinie für sichere Links ändern, ändern die Einstellungen im Zusammenhang mit dem Namen, der Priorität, den aktivierten oder deaktivierten und den Empfänger filtern die Regel für sichere Links. Alle anderen Einstellungen ändern die zugehörige Richtlinie für sichere Links.
- Wenn Sie eine Richtlinie für sichere Links entfernen, werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links entfernt.

In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt. Weitere Informationen finden Sie im Abschnitt [Verwenden von Exchange Online PowerShell oder eigenständige EoP PowerShell zum Konfigurieren von Richtlinien für sichere Links](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) weiter unten in diesem Artikel.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Wenn Sie direkt zur Seite **sichere Links** wechseln möchten, verwenden Sie <https://protection.office.com/safelinksv2> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Zum Erstellen, ändern und Löschen von Richtlinien für sichere Links müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.
  - Für den schreibgeschützten Zugriff auf Richtlinien für sichere Links müssen Sie Mitglied der Rollengruppen " **globaler Leser** " oder " **Sicherheits Leser** " sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweise**:

  - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Die empfohlenen Einstellungen für Richtlinien zu sicheren Links finden Sie unter [Richtlinieneinstellungen für sichere Links](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).

- Erlauben Sie bis zu 30 Minuten, bis eine neue oder aktualisierte Richtlinie angewendet wird.

- [Für Office 365 werden fortlaufend neue Features zu Microsoft Defender hinzugefügt](office-365-atp.md#new-features-in-microsoft-defender-for-office-365). Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren bestehenden Richtlinien für sichere Links vornehmen.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für sichere Links

Durch das Erstellen einer benutzerdefinierten Richtlinie für sichere Links im Security & Compliance Center werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit dem gleichen Namen für beide erstellt.

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.

2. Klicken Sie auf der Seite **sichere Links** auf **Erstellen**.

3. Der Assistent für **neue Richtlinien für sichere Links** wird geöffnet. Konfigurieren Sie auf der Seite **Ihre Richtlinie benennen** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.

   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Konfigurieren Sie auf der angezeigten Seite **Einstellungen** die folgenden Einstellungen:

   - **Wählen Sie die Aktion für unbekannte potenziell bösartige URLs in Nachrichten** aus: Wählen Sie **ein** aus, um den Schutz für sichere Links in e-Mail-Nachrichten zu aktivieren.

   - **Wählen Sie die Aktion für unbekannte oder potenziell schädliche URLs in Microsoft Teams** aus: Wählen Sie **ein** aus, um den Schutz für sichere Links für Links in Teams zu aktivieren.

   - Über **Prüfen der Echt Zeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen**: Wählen Sie diese Einstellung aus, um die Echtzeitüberprüfung von Links in e-Mail-Nachrichten zu aktivieren.

   - **Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht** übermitteln: Wählen Sie diese Einstellung, um zu warten, bis die URL-Überprüfung in Echtzeit abgeschlossen ist, bevor Sie die Nachricht

   - **Anwenden sicherer Links auf e-Mail-Nachrichten, die innerhalb der Organisation gesendet** werden: Wählen Sie diese Einstellung aus, um die Richtlinie für sichere Links auf Nachrichten zwischen internen Absendern und internen Empfängern anzuwenden.

   - **Benutzerklicks nicht nachverfolgen**: lassen Sie diese Einstellung nicht ausgewählt, damit der nach Verfolgungs Benutzer auf URLs in e-Mail-Nachrichten klickt.

   - **Benutzer dürfen nicht auf die ursprüngliche URL klicken**: Wählen Sie diese Einstellung aus, um zu verhindern, dass Benutzer auf die ursprüngliche URL in [Warn Seiten](atp-safe-links.md#warning-pages-from-safe-links)klicken.

   - **Die folgenden URLs dürfen nicht umgeschrieben** werden: ermöglicht den Zugriff auf die angegebenen URLs, die andernfalls durch sichere Links blockiert würden.

     Geben Sie in das Feld die gewünschte URL oder den gewünschten Wert ein, und klicken Sie dann auf ![Schaltflächensymbol hinzufügen](../../media/ITPro-EAC-AddIcon.png).

     Um einen vorhandenen Eintrag zu entfernen, wählen Sie ihn aus, und klicken Sie dann auf ![Symbol für die Schaltfläche "Löschen"](../../media/ITPro-EAC-DeleteIcon.png).

     Informationen zur Eingabesyntax finden Sie unter [Eintrags Syntax für die Liste "folgende URLs nicht umschreiben"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).

   Ausführliche Informationen zu diesen Einstellungen finden Sie unter Einstellungen für [sichere Links für e-Mail-Nachrichten](atp-safe-links.md#safe-links-settings-for-email-messages) und [Einstellungen für sichere Links für Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).

   Weitere empfohlene Werte für Standard mäßige und strenge Richtlinieneinstellungen finden Sie unter [Richtlinieneinstellungen für sichere Links](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Identifizieren Sie auf der Seite **angewendet auf** , die angezeigt wird, die internen Empfänger, auf die die Richtlinie angewendet wird.

   Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

   Klicken Sie auf **Bedingung hinzufügen**. Wählen Sie in der Dropdownliste, die angezeigt wird, eine Bedingung unter **angewendet, wenn**:

   - **Der Empfänger lautet**: gibt ein oder mehrere Postfächer, e-Mail-Benutzer oder e-Mail-Kontakte in Ihrer Organisation an.
   - **Der Empfänger ist Mitglied von**: gibt eine oder mehrere Gruppen in Ihrer Organisation an.
   - **Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.

   Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **der folgenden** Felder angezeigt.

   - Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der zu markierende Werte durch.
   - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.
   - Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.
   - Wenn Sie einzelne Einträge entfernen möchten  , klicken Sie auf Entfernen- ![ Symbol ](../../media/scc-remove-icon.png) für den Wert entfernen.
   - Wenn Sie die gesamte Bedingung entfernen möchten **, klicken Sie** ![ in der Bedingung auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) .

   Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen** , und wählen Sie einen verbleibenden Wert unter **angewendet bei** aus.

   Wenn Sie Ausnahmen hinzufügen möchten, klicken Sie auf **Bedingung hinzufügen** , und wählen Sie unter **außer if** eine Ausnahme aus. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

6. Überprüfen Sie auf der angezeigten Seite **Ihre Einstellungen überprüfen** Ihre Einstellungen. Sie können auf jeder Einstellung auf **Bearbeiten** klicken, um Sie zu ändern.

   Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien zu sicheren Links

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.

2. Wählen Sie auf der Seite **sichere Links** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).

   Die Richtliniendetails werden in einem Fly Out angezeigt.

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Verwenden der Sicherheits & Compliance Center zum Ändern von Richtlinien für sichere Links

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.

2. Wählen Sie auf der Seite **sichere Links** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).

3. Klicken Sie in der angezeigten Richtlinie Details ausfliegen, die angezeigt wird, auf **Richtlinie bearbeiten**.

Die verfügbaren Einstellungen im angezeigten ausfliegen sind mit denen identisch, die im Abschnitt [Verwenden der Sicherheits & Compliance Center zum Erstellen von Richtlinien für sichere Links](#use-the-security--compliance-center-to-create-safe-links-policies) beschrieben sind.

Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Reihenfolge der Richtlinien Priorität finden Sie in den folgenden Abschnitten.

### <a name="enable-or-disable-safe-links-policies"></a>Aktivieren oder Deaktivieren von Richtlinien für sichere Links

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.

2. Beachten Sie den Wert in der Spalte **Status** :

   - Schieben Sie die Umschaltfläche nach links, um die Richtlinie zu deaktivieren: ![Deaktivieren der Richtlinie](../../media/scc-toggle-off.png).

   - Schieben Sie die Umschaltfläche nach rechts, um die Richtlinie zu aktivieren: ![Richtlinie aktivieren](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

### <a name="set-the-priority-of-safe-links-policies"></a>Festlegen der Priorität von Richtlinien für sichere Links

Standardmäßig erhalten Richtlinien für sichere Links eine Priorität, die auf der Reihenfolge basiert, in der Sie erstellt wurden (neuere Policen haben eine niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

Richtlinien für sichere Links werden in der Reihenfolge angezeigt, in der Sie verarbeitet werden (die erste Richtlinie hat den **Prioritäts** Wert 0).

**Hinweis**: im Security & Compliance Center können Sie die Priorität der Richtlinie für sichere Links nur ändern, nachdem Sie Sie erstellt haben. In PowerShell können Sie die Standardpriorität außer Kraft setzen, wenn Sie die Regel für sichere Links erstellen (die sich auf die Priorität vorhandener Regeln auswirken kann).

Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.

2. Wählen Sie auf der Seite **sichere Links** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).

3. Klicken Sie im daraufhin angezeigten Richtliniendetails-Steuerelement auf die Schaltfläche verfügbare Priorität:

   - Für die Richtlinie für sichere Links mit dem **Prioritäts** Wert **0** ist nur die Schaltfläche **Priorität verringern** verfügbar.

   - Die Richtlinie für sichere Links mit dem Wert der niedrigsten **Priorität** (beispielsweise **3**) hat nur die Schaltfläche **Priorität verlängern** .

   - Wenn Sie über drei oder mehr Richtlinien für sichere Links verfügen, stehen für Richtlinien zwischen den **Werten der höchsten** und der niedrigsten Priorität sowohl die Tasten "Priorität" als auch " **Priorität verringern** " zur Verfügung.

4. Klicken Sie auf Priorität Verb **Essern** oder **Priorität verringern** , um den **Prioritäts** Wert zu ändern.

5. Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Verwenden der Sicherheits & Compliance Center zum Entfernen von Richtlinien für sichere Links

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**.

2. Wählen Sie auf der Seite **sichere Links** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).

3. Klicken Sie im daraufhin angezeigten Richtliniendetails-Steuerelement auf **Richtlinie löschen**, und klicken Sie dann im angezeigten Warndialogfeld auf **Ja** .

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Verwenden von Exchange Online PowerShell oder eigenständigen EoP PowerShell zum Konfigurieren von Richtlinien für sichere Links

Wie bereits beschrieben, besteht eine Richtlinie zu sicheren Links aus einer Richtlinie zu sicheren Links und einer Regel für sichere Links.

In PowerShell ist der Unterschied zwischen Richtlinien für sichere Links und Regeln für sichere Links offensichtlich. Sie verwalten Richtlinien für sichere Links mithilfe der **\* -SafeLinksPolicy-** Cmdlets und verwalten Regeln für sichere Links mithilfe der **\* -SafeLinksRule-** Cmdlets.

- In PowerShell erstellen Sie zuerst die Richtlinie für sichere Links, dann erstellen Sie die Regel für sichere Links, die die Richtlinie identifiziert, auf die die Regel angewendet wird.
- In PowerShell ändern Sie die Einstellungen in der Richtlinie für sichere Links und in der Regel für sichere Links separat.
- Wenn Sie eine Richtlinie für sichere Links aus PowerShell entfernen, wird die entsprechende Regel für sichere Links nicht automatisch entfernt und umgekehrt.

### <a name="use-powershell-to-create-safe-links-policies"></a>Verwenden von PowerShell zum Erstellen von Richtlinien für sichere Links

Das Erstellen einer Richtlinie zu sicheren Links in PowerShell erfolgt in einem zweistufigen Prozess:

1. Erstellen Sie die Richtlinie für sichere Links.
2. Erstellen Sie die Regel für sichere Links, die die Richtlinie für sichere Links angibt, auf die die Regel angewendet wird.

 **Hinweise**:

- Sie können eine neue Regel für sichere Links erstellen und ihr eine vorhandene, nicht zugeordnete Richtlinie für sichere Links zuweisen. Eine Regel für sichere Links kann nicht mehr als einer Richtlinie für sichere Links zugeordnet werden.

- Sie können die folgenden Einstellungen für neue Richtlinien für sichere Links in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Security & Compliance Center verfügbar sind:

  - Erstellen Sie die neue Richtlinie als deaktiviert (_aktiviert_ im `$false` Cmdlet **New-SafeLinksRule** ).
  - Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) für das Cmdlet **New-SafeLinksRule** fest).

- Eine neue Richtlinie für sichere Links, die Sie in PowerShell erstellen, ist erst im Security & Compliance Center sichtbar, wenn Sie die Richtlinie einer Regel für sichere Links zuweisen.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie zu sicheren Links

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links zu erstellen:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

**Hinweise**:

- Ausführliche Informationen zur Eingabesyntax, die für den _DoNotRewriteUrls_ -Parameter verwendet werden kann, finden Sie unter [Entry-Syntax für die Liste "nicht umschreiben der folgenden URLs"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).

- Weitere Syntax, die Sie für den Parameter _DoNotRewriteUrls_ verwenden können, wenn Sie vorhandene Richtlinien für sichere Links mithilfe des Cmdlets " **Satz-SafeLinksPolicy** " ändern, finden Sie im Abschnitt [Verwenden von PowerShell zum Ändern von Richtlinien für sichere Links](#use-powershell-to-modify-safe-links-policies) weiter unten in diesem Artikel.

In diesem Beispiel wird eine Richtlinie für sichere Links namens "Contoso all" mit den folgenden Werten erstellt:

- Aktivieren Sie die URL-Überprüfung und das Umschreiben in e-Mail-Nachrichten.
- Aktivieren Sie die URL-Überprüfung in Microsoft Teams (nur Tippen Sie auf Vorschau).
- Aktivieren Sie die Echtzeitüberprüfung von angeklickten URLs, einschließlich geklickter Links, die auf Dateien verweisen.
- Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht senden.
- Aktivieren Sie die URL-Überprüfung und Umschreibung für interne Nachrichten.
- Nachverfolgen von Benutzerklicks im Zusammenhang mit Safe Links Protection (der Parameter _DoNotTrackUserClicks_ wird nicht verwendet, und der Standardwert ist $false, was bedeutet, dass Benutzerklicks nachverfolgt werden).
- Benutzer können nicht auf die ursprüngliche URL klicken.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel für sichere Links

Verwenden Sie die folgende Syntax, um eine Regel für sichere Links zu erstellen:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In diesem Beispiel wird eine Regel für sichere Links namens "Contoso all" mit den folgenden Bedingungen erstellt:

- Die Regel ist mit der Richtlinie für sichere Links namens "Contoso all" verknüpft.
- Die Regel gilt für alle Empfänger in der contoso.com-Domäne.
- Da wir den _Priority_ -Parameter nicht verwenden, wird die Standardpriorität verwendet.
- Die Regel ist aktiviert (der Parameter _Enabled_ wird nicht verwendet, und der Standardwert ist `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).

### <a name="use-powershell-to-view-safe-links-policies"></a>Verwenden von PowerShell zum Anzeigen von Richtlinien für sichere Links

Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Links anzuzeigen:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Richtlinien für sichere Links zurückgegeben.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

In diesem Beispiel werden detaillierte Informationen für die Richtlinie für sichere Links namens "Contoso Executives" zurückgegeben.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).

### <a name="use-powershell-to-view-safe-links-rules"></a>Verwenden von PowerShell zum Anzeigen von Regeln für sichere Links

Verwenden Sie die folgende Syntax, um vorhandene Regeln für sichere Links anzuzeigen:

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

In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Links namens "Contoso Executives" zurückgegeben.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).

### <a name="use-powershell-to-modify-safe-links-policies"></a>Verwenden von PowerShell zum Ändern von Richtlinien für sichere Links

Sie können keine Richtlinie für sichere Links in PowerShell umbenennen (das Cmdlet " **SafeLinksPolicy** " verfügt über keinen Parameter " _Name_ "). Wenn Sie eine Richtlinie für sichere Links im Security & Compliance Center umbenennen, benennen Sie die _Regel_ für sichere Links nur um.

Die einzige zusätzliche Überlegung beim Ändern von Richtlinien für sichere Links in PowerShell ist die verfügbare Syntax für den _DoNotRewriteUrls_ -Parameter (die [Liste "nicht umschreiben der folgenden URLs"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):

- Verwenden Sie die folgende Syntax, um Werte hinzuzufügen, die vorhandene Einträge ersetzen werden: `"Entry1","Entry2,..."EntryN"` .
- Verwenden Sie die folgende Syntax, um Werte hinzuzufügen oder zu entfernen, ohne andere vorhandene Einträge zu beeinflussen: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

Andernfalls stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Richtlinie zu sicheren Links erstellen, wie im Abschnitt [Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie zu sicheren Links](#step-1-use-powershell-to-create-a-safe-links-policy) weiter oben in diesem Artikel beschrieben.

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links zu ändern:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).

### <a name="use-powershell-to-modify-safe-links-rules"></a>Verwenden von PowerShell zum Ändern von Regeln für sichere Links

Die einzige Einstellung, die beim Ändern einer Regel für sichere Links in PowerShell nicht verfügbar ist, ist der Parameter _Enabled_ , mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Links finden Sie im nächsten Abschnitt.

Andernfalls stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen einer Richtlinie zu sicheren Links](#step-2-use-powershell-to-create-a-safe-links-rule) weiter oben in diesem Artikel beschrieben.

Verwenden Sie die folgende Syntax, um eine Regel für sichere Links zu ändern:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für sichere Links

Durch das Aktivieren oder Deaktivieren einer Regel für sichere Links in PowerShell wird die gesamte Richtlinie für sichere Links aktiviert oder deaktiviert (die Regel für sichere Links und die Richtlinie zugewiesene sichere Links).

Verwenden Sie die folgende Syntax, um eine Regel für sichere Links in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die Regel für sichere Links namens "Marketing Department" deaktiviert.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) und [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Verwenden von PowerShell zum Festlegen der Priorität von Regeln für sichere Links

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie die folgende Syntax, um die Priorität einer Regel für sichere Links in PowerShell festzulegen:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

**Hinweis**: Wenn Sie die Priorität einer neuen Regel beim Erstellen festlegen möchten, verwenden Sie stattdessen den Parameter _Priority_ für das Cmdlet **New-SafeLinksRule** .

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-remove-safe-links-policies"></a>Verwenden von PowerShell zum Entfernen von Richtlinien für sichere Links

Wenn Sie mithilfe von PowerShell eine Richtlinie für sichere Links entfernen, wird die entsprechende Regel für sichere Links nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links in PowerShell zu entfernen:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Richtlinie für sichere Links namens "Marketing Department" entfernt.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).

### <a name="use-powershell-to-remove-safe-links-rules"></a>Verwenden von PowerShell zum Entfernen von Regeln für sichere Links

Wenn Sie mithilfe von PowerShell eine Regel für sichere Links entfernen, wird die entsprechende Richtlinie für sichere Links nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Regel für sichere Links in PowerShell zu entfernen:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die Regel für sichere Links namens "Marketing Department" entfernt.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).

Um zu überprüfen, ob sichere Links Nachrichten scannen, überprüfen Sie den verfügbaren Microsoft Defender für Office 365 Berichte. Weitere Informationen finden Sie unter [Anzeigen von Berichten für Defender für Office 365](view-reports-for-atp.md) und [Verwenden von Explorer im Security & Compliance Center](threat-explorer.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Richtlinien für sichere Links erfolgreich erstellt, geändert oder entfernt haben:

- Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**. Überprüfen Sie die Liste der Richtlinien, deren **Status** Werte und deren **Prioritäts** Werte. Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im verfliegt an.

- Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
