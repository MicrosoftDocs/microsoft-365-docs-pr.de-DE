---
title: Spam Confidence Level
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
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel können Administratoren erfahren, wie die SCL-Bewertung (Spam Confidence Level) die Wahrscheinlichkeit einer Nachricht als Spam bestimmt.
ms.openlocfilehash: 9448b1fd99878dbb85bc8699afc0719bc62dd951
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035248"
---
# <a name="spam-confidence-level-scl-in-office-365"></a>SCL (Spam Confidence Level) in Office 365

Wenn Microsoft 365 (Exchange Online oder eigenständiger Exchange Online Schutz (EoP) ohne Exchange Online Postfächer) eine eingehende e-Mail-Nachricht erhält, durchläuft die Nachricht die Spamfilterung und wird mit einer Spambewertung versehen. Das Ergebnis wird einer individuellen SCL-Bewertung (Spam Confidence Level) zugeordnet, die der Nachricht in einer X-Kopfzeile hinzugefügt wird. Eine höhere SCL-Bewertung gibt an, dass eine Nachricht eher Spam ist. Der Dienst nimmt auf der Grundlage der SCL-Bewertung Aktionen an der Nachricht vor.

Was der SCL-Wert bedeutet und welche Standardaktionen für Nachrichten ausgeführt werden, wird in der folgenden Tabelle beschrieben. Weitere Informationen zu Aktionen, die Sie Nachrichten basierend auf dem Spamfilter Urteil ausführen können, finden Sie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md).

||||
|:---:|---|---|
|**SCL**|**Definition**|**Standardaktion**|
|-1|Die Nachricht hat die Spamfilterung übersprungen. Die Nachricht stammt beispielsweise von einem sicheren Absender, wurde an einen sicheren Empfänger gesendet oder stammt von einem e-Mail-Quellserver in der IP-Zulassungsliste. Weitere Informationen finden Sie unter [Erstellen von Listen sicherer Absender in Office 365](create-safe-sender-lists-in-office-365.md).|Die Nachricht wird in das Postfach des Empfängers zugestellt.|
|0, 1|Spamfilterung bestimmt, dass die Nachricht kein Spam war.|Die Nachricht wird in das Postfach des Empfängers zugestellt.|
|5, 6|Spamfilterung markiert die Nachricht als **Spam**|Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.|
|9 |Spamfilterung kennzeichnete die Nachricht als **Spam mit hoher Vertrauens** Würdigkeit|Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.|
|

Sie werden feststellen, dass die SCL-Bewertung 2, 3, 4, 7 und 8 nicht von der Spamfilterung verwendet wird.

Mithilfe von Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) können Sie die SCL-Bewertung für Nachrichten Stempeln. Wenn Sie eine e-Mail-Fluss Regel zum Festlegen der SCL-Bewertung verwenden, lösen die Werte 5 oder 6 die Spam Filterungs Aktion für **Spam**aus, und die Werte 7, 8 oder 9 lösen die Spam Filterungs Aktion für **Spam mit hoher Vertrauens**Würdigkeit aus. Weitere Informationen finden Sie unter [Verwenden von Nachrichtenfluss Regeln zum Festlegen der SCL-Bewertung (Spam Confidence Level) in Nachrichten](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Ähnlich wie bei der SCL-Bewertung identifiziert die Massen Reklamations Stufe (BCL) ungültige Massen-e-Mails (auch als _graue e-Mail_bezeichnet). Eine höhere BCL gibt an, dass eine Massen-e-Mail-Nachricht häufiger Beschwerden generiert (und daher eher Spam ist). Sie konfigurieren den BCL-Schwellenwert in Anti-Spam-Richtlinien. Weitere Informationen finden Sie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md), [Bulk Complaint Level (BCL) in Office 365)](bulk-complaint-level-values.md)und [worin besteht der Unterschied zwischen Junk-e-Mail und Massen-e-Mails?](what-s-the-difference-between-junk-email-and-bulk-email.md).

||
|:-----|
|![Das Kurzsymbol für LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Neu bei Office 365?**         Entdecken Sie ﻿kostenlose Video Kurse für **Microsoft 365-Administratoren und IT-Experten**, die Ihnen von LinkedIn Learning angeboten werden.|
