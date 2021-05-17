---
title: Nahezu doppelte Erkennung – eDiscovery
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
description: Verwenden Sie die Fast-Duplikaterkennung, um textlich ähnliche Dokumente zu gruppieren, wenn Sie Falldaten in Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286021"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a>Nahezu doppelte Erkennung in Advanced eDiscovery

Erwägen Sie eine Reihe von Dokumenten, die überprüft werden sollen, bei denen eine Teilmenge auf derselben Vorlage basiert und meist dieselbe Textbausteinesprache hat, mit einigen Unterschieden hier und da. Wenn ein Prüfer diese Teilmenge identifizieren, eine davon gründlich überprüfen und die Unterschiede für den Rest überprüfen könnte, hätten sie keine eindeutigen Informationen verpasst, während sie nur einen Bruchteil der Zeit in Sich genommen hätten, die sie zum Lesen aller Dokumente in Bezug genommen hätten. Bei der Erkennung von Quasiduplikaten werden textuell ähnliche Dokumente gruppiert, um den Überprüfungsvorgang effizienter zu gestalten.

## <a name="how-does-it-work"></a>Wie funktioniert das?

Bei Ausführung der Erkennung von Quasiduplikaten analysiert das System jedes Dokument mit Text. Anschließend werden alle Dokumente miteinander verglichen, um zu bestimmen, ob ihre Ähnlichkeit über dem Schwellenwert liegt. Ist dies der Fall, werden die Dokumente gruppiert. Nachdem alle Dokumente verglichen und gruppiert wurden, wird ein Dokument aus jeder Gruppe als „Pivot“ markiert. Wenn Sie Ihre Dokumente überprüfen, können Sie zuerst das Pivot-Dokument und anschließend die restlichen Dokumente im gleichen Quasiduplikat-Satz überprüfen und sich dabei auf den Unterschied zwischen dem Pivot und dem Dokument konzentrieren, das sich in der Überprüfung befindet.
