---
title: BCL-Werte (Bulk Complaint Level)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Informationen zu BCL-Werten (Bulk Compliance Level) in Office 365.
ms.openlocfilehash: 82c006f05ce3d37ff23ca1e522b653bd26efeed8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035568"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a>Massen Reklamations Ebene (BCL) in Office 365

Massenversender unterscheiden sich in ihren Sende Mustern, der Inhaltserstellung und den Empfänger Akquisitions Methoden. Einige sind gute Massen-e-Mails, die gewünschte Nachrichten mit relevanten Inhalten an Ihre Abonnenten senden. Diese Nachrichten führen zu wenigen Beschwerden von Empfängern. Andere Absender verwenden unerwünschte Nachrichten, die den Kriterien für Spam sehr nahekommen und zu vielen Beschwerden von Empfängern führen. Nachrichten von einem Massen-Mailer werden als Massen-oder grau-e-Mail bezeichnet.

Um Nachrichten von verschiedenen Typen von Massen-e-Mails zu unterscheiden, wird eingehende e-Mails von Massen-e-Mails (Exchange Online oder eigenständiger Exchange Online Schutz (EoP) ohne Exchange Online Postfächer) eine Massen Beschwerde Ebene (BCL) zugewiesen, die der Nachricht in einer X-Kopfzeile hinzugefügt wird. Die BCL ähnelt der [SCL-Bewertung (Spam Confidence Level)](spam-confidence-levels.md) , die verwendet wird, um Nachrichten als Spam zu identifizieren. Eine höhere BCL gibt an, dass eine Massen Nachricht häufiger Beschwerden generiert (und daher eher Spam ist). Microsoft verwendet sowohl interne als auch Drittanbieterquellen, um Massen-e-Mails zu identifizieren und den entsprechenden BCL zu ermitteln.

 Bei der Spam Filterung werden Nachrichten als **Massen-e-Mails** auf der Grundlage des BCL-Schwellenwerts (der Standardwert oder ein von Ihnen festgelegter Wert) markiert und die angegebene Aktion für die Nachricht verwendet (die Standardaktion lautet "Nachricht an den Junk-e-Mail-Ordner des Empfängers senden" Weitere Informationen finden Sie unter [configure Anti-Spam Policies](configure-your-spam-filter-policies.md) und [Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mails?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Die BCL-Schwellenwerte werden in der folgenden Tabelle beschrieben.

|||
|:---:|---|
|**BCL**|**Beschreibung**|
|0|Die Nachricht stammt nicht von einem Massen-E-Mail-Absender.|
|1, 2, 3|Die Nachricht stammt von einem Massen-E-Mail-Absender, aber führt zu wenigen Beschwerden.|
|4, 5, 6, 7|Die Nachricht stammt von einem Massen-E-Mail-Absender und führt zu einer gemischten Anzahl von Beschwerden.|
|8, 9|Die Nachricht stammt von einem Massen Absender, der eine hohe Anzahl von Beschwerden generiert.|
|
