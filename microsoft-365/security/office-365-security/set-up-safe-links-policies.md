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
description: Administratoren können erfahren, wie Sie Richtlinien für sichere Links und globale Einstellungen für sichere Links in Microsoft Defender für Office 365 anzeigen, erstellen, ändern und löschen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 40ae52cfce53c3fa14253a94e72f1a2bccda9a86
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929827"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Einrichten von Richtlinien für sichere Links in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](defender-for-office-365.md) verfügen. Wenn Sie ein Privatbenutzer sind, der nach Informationen zu Safelinks in Outlook sucht, finden Sie weitere Informationen unter [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Sichere Links ist ein Feature in [Microsoft Defender für Office 365,](defender-for-office-365.md) das die URL-Überprüfung eingehender E-Mail-Nachrichten im E-Mail-Fluss sowie den Zeitpunkt der Klicküberprüfung von URLs und Links in E-Mail-Nachrichten und an anderen Speicherorten ermöglicht. Weitere Informationen finden Sie unter ["Sichere Links" in Microsoft Defender für Office 365.](safe-links.md)

Es gibt keine integrierte oder standardmäßige Richtlinie für sichere Links. Um das Scannen sicherer Links von URLs zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere Links erstellen, wie in diesem Artikel beschrieben.

> [!NOTE]
> Sie konfigurieren die globalen Einstellungen für den Schutz sicherer Links **außerhalb** von Richtlinien für sichere Links. Anweisungen finden Sie unter [Konfigurieren globaler Einstellungen für sichere Links in Microsoft Defender für Office 365.](configure-global-settings-for-safe-links.md)

Sie können Richtlinien für sichere Links im Microsoft 365 Defender-Portal oder in PowerShell konfigurieren (Exchange Online PowerShell für berechtigte Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer, aber mit Microsoft Defender für Office 365-Add-On-Abonnements).

Die grundlegenden Elemente einer Richtlinie für sichere Links sind:

- Die Richtlinie für **sichere Links:** Aktivieren Sie den Schutz für sichere Links, aktivieren Sie die Echtzeit-URL-Überprüfung, geben Sie an, ob auf den Abschluss der Echtzeitüberprüfung gewartet werden soll, bevor die Nachricht zuzustellen ist, aktivieren Sie die Überprüfung auf interne Nachrichten, geben Sie an, ob Benutzerklicks auf URLs nachverfolgen sollen, und geben Sie an, ob Benutzer auf die ursprüngliche URL klicken dürfen.
- **Die Regel für sichere Verknüpfungen:** Gibt die Prioritäts- und Empfängerfilter an (für wen die Richtlinie gilt).

> [!IMPORTANT]
> Administratoren sollten die unterschiedlichen Konfigurationseinstellungen für SafeLinks berücksichtigen. Eine der verfügbaren Optionen besteht darin, Benutzerdaten in SafeLinks einzuschließen. Dieses Feature ermöglicht *es Sicherheitsteams,* potenzielle Benutzerkompromittierungen zu untersuchen, Korrekturmaßnahmen zu ergreifen und kostspielige Verstöße zu begrenzen.

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für sichere Links im Microsoft 365 Defender-Portal verwalten:

- Wenn Sie eine Richtlinie für sichere Links erstellen, erstellen Sie tatsächlich eine Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit demselben Namen für beide.
- Wenn Sie eine Richtlinie für sichere Links ändern, ändern Einstellungen, die sich auf den Namen, die Priorität, aktiviert oder deaktiviert beziehen, und Empfängerfilter die Regel für sichere Links. Alle anderen Einstellungen ändern die zugehörige Richtlinie für sichere Links.
- Wenn Sie eine Richtlinie für sichere Links entfernen, werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links entfernt.

