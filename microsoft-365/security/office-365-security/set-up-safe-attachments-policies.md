---
title: Einrichten Tresor Anlagenrichtlinien in Microsoft Defender für Office 365
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
description: Erfahren Sie, wie Sie Tresor Anlagenrichtlinien definieren, um Ihre Organisation vor schädlichen Dateien in E-Mails zu schützen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e516a16ff28c762e154fd908312df65ea48699bc
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108223"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Einrichten Tresor Anlagenrichtlinien in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](whats-new-in-defender-for-office-365.md) verfügen. Wenn Sie ein Privatbenutzer sind, der nach Informationen zum Scannen von Anlagen in Outlook sucht, finden Sie weitere Informationen unter [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Tresor Anlagen ist ein Feature in [Microsoft Defender für Office 365,](whats-new-in-defender-for-office-365.md) das eine virtuelle Umgebung verwendet, um Anlagen in eingehenden E-Mail-Nachrichten zu überprüfen, nachdem sie vom [Antischadsoftwareschutz in Exchange Online Protection (EOP)](anti-malware-protection.md)gescannt wurden, jedoch vor der Übermittlung an Empfänger. Weitere Informationen finden Sie unter [Tresor Anlagen in Microsoft Defender für Office 365](safe-attachments.md).

Es gibt keine integrierte oder standardmäßige richtlinie für Tresor Anlagen. Um Tresor Anlagenüberprüfung von E-Mail-Nachrichtenanlagen zu erhalten, müssen Sie eine oder mehrere Tresor Anlagenrichtlinien erstellen, wie in diesem Artikel beschrieben.

Sie können Tresor Anlagenrichtlinien im Microsoft 365 Defender Portal oder in PowerShell konfigurieren (Exchange Online PowerShell für berechtigte Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer, aber mit Defender für Office 365 Add-On-Abonnements).

Die grundlegenden Elemente einer Tresor Attachments-Richtlinie sind:

- Die Richtlinie für **sichere Anlagen:** Gibt die Aktionen für unbekannte Schadsoftwareerkennungen an, gibt an, ob Nachrichten mit Schadsoftwareanlagen an eine angegebene E-Mail-Adresse gesendet werden sollen und ob Nachrichten übermittelt werden sollen, wenn Tresor Attachments-Überprüfung nicht abgeschlossen werden kann.
- **Die Regel für sichere Anlagen:** Gibt die Prioritäts- und Empfängerfilter an (für wen die Richtlinie gilt).

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Tresor Anlagenrichtlinien im Microsoft 365 Defender Portal verwalten:

- Wenn Sie eine Tresor Anlagenrichtlinie erstellen, erstellen Sie tatsächlich eine Regel für sichere Anlagen und die zugeordnete Richtlinie für sichere Anlagen gleichzeitig mit demselben Namen für beide.
- Wenn Sie eine Tresor Anlagenrichtlinie ändern, ändern Einstellungen im Zusammenhang mit dem Namen, der Priorität, aktiviert oder deaktiviert und empfängerfiltern die Regel für sichere Anlagen. Alle anderen Einstellungen ändern die zugeordnete Richtlinie für sichere Anlagen.
- Wenn Sie eine Tresor Anlagenrichtlinie entfernen, werden die Regel für sichere Anlagen und die zugehörige Richtlinie für sichere Anlagen entfernt.

In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt. Weitere Informationen finden Sie im Abschnitt ["Use Exchange Online PowerShell or standalone EOP PowerShell to configure Tresor Attachments policies"](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) weiter unten in diesem Artikel.

