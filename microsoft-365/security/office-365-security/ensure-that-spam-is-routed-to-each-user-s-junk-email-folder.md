---
title: Konfigurieren von EOP für Junkspam in Hybridumgebungen
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Administratoren erfahren, wie Sie Spam an Junk-E-Mail-Ordner von Benutzern in einer Exchange Online Protection-Hybridumgebung weiterrouten.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae6ee551d04b242891c9638d6d99d79240480d27
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205519"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Konfigurieren von eigenständigem EOP zum Senden von Spam an den Junk-E-Mail-Ordner in Hybridumgebungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection eigenständig](exchange-online-protection-overview.md)

> [!IMPORTANT]
> Dieses Thema gilt nur für eigenständige EOP-Kunden in Hybridumgebungen. Dieses Thema gilt nicht für Microsoft 365-Kunden mit Exchange Online-Postfächern.

Wenn Sie ein eigenständiger Exchange Online Protection (EOP)-Kunde in einer Hybridumgebung sind, müssen Sie Ihre lokale Exchange-Organisation so konfigurieren, dass die Spamfilterungsbewertungen von EOP erkannt und übersetzt werden, damit die Junk-E-Mail-Regel im lokalen Postfach Nachrichten in den Junk-E-Mail-Ordner verschieben kann.

Insbesondere müssen Sie Nachrichtenflussregeln (auch als Transportregeln bekannt) in Ihrer lokalen Exchange-Organisation mit Bedingungen erstellen, die Nachrichten mit einem der folgenden EOP-Antispamkopfzeilen und -Werte finden, und Aktionen, die die Spamsicherheitsstufe (Spam Confidence Level, SCL) dieser Nachrichten auf 6 festlegen:

- `X-Forefront-Antispam-Report: SFV:SPM` (Durch Spamfilterung als Spam markierte Nachricht)

- `X-Forefront-Antispam-Report: SFV:SKS` (nachricht marked as spam by mail flow rules in EOP before spam filtering)

- `X-Forefront-Antispam-Report: SFV:SKB` (nachricht marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)

Weitere Informationen zu diesen Headerwerten finden Sie unter [Antispamnachrichtenkopfzeilen](anti-spam-message-headers.md).

In diesem Thema wird beschrieben, wie Sie diese Nachrichtenflussregeln im Exchange Admin Center (EAC) und in der Exchange-Verwaltungsshell (Exchange PowerShell) in der lokalen Exchange-Organisation erstellen.

