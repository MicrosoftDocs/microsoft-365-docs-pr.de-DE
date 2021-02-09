---
title: Einblick in den Nachrichtenflussstatus der obersten Domäne im Dashboard für den Nachrichtenfluss
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
description: Administratoren können erfahren, wie Sie den Einblick in den Nachrichtenflussstatus der obersten Domäne im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um Probleme mit dem Nachrichtenfluss im Zusammenhang mit ihren MX-Einträgen zu behandeln.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: df0f571d29d72b23e7b2e210b61a4fb1676175aa
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150207"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Einblick in den Status des Nachrichtenflusses der obersten Domäne im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Die **Einblicke in den** Nachrichtenflussstatus der obersten Domäne im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) bieten Ihnen den aktuellen Nachrichtenflussstatus für Ihre Organisation. [](mail-flow-insights-v2.md)

Dieser Einblick hilft Ihnen bei der Identifizierung und Problembehandlung von Domänen, bei deren ***Nachrichtenfluss Probleme auftreten.*** Beispielsweise kann die Domäne keine externe E-Mail empfangen, weil die Domäne abgelaufen ist oder die Domäne über einen falschen MX-Eintrag verfügt.

![Widget für den Status der obersten Domäne im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-top-domain-mail-flow-status-widget.png)

Wenn Sie im **Widget** auf Details anzeigen klicken, wird ein **Flyout** für den Domänenstatus angezeigt, in dem Weitere Details zum Status jeder Domäne angezeigt werden:

- **Domäne**
- **Vorheriger MX-Eintrag**
- **Aktueller MX-Eintrag**
- **Status des E-Mail-Empfangs**
- **Domänenstatus:** Ein grünes Häkchen gibt an, dass der aktuelle MX-Eintrag (zum Zeitpunkt, zu dem Sie auf das Widget geklickt haben) dem Wert entspricht, den wir im Datensatz haben, und die Domäne hat in den letzten zwei Stunden E-Mails empfangen.

  Ein rotes X gibt an, dass der MX-Eintrag geändert wurde und die Domäne in den letzten 6 Stunden keine E-Mails empfangen hat. Dies weist wahrscheinlich darauf hin, dass Ihre Domäne abgelaufen ist oder dass der MX-Eintrag falsch aktualisiert wurde. Überprüfen Sie bei Ihrer Domänenregistrierungsstelle oder Ihrem DNS-Hostingdienst, ob die Domäne abgelaufen ist oder ob der MX-Eintrag der Domäne falsch ist.

Sie können auf **"Weitere Informationen anzeigen"** klicken, um die gleichen Informationen für weitere Domänen zu erhalten.

![Details-Flyout im Einblick in den E-Mail-Flussstatus der obersten Domäne](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)
