---
title: Erkennen von Quasiduplikaten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e1a9ffe264925911f475732ffd98a43fa533e458
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071302"
---
# <a name="near-duplicate-detection"></a>Erkennen von Quasiduplikaten

Betrachten Sie eine Reihe von Dokumenten, die überprüft werden sollen, in denen eine Teilmenge auf derselben Vorlage basiert und meist die gleiche Standardsprache mit einigen Unterschieden. Wenn ein Prüfer diese Teilmenge identifizieren konnte, überprüfen Sie eine von Ihnen gründlich, und überprüfen Sie die Unterschiede für den Rest, würden Sie keine eindeutigen Informationen verpasst haben, wobei nur ein Bruchteil der Zeit, die Sie zum Lesen aller Dokument Deckung zur Deckung genommen hätte. In der Nähe von doppelten Erkennung Gruppen werden Text ähnliche Dokumente zusammengefasst, die Ihnen dabei helfen, den Überprüfungsprozess effizienter zu gestalten.

## <a name="how-does-it-work"></a>Wie funktioniert das?

Wenn die Erkennung in der Nähe von Duplikaten ausgeführt wird, analysiert das System jedes Dokument mit Text. Anschließend vergleicht es jedes Dokument gegeneinander, um zu bestimmen, ob seine Ähnlichkeit größer als der festgelegte Schwellenwert ist. Wenn dies der Fall ist, werden die Dokumente zusammen gruppiert. Nachdem alle Dokumente verglichen und gruppiert wurden, wird ein Dokument aus jeder Gruppe als "Pivot" gekennzeichnet. Wenn Sie Ihre Dokumente überprüfen, können Sie zuerst einen Pivot überprüfen und die anderen Dokumente in derselben nahe doppelten Gruppe überprüfen, wobei Sie sich auf den Unterschied zwischen dem Pivot und dem Dokument konzentrieren, das sich in der Überprüfung befindet.
