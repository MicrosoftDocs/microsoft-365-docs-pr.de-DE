---
title: Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, um Kopien von Nachrichten zu empfangen, die Benutzer an Microsoft melden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 40e87fec3bfd8ed4402713ca7ec45499bb50c68e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287605"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer gibt es mehrere Möglichkeiten für Benutzer, Nachrichten zur Analyse an Microsoft zu melden, wie in "Melden von Nachrichten und Dateien an [Microsoft"](report-junk-email-messages-to-microsoft.md)beschrieben.

Sie können eine Nachrichtenflussregel (auch als Transportregel bezeichnet) erstellen, die nach Nachrichten sucht, die Benutzer an Microsoft melden, und Sie können Bcc-Empfänger für den Empfang von Kopien dieser gemeldeten Nachrichten konfigurieren.

Sie können die Nachrichtenflussregel im Exchange Admin Center (EAC) und in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange #A0 ) erstellen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen die entsprechenden Berechtigungen in Exchange Online oder Exchange Online Protection zugewiesen werden. Insbesondere benötigen Sie die Rolle **"Transportregeln",** die standardmäßig den Rollengruppen  **Organisationsverwaltung,** **Complianceverwaltung** (globale Administratoren) und Datensatzverwaltung zugewiesen ist.

  Weitere Informationen hierzu finden Sie in den folgenden Themen:

  - [Berechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Berechtigungen in EOP als eigenständige Lösung](feature-permissions-in-eop.md)
  - [Ändern der Mitgliederliste in Rollengruppen mithilfe der EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Informationen zum Öffnen der EAC in Exchange Online finden Sie im [Exchange Admin Center in Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center) Informationen zum Öffnen der EAC im eigenständigen EOP finden Sie im [Exchange Admin Center in EOP als eigenständige Lösung.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Weitere Informationen zu Nachrichtenflussregeln in Exchange Online und EOP als eigenständige Lösung finden Sie in den folgenden Themen:
  - [Nachrichtenflussregeln (Transportregeln) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Nachrichtenflussregel-Bedingungen und -Ausnahmen (Prädikate) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Aktionen für Nachrichtenflussregeln in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Erstellen einer Nachrichtenflussregel zum Empfangen von Kopien gemeldeter Nachrichten mithilfe der EAC

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken **Sie auf das** Symbol ![ ](../../media/ITPro-EAC-AddIcon.png) "Hinzufügen", und wählen Sie dann **"Neue Regel erstellen" aus.**

3. Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein. Beispiel: An Microsoft gemeldete Bcc-Nachrichten.

   - Klicken Sie auf **Weitere Optionen**.

   - Wenden Sie diese Regel an, wenn **:** Select **The recipient** address includes any of \> **these words**: In the Specify words or **phrases** dialog that appears, enter one of the following values, click **Add** Add Icon , and repeat ![ until ](../../media/ITPro-EAC-AddIcon.png) you've entered all the values.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     Um einen Eintrag zu bearbeiten, wählen Sie ihn aus, und klicken Sie auf das  ![ ](../../media/ITPro-EAC-EditIcon.png) Bearbeitungssymbol. Um einen Eintrag zu entfernen, wählen Sie ihn aus, und klicken **Sie auf "Entfernen"** ![ ](../../media/ITPro-EAC-DeleteIcon.png) (Symbol).

     Klicken Sie nach Abschluss des Vorgangs auf **OK**.

   - **Gehen Sie wie folgt vor:** Wählen **Sie Empfänger zum** Feld \> **Bcc hinzufügen aus.** Suchen Sie im angezeigten Dialogfeld die Empfänger, die Sie hinzufügen möchten, und wählen Sie sie aus. Klicken Sie nach Abschluss des Vorgangs auf **OK**.

4. Sie können zusätzliche Auswahl treffen, um die Regel zu überwachen, die Regel zu testen, die Regel während eines bestimmten Zeitraums zu aktivieren, und andere Einstellungen. Es wird empfohlen, die Regel zu testen, bevor Sie sie erzwingen.

5. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Verwenden von PowerShell zum Erstellen einer Nachrichtenflussregel zum Empfangen von Kopien gemeldeter Nachrichten

In diesem Beispiel wird eine neue Nachrichtenflussregel namens "Bcc Messages Reported to Microsoft" erstellt, die mithilfe der in diesem Artikel beschriebenen Methoden nach E-Mail-Nachrichten sucht, die an Microsoft gemeldet werden, und die Benutzer laura@contoso.com und julia@contoso.com als Bcc-Empfänger hinzufügt.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Gehen Sie wie folgt vor, um sicherzustellen, dass Sie eine Nachrichtenflussregeln für den Empfang von Kopien der gemeldeten Nachrichten konfiguriert haben:

- Wechseln Sie in der EAC zu **"Nachrichtenflussregeln",** wählen Sie die Regel aus, klicken Sie auf "Bearbeitungssymbol", \>  \> und überprüfen \> Sie die  ![ ](../../media/ITPro-EAC-EditIcon.png) Einstellungen.

- Führen Sie in PowerShell den folgenden Befehl aus, um die Einstellungen zu überprüfen:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Senden Sie eine Testnachrichten an eine der Berichts-E-Mail-Adressen, und überprüfen Sie die Ergebnisse.
