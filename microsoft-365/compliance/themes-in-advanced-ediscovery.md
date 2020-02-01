---
title: Designs
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
ms.openlocfilehash: 4387c5e8fc199f0f8642041473d5f28f2f9b401b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601382"
---
# <a name="themes"></a>Designs

Wie schreibt eine Person ein Dokument? Sie beginnen im Allgemeinen mit einem oder mehreren Ideen, die Sie im Dokument vermitteln möchten, und verfassen sich mit Wörtern, die mit den Ideen übereinstimmen. Je häufiger eine Idee ist, desto häufiger sind die Wörter, die mit dieser Idee verwandt sind, eher. Dies informiert darüber, wie auch Benutzer Dokumente konsumieren. Das wichtigste beim Lesen eines Dokuments ist die Idee, die das Dokument zu vermitteln versucht, welche Ideen angezeigt werden und wie die Beziehungen zwischen den Ideen aussehen.

Dies kann erweitert werden, um zu erfahren, wie eine Person eine Reihe von Dokumenten verwenden möchte. Sie möchten sehen, welche Ideen in den Sets vorhanden sind und welche Dokumente über diese Ideen sprechen. Wenn Sie ein bestimmtes Dokument finden, das interessant ist, möchten Sie auch Dokumente sehen, in denen ähnliche Ideen erörtert werden.

Die Designs-Funktionalität in Advanced eDiscovery versucht zu imitieren, wie Menschen Grund zu Dokumenten sind, indem Sie die in einer Überprüfungsgruppe besprochenen *Designs* analysieren und einem Dokument in der Überprüfungsgruppe ein Design zuweisen. In Advanced eDiscovery geht Designs einen Schritt weiter und identifiziert das *dominante Design* in jedem Dokument. Das dominante Design ist diejenige, die am häufigsten in einem Dokument angezeigt wird.

## <a name="how-does-themes-work"></a>Wie funktioniert Designs?

Die Designs-Funktion analysiert Dokumente mit Text in einem Überprüfungs Satzes, um allgemeine Designs zu analysieren, die in allen Dokumenten in der Überprüfungsgruppe angezeigt werden. Advanced eDiscovery ordnet diese Designs den Dokumenten zu, in denen Sie angezeigt werden. Außerdem werden die einzelnen Designs mit den in den Dokumenten verwendeten Wörtern versehen, die für das Design repräsentativ sind. Da ein Dokument verschiedene Arten von Gegenstand enthalten kann, weist Advanced eDiscovery häufig mehreren Designs zu Dokumenten zu. Das Design, das in einem Dokument am deutlichsten erscheint, wird als dominierendes Design festgelegt.