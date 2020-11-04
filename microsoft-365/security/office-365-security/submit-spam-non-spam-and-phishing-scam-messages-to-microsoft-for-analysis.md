---
title: Manuelles übermitteln von Nachrichten an Microsoft zur Analyse
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Administratoren und Endbenutzer können erfahren, wie Sie e-Mail-Nachrichten (gute e-Mails, die als "schlecht" oder "schlecht" gekennzeichnet sind) zur Analyse an Microsoft senden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68a0921f85e5b916cd53ebe84e4ea7d35e39967e
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877705"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Manuelles übermitteln von Nachrichten an Microsoft zur Analyse

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Wenn Sie ein Administrator in einer Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungen-Portal im Security & Compliance Center zu verwenden. Weitere Informationen finden Sie unter [Verwenden der Administrator Übermittlung zum Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft](admin-submission.md).

Es kann frustrierend sein, wenn Benutzer in Ihrer Organisation Junk-Nachrichten (Spam) oder Phishing-Nachrichten in Ihrem Posteingang empfangen oder wenn Sie keine legitime e-Mail-Nachricht erhalten, weil Sie als Junk gekennzeichnet ist. Wir optimieren unsere Spamfilter ständig, um genauere Angaben zu machen.

Sie und Ihre Benutzer können diesen Prozess unterstützen, indem Sie falsch positive Ergebnisse (gute e-Mail-Nachrichten als ungültig markiert), falsche Negative Zeichen (ungültige e-Mail-Nachricht) und Phishing-Nachrichten zur Analyse an Microsoft senden.

> [!NOTE]
> Aufgrund der hohen Anzahl von Übermittlungen, die wir erhalten, können wir möglicherweise nicht alle Anfragen zur Analyse beantworten.

## <a name="submit-false-negatives-to-microsoft"></a>Senden von falschen negativen an Microsoft

> [!TIP]
> Anstatt die folgenden Verfahren zum Melden von falsch negativen Daten zu verwenden, können Benutzer in Outlook und Outlook im Internet (früher als Outlook Web App bezeichnet) das Add-in "Berichtsnachricht" für Microsoft Outlook verwenden. Informationen zum Installieren und verwenden dieses Tools finden Sie unter [enable the Report Message Add-in](enable-the-report-message-add-in.md).

Wenn Sie eine Nachricht erhalten, die durch die Spamfilterung geleitet wurde, die als Spam oder Phishing identifiziert werden sollte, können Sie die Nachricht nach Bedarf an die Microsoft-Spam Analyse-und Microsoft-Phishing-Analyseteams senden. Die Analysten überprüfen die Nachricht und fügen Sie den Dienst weiten Filtern hinzu, wenn Sie die Klassifizierungskriterien erfüllen.

1. Erstellen Sie eine neue, leere e-Mail-Nachricht mit einem der folgenden Empfänger:

   - **Junk** : `junk@office365.microsoft.com`

   - **Phishing** : `phish@office365.microsoft.com`

2. Ziehen Sie die Junk-oder Phishing-Nachricht per Drag & Drop in die neue Nachricht. Dadurch wird die Junk-oder Phishing-Nachricht als Anlage in der neuen Nachricht gespeichert. Kopieren und Einfügen des Inhalts der Nachricht oder Weiterleiten der Nachricht (die ursprüngliche Nachricht ist erforderlich, damit die Nachrichtenkopfzeilen überprüft werden können).

   > [!NOTE]
   >
   > - Sie können mehrere Nachrichten in der neuen Nachricht anfügen. Stellen Sie sicher, dass alle Nachrichten vom gleichen Typ sind: entweder Phishing-Nachrichten oder Junk-e-Mail-Nachrichten.
   >
   > - Lassen Sie den Nachrichtentext leer.
   >
   > - Verwenden Sie entweder msg (Outlook-Standardformat) oder eml (standardmäßige Outlook im Internetformat) für die angefügten Nachrichten.

3. Wenn Sie fertig sind, klicken Sie auf **senden**.

> [!TIP]
> Administratoren haben verschiedene Möglichkeiten, bestimmte Nachrichten, die fälschlicherweise als Spam identifiziert werden, zu blockieren. Ausführliche Informationen finden Sie unter [Create blocked Sender Lists in EoP](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Senden von falsch positiven Ergebnissen an Microsoft

> [!TIP]
> Anstatt die folgenden Verfahren zum Melden von falsch positiven Ergebnissen zu verwenden, können Benutzer in Outlook und Outlook im Internet das Add-in "Berichtsnachricht" für Microsoft Outlook verwenden. Informationen zum Installieren und verwenden dieses Tools finden Sie unter [enable the Report Message Add-in](enable-the-report-message-add-in.md).

Wenn eine Nachricht fälschlicherweise als Spam identifiziert wurde, können Sie die Nachricht an das Microsoft-Spam Analyse Team übermitteln. Die Analysten bewerten die Nachricht, und (abhängig von den Ergebnissen der Analyse) können die Dienst weiten Filter so angepasst werden, dass die Nachricht durchlassen wird.

1. Erstellen Sie eine neue, leere e-Mail-Nachricht mit `not_junk@office365.microsoft.com` als Empfänger:

2. Ziehen Sie die nicht identifizierte Nachricht per Drag & Drop in die neue Nachricht. Dadurch wird die nicht identifizierte Nachricht als Anlage in der neuen Nachricht gespeichert. Kopieren und Einfügen des Inhalts der Nachricht oder Weiterleiten der Nachricht (die ursprüngliche Nachricht ist erforderlich, damit die Nachrichtenkopfzeilen überprüft werden können).

   > [!NOTE]
   >
   > - Sie können mehrere Nachrichten in der neuen Nachricht anfügen. Stellen Sie sicher, dass alle Nachrichten vom gleichen Typ sind: entweder Phishing-Nachrichten oder Junk-e-Mail-Nachrichten.
   >
   > - Lassen Sie den Nachrichtentext leer.
   >
   > - Verwenden Sie entweder msg (Outlook-Standardformat) oder eml (standardmäßige Outlook im Internetformat) für die angefügten Nachrichten.

3. Wenn Sie fertig sind, klicken Sie auf **senden**.

> [!TIP]
> Administratoren haben verschiedene Möglichkeiten, um zu ermöglichen, dass bestimmte Nachrichten die Spamfilterung überspringen. Ausführliche Informationen finden Sie unter [Create Safe Sender Lists in EoP](create-safe-sender-lists-in-office-365.md).

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Erstellen einer e-Mail-Fluss Regel zum Empfangen von Kopien von Nachrichten, die an Microsoft gemeldet werden

Anweisungen finden Sie unter [Verwenden von Nachrichtenfluss Regeln, um zu sehen, was Ihre Benutzer an Microsoft melden](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
