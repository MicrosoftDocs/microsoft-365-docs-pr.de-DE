---
title: Übersicht über den Status des Nachrichtenflusses der obersten Domäne im Dashboard für den Nachrichtenfluss
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren erfahren, wie Sie die Informationen zum Statusstatus der Nachrichtenflussstatus der Obersten Domäne im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um Probleme mit dem Nachrichtenfluss im Zusammenhang mit ihren MX-Einträgen zu behandeln.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 850e72fa0ad7a3f41450a1d0a2c02dd3df4a0cb5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206971"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Informationen zum Status des Nachrichtenflusses der obersten Domäne im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Die **Übersicht über den** Status des Nachrichtenflusses der obersten Domäne im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) gibt Ihnen den aktuellen Nachrichtenflussstatus für Ihre Organisation. [](mail-flow-insights-v2.md)

Diese Einblicke helfen Ihnen bei der Identifizierung und Problembehandlung von Domänen, bei deren ***Nachrichtenfluss Probleme auftreten.*** Beispielsweise kann die Domäne keine externen E-Mails empfangen, da die Domäne abgelaufen ist oder die Domäne über einen falschen MX-Eintrag verfügt.

![Widget "Top Domain Flow Status" im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-top-domain-mail-flow-status-widget.png)

Wenn Sie im **Widget** auf Details anzeigen klicken, wird ein **Flyout** für den Domänenstatus angezeigt, das Ihnen weitere Details zum Status jeder Domäne zeigt:

- **Domäne**
- **Vorheriger MX-Eintrag**
- **Aktueller MX-Eintrag**
- **E-Mail-Empfangsstatus**
- **Domänenstatus:** Ein grünes Häkchen gibt an, dass der aktuelle MX-Eintrag (zu dem Zeitpunkt, zu dem Sie auf das Widget geklickt haben) dem Wert entspricht, den wir auf dem Datensatz haben, und die Domäne hat in den letzten zwei Stunden E-Mails empfangen.

  Ein rotes X gibt an, dass der MX-Eintrag geändert wurde und die Domäne in den letzten 6 Stunden keine E-Mails erhalten hat. Dies bedeutet wahrscheinlich, dass Ihre Domäne abgelaufen ist oder dass der MX-Eintrag falsch aktualisiert wurde. Überprüfen Sie bei Ihrer Domänenregistrierungsstelle oder ihrem DNS-Hostingdienst, ob die Domäne abgelaufen ist oder ob der MX-Eintrag der Domäne falsch ist.

Sie können auf **Weitere Informationen anzeigen klicken,** um die gleichen Informationen für weitere Domänen zu erhalten.

![Details flyout in der Statusanzeige für den Nachrichtenfluss der obersten Domäne](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).
