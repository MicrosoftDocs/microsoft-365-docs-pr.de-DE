---
title: Konfigurieren von EoP für Junk-Spam in Hybrid Umgebungen
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Spam an Benutzer-Junk-e-Mail-Ordner in einer Exchange Online Protection Hybrid-Umgebung weiterleiten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15acc9ad87fa0c785998895d026dae036d9ddd7b
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547664"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Konfigurieren von eigenständigen EoP zur Zustellung von Spam an den Junk-e-Mail-Ordner in Hybrid Umgebungen

> [!IMPORTANT]
> Dieses Thema ist nur für eigenständige EoP-Kunden in Hybrid Umgebungen geeignet. Dieses Thema gilt nicht für Microsoft 365-Kunden mit Exchange Online Postfächern.

Wenn Sie ein eigenständiger Exchange Online Schutz-Kunde (EoP) in einer Hybridumgebung sind, müssen Sie Ihre lokale Exchange-Organisation so konfigurieren, dass Sie die Spamfilter Urteile von EoP erkennt und übersetzt, sodass die Junk-e-Mail-Regel im lokalen Postfach Nachrichten in den Junk-e-Mail-Ordner verschieben kann.

Insbesondere müssen Sie Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) in Ihrer lokalen Exchange-Organisation mit Bedingungen erstellen, die Nachrichten mit einem der folgenden EoP-Antispam-Header und-Werte und Aktionen, die die SCL-Bewertung (Spam Confidence Level) dieser Nachrichten festlegen, auf 6 finden:

- `X-Forefront-Antispam-Report: SFV:SPM` (Nachricht als Spam durch Spamfilterung gekennzeichnet)

- `X-Forefront-Antispam-Report: SFV:SKS` (Nachricht als Spam durch Nachrichtenfluss Regeln in EoP vor Spamfilterung markiert)

- `X-Forefront-Antispam-Report: SFV:SKB` (Nachricht als Spam durch Spamfilterung gekennzeichnet, da sich die e-Mail-Adresse des Absenders oder die e-Mail-Domäne in der Liste blockierter Absender oder in der Liste der blockierten Domänen in EoP befindet)

Weitere Informationen zu diesen Headerwerten finden Sie unter [Anti-Spam Message Headers](anti-spam-message-headers.md).

In diesem Thema wird beschrieben, wie Sie diese Nachrichtenfluss Regeln in der Exchange-Verwaltungskonsole und in der Exchange-Verwaltungsshell (Exchange PowerShell) in der lokalen Exchange-Organisation erstellen.

> [!TIP]
> Anstatt die Nachrichten an den Junk-e-Mail-Ordner des lokalen Benutzers zu übermitteln, können Sie in EoP Antispam-Richtlinien konfigurieren, um Spamnachrichten in EoP zu isolieren. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie müssen Berechtigungen in der lokalen Exchange-Umgebung zugewiesen werden, bevor Sie diese Verfahren ausführen können. Insbesondere müssen Sie die Rolle " **Transport Rules** " erhalten, die standardmäßig der Rollen " **Organisationsverwaltung**", " **Richtlinientreue Verwaltung**" und " **Datensatzverwaltung** " zugewiesen ist. Weitere Informationen finden Sie unter [Hinzufügen von Mitgliedern zu einer Rollengruppe](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).

- Wenn eine Nachricht an den Junk-e-Mail-Ordner in einer lokalen Exchange-Organisation übermittelt wird, wird durch eine Kombination der folgenden Einstellungen gesteuert:

  - Der Wert des _SCLJunkThreshold_ -Parameters im Cmdlet " [OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) " in der Exchange-Verwaltungsshell. Der Standardwert ist 4, was bedeutet, dass ein SCL von 5 oder höher die Nachricht an den Junk-e-Mail-Ordner des Benutzers übermitteln soll.

  - Der Wert des _SCLJunkThreshold_ -Parameters im Cmdlet "Set [-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) " im Exchange-Verwaltungsshell. Der Standardwert ist leer ($null), was bedeutet, dass die Organisations Einstellung verwendet wird.

  Ausführliche Informationen finden Sie unter [Exchange Spam Confidence Level (SCL) Schwellenwerte](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).

  - Gibt an, ob die Junk-e-Mail-Regel für das Postfach aktiviert ist (der Parameterwert _Enabled_ ist $true im Cmdlet " [MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) " im Exchange-Verwaltungsshell). Es handelt sich um die Junk-e-Mail-Regel, die die Nachricht nach der Zustellung in den Junk-e-Mail-Ordner verschiebt. Standardmäßig ist die Junk-e-Mail-Regel für Postfächer aktiviert. Weitere Informationen finden Sie unter [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).

