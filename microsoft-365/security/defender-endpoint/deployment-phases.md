---
title: Bereitstellungsphasen
description: Erfahren Sie, wie Sie Microsoft Defender for Endpoint bereitstellen, indem Sie Endpunkte für diesen Dienst vorbereiten, einrichten und integrieren.
keywords: Bereitstellen, Vorbereiten, Einrichten, Onboarding, Phase, Bereitstellung, Bereitstellen, Einführung, Konfigurieren
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3f0527192a55d67df7e23507bed46df446f8b2b7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165165"
---
# <a name="deployment-phases"></a>Bereitstellungsphasen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Erfahren Sie, wie Sie Microsoft Defender for Endpoint bereitstellen, damit Ihr Unternehmen den vorbeugenden Schutz, die Erkennung nach der Verletzung, die automatisierte Untersuchung und die Reaktion nutzen kann. 


Dieses Handbuch unterstützt Sie bei der Vorbereitung Ihrer Umgebung und der anschließenden methodischen Integration von Geräten von der Evaluierung zu einem aussagekräftigen Pilotprojekt zur vollständigen Bereitstellung.

Jeder Abschnitt entspricht einem separaten Artikel in dieser Lösung.

![Abbildung von Bereitstellungsphasen mit Details aus der Tabelle](images/deployment-guide-phases.png)


![Zusammenfassung der Bereitstellungsphasen: Vorbereiten, Einrichten, Onboarding](images/phase-diagrams/deployment-phases.png)

|Phase | Beschreibung | 
|:-------|:-----|
| [Phase 1: Vorbereiten](prepare-deployment.md)| Erfahren Sie, was Sie bei der Bereitstellung von Defender for Endpoint berücksichtigen müssen, z. B. Genehmigungen von Beteiligten, Umgebungsüberlegungen, Zugriffsberechtigungen und Einführungsreihenfolge von Funktionen. 
| [Phase 2: Setup](production-deployment.md)|  Erhalten Sie Anleitungen zu den ersten Schritten, die Sie ausführen müssen, damit Sie auf das Portal zugreifen können, z. B. das Überprüfen der Lizenzierung, das Abschließen des Setup-Assistenten und die Netzwerkkonfiguration. 
| [Phase 3: Onboarding](onboarding.md) | Erfahren Sie, wie Sie Bereitstellungsringe, unterstützte Onboardingtools basierend auf dem Endpunkttyp und das Konfigurieren der verfügbaren Funktionen verwenden. 


Nachdem Sie dieses Handbuch abgeschlossen haben, werden Sie mit den richtigen Zugriffsberechtigungen eingerichtet, Ihre Endpunkte werden onboardiert und Sensordaten für den Dienst melden, und Funktionen wie Schutz der nächsten Generation und Reduzierung der Angriffsfläche sind verfügbar.



Unabhängig von der Umgebungsarchitektur und der Bereitstellungsmethode, die Sie im [Leitfaden](deployment-strategy.md) Planen der Bereitstellung beschrieben haben, wird dieses Handbuch Sie beim Onboarding von Endpunkten unterstützen. 








## <a name="key-capabilities"></a>Wichtige Funktionen

Obwohl Microsoft Defender for Endpoint viele Funktionen bietet, besteht der Hauptzweck dieses Bereitstellungshandbuchs in der Einführung in das Onboarding von Geräten. Zusätzlich zum Onboarding werden Sie in diesem Leitfaden mit den folgenden Funktionen gestartet.



Funktion | Beschreibung 
:---|:---
Erkennung und Reaktion am Endpunkt | Funktionen zur Erkennung und Reaktion von Endpunkten werden zum Erkennen, Untersuchen und Reagieren auf Angriffsversuche und aktive Sicherheitsverletzungen verwendet.
Schutz der nächsten Generation | Zur weiteren Verstärkung des Sicherheitsperimeters Ihres Netzwerks verwendet Microsoft Defender for Endpoint den Schutz der nächsten Generation, der alle Arten neuer Bedrohungen abfangen soll.
Angriffsfläche verringern |  Stellen Sie die erste Verteidigungslinie im Stapel zur Verfügung. Indem sie sicherstellen, dass Konfigurationseinstellungen ordnungsgemäß festgelegt sind und Techniken zur Exploitminderung angewendet werden, wehren sich diese Funktionen gegen Angriffe und Nutzung.

Alle diese Funktionen sind für Microsoft Defender for Endpoint-Lizenzinhaber verfügbar. Weitere Informationen finden Sie unter [Lizenzierungsanforderungen](minimum-requirements.md#licensing-requirements).

## <a name="scope"></a>Bereich

### <a name="in-scope"></a>Im Bereich

-   Verwenden von Microsoft Endpoint Manager und Microsoft Endpoint Manager zum Integrieren von Endpunkten in den Dienst und Konfigurieren von Funktionen

-   Aktivieren von Defender for Endpoint Endpoint Detection and Response (EDR)-Funktionen

-   Aktivieren von Funktionen der Defender for Endpoint Endpoint Protection Platform (EPP)

    -   Schutz der nächsten Generation

    -   Angriffsfläche verringern


### <a name="out-of-scope"></a>Nicht inbegriffen

Die folgenden Informationen sind nicht in diesem Bereitstellungshandbuch beschrieben:

-   Konfiguration von Drittanbieterlösungen, die in Defender for Endpoint integriert werden können

-   Penetrationstests in der Produktionsumgebung




## <a name="see-also"></a>Siehe auch
- [Phase 1: Vorbereiten](prepare-deployment.md)
- [Phase 2: Einrichten](production-deployment.md)
- [Phase 3: Onboarding](onboarding.md)
- [Planen der Bereitstellung](deployment-strategy.md)