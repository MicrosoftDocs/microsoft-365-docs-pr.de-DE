---
title: Massenbeschwerdungsebenenwerte
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
description: Administratoren können sich über BCL-Werte (Bulk Compliance Level) informieren, die in Exchange Online Protection (EOP) verwendet werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d85dca6e18ebdad4d8f2a5c5f6c5b613c23b47d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065440"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Massenbeschwerdestufe (Bulk Complaint Level, BCL) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer weist EOP eingehenden Nachrichten von Massen-E-Mail-Benutzern eine massenkonforme Ebene (BCL) zu. Die BCL wird der Nachricht in einem X-Header hinzugefügt und ähnelt der Spam confidence [level (SCL),](spam-confidence-levels.md) die zum Identifizieren von Nachrichten als Spam verwendet wird. Eine höhere BCL gibt an, dass eine Massennachricht mit höherer Wahrscheinlichkeit Beschwerden generiert (und daher eher Spam ist). Microsoft verwendet sowohl interne als auch Drittanbieterquellen, um Massen-E-Mails zu identifizieren und die entsprechende BCL zu ermitteln.

Massen-E-Mails variieren in ihren Sendemustern, inhaltserstellungs- und Empfängererwerbspraktiken. Gute Massen-E-Mail-Nachrichten senden gewünschte Nachrichten mit relevanten Inhalten an ihre Abonnenten. Diese Nachrichten führen zu wenigen Beschwerden von Empfängern. Andere Absender verwenden unerwünschte Nachrichten, die den Kriterien für Spam sehr nahekommen und zu vielen Beschwerden von Empfängern führen. Nachrichten von einem Massen-E-Mail-Nachrichten werden als Massen-E-Mails oder graue E-Mails bezeichnet.

 Die Spamfilterung  markiert Nachrichten als Massen-E-Mail basierend auf dem BCL-Schwellenwert (standardwert oder einen von Ihnen angegebenen Wert) und führt die angegebene Aktion für die Nachricht aus (die Standardaktion ist, dass die Nachricht an den Junk-E-Mail-Ordner des Empfängers zugestellt wird). Weitere Informationen finden Sie unter Konfigurieren von Antispamrichtlinien und Was ist der Unterschied zwischen [Junk-E-Mails](configure-your-spam-filter-policies.md) [und Massen-E-Mails?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Die BCL-Schwellenwerte werden in der folgenden Tabelle beschrieben.

****

|BCL|Beschreibung|
|:---:|---|
|0|Die Nachricht stammt nicht von einem Massen-E-Mail-Absender.|
|1, 2, 3|Die Nachricht stammt von einem Massen-E-Mail-Absender, aber führt zu wenigen Beschwerden.|
|4, 5, 6, 7<sup>\*</sup>|Die Nachricht stammt von einem Massen-E-Mail-Absender und führt zu einer gemischten Anzahl von Beschwerden.|
|8, 9|Die Nachricht stammt von einem Massensender, der eine hohe Anzahl von Beschwerden generiert.|
|

<sup>\*</sup> Dies ist der Standardwert, der in Antispamrichtlinien verwendet wird.
