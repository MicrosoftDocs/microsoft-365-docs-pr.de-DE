---
title: Designs
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
ms.openlocfilehash: b26b031b767f23504294880f4424be5042350c71
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082549"
---
# <a name="themes"></a>Designs
Wie schreibt eine Person ein Dokument? Sie beginnen im Allgemeinen mit einem oder mehreren Ideen, die Sie im Dokument vermitteln möchten, und verfassen sich mit Wörtern, die mit den Ideen übereinstimmen. Je häufiger eine Idee ist, desto häufiger sind die Wörter, die mit dieser Idee verwandt sind, eher. Dies informiert darüber, wie Personen Dokumente auch nutzen; Das wichtigste beim Lesen eines Dokuments sind die Ideen, die das Dokument zu vermitteln versucht, und welche Ideen angezeigt werden und welche Beziehungen zwischen den Ideen bestehen.

Dies kann erweitert werden, um zu erfahren, wie eine Person eine Reihe von Dokumenten verwenden möchte. Sie möchten sehen, welche Ideen in den Sets vorhanden sind und welche Dokumente über diese Ideen sprechen. Wenn Sie ein bestimmtes Dokument finden, das interessant ist, möchten Sie auch Dokumente sehen, in denen ähnliche Ideen erörtert werden.

Designs-Modul versucht zu imitieren, wie Menschen Grund zu Dokumenten, durch die Analyse der "Designs", die in einer Überprüfung festgelegt und Zuweisen von Dokumenten. Designs geht einen Schritt weiter und identifiziert pro Dokument das "dominante Design"; dh das Design, das am häufigsten angezeigt wird.

## <a name="how-does-themes-work"></a>Wie funktioniert Designs?
Designs analysiert Dokumente mit Text in einer Überprüfungsgruppe, um allgemeine Designs zu analysieren, die in den Dokumenten angezeigt werden. Anschließend werden diese Designs den Dokumenten zugewiesen, in denen Sie angezeigt werden. Sie beschriftet außerdem jeweils Wörter, die in den Dokumenten verwendet werden, die für das Design repräsentativ sind. Da es sich bei einem Dokument um mehr als einen Betreff handeln kann, sind dem Dokument in vielen Fällen mehr als ein Design zugeordnet. Das Design, das in einem Dokument am deutlichsten erscheint, wird als dominierendes Design festgelegt.