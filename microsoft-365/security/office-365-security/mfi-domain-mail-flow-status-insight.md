---
title: Top-Domain-Nachrichtenflussstatus Einblicke im Nachrichtenfluss-Dashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie mithilfe des Nachrichtenflussstatus "Top Domain" im Nachrichtenfluss-Dashboard im Security & Compliance Center Probleme bei der Nachrichtenübermittlung im Zusammenhang mit Ihren MX-Einträgen beheben.
ms.openlocfilehash: 0d750ab4dbe5875796118086fae1d9119dc486f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920584"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Top-Domain-Nachrichtenflussstatus Einblicke im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Der **Nachrichtenflussstatus "Top Domain"** im [Nachrichten](mail-flow-insights-v2.md) Fluss-Dashboard im [Security & Compliance Center](https://protection.office.com) gibt Ihnen den aktuellen Nachrichtenflussstatus für Ihre Organisation.

Diese Einblicke helfen Ihnen bei der Identifizierung und Problembehandlung von Domänen, bei denen * *_e-Mail-Fluss_* _ Probleme auftreten. Beispielsweise kann die Domäne keine externen e-Mails empfangen, weil die Domäne abgelaufen ist oder die Domäne einen falschen MX-Eintrag aufweist.

![Top Domain Flow Status widget im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-top-domain-mail-flow-status-widget.png)

Wenn Sie auf _ *Details anzeigen* * im Widget klicken, wird ein Flyout für **Domänenstatus** angezeigt, in dem Sie weitere Informationen zum Status der einzelnen Domänen erhalten:

- **Domäne**
- **Vorheriger MX-Eintrag**
- **Aktueller MX-Eintrag**
- **E-Mail-Empfangsstatus**
- **Domänenstatus** : ein grünes Häkchen gibt an, dass der aktuelle MX-Eintrag (zu dem Zeitpunkt, zu dem Sie auf das Widget geklickt haben) dem Wert entspricht, den wir im Eintrag haben, und dass die Domäne in den letzten zwei Stunden e-Mails empfangen hat.

  Ein rotes X gibt an, dass der MX-Eintrag geändert wurde und die Domäne in den letzten 6 Stunden keine e-Mails erhalten hat. Dies deutet wahrscheinlich darauf hin, dass Ihre Domäne abgelaufen ist oder dass der MX-Eintrag falsch aktualisiert wurde. Erkundigen Sie sich bei Ihrer Domänenregistrierungsstelle oder Ihrem DNS-Hostingdienst, ob die Domäne abgelaufen ist oder ob der MX-Eintrag der Domäne falsch ist.

Sie können auf **mehr anzeigen** klicken, um dieselben Informationen für weitere Domänen anzuzeigen.

![Detail-Flyout im Nachrichtenflussstatus der oberen Domäne Insight](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Weitere Informationen

Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
