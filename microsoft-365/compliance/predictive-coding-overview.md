---
title: Vorhersagecodierungsmodul für Advanced eDiscovery (Vorschau)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Das neue Vorhersagecodierungsmodul in Advanced eDiscovery verwendet maschinelles Lernen, um Dokumente in einem Überprüfungssatz zu analysieren, der voraussagend festgelegt ist, welche Dokumente für Ihren Fall oder Ihre Untersuchung relevant sind.
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382960"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a>Vorhersagecodierungsmodul für Advanced eDiscovery (Vorschau)

Mithilfe des neuen Vorhersagecodierungsmoduls in Advanced eDiscovery Können Sie ein Modell erstellen und erstellen, um die Überprüfung von Dokumenten beginnend mit den relevantesten Dokumenten zu priorisieren. Zu Beginn können Sie ein Modell erstellen, bis zu 50 Dokumente beschriften und dann Dokumente nach Modellvorhersageergebnissen filtern, um relevante nicht relevante Dokumente zu überprüfen.

Hier finden Sie eine kurze Übersicht über den Workflow:

1. Öffnen Sie das Vorhersagecodierungsmodul in einem Überprüfungssatz.

   ![Klicken Sie in einer Rezension auf die Dropdownliste Analysieren, um zum Vorhersagecodierungsmodul zu wechseln.](..\media\PredictiveCoding1.png)

2. Klicken Sie auf der Seite **Vorhersagecodierungsmodelle** auf **Neues Modell,** um ein neues Vorhersagecodierungsmodell zu erstellen.

   ![Erstellen eines neuen Modells](..\media\PredictiveCoding2.png)

3. Beschriften Sie mindestens 50 Dokumente **als relevant** oder **Nicht relevant.** Diese Bezeichnung wird zum Trainieren des Systems verwendet.

   ![Bezeichnung von Dokumenten als relevant oder nicht relevant für die Ausbildung des Systems](..\media\PredictiveCoding3.png)

4. Wenden Sie **den Vorhersagebewertungsfilter** für Ihr Modell auf den Überprüfungssatz an. Gehen Sie hierfür folgendermaßen vor:

   1. Klicken Sie im Überprüfungssatz auf **Filter**.
   2. Erweitern Sie **auf** der Seite Filterflyout den Abschnitt **Analytics/ML,** und aktivieren Sie dann das Kontrollkästchen Vorhersageergebnis für das Modell, das Sie anwenden möchten. 
   3. Geben Sie **im Filter Prognoseergebnis** eine Vorhersageergebnis an. Der Filter zeigt die Dokumente im Überprüfungssatz an, die mit der Vorhersagebewertung übereinstimmen.

      ![Angeben eines Vorhersageergebniss zum Filtern von Dokumenten](..\media\PredictiveCoding4.png)

5. Überwachen Sie die Leistung, den Status und die Stabilität Ihres Modells.

   ![Überwachen der Leistung, des Status und der Stabilität Ihres Modells](..\media\PredictiveCoding5.png)
