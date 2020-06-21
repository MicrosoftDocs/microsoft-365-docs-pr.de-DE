---
title: Einblick in den Top-Domain-Nachrichtenflussstatus
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
description: Administratoren können sich im Nachrichtenfluss-Dashboard im Security & Compliance Center über den Nachrichtenflussstatus "Top Domain" informieren.
ms.openlocfilehash: 22b0f8cefe8baacac682550126de55dcbf880d73
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818591"
---
# <a name="top-domain-mail-flow-status-insight"></a>Einblick in den Top-Domain-Nachrichtenflussstatus

In der **oberen Domäne der Nachrichtenflussstatus** Insight erhalten Sie den aktuellen Status für die Domänen Ihrer Organisation im Hinblick auf den Nachrichtenfluss. Diese Einblicke helfen Ihnen bei der Identifizierung und Problembehandlung von Domänen, die sich auf Probleme mit dem ***e-Mail-Fluss auswirken*** (beispielsweise kann keine externe e-Mail empfangen werden), vor allem Domänen Ablauf oder Domänen mit falschen MX-Einträgen.

![Der obere Domänen Fluss Status – Einblicke im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/domain-mail-flow-status-selected.png)

Wenn Sie in der Insight auf **Details anzeigen** klicken, wird ein Flyout angezeigt, in dem Sie weitere Informationen zum Status der einzelnen Domänen erhalten.

Ein grünes Häkchen für eine Domäne gibt an, dass der aktuelle MX-Eintrag (beim Browsen in das Nachrichtenfluss-Einblicke-Dashboard) dem Wert entspricht, den wir im Datensatz haben, und dass die Domäne in den letzten zwei Stunden e-Mails empfangen hat.

Ein rotes x für eine Domäne gibt an, dass der MX-Eintrag geändert wurde und dass in den letzten 6 Stunden keine e-Mails für die Domäne empfangen wurden. Dies deutet wahrscheinlich darauf hin, dass Ihre Domäne abgelaufen ist oder dass der MX-Eintrag falsch aktualisiert wurde. Erkundigen Sie sich bei Ihrer Domänenregistrierungsstelle oder Ihrem DNS-Hostingdienst, ob die Domäne abgelaufen ist oder ob der MX-Eintrag der Domäne falsch ist.

![Das Detail-Flyout im oberen Bereich der Domänen-Flow-Status Einblicke](../../media/domain-mail-flow-status-flyout.png)

## <a name="related-topics"></a>Verwandte Themen

Weitere Informationen zu anderen e-Mail-Fluss-Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
