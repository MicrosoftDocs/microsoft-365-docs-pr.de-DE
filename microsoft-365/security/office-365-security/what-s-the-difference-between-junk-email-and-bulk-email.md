---
title: Was &apos; ist der Unterschied zwischen Junk-E-Mails und Massen-E-Mails?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die Unterschiede zwischen Junk-E-Mails (Spam) und Massen-E-Mails (graue E-Mails) in Exchange Online Protection (EOP) informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc9c94946c3da2f9a14f45070a86c557a5c7dc85
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206974"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>Was ist der Unterschied zwischen Junk-E-Mails und Massen-E-Mails in EOP?

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer fragen Kunden manchmal: "Was ist der Unterschied zwischen Junk-E-Mails und Massen-E-Mails?" In diesem Thema wird der Unterschied erläutert und die Steuerelemente beschrieben, die in EOP verfügbar sind.

- **Junk-E-Mails** sind Spam, bei denen es sich um unerwünschte und universell unerwünschte Nachrichten handelt (wenn sie ordnungsgemäß identifiziert werden). Standardmäßig lehnt das EOP Spam basierend auf der Reputation des Quell-E-Mail-Servers ab. Wenn eine Nachricht die Quell-IP-Prüfung übergibt, wird sie an die Spamfilterung gesendet. Wenn die Nachricht durch Spamfilterung als Spam klassifiziert wird, wird die Nachricht (standardmäßig) an die beabsichtigten Empfänger zugestellt und in ihren Junk-E-Mail-Ordner verschoben.

  - Sie können die Aktionen für Spamfilterungs-Urteile konfigurieren. Anweisungen finden Sie unter [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

  - Wenn Sie mit dem Spamfilter-Urteil nicht einverstanden sind, können Sie Nachrichten, die Sie als Spam oder Nichtspam betrachten, auf verschiedene Weise an Microsoft melden, wie unter Melden von Nachrichten und Dateien an [Microsoft beschrieben.](report-junk-email-messages-to-microsoft.md)

- **Massen-E-Mails** (auch als _graue E-Mails_ bezeichnet) sind schwieriger zu klassifizieren. Während Spam eine konstante Bedrohung ist, sind Massen-E-Mails häufig einmal Werbung oder Marketingnachrichten. Einige Benutzer möchten Massen-E-Mail-Nachrichten (und tatsächlich haben sie sich absichtlich angemeldet, um sie zu empfangen), während andere Benutzer Massen-E-Mails als Spam betrachten. Beispielsweise möchten einige Benutzer Werbenachrichten von der Contoso Corporation oder Einladungen zu einer bevorstehenden Konferenz zur Cybersicherheit empfangen, während andere Benutzer diese Nachrichten als Spam betrachten.

  Weitere Informationen dazu, wie Massen-E-Mails identifiziert werden, finden Sie unter [Bulk Complaint Level (BCL) in EOP](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Umgang mit Massen-E-Mails

Aufgrund der gemischten Reaktion auf Massen-E-Mails gibt es nicht universelle Anleitungen, die für jede Organisation gelten.

Antispampolizistinnen verfügen über einen standardmäßigen BCL-Schwellenwert, der zum Identifizieren von Massen-E-Mails als Spam verwendet wird. Administratoren können den Schwellenwert erhöhen oder verringern. Weitere Informationen finden Sie in den folgenden Themen:

- [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

- [EOP-Antispamrichtlinieneinstellungen](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

Eine weitere Option, die leicht übersehen werden kann: Wenn ein Benutzer sich über den Empfang von Massen-E-Mails beschwert, die Nachrichten jedoch von seriösen Absendern stammten, die die Spamfilterung in EOP übergeben, lassen Sie den Benutzer in der Massen-E-Mail-Nachricht nach einer Abmeldeoption suchen.
