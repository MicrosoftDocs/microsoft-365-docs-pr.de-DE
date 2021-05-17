---
title: Verstehen von Bedrohungsintelligenzkonzepten in Microsoft Defender for Endpoint
description: Erstellen von benutzerdefinierten Bedrohungswarnungen für Ihre Organisation und Erlernen der Konzepte zur Bedrohungsintelligenz in Microsoft Defender for Endpoint
keywords: Bedrohungsintelligenz, Warnungsdefinitionen, Gefährdungsindikatoren, ioc
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bb82634c8c2ef11131a43e8e479bf88d5626ed03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066080"
---
# <a name="understand-threat-intelligence-concepts"></a>Grundlegendes zu Threat Intelligence-Konzepten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-threatindicator-abovefoldlink) 

Erweiterte Cybersicherheitsangriffe umfassen mehrere komplexe bösartige Ereignisse, Attribute und Kontextinformationen. Die Identifizierung und Entscheidung, welche dieser Aktivitäten als verdächtig gelten, kann eine anspruchsvolle Aufgabe sein. Ihr Wissen über bekannte Attribute und ungewöhnliche Aktivitäten, die für Ihre Branche spezifisch sind, ist von grundlegender Bedeutung, um zu wissen, wann ein beobachtetes Verhalten als verdächtig bezeichnet werden soll.

Mit Microsoft Defender for Endpoint können Sie benutzerdefinierte Bedrohungswarnungen erstellen, mit deren Hilfe Sie mögliche Angriffsaktivitäten in Ihrer Organisation nachverfolgen können. Sie können verdächtige Ereignisse kennzeichnen, um Hinweise zu verbinden und möglicherweise eine Angriffskette zu beenden. Diese benutzerdefinierten Bedrohungswarnungen werden nur in Ihrer Organisation angezeigt und kennzeichnen Ereignisse, die Sie für die Nachverfolgung festlegen.

Vor dem Erstellen von benutzerdefinierten Bedrohungswarnungen ist es wichtig, die Konzepte hinter Warnungsdefinitionen und Gefährdungsindikatoren (IoCs) und deren Beziehung zu kennen.

## <a name="alert-definitions"></a>Warnungsdefinitionen
Warnungsdefinitionen sind kontextbezogene Attribute, die gemeinsam verwendet werden können, um frühe Hinweise auf einen möglichen Cybersicherheitsangriff zu identifizieren. Diese Indikatoren sind in der Regel eine Kombination aus Aktivitäten, Merkmalen und Aktionen, die von einem Angreifer ergriffen werden, um das Ziel eines Angriffs erfolgreich zu erreichen. Die Überwachung dieser Kombination von Attributen ist entscheidend, um einen Blick auf Angriffe zu gewinnen und möglicherweise die Ereigniskette zu stören, bevor das Ziel eines Angreifers erreicht wird.

## <a name="indicators-of-compromise-ioc"></a>Indikatoren für Kompromisse (IOC)
IOCs sind individuell bekannte bösartige Ereignisse, die darauf hinweisen, dass ein Netzwerk oder Gerät bereits verletzt wurde. Im Gegensatz zu Warnungsdefinitionen werden diese Indikatoren als Nachweis für eine Verletzung betrachtet. Sie werden häufig gesehen, nachdem ein Angriff bereits ausgeführt wurde und das Ziel erreicht wurde, z. B. exfiltration. Die Nachverfolgung von IOCs ist auch bei forensischen Untersuchungen wichtig. Obwohl dies möglicherweise nicht die Möglichkeit bietet, mit einer Angriffskette zu intervenieren, kann das Sammeln dieser Indikatoren hilfreich sein, um eine bessere Abwehr für mögliche zukünftige Angriffe zu erstellen.

## <a name="relationship-between-alert-definitions-and-iocs"></a>Beziehung zwischen Warnungsdefinitionen und IOCs
Im Kontext von Microsoft Defender for Endpoint sind Warnungsdefinitionen Container für IOCs und definieren die Warnung, einschließlich der Metadaten, die im Falle einer bestimmten IOC-Übereinstimmung ausgelöst werden. Verschiedene Metadaten werden als Teil der Warnungsdefinitionen bereitgestellt. Metadaten wie der Warnungsdefinitionsname des Angriffs, der Schweregrad und die Beschreibung werden zusammen mit anderen Optionen bereitgestellt.

Jedes IOC definiert die konkrete Erkennungslogik basierend auf ihrem Typ und Wert sowie ihrer Aktion, die bestimmt, wie sie abgestimmt wird. Sie ist an eine bestimmte Warnungsdefinition gebunden, die definiert, wie eine Erkennung als Warnung in der Microsoft Defender for Endpoint-Konsole angezeigt wird.

Hier ein Beispiel für ein IOC:
- Typ: Sha1
- Wert: 92cfceb39d57d914ed8b14d0e37643de0797ae56
- Aktion: Gleich

IoCs haben eine n:1-Beziehung mit Warnungsdefinitionen, so dass eine Warnungsdefinition viele IOCs enthalten kann, die ihr entsprechen.

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

Thema | Beschreibung
:---|:---
[Ziehen von Erkennungen an Ihre SIEM-Tools](configure-siem.md)| Erfahren Sie mehr über verschiedene Methoden zum Ziehen von Erkennungen.
[Aktivieren der SIEM-Integration in Microsoft Defender for Endpoint](enable-siem-integration.md)| Erfahren Sie mehr über das Aktivieren des SIEM-Integrationsfeatures auf der seite **Einstellungen** im Portal, damit Sie die erforderlichen Informationen zum Konfigurieren unterstützter SIEM-Tools verwenden und generieren können.
[Konfigurieren von Splunk zum Ziehen von Microsoft Defender for Endpoint-Erkennungen](configure-siem.md)| Erfahren Sie mehr über die Installation der modularen Eingabe-App für die REST-API und andere Konfigurationseinstellungen, damit Splunk Microsoft Defender for Endpoint-Erkennungen abrufen kann.
[Konfigurieren von HP ArcSight zum Ziehen von Microsoft Defender for Endpoint-Erkennungen](configure-arcsight.md)| Erfahren Sie mehr über die Installation des HP ArcSight REST FlexConnector-Pakets und die Dateien, die Sie zum Konfigurieren von ArcSight zum Ziehen von Microsoft Defender for Endpoint-Erkennungen benötigen.
[Microsoft Defender for Endpoint Detection-Felder](api-portal-mapping.md) | Erfahren Sie, welche Datenfelder als Teil der Benachrichtigungs-API verfügbar gemacht werden und wie sie Microsoft Defender Security Center.
[Abrufen von Microsoft Defender for Endpoint-Erkennungen mithilfe der REST-API](pull-alerts-using-rest-api.md) | Verwenden Sie den OAuth 2.0-Ablauf der Clientanmeldeinformationen, um Erkennungen von Microsoft Defender for Endpoint mithilfe der REST-API zu abrufen.
[Behandeln von Problemen mit der Integration von SIEM-Tools](troubleshoot-siem.md) | Beheben von Problemen, die beim Verwenden des SIEM-Integrationsfeatures auftreten können.



## <a name="related-topics"></a>Verwandte Themen
- [Indikatoren verwalten](manage-indicators.md)
