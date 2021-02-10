---
title: Spam Confidence Level
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
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können mehr über die SCL (Spam Confidence Level) erfahren, die auf Nachrichten in Exchange Online Protection (EOP) angewendet wurde.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e4fc20b7d7db5b85b5bdde02ab720fa26af2a4b5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167155"
---
# <a name="spam-confidence-level-scl-in-eop"></a>SCL (Spam Confidence Level) in EOP

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden eingehende Nachrichten über die Spamfilterung in EOP gesendet und erhalten eine Spam-Bewertung. Diese Bewertung wird einer individuellen SCL (Spam Confidence Level) zugeordnet, die der Nachricht in einem X-Header hinzugefügt wird. Ein höherer SCL gibt an, dass eine Nachricht mit höherer Wahrscheinlichkeit Spam ist. EOP führt eine Aktion für die Nachricht basierend auf dem SCL aus.

Was der SCL bedeutet und welche Standardaktionen für Nachrichten ergriffen werden, wird in der folgenden Tabelle beschrieben. Weitere Informationen zu Aktionen, die Sie basierend auf der Spamfilterungs-EOP für Nachrichten ausführen können, finden Sie unter "Konfigurieren von [Antispamrichtlinien in EOP".](configure-your-spam-filter-policies.md)

****

|SCL|Definition|Standardaktion|
|:---:|---|---|
|-1|Die Nachricht hat die Spamfilterung übersprungen. Die Nachricht stammt beispielsweise von einem sicheren Absender, wurde an einen sicheren Empfänger gesendet oder stammt von einem E-Mail-Quellserver in der IP-Liste. Weitere Informationen finden Sie unter [Erstellen von Listen sicherer Absender in EOP](create-safe-sender-lists-in-office-365.md).|Die Nachricht wird in das Postfach des Empfängers zugestellt.|
|0, 1|Die Spamfilterung hat festgestellt, dass es sich bei der Nachricht nicht um Spam handelte.|Die Nachricht wird in das Postfach des Empfängers zugestellt.|
|5, 6|Spamfilterung hat die Nachricht als **Spam markiert**|Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.|
|9 |Spamfilterung hat die Nachricht als Spam **mit hoher Confidence gekennzeichnet**|Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.|
|

Sie werden feststellen, dass SCL 2, 3, 4, 7 und 8 nicht von der Spamfilterung verwendet werden.

Sie können Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, um den SCL für Nachrichten zu stempeln. **Wenn** Sie eine Nachrichtenflussregel zum Festlegen der SCL verwenden, lösen die Werte 5 oder 6 die Spamfilteraktion für **Spam** aus, und die Werte 7, 8 oder 9 lösen die Spamfilterungsaktion für Spam mit hoher Spamsicherheit aus. Weitere Informationen finden Sie unter Verwenden von [Nachrichtenflussregeln zum Festlegen der SCL (Spam Confidence Level) in Nachrichten.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

Ähnlich wie der SCL identifiziert der BCL (Bulk Complaint Level) ungültige Massen-E-Mails (auch als _graue E-Mail bezeichnet)._ Ein höheres BCL-Niveau zeigt an, dass eine als Massensendung gesendete E-Mail mit größerer Wahrscheinlichkeit zu Beschwerden führen wird (und daher eher als Spam einzustufen ist). Sie konfigurieren den BCL-Schwellenwert in Antispamrichtlinien. Weitere Informationen finden Sie unter "Konfigurieren von Antispamrichtlinien in EOP", ["Bulk Complaint Level" (BCL) in EOP)](bulk-complaint-level-values.md)und Was ist der Unterschied zwischen [Junk-E-Mail](configure-your-spam-filter-policies.md)und Massen-E-Mail? [](what-s-the-difference-between-junk-email-and-bulk-email.md)

****

![Das kurze Symbol für LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Entdecken Sie kostenlose Videokurse für **Microsoft 365-Administratoren** und IT-Profis, die Ihnen von LinkedIn Learning angeboten werden.
