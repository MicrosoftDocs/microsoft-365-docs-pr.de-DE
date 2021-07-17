---
title: Überprüfen der Architekturanforderungen und Schlüsselkonzepte von Microsoft Defender für Endpunkt
description: Das technische Diagramm für Microsoft Defender für Endpunkt in Microsoft 365 Defender hilft Ihnen, die Identität in Microsoft 365 zu verstehen, bevor Sie Ihre Testumgebung oder Pilotumgebung erstellen.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4df1ac2ca5fdfaa88ec2d08c85112f52da26b873
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458130"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a>Überprüfen der Architekturanforderungen und Schlüsselkonzepte von Microsoft Defender für Endpunkt

**Gilt für:** Microsoft 365 Defender

Dieser Artikel führt Sie beim Einrichten der Evaluierung für die Microsoft Defender für Endpunkt-Umgebung.

Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-endpoint-overview.md)

Bevor Sie Microsoft Defender für Endpunkt aktivieren, stellen Sie sicher, dass Sie die Architektur verstehen und die Anforderungen erfüllen können.

## <a name="understand-the-architecture"></a>Grundlegendes zur Architektur

Das folgende Diagramm veranschaulicht die Architektur und Integration von Microsoft Defender für Endpunkt. 

![Schritte zum Hinzufügen von Microsoft Defender für Office zur Defender-Evaluierungsumgebung](../../media/defender/m365-defender-endpoint-architecture.png)

In der folgenden Tabelle wird die Abbildung beschrieben.

Call-out | Beschreibung
:---|:---|
1 | Geräte werden über eines der unterstützten Verwaltungstools an boarded. 
2 | On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.
3 | Verwaltete Geräte sind in Azure Active Directory eingebunden und/oder registriert.
4  | In die Domäne eingebundene Windows 10 Geräte werden mit Azure Active Directory mithilfe von Azure Active Directory Verbinden synchronisiert.
5  | Warnungen, Untersuchungen und Antworten von Microsoft Defender für Endpunkt werden in Microsoft 365 Defender verwaltet.

## <a name="understand-key-concepts"></a>Grundlegendes zu den wichtigsten Konzepten

In der folgenden Tabelle sind die wichtigsten Konzepte aufgeführt, die beim Auswerten, Konfigurieren und Bereitstellen von Microsoft Defender für Endpunkt zu verstehen sind: 

Konzept | Beschreibung | Weitere Informationen
:---|:---|:---|
Verwaltungsportal | Microsoft 365 Defender Portal zur Überwachung und Unterstützung bei der Reaktion auf Warnungen über potenzielle fortgeschrittene dauerhafte Bedrohungsaktivitäten oder Datenschutzverletzungen. | [Übersicht über das Microsoft Defender für Endpunkt-Portal](/defender-endpoint/portal-overview)
Attack Surface Reduction | Reduzieren Sie Ihre Angriffsflächen, indem Sie die Stellen minimieren, an denen Ihre Organisation anfällig für Cyberbedrohungen und Angriffe ist. | [Übersicht der Verringerung der Angriffsfläche](/defender-endpoint/overview-attack-surface-reduction)
Endpunkterkennung und -antwort | Endpunkterkennungs- und -reaktionsfunktionen bieten erweiterte Angriffserkennungen, die nahezu in Echtzeit und umsetzbar sind. | [Übersicht über EDR Funktionen](/defender-endpoint/overview-endpoint-detection-response)
Blockieren und Eindämmen von Verhaltensweisen | Funktionen zum Blockieren und Eindämmen von Verhaltensweisen können dazu beitragen, Bedrohungen basierend auf ihren Verhaltensweisen und Prozessstrukturen zu erkennen und zu stoppen, selbst wenn die Bedrohung mit der Ausführung begonnen hat. | [Verhaltensbasiertes Blockieren und Eindämmen](/defender-endpoint/behavioral-blocking-containment)
Automatisierte Untersuchung und Reaktion | Die automatisierte Untersuchung verwendet verschiedene Überprüfungsalgorithmen basierend auf Prozessen, die von Sicherheitsanalysten verwendet werden und darauf ausgelegt sind, Warnungen zu untersuchen und sofortige Maßnahmen zur Behebung von Verstößen zu ergreifen. | [Verwenden automatisierter Untersuchungen zum Untersuchen und Beheben von Bedrohungen](/defender-endpoint/automated-investigations)
Erweiterte Suche | Die erweiterte Suche ist ein abfragebasiertes Tool zur Bedrohungssuche, mit dem Sie rohe Daten von bis zu 30 Tagen untersuchen können, damit Sie Ereignisse in Ihrem Netzwerk proaktiv untersuchen können, um Bedrohungsindikatoren und Entitäten zu finden. | [Übersicht über die erweiterte Suche](/defender-endpoint/advanced-hunting-overview)
Bedrohungsanalyse | Bei der Bedrohungsanalyse handelt es sich um eine Reihe von Berichten von erfahrenen Microsoft-Sicherheitsexperten, die die relevantesten Bedrohungen abdecken. | [Nachverfolgen und Reagieren auf neue Bedrohungen mit Bedrohungsanalysen](/defender-endpoint/threat-analytics)


Ausführlichere Informationen zu den in Microsoft Defender für Endpunkt enthaltenen Funktionen finden Sie unter [Was ist Microsoft Defender für Endpunkt.](/defender-endpoint/microsoft-defender-endpoint)

## <a name="siem-integration"></a>SIEM-Integration

Sie können Microsoft Defender für Endpunkt in Azure Sentinel integrieren, um Sicherheitsereignisse in Ihrer Organisation umfassender zu analysieren und Playbooks für eine effektive und sofortige Reaktion zu erstellen. 

Microsoft Defender für Endpunkt kann auch in andere SIEM-Lösungen (Security Information and Event Management) integriert werden. Weitere Informationen finden Sie unter [Aktivieren der SIEM-Integration in Microsoft Defender für Endpunkt.](/defender-endpoint/enable-siem-integration)


## <a name="next-steps"></a>Nächste Schritte
[Aktivieren der Auswertung](eval-defender-endpoint-enable-eval.md)

Kehren Sie zur Übersicht für ["Auswerten von Microsoft Defender für Endpunkt"](eval-defender-endpoint-overview.md) zurück.

Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)