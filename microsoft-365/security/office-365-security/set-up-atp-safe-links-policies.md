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
ms.openlocfilehash: 29d777a7f351b9ab33232cb0136703ce3fa29842
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290153"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Einrichten von Richtlinien für sichere Links in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](office-365-atp.md) verfügen. Informationen zu Safelinks in Outlook finden Sie unter Advanced [Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Sichere Links ist ein Feature in [Microsoft Defender für Office 365,](office-365-atp.md) das die URL-Überprüfung eingehender E-Mail-Nachrichten im Nachrichtenfluss sowie die Zeit der Klicküberprüfung von URLs und Links in E-Mail-Nachrichten und an anderen Speicherorten bietet. Weitere Informationen finden Sie unter ["Sichere Links" in Microsoft Defender für Office 365.](atp-safe-links.md)

Es gibt keine integrierte oder standardmäßige Richtlinie für sichere Links. Um die Überprüfung von URLs auf sichere Links zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere Links erstellen, wie in diesem Artikel beschrieben.

> [!NOTE]
> Sie konfigurieren die globalen Einstellungen für den Schutz sicherer Links **außerhalb** von Richtlinien für sichere Links. Anweisungen finden Sie unter ["Konfigurieren globaler Einstellungen für sichere Links in Microsoft Defender für Office 365".](configure-global-settings-for-safe-links.md)

Sie können Richtlinien für sichere Links im Security & Compliance Center oder in PowerShell konfigurieren (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online-Postfächer, aber mit Microsoft Defender für Office 365-Add-On-Abonnements).

Die grundlegenden Elemente einer Richtlinie für sichere Links sind:

- Die Richtlinie für sichere **Links:** Aktivieren Sie den Schutz sicherer Links, aktivieren Sie die URL-Überprüfung in Echtzeit, geben Sie an, ob die Überprüfung in Echtzeit abgeschlossen ist, bevor die Nachricht zu senden ist, aktivieren Sie die Überprüfung auf interne Nachrichten, geben Sie an, ob Benutzerklicks auf URLs nachverfolgt werden sollen, und geben Sie an, ob Benutzer auf die ursprüngliche URL klicken dürfen.
- **Die Regel für sichere Links:** Gibt die Prioritäts- und Empfängerfilter an (für wen die Richtlinie gilt).

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für sichere Links im Security & Compliance Center verwalten:

- Wenn Sie eine Richtlinie für sichere Links erstellen, erstellen Sie tatsächlich eine Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig unter Verwendung desselben Namens für beide.
- Wenn Sie eine Richtlinie für sichere Links ändern, ändern Einstellungen im Zusammenhang mit Name, Priorität, aktiviert oder deaktiviert und Empfängerfilter die Regel für sichere Links. Alle anderen Einstellungen ändern die zugeordnete Richtlinie für sichere Links.
- Wenn Sie eine Richtlinie für sichere Links entfernen, werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links entfernt.

