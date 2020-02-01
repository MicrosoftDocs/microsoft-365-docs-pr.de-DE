---
title: Problembehandlung und Supportinformationen
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
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
ms.collection:
- M365-security-compliance
description: In diesem Thema werden die Schritte zur Problembehandlung für Endbenutzer und Administratoren beschrieben, und Sie erhalten Informationen zum Kontaktieren des technischen Supports.
ms.openlocfilehash: efb71aab852b76b2b898419444bfea4144728514
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598172"
---
# <a name="troubleshooting-and-support-information"></a>Problembehandlung und Supportinformationen

In diesem Thema werden die Schritte zur Problembehandlung für Endbenutzer und Administratoren beschrieben, und Sie erhalten Informationen zum Kontaktieren des technischen Supports.

## <a name="troubleshooting-for-users"></a>Problembehandlung für Benutzer

Gelegentlich können Probleme mit Microsoft Outlook auftreten, nachdem Sie das Add-in "Junk-e-Mail-Berichterstellung" hinzugefügt haben. Im Folgenden sind Probleme aufgeführt, die möglicherweise auftreten, sowie Tipps zum Behandeln dieser Probleme.

- Das Programm reagiert nicht, wenn Sie auf **Junk-E-Mail melden** klicken

- Outlook reagiert nicht mehr, wenn Sie eine E-Mail auswählen

- Gemeldete Junk-E-Mails können nicht übermittelt werden, und es wird eine Unzustellbarkeitsnachricht angezeigt

Um dieses Problem zu beheben, führen Sie die folgenden Schritte aus:

1. Schließen Sie Outlook, und starten Sie es neu.

2. Überprüfen Sie, ob Sie eine Testnachricht erstellen und senden können. Zu diesem Zweck können Sie eine Testnachricht an ein anderes E-Mail-Konto senden, für das Sie verantwortlich sind, und anschließend überprüfen, ob die E-Mail empfangen wurde.

Wenn das Problem fortbesteht, wenden Sie sich an Ihren Administrator.

> [!TIP]
> Sie können Spamnachrichten auch direkt an Microsoft senden (verwenden Sie zu diesem Zweck die E-Mail-Adresse [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com)). Falsch positive Ergebnisse können Sie an folgende E-Mail-Adresse senden: [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com).Weitere Informationen finden Sie unter [Übermitteln von Spam-, Nicht-Spamnachrichten und Nachrichten, die als betrügerische Phishing-Angriffe angesehen werden, an Microsoft zur Analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="troubleshooting-for-administrators"></a>Problembehandlung für Administratoren

Als Administrator können Probleme mit Benutzern auftreten, die das Add-in "Junk-e-Mail-Berichterstellung" für Outlook verwenden. Es folgen einige Tipps zur Lösung von Problemen, die möglicherweise auftreten.

### <a name="problem-an-error-message-asking-users-to-contact-their-system-administrator-continually-appears"></a>Problem: eine Fehlermeldung, in der Benutzer aufgefordert werden, Ihren System Administrator zu kontaktieren, wird ständig angezeigt.

1. Legen Sie den folgenden Registrierungsschlüsselwert auf "Verbose" fest:

   - **32-Bit-Outlook auf einem 32-Bit-Betriebssystem installiert**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **32-Bit-Outlook auf einem 64-Bit-Betriebssystem installiert**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **64 Bit Outlook (immer auf einem 64-Bit-Betriebssystem installiert)**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

2. Starten Sie Outlook neu, und fordern Sie die Benutzer auf, zurückgemeldet zu werden, wenn die Fehlermeldung angezeigt wird.

3. Erfassen Sie die Protokollinformationen am folgenden Speicherort:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Kontaktieren Sie den technischen Support für Exchange Online Protection, und übergeben Sie den Mitarbeitern diese Protokollinformationen.

### <a name="problem-users-choose-not-to-receive-a-confirmation-when-they-submit-an-email-as-junk-and-now-they-want-the-option-back"></a>Problem: Benutzer entscheiden, keine Bestätigung zu erhalten, wenn Sie eine e-Mail als Junk-e-Mail übermitteln, und möchten nun die Option zurück

1. Legen Sie den folgenden Registrierungsschlüsselwert auf "true" `HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk`fest:.

2. Starten Sie Outlook neu.

## <a name="support-information"></a>Supportinformationen

Wenn Sie Hilfe bei der Installation, Konfiguration oder Deinstallation des Add-Ins benötigen, wenden Sie sich über den Link Neue Dienstanforderung auf der Seite Support im Microsoft 365 Admin Center an den technischen Support. Weitere Optionen, einschließlich der Übermittlung einer Dienstanforderung über die Telefon-und Self-Support-Optionen, finden Sie unter [Hilfe und Support für EoP](help-and-support-for-eop.md).

## <a name="for-more-information"></a>Weitere Informationen

[Aktivieren des Berichtsnachrichts-Add-Ins](enable-the-report-message-add-in.md)

[Melden von Junk-E-Mails an Microsoft](report-junk-email-messages-to-microsoft.md)
