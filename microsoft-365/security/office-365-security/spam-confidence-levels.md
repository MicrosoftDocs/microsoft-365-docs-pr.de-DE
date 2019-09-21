---
title: SCL-Bewertungen (Spam Confidence Level)
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: Wenn eine E-Mail die Spamfilterung passiert, wird ihr eine Spambewertung zugewiesen. Diese Bewertung ist einer individuellen SCL-Bewertung (Spam Confidence Level) zugeordnet und wird als Stempel im X-Header angezeigt. Der Dienst verfährt mit den Nachrichten entsprechend der Spam Confidence-Interpretation der SCL-Bewertung. In der folgenden Tabelle ist aufgeführt, wie die unterschiedlichen SCL-Bewertungen von den Filtern interpretiert werden, und welche Aktionen standardmäßig für eingehende Nachrichten als Reaktion auf die einzelnen Bewertung erfolgen.
ms.openlocfilehash: 93b3886e1128024f3f7f2a844e2ed603e27d9b2a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082643"
---
# <a name="spam-confidence-levels"></a>SCL-Bewertungen (Spam Confidence Level)

Wenn eine E-Mail die Spamfilterung passiert, wird ihr eine Spambewertung zugewiesen. Diese Bewertung ist einer individuellen SCL-Bewertung (Spam Confidence Level) zugeordnet und wird als Stempel im X-Header angezeigt. Der Dienst verfährt mit den Nachrichten entsprechend der Spam Confidence-Interpretation der SCL-Bewertung. In der folgenden Tabelle ist aufgeführt, wie die unterschiedlichen SCL-Bewertungen von den Filtern interpretiert werden, und welche Aktionen standardmäßig für eingehende Nachrichten als Reaktion auf die einzelnen Bewertung erfolgen.
  
|**SCL-Bewertung**|**Spam Confidence-Interpretation**|**Standardaktion**|
|:-----|:-----|:-----|
|-1|Nicht-Spam, der von einem sicheren Absender, einem sicheren Empfänger oder einer sicheren aufgeführten IP-Adresse (vertrauenswürdiger Partner) stammt.|Die Nachricht wird in das Postfach des Empfängers zugestellt.|
|0, 1|Nicht-Spam, da die Nachricht überprüft und als bereinigt festgelegt wurde.|Die Nachricht wird in das Postfach des Empfängers zugestellt.|
|5, 6|Spam|Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.|
|7, 8, 9|Spam mit hoher Vertrauenswürdigkeit|Die Nachricht wird in den Ordner "Junk-E-Mail" des Empfängers zugestellt.|
   
> [!TIP]
> SCL-Bewertungen von 2, 3, 4, 7 und 8 werden vom Dienst nicht festgelegt. Eine SCL-Bewertung von 5 oder 6 wird als mutmaßlicher Spam betrachtet, der weniger sicher als Spam ist als eine SCL-Bewertung von 9, die als bestimmter Spam betrachtet wird. Unterschiedliche Aktionen für Spam und Spam mit hoher Vertrauenswürdigkeit können über Ihre Inhaltsfilter Richtlinien in der Exchange-Verwaltungskonsole konfiguriert werden. Weitere Informationen finden Sie unter [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md). Sie können auch die SCL-Bewertung für Nachrichten festlegen, die bestimmten Bedingungen unter Verwendung von Nachrichtenfluss Regeln (auch bekannt als Transportregeln) entsprechen, wie in [Verwenden von Nachrichtenfluss Regeln beschrieben, um den SCL-Wert (Spam Confidence Level) in Nachrichten festzulegen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md). Wenn Sie eine e-Mail-Fluss Regel zum Festlegen der SCL-Bewertung von 7, 8 oder 9 verwenden, wird die Nachricht als Spam mit hoher Vertrauenswürdigkeit behandelt. 
  
||
|:-----|
|![Das Kurzsymbol für LinkedIn Learning](../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Neu bei Office 365?**         Entdecken Sie die kostenlosen Videokurse für **Office 365 admins and IT pros**, präsentiert von LinkedIn Learning.|
   

