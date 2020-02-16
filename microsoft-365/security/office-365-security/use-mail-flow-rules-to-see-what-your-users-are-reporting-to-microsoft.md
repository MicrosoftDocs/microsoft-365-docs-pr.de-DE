---
title: Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
description: Sie können eine Exchange-Nachrichtenfluss Regel erstellen, um zu verhindern, dass Ihre Benutzer e-Mail-Nachrichten zur Analyse an Microsoft senden und in ihren eigenen Sicherheitsprozessen verwenden.
ms.openlocfilehash: ae8655416840dc326344e2c2aea7c67486389492
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084374"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden

Ihnen stehen verschiedene Möglichkeiten zur Verfügung, falsch positive und falsch negative Nachrichten zur Analyse an Microsoft zu senden. Als Administrator können Sie Nachrichtenflussregeln verwenden, um anzuzeigen, was Ihre Benutzer an Microsoft als Spam, kein Spam und betrügerische Phishing-Versuche melden. Weitere Informationen finden Sie unter [Übermitteln von Spam-, Nicht-Spamnachrichten und Nachrichten, die als betrügerische Phishing-Angriffe angesehen werden, an Microsoft zur Analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Umgekehrt können Sie eine Exchange-Nachrichtenfluss Regel (auch als Transportregel bezeichnet) erstellen, um zu verhindern, dass Ihre Benutzer e-Mail-Nachrichten zur Analyse an Microsoft senden und in ihren eigenen Sicherheitsprozessen verwenden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

Geschätzte Zeit bis zum Abschließen des Vorgangs: 5 Minuten

Bevor Sie dieses Verfahren bzw. diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Nachrichtenfluss" und "Outlook im webpostfach-Richtlinien" in [Exchange Online Berechtigungen](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).

Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>Verwenden Sie die Exchange-Verwaltungskonsole, um eine Nachrichtenflussregel zu erstellen, um Berichte zu Junk-E-Mails, Phishing und Nicht-Junk-E-Mails anzuzeigen.

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken Sie auf ![Hinzufügen (Symbol)](../../media/ITPro-EAC-AddIcon.gif) und wählen Sie dann **Neue Regel erstellen** aus.

3. Benennen Sie die Regel, und klicken Sie dann auf **Weitere Optionen**.

4. Unter **Diese Regel anwenden, wenn...** können Sie **Empfänger** und anschließend **Adresse enthält eines dieser Wörter** wählen.

5. Führen Sie im Feld **Wörter oder Ausdrücke angeben** die folgenden Schritte aus:

   - Geben `abuse@messaging.microsoft.com`Sie ein, klicken Sie](../../media/ITPro-EAC-AddIcon.gif)auf Add `junk@office365.microsoft.com` -Symbol **hinzu** ![fügen, geben](../../media/ITPro-EAC-AddIcon.gif)Sie ein, und klicken Sie **dann auf** ![hinzufügen. Diese e-Mail-Adressen werden verwendet, um falsch negative Nachrichten an Microsoft zu senden.

   - Geben `phish@office365.microsoft.com` Sie ein, und klicken Sie](../../media/ITPro-EAC-AddIcon.gif)dann auf Add-Symbol **Hinzufügen** ![. Diese E-Mail-Adresse wird verwendet, um verpasste Phishingnachrichten an Microsoft zu senden.

   - Geben `false_positive@messaging.microsoft.com`Sie ein, klicken Sie](../../media/ITPro-EAC-AddIcon.gif)auf Add `not_junk@office365.microsoft.com`-Symbol **hinzu** ![fügen, geben Sie](../../media/ITPro-EAC-AddIcon.gif)ein, und klicken Sie ![dann **auf Symbol hinzufügen.** Diese e-Mail-Adressen werden verwendet, um falsch positive Nachrichten an Microsoft zu senden.

   - Klicken Sie auf **OK**.

6. Wählen Sie unter **Folgendes ausführen** die Option **Bcc der Nachricht an...** aus, und wählen Sie dann die Postfächer aus, in denen Sie Nachrichten erhalten möchten.

7. Auf Wunsch können Sie unter anderem auch Einstellungen zur Überwachung der Regel, zum Testen der Regel und zum Aktivieren der Regel in einem bestimmten Zeitraum vornehmen. Wir empfehlen, die Regel über eine bestimmte Zeit zu testen, bevor Sie sie erzwingen. Weitere Informationen finden Sie unter [Procedures for Mail Flow Rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).

8. Klicken Sie auf die Schaltfläche **Speichern**, um die Regel zu speichern. Sie wird in der Liste der Regeln angezeigt.

Nachdem Sie die Regel erstellt und durchgesetzt haben, werden sämtliche von Ihrer Organisation aus an vorgegebene E-Mail-Adressen gesendeten Nachrichten in das angegebene Postfach kopiert.
