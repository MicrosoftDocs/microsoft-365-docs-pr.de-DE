---
title: Angeben eines Postfachs für Benutzerübermittlungen von Spam-und Phishing-Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie ein Postfach So konfigurieren, dass Spam-und Phishing-e-Mails erfasst werden, die von Benutzern gemeldet werden.
ms.openlocfilehash: 76264801820b6a41ee744a8adcc3b3b48a8e9479
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826741"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Angeben eines Postfachs für Benutzer Übermittlungen von Spam-und Phishing-Nachrichten in Exchange Online

In Microsoft 365-Organisationen mit Exchange Online Postfächern können Sie ein Postfach für den Empfang von Nachrichten angeben, die von Benutzern als bösartig oder nicht bösartig gemeldet werden. Wenn Benutzer Nachrichten über die verschiedenen Berichtsoptionen übermitteln, können Sie dieses Postfach zum Abfangen von Nachrichten (nur an das benutzerdefinierte Postfach senden) oder zum Empfangen von Kopien von Nachrichten (senden an das benutzerdefinierte Postfach und Microsoft) verwenden. Dieses Feature funktioniert mit den folgenden Optionen für die Nachrichtenberichterstattung:

- [Das Add-in "Berichtsnachricht"](enable-the-report-message-add-in.md)

