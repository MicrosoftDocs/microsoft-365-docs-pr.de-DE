---
title: Einschränkungen für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: Erfahren Sie mehr über die maximale Anzahl von Richtlinien und Elementen pro Richtlinie für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien.
ms.openlocfilehash: 92647911cfc3435c2d88ce5caa0624a34467a60f
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908101"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>Einschränkungen für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Wenn Sie [Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien](retention.md#retention-policies-and-retention-labels) verwenden, um Daten für Ihre Organisation automatisch zu speichern oder zu löschen, müssen Sie einige maximale Werte beachten.

## <a name="maximum-number-of-policies-per-tenant"></a>Maximale Anzahl von Richtlinien pro Mandant

Ein einzelner Mandant kann maximal 10.000 Richtlinien (beliebige Konfiguration) besitzen. Diese maximale Anzahl umfasst die verschiedenen Richtlinien für die Aufbewahrung und andere Richtlinien für Compliance, beispielsweise DLP-Richtlinien, Informationsbarrieren, eDiscovery-Aufbewahrungen und Vertraulichkeitsbezeichnungen.

Innerhalb dieses Grenzwertes von 10 000 Richtlinien gibt es ebenfalls einige Grenzwerte hinsichtlich der maximalen Anzahl von Richtlinien für die Aufbewahrung pro Workload:

- Exchange (beliebige Konfiguration): 1.800
- SharePoint oder OneDrive: (alle Websites automatisch enthalten): 13
- SharePoint oder OneDrive (bestimmte Speicherorte eingeschlossen oder ausgeschlossen): 2.600

Obwohl Aufbewahrungsrichtlinien für Microsoft Teams und Yammer Postfächer zum Speichern von Daten für Aufbewahrungszwecke verwenden, schließt die maximale Anzahl von Richtlinien für Exchange Online die Aufbewahrungsrichtlinien für Teams und Yammer aus.

## <a name="maximum-number-of-items-per-policy"></a>Höchstzahl der Einträge pro Richtlinie

Wenn Sie die optionale Konfiguration verwenden, um Ihre Aufbewahrungseinstellungen auf bestimmte Benutzer, bestimmte Microsoft 365-Gruppen oder bestimmte Websites auszudehnen, gibt es einige Einschränkungen pro Richtlinie, die zu beachten sind: 

Maximale Anzahl von Elementen pro Aufbewahrungsrichtlinie:

- Exchange-Postfächer: 1.000
- Microsoft 365-Gruppen: 1.000
- Teams Kanalnachrichten: 1.000
- Teams-Chats: 1.000
- Nachrichten in der Yammer-Community: 1.000
- Benutzernachrichten in Yammer: 1.000
- SharePoint-Websites: 100
- OneDrive-Konten: 100

Skype for Business muss für bestimmte Benutzer angelegt werden und die maximal unterstützte Anzahl pro Richtlinie beträgt 1.000.

Da diese Grenzwerte pro Richtlinie gelten, können Sie bei der Verwendung spezifischer Ein- oder Ausschlüsse, die dazu führen, dass diese Werte überschritten werden, zusätzliche Richtlinien mit denselben Aufbewahrungseinstellungen erstellen. [Beispielszenarios und Lösungen](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers), die aus diesem Grund mehrere Aufbewahrungsrichtlinien verwenden, finden Sie im nächsten Abschnitt.

Mehrere Aufbewahrungsrichtlinien führen jedoch zu erhöhtem Verwaltungsaufwand. Prüfen Sie also immer sehr genau, ob Sie Ein- und Ausschlüsse benötigen. Denken Sie daran, dass die Standardkonfiguration, die für den gesamten Standort gilt, nicht diesen Einschränkungen unterliegt. Und diese Konfigurationswahl könnte eine bessere Lösung sein, als mehrere Richtlinien zu erstellen und zu verwalten.

> [!TIP]
> Wenn Sie mehrere Richtlinien für dieses Szenario erstellen und verwalten müssen, erwägen Sie die Verwendung der [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) für eine effizientere Konfiguration.

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a>Beispiele für die Verwendung mehrerer Richtlinien zur Vermeidung einer Überschreitung der maximalen Werte

Die folgenden Beispiele bieten ein paar Entwurfslösungen für Fälle, in denen Sie nicht einfach den Ort für eine Aufbewahrungsrichtlinie angeben können, sondern die im vorherigen Abschnitt dokumentierte maximale Anzahl von Elementen berücksichtigen müssen.

