---
title: Top-Domain-Nachrichtenflussstatus Einblicke im Nachrichtenfluss-Dashboard
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie mithilfe des Nachrichtenflussstatus "Top Domain" im Nachrichtenfluss-Dashboard im Security & Compliance Center Nachrichtenflussprobleme im Zusammenhang mit MX-Einträgen in Ihren e-Mail-Domänen behandeln.
ms.openlocfilehash: 6366e3aee0ab50096f1396776397c80fabc8aaf2
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577756"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Top-Domain-Nachrichtenflussstatus Einblicke im Security & Compliance Center

Der **Nachrichtenflussstatus "Top Domain"** im [Nachrichten](mail-flow-insights-v2.md) Fluss-Dashboard im Security & Compliance Center gibt Ihnen den aktuellen Status für die Domänen Ihrer Organisation im Hinblick auf den Nachrichtenfluss. Diese Einblicke helfen Ihnen bei der Identifizierung und Problembehandlung von Domänen, die sich auf Probleme mit dem ***e-Mail-Fluss auswirken*** (beispielsweise kann keine externe e-Mail empfangen werden), vor allem Domänen Ablauf oder Domänen mit falschen MX-Einträgen.

![Top Domain Flow Status widget im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-top-domain-mail-flow-status-widget.png)

Wenn Sie im Widget auf **Details anzeigen** klicken, wird ein Flyout für **Domänenstatus** angezeigt, in dem Sie weitere Informationen zum Status der einzelnen Domänen erhalten:

- **Domäne**
- **Vorheriger MX-Eintrag**
- **Aktueller MX-Eintrag**
- **E-Mail-Empfangsstatus**
- **Domänenstatus**: ein grünes Häkchen gibt an, dass der aktuelle MX-Eintrag (zu dem Zeitpunkt, zu dem Sie auf das Widget geklickt haben) dem Wert entspricht, den wir im Datensatz haben, und dass die Domäne in den letzten zwei Stunden e-Mails empfangen hat.

  Ein rotes X gibt an, dass der MX-Eintrag geändert wurde und dass die Domäne während der letzten 6 Stunden keine e-Mails erhalten hat. Dies deutet wahrscheinlich darauf hin, dass Ihre Domäne abgelaufen ist oder dass der MX-Eintrag falsch aktualisiert wurde. Erkundigen Sie sich bei Ihrer Domänenregistrierungsstelle oder Ihrem DNS-Hostingdienst, ob die Domäne abgelaufen ist oder ob der MX-Eintrag der Domäne falsch ist.

Sie können auf **mehr anzeigen** klicken, um dieselben Informationen für weitere Domänen anzuzeigen.

![Detail-Flyout im Nachrichtenflussstatus der oberen Domäne Insight](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a>Verwandte Themen

Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
