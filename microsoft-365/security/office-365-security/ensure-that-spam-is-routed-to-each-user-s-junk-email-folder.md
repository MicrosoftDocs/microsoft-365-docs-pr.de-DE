---
title: Konfigurieren von EOP für Junk-Spam in Hybridumgebungen
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
description: Administratoren können erfahren, wie Sie Spam an Junk-E-Mail-Ordner von Benutzern in einer Exchange Online Protection-Hybridumgebung um routen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 926ac6dec33bf00fc8f0dcd292229e20ccc2b93f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167119"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Konfigurieren von EOP für die Bereitstellung von Spam an den Junk-E-Mail-Ordner in Hybridumgebungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection als eigenständige Lösung](https://go.microsoft.com/fwlink/?linkid=2148611)

> [!IMPORTANT]
> Dieses Thema ist nur für Kunden mit eigenständigem EOP in Hybridumgebungen geeignet. Dieses Thema gilt nicht für Microsoft 365-Kunden mit Exchange Online-Postfächern.

Wenn Sie ein eigenständiger Exchange Online Protection (EOP)-Kunde in einer Hybridumgebung sind, müssen Sie Ihre lokale Exchange-Organisation so konfigurieren, dass die Spamfilterbewertungen von EOP erkannt und übersetzt werden, damit die Junk-E-Mail-Regel im lokalen Postfach Nachrichten in den Junk-E-Mail-Ordner verschieben kann.

Insbesondere müssen Sie Nachrichtenflussregeln (auch als Transportregeln bekannt) in Ihrer lokalen Exchange-Organisation mit Bedingungen erstellen, die Nachrichten mit einem der folgenden EOP-Antispamheader und -Werte finden, und Aktionen, die den SCL (Spam Confidence Level) dieser Nachrichten auf 6 festlegen:

- `X-Forefront-Antispam-Report: SFV:SPM` (Nachricht, die von der Spamfilterung als Spam gekennzeichnet wurde)

- `X-Forefront-Antispam-Report: SFV:SKS` (Nachricht, die von Nachrichtenflussregeln in EOP vor der Spamfilterung als Spam gekennzeichnet wurde)

- `X-Forefront-Antispam-Report: SFV:SKB` (Nachricht, die von der Spamfilterung als Spam gekennzeichnet wurde, weil die E-Mail-Adresse oder E-Mail-Domäne des Absenders in der Liste der blockierten Absender oder der Liste blockierter Domänen in EOP enthalten ist)

Weitere Informationen zu diesen Kopfzeilenwerten finden Sie unter ["Antispam-Nachrichtenkopfzeilen".](anti-spam-message-headers.md)

In diesem Thema wird beschrieben, wie Sie diese Nachrichtenflussregeln im Exchange Admin Center (EAC) und in der Exchange-Verwaltungsshell (Exchange PowerShell) in der lokalen Exchange-Organisation erstellen.

> [!TIP]
> Anstatt die Nachrichten an den Junk-E-Mail-Ordner des lokalen Benutzers zu senden, können Sie Antispamrichtlinien in EOP konfigurieren, um Spamnachrichten in EOP zu isolieren. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Bevor Sie diese Verfahren verwenden können, müssen Ihnen in der lokalen Exchange-Umgebung Berechtigungen zugewiesen werden. Insbesondere muss Ihnen die Rolle **"Transportregeln"** zugewiesen werden, die standardmäßig  den Rollen **"Organisationsverwaltung",** **"Kompatibilitätsverwaltung"** und "Datensatzverwaltung" zugewiesen ist. Weitere Informationen finden Sie unter [Hinzufügen von Mitgliedern zu einer Rollengruppe.](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group)

- Ob und wann eine Nachricht an den Junk-E-Mail-Ordner in einer lokalen Exchange-Organisation zugestellt wird, wird durch eine Kombination der folgenden Einstellungen gesteuert:

  - Der _Wert des Parameters "SCLJunkThreshold"_ im Cmdlet ["Set-OrganizationConfig"](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) in der Exchange-Verwaltungsshell. Der Standardwert ist 4, was bedeutet, dass ein SCL von 5 oder höher die Nachricht an den Junk-E-Mail-Ordner des Benutzers senden sollte.

  - Der _Wert des Parameters "SCLJunkThreshold"_ im Cmdlet ["Set-Mailbox"](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) in der Exchange-Verwaltungsshell. Der Standardwert ist leer ($null), was bedeutet, dass die Organisationseinstellung verwendet wird.

  Weitere Informationen finden Sie unter [SCL (Spam Confidence Level) Schwellenwerte](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)für Exchange.

  - Gibt an, ob die Junk-E-Mail-Regel für das Postfach aktiviert ist (der Wert des Parameters _"Enabled"_ $true im Cmdlet ["Set-MailboxJunkEmailConfiguration"](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) in der Exchange-Verwaltungsshell). Es ist die Junk-E-Mail-Regel, die die Nachricht nach der Zustellung tatsächlich in den Junk-E-Mail-Ordner verschiebt. Standardmäßig ist die Junk-E-Mail-Regel für Postfächer aktiviert. Weitere Informationen finden Sie unter [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).

