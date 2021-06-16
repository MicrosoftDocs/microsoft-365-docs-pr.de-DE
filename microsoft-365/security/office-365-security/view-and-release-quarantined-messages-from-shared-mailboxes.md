---
title: Anzeigen und Freigeben von isolierten Nachrichten aus freigegebenen Postfächern
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
description: Benutzer können erfahren, wie sie isolierte Nachrichten anzeigen und bearbeiten, die an freigegebene Postfächer gesendet wurden, für die sie über Berechtigungen verfügen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d6aed4a6e3bc725635558a5e8394b671d11f47c
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929851"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>Anzeigen und Freigeben von isolierten Nachrichten aus freigegebenen Postfächern

> [!NOTE]
> Die in diesem Artikel beschriebenen Features befinden sich derzeit in der Vorschau, sind nicht für alle verfügbar und können geändert werden.

Benutzer können isolierte Nachrichten verwalten, wenn sie einer der Empfänger sind, wie unter [Suchen und Freigeben von isolierten Nachrichten als Benutzer in EOP](find-and-release-quarantined-messages-as-a-user.md)beschrieben. Aber wie sieht es mit freigegebenen Postfächern aus, in denen der Benutzer über Vollzugriff und die Berechtigung "Senden als" oder "Senden im Auftrag von" für das Postfach verfügt, wie [in "Freigegebene Postfächer" in Exchange Online](/exchange/collaboration-exo/shared-mailboxes)beschrieben?

Bisher war die Möglichkeit für Benutzer, isolierte Nachrichten zu verwalten, die an ein freigegebenes Postfach gesendet wurden, erforderlich, dass Administratoren die automatische Zuordnung für das freigegebene Postfach aktiviert lassen (sie ist standardmäßig aktiviert, wenn ein Administrator einem Benutzer Zugriff auf ein anderes Postfach gewährt). Abhängig von der Größe und Anzahl der Postfächer, auf die der Benutzer Zugriff hat, kann die Leistung jedoch beeinträchtigt werden, wenn Outlook versucht, *alle* Postfächer zu öffnen, auf die der Benutzer Zugriff hat. Aus diesem Grund entscheiden sich viele Administratoren [dafür, die automatische Zuordnung für freigegebene Postfächer](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)zu entfernen.

Jetzt ist das automatischeMapping für Benutzer nicht mehr erforderlich, um isolierte Nachrichten zu verwalten, die an freigegebene Postfächer gesendet wurden. Es funktioniert einfach. Es gibt zwei verschiedene Methoden für den Zugriff auf isolierte Nachrichten, die an ein freigegebenes Postfach gesendet wurden:

- Wenn der Administrator [Spambenachrichtigungen für Endbenutzer in Antispamrichtlinien aktiviert](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)hat, kann jeder Benutzer, der Zugriff auf die Spambenachrichtigungen des Endbenutzers im freigegebenen Postfach hat, auf die Schaltfläche **"Überprüfen"** in der Benachrichtigung klicken, um im Microsoft 365 Defender-Portal in Quarantäne zu gehen. Beachten Sie, dass diese Methode benutzern nur das Verwalten von isolierten Nachrichten ermöglicht, die an das freigegebene Postfach gesendet wurden. Benutzer können in diesem Kontext keine eigenen Quarantänenachrichten verwalten.

- Der Benutzer kann [zur Quarantäne im Microsoft 365 Defender-Portal wechseln.](find-and-release-quarantined-messages-as-a-user.md) Standardmäßig werden nur Nachrichten angezeigt, die an den Benutzer gesendet wurden. Der Benutzer kann jedoch die **Sortierergebnisse** (standardmäßig die **Schaltfläche "Nachrichten-ID")** in die **E-Mail-Adresse** des Empfängers ändern, die E-Mail-Adresse des freigegebenen Postfachs eingeben und dann auf **"Aktualisieren"** klicken, um die isolierten Nachrichten anzuzeigen, die an das freigegebene Postfach gesendet wurden.

  ![Sortieren von isolierten Nachrichten nach Empfänger-E-Mail-Adresse.](../../media/quarantine-sort-results-by-recipient-email-address.png)

Unabhängig von der Methode können Benutzer Verwirrung vermeiden, indem sie die Spalte **"Empfänger"** für isolierte Nachrichten einschließen. Die maximale Anzahl der anzuzeigenden Spalten ist 7. Daher muss der Benutzer auf **Spalten ändern** klicken, eine vorhandene Spalte entfernen (z. B. **Richtlinientyp),** **Empfänger** auswählen und dann auf **"Speichern"** oder **"Als Standard speichern"** klicken.

  ![Entfernen Sie die Spalte "Richtlinientyp", und fügen Sie die Spalte "Empfänger" hinzu, die unter Quarantäne gestellt werden soll.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>Dabei ist Folgendes zu berücksichtigen:

- Der erste Benutzer, der auf die isolierte Nachricht reagiert, entscheidet den Empfänger der Nachricht für alle, die das freigegebene Postfach verwenden. Wenn beispielsweise 10 Benutzer auf ein freigegebenes Postfach zugreifen und ein Benutzer entscheidet, die Quarantänenachricht zu löschen, wird die Nachricht für alle 10 Benutzer gelöscht. Wenn ein Benutzer entscheidet, die Nachricht freizugeben, wird sie ebenfalls für das freigegebene Postfach freigegeben und ist für alle anderen Benutzer des freigegebenen Postfachs zugänglich.

- Derzeit ist die Schaltfläche **"Absender blockieren"** im **Flyout "Details"** für isolierte Nachrichten, die an das freigegebene Postfach gesendet wurden, nicht verfügbar.

- Wenn Sie geschachtelte Sicherheitsgruppen verwenden, um Zugriff auf ein freigegebenes Postfach zu gewähren, empfehlen wir nicht mehr als zwei Ebenen geschachtelter Gruppen, wenn Sie Quarantänevorgänge für freigegebene Postfächer ausführen. Beispielsweise ist Gruppe A Ein Mitglied der Gruppe B, die ein Mitglied der Gruppe C ist. Um einem freigegebenen Postfach Berechtigungen zuzuweisen, fügen Sie den Benutzer nicht zu Gruppe A hinzu und weisen Sie dann Gruppe C dem freigegebenen Postfach zu.  

- Um isolierte Nachrichten für das freigegebene Postfach in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)zu verwalten, muss der Endbenutzer das Cmdlet ["Get-QuarantineMessage"](/powershell/module/exchange/get-quarantinemessage) mit freigegebener Postfach-E-Mail-Adresse für den Wert des _RecipientAddress-Parameters_ verwenden, um die Nachrichten zu identifizieren. Beispiel:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  Anschließend kann der Endbenutzer eine isolierte Nachricht aus der Liste auswählen, um sie anzuzeigen oder maßnahmen zu ergreifen.

  Dieses Beispiel zeigt alle isolierten Nachrichten, die an das freigegebene Postfach gesendet wurden, und gibt dann die erste Nachricht in der Liste aus der Quarantäne frei (die erste Nachricht in der Liste ist 0, die zweite ist 1 usw.).

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
