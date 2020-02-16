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
description: Mit Smarttags können Sie die Lernfunktionen für Computer anwenden, wenn Sie Inhalte in einem erweiterten eDiscovery-Fall überprüfen. Verwenden Sie smarttaggruppen, um die Ergebnisse von Computer Lern-Erkennungs Modellen anzuzeigen, beispielsweise das Anwalts-Client-Berechtigungsmodell.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081082"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>Einrichten von Smarttags in Advanced eDiscovery

Das maschinelle Lernen (ml) Funktionen in Advanced eDiscovery kann Ihnen helfen, den Entscheidungsprozess effizienter zu gestalten, wenn Sie Fall Dokumente in einem Überprüfungs Satzes überprüfen. Smarttags sind eine Möglichkeit, die ml-Funktionen an die Stelle zu bringen, an der die Entscheidungen aufgezeichnet werden: beim Markieren von Dokumenten während der Überprüfung. Wenn Sie eine smarttaggruppe erstellen, werden die Entscheidungen, die das Ergebnis des ml-Modells sind, das Sie der smarttaggruppe zugeordnet haben, Inline mit den Tags in der Tag-Gruppe angezeigt. Dadurch werden die Informationen zu ml-Ergebnissen Inline angezeigt, wenn Sie bestimmte Dokumente überprüfen.

## <a name="how-to-set-up-a-smart-tag-group"></a>Vorgehensweise Einrichten einer smarttaggruppe

1. Klicken Sie in einem Überprüfungs Satzes auf **Überarbeitungs Gruppe verwalten** , und klicken Sie dann auf **Tags verwalten**.

2. Klicken Sie auf **Tag-Gruppe hinzufügen** und dann auf **smarttaggruppe hinzufügen**.

3. Wählen Sie das ml-Modell aus, das Sie der Transpondergruppe zuordnen möchten.
    
   Dadurch werden eine Tag-Gruppe und *n* untergeordnete Tags erstellt, wobei *n* für die Anzahl der möglichen Ausgaben des Modells steht. Beispielsweise weist das " [Attorney-Client-Berechtigungs Erkennungs Modell](attorney-privilege-detection.md) " zwei mögliche Ausgaben auf: 

   - **Positiv** – verwenden Sie, um Dokumente zu markieren, die Inhalte für Rechtsanwälte-Clients enthalten.
   
   - **Negativ** – verwenden Sie diese, um Dokumente zu markieren, die keinen Anwalt-Client-privilegierten Inhalt enthalten.
    
    Wenn Sie dieses Modell auswählen, wird eine Transpondergruppe mit zwei untergeordneten Tags erstellt (ein untergeordnetes Tag mit dem Namen " **positive** " und das andere " **negative**") für die Überprüfungsgruppe. In diesem Beispiel entspricht jedes untergeordnete Tag einem der möglichen Ausgaben des Erkennungs Modells für das Anwalts Client-Privileg.

4. Optional können Sie die Tag-Gruppe und die untergeordneten Tags umbenennen. Beispielsweise können Sie das **positive** -Tag in " **privileged** " und das **negative** -Tag auf " **nicht privilegierte**" umbenennen.

## <a name="how-to-use-smart-tags"></a>Verwenden von Smarttags

Wenn Sie ein Dokument überprüfen, werden die Ergebnisse des Modells neben dem entsprechenden untergeordneten Tag angezeigt. Wenn Sie beispielsweise eine smarttaggruppe für die Erkennung von Anwalts Mandanten Berechtigungen haben und ein Dokument überprüfen, das potenziell privilegiert ist, wird der Grund für diese Schlussfolgerung neben dem entsprechenden Tag angezeigt. Es ist wichtig zu beachten, dass das Tag nicht automatisch auf das Dokument angewendet wird. Der Prüfer trifft die Entscheidung, wie das Dokument markiert werden soll.
