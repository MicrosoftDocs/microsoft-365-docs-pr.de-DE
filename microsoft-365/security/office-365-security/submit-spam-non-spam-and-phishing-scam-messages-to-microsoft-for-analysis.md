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
description: Administratoren und Endbenutzer können lernen, wie Sie Nachrichten (gute E-Mails, die als "schlecht" oder "schlecht" gekennzeichnet sind) zur Analyse an Microsoft senden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0d48c3c6f6d082085390d6e246a088b6d3f6bf0
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105548"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Manuelles Übermitteln von Nachrichten zur Analyse an Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Wenn Sie ein Administrator in einer Organisation mit Exchange Online Postfächern sind, empfehlen wir, die Seite **"Übermittlungen"** im Microsoft 365 Defender-Portal zu verwenden. Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)

Es kann frustrierend sein, wenn Benutzer in Ihrer Organisation Junk-Nachrichten (Spam) oder Phishing-Nachrichten in ihrem Posteingang erhalten oder wenn sie keine seriöse E-Mail-Nachricht erhalten, da sie als Junk gekennzeichnet ist. Wir optimieren unsere Spamfilter ständig, um genauer zu sein.

Sie und Ihre Benutzer können diesen Prozess unterstützen, indem Sie falsch positive Ergebnisse (gute E-Mails als schlecht markiert), falsch negative Nachrichten (ungültige E-Mails sind zulässig) und Phishingnachrichten zur Analyse an Microsoft senden.

> [!NOTE]
> Aufgrund der hohen Anzahl von Übermittlungen, die wir erhalten, können möglicherweise nicht alle Anforderungen für die Analyse beantwortet werden.

## <a name="submit-false-negatives-to-microsoft"></a>Übermitteln falsch negativer Ergebnisse an Microsoft

> [!TIP]
> Anstatt die folgenden Verfahren zum Melden falsch negativer Ergebnisse zu verwenden, können Benutzer in Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) das Add-In "Nachricht melden" oder das Add-In "Phishing melden" verwenden. Informationen zum Installieren und Verwenden dieser Tools finden Sie unter [Aktivieren des Add-Ins "Nachricht melden"](enable-the-report-message-add-in.md) und ["Bericht-Phishing"-Add-In.](enable-the-report-phish-add-in.md)

Wenn Sie eine Nachricht erhalten, die die Spamfilterung durchlaufen hat, die als Spam oder Phishing hätte identifiziert werden sollen, können Sie die Nachricht ggf. an die Microsoft-Teams für Spamanalyse und Microsoft Phishinganalyse übermitteln. Die Analysten überprüfen die Nachricht und fügen sie den dienstweiten Filtern hinzu, wenn sie die Klassifizierungskriterien erfüllt.

1. Erstellen Sie eine neue, leere E-Mail-Nachricht mit einem der folgenden Empfänger:

   - **Junk**: `junk@office365.microsoft.com`
   - **Phishing:**`phish@office365.microsoft.com`

2. Ziehen Sie die Junk- oder Phishingnachricht per Drag & Drop in die neue Nachricht. Dadurch wird die Junk- oder Phishingnachricht als Anlage in der neuen Nachricht gespeichert. Kopieren Und fügen Sie den Inhalt der Nachricht nicht ein oder leiten Sie die Nachricht weiter (wir benötigen die ursprüngliche Nachricht, damit wir die Nachrichtenkopfzeilen überprüfen können).

   > [!NOTE]
   >
   > - Sie können mehrere Nachrichten in der neuen Nachricht anfügen. Stellen Sie sicher, dass alle Nachrichten den gleichen Typ aufweisen: Phishing- oder Junk-E-Mail-Nachrichten.
   > - Lassen Sie den Nachrichtentext leer.
   > - Verwenden Sie entweder msg-Formate (Standardformat Outlook) oder EML (Standard-Outlook im Webformat) für die angefügten Nachrichten.

3. Wenn Sie fertig sind, klicken Sie auf **"Senden".**

> [!TIP]
> Administratoren haben verschiedene Möglichkeiten, bestimmte Nachrichten zu blockieren, die als Spam falsch identifiziert werden. Ausführliche Informationen finden Sie unter [Erstellen von Listen blockierter Absender in EOP.](create-block-sender-lists-in-office-365.md)

## <a name="submit-false-positives-to-microsoft"></a>Übermitteln falsch positiver Ergebnisse an Microsoft

> [!TIP]
> Anstatt die folgenden Verfahren zum Melden falsch positiver Ergebnisse zu verwenden, können Benutzer in Outlook und Outlook im Web das Add-In "Nachricht melden" oder das Add-In "Phishing melden" verwenden. Informationen zum Installieren und Verwenden dieser Tools finden Sie unter [Aktivieren des Add-Ins "Nachricht melden"](enable-the-report-message-add-in.md) und ["Bericht-Phishing"-Add-In.](enable-the-report-phish-add-in.md)

Wenn eine Nachricht fälschlicherweise als Spam identifiziert wurde, können Sie die Nachricht an das Microsoft Spam Analysis Team senden. Die Analysten bewerten die Nachricht, und (abhängig von den Ergebnissen der Analyse) können die dienstweiten Filter angepasst werden, um die Nachricht durchzulassen.

1. Erstellen Sie eine neue, leere E-Mail-Nachricht `not_junk@office365.microsoft.com` mit dem Empfänger.

2. Ziehen Sie die falsch identifizierte Nachricht per Drag & Drop in die neue Nachricht. Dadurch wird die falsch identifizierte Nachricht als Anlage in der neuen Nachricht gespeichert. Kopieren Und fügen Sie den Inhalt der Nachricht nicht ein oder leiten Sie die Nachricht weiter (wir benötigen die ursprüngliche Nachricht, damit wir die Nachrichtenkopfzeilen überprüfen können).

   > [!NOTE]
   >
   > - Sie können mehrere Nachrichten in der neuen Nachricht anfügen. Stellen Sie sicher, dass alle Nachrichten den gleichen Typ aufweisen: Phishing- oder Junk-E-Mail-Nachrichten.
   > - Lassen Sie den Nachrichtentext leer.
   > - Verwenden Sie entweder msg-Formate (Standardformat Outlook) oder EML (Standard-Outlook im Webformat) für die angefügten Nachrichten.

3. Wenn Sie fertig sind, klicken Sie auf **"Senden".**

> [!TIP]
> Administratoren haben verschiedene Möglichkeiten, bestimmten Nachrichten das Überspringen der Spamfilterung zu ermöglichen. Ausführliche Informationen finden Sie unter [Erstellen von Listen sicherer Absender in EOP.](create-safe-sender-lists-in-office-365.md)

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>Wo werden die Daten aus Übermittlungen an Microsoft gespeichert?

Die Daten befinden sich in der Office 365 Compliance-Grenze in nordamerikanischen Rechenzentren. Die Daten werden von Analysten des Entwicklungsteams überprüft, um die Effektivität der Filter zu verbessern.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Erstellen einer Nachrichtenflussregel zum Empfangen von Kopien von Nachrichten, die an Microsoft gemeldet werden

Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, welche Benutzer An Microsoft melden.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)
