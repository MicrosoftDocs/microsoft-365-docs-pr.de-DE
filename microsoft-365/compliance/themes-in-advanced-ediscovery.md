---
title: Designs - eDiscovery
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
description: Verwenden Sie Designs in Advanced eDiscovery, um Überprüfungssätze zu organisieren, indem Sie das dominante Design in jedem Dokument finden.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285531"
---
# <a name="themes-in-advanced-ediscovery"></a>Designs in Advanced eDiscovery

Wie schreibt eine Person ein Dokument? Sie beginnen in der Regel mit einem oder mehreren Ideen, die sie im Dokument vermitteln möchten, und verfassen mithilfe von Wörtern, die an den Ideen ausgerichtet sind. Um so verbreiteter eine Idee ist, werden die Wörter, die mit dieser Idee in Zusammenhang stehen, in der Regel häufiger verwendet. Dies informiert darüber, wie Auch Personen Dokumente verwenden. Wichtig beim Lesen eines Dokuments sind die Ideen, die das Dokument vermitteln soll, welche Ideen wo angezeigt werden und was die Beziehungen zwischen den Ideen sind.

Dies kann auf die Art und Weise erweitert werden, wie eine Person eine Reihe von Dokumenten nutzen möchte. Sie möchten sehen, welche Ideen in den Sätzen vorhanden sind und welche Dokumente über diese Ideen sprechen. Wenn sie ein bestimmtes Dokument von Interesse finden, möchten sie auch Dokumente sehen können, in denen ähnliche Ideen behandelt werden.

Die Themes-Funktionalität in Advanced eDiscovery versucht nachzuahmen, wie Menschen  über Dokumente nachdenklich sind, indem sie die Designs analysiert, die in einem Überprüfungssatz behandelt werden, und Dokumente im Überprüfungssatz ein Design zuweisen. Im Advanced eDiscovery Designs einen Schritt weiter und identifiziert das *dominante Design* in jedem Dokument. Das dominante Design ist das Design, das am häufigsten in einem Dokument angezeigt wird.

## <a name="how-does-themes-work"></a>Wie funktioniert Designs?

Die Funktion „Designs“ untersucht Dokumente mit Text in einem Prüfdateisatz auf gemeinsame Designs, die in allen Dokumenten des Prüfdateisatzes enthalten sind. Advanced eDiscovery weist diese Designs den Dokumenten zu, in denen Sie enthalten sind. Außerdem wird jedes Design mit den in den Dokumenten verwendeten Wörtern gekennzeichnet, die für das Design repräsentativ sind. Da ein Dokument verschiedene Typen von Designs enthalten kann, weist Advanced eDiscovery Dokumenten häufig mehrere Designs zu. Das Design, das in einem Dokument am stärksten vertreten ist, wird als dominantes Design festgelegt.
