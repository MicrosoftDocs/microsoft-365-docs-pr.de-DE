---
title: Einschränkungen für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Erfahren Sie mehr über die maximale Anzahl von Richtlinien und Elementen pro Richtlinie für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien.
ms.openlocfilehash: 547c6396fa9bfcba6dbd271f09a7ea59f9acf170
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261586"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>Einschränkungen für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Wenn Sie [Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien](retention.md#retention-policies-and-retention-labels) verwenden, um Daten für Ihre Organisation automatisch zu speichern oder zu löschen, müssen Sie einige maximale Werte beachten.

## <a name="maximum-number-of-policies-per-tenant"></a>Maximale Anzahl von Richtlinien pro Mandant

Ein einzelner Mandant kann maximal 10.000 Richtlinien (beliebige Konfiguration) besitzen. Diese maximale Anzahl umfasst die verschiedenen Richtlinien für die Aufbewahrung und andere Richtlinien für Compliance wie z. B. DLP-Richtlinien.

Maximale Anzahl von Richtlinien für die Aufbewahrung pro Workload:

- Exchange Online (beliebige Konfiguration): 1.800
- SharePoint oder OneDrive: (alle Websites automatisch enthalten): 13
- SharePoint oder OneDrive (bestimmte Speicherorte eingeschlossen oder ausgeschlossen): 2.600

## <a name="maximum-number-of-items-per-policy"></a>Höchstzahl der Einträge pro Richtlinie

Wenn Sie die optionale Konfiguration verwenden, um Ihre Aufbewahrungseinstellungen auf bestimmte Benutzer, bestimmte Microsoft 365-Gruppen oder bestimmte Websites auszudehnen, gibt es einige Einschränkungen pro Richtlinie, die zu beachten sind: 

Maximale Anzahl von Elementen pro Aufbewahrungsrichtlinie:

  - 1.000 Postfächer (Benutzerpostfächer oder Gruppenpostfächer)
  - 1.000 Microsoft 365-Gruppen
  - 1.000 Benutzer für private Teams-Chats
  - 100 Websites (OneDrive oder SharePoint)

Da diese Grenzwerte pro Richtlinie gelten, können Sie bei der Verwendung spezifischer Ein- oder Ausschlüsse, die dazu führen, dass diese Werte überschritten werden, zusätzliche Richtlinien mit denselben Aufbewahrungseinstellungen erstellen. [Beispielszenarios und Lösungen](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers), die aus diesem Grund mehrere Aufbewahrungsrichtlinien verwenden, finden Sie im nächsten Abschnitt.

Mehrere Aufbewahrungsrichtlinien führen jedoch zu erhöhtem Verwaltungsaufwand. Prüfen Sie also immer sehr genau, ob Sie Ein- und Ausschlüsse benötigen. Denken Sie daran, dass die Standardkonfiguration, die für den gesamten Standort gilt, nicht diesen Einschränkungen unterliegt. Und diese Konfigurationswahl könnte eine bessere Lösung sein, als mehrere Richtlinien zu erstellen und zu verwalten.

> [!TIP]
> Wenn Sie mehrere Richtlinien für dieses Szenario erstellen und verwalten müssen, erwägen Sie die Verwendung der [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) für eine effizientere Konfiguration.

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a>Beispiele für die Verwendung mehrerer Richtlinien zur Vermeidung einer Überschreitung der maximalen Werte

Die folgenden Beispiele bieten ein paar Entwurfslösungen für Fälle, in denen Sie nicht einfach den Ort für eine Aufbewahrungsrichtlinie angeben können, sondern die im vorherigen Abschnitt dokumentierte maximale Anzahl von Elementen berücksichtigen müssen.

Exchange-Beispiel:

- **Voraussetzung**: In einer Organisation, die mehr als 40.000 Benutzerpostfächer hat, müssen die E-Mails der meisten Benutzer für 7 Jahre aufbewahrt werden, aber für eine Untermenge identifizierter Benutzer (425) müssen die E-Mails nur 5 Jahre aufbewahrt werden.

- **Lösung**: Erstellen Sie eine Aufbewahrungsrichtlinie für Exchange-E-Mail mit einem Aufbewahrungszeitraum von 7 Jahren, und schließen Sie die Untermenge der Benutzer aus. Erstellen Sie dann eine zweite Aufbewahrungsrichtlinie für Exchange-E-Mail mit einem Aufbewahrungszeitraum von 5 Jahren, und schließen Sie die Untermenge der Benutzer ein. 
    
    In beiden Fällen liegt die Anzahl der ein- und ausgeschlossenen Benutzer unter der maximalen Anzahl angegebener Postfächer für eine einzelne Richtlinie, und die Untermenge der Benutzer muss explizit aus der ersten Richtlinie ausgeschlossen werden, weil sie einen längeren [Aufbewahrungszeitraum](retention.md#the-principles-of-retention-or-what-takes-precedence) als die zweite Richtlinie hat. Wäre für die Untermenge von Benutzern eine Aufbewahrungsrichtlinie mit längerem Aufbewahrungszeitraum erforderlich, müssten Sie sie nicht aus der ersten Richtlinie ausschließen.
     
    Bei dieser Lösung wird, wenn ein neuer Benutzer der Organisation beitritt, dessen Postfach automatisch in die erste Richtlinie für 7 Jahre aufgenommen, was keine Auswirkungen auf die maximale Anzahl unterstützter Benutzer hat. Neue Benutzer, für die ein Aufbewahrungszeitraum von 5 Jahren erforderlich ist, erhöhen jedoch die Ein- und Ausschlussanzahl, deren Grenzwert bei 1.000 erreicht würde.

SharePoint-Beispiel:

- **Voraussetzung**: Eine Organisation hat mehrere Tausend SharePoint-Sites, aber nur 2.000 Sites erfordern einen Aufbewahrungszeitraum von 10 Jahren, und 8.000 Sites erfordern einen Aufbewahrungszeitraum von 4 Jahren.

- **Lösung**: Erstellen Sie 20 Aufbewahrungsrichtlinien für SharePoint mit einem Aufbewahrungszeitraum von 10 Jahren, die 100 spezifische Sites enthalten, und erstellen Sie 80 Aufbewahrungsrichtlinien für SharePoint mit einem Aufbewahrungszeitraum von 4 Jahren, die 100 spezifische Sites enthalten.
    
    Da Sie nicht alle SharePoint-Sites aufbewahren müssen, müssen Sie Aufbewahrungsrichtlinien erstellen, die die spezifischen Sites angeben. Da eine Aufbewahrungsrichtlinie nicht mehr als 100 angegebene Sites unterstützt, müssen Sie mehrere Richtlinien für die zwei Aufbewahrungszeiträume erstellen. Diese Aufbewahrungszeiträume belegen die maximale Anzahl eingeschlossener Sites, weshalb die nächste neue Site, die aufbewahrt werden muss, eine neue Aufbewahrungsrichtlinie erfordern würde, unabhängig vom Aufbewahrungszeitraum.

