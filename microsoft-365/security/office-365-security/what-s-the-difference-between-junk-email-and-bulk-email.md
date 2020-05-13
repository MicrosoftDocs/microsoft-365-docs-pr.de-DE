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
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die Unterschiede zwischen Junk-e-Mails (Spam) und Massen-e-Mails (Gray Mail) in Exchange Online Protection (EoP) informieren.
ms.openlocfilehash: 6936028aa7bda538f0e49429d22f28c7a78cdb36
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208452"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mails in EoP?

In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer Fragen Kunden manchmal: "Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mails?" In diesem Thema wird der Unterschied erläutert und die Steuerelemente beschrieben, die in EoP zur Verfügung stehen.

- **Junk-e-** Mails sind Spam, bei denen es sich um unerwünschte und universell unerwünschte Nachrichten handelt (wenn Sie richtig identifiziert werden). Standardmäßig lehnt der EoP Spam basierend auf der Reputation des Quell-e-Mail-Servers ab. Wenn eine Nachricht die Quell-IP-Prüfung übergibt, wird Sie an die Spamfilterung gesendet. Wenn die Nachricht durch Spamfilterung als Spam klassifiziert wird, wird die Nachricht (standardmäßig) an die beabsichtigten Empfänger übermittelt und in Ihren Junk-e-Mail-Ordner verschoben.

  - Sie können die Aktionen konfigurieren, die für Spamfilter Urteile ausgeführt werden sollen. Anweisungen finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md).

  - Wenn Sie mit dem Spam Filterungs Urteil nicht einverstanden sind, können Sie Nachrichten, die Sie als Spam oder als nicht-Spam eingestuft haben, auf verschiedene Weise als Spam oder als nicht-Spam für Microsoft melden, wie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md)beschrieben.

- **Massen-e-** Mails (auch als _graue e-Mail_bezeichnet) ist schwieriger zu klassifizieren. Während Spam eine ständige Bedrohung darstellt, handelt es sich bei Massen-e-Mails häufig um einmalige Werbung oder Marketingnachrichten. Einige Benutzer möchten Massen-e-Mails (und tatsächlich haben Sie sich absichtlich für den Empfang angemeldet), während andere Benutzer Massen-e-Mails als Spam einschätzen. Einige Benutzer möchten beispielsweise Werbenachrichten von der Contoso Corporation oder Einladungen zu einer bevorstehenden Konferenz über Cyber Security erhalten, während andere Benutzer dieselben Nachrichten als Spam einstufen.

  Weitere Informationen zur Identifizierung von Massen-e-Mails finden Sie unter [Bulk Complaint Level (BCL) in EoP](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Umgang mit Massen-E-Mails

Aufgrund der gemischten Reaktion auf Massen-e-Mails gibt es keine universellen Anleitungen für jede Organisation.

Anti-Spam-Richtlinien haben einen standardmäßigen BCL-Schwellenwert, der verwendet wird, um Massen-e-Mails als Spam zu identifizieren. Administratoren können den Schwellenwert erweitern oder verringern. Weitere Informationen hierzu finden Sie in den folgenden Themen:

- [Konfigurieren von Anti-Spam-Richtlinien in EoP](configure-your-spam-filter-policies.md).

- [EoP-Anti-Spam-Richtlinieneinstellungen](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Eine weitere Option, die leicht übersehen werden kann: Wenn ein Benutzer über das Empfangen von Massen-e-Mails klagt, aber die Nachrichten von seriösen Absendern sind, die Spamfilterung in EoP übergeben, muss der Benutzer nach einer Option zum Abmelden in der Massen-e-Mail-Nachricht suchen.
