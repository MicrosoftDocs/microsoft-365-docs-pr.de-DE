---
title: Werte der Ebene für Massenbeanstandung
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Administratoren können sich über Werte der Massenkonformitätsstufe (Bulk Compliance Level, BCL) informieren, die in Exchange Online Protection (EOP) verwendet werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c68314cf992d39a105293955b6fade7b1a2bec56
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289895"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>BCL (Bulk Complaint Level) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer weist EOP eingehenden Nachrichten von Massen-E-Mail-Benutzern eine massenkonforme Ebene (BCL) zu. Der BCL wird der Nachricht in einem X-Header hinzugefügt und ähnelt dem [SCL (Spam Confidence Level),](spam-confidence-levels.md) mit dem Nachrichten als Spam identifiziert werden. Ein höherer BCL gibt an, dass eine Massennachricht mit höherer Wahrscheinlichkeit Beschwerden generiert (und daher mit höherer Wahrscheinlichkeit Spam ist). Microsoft verwendet sowohl interne als auch Drittanbieterquellen, um Massen-E-Mails zu identifizieren und den entsprechenden BCL zu ermitteln.

Massen-E-Mail-Absender variieren in ihren Sendemustern, Inhaltserstellungs- und Empfängererwerbsmethoden. Gute Massen-E-Mail-Nachrichten senden die gewünschten Nachrichten mit relevanten Inhalten an ihre Abonnenten. Diese Nachrichten führen zu wenigen Beschwerden von Empfängern. Andere Absender verwenden unerwünschte Nachrichten, die den Kriterien für Spam sehr nahekommen und zu vielen Beschwerden von Empfängern führen. Nachrichten von einem Massen-E-Mail-Nachrichten werden als Massen-E-Mails oder graue E-Mails bezeichnet.

 Die Spamfilterung  markiert Nachrichten als Massen-E-Mail basierend auf dem BCL-Schwellenwert (standardwert oder einem von Ihnen angegebenen Wert) und führt die angegebene Aktion für die Nachricht aus (die Standardaktion besteht in der Bereitstellung der Nachricht an den Junk-E-Mail-Ordner des Empfängers). Weitere Informationen finden Sie unter ["Konfigurieren von Antispamrichtlinien"](configure-your-spam-filter-policies.md) und was [ist der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Die BCL-Schwellenwerte werden in der folgenden Tabelle beschrieben.

****

|BCL|Beschreibung|
|:---:|---|
|0|Die Nachricht stammt nicht von einem Massen-E-Mail-Absender.|
|1, 2, 3|Die Nachricht stammt von einem Massen-E-Mail-Absender, aber führt zu wenigen Beschwerden.|
|4, 5, 6, 7<sup>\*</sup>|Die Nachricht stammt von einem Massen-E-Mail-Absender und führt zu einer gemischten Anzahl von Beschwerden.|
|8, 9|Die Nachricht stammt von einem Massensender, der eine hohe Anzahl von Beschwerden generiert.|
|

<sup>\*</sup> Dies ist der Standardschwellenwert, der in Antispamrichtlinien verwendet wird.
