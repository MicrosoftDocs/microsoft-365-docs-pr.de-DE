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
description: Administratoren und Endbenutzer können erfahren, wie Sie Nachrichten (gute E-Mails, die als ungültige oder ungültige E-Mails zugelassen sind) zur Analyse an Microsoft senden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c3a02c710472a996245a38d996ff4485efd1748
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624025"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Manuelles Übermitteln von Nachrichten zur Analyse an Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Wenn Sie ein Administrator in einer Organisation mit Exchange Online sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden. Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

Es kann frustrierend sein, wenn Benutzer in Ihrer Organisation Junknachrichten (Spam) oder Phishingnachrichten im Posteingang empfangen oder wenn sie keine legitime E-Mail-Nachricht erhalten, weil sie als Junk gekennzeichnet ist. Wir optimieren unsere Spamfilter ständig, um präziser zu sein.

Sie und Ihre Benutzer können diesen Prozess unterstützen, indem Sie falsch positive Ergebnisse (gute E-Mails, die als ungültig gekennzeichnet sind), falsch negative Nachrichten (ungültige E-Mails zulässig) und Phishingnachrichten zur Analyse an Microsoft übermitteln.

> [!NOTE]
> Aufgrund der hohen Anzahl von Übermittlungen, die wir erhalten, können wir möglicherweise nicht alle Analyseanforderungen beantworten.

## <a name="submit-false-negatives-to-microsoft"></a>Übermitteln falscher Negative an Microsoft

> [!TIP]
> Anstatt die folgenden Verfahren zum Melden falscher Negative zu verwenden, können Benutzer in Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) das Add-In "Nachricht melden" oder das Phishing-Add-In melden verwenden. Informationen zum Installieren und Verwenden dieser Tools finden Sie unter [Enable the Report Message add-in](enable-the-report-message-add-in.md) und Enable the Report Phishing [add-in](enable-the-report-phish-add-in.md).

Wenn Sie eine Nachricht erhalten, die die Spamfilterung passiert hat, die als Spam oder Phishing identifiziert werden sollte, können Sie die Nachricht an die Microsoft Spam Analysis- und Microsoft Phishing Analysis Teams senden. Die Analysten überprüfen die Nachricht und fügen sie den dienstweiten Filtern hinzu, wenn sie die Klassifizierungskriterien erfüllt.

1. Erstellen Sie eine neue leere E-Mail-Nachricht mit einem der folgenden Empfänger:

   - **Junk**: `junk@office365.microsoft.com`
   - **Phishing**: `phish@office365.microsoft.com`

2. Ziehen Sie die Junk- oder Phishingnachricht in die neue Nachricht, und legen Sie sie ab. Dadurch wird die Junk- oder Phishingnachricht als Anlage in der neuen Nachricht gespeichert. Kopieren Sie nicht den Inhalt der Nachricht, und fügen Sie ihn nicht ein, oder geben Sie die Nachricht weiter (wir benötigen die ursprüngliche Nachricht, damit wir die Nachrichtenkopfzeilen überprüfen können).

   > [!NOTE]
   >
   > - Sie können mehrere Nachrichten in der neuen Nachricht anfügen. Stellen Sie sicher, dass alle Nachrichten denselben Typ haben: Entweder Phishingnachrichten oder Junk-E-Mail-Nachrichten.
   > - Lassen Sie den Nachrichtentext leer.
   > - Verwenden Sie für die angefügten Nachrichten Outlook .msg (Standardformat) oder EML (Standardformat Outlook Webformat).

3. Klicken Sie nach Abschluss des Abschlusses auf **Senden**.

> [!TIP]
> Administratoren haben verschiedene Möglichkeiten, bestimmte Nachrichten zu blockieren, die als Spam falsch identifiziert werden. Weitere Informationen finden Sie unter [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Senden falsch positiver Ergebnisse an Microsoft

> [!TIP]
> Anstatt die folgenden Verfahren zum Melden falsch positiver Ergebnisse zu verwenden, können Benutzer in Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) das Berichtsnachrichten-Add-In oder das Phishing-Add-In Melden verwenden. Informationen zum Installieren und Verwenden dieser Tools finden Sie unter [Enable the Report Message add-in](enable-the-report-message-add-in.md) und Enable the Report Phishing [add-in](enable-the-report-phish-add-in.md).

Wenn eine Nachricht fälschlicherweise als Spam identifiziert wurde, können Sie die Nachricht an das Microsoft Spam Analysis Team übermitteln. Die Analysten werten die Nachricht aus, und (abhängig von den Ergebnissen der Analyse) können die dienstweiten Filter angepasst werden, um die Nachricht durch zu ermöglichen.

1. Erstellen Sie eine neue leere E-Mail-Nachricht mit `not_junk@office365.microsoft.com` als Empfänger.

2. Ziehen Sie die falsch identifizierte Nachricht in die neue Nachricht, und legen Sie sie ab. Dadurch wird die falsch identifizierte Nachricht als Anlage in der neuen Nachricht gespeichert. Kopieren Sie nicht den Inhalt der Nachricht, und fügen Sie ihn nicht ein, oder geben Sie die Nachricht weiter (wir benötigen die ursprüngliche Nachricht, damit wir die Nachrichtenkopfzeilen überprüfen können).

   > [!NOTE]
   >
   > - Sie können mehrere Nachrichten in der neuen Nachricht anfügen. Stellen Sie sicher, dass alle Nachrichten denselben Typ haben: Entweder Phishingnachrichten oder Junk-E-Mail-Nachrichten.
   > - Lassen Sie den Nachrichtentext leer.
   > - Verwenden Sie für die angefügten Nachrichten Outlook .msg (Standardformat) oder EML (Standardformat Outlook Webformat).

3. Klicken Sie nach Abschluss des Abschlusses auf **Senden**.

> [!TIP]
> Administratoren haben verschiedene Möglichkeiten, bestimmten Nachrichten das Überspringen der Spamfilterung zu ermöglichen. Weitere Informationen finden Sie unter [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>Wo werden die Daten aus Übermittlungen an Microsoft gespeichert?

Die Daten befinden sich in Office 365 Compliancegrenze in nordamerikanischen Rechenzentren. Die Daten werden von Analysten des Engineering-Teams überprüft, um die Effektivität der Filter zu verbessern.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Erstellen einer Nachrichtenflussregel zum Empfangen von Kopien von Nachrichten, die an Microsoft gemeldet werden

Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, welche Benutzer Microsoft melden.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)
