---
title: Anzeigen und Veröffentlichen isolierter Nachrichten aus freigegebenen Postfächern
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
description: Benutzer können erfahren, wie sie Nachrichten in Quarantäne anzeigen und verwenden, die an freigegebene Postfächer gesendet wurden, für die sie über Berechtigungen verfügen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cb42c887df384a418ab01e3a232cdb1f4a7b6e19
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922328"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>Anzeigen und Veröffentlichen isolierter Nachrichten aus freigegebenen Postfächern

> [!NOTE]
> Die in diesem Artikel beschriebenen Features befinden sich derzeit in Der Vorschau, sind nicht für alle verfügbar und können geändert werden.

Benutzer können isolierte Nachrichten dort verwalten, wo sie einer der Empfänger sind, wie unter Suchen und Veröffentlichen von isolierten Nachrichten als Benutzer [in EOP beschrieben.](find-and-release-quarantined-messages-as-a-user.md) Aber wie sieht es mit freigegebenen Postfächern aus, bei denen der Benutzer über vollzugriffs- und Sendeberechtigungen für das Postfach verfügt, wie unter Freigegebene Postfächer [in Exchange Online beschrieben?](/exchange/collaboration-exo/shared-mailboxes)

Zuvor mussten Administratoren die Möglichkeit, isolierte Nachrichten, die an ein freigegebenes Postfach gesendet wurden, für das freigegebene Postfach aktiviert lassen (es ist standardmäßig aktiviert, wenn ein Administrator einem Benutzer Zugriff auf ein anderes Postfach gewährt). Je nach Größe und Anzahl der Postfächer, auf die der Benutzer Zugriff hat,  kann die Leistung jedoch darunter leiden, wenn Outlook versucht, alle Postfächer zu öffnen, auf die der Benutzer Zugriff hat. Aus diesem Grund entscheiden sich viele Administratoren dafür, die [automatischeMapping für freigegebene Postfächer zu entfernen.](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)

Jetzt ist das automatischeMapping nicht mehr erforderlich, damit Benutzer isolierte Nachrichten verwalten können, die an freigegebene Postfächer gesendet wurden. Es funktioniert einfach. Es gibt zwei verschiedene Methoden für den Zugriff auf isolierte Nachrichten, die an ein freigegebenes Postfach gesendet wurden:

- Wenn der Administrator Spambenachrichtigungen für Endbenutzer [in](configure-your-spam-filter-policies.md) Antispamrichtlinien aktiviert hat, kann jeder Benutzer, der  Zugriff auf die Spambenachrichtigungen für Endbenutzer im freigegebenen Postfach hat, auf die Schaltfläche Überprüfen in der Benachrichtigung klicken, um im Security & Compliance Center in Quarantäne zu wechseln. Beachten Sie, dass diese Methode benutzern nur die Verwaltung isolierter Nachrichten ermöglicht, die an das freigegebene Postfach gesendet wurden. Benutzer können in diesem Kontext keine eigenen Quarantänenachrichten verwalten.

- Der Benutzer kann [zur Quarantäne im Security & Compliance Center wechseln.](find-and-release-quarantined-messages-as-a-user.md) Standardmäßig werden nur Nachrichten angezeigt, die an den Benutzer gesendet wurden. Der Benutzer kann jedoch die Sortierergebnisse **(standardmäßig** die Schaltfläche  **Nachrichten-ID)** in Empfänger-E-Mail-Adresse **ändern,** die E-Mail-Adresse des freigegebenen Postfachs eingeben und dann auf Aktualisieren klicken, um die isolierten Nachrichten zu sehen, die an das freigegebene Postfach gesendet wurden.

  ![Sortieren von isolierten Nachrichten nach E-Mail-Adresse des Empfängers.](../../media/quarantine-sort-results-by-recipient-email-address.png)

Unabhängig von der Methode können Benutzer Verwirrung vermeiden, indem sie die **Spalte Empfänger** für isolierte Nachrichten verwenden. Die maximale Anzahl der anzuzeigende Spalten ist 7. Daher muss der Benutzer auf Spalten **ändern,** eine vorhandene Spalte entfernen (z. B. Richtlinientyp), Empfänger auswählen und dann auf **Speichern** oder Als Standard speichern **klicken.** 

  ![Entfernen Sie die Spalte Richtlinientyp, und fügen Sie die Spalte Empfänger zur Quarantäne hinzu.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>Dabei ist Folgendes zu berücksichtigen:

- Der erste Benutzer, der auf die isolierte Nachricht eingreift, bestimmt das Schicksal der Nachricht für alle Benutzer, die das freigegebene Postfach verwenden. Wenn beispielsweise 10 Benutzer auf ein freigegebenes Postfach zugreifen und ein Benutzer die Quarantänenachricht löschen will, wird die Nachricht für alle 10 Benutzer gelöscht. Wenn sich ein Benutzer entschließen sollte, die Nachricht frei zu geben, wird sie für das freigegebene Postfach freigegeben und ist für alle anderen Benutzer des freigegebenen Postfachs zugänglich.

- Derzeit ist die **Schaltfläche Absender blockieren** im **Flyout Details** für isolierte Nachrichten, die an das freigegebene Postfach gesendet wurden, nicht verfügbar.

- Zum Verwalten isolierter Nachrichten für das freigegebene Postfach in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)muss der Endbenutzer das [Cmdlet Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) mit freigegebener Postfach-E-Mail-Adresse für den Wert des _Parameters RecipientAddress_ verwenden, um die Nachrichten zu identifizieren. Beispiel:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  Anschließend kann der Endbenutzer eine isolierte Nachricht aus der Liste auswählen, um eine Aktion zu sehen oder zu ergreifen.

  In diesem Beispiel werden alle isolierten Nachrichten angezeigt, die an das freigegebene Postfach gesendet wurden, und dann die erste Nachricht in der Liste aus der Quarantäne freigegeben (die erste Nachricht in der Liste ist 0, die zweite ist 1 und so weiter).

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  Ausführliche Informationen zu Syntax und Parametern finden Sie in den folgenden Themen:

  - [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)