---
title: Worin besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: In diesem Thema wird der Unterschied zwischen Junk-e-Mails (Spam) und Massen-e-Mails sowie die zugehörigen Steuerelemente in Office 365 erläutert.
ms.openlocfilehash: 15ca00b007ef0b8470e1b30608a695a90bd638b2
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630833"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>Worin besteht der Unterschied zwischen Junk- und Massen-E-Mails?

Microsoft 365 Kunden mit Postfächern in Exchange Online oder eigenständigen Exchange Online Schutz Kunden ohne Exchange Online Postfächer Fragen manchmal: "Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mail-EoP?" In diesem Thema wird der Unterschied erläutert und die Steuerelemente beschrieben, die in EoP zur Verfügung stehen.

- **Junk-e-** Mails sind Spam, bei denen es sich um unerwünschte und universell unerwünschte Nachrichten handelt (wenn Sie richtig identifiziert werden). Standardmäßig lehnt der EoP Spam basierend auf der Reputation des Quell-e-Mail-Servers ab. Wenn eine Nachricht die Quell-IP-Prüfung übergibt, wird Sie an die Spamfilterung gesendet. Wenn die Nachricht durch Spamfilterung als Spam klassifiziert wird, wird die Nachricht (standardmäßig) an die beabsichtigten Empfänger übermittelt und in Ihren Junk-e-Mail-Ordner verschoben.

  - Sie können die Aktionen konfigurieren, die für Spamfilter Urteile ausgeführt werden sollen. Anweisungen finden Sie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md).

  - Wenn Sie mit dem Spam Filterungs Urteil nicht einverstanden sind, können Sie Nachrichten, die Sie als Spam oder als nicht-Spam eingestuft haben, auf verschiedene Weise als Spam oder als nicht-Spam für Microsoft melden, wie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md)beschrieben.

- **Massen-e-** Mails (auch als _graue e-Mail_bezeichnet) ist schwieriger zu klassifizieren. Während Spam eine ständige Bedrohung darstellt, handelt es sich bei Massen-e-Mails häufig um einmalige Werbung oder Marketingnachrichten. Einige Benutzer möchten Massen-e-Mails (und tatsächlich haben Sie sich absichtlich für den Empfang angemeldet), während andere Benutzer Massen-e-Mails als Spam einschätzen. Einige Benutzer möchten beispielsweise Werbenachrichten von der Contoso Corporation oder Einladungen zu einer bevorstehenden Konferenz über Cyber Security erhalten, während andere Benutzer dieselben Nachrichten als Spam einstufen.

  Weitere Informationen zur Identifizierung von Massen-e-Mails finden Sie unter [Bulk Complaint Level (BCL) in Office 365](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Umgang mit Massen-E-Mails

Aufgrund der gemischten Reaktion auf Massen-e-Mails gibt es keine universellen Anleitungen für jede Organisation.

Anti-Spam-Richtlinien haben einen standardmäßigen BCL-Schwellenwert, der verwendet wird, um Massen-e-Mails als Spam zu identifizieren. Administratoren können den Schwellenwert erweitern oder verringern. Weitere Informationen hierzu finden Sie in den folgenden Themen:

- [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).

- [EoP-Anti-Spam-Richtlinieneinstellungen](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Eine weitere Option, die leicht übersehen werden kann: Wenn ein Benutzer über das Empfangen von Massen-e-Mails klagt, aber die Nachrichten von seriösen Absendern sind, die Spamfilterung in EoP übergeben, muss der Benutzer nach einer Option zum Abmelden in der Massen-e-Mail-Nachricht suchen.
