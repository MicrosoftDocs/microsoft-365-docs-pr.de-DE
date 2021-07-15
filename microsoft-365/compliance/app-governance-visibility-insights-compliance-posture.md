---
title: Bestimmen Ihrer App-Compliance-Ausrichtung
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
description: Bestimmen Sie Ihre App-Compliance-Ausrichtung.
ms.openlocfilehash: 3d7cac319c31bac40a3aad2f6b9a4c16303f6a20
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420124"
---
# <a name="determine-your-app-compliance-posture"></a>Bestimmen Ihrer App-Compliance-Ausrichtung

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Mit der Microsoft-App-Governance können Sie die Compliance-Ausrichtung der Drittanbieter-Apps und deren Zugriff auf Daten in Ihrem Microsoft 365 Mandanten schnell über die Übersichtsseite der App-Governance im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/appgovernance) beurteilen.

![Die Übersichtsseite der App-Governance im Microsoft 365 Compliance Center](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> Ihr Anmeldekonto muss über eine [dieser Rollen](app-governance-get-started.md#administrator-roles) verfügen, um App-Governance-Daten anzeigen zu können.
>

Von dieser Seite aus können Sie Folgendes sehen:

- Für OAuth-fähige Apps, welche die Microsoft Graph-API verwenden:

  - Wie viele befinden sich in Ihrem Mandanten?
  - Wie viele sind möglicherweise überprivilegiert?
  - Wie viele haben hohe Berechtigungen?

  Anhand dieser Informationen können Sie das Risiko für Ihre Organisation ermitteln, das überprivilegierte Apps und solche mit hohen Berechtigungen darstellen.

- Für Benachrichtigungen:

  - Wie viele aktive Benachrichtigungen Ihr Mandant hat
  - Wie viele basieren auf Erkennungen der App-Governance (**Bedrohungsbenachrichtigungen**)
  - Wie viele basieren auf App-Richtlinien, die Sie eingerichtet haben (**Richtlinienbenachrichtigungen**)
  - Die letzten zehn 10 Benachrichtigungen

  Anhand dieser Informationen können Sie bestimmen, wie schnell Benachrichtigungen erstellt werden, und wie hoch die relative Anzahl der erkannten und richtlinienbasierten Alarme ist.

- Für Daten- und Ressourcenzugriff:

  - Die API-Datenzugriffe der Anwendung in den letzten 90 Tagen
  - Die Nutzung der wichtigsten Ressourcen in den letzten 90 Tagen

  Anhand dieser Informationen können Sie ermitteln, ob es anomale Spitzen beim Zugriff auf die Daten in Ihrem Microsoft 365-Mandanten gibt.
