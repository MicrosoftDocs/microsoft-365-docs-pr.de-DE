---
title: Anzeigen und Freigeben von isolierten Nachrichten in freigegebenen Postfächern
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Benutzer können erfahren, wie Sie in Quarantäne befindliche Nachrichten anzeigen und bearbeiten, die an freigegebene Postfächer gesendet wurden, für die Sie Berechtigungen besitzen.
ms.openlocfilehash: 34a401d3bff66926acd3e04d7144ce465dfa3dbb
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688029"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>Anzeigen und Freigeben von isolierten Nachrichten in freigegebenen Postfächern

> [!NOTE]
> Die in diesem Artikel beschriebenen Features sind derzeit in der Vorschau, stehen nicht für alle zur Verfügung und können geändert werden.

Benutzer können isolierte Nachrichten verwalten, wenn Sie zu den Empfängern gehören, wie unter [Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer in EoP](find-and-release-quarantined-messages-as-a-user.md)beschrieben. Was ist aber mit freigegebenen Postfächern, bei denen der Benutzer über die Berechtigungen "Vollzugriff" und "Senden als" oder "Senden im Auftrag von" für das Postfach verfügt, wie in [freigegebenen Exchange Online Postfächern](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)

Die Möglichkeit für Benutzer, isolierte Nachrichten, die an ein freigegebenes Postfach gesendet wurden, zu verwalten, erforderte Administrators, damit die automatische Zuordnung für das freigegebene Postfach aktiviert bleibt (Sie ist standardmäßig aktiviert, wenn ein Administrator einem Benutzer Zugriff auf ein anderes Postfach gewährt). Je nach Größe und Anzahl der Postfächer, auf die der Benutzer Zugriff hat, kann die Leistung jedoch beeinträchtigt werden, wenn Ausblicke versucht, *alle* Postfächer zu öffnen, auf die der Benutzer Zugriff hat. Aus diesem Grund entscheiden sich viele Administratoren für das [Entfernen der automatischen Zuordnung für freigegebene Postfächer](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).

Nun ist die automatische Zuordnung nicht mehr erforderlich, damit Benutzer isolierte Nachrichten verwalten können, die an freigegebene Postfächer gesendet wurden. Es funktioniert einfach. Es gibt zwei verschiedene Methoden für den Zugriff auf isolierte Nachrichten, die an ein freigegebenes Postfach gesendet wurden:

- Wenn der Administrator [Spambenachrichtigungen für Endbenutzer](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in Anti-Spam-Richtlinien aktiviert hat, können alle Benutzer, die Zugriff auf die Spambenachrichtigungen für Endbenutzer im freigegebenen Postfach haben, auf die Schaltfläche **überprüfen** in der Benachrichtigung klicken, um im Sicherheits & Compliance Center in Quarantäne zu wechseln. Beachten Sie, dass mit dieser Methode nur Benutzer isolierte Nachrichten verwalten können, die an das freigegebene Postfach gesendet wurden. Benutzer können in diesem Kontext keine eigenen Quarantäne Nachrichten verwalten.

- Der Benutzer kann [im Sicherheits & Compliance Center zur Quarantäne wechseln](find-and-release-quarantined-messages-as-a-user.md). Standardmäßig werden nur Nachrichten angezeigt, die an den Benutzer gesendet wurden. Der Benutzer kann jedoch die **Sortierergebnisse** (die **Schaltfläche Nachrichten-ID** standardmäßig) in **Empfänger e-Mail-Adresse** ändern, die e-Mail-Adresse des freigegebenen Postfachs eingeben und dann auf **Aktualisieren** klicken, um die an das freigegebene Postfach gesendeten Nachrichten anzuzeigen.

  ![Sortieren von isolierten Nachrichten nach Empfänger-e-Mail-Adresse.](../../media/quarantine-sort-results-by-recipient-email-address.png)

Unabhängig von der Methode können Benutzer Verwirrung vermeiden, indem Sie die **Empfänger** Spalte für isolierte Nachrichten einschließen. Die maximale Anzahl von anzuzeigenden Spalten ist 7, sodass der Benutzer auf **Spalten ändern**, eine vorhandene Spalte entfernen (beispielsweise **Richtlinientyp**), **Empfänger** auswählen und dann auf **Speichern** oder **als Standard speichern** klicken muss.

  ![Entfernen Sie die Spalte Richtlinientyp, und fügen Sie die Spalte Empfänger der Quarantäne hinzu.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>Dabei ist Folgendes zu berücksichtigen:

- Der erste Benutzer, der in der isolierten Nachricht agiert, entscheidet über das Schicksal der Nachricht für jeden, der das freigegebene Postfach verwendet. Wenn beispielsweise ein freigegebenes Postfach von zehn Benutzern verwendet wird und ein Benutzer entscheidet, die Quarantäne Nachricht zu löschen, wird die Nachricht für alle 10 Benutzer gelöscht. Wenn ein Benutzer sich entschließt, die Nachricht zu veröffentlichen, wird dieser ebenfalls für das freigegebene Postfach freigegeben und ist für alle anderen Benutzer des freigegebenen Postfachs zugänglich.

- Derzeit steht die Schaltfläche " **Absender blockieren** " im **Detail** -Flyout für in Quarantäne befindliche Nachrichten, die an das freigegebene Postfach gesendet wurden, nicht zur Verfügung.

- Zum Verwalten von Nachrichten in Quarantäne für das freigegebene Postfach in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)muss der Endbenutzer das Cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) mit freigegebener e-Mail-Adresse des Postfachs für den Wert des Parameters _RecipientAddress_ verwenden, um die Nachrichten zu identifizieren. Beispiel:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  Anschließend kann der Endbenutzer eine isolierte Nachricht aus der Liste auswählen, um Sie anzuzeigen oder Maßnahmen für diese Aktion durchführen.

  In diesem Beispiel werden alle Nachrichten in Quarantäne angezeigt, die an das freigegebene Postfach gesendet wurden, und dann wird die erste Nachricht in der Liste aus der Quarantäne freigegeben (die erste Nachricht in der Liste ist 0, die zweite ist 1 usw.).

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  Ausführliche Informationen zu Syntax und Parametern finden Sie in den folgenden Themen:

  - [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [Vorschau-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