> [!TIP]
> Anstatt die Nachrichten an den Junk-E-Mail-Ordner des lokalen Benutzers zu senden, können Sie Antispamrichtlinien in EOP konfigurieren, um Spamnachrichten in EOP zu isolieren. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Bevor Sie diese Verfahren tun können, müssen Ihnen in der lokalen Exchange-Umgebung berechtigungen zugewiesen werden. Insbesondere muss Ihnen die Rolle **Transportregeln** zugewiesen werden, die standardmäßig den Rollen **Organisationsverwaltung,** **Complianceverwaltung** und **Datensatzverwaltung** zugewiesen ist. Weitere Informationen finden Sie unter [Hinzufügen von Mitgliedern zu einer Rollengruppe](/Exchange/permissions/role-group-members#add-members-to-a-role-group).

- Ob und wann eine Nachricht an den Junk-E-Mail-Ordner in einer lokalen Exchange-Organisation übermittelt wird, wird durch eine Kombination der folgenden Einstellungen gesteuert:

  - Der _SCLJunkThreshold-Parameterwert_ im [Cmdlet Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) in der Exchange-Verwaltungsshell. Der Standardwert ist 4, was bedeutet, dass eine SCL von 5 oder höher die Nachricht an den Junk-E-Mail-Ordner des Benutzers senden sollte.

  - Der _SCLJunkThreshold-Parameterwert_ im [Cmdlet Set-Mailbox](/powershell/module/exchange/set-mailbox) in der Exchange-Verwaltungsshell. Der Standardwert ist leer ($null), was bedeutet, dass die Organisationseinstellung verwendet wird.

  Weitere Informationen finden Sie unter [Exchange Spam Confidence Level (SCL) thresholds](/Exchange/antispam-and-antimalware/antispam-protection/scl).

  - Gibt an, ob die Junk-E-Mail-Regel für das Postfach aktiviert ist (der Wert des Parameters _Enabled_ $true im [Cmdlet Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) in der Exchange-Verwaltungsshell). Es ist die Junk-E-Mail-Regel, die die Nachricht nach der Zustellung in den Junk-E-Mail-Ordner verschiebt. Standardmäßig ist die Junk-E-Mail-Regel für Postfächer aktiviert. Weitere Informationen finden Sie unter [Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).

- Informationen zum Öffnen der EAC auf einem Exchange Server finden Sie unter [Exchange Admin Center in Exchange Server](/Exchange/architecture/client-access/exchange-admin-center). Informationen zum Öffnen der Exchange-Verwaltungsshell finden Sie unter [Öffnen der Exchange-Verwaltungsshell](/powershell/exchange/open-the-exchange-management-shell).

- Weitere Informationen zu Nachrichtenflussregeln in lokalen Exchange finden Sie in den folgenden Themen:

  - [E-Mail-Flussregeln in Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Nachrichtenflussregelbedingungen und Ausnahmen (Prädikate) in Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Nachrichtenflussregelaktionen in Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Erstellen von Nachrichtenflussregeln, die die SCL von EOP-Spamnachrichten festlegen, mithilfe der EAC

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken **Sie auf** Hinzufügen ![ (Symbol) und wählen Sie in der ](../../media/ITPro-EAC-AddIcon.png) **angezeigten** Dropdownliste Neue Regel erstellen aus.

3. Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein. Beispiel:

     - EOP SFV:SPM zu SCL 6

     - EOP SFV:SKS zu SCL 6

     - EOP SFV:SKB zu SCL 6

   - Klicken Sie auf **Weitere Optionen**.

   - **Wenden Sie diese Regel an,** wenn : Select **A message header** eines der folgenden Wörter \> **enthält.**

     Gehen Sie **in der Eingabetextkopfzeile mit dem angezeigten** Satz "Wörter eingeben" wie folgt vor:

     - Klicken Sie **auf Text eingeben.** Geben Sie **im angezeigten** Dialogfeld Kopfzeilennamen angeben **X-Forefront-Antispam-Report** ein, und klicken Sie dann auf **OK**.

     - Klicken  **Sie auf Wörter eingeben**. Geben  Sie im angezeigten Dialogfeld Wörter oder Ausdrücke angeben einen der EOP-Spamheaderwerte ein (**SFV:SPM**, **SFV:SKS** oder **SFV:SKB**), klicken Sie auf Hinzufügen  ![ (Symbol) und dann ](../../media/ITPro-EAC-AddIcon.png) auf **OK**.

   - **Gehen Sie wie folgt** vor: Wählen Sie **Nachrichteneigenschaften ändern Festlegen** der Spamsicherheitsstufe \> **(Spam Confidence Level, SCL) aus.**

     Wählen Sie **im angezeigten** Dialogfeld SCL angeben die Option **6** aus (der Standardwert ist **5**).

   Klicken Sie nach Abschluss des Abschlusses auf **Speichern.**

Wiederholen Sie diese Schritte für die verbleibenden EOP-Spam-Verdict-Werte (**SFV:SPM**, **SFV:SKS** oder **SFV:SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Verwenden der Exchange-Verwaltungsshell zum Erstellen von Nachrichtenflussregeln, die die SCL von EOP-Spamnachrichten festlegen

Verwenden Sie die folgende Syntax, um die drei Nachrichtenflussregeln zu erstellen:

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

Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Gehen Sie wie folgt vor, um zu überprüfen, ob Sie die eigenständige EOP erfolgreich konfiguriert haben, um Spam an den Junk-E-Mail-Ordner in der Hybridumgebung zu senden:

- Wechseln Sie in der EAC zu **Nachrichtenflussregeln,** wählen Sie die Regel aus, und klicken Sie dann auf Bearbeiten (Symbol bearbeiten), \> um die Einstellungen  ![ zu ](../../media/ITPro-EAC-EditIcon.png) überprüfen.

- Ersetzen Sie in der Exchange-Verwaltungsshell durch den Namen der Nachrichtenflussregel, und geben Sie den folgenden Befehl zurück, um \<RuleName\> die Einstellungen zu überprüfen:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- Senden Sie in einem externen E-Mail-System, das ausgehende Nachrichten nicht auf Spam scannt, eine allgemeine Testnachricht für unaufgeforderte Massen-E-Mails (GTUBE) an einen betroffenen Empfänger, und vergewissern Sie sich, dass sie an ihren Junk-E-Mail-Ordner zugestellt wird. Eine GTUBE-Nachricht ähnelt der EICAR-Textdatei (European Institute for Computer Antivirus Research) zum Testen der Schadsoftwareeinstellungen.

  Um eine GTUBE-Nachricht zu senden, fügen Sie den folgenden Text in den Textkörper einer E-Mail-Nachricht in einer einzigen Zeile ein, ohne Leerzeichen oder Zeilenumbrüche:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```