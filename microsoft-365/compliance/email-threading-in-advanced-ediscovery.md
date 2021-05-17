---
title: E-Mail-Threading in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Beim Durchführen einer Advanced eDiscovery analysiert das E-Mail-Threading eine E-Mail-Unterhaltung und trennt jede Nachricht in verschiedene Kategorien.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285561"
---
# <a name="email-threading-in-advanced-ediscovery"></a>E-Mail-Threading in Advanced eDiscovery

Betrachten Sie eine E-Mail-Unterhaltung, die seit einer Weile läuft. In den meisten Fällen enthält die letzte E-Mail im Thread den Inhalt aller vorherigen E-Mails. Wenn Sie die letzte E-Mail überprüfen, erhalten Sie einen vollständigen Kontext der Unterhaltung, die im Thread passiert ist. Durch E-Mail-Threading werden solche E-Mails identifiziert, sodass Prüfer einen Bruchteil der gesammelten Dokumente überprüfen können, ohne einen Kontext zu verlieren.

## <a name="what-does-email-threading-do"></a>Was macht E-Mail-Threading?

E-Mail-Threading analysiert jede E-Mail und destrukturiert sie an einzelne Nachrichten. Jede E-Mail ist eine Kette von einzelnen Nachrichten. Anschließend werden alle E-Mails im Überprüfungssatz analysiert, um festzustellen, ob eine E-Mail eindeutigen Inhalt hat oder ob die Kette vollständig in einer anderen E-Mail enthalten ist. Am Ende werden E-Mails in vier Kategorien unterteilt:

- **Inklusiv**: Die letzte Nachricht der E-Mail hat einen eindeutigen Inhalt, und die E-Mail enthält alle Anhänge, die Teil anderer E-Mails waren, deren Inhalt vollständig in dieser E-Mail angezeigt wird.

- **Inklusiv – Minus**: Die letzte Nachricht in der E-Mail hat einen eindeutigen Inhalt, aber einige Anhänge, die Teil anderer E-Mails waren, deren Inhalt vollständig in dieser E-Mail angezeigt wird, sind nicht in dieser E-Mail enthalten.

- **Inklusiv – Kopie**: Eine genaue Kopie einer als „Inklusiv“ bzw. „Inklusiv – Minus“ gekennzeichneten E-Mail.

- **Ohne**: Der Inhalt dieser E-Mail ist vollständig in mindestens einer als „Inklusiv“ bzw. „Inklusiv – Minus“ gekennzeichneten E-Mail enthalten.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>Wie unterscheiden sie sich von Unterhaltungen in Outlook?

Auf einen Blick klingt dies ähnlich wie bei Unterhaltungsgruppen in Outlook. Es gibt jedoch einige wichtige Unterschiede. Stellen Sie sich eine E-Mail-Unterhaltung vor, die in zwei Unterhaltungen gegabelt wurde. Beispielsweise hat jemand auf eine E-Mail geantwortet, die nicht die neueste in der Unterhaltung ist, sodass die letzten beiden E-Mails in der Unterhaltung jeweils eindeutige Inhalte haben.

Outlook die E-Mails weiterhin in einer einzigen Unterhaltung gruppieren. Wenn Sie nur die letzte E-Mail lesen, würde der Kontext der vorletzten E-Mail fehlen, die auch eindeutige Inhalte enthält. Da das E-Mail-Threading jede E-Mail in einzelne Komponenten analysiert und vergleicht, würde das E-Mail-Threading die beiden letzten E-Mails als inklusive e-Mail markieren, um sicherzustellen, dass Sie keinen Kontext verpassen, solange Sie alle als inklusiv markierten E-Mails lesen.
