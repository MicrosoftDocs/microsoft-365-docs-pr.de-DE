---
title: Anzeigen und Losspeichern von Nachrichten in Quarantäne aus freigegebenen Postfächern
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Benutzer können erfahren, wie sie nachrichten in Quarantäne anzeigen und darauf zugreifen können, die an freigegebene Postfächer gesendet wurden, für die sie über Berechtigungen verfügen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3efccca375745b0850c91039165b72a7d6f0bcb3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931446"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>Anzeigen und Veröffentlichen von Nachrichten in Quarantäne aus freigegebenen Postfächern

> [!NOTE]
> Die in diesem Artikel beschriebenen Features befinden sich derzeit in der Vorschau, sind nicht für alle verfügbar und können geändert werden.

Benutzer können isolierte Nachrichten dort verwalten, wo sie einer der Empfänger sind, wie unter "Suchen und Veröffentlichen von Isolierten Nachrichten" als Benutzer [in EOP beschrieben.](find-and-release-quarantined-messages-as-a-user.md) Aber wie sieht es mit freigegebenen Postfächern aus, bei denen der Benutzer über die Berechtigungen "Vollzugriff" und "Senden als" oder "Senden im Auftrag von" für das Postfach verfügt, wie in den freigegebenen Postfächern [in Exchange Online beschrieben?](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)

Bisher mussten Administratoren, die Benutzern die Verwaltung von Nachrichten in Quarantäne ermöglichen konnten, die an ein freigegebenes Postfach gesendet wurden, die automatischeMapping für das freigegebene Postfach aktiviert lassen (sie ist standardmäßig aktiviert, wenn ein Administrator einem Benutzer Zugriff auf ein anderes Postfach gewährt). Je nach Größe und Anzahl der Postfächer, auf die der Benutzer Zugriff hat,  kann die Leistung jedoch beeinträchtigen, wenn Outlook versucht, alle Postfächer zu öffnen, auf die der Benutzer Zugriff hat. Aus diesem Grund entscheiden sich viele Administratoren dafür, die [automatischeMapping für freigegebene Postfächer zu entfernen.](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)

Jetzt ist die automatischeMapping nicht mehr erforderlich, damit Benutzer isolierte Nachrichten verwalten können, die an freigegebene Postfächer gesendet wurden. Es funktioniert einfach. Es gibt zwei verschiedene Methoden für den Zugriff auf isolierte Nachrichten, die an ein freigegebenes Postfach gesendet wurden:

- Wenn der Administrator Spambenachrichtigungen für Endbenutzer [in](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) Antispamrichtlinien aktiviert hat, kann jeder Benutzer, der  Zugriff auf die Spambenachrichtigungen für Endbenutzer im freigegebenen Postfach hat, auf die Schaltfläche "Überprüfen" in der Benachrichtigung klicken, um im Security & Compliance Center in Quarantäne zu gehen. Beachten Sie, dass mit dieser Methode nur Benutzer isolierte Nachrichten verwalten können, die an das freigegebene Postfach gesendet wurden. Benutzer können in diesem Kontext keine eigenen Quarantänenachrichten verwalten.

- Der Benutzer kann im Security & Compliance Center zur [Quarantäne wechseln.](find-and-release-quarantined-messages-as-a-user.md) Standardmäßig werden nur Nachrichten angezeigt, die an den Benutzer gesendet wurden. Der Benutzer kann jedoch die Sortierergebnisse **(standardmäßig** die Schaltfläche "Nachrichten-ID") in die E-Mail-Adresse des Empfängers **ändern,** die E-Mail-Adresse des freigegebenen Postfachs eingeben und dann auf "Aktualisieren" klicken, um die isolierten Nachrichten zu sehen, die an das freigegebene Postfach gesendet wurden.  

  ![Sortieren von isolierten Nachrichten nach E-Mail-Adresse des Empfängers.](../../media/quarantine-sort-results-by-recipient-email-address.png)

Unabhängig von der Methode können Benutzer Verwirrung vermeiden, indem sie die Spalte **"Empfänger"** für isolierte Nachrichten verwenden. Die maximale Anzahl der anzuzeigende Spalten beträgt 7, daher muss der Benutzer auf Spalten **ändern,** eine vorhandene Spalte  entfernen (z. B. Richtlinientyp), Empfänger auswählen **und** dann auf "Speichern" oder "Als Standard speichern" **klicken.**

  ![Entfernen Sie die Spalte "Richtlinientyp", und fügen Sie die Spalte "Empfänger" der Quarantäne hinzu.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>Dabei ist Folgendes zu berücksichtigen:

- Der erste Benutzer, der auf die isolierte Nachricht zugreift, entscheidet, wie die Nachricht für alle Benutzer des freigegebenen Postfachs ist. Wenn beispielsweise von 10 Benutzern auf ein freigegebenes Postfach zugegriffen wird und ein Benutzer die Quarantänenachricht löscht, wird die Nachricht für alle 10 Benutzer gelöscht. Wenn sich ein Benutzer entschließen, die Nachricht frei zu geben, wird sie für das freigegebene Postfach freigegeben und ist für alle anderen Benutzer des freigegebenen Postfachs zugänglich.

- Derzeit ist die Schaltfläche **"Absender blockieren"** im Flyout **"Details"** für isolierte Nachrichten, die an das freigegebene Postfach gesendet wurden, nicht verfügbar.

- Um isolierte Nachrichten für das freigegebene Postfach in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)zu verwalten, muss der Endbenutzer das Cmdlet ["Get-QuarantineMessage"](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) mit freigegebener Postfach-E-Mail-Adresse für den Wert des Parameters _"RecipientAddress"_ verwenden, um die Nachrichten zu identifizieren. Zum Beispiel:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  Anschließend kann der Endbenutzer eine isolierte Nachricht aus der Liste auswählen, um sie anzeigen oder Aktionen ergreifen zu können.

  In diesem Beispiel werden alle isolierten Nachrichten angezeigt, die an das freigegebene Postfach gesendet wurden, und anschließend wird die erste Nachricht in der Liste aus der Quarantäne entfernt (die erste Nachricht in der Liste ist 0, die zweite ist 1 und so weiter).

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  Ausführliche Informationen zu Syntax und Parametern finden Sie in den folgenden Themen:

  - [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