- Informationen zum Öffnen der EAC auf einem Exchange Server finden Sie im [Exchange Admin Center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center). Informationen zum Öffnen der Exchange-Verwaltungsshell finden Sie unter [Öffnen der Exchange-Verwaltungsshell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).

- Weitere Informationen zu Nachrichtenflussregeln im lokalen Exchange finden Sie in den folgenden Themen:

  - [Nachrichtenflussregeln in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Nachrichtenflussregelbedingungen und Ausnahmen (Prädikate) in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Nachrichtenflussregelaktionen in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Erstellen von Nachrichtenflussregeln, die den SCL von EOP-Spamnachrichten festlegen, mithilfe der EAC

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken **Sie auf das** Symbol ![ "Hinzufügen", und wählen Sie in der angezeigten Dropdownliste "Neue Regel ](../../media/ITPro-EAC-AddIcon.png) erstellen" aus. 

3. Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein. Zum Beispiel:

     - EOP SFV:SPM zu SCL 6

     - EOP SFV:SKS zu SCL 6

     - EOP SFV:SKB zu SCL 6

   - Klicken Sie auf **Weitere Optionen**.

   - **Wenden Sie diese Regel an, wenn**: Select **A message header** includes any of these \> **words**.

     Gehen Sie **in der Kopfzeile "Text eingeben"** mit dem angezeigten Satz "Wörter eingeben" wie folgt vor:

     - Klicken Sie **auf "Text eingeben".** Geben Sie **im angezeigten** Dialogfeld "Kopfzeilennamen angeben" **X-Forefront-Antispam-Report** ein, und klicken Sie dann auf **OK.**

     - Klicken **Sie auf "Wörter eingeben".** Geben  Sie im angezeigten Dialogfeld "Wörter oder Ausdrücke angeben" einen der EOP-Spamheaderwerte (**SFV:SPM**, **SFV:SKS** oder **SFV:SKB)** ein, klicken Sie auf "Hinzufügen" (Symbol) und dann auf  ![ ](../../media/ITPro-EAC-AddIcon.png) **"OK".**

   - **Gehen Sie wie folgt vor:** Wählen **Sie "Nachrichteneigenschaften** \> **ändern" aus, um die SCL (Spam Confidence Level) zu setzen.**

     Wählen Sie **im angezeigten Dialogfeld "SCL** angeben" **die Option 6** aus (der Standardwert ist **5**).

   Wenn Sie fertig sind, klicken Sie auf **"Speichern".**

Wiederholen Sie diese Schritte für die verbleibenden EOP-Spam-Werte (**SFV:SPM**, **SFV:SKS** oder **SFV:SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Verwenden der Exchange-Verwaltungsshell, um Nachrichtenflussregeln zu erstellen, die den SCL von EOP-Spamnachrichten festlegen

Verwenden Sie die folgende Syntax, um die drei Nachrichtenflussregeln zu erstellen:

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

Zum Beispiel:

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

Gehen Sie wie folgt vor, um sicherzustellen, dass Sie EOP für die Bereitstellung von Spam an den Junk-E-Mail-Ordner in einer Hybridumgebung erfolgreich konfiguriert haben:

- Wechseln Sie in der EAC zu **"Nachrichtenflussregeln",** wählen Sie die Regel aus, und klicken Sie dann auf "Bearbeiten", um \> die Einstellungen  ![ zu ](../../media/ITPro-EAC-EditIcon.png) überprüfen.

- Ersetzen Sie in der Exchange-Verwaltungsshell den Namen der Nachrichtenflussregel, und ruln Sie den folgenden Befehl, \<RuleName\> um die Einstellungen zu überprüfen:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- Senden Sie in einem externen E-Mail-System, das ausgehende Nachrichten nicht auf Spam scannt, einen generischen Test auf junk-E-Mail (Junk-E-Mail) an einen betroffenen Empfänger, und vergewissern Sie sich, dass sie an ihren Junk-E-Mail-Ordner zugestellt wurde. Eine GTUBE-Nachricht ähnelt der EICAR-Textdatei (European Institute for Computer Antivirus Research) zum Testen der Schadsoftwareeinstellungen.

  Um eine GTUBE-Nachricht zu senden, fügen Sie den folgenden Text in den Text einer E-Mail-Nachricht in einer zeile ohne Leerzeichen oder Zeilenumbrüche ein:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
