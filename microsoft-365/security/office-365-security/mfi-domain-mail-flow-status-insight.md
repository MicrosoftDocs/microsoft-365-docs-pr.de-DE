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
description: Administratoren können erfahren, wie Sie mithilfe des Nachrichtenflussstatus "Top Domain" im Nachrichtenfluss-Dashboard im Security & Compliance Center Nachrichtenflussprobleme im Zusammenhang mit MX-Einträgen in Ihren e-Mail-Domänen behandeln.
ms.openlocfilehash: d4abc311e96df87894d5f059328f1a16a00190b8
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877508"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Top-Domain-Nachrichtenflussstatus Einblicke im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Der **Nachrichtenflussstatus "Top Domain"** im [Nachrichten](mail-flow-insights-v2.md) Fluss-Dashboard im [Security & Compliance Center](https://protection.office.com) gibt Ihnen den aktuellen Status für die Domänen Ihrer Organisation im Hinblick auf den Nachrichtenfluss. Diese Einblicke helfen Ihnen bei der Identifizierung und Problembehandlung von Domänen, bei denen der * *_e-Mail-Fluss Auswirkungen_* auf _ Probleme auftritt (beispielsweise externe e-Mails können nicht empfangen werden), insbesondere Domänen ablaufungen oder Domänen mit falschen MX-Einträgen.

![Top Domain Flow Status widget im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-top-domain-mail-flow-status-widget.png)

Wenn Sie auf _ *Details anzeigen* * im Widget klicken, wird ein Flyout für **Domänenstatus** angezeigt, in dem Sie weitere Informationen zum Status der einzelnen Domänen erhalten:

- **Domäne**
- **Vorheriger MX-Eintrag**
- **Aktueller MX-Eintrag**
- **E-Mail-Empfangsstatus**
- **Domänenstatus** : ein grünes Häkchen gibt an, dass der aktuelle MX-Eintrag (zu dem Zeitpunkt, zu dem Sie auf das Widget geklickt haben) dem Wert entspricht, den wir im Datensatz haben, und dass die Domäne in den letzten zwei Stunden e-Mails empfangen hat.

  Ein rotes X gibt an, dass der MX-Eintrag geändert wurde und dass die Domäne während der letzten 6 Stunden keine e-Mails erhalten hat. Dies deutet wahrscheinlich darauf hin, dass Ihre Domäne abgelaufen ist oder dass der MX-Eintrag falsch aktualisiert wurde. Erkundigen Sie sich bei Ihrer Domänenregistrierungsstelle oder Ihrem DNS-Hostingdienst, ob die Domäne abgelaufen ist oder ob der MX-Eintrag der Domäne falsch ist.

Sie können auf **mehr anzeigen** klicken, um dieselben Informationen für weitere Domänen anzuzeigen.

![Detail-Flyout im Nachrichtenflussstatus der oberen Domäne Insight](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a>Verwandte Themen

Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
