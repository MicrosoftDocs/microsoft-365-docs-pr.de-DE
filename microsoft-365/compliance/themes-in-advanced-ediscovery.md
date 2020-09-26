---
title: Designs – eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Verwenden Sie Designs in Advanced eDiscovery, um Überprüfungs Sätze zu organisieren, indem Sie das dominante Design in jedem Dokument finden.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285531"
---
# <a name="themes-in-advanced-ediscovery"></a>Designs in Advanced eDiscovery

Wie schreibt eine Person ein Dokument? Sie beginnen im Allgemeinen mit einem oder mehreren Ideen, die Sie im Dokument vermitteln möchten, und verfassen sich mit Wörtern, die mit den Ideen übereinstimmen. Je häufiger eine Idee ist, desto häufiger sind die Wörter, die mit dieser Idee verwandt sind, eher. Dies informiert darüber, wie auch Benutzer Dokumente konsumieren. Das wichtigste beim Lesen eines Dokuments ist die Idee, die das Dokument zu vermitteln versucht, welche Ideen angezeigt werden und wie die Beziehungen zwischen den Ideen aussehen.

Dies kann erweitert werden, um zu erfahren, wie eine Person eine Reihe von Dokumenten verwenden möchte. Sie möchten sehen, welche Ideen in den Sets vorhanden sind und welche Dokumente über diese Ideen sprechen. Wenn Sie ein bestimmtes Dokument finden, das interessant ist, möchten Sie auch Dokumente sehen, in denen ähnliche Ideen erörtert werden.

Die Designs-Funktionalität in Advanced eDiscovery versucht zu imitieren, wie Menschen Grund zu Dokumenten sind, indem Sie die in einer Überprüfungsgruppe besprochenen *Designs* analysieren und einem Dokument in der Überprüfungsgruppe ein Design zuweisen. In Advanced eDiscovery geht Designs einen Schritt weiter und identifiziert das *dominante Design* in jedem Dokument. Das dominante Design ist diejenige, die am häufigsten in einem Dokument angezeigt wird.

## <a name="how-does-themes-work"></a>Wie funktioniert Designs?

Die Funktion „Designs“ untersucht Dokumente mit Text in einem Prüfdateisatz auf gemeinsame Designs, die in allen Dokumenten des Prüfdateisatzes enthalten sind. Advanced eDiscovery weist diese Designs den Dokumenten zu, in denen Sie enthalten sind. Außerdem wird jedes Design mit den in den Dokumenten verwendeten Wörtern gekennzeichnet, die für das Design repräsentativ sind. Da ein Dokument verschiedene Typen von Designs enthalten kann, weist Advanced eDiscovery Dokumenten häufig mehrere Designs zu. Das Design, das in einem Dokument am stärksten vertreten ist, wird als dominantes Design festgelegt.
