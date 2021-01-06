---
title: Reihenfolge und Priorität des e-Mail-Schutzes
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitscenter, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
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
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die Anwendungsreihenfolge von Schutzmaßnahmen in Exchange Online Protection (EoP) und darüber informieren, wie der Prioritätswert in Schutzrichtlinien festlegt, welche Richtlinie angewendet wird.
ms.openlocfilehash: a18234344e1100f3b6a03c10e970c8195e53e7df
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760566"
---
# <a name="order-and-precedence-of-email-protection"></a>Reihenfolge und Priorität des e-Mail-Schutzes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer werden eingehende e-Mails möglicherweise von mehreren Schutzformen gekennzeichnet. Beispielsweise die integrierten Anti-Phishing-Richtlinien in EoP, die allen Microsoft 365-Kunden zur Verfügung stehen, sowie die robusteren AntiPhishing-Richtlinien, die Microsoft Defender für Office 365 Kunden zur Verfügung stehen. Nachrichten werden auch durch mehrere Erkennungs Scans für Schadsoftware, Spam, Phishing, usw. geleitet. Angesichts all dieser Aktivitäten kann es einige Verwirrung darüber geben, welche Richtlinie angewendet wird.

Im Allgemeinen wird eine Richtlinie, die auf eine Nachricht angewendet wird, im **X-Forefront-Antispam-Report-** Header in der Cat-Eigenschaft **(Category)** identifiziert. Weitere Informationen finden Sie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md).

Es gibt zwei Hauptfaktoren, die bestimmen, welche Richtlinie auf eine Nachricht angewendet wird:

- **Die Priorität des e-Mail-Schutztyps**: Diese Reihenfolge kann nicht konfiguriert werden und wird in der folgenden Tabelle beschrieben:

  ****

  |Priorität|E-Mail-Schutz|Kategorie|Verwalten von|
  |---|---|---|---|
  |1 |Schadsoftware|Kat: MALW|[Konfigurieren von Anti-Malware-Richtlinien in EoP](configure-anti-malware-policies.md)|
  |2 |Phishing|Kat: PHSH|[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)|
  |3 |Spam mit hoher Vertrauenswürdigkeit|Kat: HSPM|[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)|
  |4 |Spoofing|Kat: Spoof|[Konfigurieren von Spoof Intelligence in EoP](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|Benutzeridentitätswechsel (geschützte Benutzer)|Uimp|[Konfigurieren von Anti-Phishing-Richtlinien in Microsoft Defender für Office 365](configure-atp-anti-phishing-policies.md)|
  |6<sup>\*</sup>|Domänen Identitätswechsel (geschützte Domänen)|DIMP|[Konfigurieren von Anti-Phishing-Richtlinien in Microsoft Defender für Office 365](configure-atp-anti-phishing-policies.md)|
  |7 |Spam|Kat: SPM|[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)|
  |8 |Masse|Kat: Bulk|[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> Diese Features stehen nur in Anti-Phishing-Richtlinien in Microsoft Defender für Office 365 zur Verfügung.

- **Die Priorität der Richtlinie**: für jeden Schutztyp (Antispam, Antischadsoftware, Antiphishing usw.) gibt es eine Standardrichtlinie, die für alle gilt, aber Sie können benutzerdefinierte Richtlinien erstellen, die für bestimmte Benutzer gelten. Jede benutzerdefinierte Richtlinie verfügt über einen Prioritätswert, der die Reihenfolge festlegt, in der die Richtlinien angewendet werden. Die Standardrichtlinie wird immer zuletzt angewendet.

  Wenn ein Benutzer in mehreren Richtlinien desselben Typs definiert ist, wird nur die Richtlinie mit der höchsten Priorität auf diese angewendet. Alle verbleibenden Richtlinien dieses Typs werden nicht für den Benutzer ausgewertet (einschließlich der Standardrichtlinie).

Nehmen wir beispielsweise die folgenden AntiPhishing-Richtlinien in Microsoft Defender für Office 365, die für **dieselben Benutzer gelten**, und eine Nachricht, die sowohl als Benutzeridentitätswechsel als auch als Spoofing identifiziert wird:

  ****

  |Name der Richtlinie|Priorität|Benutzeridentitätswechsel|Anti-Spoofing|
  |---|---|---|---|
  |Richtlinie A|1 |Ein|Off|
  |Richtlinie B|2 |Off|Ein|
  |

1. Die Nachricht wird als spoof gekennzeichnet und behandelt, da Spoofing eine höhere Priorität (4) als der Benutzeridentitätswechsel (5) hat.
2. Richtlinie A wird auf die Benutzer angewendet, da Sie eine höhere Priorität als Richtlinie B hat.
3. Basierend auf den Einstellungen in Richtlinie A wird keine Aktion für die Nachricht ausgeführt, da die Antispoofing-Funktion in der Richtlinie deaktiviert ist.
4. Die Richtlinienverarbeitung wird angehalten, sodass Richtlinie B niemals auf die Benutzer angewendet wird.

Da es möglich ist, dass dieselben Benutzer absichtlich oder unbeabsichtigt in mehreren benutzerdefinierten Richtlinien desselben Typs enthalten sind, verwenden Sie die folgenden Entwurfsrichtlinien für benutzerdefinierte Richtlinien:

- Zuweisen einer höheren Priorität zu Richtlinien, die für eine kleine Anzahl von Benutzern gelten, und eine niedrigere Priorität für Richtlinien, die für eine große Anzahl von Benutzern gelten. Denken Sie daran, dass die Standardrichtlinie immer zuletzt angewendet wird.
- Konfigurieren Sie Ihre Richtlinien mit höherer Priorität so, dass Sie strengere oder speziellere Einstellungen als Richtlinien niedrigerer Priorität haben.
- Sie sollten weniger benutzerdefinierte Richtlinien verwenden (verwenden Sie nur benutzerdefinierte Richtlinien für Benutzer, die strengere oder speziellere Einstellungen benötigen).
