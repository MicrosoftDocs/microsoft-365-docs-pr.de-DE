---
title: Beheben eines möglichen Einblicks in den E-Mail-Loop
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Administratoren erfahren, wie Sie den Einblick in mögliche E-Mail-Schleifen im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um E-Mail-Schleifen in ihrer Organisation zu identifizieren und zu beheben.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206344"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Beheben möglicher Einblicke in die E-Mail-Schleife im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

E-Mail-Schleifen sind schlecht, da:

- Sie verschwenden Systemressourcen.
- Sie nutzen das E-Mail-Volumenkontingent Ihrer Organisation.
- Sie senden verwirrende Unzustellbarkeitsberichte (auch als Unzustellbarkeitsberichte oder Unzustellbarkeitsnachrichten bezeichnet) an die ursprünglichen Nachrichtensender.

Der Einblick in mögliche  **E-Mail-Schleifen** [](mail-flow-insights-v2.md) beheben im Bereich Empfohlen für Sie des Nachrichtenflussdashboards im Security & Compliance Center benachrichtigt Sie, wenn eine E-Mail-Schleife in Ihrer Organisation erkannt wird. [](https://protection.office.com)

Diese Einsicht wird erst angezeigt, nachdem die Bedingung erkannt wurde (wenn Sie keine E-Mail-Schleifen haben, wird der Einblick nicht angezeigt).

![Beheben des Einblicks zu langsamen Nachrichtenflussregeln im Bereich Empfohlen für Sie im Dashboard für den Nachrichtenfluss](../../media/mfi-fix-possible-mail-loop.png)

Wenn Sie auf **Details im** Widget anzeigen klicken, wird ein Flyout mit weiteren Informationen angezeigt:

- **Domäne**
- **Anzahl der Nachrichten**: Sie können auf [](message-trace-scc.md) Beispielnachrichten **anzeigen** klicken, um die Ergebnisse der Nachrichtenverfolgung für ein Beispiel der Nachrichten zu sehen, die von der Schleife betroffen waren.
- **Domänentyp**" Beispiel: Autoritative oder nicht autorisierende.
- **MX-Eintrag:** Die Werte host (**Mail server**) und **Priority** des MX-Eintrags für die Domäne.
- **Loop reason** und **How to fix**: Wir identifizieren die gängigsten Szenarien für E-Mail-Schleifen und bieten empfohlene Aktionen zum Beheben der Schleife.

![Details-Flyout, das angezeigt wird, nachdem Sie auf Details in der Möglichen E-Mail-Schleife korrigieren geklickt haben](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).
