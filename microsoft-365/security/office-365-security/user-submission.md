---
title: Angeben eines Postfachs für Benutzerübermittlungen von Spam-und Phishing-Nachrichten
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
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie ein Postfach So konfigurieren, dass Spam-und Phishing-e-Mails erfasst werden, die von Benutzern gemeldet werden.
ms.openlocfilehash: 2931171d8e2dcd26593904385aec872c8967abf4
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213352"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Angeben eines Postfachs für Benutzer Übermittlungen von Spam-und Phishing-Nachrichten in Exchange Online

In Microsoft 365-Organisationen mit Exchange Online Postfächern können Sie ein Postfach für den Empfang von Nachrichten angeben, die von Benutzern als bösartig oder nicht bösartig gemeldet werden. Wenn Benutzer Nachrichten über die verschiedenen Berichtsoptionen übermitteln, können Sie dieses Postfach zum Abfangen von Nachrichten (nur an das benutzerdefinierte Postfach senden) oder zum Empfangen von Kopien von Nachrichten (senden an das benutzerdefinierte Postfach und Microsoft) verwenden. Dieses Feature funktioniert mit den folgenden Optionen für die Nachrichtenberichterstattung:

- [Das Add-in "Berichtsnachricht"](enable-the-report-message-add-in.md)

- [Integrierte Berichterstellung in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (früher bekannt als Outlook Web App)

Sie können auch Nachrichten Berichterstattungstools von Drittanbietern konfigurieren, um Nachrichten an das von Ihnen angegebene Postfach weiterzuleiten.

Durch das Übermitteln von Benutzern gemeldeten Nachrichten an ein benutzerdefiniertes Postfach anstatt direkt an Microsoft können Ihre Administratoren Nachrichten selektiv und manuell über [Administrator Übermittlung](admin-submission.md)an Microsoft melden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Wenn Sie direkt zur Seite **Benutzereingaben** wechseln möchten, verwenden Sie <https://protection.office.com/userSubmissionsReportMessage> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit einer eigenständigen EoP PowerShell finden Sie unter [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Um das Postfach für Benutzer Übermittlungen zu konfigurieren, müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein. Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Konfigurieren des Postfachs für Benutzer Übermittlungen mithilfe des Security & Compliance Centers

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Users Submissions**.

2. Wählen Sie auf der Seite **Benutzereingaben** , die angezeigt wird, eine der folgenden Optionen aus:

   - **Aktivieren der Berichtsnachrichten Funktion für Outlook (empfohlen)**: Wählen Sie diese Option aus, wenn Sie das Add-in "Berichtsnachricht" oder die integrierte Berichterstellung in Outlook im Internet verwenden, und konfigurieren Sie dann die folgenden Einstellungen:

     - **Anpassen der Bestätigungsnachricht für Endbenutzer**: Klicken Sie auf diesen Link. Konfigurieren Sie im angezeigten Flyout für die **Bestätigung der Nachrichten Anpassung** die folgenden Einstellungen:

       - **Vor der Übermittlung**: Geben Sie in den Feldern **Titel** und **Bestätigungsmeldung** den beschreibenden Text ein, den Benutzer sehen, bevor Sie eine Nachricht mithilfe des Berichtsnachrichten-Add-Ins melden. Sie können die Variable% type% verwenden, um den Übermittlungs einzubeziehen (Junk, not Junk, Phishing, etc.).

         Wie bereits erwähnt, wird der Benachrichtigung auch der folgende Text hinzugefügt:

         > Ihre e-Mail-Nachricht wird an Microsoft zur Analyse übermittelt. Einige e-Mails enthalten möglicherweise persönliche oder vertrauliche Informationen.

       - **Nach der Übermittlung**: Klicken Sie auf ![ Symbol erweitern ](../../media/scc-expand-icon.png) . Geben Sie in die **Meldungs** Felder **Titel** und Bestätigung den beschreibenden Text ein, den Benutzer sehen, nachdem Sie eine Nachricht mithilfe des Berichtsnachrichten-Add-ins gemeldet haben. Sie können die Variable% type% verwenden, um den Übermittlungs einzubeziehen.

      Klicken Sie nach Abschluss des Vorgangs auf **Speichern**. Klicken Sie auf der Seite **Benutzereingaben** auf wieder **herstellen** , um diese Werte zu löschen.

   - **Senden Sie die gemeldeten Nachrichten an**: führen Sie eine der folgenden Optionen aus:

     - **Microsoft (empfohlen)**: das Postfach "Benutzer Übermittlungen" wird nicht verwendet (alle gemeldeten Nachrichten werden an Microsoft weitergegeben).

     - **Microsoft und ein benutzerdefiniertes Postfach**: Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein. Verteilergruppen sind nicht zulässig.

     - **Benutzerdefiniertes Postfach**: Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein. Verteilergruppen sind nicht zulässig.

     Wenn Sie fertig sind, klicken Sie auf **bestätigen**.

     ![Senden von gemeldeten Nachrichten an Microsoft und ein benutzerdefiniertes Postfach](../../media/user-submission-enable-outlook-report-message.png)

   - **Deaktivieren der Berichtsnachrichten Funktion für Outlook**: Wählen Sie diese Option aus, wenn Sie Drittanbieter-Berichterstattungstools anstelle des Berichtsnachrichten-Add-Ins oder der integrierten Berichterstellung in Outlook im Internet verwenden, und konfigurieren Sie dann die folgenden Einstellungen:

     Wählen Sie **dieses benutzerdefinierte Postfach verwenden aus, um Benutzer gemeldete Übermittlungen zu empfangen**. Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Postfachs oder die e-Mail-Adresse des Postfachs ein, das Sie erstellen möchten.

     Wenn Sie fertig sind, klicken Sie auf **bestätigen**.

     ![Senden von gemeldeten Nachrichten an ein benutzerdefiniertes Postfach mithilfe von Drittanbietertools](../../media/user-submission-disable-outlook-report-message.png)
