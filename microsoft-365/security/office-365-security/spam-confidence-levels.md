---
title: Spam Confidence Level
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die SCL-Bewertung (Spam Confidence Level) informieren, die auf Nachrichten in Exchange Online Protection (EoP) angewendet wird.
ms.openlocfilehash: fbd892b0171cee71f516d7ca3b26b91da664af79
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202233"
---
# <a name="spam-confidence-level-scl-in-eop"></a>SCL (Spam Confidence Level) in EoP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer werden eingehende Nachrichten über die Spamfilterung in EoP durchlaufen und einem Spam-Faktor zugewiesen. Das Ergebnis wird einer individuellen SCL-Bewertung (Spam Confidence Level) zugeordnet, die der Nachricht in einer X-Kopfzeile hinzugefügt wird. Eine höhere SCL-Bewertung gibt an, dass eine Nachricht eher Spam ist. EoP nimmt auf der Nachricht basierend auf der SCL-Bewertung Aktionen vor.

Was der SCL-Wert bedeutet und welche Standardaktionen für Nachrichten ausgeführt werden, wird in der folgenden Tabelle beschrieben. Weitere Informationen zu Aktionen, die Sie Nachrichten basierend auf dem Spamfilter Urteil ausführen können, finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md).

****

|SCL|Definition|Standardaktion|
|:---:|---|---|
|-1|Die Nachricht hat die Spamfilterung übersprungen. Die Nachricht stammt beispielsweise von einem sicheren Absender, wurde an einen sicheren Empfänger gesendet oder stammt von einem e-Mail-Quellserver in der IP-Zulassungsliste. Weitere Informationen finden Sie unter [Erstellen sicherer Absenderlisten in EoP](create-safe-sender-lists-in-office-365.md).|Die Nachricht wird in das Postfach des Empfängers zugestellt.|
|0, 1|Spamfilterung bestimmt, dass die Nachricht kein Spam war.|Die Nachricht wird in das Postfach des Empfängers zugestellt.|
|5, 6|Spamfilterung markiert die Nachricht als **Spam**|Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.|
|9 |Spamfilterung kennzeichnete die Nachricht als **Spam mit hoher Vertrauens** Würdigkeit|Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.|
|

Sie werden feststellen, dass die SCL-Bewertung 2, 3, 4, 7 und 8 nicht von der Spamfilterung verwendet wird.

Mithilfe von Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) können Sie die SCL-Bewertung für Nachrichten Stempeln. Wenn Sie eine e-Mail-Fluss Regel zum Festlegen der SCL-Bewertung verwenden, lösen die Werte 5 oder 6 die Spam Filterungs Aktion für **Spam**aus, und die Werte 7, 8 oder 9 lösen die Spam Filterungs Aktion für **Spam mit hoher Vertrauens**Würdigkeit aus. Weitere Informationen finden Sie unter [Verwenden von Nachrichtenfluss Regeln zum Festlegen der SCL-Bewertung (Spam Confidence Level) in Nachrichten](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Ähnlich wie bei der SCL-Bewertung identifiziert die Massen Reklamations Stufe (BCL) ungültige Massen-e-Mails (auch als _graue e-Mail_bezeichnet). Ein höheres BCL-Niveau zeigt an, dass eine als Massensendung gesendete E-Mail mit größerer Wahrscheinlichkeit zu Beschwerden führen wird (und daher eher als Spam einzustufen ist). Sie konfigurieren den BCL-Schwellenwert in Anti-Spam-Richtlinien. Weitere Informationen finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md), [Bulk Complaint Level (BCL) in EoP)](bulk-complaint-level-values.md)und [worin besteht der Unterschied zwischen Junk-e-Mail und Massen-e-Mails?](what-s-the-difference-between-junk-email-and-bulk-email.md).

|<!-- -->|
|---|
|![Das kurze Symbol für LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Entdecken Sie ﻿kostenlose Video Kurse für **Microsoft 365-Administratoren und IT-Experten**, die Ihnen von LinkedIn Learning angeboten werden.|
