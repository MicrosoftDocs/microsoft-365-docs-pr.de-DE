---
title: Werte für Massen Reklamations Stufen
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
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Administratoren können Informationen zu den Werten für die Massen Konformitätsstufe (BCL) erhalten, die in Exchange Online Protection (EoP) verwendet werden.
ms.openlocfilehash: e24c0c97afcca2e7aa014d929d7b2131c6a2d074
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827433"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Massen Reklamations Ebene (BCL) in EoP

In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer weist EoP eingehenden Nachrichten von Massen versandern eine Massen konforme Ebene (BCL) zu. Die BCL wird der Nachricht in einer X-Kopfzeile hinzugefügt und ähnelt der [SCL-Bewertung (Spam Confidence Level)](spam-confidence-levels.md) , die zum Identifizieren von Nachrichten als Spam verwendet wird. Eine höhere BCL gibt an, dass eine Massen Nachricht häufiger Beschwerden generiert (und daher eher Spam ist). Microsoft verwendet sowohl interne als auch Drittanbieterquellen, um Massen-e-Mails zu identifizieren und den entsprechenden BCL zu ermitteln.

Massenversender unterscheiden sich in ihren Sende Mustern, der Inhaltserstellung und den Empfänger Akquisitions Methoden. Gute Massenversender senden gewünschte Nachrichten mit relevanten Inhalten an Ihre Abonnenten. Diese Nachrichten führen zu wenigen Beschwerden von Empfängern. Andere Absender verwenden unerwünschte Nachrichten, die den Kriterien für Spam sehr nahekommen und zu vielen Beschwerden von Empfängern führen. Nachrichten von einem Massen-Mailer werden als Massen-oder grau-e-Mail bezeichnet.

 Bei der Spam Filterung werden Nachrichten als **Massen-e-Mails** auf der Grundlage des BCL-Schwellenwerts (der Standardwert oder ein von Ihnen festgelegter Wert) markiert und die angegebene Aktion für die Nachricht verwendet (die Standardaktion lautet "Nachricht an den Junk-e-Mail-Ordner des Empfängers senden" Weitere Informationen finden Sie unter [configure Anti-Spam Policies](configure-your-spam-filter-policies.md) und [Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mails?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Die BCL-Schwellenwerte werden in der folgenden Tabelle beschrieben.

****

|BCL|Beschreibung|
|:---:|---|
|0|Die Nachricht stammt nicht von einem Massen-E-Mail-Absender.|
|1, 2, 3|Die Nachricht stammt von einem Massen-E-Mail-Absender, aber führt zu wenigen Beschwerden.|
|4, 5, 6, 7|Die Nachricht stammt von einem Massen-E-Mail-Absender und führt zu einer gemischten Anzahl von Beschwerden.|
|8, 9|Die Nachricht stammt von einem Massen Absender, der eine hohe Anzahl von Beschwerden generiert.|
|