Exchange-Beispiel:

- **Voraussetzung**: In einer Organisation, die mehr als 40.000 Benutzerpostfächer hat, müssen die E-Mails der meisten Benutzer für 7 Jahre aufbewahrt werden, aber für eine Untermenge identifizierter Benutzer (425) müssen die E-Mails nur 5 Jahre aufbewahrt werden.

- **Lösung**: Erstellen Sie eine Aufbewahrungsrichtlinie für Exchange-E-Mail mit einem Aufbewahrungszeitraum von 7 Jahren, und schließen Sie die Untermenge der Benutzer aus. Erstellen Sie dann eine zweite Aufbewahrungsrichtlinie für Exchange-E-Mail mit einem Aufbewahrungszeitraum von 5 Jahren, und schließen Sie die Untermenge der Benutzer ein. 
    
    In beiden Fällen liegt die Anzahl der ein- und ausgeschlossenen Benutzer unter der maximalen Anzahl angegebener Postfächer für eine einzelne Richtlinie, und die Untermenge der Benutzer muss explizit aus der ersten Richtlinie ausgeschlossen werden, weil sie einen längeren [Aufbewahrungszeitraum](retention.md#the-principles-of-retention-or-what-takes-precedence) als die zweite Richtlinie hat. Wäre für die Untermenge von Benutzern eine Aufbewahrungsrichtlinie mit längerem Aufbewahrungszeitraum erforderlich, müssten Sie sie nicht aus der ersten Richtlinie ausschließen.
     
    Bei dieser Lösung wird, wenn ein neuer Benutzer der Organisation beitritt, dessen Postfach automatisch in die erste Richtlinie für 7 Jahre aufgenommen, was keine Auswirkungen auf die maximale Anzahl unterstützter Benutzer hat. Neue Benutzer, für die ein Aufbewahrungszeitraum von 5 Jahren erforderlich ist, erhöhen jedoch die Ein- und Ausschlussanzahl, deren Grenzwert bei 1.000 erreicht würde.

SharePoint-Beispiel:

- **Voraussetzung**: Eine Organisation hat mehrere Tausend SharePoint-Sites, aber nur 2.000 Sites erfordern einen Aufbewahrungszeitraum von 10 Jahren, und 8.000 Sites erfordern einen Aufbewahrungszeitraum von 4 Jahren.

- **Lösung**: Erstellen Sie 20 Aufbewahrungsrichtlinien für SharePoint mit einem Aufbewahrungszeitraum von 10 Jahren, die 100 spezifische Sites enthalten, und erstellen Sie 80 Aufbewahrungsrichtlinien für SharePoint mit einem Aufbewahrungszeitraum von 4 Jahren, die 100 spezifische Sites enthalten.
    
    Da Sie nicht alle SharePoint-Sites aufbewahren müssen, müssen Sie Aufbewahrungsrichtlinien erstellen, die die spezifischen Sites angeben. Da eine Aufbewahrungsrichtlinie nicht mehr als 100 angegebene Sites unterstützt, müssen Sie mehrere Richtlinien für die zwei Aufbewahrungszeiträume erstellen. Diese Aufbewahrungszeiträume belegen die maximale Anzahl eingeschlossener Sites, weshalb die nächste neue Site, die aufbewahrt werden muss, eine neue Aufbewahrungsrichtlinie erfordern würde, unabhängig vom Aufbewahrungszeitraum.

## <a name="maximum-number-of-items-for-disposition"></a>Maximale Anzahl von Artikeln zur Löschung

Bei der [Löschung von Inhalten](disposition.md) sind einige Limits zu beachten:

- 1.000.000 ausstehende Elemente zur Löschung pro Phase für jede Aufbewahrungsbezeichnung

- Löschungsnachweis für bis zu sieben Jahre nach der Löschung des Elements, mit einer Höchstgrenze von 1.000.000 Elementen pro Aufbewahrungsbezeichnung für diesen Zeitraum. 
    
Wenn Sie für Elemente, die als Datensätze gekennzeichnet sind, einen Verfügungsnachweis benötigen, der diesen Grenzwert von 1000000 überschreitet, wenden Sie sich an den [Microsoft-Support](../business-video/get-help-support.md).
