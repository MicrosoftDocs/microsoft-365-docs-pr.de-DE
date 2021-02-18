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
description: Administratoren können erfahren, wie Sie den Einblick in mögliche E-Mail-Schleifen im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um E-Mail-Schleifen in ihrer Organisation zu identifizieren und zu beheben.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7fde0041dfb9901cb0a327eafec78d98a40b4cb9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290561"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Beheben möglicher Einblicke in die E-Mail-Schleife im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

E-Mail-Schleifen sind ungültig, weil:

- Sie verschwenden Systemressourcen.
- Sie nutzen das E-Mail-Volumenkontingent Ihrer Organisation.
- Sie senden verwirrende Unzustellbarkeitsberichte (auch NDRs oder Unzustellbarkeitsnachrichten bezeichnet) an die ursprünglichen Absender von Nachrichten.

The **Fix possible mail loop** insight in the Recommended for **you** area of the Mail [flow dashboard](mail-flow-insights-v2.md) in the Security & [Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.

Dieser Einblick wird erst angezeigt, nachdem die Bedingung erkannt wurde (wenn Sie keine E-Mail-Schleifen haben, wird der Einblick nicht angezeigt).

![Beheben der Einblicke in langsame Nachrichtenflussregeln im Bereich "Empfohlen für Sie" des Dashboards für den Nachrichtenfluss](../../media/mfi-fix-possible-mail-loop.png)

Wenn Sie im **Widget auf Details** anzeigen klicken, wird ein Flyout mit weiteren Informationen angezeigt:

- **Domäne**
- **Anzahl der Nachrichten:**  Sie können auf [](message-trace-scc.md) "Beispielmeldungen anzeigen" klicken, um die Ergebnisse der Nachrichtenverfolgung für eine Stichprobe der Nachrichten zu sehen, die von der Schleife betroffen waren.
- **Domänentyp**" Beispielsweise autorisierend oder nicht autorisierend.
- **MX-Eintrag:** Der Host (**E-Mail-Server**) und **die Prioritätswerte** des MX-Eintrags für die Domäne.
- **Loop reason** and **How to fix:** We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.

![Details-Flyout, das angezeigt wird, nachdem Sie auf "Details anzeigen" im Einblick "Mögliche E-Mail-Schleife korrigieren" geklickt haben](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)
