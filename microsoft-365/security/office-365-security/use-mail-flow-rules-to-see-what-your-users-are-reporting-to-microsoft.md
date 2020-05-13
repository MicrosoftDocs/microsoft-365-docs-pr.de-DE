---
title: Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Nachrichtenfluss Regeln (auch bekannt als Transportregeln) verwenden, um Kopien von Nachrichten zu erhalten, die Benutzer an Microsoft melden.
ms.openlocfilehash: 3c0ff9556b9800a0c3be22f52d108d6b16cc6657
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213484"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden

In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer gibt es mehrere Möglichkeiten für Benutzer, Nachrichten an Microsoft zur Analyse zu melden, wie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md)beschrieben.

Sie können eine e-Mail-Fluss Regel (auch als Transportregel bezeichnet) erstellen, die nach Nachrichten sucht, die Benutzer an Microsoft melden, und Sie können Bcc-Empfänger so konfigurieren, dass Kopien dieser gemeldeten Nachrichten empfangen werden.

Sie können die Nachrichtenfluss Regel in der Exchange-Verwaltungskonsole (EAC) und in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer) erstellen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie müssen Berechtigungen in Exchange Online oder EoP zugewiesen werden, bevor Sie diese Verfahren ausführen können. Insbesondere müssen Sie die Rolle " **Transport Rules** " erhalten, die standardmäßig der Rollen " **Organisationsverwaltung**", " **Richtlinientreue Verwaltung**" und " **Datensatzverwaltung** " zugewiesen ist. Weitere Informationen finden Sie unter [Verwalten von Rollengruppen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Informationen zum Öffnen des EAC finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) oder [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit einer eigenständigen EoP PowerShell finden Sie unter [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Weitere Informationen zu Nachrichtenfluss Regeln in Exchange Online und eigenständigen EoP finden Sie in den folgenden Themen:

  - [Nachrichtenflussregeln (Transportregeln) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Nachrichtenflussregel-Bedingungen und -Ausnahmen (Prädikate) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Aktionen für Nachrichtenflussregeln in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Erstellen einer e-Mail-Fluss Regel zum Empfangen von Kopien gemeldeter Nachrichten mithilfe der Exchange-Verwaltungskonsole

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) , und wählen Sie dann **neue Regel erstellen**aus.

3. Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein. Beispielsweise Bcc-Nachrichten, die an Microsoft gemeldet wurden.

   - Klicken Sie auf **Weitere Optionen**.

   - **Diese Regel anwenden, wenn**: Wählen Sie **die Empfänger** \> **Adresse enthält eines dieser Wörter**aus: Geben Sie im angezeigten Dialogfeld **Wörter oder Ausdrücke angeben** einen der folgenden Werte ein, klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) , und wiederholen Sie diese Schritte, bis Sie alle Werte eingegeben haben.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Um einen Eintrag zu bearbeiten, wählen Sie ihn aus, und klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-EditIcon.png) . Um einen Eintrag zu entfernen, wählen Sie ihn aus, und klicken Sie auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .

     Klicken Sie nach Abschluss des Vorgangs auf **OK**.

   - **Gehen Sie wie folgt**vor: Wählen Sie Empfänger **Add recipients** \> **zum Feld Bcc**hinzufügen aus. Suchen Sie im angezeigten Dialogfeld die Empfänger, die Sie hinzufügen möchten, und wählen Sie Sie aus. Klicken Sie nach Abschluss des Vorgangs auf **OK**.

4. Sie können eine weitere Auswahl treffen, um die Regel zu überwachen, die Regel zu testen, die Regel während eines bestimmten Zeitraums zu aktivieren und andere Einstellungen. Es wird empfohlen, die Regel zu testen, bevor Sie Sie erzwingen.

5. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Verwenden von PowerShell zum Erstellen einer e-Mail-Fluss Regel zum Empfangen von Kopien gemeldeter Nachrichten

In diesem Beispiel wird eine neue e-Mail-Fluss Regel namens Bcc-Nachrichten an Microsoft erstellt, die nach e-Mail-Nachrichten sucht, die mithilfe der in diesem Thema beschriebenen Methoden an Microsoft gemeldet werden, und fügt die Benutzer Laura@contoso.com und Julia@contoso.com als Bcc-Empfänger hinzu.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie eine Nachrichtenfluss Regel für den Empfang von Kopien gemeldeter Nachrichten konfiguriert haben:

- Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** \> Wählen Sie die Regel \> Klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-EditIcon.png) , und überprüfen Sie die Einstellungen.

- Führen Sie in PowerShell den folgenden Befehl aus, um die Einstellungen zu überprüfen:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Senden Sie eine Testnachricht an eine der Berichts-e-Mail-Adressen, und überprüfen Sie die Ergebnisse.
