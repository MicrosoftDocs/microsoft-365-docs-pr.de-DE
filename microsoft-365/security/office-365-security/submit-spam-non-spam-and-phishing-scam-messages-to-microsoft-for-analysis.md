---
title: Manuelles übermitteln von Nachrichten an Microsoft zur Analyse
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Sie und Ihre Benutzer können falsche Negative und falsch positive Spamnachrichten zur Analyse an Microsoft übermitteln. '
ms.openlocfilehash: 77807f710743d98dc2e1564f804b6a67add67def
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529049"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Manuelles übermitteln von Nachrichten an Microsoft zur Analyse

> [!NOTE]
> Wenn Sie ein Administrator in einer Office 365 Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungen-Portal im Office 365 Security & Compliance Center zu verwenden. Weitere Informationen finden Sie unter [Verwenden der Administrator Übermittlung zum Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft](admin-submission.md).

Es kann frustrierend sein, wenn Benutzer in Ihrer Organisation Junk-Nachrichten (Spam) oder Phishing-Nachrichten in Ihrem Posteingang empfangen oder wenn Sie keine legitime e-Mail-Nachricht erhalten, weil Sie als Junk gekennzeichnet ist. Wir optimieren unsere Spamfilter ständig, um genauere Angaben zu machen.

Sie und Ihre Benutzer können diesen Prozess unterstützen, indem Sie falsch positive Ergebnisse (gute e-Mail-Nachrichten als ungültig markiert), falsche Negative Zeichen (ungültige e-Mail-Nachricht) und Phishing-Nachrichten zur Analyse an Microsoft senden.

> [!NOTE]
> Aufgrund der hohen Anzahl von Übermittlungen, die wir erhalten, können wir möglicherweise nicht alle Anfragen zur Analyse beantworten.

## <a name="submit-false-negatives-to-microsoft"></a>Senden von falschen negativen an Microsoft

> [!TIP]
> Anstatt die folgenden Verfahren zum Melden von falsch negativen Daten zu verwenden, können Benutzer in Outlook und Outlook im Internet (früher als Outlook Web App bezeichnet) das Add-in "Berichtsnachricht" für Microsoft Outlook verwenden. Informationen zum Installieren und verwenden dieses Tools finden Sie unter [enable the Report Message Add-in](enable-the-report-message-add-in.md).

Wenn Sie eine Nachricht erhalten, die durch die Spamfilterung geleitet wurde, die als Spam oder Phishing identifiziert werden sollte, können Sie die Nachricht nach Bedarf an die Microsoft-Spam Analyse-und Microsoft-Phishing-Analyseteams senden. Die Analysten überprüfen die Nachricht und fügen Sie den Dienst weiten Filtern hinzu, wenn Sie die Klassifizierungskriterien erfüllen.

1. Erstellen Sie eine neue, leere e-Mail-Nachricht mit einem der folgenden Empfänger:

   - **Junk**:`junk@office365.microsoft.com`

   - **Phishing**:`phish@office365.microsoft.com`

2. Ziehen Sie die Junk-oder Phishing-Nachricht per Drag & Drop in die neue Nachricht. Dadurch wird die Junk-oder Phishing-Nachricht als Anlage in der neuen Nachricht gespeichert. Kopieren und Einfügen des Inhalts der Nachricht oder Weiterleiten der Nachricht (die ursprüngliche Nachricht ist erforderlich, damit die Nachrichtenkopfzeilen überprüft werden können).

   > [!NOTE]
   > <ul><li>Sie können mehrere Nachrichten in der neuen Nachricht anfügen. Stellen Sie sicher, dass alle Nachrichten vom gleichen Typ sind: entweder Phishing-Scam-Nachrichten oder Junk-e-Mail-Nachrichten.</li><li>Lassen Sie den Nachrichtentext leer.</li><li>Verwenden Sie entweder msg (Outlook-Standardformat) oder eml (standardmäßige Outlook im Internetformat) für die angefügten Nachrichten.</li></ul>

3. Wenn Sie fertig sind, klicken Sie auf **senden**.

