---
title: Verwalten von Microsoft Defender für Endpunkt-Vorfällen
description: Verwalten Sie Vorfälle, indem Sie sie zuweisen, ihren Status aktualisieren oder die Klassifizierung festlegen.
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
ms.openlocfilehash: c86b53abf54788740c8c78cb0ecf9251b10ea8f7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842338"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a>Verwalten von Microsoft Defender für Endpunkt-Vorfällen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Die Verwaltung von Vorfällen ist ein wichtiger Bestandteil jedes Cybersicherheitsvorgangs. Sie können Vorfälle verwalten, indem Sie einen Vorfall in der **Vorfallwarteschlange** oder im **Bereich "Vorfallverwaltung"** auswählen. 


Wenn Sie einen Vorfall aus der **Vorfallwarteschlange** auswählen, wird der **Bereich "Vorfallverwaltung"** angezeigt, auf dem Sie die Vorfallseite für Details öffnen können.


![Abbildung des Bereichs "Vorfallverwaltung"](images/atp-incidents-mgt-pane-updated.png)

Sie können Sich selbst Vorfälle zuweisen, den Status und die Klassifizierung ändern, umbenennen oder kommentieren, um ihren Fortschritt nachzuverfolgen.

> [!TIP]
> Für eine zusätzliche Sichtbarkeit auf einen Blick werden Vorfallnamen automatisch basierend auf Warnungsattributen generiert, z. B. der Anzahl der betroffenen Endpunkte, betroffenen Benutzer, Erkennungsquellen oder Kategorien. Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.
>
> Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet werden.*
>
> Vorfälle, die vor dem Rollout der automatischen Benennung von Vorfällen vorhanden waren, behalten ihre Namen.
>


![Abbildung der Vorfalldetailseite](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a>Zuweisen von Vorfällen
Wenn ein Vorfall noch nicht zugewiesen wurde, können Sie **"Mir zuweisen"** auswählen, um den Vorfall sich selbst zuzuweisen. Dies setzt voraus, dass nicht nur der Vorfall, sondern auch alle ihm zugeordneten Alerts in Ihrem Besitz sind.

## <a name="set-status-and-classification"></a>Festlegen des Status und der Klassifizierung
### <a name="incident-status"></a>Status des Vorfalls
Sie können Ereignisse kategorisieren (z.B. als **aktive** oder **aufgelöste**), indem Sie deren Status ändern, während ihre Untersuchung voranschreitet. Auf diese Weise können Sie organisieren und verwalten, wie Ihr Team auf Vorfälle reagiert.

Beispielsweise kann Ihr SoC-Analyst die dringenden **aktiven** Vorfälle für den Tag überprüfen und sie sich selbst zur Untersuchung zuweisen.

Alternativ kann Ihr SoC-Analyst den Vorfall als **behoben** festlegen, wenn der Vorfall behoben wurde. 

### <a name="classification"></a>Klassifizierung
Sie können festlegen, dass keine Klassifizierung festgelegt wird, oder Sie können angeben, ob ein Vorfall wahr oder falsch ist. Auf diese Weise kann das Team Muster erkennen und von ihnen lernen.

### <a name="add-comments"></a>Kommentare hinzufügen
Sie können Kommentare hinzufügen und Historien-Ereignisse zu einem Vorfall anzeigen, um die vorherigen vorgenommenen Änderungen anzuzeigen.

Immer wenn eine Änderung an einem Alert vorgenommen oder ein Kommentar zu einem Alert hinterlassen wird, wird dies im Abschnitt Kommentare und Verlauf aufgezeichnet.

Hinzugefügte Kommentare werden sofort in diesem Bereich angezeigt.



## <a name="related-topics"></a>Verwandte Themen
- [Vorfallswarteschlange](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Anzeigen und Organisieren der Vorfallswarteschlange](view-incidents-queue.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
