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
ms.openlocfilehash: 152f68e8fe0e7d7340d2e048bc73684bc079386f
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438024"
---
# <a name="determine-your-app-compliance-posture"></a>Bestimmen Ihrer App-Compliance-Ausrichtung

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Mit der Microsoft-App-Governance können Sie die Compliance-Ausrichtung der Drittanbieter-Apps und deren Zugriff auf Daten in Ihrem Microsoft 365 Mandanten schnell über die Übersichtsseite der App-Governance im [Microsoft 365 Compliance Center](https://aka.ms/appgovernance) beurteilen.

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

  - Gesamtanzahl der Daten, auf die Apps im Mandanten über die Graph-API im aktuellen und in den letzten drei Kalendermonaten zugegriffen haben. (Umfasst derzeit nur E-Mail- und Dateiupload- und Downloadnutzung)
  - Datennutzung im aktuellen und in den letzten drei Kalendermonaten, aufgeschlüsselt nach Ressourcentyp. (Umfasst derzeit nur E-Mail- und Dateiupload- und Downloadnutzung)

  Anhand dieser Informationen können Sie ermitteln, ob es beim Zugriff auf die Daten in Ihrem Microsoft 365-Mandanten einen ungewöhnlichen Anstieg gibt.