> [!TIP]
> Administratoren haben verschiedene Möglichkeiten, bestimmte Nachrichten, die fälschlicherweise als Spam identifiziert werden, zu blockieren. Ausführliche Informationen finden Sie unter [Create blocked Sender Lists in Office 365](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Senden von falsch positiven Ergebnissen an Microsoft

> [!TIP]
> Anstatt die folgenden Verfahren zum Melden von falsch positiven Ergebnissen zu verwenden, können Benutzer in Outlook und Outlook im Internet das Add-in "Berichtsnachricht" für Microsoft Outlook verwenden. Informationen zum Installieren und verwenden dieses Tools finden Sie unter [enable the Report Message Add-in](enable-the-report-message-add-in.md).

Wenn eine Nachricht fälschlicherweise als Spam identifiziert wurde, können Sie die Nachricht an das Microsoft-Spam Analyse Team übermitteln. Die Analysten bewerten die Nachricht, und (abhängig von den Ergebnissen der Analyse) können die Dienst weiten Filter so angepasst werden, dass die Nachricht durchlassen wird.

1. Erstellen Sie eine neue, leere e- `not_junk@office365.microsoft.com` Mail-Nachricht mit als Empfänger:

2. Ziehen Sie die nicht identifizierte Nachricht per Drag & Drop in die neue Nachricht. Dadurch wird die nicht identifizierte Nachricht als Anlage in der neuen Nachricht gespeichert. Kopieren und Einfügen des Inhalts der Nachricht oder Weiterleiten der Nachricht (die ursprüngliche Nachricht ist erforderlich, damit die Nachrichtenkopfzeilen überprüft werden können).

   > [!NOTE]
   > <ul><li>Sie können mehrere Nachrichten in der neuen Nachricht anfügen. Stellen Sie sicher, dass alle Nachrichten vom gleichen Typ sind: entweder Phishing-Nachrichten oder Junk-e-Mail-Nachrichten.</li><li>Lassen Sie den Nachrichtentext leer.</li><li>Verwenden Sie entweder msg (Outlook-Standardformat) oder eml (standardmäßige Outlook im Internetformat) für die angefügten Nachrichten.</li></ul>

3. Wenn Sie fertig sind, klicken Sie auf **senden**.

> [!TIP]
> Administratoren haben verschiedene Möglichkeiten, um zu ermöglichen, dass bestimmte Nachrichten die Spamfilterung überspringen. Ausführliche Informationen finden Sie unter [Create Safe Sender Lists in Office 365](create-safe-sender-lists-in-office-365.md).

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Erstellen einer e-Mail-Fluss Regel zum Empfangen von Kopien von Nachrichten, die an Microsoft gemeldet werden

Sie können eine e-Mail-Fluss Regel (auch als Transportregel bezeichnet) erstellen, die nach e-Mail-Nachrichten sucht, die an Microsoft mithilfe der in diesem Thema beschriebenen Methoden gemeldet werden, und Sie können Bcc-Empfänger so konfigurieren, dass Kopien dieser gemeldeten Nachrichten empfangen werden.

Sie können die Nachrichtenfluss Regel in der Exchange-Verwaltungskonsole (EAC) und in PowerShell (Exchange Online PowerShell für Office 365 Kunden erstellen; Exchange Online Protection PowerShell für eigenständige EoP-Kunden).

### <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie müssen Berechtigungen in Exchange Online zugewiesen werden, bevor Sie diese Verfahren ausführen können. Insbesondere müssen Sie die Rolle " **Transport Rules** " erhalten, die standardmäßig der Rollen " **Organisationsverwaltung**", " **Richtlinientreue Verwaltung**" und " **Datensatzverwaltung** " zugewiesen ist. Weitere Informationen finden Sie unter [Verwalten von Rollengruppen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Informationen zum Öffnen des EAC in Exchange Online finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Weitere Informationen zu Nachrichtenfluss Regeln in Exchange Online und eigenständigen EoP finden Sie in den folgenden Themen:

  - [Nachrichtenflussregeln (Transportregeln) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Nachrichtenflussregel-Bedingungen und -Ausnahmen (Prädikate) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Aktionen für Nachrichtenflussregeln in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Erstellen einer e-Mail-Fluss Regel zum Empfangen von Kopien gemeldeter Nachrichten mithilfe der Exchange-Verwaltungskonsole

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken Sie auf Add](../../media/ITPro-EAC-AddIcon.png) -Symbol **Hinzufügen** ![, und wählen Sie dann **neue Regel erstellen**aus.

3. Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein. Beispielsweise Bcc-Nachrichten, die an Microsoft gemeldet wurden.

   - Klicken Sie auf **Weitere Optionen**.

   - **Diese Regel anwenden, wenn**: Wählen Sie **die Empfänger** \> **Adresse enthält eines dieser Wörter**aus: Geben Sie im angezeigten Dialogfeld **Wörter oder Ausdrücke angeben** einen der folgenden Werte ein, klicken Sie auf](../../media/ITPro-EAC-AddIcon.png)Add-Symbol **Hinzufügen** ![, und wiederholen Sie diese Schritte, bis Sie alle Werte eingegeben haben.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Um einen Eintrag zu bearbeiten, wählen Sie ihn **Edit** ![aus, und](../../media/ITPro-EAC-EditIcon.png)klicken Sie auf Bearbeitungssymbol bearbeiten. Um einen Eintrag zu entfernen, wählen Sie ihn **Remove** ![aus, und](../../media/ITPro-EAC-DeleteIcon.png)klicken Sie auf entfernen-Symbol entfernen.

     Klicken Sie nach Abschluss des Vorgangs auf **OK**.

   - **Gehen Sie wie folgt**vor: Wählen Sie Empfänger \> **zum Feld Bcc** **Hinzufügen** aus. Suchen Sie im angezeigten Dialogfeld die Empfänger, die Sie hinzufügen möchten, und wählen Sie Sie aus. Klicken Sie nach Abschluss des Vorgangs auf **OK**.

4. Sie können eine weitere Auswahl treffen, um die Regel zu überwachen, die Regel zu testen, die Regel während eines bestimmten Zeitraums zu aktivieren und andere Einstellungen. Es wird empfohlen, die Regel zu testen, bevor Sie Sie erzwingen.

5. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Verwenden von PowerShell zum Erstellen einer e-Mail-Fluss Regel zum Empfangen von Kopien gemeldeter Nachrichten

In diesem Beispiel wird eine neue e-Mail-Fluss Regel namens Bcc-Nachrichten an Microsoft erstellt, die nach e-Mail-Nachrichten sucht, die mithilfe der in diesem Thema beschriebenen Methoden an Microsoft gemeldet werden, und fügt die Benutzer Laura@contoso.com und Julia@contoso.com als Bcc-Empfänger hinzu.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie eine Nachrichtenfluss Regel für den Empfang von Kopien gemeldeter Nachrichten konfiguriert haben:

- Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** \> \> wählen Sie die Regel](../../media/ITPro-EAC-EditIcon.png)klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![, und überprüfen Sie die Einstellungen.

- Führen Sie in PowerShell den folgenden Befehl aus, um die Einstellungen zu überprüfen:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Senden Sie eine Testnachricht an eine der Berichts-e-Mail-Adressen, und überprüfen Sie die Ergebnisse.
