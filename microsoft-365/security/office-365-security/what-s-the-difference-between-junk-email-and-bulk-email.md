---
title: Worin &apos; besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?
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
description: Administratoren können sich über die Unterschiede zwischen Junk-E-Mail (Spam) und Massen-E-Mail (graue E-Mail) in Exchange Online Protection (EOP) informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c656ed1807b451ae03ecfeb0f220f5d7b902c7ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290645"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>Worin besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail in EOP?

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer fragen Kunden manchmal: "Was ist der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?" In diesem Thema wird der Unterschied erläutert und die in EOP verfügbaren Steuerelemente beschrieben.

- **Junk-E-Mails** sind Spam, die unerwünschte und universell unerwünschte Nachrichten sind (wenn sie ordnungsgemäß identifiziert werden). Standardmäßig weist EOP Spam basierend auf der Reputation des Quell-E-Mail-Servers zurück. Wenn eine Nachricht die Quell-IP-Überprüfung besteht, wird sie an die Spamfilterung gesendet. Wenn die Nachricht von der Spamfilterung als Spam klassifiziert wird, wird die Nachricht (standardmäßig) an die vorgesehenen Empfänger zugestellt und in ihren Junk-E-Mail-Ordner verschoben.

  - Sie können die Aktionen konfigurieren, die bei Spamfilterungen zu ergreifen sind. Anweisungen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP.](configure-your-spam-filter-policies.md)

  - Wenn Sie mit der Spamfilterung nicht einverstanden sind, können Sie Nachrichten, die Sie als Spam oder Nichtspam betrachten, auf verschiedene Weise an Microsoft melden, wie in "Melden von Nachrichten und Dateien an [Microsoft" beschrieben.](report-junk-email-messages-to-microsoft.md)

- **Massen-E-Mail** (auch als _graue_ E-Mail bezeichnet) ist schwieriger zu klassifizieren. Während Spam eine konstante Bedrohung darstellt, sind Massen-E-Mails häufig nur einmal Ankündigungen oder Marketingnachrichten. Einige Benutzer möchten Massen-E-Mail-Nachrichten (und tatsächlich haben sie sich absichtlich angemeldet, um sie zu empfangen), während andere Benutzer Massen-E-Mails als Spam betrachten. Beispielsweise möchten einige Benutzer Werbenachrichten von der Contoso Corporation oder Einladungen zu einer bevorstehenden Konferenz zur Cybersicherheit empfangen, während andere Benutzer diese Nachrichten als Spam betrachten.

  Weitere Informationen dazu, wie Massen-E-Mails identifiziert werden, finden Sie unter [Bulk Complaint Level (BCL) in EOP](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Umgang mit Massen-E-Mails

Aufgrund der gemischten Reaktion auf Massen-E-Mails gibt es nicht universelle Anleitungen, die für jede Organisation gelten.

Antispam-Policen verfügen über einen standardmäßigen BCL-Schwellenwert, der verwendet wird, um Massen-E-Mails als Spam zu identifizieren. Administratoren können den Schwellenwert erhöhen oder verringern. Weitere Informationen hierzu finden Sie in den folgenden Themen:

- [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

- [Antispamrichtlinieneinstellungen für EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Eine weitere Leicht zu übersehende Option: Wenn sich ein Benutzer über den Empfang von Massen-E-Mails beschwert, die Nachrichten jedoch von seriösen Absendern gesendet werden, die die Spamfilterung in EOP bestehen, lassen Sie den Benutzer in der Massen-E-Mail nach einer Option zum Kündigen des Abonnements suchen.
