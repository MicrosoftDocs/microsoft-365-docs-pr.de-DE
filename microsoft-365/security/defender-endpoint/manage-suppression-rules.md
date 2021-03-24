---
title: Verwalten von Unterdrückungsregeln für Microsoft Defender for Endpoint
description: Möglicherweise müssen Sie verhindern, dass Warnungen im Portal angezeigt werden, indem Sie Unterdrückungsregeln verwenden. Erfahren Sie, wie Sie Ihre Unterdrückungsregeln in Microsoft Defender ATP verwalten.
keywords: Verwalten von Unterdrückung, Regeln, Regelname, Bereich, Aktion, Warnungen, Aktivieren, Deaktivieren
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
ms.openlocfilehash: 3b65b71cc90d8e79b5de02822a12d8a44cf6c0a6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063967"
---
# <a name="manage-suppression-rules"></a>Verwalten von Unterdrückungsregeln

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Es kann Szenarien gibt, in denen Sie das Anzeigen von Warnungen im Portal unterdrücken müssen. Sie können Unterdrückungsregeln für bestimmte Warnungen erstellen, die als harmlos bekannt sind, z. B. bekannte Tools oder Prozesse in Ihrer Organisation. Weitere Informationen zum Unterdrücken von Warnungen finden Sie unter [Suppress alerts](manage-alerts.md).

Sie können eine Liste aller Unterdrückungsregeln anzeigen und an einem ort verwalten. Sie können auch eine Warnungsunterdrückungsregel aktivieren oder deaktivieren.


1. Wählen Sie im Navigationsbereich  >  Einstellungsbenachrichtigungsunterdrückung **aus.** Die Liste der Unterdrückungsregeln, die Benutzer in Ihrer Organisation erstellt haben, wird angezeigt.

2. Wählen Sie eine Regel aus, indem Sie auf das Kontrollkästchen neben dem Regelnamen klicken.

3. Klicken **Sie auf Regel aktivieren,** Regel **bearbeiten** oder  **Regel löschen**. Wenn Sie Änderungen an einer Regel vornehmen, können Sie Warnungen veröffentlichen, die bereits unterdrückt wurden, unabhängig davon, ob diese Warnungen den neuen Kriterien entsprechen. 


## <a name="view-details-of-a-suppression-rule"></a>Anzeigen von Details einer Unterdrückungsregel

1. Wählen Sie im Navigationsbereich  >  Einstellungsbenachrichtigungsunterdrückung **aus.** Die Liste der Unterdrückungsregeln, die Benutzer in Ihrer Organisation erstellt haben, wird angezeigt.

2. Klicken Sie auf einen Regelnamen. Details der Regel werden angezeigt. Ihnen werden die Regeldetails angezeigt, z. B. Status, Bereich, Aktion, Anzahl der übereinstimmenden Warnungen, erstellt von und Datum, an dem die Regel erstellt wurde. Sie können auch zugeordnete Warnungen und die Regelbedingungen anzeigen.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Warnungen](manage-alerts.md)
