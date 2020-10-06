---
title: Microsoft Threat Protection evaluieren
description: Richten Sie Ihr Microsoft Threat Protection-Test Labor oder Ihre Pilotumgebung ein, um zu testen, wie die koordinierte Bedrohungsschutz Lösung zum Schutz von Geräten, Identitäten, Daten und Anwendungen Ihrer Organisation helfen kann.
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 3768937fc882fee8d6a744e4fb504095882c7e81
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368059"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a>Erstellen eines Microsoft Threat Protection-Testlabors oder einer Pilotumgebung 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Der Zweck der Erstellung dieser Test Labor-oder Pilotumgebung besteht darin, die umfassenden, integrierten und intelligenten Funktionen von Microsoft Threat Protection in Erkennung, Verhinderung, Untersuchung und Antwort zu veranschaulichen, die Sie in Ihrer Organisation verwenden können. 

Dieses Handbuch führt Sie durch die Schritte zum Starten Ihrer Microsoft Threat Protection-Evaluierung basierend auf den empfohlenen Bereitstellungspfaden. Das Ziel besteht darin, Sie beim Einrichten der integrierten Microsoft Threat Protection-Dienste in einer Testumgebung bei der Verwendung eines Testkontos oder in einer Pilotumgebung in der Produktion bei Verwendung einer Vollversion zu unterstützen. Die Ergebnisse von sind hilfreich bei der Darstellung von Sicherheitseinsatz-Anwendungsfällen für Entscheidungsträger der Sicherheitslösung in Ihrer Organisation. Wenn Sie die Angriffssimulationen ausgeführt haben und mit den Ergebnissen zufrieden sind, können Sie Sie in Ihrer Organisation mit Hilfe von technischen Microsoft-Vertriebsexperten oder Experten in Ihrer Organisation vollständig bereitstellen und in Betrieb nehmen. 

Dieses Handbuch hilft Ihnen dabei:
- Einrichten des Lab-Servers und der Computer
- Konfigurieren von Active Directory mit Benutzern und Gruppen
- Einrichten und Konfigurieren von Azure ATP, Office ATP, Microsoft Defender ATP und Microsoft Cloud App Security
- Einrichten von lokalen Richtlinien für Ihren Server und ihre Computer
- Simulieren eines Bedrohungs Angriffs zum Generieren eines Test Vorfalls oder einer Warnung in Microsoft Threat Protection

>[!IMPORTANT]
>Um optimale Ergebnisse zu erzielen, befolgen Sie die Anweisungen im Labor Setup so genau wie möglich.


## <a name="deployment-phases"></a>Bereitstellungsphasen

Es gibt drei Phasen, in denen eine Microsoft Threat Protection-Testumgebung erstellt und bereitgestellt wird:

|Phase | Beschreibung | 
|:-------|:-----|
| ![Phase 1: Vorbereiten](../../media/prepare.png)<br>[Phase 1: Vorbereiten](prepare-mtpeval.md)| Erfahren Sie, was Sie bei der Bereitstellung von Microsoft Threat Protection in einer Test Labor-oder Pilotumgebung berücksichtigen müssen: <br><br>-Stakeholder und Sign-Off <br> -Umgebungs Überlegungen <br>-Access <br>-Azure-Active Directory-Setup <br> -Konfigurations Reihenfolge
|  ![Phase 2: Setup](../../media/setup.png) <br>[Phase 2: Setup](setup-mtpeval.md)|  Führen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center aus, um Ihre Microsoft Threat Protection-Testumgebung oder Pilotumgebung einzurichten. Sie werden zu folgenden Themen geführt:<br><br>-Registrieren für Microsoft 365 E5-Testversion <br>  -Domäne konfigurieren<br>-Zuweisen von Microsoft 365 E5-Lizenzen<br>-Abschließen des Setup-Assistenten im Portal|
|  ![Phase 3: Konfigurieren von & Onboard](../../media/config-onboard.png) <br>[Phase 3: Konfigurieren von & Onboard](config-mtpeval.md) | Konfigurieren Sie die einzelnen Microsoft Threat Protection-Pfeiler und Onboard-Endpunkte. Sie werden zu folgenden Themen geführt:<br><br>-Konfigurieren Office 365 Advanced Threat Protection<br>-Konfigurieren der Microsoft Cloud-App-Sicherheit<br>-Konfigurieren von Azure Advanced Threat Protection<br>-Konfigurieren von Microsoft Defender Advanced Threat Protection 


## <a name="in-scope"></a>Im Bereich

Die folgenden Aufgaben liegen im Bereich dieses Handbuchs:
-   Einrichten von Azure Active Directory
-   Einrichten von Microsoft Threat Protection
    -   Registrieren Sie sich für die Microsoft 365 E5-Testversion, oder verwenden Sie Ihre vollständige Lizenz, wenn Sie ein Pilotprojekt betreiben.
    -   Konfigurieren der Domäne
    -   Zuweisen von Microsoft 365 E5-Lizenzen
    -   Abschließen des Setup-Assistenten im Portal
-   Konfigurieren aller Microsoft Threat Protection-Säulen basierend auf bewährten Methoden
    -   Office 365 Advanced Threat Protection
    -   Azure Advanced Threat Protection
    -   Microsoft Cloud App-Sicherheit
    -   Microsoft Defender Advanced Threat Protection

## <a name="out-of-scope"></a>Nicht inbegriffen

Im Rahmen dieses Bereitstellungshandbuchs liegen folgende Schritte vor:

-   Konfiguration von Drittanbieterlösungen, die sich möglicherweise in Microsoft Threat Protection integrieren lassen
-   Penetrationstests in der Produktionsumgebung

## <a name="next-step"></a>Nächster Schritt
![Phase 1: Vorbereiten](../../media/prepare.png) <br>[Phase 1: Vorbereiten](prepare-mtpeval.md) 
<br> Vorbereiten Ihrer Testlabor-oder Pilotumgebung für den Microsoft Threat Protection-Test
