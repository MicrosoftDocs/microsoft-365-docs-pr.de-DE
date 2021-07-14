---
title: Erste Schritte mit App-Richtlinien
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Erste Schritte mit „Erfahren Sie mehr über App-Richtlinien“
ms.openlocfilehash: 3f80048835388e740ba64ac36d1aa19594bf7a9d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420209"
---
# <a name="get-started-with-app-policies"></a>Erste Schritte mit App-Richtlinien

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

App-Richtlinien für die Microsoft-App-Governance sind die Möglichkeit, proaktivere oder reaktivere Bedingungen zu implementieren, um Warnungen oder automatische Korrekturen für Ihre spezifischen Anforderungen an die App-Compliance in Ihrer Organisation zu erstellen.

Um die Liste der aktuellen App-Richtlinie zu anzuzeigen, wechseln Sie zur **Microsoft 365 Compliance Center > App-Schutz und -Governance > Übersicht > Richtlinien**.

![Übersichtsseite der MAPG-Richtlinien im Microsoft 365 Compliance Center](..\media\manage-app-protection-governance\mapg-cc-policies.png)

## <a name="whats-available-on-the-app-policies-dashboard"></a>Was ist im App-Richtliniendashboard verfügbar?

Angezeigt werden die Anzahl der aktiven, inaktiven und Testrichtlinien sowie die folgenden Informationen für jede Richtlinie:

- **Name der Richtlinie**
- **Status**

  - **Aktiv**: Alle Richtlinienauswertungen und -aktionen sind aktiv.
  - **Inaktiv**: Alle Richtlinienauswertungen und -aktionen sind deaktiviert.
  - **Überwachungsmodus**: Die Richtlinienauswertung befindet sich im Überwachungsmodus. Die Richtlinie ist aktiv, aber Richtlinienaktionen sind deaktiviert.

- **Schweregrad**: Schweregrad, der für alle Warnungen festgelegt ist, die ausgelöst werden, weil diese Richtlinie als „true“ ausgewertet wird, was Teil der Konfiguration der Richtlinie ist.
- **Anzahl der aktiven Warnungen**: Warnungen, die von der Richtlinie generiert werden und den Status **In Bearbeitung** oder **Neu** aufweisen.
- **Anzahl der Warnungen insgesamt**: Aktive und aufgelöste Warnungen für diese Richtlinie.
- **Datum der letzten Warnung**: Datum der letzten, aufgrund dieser Richtlinie generierten Warnung.
- **Letzte Änderung**: Datum, an dem diese Richtlinie zuletzt geändert wurde.

Die Richtlinienliste ist standardmäßig nach **Letzte Änderung** sortiert. Um die Liste nach einem anderen Attribut zu sortieren, wählen Sie den Attributnamen aus.

Wenn Sie eine Richtlinie auswählen, wird ein detaillierter Richtlinienbereich mit den folgenden zusätzlichen Details angezeigt:

- **Beschreibung**: Eine ausführlichere Erläuterung des Zwecks der Richtlinie.
- **Erstellt von**: Benutzerprinzipalname (UPN) des Kontos, das die Richtlinie erstellt hat.
- Eine Liste der aktiven Warnungen, die von dieser Richtlinie generiert wurden.

Sie können eine App-Richtlinie bearbeiten oder löschen, indem Sie im Richtliniendetailbereich **Bearbeiten** oder **Löschen** auswählen oder indem Sie die vertikalen Auslassungspunkte der Richtlinie in der Richtlinienliste auswählen.

Sie können auch folgende Aktionen ausführen:

- Eine neue Richtlinie erstellen. Sie können mit einer App-Nutzungsrichtlinie oder einer Berechtigungsrichtlinie beginnen.
- Exportieren Sie die Richtlinienliste in eine CSV-Datei. Sie können die CVS-Datei beispielsweise in Microsoft Excel öffnen, die Richtlinien nach **Schweregrad** und dann nach **Anzahl der Warnungen insgesamt** sortieren.
- Die Richtlinienliste durchsuchen.

## <a name="next-step"></a>Nächster Schritt

[Erstellen einer App-Richtlinie](app-governance-app-policies-create.md)