- Informationen zum Öffnen des EAC auf einem Exchange Server finden Sie unter [Exchange Admin Center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center). Informationen zum Öffnen des Exchange-Verwaltungsshell finden Sie unter [Öffnen des Exchange-Verwaltungsshell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).

- Weitere Informationen zu Nachrichtenfluss Regeln in lokalen Exchange finden Sie in den folgenden Themen:

  - [Nachrichtenfluss Regeln in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Nachrichtenfluss Regel-Bedingungen und-Ausnahmen (Prädikate) in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Aktionen für Nachrichtenfluss Regeln in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Verwenden der Exchange-Verwaltungskonsole zum Erstellen von Nachrichtenfluss Regeln zum Festlegen der SCL-Bewertung von EoP-Spamnachrichten

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken Sie auf Add-Symbol **Hinzufügen** , ![ ](../../media/ITPro-EAC-AddIcon.png) und wählen Sie in der angezeigten Dropdownliste **neue Regel erstellen** aus.

3. Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein. Beispiel:

     - EoP SFV: SPM zu SCL-Bewertung 6

     - EoP SFV: SKS zu SCL-Bewertung 6

     - EoP SFV: SKB to SCL 6

   - Klicken Sie auf **Weitere Optionen**.

   - **Diese Regel anwenden, wenn**: Wählen Sie **einen Nachrichtenkopf** \> **mit einem beliebigen dieser Wörter**aus.

     Führen Sie in der **Kopfzeile Text eingeben** die folgenden Schritte aus, um Wörter Satz eingeben, der angezeigt wird:

     - Klicken Sie auf **Text eingeben**. Geben Sie im angezeigten Dialogfeld **Kopfzeile angeben** den Namen **X-Forefront-Antispam-Report** ein, und klicken Sie dann auf **OK**.

     - Klicken Sie auf  **Wörter eingeben**. Geben Sie im daraufhin angezeigten Dialogfeld **Wörter oder Ausdrücke angeben** einen der EoP-Spam Headerwerte ein (**SFV: SPM**, **SFV: SKS**oder **SFV: SKB**), klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) , und klicken Sie dann auf **OK**.

   - **Gehen Sie folgen**dermaßen vor: Wählen Sie **ändern die Nachrichteneigenschaften** \> **Festlegen der SCL-Bewertung (Spam Confidence Level)**.

     Wählen Sie im angezeigten **SCL** -Dialogfeld die Option **6** (der Standardwert ist **5**) aus.

   Wenn Sie fertig sind, klicken Sie auf **Speichern**

Wiederholen Sie diese Schritte für die restlichen EoP-Spam Urteils Werte (**SFV: SPM**, **SFV: SKS**oder **SFV: SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Verwenden der Exchange-Verwaltungsshell zum Erstellen von Nachrichtenfluss Regeln, die die SCL-Bewertung von EoP-Spamnachrichten festlegen

Verwenden Sie die folgende Syntax, um die drei Nachrichtenfluss Regeln zu erstellen:

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

Beispiel:

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie den eigenständigen EoP erfolgreich für die Zustellung von Spam an den Junk-e-Mail-Ordner in einer Hybridumgebung konfiguriert haben:

- Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**, wählen Sie die Regel **Edit** aus, und klicken Sie dann auf ![ Bearbeitungssymbol bearbeiten, ](../../media/ITPro-EAC-EditIcon.png) um die Einstellungen zu überprüfen.

- Ersetzen Sie im Exchange-Verwaltungsshell \<RuleName\> durch den Namen der e-Mail-Fluss Regel, und Regel Sie den folgenden Befehl, um die Einstellungen zu überprüfen:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- Senden Sie in einem externen e-Mail-System **, das ausgehende Nachrichten nicht nach Spam scannt**, einen generischen Test für unangeforderte Massen-e-Mail (GTUBE) an einen betroffenen Empfänger, und vergewissern Sie sich, dass er an den Junk-e-Mail-Ordner gesendet wird. Eine GTUBE-Nachricht ähnelt der EICAR-Textdatei (European Institute for Computer Antivirus Research) zum Testen der Schadsoftwareeinstellungen.

  Um eine GTUBE-Nachricht zu senden, fügen Sie den folgenden Text in den Textkörper einer e-Mail-Nachricht in einer einzelnen Zeile ohne Leerzeichen oder Zeilenumbrüche ein:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
