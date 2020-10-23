---
title: Microsoft 365 Compliance-Unterstützung für Versionshinweise zu Doppelbyte-Zeichensätzen (Vorschau)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Versionshinweise zur Unterstützung von Doppelbyte-Zeichensätzen.
ms.openlocfilehash: 1c2244c49a92aa2c00fad06caa8194cf7e32220e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681501"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a>Unterstützung für Versionshinweise zu Doppelbyte-Zeichensätzen (Vorschau)

 Microsoft 365 Information Protection unterstützt jetzt in der Vorschau Sprachen mit Doppelbyte-Zeichensätzen für:

- Chinesisch (vereinfacht)
- Chinesisch (traditionell)
- Koreanisch
- Japanisch

Diese Unterstützung ist für vertrauliche Informationstypen und Stichwort-Wörterbücher verfügbar und wird in den Lösungen Data Loss Prevention, Communications Compliance, Exchange Online, Microsoft Office SharePoint Online, Microsoft OneDrive for Business und Microsoft Teams widergespiegelt.

## <a name="known-issues"></a>Bekannte Probleme

- Wenn eine an eine E-Mail angehängte Textdatei im UTF-8-Format ohne Byte-Order-Markierung (BOM) vorliegt, wird die E-Mail von der Kommunikationscompliance-Richtlinie nicht erkannt.

- Kommunikationscompliance-Richtlinien können keine Werte erkennen, wenn ein Satz für die Richtlinienbedingung eingegeben wird: "Nachricht enthält eines dieser Wörter". Wenn der in der Richtlinie angegebene Text als Wort geschrieben ist, kann er erkannt werden. Befindet sich der Text jedoch in der Mitte eines Satzes, wird er nicht erkannt.

- Kommunikationscompliance-Richtlinien, die Wörterbücher als Typinformationen angeben, erkennen private Teams-Chats und Teams-Channel-Chats nicht.

- Die folgenden Bedingungen werden für die Kommunikationscompliance-Richtlinie zum gegenwärtigen Zeitpunkt nicht unterstützt (wir planen, diese Probleme in Zukunft zu beheben): 
  - „Nachricht enthält eines dieser Wörter“
  - „Nachricht enthält keines dieser Wörter“
  - „Anlage enthält eines dieser Wörter“
  - „Anlage enthält eines dieser Wörter“

Stattdessen empfehlen wir, einen benutzerdefinierten Typ sensibler Informationen (SIT) mit einem Schlüsselwörterbuch zu erstellen, der Muster in Nachrichten und Anhängen erkennt. Der benutzerdefinierte SIT sollte als Bedingung für die Kommunikationscompliance-Richtlinie zu verwenden.