In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt. Weitere Informationen finden Sie im Abschnitt "Verwenden von Exchange Online PowerShell oder der eigenständigen [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) zum Konfigurieren von Richtlinien für sichere Links" weiter unten in diesem Artikel.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite "Sichere **Links" zu** gelangen, verwenden Sie <https://protection.office.com/safelinksv2> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden:
  - Zum Erstellen, Ändern und Löschen von Richtlinien für sichere  Links müssen  Sie Mitglied der Rollengruppe "Organisationsverwaltung" oder "Sicherheitsadministrator" im Security & Compliance **Center** und Mitglied der Rollengruppe "Organisationsverwaltung" in Exchange Online sein. 
  - Für den schreibgeschützten Zugriff auf Richtlinien für sichere  Links müssen Sie Mitglied der Rollengruppe "Globaler Leser" oder **"Sicherheitsleser"** sein.

  Weitere Informationen finden Sie unter ["Berechtigungen" im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) und in Exchange [Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > 
  > - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  . - Die **Rollengruppe "Organisationsverwaltung** nur anzeigen" in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch den schreibgeschützten Zugriff auf das Feature.

- Die empfohlenen Einstellungen für Richtlinien für sichere Links finden Sie unter Richtlinieneinstellungen für [sichere Links.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

- Es kann bis zu 30 Minuten dauern, bis eine neue oder aktualisierte Richtlinie angewendet wird.

- [Microsoft Defender für Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)werden ständig neue Features hinzugefügt. Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren vorhandenen Richtlinien für sichere Links vornehmen.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für sichere Links

Beim Erstellen einer benutzerdefinierten Richtlinie für sichere Links im Security & Compliance Center werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit demselben Namen für beide erstellt.

1. Wechseln Sie im Security & Compliance Center zu **"AtP-sichere** Links" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**

2. Klicken Sie **auf der Seite "Sichere Links"** auf **"Erstellen".**

3. Der **Assistent für neue Richtlinien für sichere** Links wird geöffnet. Konfigurieren Sie **auf der Seite "Ihre Richtlinie benennen"** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.

   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Konfigurieren Sie **auf** der angezeigten Seite "Einstellungen" die folgenden Einstellungen:

   - **Wählen Sie die Aktion für unbekannte potenziell schädliche URLs in** Nachrichten aus: Aktivieren Sie **diese Option,** um den Schutz sicherer Links für Links in E-Mail-Nachrichten zu aktivieren.

   - **Wählen Sie die Aktion für unbekannte oder potenziell** schädliche URLs in Microsoft Teams aus: Aktivieren Sie **diese** Option, um den Schutz sicherer Links für Links in Teams zu aktivieren.

   - **Anwenden der Echtzeit-URL-Überprüfung** auf verdächtige Links und Links, die auf Dateien verweisen: Wählen Sie diese Einstellung aus, um das Scannen von Links in E-Mail-Nachrichten in Echtzeit zu aktivieren.

   - **Warten Sie, bis die URL-Überprüfung** abgeschlossen ist, bevor Sie die Nachricht zustellen: Wählen Sie diese Einstellung aus, um auf den Abschluss der Echtzeit-URL-Überprüfung zu warten, bevor Sie die Nachricht zustellen.

   - **Sichere Links auf** E-Mail-Nachrichten anwenden, die innerhalb der Organisation gesendet werden: Wählen Sie diese Einstellung aus, um die Richtlinie für sichere Links auf Nachrichten zwischen internen Absendern und internen Empfängern anzuwenden.

   - **Benutzerklicks nicht nachverfolgen:** Lassen Sie diese Einstellung deaktiviert, damit der Nachverfolgungsbenutzer auf URLs in E-Mail-Nachrichten klickt.

   - **Benutzer dürfen nicht zur** ursprünglichen URL klicken: Wählen Sie diese Einstellung aus, um zu blockieren, dass Benutzer auf Warnseiten auf die ursprüngliche URL [klicken.](atp-safe-links.md#warning-pages-from-safe-links)

   - **Schreiben Sie die folgenden URLs** nicht neu: Ermöglicht den Zugriff auf die angegebenen URLs, die andernfalls durch sichere Links blockiert würden.

     Geben Sie in das Feld die URL oder den Wert ein, die Sie verwenden möchten, und klicken Sie dann auf ![Schaltflächensymbol hinzufügen](../../media/ITPro-EAC-AddIcon.png).

     Um einen vorhandenen Eintrag zu entfernen, wählen Sie ihn aus, und klicken Sie dann auf ![Schaltflächensymbol löschen](../../media/ITPro-EAC-DeleteIcon.png).

     Informationen zur Eintragssyntax finden Sie in der Eintragssyntax für die Liste ["Die folgenden URLs dürfen](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)nicht neu geschrieben werden".

   Ausführliche Informationen zu diesen Einstellungen finden Sie unter Einstellungen für sichere [Links für](atp-safe-links.md#safe-links-settings-for-email-messages) E-Mail-Nachrichten und Einstellungen für sichere Links für [Microsoft Teams.](atp-safe-links.md#safe-links-settings-for-microsoft-teams)

   Weitere Informationen zu den empfohlenen Werten für Standard- und Strikte Richtlinieneinstellungen finden Sie unter Richtlinieneinstellungen für [sichere Links.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Identifizieren Sie **auf der angezeigten** Seite "Angewendet auf" die internen Empfänger, auf die die Richtlinie angewendet wird.

   Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

   Klicken **Sie auf Bedingung hinzufügen**. Wählen Sie in der angezeigten Dropdownliste eine Bedingung unter **"Angewendet" aus, wenn:**

   - **Der Empfänger ist:** Gibt ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation an.
   - **Der Empfänger ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an.
   - **Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.

   Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **Beliebigen dieser Kontrollkästchen** angezeigt.

   - Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der werte aus.
   - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.
   - Wenn Sie weitere Werte hinzufügen möchten, klicken Sie in einen leeren Bereich des Felds.
   - Klicken Sie zum Entfernen einzelner Einträge **auf** das Symbol ![ ](../../media/scc-remove-icon.png) "Entfernen" für den Wert.
   - Um die gesamte Bedingung zu entfernen, **klicken** Sie in der Bedingung ![ auf ](../../media/scc-remove-icon.png) "Entfernen".

   Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf "Bedingung **hinzufügen",** und wählen Sie unter "Angewendet" einen verbleibenden Wert **aus, wenn**.

   Klicken Sie zum Hinzufügen von Ausnahmen auf **"Bedingung hinzufügen",** und wählen Sie unter "Außer wenn" **eine Ausnahme aus.** Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

6. Überprüfen Sie **ihre Einstellungen auf** der angezeigten Seite "Einstellungen überprüfen". Sie können **in** jeder Einstellung auf "Bearbeiten" klicken, um sie zu ändern.

   Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien für sichere Links

1. Wechseln Sie im Security & Compliance Center zu **"AtP-sichere** Links" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**

2. Wählen Sie **auf der Seite "Sichere** Links" eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

   Die Richtliniendetails werden in einem Flyout angezeigt.

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Verwenden des Security & Compliance Center zum Ändern von Richtlinien für sichere Links

1. Wechseln Sie im Security & Compliance Center zu **"AtP-sichere** Links" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**

2. Wählen Sie auf der Seite **"Sichere** Links" eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

3. Klicken Sie in den angezeigten Richtliniendetails auf **"Richtlinie bearbeiten".**

Die verfügbaren Einstellungen im angezeigten Flyout sind identisch mit den einstellungen, die im Abschnitt "Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für sichere [Links" beschrieben](#use-the-security--compliance-center-to-create-safe-links-policies) sind.

Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Prioritätsreihenfolge der Richtlinie finden Sie in den folgenden Abschnitten.

### <a name="enable-or-disable-safe-links-policies"></a>Aktivieren oder Deaktivieren von Richtlinien für sichere Links

1. Wechseln Sie im Security & Compliance Center zu **"AtP-sichere** Links" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**

2. Beachten Sie den  Wert in der Statusspalte:

   - Schieben Sie die Umschaltfläche nach links, um die Richtlinie zu deaktivieren: ![Richtlinie deaktivieren](../../media/scc-toggle-off.png).

   - Schieben Sie die Umschaltfläche nach rechts, um die Richtlinie zu aktivieren: ![Richtlinie aktivieren](../../media/scc-toggle-on.png).

### <a name="set-the-priority-of-safe-links-policies"></a>Festlegen der Priorität von Richtlinien für sichere Links

Standardmäßig erhalten Richtlinien für sichere Links eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

Richtlinien für sichere Links werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0).

> [!NOTE]
> Im Security & Compliance Center können Sie die Priorität der Richtlinie für sichere Links erst ändern, nachdem Sie sie erstellt haben. In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Regel für sichere Links erstellen (die sich auf die Priorität vorhandener Regeln auswirken kann).

Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).

1. Wechseln Sie im Security & Compliance Center zu **"AtP-sichere** Links" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**

2. Wählen Sie **auf der Seite "Sichere** Links" eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

3. Klicken Sie in den angezeigten Richtliniendetails auf die Schaltfläche "Verfügbare Priorität":

   - Die Richtlinie für sichere Links mit dem **Prioritätswert** **0** verfügt nur über die Schaltfläche "Priorität **verringern".**

   - Für die Richtlinie für sichere Links mit dem niedrigsten **Prioritätswert** (z. B. **3)** ist nur die Schaltfläche "Priorität **erhöhen"** verfügbar.

   - Wenn Sie über drei oder mehr Richtlinien für sichere Links verfügen, stehen richtlinien zwischen dem höchsten und dem niedrigsten Prioritätswert sowohl die Schaltflächen "Priorität erhöhen" als auch **"Priorität verringern"** zur Verfügung. 

4. Klicken **Sie auf "Priorität erhöhen"** **oder "Priorität verringern",** um den **Prioritätswert zu** ändern.

5. Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Verwenden des Security & Compliance Center zum Entfernen von Richtlinien für sichere Links

1. Wechseln Sie im Security & Compliance Center zu **"AtP-sichere** Links" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**

2. Wählen Sie **auf der Seite "Sichere** Links" eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).

3. Klicken Sie in den angezeigten Richtliniendetails auf "Richtlinie löschen", und klicken Sie dann **im** angezeigten Warndialogfeld auf "Ja".

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Verwenden von Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren von Richtlinien für sichere Links

Wie zuvor beschrieben, besteht eine Richtlinie für sichere Links aus einer Richtlinie für sichere Links und einer Regel für sichere Links.

In PowerShell ist der Unterschied zwischen Richtlinien für sichere Links und Regeln für sichere Links offensichtlich. Richtlinien für sichere Links werden mithilfe der **\* Cmdlets "-SafeLinksPolicy"** und Regeln für sichere Links mithilfe der **\* Cmdlets "-SafeLinksRule"** verwaltet.

- In PowerShell erstellen Sie zuerst die Richtlinie für sichere Links und dann die Regel für sichere Links, die die Richtlinie identifiziert, auf die die Regel angewendet wird.
- In PowerShell ändern Sie die Einstellungen in der Richtlinie für sichere Links und die Regel für sichere Links separat.
- Wenn Sie eine Richtlinie für sichere Links aus PowerShell entfernen, wird die entsprechende Regel für sichere Links nicht automatisch entfernt und umgekehrt.

### <a name="use-powershell-to-create-safe-links-policies"></a>Verwenden von PowerShell zum Erstellen von Richtlinien für sichere Links

Das Erstellen einer Richtlinie für sichere Links in PowerShell besteht aus zwei Schritte:

1. Erstellen Sie die Richtlinie für sichere Links.
2. Erstellen Sie die Regel für sichere Links, die die Richtlinie für sichere Links angibt, auf die die Regel angewendet wird.

> [!NOTE]
> 
> - Sie können eine neue Regel für sichere Links erstellen und ihr eine vorhandene, nicht zugeordnete Richtlinie für sichere Links zuweisen. Eine Regel für sichere Links kann nicht mehreren Richtlinien für sichere Links zugeordnet werden.
> 
> - Sie können die folgenden Einstellungen für neue Richtlinien für sichere Links in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:
> 
>   - Erstellen Sie die neue Richtlinie als deaktiviert _(aktiviert_ `$false` im **Cmdlet "New-SafeLinksRule").**
>   - Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ ) im _\<Number\>_ **Cmdlet "New-SafeLinksRule"** festgelegt.
> 
> - Eine neue Richtlinie für sichere Links, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Regel für sichere Links zuweisen.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Schritt 1: Erstellen einer Richtlinie für sichere Links mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links zu erstellen:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - Details zur Eintragssyntax, die für den Parameter _"DoNotRewriteUrls"_ verwendet werden soll, finden Sie in der Eintragssyntax für die Liste ["Folgende URLs nicht umschreiben".](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)
> 
> - Weitere Syntax, die Sie für den Parameter _"DoNotRewriteUrls"_ verwenden können, wenn Sie vorhandene Richtlinien für sichere Links mithilfe des Cmdlets **"Set-SafeLinksPolicy"** ändern, finden Sie im Abschnitt "Verwenden von [PowerShell](#use-powershell-to-modify-safe-links-policies) zum Ändern von Richtlinien für sichere Links" weiter unten in diesem Artikel.

In diesem Beispiel wird eine Richtlinie für sichere Links namens "Contoso All" mit den folgenden Werten erstellt:

- Aktivieren sie die URL-Überprüfung und -Umschreibung in E-Mail-Nachrichten.
- Aktivieren sie die URL-Überprüfung in Teams (nur TAP-Vorschau).
- Aktivieren Sie die Echtzeitprüfung von angeklickten URLs, einschließlich angeklickter Links, die auf Dateien verweisen.
- Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht zu senden.
- Aktivieren Sie die URL-Überprüfung und -Umschreibung für interne Nachrichten.
- Nachverfolgen von Benutzerklicks im Zusammenhang mit dem Schutz sicherer Links (der Parameter _"DoNotTrackUserClicks"_ wird nicht verwendet, und der Standardwert ist $false, was bedeutet, dass Benutzerklicks nachverfolgt werden).
- Lassen Sie nicht zu, dass Benutzer auf die ursprüngliche URL klicken.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Schritt 2: Erstellen einer Regel für sichere Links mithilfe von PowerShell

Verwenden Sie folgende Syntax, um eine Regel für sichere Links zu erstellen:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In diesem Beispiel wird eine Regel für sichere Links namens "Contoso All" mit den folgenden Bedingungen erstellt:

- Die Regel ist der Richtlinie für sichere Links namens "Contoso All" zugeordnet.
- Die Regel gilt für alle Empfänger in der contoso.com Domäne.
- Da der Parameter _"Priority"_ nicht verwendet wird, wird die Standardpriorität verwendet.
- Die Regel ist aktiviert (der Parameter _"Enabled"_ wird nicht verwendet, und der Standardwert ist `$true` " ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).

### <a name="use-powershell-to-view-safe-links-policies"></a>Anzeigen von Richtlinien für sichere Links mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Links anzeigen zu können:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Übersichtsliste aller Richtlinien für sichere Links zurückgegeben.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

In diesem Beispiel werden detaillierte Informationen für die Richtlinie für sichere Links namens "Contoso Executives" zurückgegeben.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).

### <a name="use-powershell-to-view-safe-links-rules"></a>Verwenden von PowerShell zum Anzeigen von Regeln für sichere Links

Verwenden Sie die folgende Syntax, um vorhandene Regeln für sichere Links anzeigen zu können:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Übersichtsliste aller Regeln für sichere Links zurückgegeben.

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

Sie können eine Richtlinie für sichere Links in PowerShell nicht umbenennen (das **Cmdlet "Set-SafeLinksPolicy"** hat keinen _Parameter "Name")._ Wenn Sie eine Richtlinie für sichere Links im Security & Compliance Center umbenennen, benennen Sie nur die Regel für sichere Links _um._

Die einzige zusätzliche Überlegung zum Ändern von Richtlinien für sichere Links in PowerShell ist die verfügbare Syntax für den Parameter _"DoNotRewriteUrls"_ (die Liste ["Folgende URLs](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)dürfen nicht neu geschrieben werden" ):

- Verwenden Sie die folgende Syntax, um Werte hinzuzufügen, die vorhandene Einträge `"Entry1","Entry2,..."EntryN"` ersetzen:
- Verwenden Sie die folgende Syntax, um Werte ohne Auswirkungen auf andere Einträge hinzuzufügen oder zu entfernen: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine Richtlinie für sichere Links erstellen, wie in Schritt [1 beschrieben:](#step-1-use-powershell-to-create-a-safe-links-policy) Verwenden von PowerShell zum Erstellen eines Richtlinienabschnitts für sichere Links weiter oben in diesem Artikel.

Verwenden Sie folgende Syntax, um eine Richtlinie für sichere Links zu ändern:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).

### <a name="use-powershell-to-modify-safe-links-rules"></a>Verwenden von PowerShell zum Ändern von Regeln für sichere Links

Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine Regel für sichere Links in PowerShell ändern, ist der Parameter _"Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Links finden Sie im nächsten Abschnitt.

Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine Regel erstellen, wie in Schritt [2 beschrieben:](#step-2-use-powershell-to-create-a-safe-links-rule) Verwenden von PowerShell zum Erstellen eines Regelabschnitts für sichere Links weiter oben in diesem Artikel.

Verwenden Sie die folgende Syntax, um eine Regel für sichere Links zu ändern:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für sichere Links

Durch Aktivieren oder Deaktivieren einer Regel für sichere Links in PowerShell wird die gesamte Richtlinie für sichere Links (die Regel für sichere Links und die zugewiesene Richtlinie für sichere Links) aktiviert oder deaktiviert.

Verwenden Sie folgende Syntax, um eine Regel für sichere Links in PowerShell zu aktivieren oder zu deaktivieren:

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) und [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Verwenden von PowerShell zum Festlegen der Priorität von Regeln für sichere Links

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie die folgende Syntax, um die Priorität einer Regel für sichere Links in PowerShell zu festlegen:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den Parameter _"Priority"_ im **Cmdlet "New-SafeLinksRule".**

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-remove-safe-links-policies"></a>Verwenden von PowerShell zum Entfernen von Richtlinien für sichere Links

Wenn Sie PowerShell verwenden, um eine Richtlinie für sichere Links zu entfernen, wird die entsprechende Regel für sichere Links nicht entfernt.

Verwenden Sie folgende Syntax, um eine Richtlinie für sichere Links in PowerShell zu entfernen:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Richtlinie für sichere Links namens "Marketing Department" entfernt.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).

### <a name="use-powershell-to-remove-safe-links-rules"></a>Verwenden von PowerShell zum Entfernen von Regeln für sichere Links

Wenn Sie PowerShell verwenden, um eine Regel für sichere Links zu entfernen, wird die entsprechende Richtlinie für sichere Links nicht entfernt.

Verwenden Sie folgende Syntax, um eine Regel für sichere Links in PowerShell zu entfernen:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die Regel für sichere Links namens "Marketing Department" entfernt.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).

Überprüfen Sie die verfügbaren Microsoft Defender für Office 365-Berichte, um sicherzustellen, dass sichere Links Nachrichten überprüfen. Weitere Informationen finden Sie unter [Anzeigen von Berichten für Defender für Office 365](view-reports-for-atp.md) und Verwenden von Explorer im Security & Compliance [Center](threat-explorer.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Gehen Sie wie folgt vor, um sicherzustellen, dass Richtlinien für sichere Links erfolgreich erstellt, geändert oder entfernt wurden:

- Wechseln Sie im Security & Compliance Center zu **"AtP-sichere** Links" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.** Überprüfen Sie die Liste der Richtlinien, deren **Statuswerte** und ihre **Prioritätswerte.** Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.

- Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie \<Name\> die Einstellungen:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
