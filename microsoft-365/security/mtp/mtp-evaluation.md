---
title: Auswerten von Microsoft 365 Defender
description: Richten Sie Ihre Microsoft 365 Defender Test Lab oder Pilotumgebung ein, um die Sicherheitslösung zum Schutz von Geräten, Identitäten, Daten und Anwendungen in Ihrer Organisation zu testen und zu erleben.
keywords: Microsoft Threat Protection-Testversion, testen Sie Microsoft Threat Protection, bewerten Sie Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab, Microsoft Threat Protection Pilot, Cyber Security, Advanced persistent Threat, Enterprise Security, Devices, Device, Identity, users, Data, Applications, Incidents, Automated Investigation and Remediation, Advanced Hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: d6c96f7720344721bb2786dc130c490a5a8ea657
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846484"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Erstellen eines Microsoft 365 Defender-Testlabors oder einer Pilotumgebung 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Der Zweck der Erstellung dieser Test Labor-oder Pilotumgebung besteht darin, die umfassenden und integrierten Funktionen von Microsoft 365 Defender zu veranschaulichen. Erfahren Sie, wie diese intelligente Sicherheitslösung erkannt, verhindert, automatisch untersucht und auf Erweiterte Bedrohungen Ihrer Organisation reagiert. 

Dieses Handbuch führt Sie durch die Schritte zum Starten Ihrer Microsoft 365 Defender-Evaluierung basierend auf den empfohlenen Bereitstellungspfaden. Das Ziel besteht darin, Sie bei der Einrichtung der Sicherheitslösung entweder in einer Testumgebung mit einem Test Konto oder in einer Pilotumgebung in der Produktion mit einer Vollversion zu unterstützen. Durch die Vorbereitung Ihrer Test Labor-oder Pilotumgebung können Sie Entscheidungsträgern in Ihrer Organisation bei der Vorgehensweise Sicherheitseinsatz-Anwendungsfällen helfen. Wenn Sie die Angriffssimulationen ausgeführt haben und mit den Ergebnissen zufrieden sind, können Sie Sie in Ihrer Organisation mit Hilfe von technischen Microsoft-Vertriebsexperten oder Experten in Ihrer Organisation vollständig bereitstellen und in Betrieb nehmen. 

Dieses Handbuch hilft Ihnen dabei:
- Einrichten des Lab-Servers und der Computer
- Konfigurieren von Active Directory mit Benutzern und Gruppen
- Einrichten und Konfigurieren von Microsoft Defender für Identity, Microsoft Defender für Office 365, Microsoft Defender for Endpoint und Microsoft Cloud App Security
- Einrichten von lokalen Richtlinien für Ihren Server und ihre Computer
- Simulieren eines Bedrohungs Angriffs zum Generieren eines Test Vorfalls oder einer Warnung in Microsoft 365 Defender

>[!IMPORTANT]
>Um optimale Ergebnisse zu erzielen, befolgen Sie die Anweisungen im Labor Setup so genau wie möglich.


## <a name="deployment-phases"></a>Bereitstellungsphasen

Es gibt drei Phasen, in denen eine Microsoft 365 Defender-Testumgebung erstellt und bereitgestellt wird:

|Phase | Beschreibung | 
|:-------|:-----|
| ![Phase 1: Vorbereiten](../../media/prepare.png)<br>[Phase 1: Vorbereiten](prepare-mtpeval.md)| Erfahren Sie, was Sie bei der Bereitstellung von Microsoft 365 Defender in einer Test Labor-oder Pilotumgebung berücksichtigen müssen: <br><br>-Stakeholder und Sign-Off <br> -Umgebungs Überlegungen <br>-Access <br>-Azure-Active Directory-Setup <br> -Konfigurations Reihenfolge
|  ![Phase 2: Setup](../../media/setup.png) <br>[Phase 2: Setup](setup-mtpeval.md)|  Führen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center aus, um die Testumgebung für das Microsoft 365 Defender-Testlabor oder die Pilotumgebung einzurichten. Sie werden zu folgenden Themen geführt:<br><br>-Registrieren für Microsoft 365 E5-Testversion <br>  -Domäne konfigurieren<br>-Zuweisen von Microsoft 365 E5-Lizenzen<br>-Abschließen des Setup-Assistenten im Portal|
|  ![Phase 3: Konfigurieren von & Onboard](../../media/config-onboard.png) <br>[Phase 3: Konfigurieren von & Onboard](config-mtpeval.md) | Konfigurieren Sie die einzelnen Microsoft 365 Defender-Pfeiler und Onboard-Endpunkte. Sie werden zu folgenden Themen geführt:<br><br>-Konfigurieren von Microsoft Defender für Office 365<br>-Konfigurieren der Microsoft Cloud-App-Sicherheit<br>-Konfigurieren von Microsoft Defender für Identity<br>-Konfigurieren von Microsoft Defender für Endpoint


## <a name="in-scope"></a>Im Bereich

Die folgenden Aufgaben liegen im Bereich dieses Handbuchs:
-   Einrichten von Azure Active Directory
-   Einrichten von Microsoft 365 Defender
    -   Registrieren Sie sich für die Microsoft 365 E5-Testversion, oder verwenden Sie Ihre vollständige Lizenz, wenn Sie ein Pilotprojekt betreiben.
    -   Konfigurieren der Domäne
    -   Zuweisen von Microsoft 365 E5-Lizenzen
    -   Abschließen des Setup-Assistenten im Portal
-   Konfigurieren aller Microsoft 365 Defender-Säulen basierend auf bewährten Methoden
    -   Microsoft Defender für Office 365
    -   Microsoft Defender für Identity
    -   Microsoft Cloud App-Sicherheit
    -   Microsoft Defender für Endpunkt

## <a name="out-of-scope"></a>Nicht inbegriffen

Im Rahmen dieses Bereitstellungshandbuchs liegen folgende Schritte vor:

-   Konfiguration von Drittanbieterlösungen, die in Microsoft 365 Defender integriert werden können
-   Penetrationstests in der Produktionsumgebung

## <a name="next-step"></a>Nächster Schritt
![Phase 1: Vorbereiten](../../media/prepare.png) <br>[Phase 1: Vorbereiten](prepare-mtpeval.md) 
<br> Vorbereiten des Testlabors oder der Pilotumgebung für den Microsoft 365 Defender
