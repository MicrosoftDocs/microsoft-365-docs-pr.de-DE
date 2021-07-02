---
title: Konfigurieren der Übermittlung von Phishingsimulationen von Drittanbietern an Benutzer und ungefilterte Nachrichten an SecOps-Postfächer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Administratoren können erfahren, wie Sie die erweiterte Übermittlungsrichtlinie in Exchange Online Protection (EOP) verwenden, um Nachrichten zu identifizieren, die in bestimmten unterstützten Szenarien (Phishingsimulationen von Drittanbietern und Nachrichten, die an SecOps-Postfächer (Security Operations) übermittelt werden, nicht gefiltert werden sollten.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 053f88da96983b03ad03e75c11a4fa692ac6a850
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256867"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Konfigurieren der Übermittlung von Phishingsimulationen von Drittanbietern an Benutzer und ungefilterte Nachrichten an SecOps-Postfächer

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Das in diesem Artikel beschriebene Feature befindet sich in der Vorschau, ist nicht für alle verfügbar und kann geändert werden.

Um Ihre Organisation [standardmäßig zu schützen,](secure-by-default.md)erlaubt Exchange Online Protection (EOP) keine sicheren Listen oder Filterumgehungen für Nachrichten, die als Schadsoftware oder Phishing mit hoher Vertrauenswürdigkeit identifiziert werden. Es gibt jedoch bestimmte Szenarien, die die Übermittlung ungefilterter Nachrichten erfordern. Beispiel:

- **Phishingsimulationen von Drittanbietern:** Simulierte Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren, bevor sich ein tatsächlicher Angriff auf Ihre Organisation auswirkt.
- **Sicherheitsvorgänge (SecOps) Postfächer:** Dedizierte Postfächer, die von Sicherheitsteams verwendet werden, um ungefilterte Nachrichten zu sammeln und zu analysieren (sowohl gut als auch schlecht).

Sie verwenden die _erweiterte Übermittlungsrichtlinie_ in Microsoft 365, um zu verhindern, dass diese Nachrichten _in diesen spezifischen Szenarien_ gefiltert werden. <sup>\*</sup> Die erweiterte Übermittlungsrichtlinie stellt sicher, dass Nachrichten in diesen Szenarien die folgenden Ergebnisse erzielen:

- Filter in EOP und Microsoft Defender für Office 365 keine Aktion für diese Nachrichten ausführen.<sup>\*</sup>
- [Zero-Hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup>
- [Standardsystemwarnungen](alerts.md) werden für diese Szenarien nicht ausgelöst.
- [AIR und Clustering in Defender für Office 365](office-365-air.md) ignoriert diese Nachrichten.
- Speziell für Phishingsimulationen von Drittanbietern:
  - [Administratorübermittlungen](admin-submission.md) generieren eine automatische Antwort, die besagt, dass die Nachricht Teil einer Phishingsimulationskampagne ist und keine echte Bedrohung ist. Warnungen und AIR werden nicht ausgelöst.
  - [Tresor Links in Defender für Office 365](safe-links.md) blockieren oder detonieren die spezifisch identifizierten URLs in diesen Nachrichten nicht.
  - [Tresor Anlagen in Defender für Office 365](safe-attachments.md) detonieren anlagen in diesen Nachrichten nicht.

<sup>\*</sup> Sie können die Schadsoftwarefilterung oder ZAP für Schadsoftware nicht umgehen.

Nachrichten, die von der erweiterten Übermittlungsrichtlinie identifiziert werden, sind keine Sicherheitsbedrohungen, daher werden die Nachrichten als Systemüberschreibungen gekennzeichnet. Administratoren können diese Systemüberschreibungen in den folgenden Umgebungen filtern und analysieren:

- [Bedrohungs-Explorer/Echtzeiterkennungen in Defender für Office 365 Plan 2](threat-explorer.md)
- Die [Seite "E-Mail-Entität" im Bedrohungs-Explorer/Echtzeiterkennungen](mdo-email-entity-page.md)
- Der [Statusbericht zum Bedrohungsschutz](view-email-security-reports.md#threat-protection-status-report)
- [Erweiterte Suche in Microsoft Defender für Endpunkt](../defender-endpoint/advanced-hunting-overview.md)
- [Kampagnenansichten](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>. To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:
  - Um konfigurierte Einstellungen in der erweiterten Übermittlungsrichtlinie zu erstellen, zu ändern oder zu entfernen, müssen Sie Mitglied der Rollengruppe **"Sicherheitsadministrator"** im **Microsoft 365 Defender-Portal** und Mitglied der **Rollengruppe "Organisationsverwaltung"** in **Exchange Online** sein.
  - Für den schreibgeschützten Zugriff auf die Erweiterte Übermittlungsrichtlinie müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md) und [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > Wenn Sie Benutzer zur entsprechenden Azure Active Directory Rolle hinzufügen, erhalten Benutzer die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Verwenden des Microsoft 365 Defender-Portals zum Konfigurieren von SecOps-Postfächern in der erweiterten Übermittlungsrichtlinie

1. Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-&** \> **Zusammenarbeitsrichtlinien &** Seite \> "Regeln für **Bedrohungsrichtlinien"** im Abschnitt \>  \> **"Erweiterte Zustellung".**

2. Überprüfen Sie auf der Seite **"Erweiterte Zustellung",** ob die Registerkarte **"SecOps-Postfach"** ausgewählt ist, und führen Sie dann einen der folgenden Schritte aus:
   - Klicken Sie auf ![ ](../../media/m365-cc-sc-edit-icon.png) **"Bearbeiten"-Symbol**.
   - Wenn keine konfigurierten Phishingsimulationen vorhanden sind, klicken Sie auf **Hinzufügen.**

3. Geben Sie im Flyout **"SecOps-Postfächer bearbeiten",** das geöffnet wird, ein vorhandenes Exchange Online Postfach ein, das Sie als SecOps-Postfach festlegen möchten, indem Sie einen der folgenden Schritte ausführen:
   - Klicken Sie in das Feld, lassen Sie die Liste der Postfächer auflösen, und wählen Sie dann das Postfach aus.
   - Klicken Sie in das Feld, um einen Bezeichner für das Postfach (Name, Anzeigename, Alias, E-Mail-Adresse, Kontoname usw.) einzugeben, und wählen Sie das Postfach (Anzeigename) aus den Ergebnissen aus.

     Wiederholen Sie diesen Schritt so oft wie nötig. Verteilergruppen sind nicht zulässig.

     Um einen vorhandenen Wert zu entfernen, klicken Sie auf das ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

4. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

Die von Ihnen konfigurierten SecOps-Postfacheinträge werden auf der Registerkarte **"SecOps-Postfach"** angezeigt. Wenn Sie Änderungen vornehmen möchten, klicken Sie ![ auf der Registerkarte auf das ](../../media/m365-cc-sc-edit-icon.png) Bearbeitungssymbol **"Bearbeiten".**

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Verwenden des Microsoft 365 Defender Portals zum Konfigurieren von Phishingsimulationen von Drittanbietern in der erweiterten Übermittlungsrichtlinie

1. Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-&** \> **Zusammenarbeitsrichtlinien &** Seite \> "Regeln für **Bedrohungsrichtlinien"** im Abschnitt \>  \> **"Erweiterte Zustellung".**

2. Wählen Sie auf der Seite **"Erweiterte Übermittlung"** die Registerkarte **"Phishingsimulation"** aus, und führen Sie dann einen der folgenden Schritte aus:
   - Klicken Sie auf ![ ](../../media/m365-cc-sc-edit-icon.png) **"Bearbeiten"-Symbol**.
   - Wenn keine konfigurierten Phishingsimulationen vorhanden sind, klicken Sie auf **Hinzufügen.**

3. Konfigurieren Sie im Flyout **"Phishingsimulation** von Drittanbietern bearbeiten", das geöffnet wird, die folgenden Einstellungen:

   - **Sendende Domäne:** Erweitern Sie diese Einstellung, und geben Sie mindestens eine E-Mail-Adressdomäne (z. B. contoso.com) ein, indem Sie in das Feld klicken, einen Wert eingeben und dann die EINGABETASTE drücken oder den Wert auswählen, der unterhalb des Felds angezeigt wird. Wiederholen Sie diesen Schritt so oft wie nötig. Sie können bis zu 10 Einträge hinzufügen.
   - **Senden der IP:** Erweitern Sie diese Einstellung, und geben Sie mindestens eine gültige IPv4-Adresse ein, indem Sie in das Feld klicken, einen Wert eingeben und dann die EINGABETASTE drücken oder den Wert auswählen, der unter dem Feld angezeigt wird. Wiederholen Sie diesen Schritt so oft wie nötig. Sie können bis zu 10 Einträge hinzufügen. Gültige Werte sind:
     - Single IP: For example, 192.168.1.1.
     - IP-Bereich: Beispiel: 192.168.0.1-192.168.0.254.
     - CIDR-IP: Beispiel: 192.168.0.1/25.
   - **Zuzulassende Simulations-URLs:** Erweitern Sie diese Einstellung, und geben Sie optional bestimmte URLs ein, die Teil Ihrer Phishingsimulationskampagne sind, die nicht blockiert oder detoniert werden soll, indem Sie in das Feld klicken, einen Wert eingeben und dann die EINGABETASTE drücken oder den Wert auswählen, der unter dem Feld angezeigt wird. Sie können bis zu 10 Einträge hinzufügen.

   Um einen vorhandenen Wert zu entfernen, klicken Sie auf das ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

4. Wenn Sie fertig sind, führen Sie einen der folgenden Schritte aus:
   - **First time**: Click **Add**, and then click **Close**.
   - **Vorhandenes bearbeiten:** Klicken Sie auf **"Speichern"** und dann auf **"Schließen".**

Die von Ihnen konfigurierten Einträge für Phishingsimulationen von Drittanbietern werden auf der Registerkarte **"Phishingsimulation"** angezeigt. Wenn Sie Änderungen vornehmen möchten, klicken Sie ![ auf der Registerkarte auf das ](../../media/m365-cc-sc-edit-icon.png) Bearbeitungssymbol **"Bearbeiten".**

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Zusätzliche Szenarien, für die eine Filterumgehung erforderlich ist

Zusätzlich zu den beiden Szenarien, die Ihnen mit der erweiterten Übermittlungsrichtlinie helfen können, gibt es weitere Szenarien, in denen Sie die Filterung umgehen müssen:

- **Filter von Drittanbietern:** Wenn der MX-Eintrag Ihrer Domäne *nicht* auf Office 365 verweist (Nachrichten werden zuerst an eine andere Stelle weitergeleitet), ist [die standardmäßige Sicherheit](secure-by-default.md) nicht *verfügbar.* Wenn Sie Schutz hinzufügen möchten, müssen Sie die erweiterte Filterung für Connectors aktivieren (auch als *Skip-Eintrag* bezeichnet). Weitere Informationen finden Sie unter Verwalten des [Nachrichtenflusses mithilfe eines Clouddiensts eines Drittanbieters mit Exchange Online.](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud) Wenn Sie die erweiterte Filterung für Connectors nicht wünschen, verwenden Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet), um die Microsoft-Filterung für Nachrichten zu umgehen, die bereits von der Drittanbieterfilterung ausgewertet wurden. Weitere Informationen finden Sie unter [Verwenden von Nachrichtenflussregeln, um die SCL in Nachrichten festzulegen.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)

- **Falsch positive Ergebnisse, die überprüft** werden: Möglicherweise möchten Sie bestimmten Nachrichten, die noch von Microsoft über [Administratorübermittlungen](admin-submission.md) analysiert werden, vorübergehend gestatten, bekannte gute Nachrichten zu melden, die fälschlicherweise als falsch für Microsoft gekennzeichnet sind (falsch positive Ergebnisse). Wie bei allen Außerkraftsetzungen wird **_dringend empfohlen,_** dass diese Außerkraftsetzungen temporär sind.

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a>Exchange Online PowerShell-Verfahren für SecOps-Postfächer in der erweiterten Übermittlungsrichtlinie

In Exchange Online PowerShell sind die grundlegenden Elemente von SecOps-Postfächern in der erweiterten Übermittlungsrichtlinie:

- **Die SecOps-Außerkraftsetzungsrichtlinie:** Gesteuert von den **\* -SecOpsOverridePolicy-Cmdlets.**
- **Die SecOps-Überschreibungsregel:** Gesteuert von den **\* -SecOpsOverrideRule-Cmdlets.**

Dieses Verhalten hat die folgenden Ergebnisse:

- Sie erstellen zuerst die Richtlinie, dann die Regel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.
- Wenn Sie eine Richtlinie aus PowerShell entfernen, wird auch die entsprechende Regel entfernt.
- Wenn Sie eine Regel aus PowerShell entfernen, wird die entsprechende Richtlinie nicht entfernt. Sie müssen die entsprechende Richtlinie manuell entfernen.

### <a name="use-powershell-to-configure-secops-mailboxes"></a>Verwenden von PowerShell zum Konfigurieren von SecOps-Postfächern

Das Konfigurieren eines SecOps-Postfachs in der erweiterten Übermittlungsrichtlinie in PowerShell besteht aus zwei Schritten:

1. Erstellen Sie die SecOps-Außerkraftsetzungsrichtlinie.
2. Erstellen Sie die SecOps-Überschreibungsregel, die die Richtlinie angibt, auf die die Regel angewendet wird.

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a>Schritt 1: Verwenden von PowerShell zum Erstellen der SecOps-Außerkraftsetzungsrichtlinie

Verwenden Sie die folgende Syntax, um die SecOps-Außerkraftsetzungsrichtlinie zu erstellen:

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

**Hinweis:** Unabhängig vom angegebenen Namenswert lautet der Richtlinienname SecOpsOverridePolicy, daher können Sie diesen Wert auch verwenden.

In diesem Beispiel wird die SecOps-Postfachrichtlinie erstellt.

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a>Schritt 2: Verwenden von PowerShell zum Erstellen der SecOps-Überschreibungsregel

In diesem Beispiel wird die SecOps-Postfachregel mit den angegebenen Einstellungen erstellt.

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

**Hinweis:****Unabhängig vom angegebenen Namenswert lautet der Regelname SecOpsOverrideRule, wobei es sich um \<GUID\> \<GUID\> einen eindeutigen GUID-Wert handelt (z. B. 6fed4b63-3563-495d-a481-b24a311f8329).

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).

### <a name="use-powershell-to-view-the-secops-override-policy"></a>Verwenden von PowerShell zum Anzeigen der SecOps-Überschreibungsrichtlinie

In diesem Beispiel werden detaillierte Informationen zu der einzigen SecOps-Postfachrichtlinie zurückgegeben.

```powershell
Get-SecOpsOverridePolicy
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SecOpsOverridePolicy".](/powershell/module/exchange/get-secopsoverridepolicy)

### <a name="use-powershell-to-view-secops-override-rules"></a>Verwenden von PowerShell zum Anzeigen von SecOps-Überschreibungsregeln

In diesem Beispiel werden detaillierte Informationen zu SecOps-Überschreibungsregeln zurückgegeben.

```powershell
Get-SecOpsOverrideRule
```

Obwohl der vorherige Befehl nur eine Regel zurückgeben sollte, können alle Regeln, die gelöscht werden müssen, auch in die Ergebnisse einbezogen werden.

In diesem Beispiel werden die gültige Regel (eine) und alle ungültigen Regeln identifiziert.

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

Nachdem Sie die ungültigen Regeln identifiziert haben, können Sie sie mithilfe des Cmdlets **Remove-SecOpsOverrideRule** entfernen, wie [weiter unten in diesem Artikel](#use-powershell-to-remove-secops-override-rules)beschrieben.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SecOpsOverrideRule"](/powershell/module/exchange/get-secopsoverriderule)

### <a name="use-powershell-to-modify-the-secops-override-policy"></a>Verwenden von PowerShell zum Ändern der SecOps-Überschreibungsrichtlinie

Verwenden Sie die folgende Syntax, um die SecOps-Außerkraftsetzungsrichtlinie zu ändern:

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

In diesem Beispiel wird der SecOps-Überschreibungsrichtlinie secops2@contoso.com hinzugefügt.

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

**Hinweis:** Wenn eine zugeordnete, gültige SecOps-Außerkraftsetzungsregel vorhanden ist, werden auch die E-Mail-Adressen in der Regel aktualisiert.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SecOpsOverridePolicy".](/powershell/module/exchange/set-secopsoverridepolicy)

### <a name="use-powershell-to-modify-a-secops-override-rule"></a>Verwenden von PowerShell zum Ändern einer SecOps-Überschreibungsregel

Das Cmdlet **"Set-SecOpsOverrideRule"** ändert die E-Mail-Adressen in der SecOps-Überschreibungsregel nicht. Verwenden Sie das Cmdlet **"Set-SecOpsOverridePolicy", um die E-Mail-Adressen in der SecOps-Überschreibungsregel zu** ändern.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SecOpsOverrideRule".](/powershell/module/exchange/set-secopsoverriderule)

### <a name="use-powershell-to-remove-the-secops-override-policy"></a>Verwenden von PowerShell zum Entfernen der SecOps-Überschreibungsrichtlinie

In diesem Beispiel werden die SecOps-Postfachrichtlinie und die entsprechende Regel entfernt.

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).

### <a name="use-powershell-to-remove-secops-override-rules"></a>Verwenden von PowerShell zum Entfernen von SecOps-Überschreibungsregeln

Verwenden Sie die folgende Syntax, um eine SecOps-Überschreibungsregel zu entfernen:

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

In diesem Beispiel wird die angegebene SecOps-Überschreibungsregel entfernt.

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Exchange Online PowerShell-Verfahren für Phishingsimulationen von Drittanbietern in der erweiterten Übermittlungsrichtlinie

In Exchange Online PowerShell sind die grundlegenden Elemente von Phishingsimulationen von Drittanbietern in der erweiterten Übermittlungsrichtlinie:

- **Die Richtlinie zur Außerkraftsetzung der Phishingsimulation:** Gesteuert von den Cmdlets **\* "-PhishSimOverridePolicy".**
- **Die Überschreibungsregel für die Phishingsimulation:** Gesteuert von den **\* -PhishSimOverrideRule-Cmdlets.**

Dieses Verhalten hat die folgenden Ergebnisse:

- Sie erstellen zuerst die Richtlinie und dann die Regel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.
- Sie ändern die Einstellungen in der Richtlinie und der Regel separat.
- Wenn Sie eine Richtlinie aus PowerShell entfernen, wird auch die entsprechende Regel entfernt.
- Wenn Sie eine Regel aus PowerShell entfernen, wird die entsprechende Richtlinie nicht entfernt. Sie müssen die entsprechende Richtlinie manuell entfernen.

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a>Verwenden von PowerShell zum Konfigurieren von Phishingsimulationen von Drittanbietern

Das Konfigurieren einer Phishingsimulation eines Drittanbieters in der erweiterten Übermittlungsrichtlinie in PowerShell besteht aus zwei Schritten:

1. Erstellen Sie die Richtlinie für die Außerkraftsetzung der Phishingsimulation.
2. Erstellen Sie die Überschreibungsregel für die Phishingsimulation, die die Richtlinie angibt, für die die Regel gilt.

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a>Schritt 1: Verwenden von PowerShell zum Erstellen der Richtlinie zur Außerkraftsetzung der Phishingsimulation

In diesem Beispiel wird die Richtlinie für die Außerkraftsetzung der Phishingsimulation erstellt.

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

**Hinweis:** Unabhängig vom angegebenen Namenswert lautet der Richtlinienname PhishSimOverridePolicy, daher können Sie diesen Wert auch verwenden.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a>Schritt 2: Verwenden von PowerShell zum Erstellen der Außerkraftsetzungsregel für Phishingsimulationen

Verwenden Sie die folgende Syntax:

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

Unabhängig vom angegebenen Namenswert lautet der Regelname PhishSimOverrideRule, wobei es sich um \<GUID\> \<GUID\> einen eindeutigen GUID-Wert handelt (z. B. a0eae53e-d755-4a42-9320-b9c6b55c5011).

Ein gültiger IP-Adresseintrag ist einer der folgenden Werte:

- Single IP: For example, 192.168.1.1.
- IP-Bereich: Beispiel: 192.168.0.1-192.168.0.254.
- CIDR-IP: Beispiel: 192.168.0.1/25.

In diesem Beispiel wird die Überschreibungsregel für die Phishingsimulation mit den angegebenen Einstellungen erstellt.

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a>Verwenden von PowerShell zum Anzeigen der Richtlinie zur Außerkraftsetzung der Phishingsimulation

In diesem Beispiel werden detaillierte Informationen zu der einzigen Außerkraftsetzungsrichtlinie für Phishingsimulationen zurückgegeben.

```powershell
Get-PhishSimOverridePolicy
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-PhishSimOverridePolicy".](/powershell/module/exchange/get-phishsimoverridepolicy)

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a>Verwenden von PowerShell zum Anzeigen von Überschreibungsregeln für Phishingsimulationen

In diesem Beispiel werden detaillierte Informationen zu Überschreibungsregeln für Phishingsimulationen zurückgegeben.

```powershell
Get-PhishSimOverrideRule
```

Obwohl der vorherige Befehl nur eine Regel zurückgeben sollte, können alle Regeln, die gelöscht werden müssen, auch in die Ergebnisse einbezogen werden.

In diesem Beispiel werden die gültige Regel (eine) und alle ungültigen Regeln identifiziert.

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

Nachdem Sie die ungültigen Regeln identifiziert haben, können Sie sie mithilfe des Cmdlets **Remove-PhisSimOverrideRule** entfernen, wie [weiter unten in diesem Artikel](#use-powershell-to-remove-phishing-simulation-override-rules)beschrieben.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-PhishSimOverrideRule".](/powershell/module/exchange/get-phishsimoverriderule)

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a>Verwenden von PowerShell zum Ändern der Richtlinie für die Außerkraftsetzung der Phishingsimulation

Verwenden Sie die folgende Syntax, um die Richtlinie für die Außerkraftsetzung der Phishingsimulation zu ändern:

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

In diesem Beispiel wird die Richtlinie für die Außerkraftsetzung der Phishingsimulation deaktiviert.

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-PhishSimOverridePolicy".](/powershell/module/exchange/set-phishsimoverridepolicy)

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a>Verwenden von PowerShell zum Ändern einer Überschreibungsregel für Phishingsimulationen

Verwenden Sie die folgende Syntax, um die Außerkraftsetzungsregel für phishingsimulationen zu ändern:

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

In diesem Beispiel wird die angegebene Außerkraftsetzungsregel für Phishingsimulationen mit den folgenden Einstellungen geändert:

- Fügen Sie den Domäneneintrag blueyonderairlines.com hinzu.
- Entfernen Sie den IP-Adresseintrag 192.168.1.55.

Beachten Sie, dass sich diese Änderungen nicht auf vorhandene Einträge auswirken.

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-PhishSimOverrideRule".](/powershell/module/exchange/set-phishsimoverriderule)

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a>Verwenden von PowerShell zum Entfernen einer Richtlinie zur Außerkraftsetzung einer Phishingsimulation

In diesem Beispiel werden die Richtlinie für die Außerkraftsetzung der Phishingsimulation und die entsprechende Regel entfernt.

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a>Verwenden von PowerShell zum Entfernen von Außerkraftsetzungsregeln für Phishingsimulationen

Verwenden Sie die folgende Syntax, um eine Außerkraftsetzungsregel für Phishingsimulationen zu entfernen:

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

In diesem Beispiel wird die angegebene Überschreibungsregel für phishingsimulationen entfernt.

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).
