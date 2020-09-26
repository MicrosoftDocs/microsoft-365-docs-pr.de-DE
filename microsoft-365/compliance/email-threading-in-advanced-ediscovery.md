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
description: Bei der Durchführung einer erweiterten eDiscovery-Analyse analysiert e-Mail-Threading eine e-Mail-Unterhaltung und trennt jede Nachricht in verschiedene Kategorien.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285561"
---
# <a name="email-threading-in-advanced-ediscovery"></a>E-Mail-Threading in Advanced eDiscovery

Ziehen Sie eine e-Mail-Unterhaltung in Frage, die schon eine Weile vorgeht. In den meisten Fällen enthält die letzte e-Mail im Thread die Inhalte aller vorherigen e-Mails. Wenn Sie die letzte e-Mail überprüfen, erhalten Sie einen vollständigen Kontext der Unterhaltung, die im Thread aufgetreten ist. E-Mail-Threading identifiziert solche e-Mails, sodass Bearbeiter einen Bruchteil der gesammelten Dokumente überprüfen können, ohne dass ein Kontext verloren geht.

## <a name="what-does-email-threading-do"></a>Was bewirkt das e-Mail-Threading?

E-Mail-Threading analysiert jede e-Mail und dekonstruiert Sie in einzelne Nachrichten; jede e-Mail ist eine Kette einzelner Nachrichten. Anschließend werden alle e-Mails in der Überprüfungsgruppe analysiert, um festzustellen, ob eine e-Mail über eindeutige Inhalte verfügt oder ob die Kette vollständig in einer anderen e-Mail enthalten ist. Am Ende werden e-Mails in vier Kategorien unterteilt:

- **Inklusiv**: Die letzte Nachricht der E-Mail hat einen eindeutigen Inhalt, und die E-Mail enthält alle Anhänge, die Teil anderer E-Mails waren, deren Inhalt vollständig in dieser E-Mail angezeigt wird.

- **Inklusiv – Minus**: Die letzte Nachricht in der E-Mail hat einen eindeutigen Inhalt, aber einige Anhänge, die Teil anderer E-Mails waren, deren Inhalt vollständig in dieser E-Mail angezeigt wird, sind nicht in dieser E-Mail enthalten.

- **Inklusiv – Kopie**: Eine genaue Kopie einer als „Inklusiv“ bzw. „Inklusiv – Minus“ gekennzeichneten E-Mail.

- **Ohne**: Der Inhalt dieser E-Mail ist vollständig in mindestens einer als „Inklusiv“ bzw. „Inklusiv – Minus“ gekennzeichneten E-Mail enthalten.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>Wie unterscheidet er sich von den Unterhaltungen in Outlook?

Dies klingt auf einen Blick ähnlich wie Konversations Gruppierungen in Outlook. Es gibt jedoch einige wichtige Unterschiede. Halten Sie sich an eine e-Mail-Unterhaltung, die in zwei Unterhaltungen verzweigt wurde. Beispielsweise hat jemand auf eine e-Mail geantwortet, die nicht die neueste in der Unterhaltung ist, sodass die letzten beiden e-Mails in der Unterhaltung über eindeutige Inhalte verfügen.

Outlook würde die e-Mails weiterhin in einer einzigen Unterhaltung gruppieren. Wenn Sie nur die letzte e-Mail lesen, würde das Fehlen des Kontexts der vorletzte e-Mail bedeuten, die auch eindeutige Inhalte enthält. Da e-Mail-Threading jede e-Mail in einzelne Komponenten analysiert und diese vergleicht, würde das e-Mail-Threading beide beiden letzten e-Mails als inklusiv kennzeichnen und sicherstellen, dass Sie keinen Kontext verpassen, solange Sie alle als inklusiv markierten e-Mails lesen.
