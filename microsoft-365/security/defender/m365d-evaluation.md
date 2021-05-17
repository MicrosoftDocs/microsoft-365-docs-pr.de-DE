---
title: Microsoft 365 Defender testen
description: Richten Sie ihre Microsoft 365 Testumgebung oder Pilotumgebung für Defender ein, um die Sicherheitslösung zum Schutz von Geräten, Identitäten, Daten und Anwendungen in Ihrer Organisation auszuprobieren und zu erleben.
keywords: Microsoft 365 Defender Trial, try Microsoft 365 Defender, evaluate Microsoft 365 Defender, Microsoft 365 Defender evaluation lab, Microsoft 365 Defender pilot, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933169"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Erstellen einer Microsoft 365 Testumgebung oder Pilotumgebung für Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender


Dieses Handbuch hilft Ihnen bei der Einrichtung einer Laborumgebung mit Benutzern und Gruppen und führt Sie dann durch die Konfiguration der Funktionen in Microsoft 365 Defender, damit Sie einen Bedrohungsangriff imitieren und ein aussagekräftiges Testergebnis erzielen können. 

Der Zweck der Erstellung dieser Testumgebung oder Pilotumgebung besteht in der Veranschaulichen der umfassenden und integrierten Microsoft 365 Defender-Funktionen. Erfahren Sie, wie diese intelligente Sicherheitslösung erweiterte Bedrohungen in Ihrer Organisation erkennt, verhindert, automatisch untersucht und reagiert. 


Sie werden anhand der empfohlenen Bereitstellungspfade durch die Schritte geführt, um Microsoft 365 Defender-Evaluierung zu starten. Das Ziel besteht in der Einrichtung der Sicherheitslösung entweder in einer Laborumgebung mit einem Testkonto oder in einer Pilotumgebung in der Produktion mit volllizenz. Durch die Vorbereitung Ihrer Testumgebung oder Pilotumgebung können Sie Entscheidungsträgern in Ihrer Organisation Verwendungsfälle für Sicherheitsoperation präsentieren. Wenn Sie mit der Ausführung Ihrer Angriffssimulationen fertig sind und mit den Ergebnissen zufrieden sind, können Sie sie in Ihrer Organisation vollständig bereitstellen und mithilfe von Microsoft Technical Sales Professionals oder Experten in Ihrer Organisation operationalisieren. 

Dieses Handbuch hilft Ihnen dabei:
- Einrichten des Laborservers und der Computer
- Konfigurieren von Active Directory mit Benutzern und Gruppen
- Einrichten und Konfigurieren von Microsoft Defender for Identity, Microsoft Defender für Office 365, Microsoft Defender für Endpoint und Microsoft Cloud App Security
- Einrichten lokaler Richtlinien für Server und Computer
- Imitieren eines Bedrohungsangriffs zum Generieren eines Testvorfalls oder einer Warnung in Microsoft 365 Defender

>[!IMPORTANT]
>Um optimale Ergebnisse zu erzielen, befolgen Sie die Anweisungen zum Einrichten des Labors so genau wie möglich.


## <a name="deployment-phases"></a>Bereitstellungsphasen

Es gibt drei Phasen beim Erstellen einer Microsoft 365 Defender-Testumgebung.

![Bereitstellungsphasen: Vorbereiten, Einrichten, Onboarding](../../media/evaluation-guide-phases.png)

|Phase | Beschreibung | 
|:-------|:-----|
|[Phase 1: Vorbereiten](prepare-m365d-eval.md)| Erfahren Sie, was Sie bei der Bereitstellung Microsoft 365 Defender in einer Testumgebung oder Pilotumgebung berücksichtigen müssen: <br><br>– Beteiligte und Abmelden <br> – Überlegungen zur Umgebung <br>- Access <br>- Azure Active Directory Setup <br> - Konfigurationsreihenfolge
|[Phase 2: Setup](setup-m365deval.md)|  Ergreifen Sie die ersten Schritte, um auf Microsoft 365 Security Center zu zugreifen, um Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung zu einrichten. Sie werden geführt zu:<br><br>– Registrieren für Microsoft 365 E5 Testversion <br>  - Konfigurieren der Domäne<br>- Zuweisen Microsoft 365 E5 Lizenzen<br>– Abschließen des Setup-Assistenten im Portal|
|[Phase 3: Konfigurieren & Onboard](config-m365d-eval.md) | Konfigurieren Sie Microsoft 365 Defender-Säule und onboard-Endpunkte. Sie werden geführt zu:<br><br>- Konfigurieren von Microsoft Defender für Office 365<br>- Konfigurieren Microsoft Cloud App Security<br>- Konfigurieren von Microsoft Defender for Identity<br>- Konfigurieren von Microsoft Defender for Endpoint


Nachdem Sie dieses Handbuch abgeschlossen haben, hätten Sie die beteiligten Beteiligten und die erforderlichen Genehmigungen identifiziert, über die richtigen Zugriffsberechtigungen verfügen, sich für Testversionen registrieren, Domänen und jede der Microsoft 365 Defender-Säulen konfiguriert, und Ihre Endpunkte werden in den Dienst eingebunden.

## <a name="key-capabilities"></a>Wichtige Funktionen

Während Microsoft 365 Defender viele Funktionen bietet, besteht der Hauptzweck dieses Bereitstellungshandbuchs in der Einführung in das Onboarding von Geräten. Zusätzlich zum Onboarding werden Sie in diesem Leitfaden mit den folgenden Funktionen gestartet.


Funktion | Beschreibung 
:---|:---
Microsoft Defender für Office 365 | Schützt Ihre gesamte Office 365 vor heutigen Bedrohungen
Microsoft Defender for Identity | Identifiziert und erkennt Bedrohungen für gefährdete Identitäten und böswillige Insideraktionen.
Microsoft Cloud App Security | Bietet umfassende Sichtbarkeit, steuern Sie den Datenverkehr und erkennen Cyberangriffe über Clouddienste hinweg.
Microsoft Defender für Endpunkt | Verhindert, erkennt und stellt Reaktionsfunktionen für erweiterte Bedrohungen mit umfassender Endpunktsicherheit bereit.


## <a name="in-scope"></a>Im Bereich

Die folgenden Aufgaben sind für dieses Handbuch im Bereich:
-   Einrichten Azure Active Directory
-   Einrichten von Microsoft 365 Defender
    -   Registrieren Sie sich für Microsoft 365 E5 Testversion, oder verwenden Sie Ihre Volllizenz, wenn Sie ein Pilotprojekt ausführen
    -   Konfigurieren der Domäne
    -   Zuweisen Microsoft 365 E5 Lizenzen
    -   Abschließen des Setup-Assistenten im Portal
-   Konfigurieren aller Microsoft 365 defender-Säulen basierend auf bewährten Methoden
    -   Microsoft Defender für Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender für Endpunkt

## <a name="out-of-scope"></a>Nicht inbegriffen

Die folgenden Informationen sind nicht in diesem Bereitstellungshandbuch beschrieben:

-   Konfiguration von Drittanbieterlösungen, die in Defender integriert Microsoft 365 können
-   Penetrationstests in der Produktionsumgebung

## <a name="next-step"></a>Nächster Schritt
[Phase 1: Vorbereiten](prepare-m365d-eval.md) 
<br> Vorbereiten ihrer Microsoft 365 Testumgebung oder Pilotumgebung für Defender
