---
title: Reihenfolge und Rangfolge des E-Mail-Schutzes
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Security Center, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die Anwendungsreihenfolge von Schutzen in Exchange Online Protection (EOP) und darüber informieren, wie der Prioritätswert in Schutzrichtlinien bestimmt, welche Richtlinie angewendet wird.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b2a72420340993c027ec99820dcd3edddab1a304
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063352"
---
# <a name="order-and-precedence-of-email-protection"></a>Reihenfolge und Rangfolge des E-Mail-Schutzes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer können eingehende E-Mails durch mehrere Arten von Schutz gekennzeichnet werden. Beispielsweise die integrierten Antiphishingrichtlinien in EOP, die für alle Microsoft 365-Kunden verfügbar sind, und die stabileren Antiphishingrichtlinien, die Microsoft Defender für Office 365-Kunden zur Verfügung stehen. Nachrichten werden auch durch mehrere Erkennungsscans auf Schadsoftware, Spam, Phishing usw. übergeben. Bei all dieser Aktivität kann es verwirrung darüber sein, welche Richtlinie angewendet wird.

Im Allgemeinen wird eine Richtlinie, die auf eine Nachricht angewendet wird, im **X-Forefront-Antispam-Report-Header** in der **CAT(Category)-Eigenschaft** identifiziert. Weitere Informationen finden Sie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md).

Es gibt zwei wichtige Faktoren, die bestimmen, welche Richtlinie auf eine Nachricht angewendet wird:

- **Die Priorität des E-Mail-Schutztyps**: Diese Reihenfolge ist nicht konfigurierbar und wird in der folgenden Tabelle beschrieben:

  ****

  |Priorität|E-Mail-Schutz|Kategorie|Zu verwaltende Stelle|
  |---|---|---|---|
  |1|Schadsoftware|CAT:MALW|[Konfigurieren von An malware-Richtlinien in EOP](configure-anti-malware-policies.md)|
  |2|Phishing|CAT:PHSH|[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)|
  |3|Spam mit hoher Vertrauenswürdigkeit|CAT:HSPM|[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)|
  |4 |Spoofing|CAT:SPOOF|[Konfigurieren von Spoof Intelligence in EOP](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|Benutzerwechsel (geschützte Benutzer)|UIMP|[Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365](configure-atp-anti-phishing-policies.md)|
  |6<sup>\*</sup>|Domänenwechsel (geschützte Domänen)|DIMP|[Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365](configure-atp-anti-phishing-policies.md)|
  |7 |Spam|CAT:SPM|[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)|
  |8 |Masse|CAT:BULK|[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> Diese Features sind nur in Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügbar.

- **Die Priorität** der Richtlinie: Für jeden Schutztyp (Antispam, Schadsoftware, Antiphishing usw.) gibt es eine Standardrichtlinie, die für alle gilt, Sie können jedoch benutzerdefinierte Richtlinien erstellen, die für bestimmte Benutzer gelten. Jede benutzerdefinierte Richtlinie hat einen Prioritätswert, der die Reihenfolge bestimmt, in der die Richtlinien angewendet werden. Die Standardrichtlinie wird immer zuletzt angewendet.

  Wenn ein Benutzer in mehreren Richtlinien desselben Typs definiert ist, wird nur die Richtlinie mit der höchsten Priorität auf sie angewendet. Alle verbleibenden Richtlinien dieses Typs werden nicht für den Benutzer ausgewertet (einschließlich der Standardrichtlinie).

Berücksichtigen Sie beispielsweise die folgenden Antiphishingrichtlinien in Microsoft Defender für Office 365, die für dieselben Benutzer gelten, und eine Nachricht, die sowohl als Identitätswechsel als auch als Spoofing identifiziert wird:

  ****

  |Richtlinienname|Priorität|Benutzeridentitätswechsel|Antis spoofing|
  |---|---|---|---|
  |Richtlinie A|1|Ein|Off|
  |Richtlinie B|2|Off|Ein|
  |

1. Die Nachricht wird als Spoof gekennzeichnet und behandelt, da spoofing eine höhere Priorität (4) hat als der Identitätswechsel des Benutzers (5).
2. Richtlinie A wird auf die Benutzer angewendet, da sie eine höhere Priorität als Richtlinie B hat.
3. Basierend auf den Einstellungen in Richtlinie A wird keine Aktion für die Nachricht ergriffen, da antis spoofing in der Richtlinie deaktiviert ist.
4. Die Richtlinienverarbeitung wird beendet, sodass Richtlinie B nie auf die Benutzer angewendet wird.

Da es möglich ist, dass dieselben Benutzer absichtlich oder unbeabsichtigt in mehrere benutzerdefinierte Richtlinien desselben Typs einbezogen werden, verwenden Sie die folgenden Entwurfsrichtlinien für benutzerdefinierte Richtlinien:

- Weisen Sie Richtlinien, die für eine kleine Anzahl von Benutzern gelten, eine höhere Priorität zu, und eine niedrigere Priorität für Richtlinien, die für eine große Anzahl von Benutzern gelten. Denken Sie daran, dass die Standardrichtlinie immer zuletzt angewendet wird.
- Konfigurieren Sie Ihre Richtlinien mit höherer Priorität so, dass sie strengere oder speziellere Einstellungen als Richtlinien mit niedrigerer Priorität haben.
- Erwägen Sie die Verwendung weniger benutzerdefinierter Richtlinien (verwenden Sie nur benutzerdefinierte Richtlinien für Benutzer, die strengere oder speziellere Einstellungen benötigen).