- [Integrierte Berichterstellung in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (früher bekannt als Outlook Web App)

- Integrierte Berichterstellung in Outlook für IOS und Android

  > [!NOTE]
  > Wenn die Berichterstellung [in Outlook im Internet deaktiviert](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)wurde, werden durch die Aktivierung von Benutzereingaben hier die Einstellungen außer Kraft gesetzt, und Benutzer können erneut Nachrichten in Outlook im Internet melden.

Sie können auch Nachrichten Berichterstattungstools von Drittanbietern konfigurieren, um Nachrichten an das von Ihnen angegebene Postfach weiterzuleiten.

Durch das Übermitteln von Benutzern gemeldeten Nachrichten an ein benutzerdefiniertes Postfach anstatt direkt an Microsoft können Ihre Administratoren Nachrichten selektiv und manuell über [Administrator Übermittlung](admin-submission.md)an Microsoft melden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Wenn Sie direkt zur Seite **Benutzereingaben** wechseln möchten, verwenden Sie <https://protection.office.com/userSubmissionsReportMessage> .

- Bevor Sie die in diesem Artikel besprochenen Verfahren ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:

  - Um die Konfiguration für Benutzer Übermittlungen zu ändern, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

    - **Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Für den schreibgeschützten Zugriff auf Benutzereingaben müssen Sie Mitglied einer der folgenden Rollengruppen sein:

    - **Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Konfigurieren des Postfachs für Benutzer Übermittlungen mithilfe des Security & Compliance Centers

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Users Submissions**.

2. Wählen Sie auf der Seite **Benutzereingaben** , die angezeigt wird, eine der folgenden Optionen aus:

   a. **Aktivieren der Berichtsnachrichten Funktion für Outlook (empfohlen)**: Wählen Sie diese Option aus, wenn Sie das Add-in "Berichtsnachricht" oder die integrierte Berichterstellung in Outlook im Internet verwenden, und konfigurieren Sie dann die folgenden Einstellungen:

      - **Anpassen der Bestätigungsnachricht für Endbenutzer**: Klicken Sie auf diesen Link. Konfigurieren Sie im angezeigten Flyout für die **Bestätigung der Nachrichten Anpassung** die folgenden Einstellungen:

      - **Vor der Übermittlung**: Geben Sie in den Feldern **Titel** und **Bestätigungsmeldung** den beschreibenden Text ein, den Benutzer sehen, bevor Sie eine Nachricht mithilfe des Berichtsnachrichten-Add-Ins melden. Sie können die Variable% type% verwenden, um den Übermittlungs einzubeziehen (Junk, not Junk, Phishing, etc.).

        Wenn Sie eine Option auswählen, die die gemeldeten Nachrichten an Microsoft sendet, wird der Benachrichtigung auch der folgende Text hinzugefügt:

        > Ihre e-Mail-Nachricht wird an Microsoft zur Analyse übermittelt. Einige e-Mails enthalten möglicherweise persönliche oder vertrauliche Informationen.

      - **Nach der Übermittlung**: Klicken Sie auf ![ Symbol erweitern ](../../media/scc-expand-icon.png) . Geben Sie in die **Meldungs** Felder **Titel** und Bestätigung den beschreibenden Text ein, den Benutzer sehen, nachdem Sie eine Nachricht mithilfe des Berichtsnachrichten-Add-ins gemeldet haben. Sie können die Variable% type% verwenden, um den Übermittlungs einzubeziehen.

      Klicken Sie nach Abschluss des Vorgangs auf **Speichern**. Klicken Sie auf der Seite **Benutzereingaben** auf wieder **herstellen** , um diese Werte zu löschen.

      - **Senden Sie die gemeldeten Nachrichten an**: führen Sie eine der folgenden Optionen aus:

        - **Microsoft (empfohlen)**: das Postfach "Benutzer Übermittlungen" wird nicht verwendet (alle gemeldeten Nachrichten werden an Microsoft weitergegeben).

        - **Microsoft und ein benutzerdefiniertes Postfach**: Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein. Verteilergruppen sind nicht zulässig. Benutzer Übermittlungen werden sowohl an Microsoft für die Analyse als auch an das benutzerdefinierte Postfach für Ihr Administrator-oder Sicherheits Betriebsteam zu analysieren gehen.

        - **Benutzerdefiniertes Postfach**: Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein. Verteilergruppen sind nicht zulässig. Verwenden Sie diese Option, wenn die Nachricht nur für die Analyse zuerst an ein Administrator-oder Sicherheits Betriebsteam gesendet werden soll. Nachrichten werden nicht an Microsoft weitergeleitet, es sei denn, der Administrator leitet Sie selbst weiter.

        > [!NOTE]
        > US-Regierungsorganisationen (gcc, gcc-H und DoD) können nur **benutzerdefiniertes Postfach**konfigurieren. Die beiden anderen Optionen sind deaktiviert. 

      Wenn Sie fertig sind, klicken Sie auf **bestätigen**.

      > [!CAUTION]
      > Wenn Sie die [Junk-e-Mail-Berichterstellung in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) im Internet mit Outlook im WebPost Fach Richtlinien deaktiviert haben, aber eine der vorherigen Einstellungen für das Melden von Nachrichten an Microsoft konfiguriert haben, können Benutzer Nachrichten an Microsoft in Outlook im Internet über das Add-in "Berichtsnachricht" melden.

   - **Deaktivieren der Berichtsnachrichten Funktion für Outlook**: Wählen Sie diese Option aus, wenn Sie Drittanbieter-Berichterstattungstools anstelle des Berichtsnachrichten-Add-Ins oder der integrierten Berichterstellung in Outlook im Internet verwenden, und konfigurieren Sie dann die folgenden Einstellungen:

      Wählen Sie **dieses benutzerdefinierte Postfach verwenden aus, um Benutzer gemeldete Übermittlungen zu empfangen**. Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Postfachs ein, das sich bereits in Office 365 befindet. Hierbei muss es sich um ein vorhandenes Postfach in Exchange Online handeln, das e-Mails empfangen kann.

      Wenn Sie fertig sind, klicken Sie auf **bestätigen**.

## <a name="message-submission-format"></a>Nachrichten Übermittlungs Format

Nachrichten, die an benutzerdefinierte Postfächer gesendet werden, müssen einem bestimmten Übermittlungs Nachrichtenformat entsprechen. Der Betreff (Umschlag Titel) der Übermittlung sollte in folgendem Format vorliegen:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

were SafetyAPIAction ist einer der folgenden Integer-Werte:

- 1: Junk
- 2: NotJunk
- 3: Phishing

Im folgenden Beispiel:

- Die Nachricht wird als Phishing gemeldet.
- Die Netzwerknachrichten-ID lautet 49871234-6dc6-43E8-ABCD-08d797f20abe.
- Die Absender-IP-Adresse lautet 167.220.232.101.
- Die von-Adresse lautet Test@contoso.com.
- Die Betreffzeile der Nachricht lautet "Testen der Phishing-Übermittlung"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

Nachrichten, die diesem Format nicht entsprechen, werden im Übermittlungen-Portal nicht ordnungsgemäß angezeigt.
