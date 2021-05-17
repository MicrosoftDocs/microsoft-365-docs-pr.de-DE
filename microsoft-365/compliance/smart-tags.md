---
title: Einrichten von Smarttags in Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: Mit Smarttags können Sie die Machine Learning-Funktionen beim Überprüfen von Inhalten in einem Advanced eDiscovery anwenden. Verwenden Sie Smarttaggruppen, um die Ergebnisse von Machine-Learning-Erkennungsmodellen wie dem Anwalts-Client-Berechtigungsmodell anzeigen zu können.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081082"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>Einrichten von Smarttags in Advanced eDiscovery

Maschinelles Lernen (ML)-Funktionen in Advanced eDiscovery können Ihnen helfen, den Entscheidungsprozess effizienter zu gestalten, wenn Sie Falldokumente in einem Überprüfungssatz überprüfen. Smarttags sind eine Möglichkeit, die Funktionen ML, wo die Entscheidungen aufgezeichnet werden: beim Taggen von Dokumenten während der Überprüfung. Wenn Sie eine Smarttaggruppe erstellen, werden die Entscheidungen, die das Ergebnis des ML-Modells sind, das Sie der Smarttaggruppe zugeordnet haben, in der Zeile mit den Tags in der Taggruppe angezeigt. Dies hilft ihnen, ML informationen in der Zeile zu sehen, wenn Sie bestimmte Dokumente überprüfen.

## <a name="how-to-set-up-a-smart-tag-group"></a>Einrichten einer Smarttaggruppe

1. Klicken Sie in einem Überprüfungssatz auf **Überprüfungssatz verwalten,** und klicken Sie dann **auf Tags verwalten.**

2. Klicken **Sie auf Taggruppe hinzufügen,** und wählen Sie **dann Smarttaggruppe hinzufügen aus.**

3. Wählen Sie das ML aus, das Sie der Taggruppe zuordnen möchten.
    
   Dadurch werden eine Taggruppe und *untergeordnete N-Tags* erstellt, wobei *N* die Anzahl möglicher Ausgaben des Modells ist. Das Erkennungsmodell der [Anwalts-Client-Rechte verfügt](attorney-privilege-detection.md) beispielsweise über zwei mögliche Ausgaben: 

   - **Positiv** – Verwenden Sie zum Markieren von Dokumenten, die privilegierte Inhalte des Anwaltsclients enthalten.
   
   - **Negativ** – Verwenden Sie zum Markieren von Dokumenten, die keine privilegierten Inhalte des Anwaltsclients enthalten.
    
    Wenn Sie dieses Modell auswählen, wird eine Taggruppe mit zwei untergeordneten Tags erstellt (ein untergeordnetes Tag mit dem Namen **Positive** und das andere mit dem Namen **Negative**) für den Überprüfungssatz. In diesem Beispiel entspricht jedes untergeordnete Tag einer der möglichen Ausgaben aus dem Erkennungsmodell für Anwalts-Client-Rechte.

4. Optional können Sie die Taggruppe und die untergeordneten Tags umbenennen. Beispielsweise könnten Sie das **Positive-Tag** in **Privileged** und **das Negative-Tag** in **Not privileged umbenennen.**

## <a name="how-to-use-smart-tags"></a>Verwenden von Smarttags

Beim Überprüfen eines Dokuments werden die Ergebnisse des Modells neben dem entsprechenden untergeordneten Tag angezeigt. Wenn Sie beispielsweise über eine Smarttaggruppe für die Erkennung von Anwalts-Client-Berechtigungen verfügen und ein Dokument überprüfen, das potenziell privilegierte Berechtigungen hat, wird der Grund für diese Schlussfolgerung neben dem entsprechenden Tag angezeigt. Beachten Sie, dass das Tag nicht automatisch auf das Dokument angewendet wird. Der Prüfer entscheidet über das Taggen des Dokuments.
