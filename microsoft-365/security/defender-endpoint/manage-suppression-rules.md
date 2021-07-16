---
title: Verwalten von Microsoft Defender für Endpunkt-Unterdrückungsregeln
description: Möglicherweise müssen Sie verhindern, dass Warnungen mithilfe von Unterdrückungsregeln im Portal angezeigt werden. Erfahren Sie, wie Sie Ihre Unterdrückungsregeln in Microsoft Defender für Endpunkt verwalten.
keywords: Verwalten von Unterdrückung, Regeln, Regelname, Bereich, Aktion, Warnungen, aktivieren, deaktivieren
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 74b89d86b770cb47a0855b45d457ea8ce5fb9802
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454757"
---
# <a name="manage-suppression-rules"></a>Verwalten von Unterdrückungsregeln

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Es kann Szenarien geben, in denen Sie verhindern müssen, dass Warnungen im Portal angezeigt werden. Sie können Unterdrückungsregeln für bestimmte Warnungen erstellen, die bekanntermaßen unauffällig sind, z. B. bekannte Tools oder Prozesse in Ihrer Organisation. Weitere Informationen zum Unterdrücken von Warnungen finden Sie unter ["Warnungen unterdrücken".](manage-alerts.md)

Sie können eine Liste aller Unterdrückungsregeln anzeigen und an einem zentralen Ort verwalten. Sie können eine Regel zur Unterdrückung von Warnungen auch aktivieren oder deaktivieren.


1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Warnungsunterdrückung**  >  **für Endpunktregeln**  >  aus. Die Liste der Unterdrückungsregeln, die Benutzer in Ihrer Organisation erstellt haben, wird angezeigt.

2. Wählen Sie eine Regel aus, indem Sie auf das Kontrollkästchen neben dem Regelnamen klicken.

3. Klicken Sie **auf "Regel aktivieren",** **"Regel bearbeiten"** oder **"Regel löschen".** Wenn Sie Änderungen an einer Regel vornehmen, können Sie Benachrichtigungen freigeben, die sie bereits unterdrückt hat, unabhängig davon, ob diese Warnungen den neuen Kriterien entsprechen. 


## <a name="view-details-of-a-suppression-rule"></a>Anzeigen von Details einer Unterdrückungsregel

1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Warnungsunterdrückung**  >  **für Endpunktregeln**  >  aus. Die Liste der Unterdrückungsregeln, die Benutzer in Ihrer Organisation erstellt haben, wird angezeigt.

2. Klicken Sie auf einen Regelnamen. Details der Regel werden angezeigt. Sie sehen die Regeldetails wie Status, Bereich, Aktion, Anzahl der übereinstimmenden Warnungen, erstellt von und Datum, an dem die Regel erstellt wurde. Sie können auch zugeordnete Warnungen und die Regelbedingungen anzeigen.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Warnungen](manage-alerts.md)
