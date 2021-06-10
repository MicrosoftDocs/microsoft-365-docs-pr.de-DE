---
title: Reihenfolge und Rangfolge des E-Mail-Schutzes
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Security Center, Microsoft 365 Defender-Portal, Microsoft Defender für Endpunkt, Microsoft Defender für Office 365, Microsoft Defender for Identity
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
description: Administratoren können mehr über die Anwendungsreihenfolge von Schutzmaßnahmen in Exchange Online Protection (EOP) erfahren und erfahren, wie der Prioritätswert in Schutzrichtlinien bestimmt, welche Richtlinie angewendet wird.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7243fd79287e19528e999774dbd0dd018fa86759
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877848"
---
# <a name="order-and-precedence-of-email-protection"></a>Reihenfolge und Rangfolge des E-Mail-Schutzes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer werden eingehende E-Mails möglicherweise durch mehrere Schutzformen gekennzeichnet. Beispielsweise die integrierten Antiphishingrichtlinien in EOP, die für alle Microsoft 365 Kunden verfügbar sind, und die stabileren Antiphishingrichtlinien, die Microsoft Defender für Office 365 Kunden zur Verfügung stehen. Nachrichten durchlaufen auch mehrere Erkennungsscans auf Schadsoftware, Spam, Phishing usw. Bei all dieser Aktivität kann es einige Verwirrung darüber geben, welche Richtlinie angewendet wird.

Im Allgemeinen wird eine Richtlinie, die auf eine Nachricht angewendet wird, im **X-Forefront-Antispam-Report-Header** in der **CAT -Eigenschaft (Category)** identifiziert. Weitere Informationen finden Sie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md).

Es gibt zwei wichtige Faktoren, die bestimmen, welche Richtlinie auf eine Nachricht angewendet wird:

- **Die Priorität des E-Mail-Schutztyps:** Diese Reihenfolge kann nicht konfiguriert werden und wird in der folgenden Tabelle beschrieben:

  <br>

  ****

  |Priorität|E-Mail-Schutz|Kategorie|Verwalten|
  |---|---|---|---|
  |1|Schadsoftware|CAT:MALW|[Konfigurieren von Antischadsoftwarerichtlinien in EOP](configure-anti-malware-policies.md)|
  |2|Phishing|CAT:PHSH|[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)|
  |3|Spam mit hoher Vertrauenswürdigkeit|CAT:HSPM|[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)|
  |4 |Spoofing|CAT:SPOOF|[Einblick in die Spoofintelligenz in EOP](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|Benutzeridentitätswechsel (geschützte Benutzer)|UIMP|[Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365](configure-atp-anti-phishing-policies.md)|
  |6<sup>\*</sup>|Domänenidentitätswechsel (geschützte Domänen)|DIMP|[Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365](configure-atp-anti-phishing-policies.md)|
  |7 |Spam|CAT:SPM|[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)|
  |8 |Masse|CAT:BULK|[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup>Diese Features sind nur in Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügbar.

- **Die Priorität der Richtlinie:** Für jede Art von Richtlinie (Antispam, Antischadsoftware, Antiphishing usw.) gibt es eine Standardrichtlinie, die für jeden gilt, Sie können jedoch benutzerdefinierte Richtlinien erstellen, die für bestimmte Benutzer gelten. Jede benutzerdefinierte Richtlinie hat einen Prioritätswert, der die Reihenfolge bestimmt, in der die Richtlinien angewendet werden. Die Standardrichtlinie wird immer zuletzt angewendet.

  Wenn ein Benutzer in mehreren Richtlinien desselben Typs definiert ist, wird nur die Richtlinie mit der höchsten Priorität auf sie angewendet. Alle verbleibenden Richtlinien dieses Typs werden für den Benutzer nicht ausgewertet (einschließlich der Standardrichtlinie).

Betrachten Sie beispielsweise die folgenden Antiphishingrichtlinien in Microsoft Defender für Office 365, die für **dieselben Benutzer gelten,** und eine Nachricht, die sowohl als Identitätswechsel als auch als Spoofing identifiziert wird:

<br>

****

|Richtlinienname|Priorität|Benutzeridentitätswechsel|Antispoofing|
|---|---|---|---|
|Richtlinie A|1|Ein|Aus|
|Richtlinie B|2|Aus|Ein|
|

1. Die Nachricht wird markiert und als Spoofing behandelt, da Spoofing eine höhere Priorität (4) hat als der Benutzeridentitätswechsel (5).
2. Richtlinie A wird auf die Benutzer angewendet, da sie eine höhere Priorität hat als Richtlinie B.
3. Basierend auf den Einstellungen in Richtlinie A wird keine Aktion für die Nachricht ausgeführt, da Antispoofing in der Richtlinie deaktiviert ist.
4. Die Richtlinienverarbeitung wird beendet, sodass Richtlinie B nie auf die Benutzer angewendet wird.

Da es möglich ist, dass dieselben Benutzer absichtlich oder unbeabsichtigt in mehrere benutzerdefinierte Richtlinien desselben Typs eingeschlossen werden, verwenden Sie die folgenden Entwurfsrichtlinien für benutzerdefinierte Richtlinien:

- Weisen Sie Richtlinien, die für eine kleine Anzahl von Benutzern gelten, eine höhere Priorität zu, und weisen Sie Richtlinien, die für eine große Anzahl von Benutzern gelten, eine niedrigere Priorität zu. Denken Sie daran, dass die Standardrichtlinie immer zuletzt angewendet wird.
- Konfigurieren Sie Ihre Richtlinien mit höherer Priorität so, dass sie strengere oder speziellere Einstellungen als Richtlinien mit niedrigerer Priorität haben.
- Erwägen Sie die Verwendung weniger benutzerdefinierter Richtlinien (verwenden Sie nur benutzerdefinierte Richtlinien für Benutzer, die strengere oder speziellere Einstellungen benötigen).
