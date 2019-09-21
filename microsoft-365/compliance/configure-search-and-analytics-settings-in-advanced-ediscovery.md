---
title: Konfigurieren der Such- und Analyseeinstellungen
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
ms.openlocfilehash: 5aa83f4f736c239b1cdfe940f27cfaa4b981ff64
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081020"
---
# <a name="configure-search-and-analytics-settings"></a>Konfigurieren der Such- und Analyseeinstellungen


## <a name="near-duplicates-and-email-threading"></a>Nahe Duplikate und e-Mail-Threading

In diesem Abschnitt können Sie Parameter für die doppelte Erkennung, in der Nähe der doppelten Erkennung und beim e-Mail-Threading festlegen.

- Aktivieren/deaktivieren: doppelte Erkennung, nahezu doppelte Erkennung und e-Mail-Threading als Teil des Analyse Flusses einschließen, falls aktiviert. Da Sie sich übereinander aufbauen, müssen Sie alle aktivieren oder deaktivieren.

- Schwellenwert: Wenn sich die Ähnlichkeits Ebene zweier Dokumente über dem Schwellenwert befindet, werden Sie in derselben nahe doppelten Gruppe platziert.

- Duplikate standardmäßig ausblenden: Wenn diese Einstellung aktiviert ist, wird in der Überprüfungsgruppe standardmäßig ein Filter zum Ausblenden von doppelten Dokumenten angewendet. Der Filter kann bei Bedarf manuell in der Überprüfungsgruppe entfernt werden.

- Minimale/maximale Anzahl von Wörtern: nahe Duplikate und e-Mail-Threading werden nur für Dokumente ausgeführt, die mindestens die minimale Anzahl von Wörtern und höchstens die maximale Anzahl von Wörtern aufweisen.
Weitere Informationen finden Sie [in der Nähe der doppelten Erkennung](near-duplicates.md) und des [e-Mail-Threadings](email-threading.md).

## <a name="themes"></a>Designs

In diesem Abschnitt können Sie Parameter für Designs festlegen.

- Aktivieren/deaktivieren: einbeziehen von Designs beim Clustering als Teil des Analyse Flusses, falls aktiviert.
- Anpassen der maximalen Anzahl von Designs dynamisch dynamisch: in bestimmten Fällen gibt es nicht genügend Dokumente, um die gewünschte Anzahl von Designs zu erstellen. Wenn diese Einstellung aktiviert ist, wird nicht versucht, die gewünschte maximale Anzahl von Designs zu erzwingen, sondern das System passt die maximale Anzahl von Designs dynamisch an.
- Maximale Anzahl von Designs: gewünschte Anzahl von Designs
- Zahlen in Designs einbeziehen: Wenn diese Option aktiviert ist, werden beim Generieren von Designs Zahlen in enthalten.  

## <a name="optical-character-recognition-ocr"></a>Optische Zeichenerkennung (OCR)

Wenn diese Einstellung aktiviert ist, wird die OCR für Bilder ausgeführt, die in Überprüfungs Sätzen aufgenommen werden, damit Sie durchsuchbar werden können.

## <a name="ignore-text"></a>Text ignorieren

Es gibt Fälle, in denen bestimmte Texte die Qualität von Analysen vermindern, wie lange Haftungsausschlüsse, die zu bestimmten e-Mails hinzugefügt werden, unabhängig vom Inhalt der e-Mail. Wenn Sie solche Fälle kennen, können Sie diesen Text aus Analysen ausschließen, indem Sie den Text angeben (Regex wird unterstützt) und welche Module für den Text ausgeschlossen werden sollen.