> [!NOTE]
> Im globalen Einstellungsbereich von Tresor Anlageneinstellungen konfigurieren Sie Features, die nicht von Tresor Anlagenrichtlinien abhängig sind. Anweisungen finden Sie unter [Aktivieren von Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) und Tresor Dokumente in [Microsoft 365 E5](safe-docs.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>. To go directly to the **Tresor Attachments** page, use <https://security.microsoft.com/safeattachmentv2> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie benötigen Berechtigungen, bevor Sie die Verfahren in diesem Artikel ausführen können:
  - Um Tresor Anlagenrichtlinien zu erstellen, zu ändern und zu löschen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** im Microsoft 365 Defender-Portal **und** Mitglied der Rollengruppe **"Organisationsverwaltung"** in Exchange Online sein.
  - Für den schreibgeschützten Zugriff auf Tresor Anlagenrichtlinien müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** im Microsoft 365 Defender Portal sein.

  Weitere Informationen finden Sie unter ["Berechtigungen" im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md) und ["Berechtigungen" in Exchange Online.](/exchange/permissions-exo/permissions-exo)

  **Hinweise**:

  - Wenn Sie Benutzer zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center hinzufügen, erhalten Benutzer die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Unsere empfohlenen Einstellungen für Tresor Anlagenrichtlinien finden Sie unter [Tresor Anlageneinstellungen.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

- Es kann bis zu 30 Minuten dauern, bis eine neue oder aktualisierte Richtlinie angewendet wird.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a>Verwenden des Microsoft 365 Defender Portals zum Erstellen Tresor Anlagenrichtlinien

Beim Erstellen einer benutzerdefinierten Tresor Anlagenrichtlinie im Microsoft 365 Defender Portal werden die Regel für sichere Anlagen und die zugehörige Richtlinie für sichere Anlagen gleichzeitig mit demselben Namen für beide erstellt.

1. Wechseln Sie im Microsoft 365 Defender Portal zur Seite Richtlinien für **E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für Die \> **Bedrohungsregeln** \>  Tresor \> **Anlagen.**

2. Klicken Sie auf der Seite **Tresor Anlagen** auf das ![ Symbol ](../../media/m365-cc-sc-create-icon.png) **"Erstellen".**

3. Der Richtlinienassistent wird geöffnet. Konfigurieren Sie auf der Seite **"Richtlinie benennen"** die folgenden Einstellungen:
   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.
   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

4. Identifizieren Sie auf der angezeigten Seite **"Benutzer und Domänen"** die internen Empfänger, für die die Richtlinie gilt (Empfängerbedingungen):
   - **Benutzer**: Die angegebenen Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.
   - **Gruppen**: Die angegebenen Verteilergruppen, E-Mail-aktivierten Sicherheitsgruppen oder Microsoft 365-Gruppen in Ihrer Organisation.
   - **Domänen**: Alle Empfänger in der angegebenen [akzeptierten Domäne](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in Ihrer Organisation.

   Klicken Sie auf das entsprechende Feld, beginnen Sie mit der Eingabe eines Wertes, und wählen Sie den gewünschten Wert aus den Ergebnissen aus. Wiederholen Sie diesen Vorgang so oft wie nötig. Um einen vorhandenen Wert zu entfernen, klicken Sie auf das ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

   Für Benutzer oder Gruppen können Sie die meisten Bezeichner verwenden (Name, Anzeigename, Alias, E-Mail-Adresse, Kontoname usw.), aber in den Ergebnissen wird der entsprechende Anzeigename angezeigt. Geben Sie für Benutzer einen einzelnen Stern (\*) ein, um alle verfügbaren Werte anzuzeigen.

   Mehreren Werten in der gleichen Bedingung verwenden die „ODER“-Logik (z. B. _\<recipient1\>_ ODER _\<recipient2\>_). Unterschiedlichen Bedingungen verwenden die „UND“-Logik (z. B. _\<recipient1\>_ UND _\<member of group 1\>_).

   - **Ausschließen dieser Benutzer, Gruppen und Domänen**: Um Ausnahmen für die internen Empfänger hinzuzufügen, für welche die Richtlinie gilt (Empfängerausnahmen), wählen Sie diese Option und konfigurieren Sie die Ausnahmen. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

5. Konfigurieren Sie auf der **seite Einstellungen** die folgenden Einstellungen:

   - **Tresor Attachments unknown malware response:** Select one of the following values:
     - **Aus:** In der Regel wird dieser Wert nicht empfohlen.
     - **Überwachen**
     - **Block**: Dies ist der Standardwert und der empfohlene Wert in den [voreingestellten Standard- und Strict-Sicherheitsrichtlinien.](preset-security-policies.md)
     - **Replace**
     - **Dynamische Zustellung (Vorschaufeature)**

     Diese Werte werden in [den Richtlinieneinstellungen für Tresor Anlagen](safe-attachments.md#safe-attachments-policy-settings)erläutert.

   - **Umleiten von Nachrichten mit erkannten Anlagen:** Wenn Sie **"Umleitung aktivieren"** auswählen, können Sie eine E-Mail-Adresse in den **Nachrichten senden angeben, die blockierte, überwachte oder ersetzte Anlagen an das angegebene E-Mail-Adressfeld enthalten,** um Nachrichten zu senden, die Schadsoftwareanlagen zur Analyse und Untersuchung enthalten.

     Die Empfehlung für Standard- und Strict-Richtlinieneinstellungen besteht darin, die Umleitung zu aktivieren. Weitere Informationen finden Sie unter [Tresor Anlageneinstellungen.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

   - **Wenden Sie die Erkennungsantwort Tresor Anlagen an, wenn die Überprüfung nicht abgeschlossen werden kann (Timeout oder Fehler):** Die durch Tresor Anlagen angegebene **Antwort auf unbekannte Schadsoftware** wird für Nachrichten ausgeführt, auch wenn Tresor Attachments-Überprüfung nicht abgeschlossen werden kann. Wenn Sie diese Option ausgewählt haben, wählen Sie immer **Umleitung aktivieren** aus, und geben Sie eine E-Mail-Adresse an, um Nachrichten zu senden, die Schadsoftwareanlagen enthalten. Andernfalls können Nachrichten verloren gegangen sein.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

6. Überprüfen Sie auf der angezeigten Seite **Überprüfung** Ihre Einstellungen. Sie können in jedem Abschnitt **Bearbeiten** auswählen, um die Einstellungen in diesem Abschnitt zu ändern. Alternativ können Sie auf **Zurück** klicken oder die entsprechende Seite im Assistenten auswählen.

   Klicken Sie nach Abschluss des Vorgangs auf **Senden**.

7. Klicken Sie in der angezeigten Bestätigungsseite auf **Fertig**.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a>Verwenden des Microsoft 365 Defender Portals zum Anzeigen Tresor Anlagenrichtlinien

1. Wechseln Sie im Microsoft 365 Defender Portal zur Seite Richtlinien für **E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für Die \> **Bedrohungsregeln** \>  Tresor \> **Anlagen.**

2. Auf der Seite **Tresor Anlagen** werden die folgenden Eigenschaften in der Liste der Richtlinien angezeigt:
   - **Name**
   - **Status**
   - **Priorität**

3. Wenn Sie eine Richtlinie auswählen, indem Sie auf den Namen klicken, werden die Richtlinieneinstellungen in einem Flyout angezeigt.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a>Verwenden des Microsoft 365 Defender Portals zum Ändern Tresor Anlagenrichtlinien

1. Wechseln Sie im Microsoft 365 Defender Portal zur Seite Richtlinien für **E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für Die \> **Bedrohungsregeln** \>  Tresor \> **Anlagen.**

2. Wählen Sie auf der Seite **Tresor Anlagen** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.

3. Wählen Sie im angezeigten Flyout für die Richtliniendetails in jedem Abschnitt die Option **Bearbeiten** aus, um die Einstellungen innerhalb des Abschnitts zu ändern. Weitere Informationen zu den Einstellungen finden Sie im Abschnitt ["Verwenden des Microsoft 365 Defender Portals zum Erstellen Tresor Anlagenrichtlinien"](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) weiter oben in diesem Artikel.  

Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Reihenfolge der Richtlinienpriorität finden Sie in den folgenden Abschnitten.

### <a name="enable-or-disable-safe-attachments-policies"></a>Aktivieren oder Deaktivieren Tresor Anlagenrichtlinien

1. Wechseln Sie im Microsoft 365 Defender Portal zur Seite Richtlinien für **E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für Die \> **Bedrohungsregeln** \>  Tresor \> **Anlagen.**

2. Wählen Sie auf der Seite **Tresor Anlagen** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.

3. Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie einen der folgenden Werte sehen:
   - **Richtlinie deaktiviert**: Um die Richtlinie zu aktivieren, klicken Sie auf ![Symbol „Aktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivieren**.
   - **Richtlinie aktiviert**: Um die Richtlinie zu deaktivieren, klicken Sie auf ![Symbol „Deaktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Deaktivieren**.

4. Klicken Sie im angezeigten Bestätigungsdialog auf **Aktivieren** oder **Deaktivieren**.

5. Klicken Sie im Flyout der Richtliniendetails auf **Schließen**.

Zurück auf der Richtlinien-Hauptseite wird der Wert **Status** der Richtlinie **Aktiviert** oder **Deaktiviert** sein.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Festlegen der Priorität von Tresor Anlagenrichtlinien

Standardmäßig erhalten Tresor Anlagenrichtlinien eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

Tresor Anlagenrichtlinien werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0).

**Hinweis:** Im Microsoft 365 Defender Portal können Sie die Priorität der Richtlinie Tresor Anlagen erst ändern, nachdem Sie sie erstellt haben. In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Regel für sichere Anlagen erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).

Um die Priorität einer Richtlinie zu ändern, klicken Sie in den Eigenschaften einer Richtlinie auf **Priorität erhöhen** oder **Priorität verringern** (Sie können den Zahlenwert der **Priorität** im Microsoft 365 Defender-Portal nicht direkt modifizieren). Die Priorität einer Richtlinie zu verändern macht nur Sinn, wenn Sie mehrere Richtlinien haben.

1. Wechseln Sie im Portal Microsoft 365 Defender zur Seite Richtlinien für **E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für \> **Bedrohungsregeln** \>  Tresor \> **Anlagen.**

2. Wählen Sie auf der Seite **Tresor Anlagen** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.

3. Oben im angezeigten Flyout für Richtliniendetails wird angezeigt, wie Sie die **Priorität** erhöhen oder **verringern,** basierend auf dem aktuellen Prioritätswert und der Anzahl der Richtlinien:
   - Für die Richtlinie mit dem **Prioritätswert** **0** ist nur die Option **"Priorität verringern"** verfügbar.
   - Für die Richtlinie mit dem niedrigsten **Prioritätswert** (z. B. **3)** ist nur die Option **"Priorität erhöhen"** verfügbar.
   - Wenn Sie über drei oder mehr Richtlinien verfügen, stehen für die Richtlinien zwischen den Werten mit der höchsten und der niedrigsten Priorität die Optionen **"Priorität erhöhen"** und **"Verringern"** zur Verfügung.

   Klicken Sie auf ![Symbol „Priorität erhöhen“](../../media/m365-cc-sc-increase-icon.png) **Priorität erhöhen** oder ![Symbol „Priorität verringern“](../../media/m365-cc-sc-decrease-icon.png) **Priorität verringern**, um den **Prioritätswert** zu ändern.

4. Wenn Sie den Vorgang abgeschlossen haben, klicken Sie im Flyout der Richtliniendetails auf **Schließen**.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a>Verwenden des Microsoft 365 Defender Portals zum Entfernen Tresor Anlagenrichtlinien

1. Wechseln Sie im Portal Microsoft 365 Defender zur Seite Richtlinien für **E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für \> **Bedrohungsregeln** \>  Tresor \> **Anlagen.**

2. Wählen Sie auf der Seite **Tresor Anlagen** eine benutzerdefinierte Richtlinie aus der Liste aus, indem Sie auf den Namen der Richtlinie klicken.

3. Ganz oben auf dem angezeigten Flyout der Richtliniendetails klicken Sie auf ![Symbol „Weiter Aktionen“](../../media/m365-cc-sc-more-actions-icon.png) **Weitere Aktionen** \> ![Symbol „Richtlinie löschen“](../../media/m365-cc-sc-delete-icon.png) **Richtlinie löschen**.

4. Klicken Sie im angezeigten Bestätigungsdialog auf **Ja**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies&quot;></a>Verwenden Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren Tresor Anlagenrichtlinien

Wie zuvor beschrieben besteht eine richtlinie für Tresor Anlagen aus einer Richtlinie für sichere Anlagen und einer Regel für sichere Anlagen.

In PowerShell ist der Unterschied zwischen Richtlinien für sichere Anlagen und Regeln für sichere Anlagen offensichtlich. Sie verwalten Richtlinien für sichere Anlagen mithilfe der Cmdlets **\* &quot;-SafeAttachmentPolicy&quot;,** und Sie verwalten Regeln für sichere Anlagen mithilfe der Cmdlets **\* &quot;-SafeAttachmentRule&quot;.**

- In PowerShell erstellen Sie zuerst die Richtlinie für sichere Anlagen und dann die Regel für sichere Anlagen, die die Richtlinie identifiziert, für die die Regel gilt.
- In PowerShell ändern Sie die Einstellungen in der Richtlinie für sichere Anlagen und die Regel für sichere Anlagen separat.
- Wenn Sie eine Richtlinie für sichere Anlagen aus PowerShell entfernen, wird die entsprechende Regel für sichere Anlagen nicht automatisch entfernt und umgekehrt.

### <a name=&quot;use-powershell-to-create-safe-attachments-policies&quot;></a>Verwenden von PowerShell zum Erstellen Tresor Anlagenrichtlinien

Das Erstellen einer Tresor Anlagenrichtlinie in PowerShell besteht aus zwei Schritten:

1. Erstellen Sie die Richtlinie für sichere Anlagen.
2. Erstellen Sie die Regel für sichere Anlagen, die die Richtlinie für sichere Anlagen angibt, auf die die Regel angewendet wird.

 **Hinweise**:

- Sie können eine neue Regel für sichere Anlagen erstellen und ihr eine vorhandene, nicht zugeordnete Richtlinie für sichere Anlagen zuweisen. Eine Regel für sichere Anlagen kann nicht mehr als einer Richtlinie für sichere Anlagen zugeordnet werden.

- Sie können die folgenden Einstellungen für neue Richtlinien für sichere Anlagen in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Microsoft 365 Defender Portal verfügbar sind:
  - Erstellen Sie die neue Richtlinie als deaktiviert _(aktiviert_ `$false` im Cmdlet **&quot;New-SafeAttachmentRule").**
  - Legen Sie die Priorität der Richtlinie während der Erstellung _(Priorität)_ _\<Number\>_ im Cmdlet **"New-SafeAttachmentRule"** fest.

- Eine neue Richtlinie für sichere Anlagen, die Sie in PowerShell erstellen, ist erst im Microsoft 365 Defender-Portal sichtbar, wenn Sie die Richtlinie einer Regel für sichere Anlagen zuweisen.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für sichere Anlagen

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Anlagen zu erstellen:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

In diesem Beispiel wird eine Richtlinie für sichere Anlagen namens "Contoso All" mit den folgenden Werten erstellt:

- Blockieren Sie Nachrichten, die gefunden werden, dass sie Schadsoftware enthalten, indem Tresor Dokumente scannen (der _Parameter "Action"_ wird nicht verwendet, und der Standardwert lautet `Block` ).
- Die Umleitung ist aktiviert, und Nachrichten, die Schadsoftware enthalten, werden zur Analyse und Untersuchung an sec-ops@contoso.com gesendet.
- Wenn Tresor Attachments-Überprüfung nicht verfügbar ist oder Fehler auftreten, übermitteln Sie die Nachricht nicht (wir verwenden den _Parameter ActionOnError_ nicht und der Standardwert lautet `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel für sichere Anlagen

Verwenden Sie die folgende Syntax, um eine Regel für sichere Anlagen zu erstellen:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In diesem Beispiel wird eine Regel für sichere Anlagen mit dem Namen "Contoso All" mit den folgenden Bedingungen erstellt:

- Die Regel ist der Richtlinie für sichere Anlagen mit dem Namen "Contoso All" zugeordnet.
- Die Regel gilt für alle Empfänger in der contoso.com Domäne.
- Da der Parameter _"Priority"_ nicht verwendet wird, wird die Standardpriorität verwendet.
- Die Regel ist aktiviert (wir verwenden nicht den Parameter _Enabled,_ und der Standardwert lautet `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Verwenden von PowerShell zum Anzeigen von Richtlinien für sichere Anlagen

Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Anlagen anzuzeigen:

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SafeAttachmentPolicy".](/powershell/module/exchange/get-safeattachmentpolicy)

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

In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Anlagen mit dem Namen "Contoso Executives" zurückgegeben.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Verwenden von PowerShell zum Ändern von Richtlinien für sichere Anlagen

Sie können eine Richtlinie für sichere Anlagen in PowerShell nicht umbenennen (das Cmdlet **"Set-SafeAttachmentPolicy"** hat keinen _Name-Parameter)._ Wenn Sie eine Tresor Anlagenrichtlinie im Microsoft 365 Defender-Portal umbenennen, werden Sie nur die _Regel für_ sichere Anlagen umbenennen.

Andernfalls sind die gleichen Einstellungen verfügbar, wenn Sie eine Richtlinie für sichere Anlagen erstellen, wie im [Abschnitt "Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für sichere Anlagen"](#step-1-use-powershell-to-create-a-safe-attachment-policy) weiter oben in diesem Artikel beschrieben.

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Anlagen zu ändern:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeAttachmentPolicy".](/powershell/module/exchange/set-safeattachmentpolicy)

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Verwenden von PowerShell zum Ändern von Regeln für sichere Anlagen

Die einzige Einstellung, die beim Ändern einer Regel für sichere Anlagen in PowerShell nicht verfügbar ist, ist der _Parameter "Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Anlagen finden Sie im nächsten Abschnitt.

Andernfalls sind die gleichen Einstellungen verfügbar, wenn Sie eine Regel wie im [Abschnitt "Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel](#step-2-use-powershell-to-create-a-safe-attachment-rule) für sichere Anlagen" weiter oben in diesem Artikel beschrieben erstellen.

Verwenden Sie die folgende Syntax, um eine Regel für sichere Anlagen zu ändern:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeAttachmentRule".](/powershell/module/exchange/set-safeattachmentrule)

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für sichere Anlagen

Das Aktivieren oder Deaktivieren einer Regel für sichere Anlagen in PowerShell aktiviert oder deaktiviert die gesamte Tresor Anlagenrichtlinie (die Regel für sichere Anlagen und die Richtlinie für zugewiesene sichere Anlagen).

Verwenden Sie die folgende Syntax, um eine Regel für sichere Anlagen in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die Regel für sichere Anlagen mit dem Namen "Marketing Department" deaktiviert.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) und [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>Verwenden von PowerShell zum Festlegen der Priorität von Regeln für sichere Anlagen

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie die folgende Syntax, um die Priorität einer Regel für sichere Anlagen in PowerShell festzulegen:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Hinweis:** Um die Priorität einer neuen Regel beim Erstellen festzulegen, verwenden Sie stattdessen den Parameter _"Priority"_ im Cmdlet **"New-SafeAttachmentRule".**

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeAttachmentRule".](/powershell/module/exchange/set-safeattachmentrule)

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>Verwenden von PowerShell zum Entfernen sicherer Anlagenrichtlinien

Wenn Sie PowerShell zum Entfernen einer Richtlinie für sichere Anlagen verwenden, wird die entsprechende Regel für sichere Anlagen nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Anlagen in PowerShell zu entfernen:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Richtlinie für sichere Anlagen mit dem Namen "Marketing Department" entfernt.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>Verwenden von PowerShell zum Entfernen von Regeln für sichere Anlagen

Wenn Sie PowerShell zum Entfernen einer Regel für sichere Anlagen verwenden, wird die entsprechende Richtlinie für sichere Anlagen nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Regel für sichere Anlagen in PowerShell zu entfernen:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die Regel für sichere Anlagen mit dem Namen "Marketing Department" entfernt.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Tresor Anlagenrichtlinien erfolgreich erstellt, geändert oder entfernt haben:

- Wechseln Sie im Portal Microsoft 365 Defender zur Seite Richtlinien für **E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für \> **Bedrohungsregeln** \>  Tresor \> **Anlagen.** Überprüfen Sie die Liste der Richtlinien, ihre **Statuswerte** und ihre **Prioritätswerte.** Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, indem Sie auf den Namen klicken, und zeigen Sie die Details im Flyout an.

- Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Um zu überprüfen, ob Tresor Anlagen Nachrichten überprüft, überprüfen Sie den verfügbaren Defender auf Office 365 Berichte. Weitere Informationen finden Sie unter [Anzeigen von Berichten für Defender für Office 365](view-reports-for-mdo.md) und Verwenden von Explorer im Microsoft 365 Defender [Portal.](threat-explorer.md)
