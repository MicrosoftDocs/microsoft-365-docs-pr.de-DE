---
title: Manuelles Übermitteln von Nachrichten zur Analyse an Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Administratoren und Endbenutzer können erfahren, wie Sie Nachrichten (gute E-Mails, die als ungültige oder ungültige E-Mails zulässig sind) zur Analyse an Microsoft senden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d5d3b7a51c39b85af8a6fae84f525da6d806789c
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029584"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Manuelles Übermitteln von Nachrichten zur Analyse an Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Wenn Sie ein Administrator in einer Organisation mit Exchange Online-Postfächern sind, empfehlen wir die Verwendung des Übermittlungsportals im Security & Compliance Center. Weitere Informationen finden Sie unter ["Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft ".](admin-submission.md)

It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk. Wir optimieren unsere Spamfilter ständig, um präziser zu sein.

Sie und Ihre Benutzer können diesen Prozess unterstützen, indem Sie falsch positive Ergebnisse (gute E-Mails als schlecht gekennzeichnet), falsch negative Ergebnisse (ungültige E-Mails sind zugelassen) und Phishingnachrichten zur Analyse an Microsoft übermitteln.

> [!NOTE]
> Aufgrund der hohen Anzahl von Übermittlungen, die wir erhalten, können wir möglicherweise nicht alle Analyseanforderungen beantworten.

## <a name="submit-false-negatives-to-microsoft"></a>Übermitteln falsch negativer Meldungen an Microsoft

> [!TIP]
> Anstatt die folgenden Verfahren zum Melden falsch negativer Negative zu verwenden, können Benutzer in Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) das Report Message-Add-In oder das Phishing-Add-In "Melden" verwenden. Informationen zum Installieren und Verwenden dieser Tools finden Sie unter "Aktivieren des [Nachrichten-Add-Ins](enable-the-report-message-add-in.md) "Melden" und "Aktivieren des [Phishing-Add-Ins "Melden"](enable-the-report-phish-add-in.md).

Wenn Sie eine Nachricht erhalten, die die Spamfilterung passiert hat, die als Spam oder Phishing identifiziert worden sein sollte, können Sie die Nachricht gegebenenfalls an die Microsoft-Teams für die Spamanalyse und die Microsoft-Phishinganalyse übermitteln. Die Analysten überprüfen die Nachricht und fügen sie den dienstweiten Filtern hinzu, wenn sie die Klassifizierungskriterien erfüllt.

1. Erstellen Sie eine neue leere E-Mail-Nachricht mit einem der folgenden Empfänger:

   - **Junk:**`junk@office365.microsoft.com`

   - **Phishing:**`phish@office365.microsoft.com`

2. Ziehen Sie die Junk- oder Phishingnachricht per Drag and Drop in die neue Nachricht. Dadurch wird die Junk- oder Phishingnachricht als Anlage in der neuen Nachricht gespeichert. Kopieren Sie den Inhalt der Nachricht nicht, und fügen Sie ihn nicht ein, und geben Sie die Nachricht nicht weiter (wir benötigen die ursprüngliche Nachricht, damit wir die Nachrichtenkopfzeilen überprüfen können).

   > [!NOTE]
   >
   > - Sie können mehrere Nachrichten in der neuen Nachricht anfügen. Stellen Sie sicher, dass alle Nachrichten den gleichen Typ haben: entweder Phishing- oder Junk-E-Mail-Nachrichten.
   >
   > - Lassen Sie den Nachrichtentext leer.
   >
   > - Verwenden Sie entweder msg (Outlook-Standardformat) oder EML (Outlook im Web-Standardformat) für die angefügten Nachrichten.

3. Klicken Sie nach Abschluss des Abschlusses auf **"Senden".**

> [!TIP]
> Administratoren haben mehrere Möglichkeiten, bestimmte Nachrichten zu blockieren, die falsch als Spam erkannt werden. Weitere Informationen finden Sie unter [Erstellen von Listen blockierter Absender in EOP](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Übermitteln falsch positiver Ergebnisse an Microsoft

> [!TIP]
> Anstatt die folgenden Verfahren zum Melden falsch positiver Ergebnisse zu verwenden, können Benutzer in Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) das Add-In "Nachricht melden" oder das "Phishing-Add-In melden" verwenden. Informationen zum Installieren und Verwenden dieser Tools finden Sie unter "Aktivieren des [Nachrichten-Add-Ins](enable-the-report-message-add-in.md) "Melden" und "Aktivieren des [Phishing-Add-Ins "Melden"](enable-the-report-phish-add-in.md).


Wenn eine Nachricht fälschlicherweise als Spam identifiziert wurde, können Sie die Nachricht an das Microsoft Spam Analysis Team übermitteln. Die Analysten werten die Nachricht aus, und (abhängig von den Ergebnissen der Analyse) können die dienstweiten Filter angepasst werden, um die Nachricht zu durchkommen.

1. Erstellen Sie eine neue leere E-Mail-Nachricht mit `not_junk@office365.microsoft.com` dem Empfänger:

2. Ziehen Sie die falsch identifizierte Nachricht per Drag and Drop in die neue Nachricht. Dadurch wird die falsch identifizierte Nachricht als Anlage in der neuen Nachricht gespeichert. Kopieren Sie den Inhalt der Nachricht nicht, und fügen Sie ihn nicht ein, und geben Sie die Nachricht nicht weiter (wir benötigen die ursprüngliche Nachricht, damit wir die Nachrichtenkopfzeilen überprüfen können).

   > [!NOTE]
   >
   > - Sie können mehrere Nachrichten in der neuen Nachricht anfügen. Stellen Sie sicher, dass alle Nachrichten den gleichen Typ haben: entweder Phishing- oder Junk-E-Mail-Nachrichten.
   >
   > - Lassen Sie den Nachrichtentext leer.
   >
   > - Verwenden Sie entweder msg (Outlook-Standardformat) oder EML (Outlook im Web-Standardformat) für die angefügten Nachrichten.

3. Klicken Sie nach Abschluss des Abschlusses auf **"Senden".**

> [!TIP]
> Administratoren haben mehrere Möglichkeiten, bestimmten Nachrichten das Überspringen der Spamfilterung zu erlauben. Weitere Informationen finden Sie unter [Erstellen von Listen sicherer Absender in EOP](create-safe-sender-lists-in-office-365.md).

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>Wo werden die Daten aus Übermittlungen an Microsoft gespeichert?

Die Daten befinden sich in nordamerikanischen Rechenzentren in der Office 365-Compliance-Grenze. Die Daten werden von Analysten des Technikteams überprüft, um die Effektivität der Filter zu verbessern.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Erstellen einer Nachrichtenflussregel zum Empfangen von Kopien von Nachrichten, die an Microsoft gemeldet werden

Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, was Ihre Benutzer an Microsoft melden.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)