In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt. Weitere Informationen finden Sie im Abschnitt ["Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies"](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) weiter unten in diesem Artikel.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/>. To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:
  - Um Richtlinien für sichere Links zu erstellen, zu ändern und zu löschen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** im Microsoft 365 Defender-Portal **und** Mitglied der **Rollengruppe "Organisationsverwaltung"** in Exchange Online sein.
  - Für den schreibgeschützten Zugriff auf Richtlinien für sichere Links müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-in-the-security-and-compliance-center.md) und [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > 
  > - Wenn Sie Benutzer zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center hinzufügen, erhalten Benutzer die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  . – Die Rollengruppe **"Organisationsverwaltung nur anzeigen"** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) bietet auch schreibgeschützten Zugriff auf das Feature.

- Unsere empfohlenen Einstellungen für Richtlinien für sichere Links finden Sie unter ["Richtlinieneinstellungen für sichere Links".](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

- Es kann bis zu 30 Minuten dauern, bis eine neue oder aktualisierte Richtlinie angewendet wird.

- [Microsoft Defender werden kontinuierlich neue Features für Office 365 hinzugefügt.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365) Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren vorhandenen Richtlinien für sichere Links vornehmen.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a>Verwenden des Microsoft 365 Defender-Portals zum Erstellen von Richtlinien für sichere Links

Beim Erstellen einer benutzerdefinierten Richtlinie für sichere Links im Microsoft 365 Defender-Portal werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit demselben Namen für beide erstellt.

1. Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien & Regeln** Threat \> **Policies** \> **Safe Links**.

2. Klicken Sie auf der Seite **"Sichere Links"** auf **"Erstellen".**

3. Der Assistent **für neue Richtlinien für sichere Links** wird geöffnet. Konfigurieren Sie auf der Seite **"Richtlinie benennen"** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.

   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

4. Konfigurieren Sie auf der **angezeigten Einstellungen** Seite die folgenden Einstellungen:

   - **Wählen Sie die Aktion für unbekannte potenziell schädliche URLs in Nachrichten** aus: Aktivieren Sie **"Ein",** um den Schutz sicherer Links für Links in E-Mail-Nachrichten zu aktivieren.

   - **Wählen Sie die Aktion für unbekannte oder potenziell schädliche URLs in Microsoft Teams** aus: **Aktivieren** Sie "Ein", um den Schutz sicherer Links für Links in Teams zu aktivieren.

   - **Wenden Sie die URL-Überprüfung in Echtzeit auf verdächtige Links und Links an, die auf Dateien verweisen:** Wählen Sie diese Einstellung aus, um die Echtzeitüberprüfung von Links in E-Mail-Nachrichten zu aktivieren.

   - **Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht übermitteln:** Wählen Sie diese Einstellung aus, um auf den Abschluss der URL-Überprüfung in Echtzeit zu warten, bevor Sie die Nachricht übermitteln.

   - **Anwenden von sicheren Links auf E-Mail-Nachrichten, die innerhalb der Organisation gesendet werden:** Wählen Sie diese Einstellung aus, um die Richtlinie für sichere Links auf Nachrichten zwischen internen Absendern und internen Empfängern anzuwenden.

   - **Benutzerklicks nicht nachverfolgen:** Lassen Sie diese Einstellung deaktiviert, um das Nachverfolgen von Benutzerklicks auf URLs in E-Mail-Nachrichten zu aktivieren.

   - **Benutzer dürfen nicht auf die ursprüngliche URL klicken:** Wählen Sie diese Einstellung aus, um zu verhindern, dass Benutzer auf [Warnseiten](safe-links.md#warning-pages-from-safe-links)auf die ursprüngliche URL klicken.

   - **Schreiben Sie die folgenden URLs nicht neu:** Ermöglicht den Zugriff auf die angegebenen URLs, die andernfalls durch sichere Links blockiert würden.

     Geben Sie in das Feld die gewünschte URL oder den gewünschten Wert ein, und klicken Sie dann auf ![Symbol "Schaltfläche hinzufügen"](../../media/ITPro-EAC-AddIcon.png).

     Um einen vorhandenen Eintrag zu entfernen, wählen Sie ihn aus, und klicken Sie dann auf ![Schaltflächensymbol löschen](../../media/ITPro-EAC-DeleteIcon.png).

     Informationen zur Eintragssyntax finden Sie unter [Eintragssyntax für die Liste "Die folgenden URLs nicht neu schreiben".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)

   Ausführliche Informationen zu diesen Einstellungen finden Sie unter [Einstellungen für sichere Links für E-Mail-Nachrichten](safe-links.md#safe-links-settings-for-email-messages) und Einstellungen für sichere Links für [Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).

   Weitere empfohlene Werte für Standard- und Strict-Richtlinieneinstellungen finden Sie unter ["Richtlinieneinstellungen für sichere Links".](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

5. Identifizieren Sie auf der angezeigten Seite **Angewendet** auf die internen Empfänger, für die die Richtlinie gilt.

   Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

   Klicken Sie auf **"Bedingung hinzufügen".** Wählen Sie in der angezeigten Dropdownliste eine Bedingung unter **"Angewendet"** aus, wenn:

   - **Der Empfänger lautet:** Gibt ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation an.
   - **Der Empfänger ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an.
   - **Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.

   Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **dieser** Kontrollkästchen angezeigt.

   - Klicken Sie in das Feld, und scrollen Sie durch die Liste der auszuwählenden Werte.
   - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.
   - Klicken Sie auf einen leeren Bereich im Feld, um weitere Werte hinzuzufügen.
   - Um einzelne Einträge zu entfernen, klicken Sie auf das Symbol **"Entfernen"** ![ für den ](../../media/scc-remove-icon.png) Wert.
   - Klicken Sie zum Entfernen der gesamten Bedingung auf das Symbol **"Entfernen"** ![ für die ](../../media/scc-remove-icon.png) Bedingung.

   Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **"Bedingung hinzufügen",** und wählen Sie unter **Angewendet** einen verbleibenden Wert aus.

   Klicken Sie zum Hinzufügen von Ausnahmen auf **"Bedingung hinzufügen",** und wählen Sie unter **"Ausnahme wenn"** eine Ausnahme aus. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

6. Überprüfen Sie auf der daraufhin angezeigten Seite **"Einstellungen überprüfen"** Ihre Einstellungen. Sie können in jeder Einstellung auf **Bearbeiten** klicken, um sie zu ändern.

   Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a>Verwenden des Microsoft 365 Defender-Portals zum Anzeigen von Richtlinien für sichere Links

1. Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien & Regeln** Threat \> **Policies** \> **Safe Links**.

2. Wählen Sie auf der Seite **"Sichere Links"** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

   Die Richtliniendetails werden in einem Flyout angezeigt.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a>Verwenden des Microsoft 365 Defender-Portals zum Ändern von Richtlinien für sichere Links

1. Wechseln Sie im Microsoft 365 Defender-Portal zu ***Richtlinien & Regeln** Für \> **Bedrohungsrichtlinien** sichere \> **Links.**

2. Wählen Sie auf der Seite **"Sichere Links"** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

3. Klicken Sie in den angezeigten Richtliniendetails auf **"Richtlinie bearbeiten".**

Die verfügbaren Einstellungen im angezeigten Flyout sind identisch mit den Einstellungen, die im Abschnitt ["Verwenden des Microsoft 365 Defender-Portals zum Erstellen von Richtlinien](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) für sichere Links" beschrieben sind.

Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Reihenfolge der Richtlinienpriorität finden Sie in den folgenden Abschnitten.

### <a name="enable-or-disable-safe-links-policies"></a>Aktivieren oder Deaktivieren von Richtlinien für sichere Links

1. Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien & Regeln** Für \> **Bedrohungsrichtlinien** sichere \> **Links.**

2. Beachten Sie den Wert in der Spalte **"Status":**

   - Schieben Sie die Umschaltfläche nach links, um die Richtlinie zu deaktivieren: ![Richtlinie deaktivieren](../../media/scc-toggle-off.png).

   - Schieben Sie die Umschaltfläche nach rechts, um die Richtlinie zu aktivieren: ![Richtlinie aktivieren](../../media/scc-toggle-on.png).

### <a name="set-the-priority-of-safe-links-policies"></a>Festlegen der Priorität von Richtlinien für sichere Links

Standardmäßig erhalten Richtlinien für sichere Links eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

Richtlinien für sichere Links werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0).

> [!NOTE]
> Im Microsoft 365 Defender-Portal können Sie die Priorität der Richtlinie für sichere Links erst ändern, nachdem Sie sie erstellt haben. In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Regel für sichere Verknüpfungen erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).

Um die Priorität einer Richtlinie zu ändern, verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können die **Prioritätsnummer** im Microsoft 365 Defender-Portal nicht direkt ändern).

1. Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien & Regeln** Für \> **Bedrohungsrichtlinien** sichere \> **Links.**

2. Wählen Sie auf der Seite **"Sichere Links"** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

3. Klicken Sie im angezeigten Flyout mit den Richtliniendetails auf die Schaltfläche "Verfügbare Priorität":

   - Für die Richtlinie für sichere Links mit dem **Prioritätswert** **0** ist nur die Schaltfläche **"Priorität verringern"** verfügbar.

   - Für die Richtlinie für sichere Verknüpfungen mit dem niedrigsten **Prioritätswert** (z. B. **3)** ist nur die Schaltfläche **"Priorität erhöhen"** verfügbar.

   - Wenn Sie über drei oder mehr Richtlinien für sichere Verknüpfungen verfügen, sind für Richtlinien zwischen den Werten mit der höchsten und der niedrigsten Priorität sowohl die Schaltflächen **"Priorität erhöhen"** als auch **"Priorität verringern"** verfügbar.

4. Klicken Sie auf **"Priorität erhöhen"** oder **"Priorität verringern",** um den **Wert "Priorität"** zu ändern.

5. Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a>Verwenden des Microsoft 365 Defender-Portals zum Entfernen von Richtlinien für sichere Links

1. Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien & Regeln** Für \> **Bedrohungsrichtlinien** sichere \> **Links.**

2. Wählen Sie auf der Seite **"Sichere Links"** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

3. Klicken Sie in den angezeigten Richtliniendetails auf **"Richtlinie löschen",** und klicken Sie dann im daraufhin angezeigten Warndialogfeld auf **"Ja".**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Verwenden Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren von Richtlinien für sichere Links

Wie zuvor beschrieben besteht eine Richtlinie für sichere Links aus einer Richtlinie für sichere Links und einer Regel für sichere Links.

In PowerShell ist der Unterschied zwischen Richtlinien für sichere Links und Regeln für sichere Links offensichtlich. Sie verwalten Richtlinien für sichere Links mithilfe der Cmdlets **\* "-SafeLinksPolicy",** und Sie verwalten Regeln für sichere Links mithilfe der Cmdlets **\* "-SafeLinksRule".**

- In PowerShell erstellen Sie zuerst die Richtlinie für sichere Links und dann die Regel für sichere Links, die die Richtlinie identifiziert, für die die Regel gilt.
- In PowerShell ändern Sie die Einstellungen in der Richtlinie für sichere Links und die Regel für sichere Links separat.
- Wenn Sie eine Richtlinie für sichere Links aus PowerShell entfernen, wird die entsprechende Regel für sichere Links nicht automatisch entfernt und umgekehrt.

### <a name="use-powershell-to-create-safe-links-policies"></a>Verwenden von PowerShell zum Erstellen von Richtlinien für sichere Links

Das Erstellen einer Richtlinie für sichere Links in PowerShell besteht aus zwei Schritten:

1. Erstellen Sie die Richtlinie für sichere Links.
2. Erstellen Sie die Regel für sichere Links, die die Richtlinie für sichere Links angibt, auf die die Regel angewendet wird.

> [!NOTE]
> 
> - Sie können eine neue Regel für sichere Links erstellen und ihr eine vorhandene Richtlinie für nicht zugeordnete sichere Links zuweisen. Eine Regel für sichere Links kann nicht mehr als einer Richtlinie für sichere Links zugeordnet werden.
> 
> - Sie können die folgenden Einstellungen für neue Richtlinien für sichere Links in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Microsoft 365 Defender-Portal verfügbar sind:
> 
>   - Erstellen Sie die neue Richtlinie als deaktiviert _(aktiviert_ `$false` für das Cmdlet **"New-SafeLinksRule").**
>   - Legen Sie die Priorität der Richtlinie während der Erstellung _(Priorität)_ _\<Number\>_ im Cmdlet **"New-SafeLinksRule"** fest.
> 
> - Eine neue Richtlinie für sichere Links, die Sie in PowerShell erstellen, ist erst im Microsoft 365 Defender-Portal sichtbar, wenn Sie die Richtlinie einer Regel für sichere Links zuweisen.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für sichere Links

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links zu erstellen:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - Ausführliche Informationen zur Eintragssyntax, die für den _DoNotRewriteUrls-Parameter_ verwendet werden soll, finden Sie unter [Eintragssyntax für die Liste "Die folgenden URLs nicht neu schreiben".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)
> 
> - Eine zusätzliche Syntax, die Sie für den _DoNotRewriteUrls-Parameter_ verwenden können, wenn Sie vorhandene Richtlinien für sichere Links mithilfe des Cmdlets **"Set-SafeLinksPolicy"** ändern, finden Sie im Abschnitt ["Verwenden von PowerShell zum Ändern](#use-powershell-to-modify-safe-links-policies) von Richtlinien für sichere Verknüpfungen" weiter unten in diesem Artikel.

In diesem Beispiel wird eine Richtlinie für sichere Verknüpfungen namens "Contoso All" mit den folgenden Werten erstellt:

- Aktivieren Sie die URL-Überprüfung und -Umschreibung in E-Mail-Nachrichten.
- Aktivieren Sie die URL-Überprüfung in Teams (nur TAP Preview).
- Aktivieren Sie die Echtzeitüberprüfung von angeklickten URLs, einschließlich angeklickter Links, die auf Dateien verweisen.
- Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht übermitteln.
- Aktivieren Sie die URL-Überprüfung und das Umschreiben für interne Nachrichten.
- Nachverfolgen von Benutzerklicks im Zusammenhang mit dem Schutz sicherer Links (wir verwenden nicht den _DoNotTrackUserClicks-Parameter,_ und der Standardwert ist $false, was bedeutet, dass Benutzerklicks nachverfolgt werden).
- Benutzer dürfen nicht auf die ursprüngliche URL klicken.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel für sichere Links

Verwenden Sie diese Syntax, um eine Regel für sichere Links zu erstellen:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In diesem Beispiel wird eine Regel für sichere Verknüpfungen namens "Contoso All" mit den folgenden Bedingungen erstellt:

- Die Regel ist der Richtlinie für sichere Verknüpfungen namens Contoso All zugeordnet.
- Die Regel gilt für alle Empfänger in der contoso.com Domäne.
- Da der Parameter _"Priority"_ nicht verwendet wird, wird die Standardpriorität verwendet.
- Die Regel ist aktiviert (wir verwenden nicht den Parameter _Enabled,_ und der Standardwert lautet `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).

### <a name="use-powershell-to-view-safe-links-policies"></a>Verwenden von PowerShell zum Anzeigen von Richtlinien für sichere Links

Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Links anzuzeigen:

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SafeLinksPolicy".](/powershell/module/exchange/get-safelinkspolicy)

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

In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Links namens Contoso Executives zurückgegeben.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SafeLinksRule".](/powershell/module/exchange/get-safelinksrule)

### <a name="use-powershell-to-modify-safe-links-policies"></a>Verwenden von PowerShell zum Ändern von Richtlinien für sichere Links

Sie können eine Richtlinie für sichere Links in PowerShell nicht umbenennen (das Cmdlet **"Set-SafeLinksPolicy"** hat keinen _Name-Parameter)._ Wenn Sie eine Richtlinie für sichere Links im Microsoft 365 Defender-Portal umbenennen, benennen Sie nur die _Regel für_ sichere Links um.

Die einzige zusätzliche Überlegung zum Ändern von Richtlinien für sichere Links in PowerShell ist die verfügbare Syntax für den _Parameter "DoNotRewriteUrls"_ (die [Liste "Die folgenden URLs nicht umschreiben"):](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- Verwenden Sie die folgende Syntax, um Werte hinzuzufügen, die vorhandene Einträge `"Entry1","Entry2,..."EntryN"` ersetzen:
- Verwenden Sie die folgende Syntax, um Werte hinzuzufügen oder zu entfernen, ohne dass sich dies auf andere Einträge auswirkt: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

Andernfalls sind die gleichen Einstellungen verfügbar, wenn Sie eine Richtlinie für sichere Links erstellen, wie im [Abschnitt "Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für sichere Links"](#step-1-use-powershell-to-create-a-safe-links-policy) weiter oben in diesem Artikel beschrieben.

Verwenden Sie diese Syntax, um eine Richtlinie für sichere Links zu ändern:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeLinksPolicy".](/powershell/module/exchange/set-safelinkspolicy)

### <a name="use-powershell-to-modify-safe-links-rules"></a>Verwenden von PowerShell zum Ändern von Regeln für sichere Links

Die einzige Einstellung, die beim Ändern einer Regel für sichere Verknüpfungen in PowerShell nicht verfügbar ist, ist der _Parameter "Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Links finden Sie im nächsten Abschnitt.

Andernfalls sind die gleichen Einstellungen verfügbar, wenn Sie eine Regel erstellen, wie im [Abschnitt "Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel](#step-2-use-powershell-to-create-a-safe-links-rule) für sichere Links" weiter oben in diesem Artikel beschrieben.

Verwenden Sie die folgende Syntax, um eine Regel für sichere Links zu ändern:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeLinksRule".](/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für sichere Links

Durch Aktivieren oder Deaktivieren einer Regel für sichere Links in PowerShell wird die gesamte Richtlinie für sichere Links (die Regel für sichere Links und die Richtlinie für zugewiesene sichere Links) aktiviert oder deaktiviert.

Verwenden Sie die folgende Syntax, um eine Regel für sichere Links in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die Regel für sichere Links mit dem Namen "Marketing Department" deaktiviert.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Enable-SafeLinksRule"](/powershell/module/exchange/enable-safelinksrule) und ["Disable-SafeLinksRule".](/powershell/module/exchange/disable-safelinksrule)

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Verwenden von PowerShell zum Festlegen der Priorität von Regeln für sichere Links

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie die folgende Syntax, um die Priorität einer Regel für sichere Links in PowerShell festzulegen:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> Um die Priorität einer neuen Regel beim Erstellen festzulegen, verwenden Sie stattdessen den Parameter _"Priority"_ im Cmdlet **"New-SafeLinksRule".**

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeLinksRule".](/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-remove-safe-links-policies"></a>Verwenden von PowerShell zum Entfernen von Richtlinien für sichere Links

Wenn Sie PowerShell verwenden, um eine Richtlinie für sichere Links zu entfernen, wird die entsprechende Regel für sichere Links nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links in PowerShell zu entfernen:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Richtlinie für sichere Links mit dem Namen "Marketing Department" entfernt.

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

In diesem Beispiel wird die Regel für sichere Verknüpfungen mit dem Namen "Marketing Department" entfernt.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).

Um zu überprüfen, ob sichere Links Nachrichten überprüfen, überprüfen Sie den verfügbaren Microsoft Defender auf Office 365 Berichte. Weitere Informationen finden Sie unter [Anzeigen von Berichten für Defender für Office 365](view-reports-for-mdo.md) und Verwenden von Explorer im Microsoft 365 [Defender-Portal.](threat-explorer.md)

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Richtlinien für sichere Links erfolgreich erstellt, geändert oder entfernt haben:

- Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien & Regeln** Für \> **Bedrohungsrichtlinien** sichere \> **Links.** Überprüfen Sie die Liste der Richtlinien, ihre **Statuswerte** und ihre **Prioritätswerte.** Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.

- Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```