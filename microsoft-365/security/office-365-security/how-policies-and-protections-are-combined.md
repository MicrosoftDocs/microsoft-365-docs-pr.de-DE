---
title: Reihenfolge und Priorität des e-Mail-Schutzes in Office 365
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitscenter, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
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
ms.collection:
- M365-security-compliance
description: Beschreibt die Anwendungsreihenfolge von Office 365 Schutz sowie die Art und Weise, wie der Prioritätswert in Schutzrichtlinien festlegt, welche Richtlinie angewendet wird.
ms.openlocfilehash: 9f2033b1ec066c1f8501ce019b8f8c7f3748fd15
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895335"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a>Reihenfolge und Priorität des e-Mail-Schutzes in Office 365

Als Office 365 Benutzer können Ihre eingehenden e-Mails durch mehrere Schutzformen gekennzeichnet werden. Beispielsweise die integrierten EoP-Anti-Phishing-Richtlinien, die allen Office 365 Kunden zur Verfügung stehen, und die robusteren ATP-Richtlinien für die Anti-Phishing, die auch Office 365 Advanced Threat Protection-Kunden zur Verfügung stehen. Nachrichten werden auch durch mehrere Erkennungs Scans für Schadsoftware, Spam, Phishing, usw. geleitet. Angesichts all dieser Aktivitäten kann es einige Verwirrung darüber geben, welche Richtlinie angewendet wird.

Im Allgemeinen wird eine Richtlinie, die auf eine Nachricht angewendet wird, im **X-Forefront-Antispam-Report-** Header in der Cat-Eigenschaft **(Category)** identifiziert. Weitere Informationen finden Sie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md).

Es gibt zwei Hauptfaktoren, die bestimmen, welche Richtlinie auf eine Nachricht angewendet wird:

- **Die Priorität des e-Mail-Schutztyps**: Diese Reihenfolge kann nicht konfiguriert werden und wird in der folgenden Tabelle beschrieben:

  |||||
  |---|---|---|---|
  |**Priority**|**E-Mail-Schutz**|**Kategorie**|**Verwalten von**|
  |1|Schadsoftware|Kat: MALW|[Konfigurieren von Anti-Malware-Richtlinien in Office 365](configure-anti-malware-policies.md)|
  |2|Phishing-E-Mail|Kat: PHSH|[Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md)|
  |3|Spam mit hoher Vertrauenswürdigkeit|Kat: HSPM|[Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md)|
  |4 |Spoofing|Kat: Spoof|[Einrichten von Office 365 ATP-Richtlinien für Anti-Phishing und Anti-Phishing](set-up-anti-phishing-policies.md) <Br/><br/> [Weitere Informationen zu Spoofing Intelligence](learn-about-spoof-intelligence.md)|
  |5 |Spam|Kat: SPM|[Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md)|
  |6 |Massensendung|Kat: Bulk|[Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|Domänen Identitätswechsel|DIMP|[Einrichten von Office 365 ATP-Richtlinien für Anti-Phishing und Anti-Phishing](set-up-anti-phishing-policies.md)|
  |8<sup>\*</sup>|Benutzeridentitätswechsel|Uimp|[Einrichten von Office 365 ATP-Richtlinien für Anti-Phishing und Anti-Phishing](set-up-anti-phishing-policies.md)|
  |

  <sup>\*</sup>Diese Funktionen sind nur in ATP verfügbar.

- **Die Priorität der Richtlinie**: für jeden Schutztyp (Antispam, Antischadsoftware, Antiphishing usw.) gibt es eine Standardrichtlinie, die für alle gilt, aber Sie können benutzerdefinierte Richtlinien erstellen, die für bestimmte Benutzer gelten. Jede benutzerdefinierte Richtlinie verfügt über einen Prioritätswert, der die Reihenfolge festlegt, in der die Richtlinien angewendet werden. Die Standardrichtlinie wird immer zuletzt angewendet.

  Wenn ein Benutzer in mehreren benutzerdefinierten Richtlinien definiert ist, wird nur die Richtlinie mit der höchsten Priorität auf diese angewendet. Alle verbleibenden Richtlinien werden für den Benutzer (einschließlich der Standardrichtlinie) nicht ausgewertet.

Sehen Sie sich beispielsweise die folgenden AntiPhishing-Richtlinien an, die **für dieselben Benutzer gelten**, und eine Nachricht, die sowohl als Benutzeridentitätswechsel als auch als Spoofing identifiziert wird:

  |||||
  |---|---|---|---|
  |**Anti-Spam-Richtlinie**|**Priority**|**Benutzeridentitätswechsel (ATP)**|**Anti-Spoofing (EoP)**|
  |Richtlinie A|1|Ein|Off|
  |Richtlinie B|2|Off|Ein|
  |

1. Die Nachricht wird als spoof gekennzeichnet und behandelt, da Spoofing eine höhere Priorität (4) als der Benutzeridentitätswechsel (8) hat.
2. Richtlinie A wird auf die Benutzer angewendet, da Sie eine höhere Priorität als Priorität B hat.
3. Basierend auf den Einstellungen in Richtlinie A wird keine Aktion für die Nachricht ausgeführt, da die Antispoofing-Funktion in der Richtlinie deaktiviert ist.
4. Die Anti-Spam-Richtlinienverarbeitung wird angehalten, daher wird Richtlinie B nie auf die Benutzer angewendet.

Da es möglich ist, viele Benutzer in vielen benutzerdefinierten Richtlinien desselben Typs zu verwenden, sollten Sie die folgenden Entwurfsrichtlinien für benutzerdefinierte Richtlinien beachten:

- Zuweisen einer höheren Priorität zu Richtlinien, die für eine kleine Anzahl von Benutzern gelten, und eine niedrigere Priorität für Richtlinien, die für eine große Anzahl von Benutzern gelten. Denken Sie daran, dass die Standardrichtlinie immer zuletzt angewendet wird.
- Konfigurieren Sie Ihre Richtlinien mit höherer Priorität so, dass Sie strengere oder speziellere Einstellungen als Richtlinien niedrigerer Priorität haben.
- Sie sollten weniger benutzerdefinierte Richtlinien verwenden (verwenden Sie nur benutzerdefinierte Richtlinien für Benutzer, die strengere oder speziellere Einstellungen benötigen).
