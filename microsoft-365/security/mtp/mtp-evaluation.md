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
ms.openlocfilehash: 8504b036203e1f73dc9e0a0d79a228425fb88bfa
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659633"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Erstellen eines Microsoft 365 Defender-Testlabors oder einer Pilotumgebung 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender


Dieses Handbuch hilft Ihnen beim Einrichten einer Lab-Umgebung mit Benutzern und Gruppen und führt Sie durch die Konfiguration der Funktionen in Microsoft 365 Defender, sodass Sie einen Bedrohungs Angriff nachahmen und ein aussagekräftiges Testergebnis erhalten können. 

Der Zweck der Erstellung dieser Test Labor-oder Pilotumgebung besteht darin, die umfassenden und integrierten Funktionen von Microsoft 365 Defender zu veranschaulichen. Erfahren Sie, wie diese intelligente Sicherheitslösung erkannt, verhindert, automatisch untersucht und auf Erweiterte Bedrohungen Ihrer Organisation reagiert. 


Sie werden durch die Schritte zum Starten Ihrer Microsoft 365 Defender-Evaluierung basierend auf den empfohlenen Bereitstellungspfaden geführt. Das Ziel besteht darin, Sie bei der Einrichtung der Sicherheitslösung entweder in einer Testumgebung mit einem Test Konto oder in einer Pilotumgebung in der Produktion mit einer Vollversion zu unterstützen. Durch die Vorbereitung Ihrer Test Labor-oder Pilotumgebung können Sie Entscheidungsträgern in Ihrer Organisation bei der Vorgehensweise Sicherheitseinsatz-Anwendungsfällen helfen. Wenn Sie die Angriffssimulationen ausgeführt haben und mit den Ergebnissen zufrieden sind, können Sie Sie in Ihrer Organisation mit Hilfe von technischen Microsoft-Vertriebsexperten oder Experten in Ihrer Organisation vollständig bereitstellen und in Betrieb nehmen. 

Dieses Handbuch hilft Ihnen dabei:
- Einrichten des Lab-Servers und der Computer
- Konfigurieren von Active Directory mit Benutzern und Gruppen
- Einrichten und Konfigurieren von Microsoft Defender für Identity, Microsoft Defender für Office 365, Microsoft Defender for Endpoint und Microsoft Cloud App Security
- Einrichten von lokalen Richtlinien für Ihren Server und ihre Computer
- Simulieren eines Bedrohungs Angriffs zum Generieren eines Test Vorfalls oder einer Warnung in Microsoft 365 Defender

>[!IMPORTANT]
>Um optimale Ergebnisse zu erzielen, befolgen Sie die Anweisungen im Labor Setup so genau wie möglich.


## <a name="deployment-phases"></a>Bereitstellungsphasen

Es gibt drei Phasen beim Erstellen einer Testumgebung für Microsoft 365 Defender.

![Bereitstellungsphasen: vorbereiten, einrichten, Onboard](../../media/evaluation-guide-phases.png)

|Phase | Beschreibung | 
|:-------|:-----|
|[Phase 1: Vorbereiten](prepare-mtpeval.md)| Erfahren Sie, was Sie bei der Bereitstellung von Microsoft 365 Defender in einer Test Labor-oder Pilotumgebung berücksichtigen müssen: <br><br>-Stakeholder und Sign-Off <br> -Umgebungs Überlegungen <br>-Access <br>-Azure-Active Directory-Setup <br> -Konfigurations Reihenfolge
|[Phase 2: Setup](setup-mtpeval.md)|  Führen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center aus, um die Testumgebung für das Microsoft 365 Defender-Testlabor oder die Pilotumgebung einzurichten. Sie werden zu folgenden Themen geführt:<br><br>-Registrieren für Microsoft 365 E5-Testversion <br>  -Domäne konfigurieren<br>-Zuweisen von Microsoft 365 E5-Lizenzen<br>-Abschließen des Setup-Assistenten im Portal|
|[Phase 3: Konfigurieren von & Onboard](config-mtpeval.md) | Konfigurieren Sie die einzelnen Microsoft 365 Defender-Pfeiler und Onboard-Endpunkte. Sie werden zu folgenden Themen geführt:<br><br>-Konfigurieren von Microsoft Defender für Office 365<br>-Konfigurieren der Microsoft Cloud-App-Sicherheit<br>-Konfigurieren von Microsoft Defender für Identity<br>-Konfigurieren von Microsoft Defender für Endpoint


Nachdem Sie dieses Handbuch abgeschlossen haben, hätten Sie die beteiligten Beteiligten und die erforderlichen Genehmigungen identifiziert, über die richtigen Zugriffsberechtigungen verfügen, sich für eine Testversion angemeldet haben, konfigurierte Domänen und alle Microsoft 365 Defender-Säulen haben und die Endpunkte an den Dienst weitergeleitet werden.

## <a name="key-capabilities"></a>Wichtige Funktionen

Während Microsoft 365 Defender zahlreiche Funktionen bietet, besteht der Hauptzweck dieses Bereitstellungshandbuchs darin, Ihnen den Einstieg in die Onboarding-Geräte zu ermöglichen. Neben dem Onboarding erhalten Sie in diesem Leitfaden zunächst die folgenden Funktionen.


Funktion | Beschreibung 
:---|:---
Microsoft Defender für Office 365 | Schützt Ihr gesamtes Office 365 Umgebung vor den Bedrohungen von heute
Microsoft Defender for Identity | Identifiziert und erkennt Bedrohungen für kompromittierte Identitäten und böswillige Insider Aktionen.
Microsoft Cloud App Security | Bietet umfangreiche Sichtbarkeit, steuert Daten Reisen und erkennt Bedrohungen in Cloud-Diensten.
Microsoft Defender für Endpunkt | Verhindert, erkennt und stellt Reaktionsfunktionen für erweiterte Bedrohungen mit umfassender Endpunktsicherheit bereit.


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
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender für Endpunkt

## <a name="out-of-scope"></a>Nicht inbegriffen

Im Rahmen dieses Bereitstellungshandbuchs liegen folgende Schritte vor:

-   Konfiguration von Drittanbieterlösungen, die in Microsoft 365 Defender integriert werden können
-   Penetrationstests in der Produktionsumgebung

## <a name="next-step"></a>Nächster Schritt
[Phase 1: Vorbereiten](prepare-mtpeval.md) 
<br> Vorbereiten des Testlabors oder der Pilotumgebung für den Microsoft 365 Defender
