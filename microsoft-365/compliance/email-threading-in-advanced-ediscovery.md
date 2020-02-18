---
title: E-Mail-Threading
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
ms.assetid: ''
description: ''
ms.openlocfilehash: ea40acc3c83d5083a68473223f849a9bebbe98ce
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074742"
---
# <a name="email-threading"></a>E-Mail-Threading

Ziehen Sie eine e-Mail-Unterhaltung in Frage, die schon eine Weile vorgeht. In den meisten Fällen enthält die letzte e-Mail im Thread die Inhalte aller vorherigen e-Mails. Wenn Sie die letzte e-Mail überprüfen, erhalten Sie einen vollständigen Kontext der Unterhaltung, die im Thread aufgetreten ist. E-Mail-Threading identifiziert solche e-Mails, sodass Bearbeiter einen Bruchteil der gesammelten Dokumente überprüfen können, ohne dass ein Kontext verloren geht.

## <a name="what-does-email-threading-do"></a>Was bewirkt das e-Mail-Threading?

E-Mail-Threading analysiert jede e-Mail und desconstructs Sie an einzelne Nachrichten; jede e-Mail ist eine Kette einzelner Nachrichten. Anschließend werden alle e-Mails in der Überprüfungsgruppe analysiert, um festzustellen, ob eine e-Mail über eindeutige Inhalte verfügt oder ob die Kette vollständig in einer anderen e-Mail enthalten ist. Am Ende werden e-Mails in vier Kategorien unterteilt:

- **Inclusive**: die letzte Nachricht in der e-Mail weist eindeutige Inhalte auf, und die e-Mail enthält alle Anlagen, die in anderen e-Mails enthalten waren, in denen der Inhalt vollständig in dieser e-Mail enthalten ist.


- **Inclusive minus**: die letzte Nachricht in der e-Mail hat eindeutige Inhalte, aber die e-Mail enthält nicht einige der Anlagen, die in anderen e-Mails enthalten waren, in denen der Inhalt vollständig in dieser e-Mail enthalten ist.

- **Inklusive Kopie**: eine exakte Kopie einer inclusive/inklusive minus-e-Mail

- **None**: der Inhalt dieser e-Mail-Nachricht ist vollständig in mindestens einer e-Mail enthalten, die als inclusive/inclusive minus gekennzeichnet ist.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>Wie unterscheidet er sich von den Unterhaltungen in Outlook?
Dies klingt auf einen Blick ähnlich wie Konversations Gruppierungen in Outlook. Es gibt jedoch einige wichtige Unterschiede. Halten Sie sich an eine e-Mail-Unterhaltung, die in zwei Unterhaltungen verzweigt wurde. Beispielsweise hat jemand auf eine e-Mail geantwortet, die nicht die neueste in der Unterhaltung ist, sodass die letzten beiden e-Mails in der Unterhaltung über eindeutige Inhalte verfügen.

Outlook würde die e-Mails weiterhin in einer einzigen Unterhaltung gruppieren. Wenn Sie nur die letzte e-Mail lesen, würde das Fehlen des Kontexts der vorletzte e-Mail bedeuten, die auch eindeutige Inhalte enthält. Da das e-Mail-Threading jede e-Mail in einzelne Komponenten analysiert und diese vergleicht, würde das e-Mail-Threading beide letzten e-Mails als inklusivzeichen markieren, um sicherzustellen, dass Sie keinen Kontext verpassen, solange Sie alle als inklusiv markierten e-Mails lesen.
