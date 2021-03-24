---
title: Verwalten von Microsoft Defender ATP-Vorfällen
description: Verwalten von Vorfällen durch Zuweisen, Aktualisieren des Status oder Festlegen der Klassifizierung.
keywords: Vorfälle, verwalten, zuweisen, Status, Klassifizierung, echte Warnung, falsche Warnung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 412938e506895aaabfa0796cb1d46ea892876435
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062152"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a>Verwalten von Microsoft Defender for Endpoint-Vorfällen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Die Verwaltung von Vorfällen ist ein wichtiger Bestandteil jedes Cybersicherheitsvorgangs. Sie können Vorfälle verwalten, indem Sie einen Vorfall in der **Incidents-Warteschlange** oder im **Bereich Incidents Management auswählen.** 


Wenn Sie einen Vorfall aus  der **Incidents-Warteschlange auswählen,** wird der Bereich "Vorfallverwaltung" geöffnet, auf dem Sie die Vorfallseite für Details öffnen können.


![Abbildung des Bereichs "Verwaltung von Vorfällen"](images/atp-incidents-mgt-pane-updated.png)

Sie können Vorfälle sich selbst zuweisen, den Status und die Klassifizierung ändern, sie umbenennen oder kommentieren, um den Fortschritt nachzuverfolgen.

> [!TIP]
> Für eine zusätzliche Sichtbarkeit auf einen Blick werden Vorfallnamen automatisch basierend auf Warnungsattributen wie der Anzahl betroffener Endpunkte, betroffener Benutzer, Erkennungsquellen oder Kategorien generiert. Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.
>
> Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet wurden.*
>
> Vorfälle, die vor dem Rollout der automatischen Benennung von Vorfällen vorhanden waren, behalten ihre Namen bei.
>


![Abbildung der Detailseite für Vorfälle](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a>Zuweisen von Vorfällen
Wenn ein Vorfall noch nicht zugewiesen wurde, können Sie **zuweisen** auswählen, um den Vorfall sich selbst zuzuordnen. Dies setzt voraus, dass nicht nur der Vorfall, sondern auch alle ihm zugeordneten Alerts in Ihrem Besitz sind.

## <a name="set-status-and-classification"></a>Festlegen des Status und der Klassifizierung
### <a name="incident-status"></a>Status des Vorfalls
Sie können Ereignisse kategorisieren (z.B. als **aktive** oder **aufgelöste**), indem Sie deren Status ändern, während ihre Untersuchung voranschreitet. Auf diese Weise können Sie organisieren und verwalten, wie Ihr Team auf Vorfälle reagiert.

Beispielsweise kann Ihr SoC-Analyst die dringenden **Aktiven** Vorfälle für den Tag überprüfen und sie sich selbst zur Untersuchung zuweisen.

Alternativ kann Ihr SoC-Analyst den Vorfall als **Aufgelöst** festlegen, wenn der Vorfall behoben wurde. 

### <a name="classification"></a>Klassifizierung
Sie können festlegen, dass keine Klassifizierung festgelegt wird, oder Sie können angeben, ob ein Vorfall wahr oder falsch ist. Auf diese Weise kann das Team Muster erkennen und von ihnen lernen.

### <a name="add-comments"></a>Kommentare hinzufügen
Sie können Kommentare hinzufügen und Historien-Ereignisse zu einem Vorfall anzeigen, um die vorherigen vorgenommenen Änderungen anzuzeigen.

Immer wenn eine Änderung an einem Alert vorgenommen oder ein Kommentar zu einem Alert hinterlassen wird, wird dies im Abschnitt Kommentare und Verlauf aufgezeichnet.

Hinzugefügte Kommentare werden sofort in diesem Bereich angezeigt.



## <a name="related-topics"></a>Verwandte Themen
- [Warteschlange für Vorfälle](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Anzeigen und Organisieren der Incidents-Warteschlange](view-incidents-queue.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
