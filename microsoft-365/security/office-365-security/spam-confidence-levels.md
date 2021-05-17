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
description: Administratoren können mehr über die Spamsicherheitsstufe (Spam Confidence Level, SCL) erfahren, die auf Nachrichten in EOP (EOP Exchange Online Protection angewendet wurde.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 951bbcb5fcbcc7b7916ee1c34c4ab489d54b6667
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204054"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Spam confidence level (SCL) in EOP

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden eingehende Nachrichten in EOP durch spamfiltert und erhalten eine Spampunktzahl. Diese Bewertung wird einer individuellen Spamvertrauensstufe (SCL) zugeordnet, die der Nachricht in einem X-Header hinzugefügt wird. Eine höhere SCL gibt an, dass es sich bei einer Nachricht wahrscheinlicher um Spam handelt. EOP führt eine Aktion für die Nachricht basierend auf der SCL aus.

Was die SCL bedeutet, und die Standardaktionen, die für Nachrichten ergriffen werden, werden in der folgenden Tabelle beschrieben. Weitere Informationen zu Aktionen, die Sie für Nachrichten basierend auf dem Spamfilter-Urteil ausführen können, finden Sie unter [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

****

|SCL|Definition|Standardaktion|
|:---:|---|---|
|-1|Die Nachricht hat die Spamfilterung übersprungen. Die Nachricht stammt beispielsweise von einem sicheren Absender, wurde an einen sicheren Empfänger gesendet oder stammt von einem E-Mail-Quellserver in der LISTE der zulässigen IP-Adressen. Weitere Informationen finden Sie unter [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).|Die Nachricht wird in das Postfach des Empfängers zugestellt.|
|0, 1|Die Spamfilterung hat festgestellt, dass es sich bei der Nachricht nicht um Spam handelte.|Die Nachricht wird in das Postfach des Empfängers zugestellt.|
|5, 6|Spamfilterung markierte die Nachricht als **Spam**|Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.|
|9 |Spamfilterung markierte die Nachricht als **Spam mit hoher Vertrauenssicherheit**|Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.|
|

Sie werden feststellen, dass SCL 2, 3, 4, 7 und 8 nicht von der Spamfilterung verwendet werden.

Sie können Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, um die SCL für Nachrichten zu stempeln. Wenn Sie eine Nachrichtenflussregel zum Festlegen der SCL verwenden, lösen die Werte 5 oder 6 die Spamfilteraktion für **Spam** aus, und die Werte 7, 8 oder 9 lösen die Spamfilteraktion für Spam mit hoher Sicherheit **aus.** Weitere Informationen finden Sie unter Verwenden von Nachrichtenflussregeln zum Festlegen der Spamsicherheitsstufe [(Spam Confidence Level, SCL) in Nachrichten](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Ähnlich wie beim SCL identifiziert die Massenbeschwerdestufe (Bulk Complaint Level, BCL) ungültige Massen-E-Mails (auch als _graue E-Mail bezeichnet)._ Ein höheres BCL-Niveau zeigt an, dass eine als Massensendung gesendete E-Mail mit größerer Wahrscheinlichkeit zu Beschwerden führen wird (und daher eher als Spam einzustufen ist). Sie konfigurieren den BCL-Schwellenwert in Antispamrichtlinien. Weitere Informationen finden Sie unter Konfigurieren von Antispamrichtlinien in EOP, Massenbeschwerdestufe [(BCL) in EOP)](bulk-complaint-level-values.md)und Was ist der Unterschied zwischen [Junk-E-Mail](configure-your-spam-filter-policies.md)und [Massen-E-Mail?](what-s-the-difference-between-junk-email-and-bulk-email.md).

****

![Das kurze Symbol für LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Entdecken Sie kostenlose Videokurse **für Microsoft 365 und IT-Profis,** die Ihnen von LinkedIn Learning zur Verfügung steht.
