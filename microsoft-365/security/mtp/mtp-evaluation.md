---
title: Microsoft 365 Defender testen
description: Richten Sie Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung ein, um die Sicherheitslösung zum Schutz von Geräten, Identitäten, Daten und Anwendungen in Ihrer Organisation auszuprobieren und zu testen.
keywords: Testversion von Microsoft Threat Protection, Testen von Microsoft Threat Protection, Bewerten von Microsoft Threat Protection, Microsoft Threat Protection-Evaluierungslabor, Microsoft Threat Protection-Pilot, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Wartung, erweiterte Suche
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930210"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Erstellen einer Microsoft 365 Defender-Testumgebung oder -Pilotumgebung 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender


Dieses Handbuch unterstützt Sie beim Einrichten einer Laborumgebung mit Benutzern und Gruppen und führt Sie dann durch die Konfiguration der Funktionen in Microsoft 365 Defender, sodass Sie einen Bedrohungsangriff imitieren und ein aussagekräftiges Testergebnis erhalten können. 

Der Zweck der Erstellung dieser Testumgebung oder Pilotumgebung besteht im Veranschaulichen der umfassenden und integrierten Microsoft 365 Defender-Funktionen. Erfahren Sie, wie diese intelligente Sicherheitslösung erweiterte Bedrohungen in Ihrer Organisation erkennt, verhindert, automatisch untersucht und darauf reagiert. 


Sie werden durch die Schritte zum Starten der Microsoft 365 Defender-Evaluierung basierend auf den empfohlenen Bereitstellungspfaden geführt. Das Ziel ist es, Sie beim Einrichten der Sicherheitslösung entweder in einer Testumgebung mit einem Testkonto oder in einer Pilotumgebung in der Produktion mit einer Volllizenz zu unterstützen. Durch die Vorbereitung ihrer Testumgebung oder Pilotumgebung können Sie Entscheidungsträgern in Ihrer Organisation Verwendungsfälle für Sicherheitsoperation präsentieren. Wenn Sie mit der Ausführung Ihrer Angriffssimulationen fertig sind und mit den Ergebnissen zufrieden sind, können Sie sie mithilfe von Technischen Vertriebsexperten oder Experten in Ihrer Organisation vollständig in Ihrer Organisation bereitstellen und operationalisieren. 

Dieses Handbuch hilft Ihnen dabei:
- Einrichten des Laborservers und der Computer
- Konfigurieren von Active Directory mit Benutzern und Gruppen
- Einrichten und Konfigurieren von Microsoft Defender for Identity, Microsoft Defender für Office 365, Microsoft Defender for Endpoint und Microsoft Cloud App Security
- Einrichten lokaler Richtlinien für Ihren Server und Ihre Computer
- Imitieren eines Bedrohungsangriffs, um einen Testvorfall oder eine Warnung in Microsoft 365 Defender zu generieren

>[!IMPORTANT]
>Befolgen Sie für optimale Ergebnisse die Anweisungen zum Einrichten der Übung so genau wie möglich.


## <a name="deployment-phases"></a>Bereitstellungsphasen

Es gibt drei Phasen beim Erstellen einer Microsoft 365 Defender-Testumgebung.

![Bereitstellungsphasen: Vorbereiten, Einrichten, Onboarding](../../media/evaluation-guide-phases.png)

|Phase | Beschreibung | 
|:-------|:-----|
|[Phase 1: Vorbereiten](prepare-mtpeval.md)| Erfahren Sie, was Sie bei der Bereitstellung von Microsoft 365 Defender in einer Testumgebung oder Pilotumgebung berücksichtigen müssen: <br><br>– Projektbeteiligten und Abmelden <br> – Überlegungen zur Umgebung <br>– Zugriff <br>– Azure Active Directory Setup <br> – Konfigurationsreihenfolge
|[Phase 2: Einrichten](setup-mtpeval.md)|  Machen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center, um Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung zu einrichten. Sie werden geführt zu:<br><br>– Registrieren für Die Testversion von Microsoft 365 E5 <br>  - Konfigurieren der Domäne<br>– Zuweisen von Microsoft 365 E5-Lizenzen<br>– Abschließen des Setup-Assistenten im Portal|
|[Phase 3: Konfigurieren & Onboarding](config-mtpeval.md) | Konfigurieren Sie die einzelnen Microsoft 365 Defender-Säulen- und Onboard-Endpunkte. Sie werden geführt zu:<br><br>- Konfigurieren von Microsoft Defender für Office 365<br>– Konfigurieren von Microsoft Cloud App Security<br>– Konfigurieren von Microsoft Defender for Identity<br>- Konfigurieren von Microsoft Defender für Endpunkt


Nachdem Sie dieses Handbuch abgeschlossen haben, hätten Sie die beteiligten Beteiligten und die erforderlichen Genehmigungen identifiziert, über die richtigen Zugriffsberechtigungen verfügen, sich für die Testversion registrieren, Domänen und jede der Microsoft 365 Defender-Säulen konfiguriert, und Ihre Endpunkte werden in den Dienst eingebunden.

## <a name="key-capabilities"></a>Wichtige Funktionen

Obwohl Microsoft 365 Defender viele Funktionen bietet, besteht der Hauptzweck dieses Bereitstellungshandbuchs im Einstieg in das Onboarding von Geräten. Zusätzlich zum Onboarding erhalten Sie in diesem Leitfaden die ersten Schritte mit den folgenden Funktionen.


Funktion | Beschreibung 
:---|:---
Microsoft Defender für Office 365 | Schützt Ihre gesamte Office 365-Envrionment vor heutigen Bedrohungen.
Microsoft Defender for Identity | Identifiziert und erkennt Bedrohungen für gefährdete Identitäten und böswillige Insideraktionen.
Microsoft Cloud App-Sicherheit | Bietet umfassende Transparenz, kontrolle über den Datenverkehr und erkennt Cyberbedrohungen über Clouddienste hinweg.
Microsoft Defender für Endpunkt | Verhindert, erkennt und bietet Reaktionsfunktionen für erweiterte Bedrohungen mit umfassender Endpunktsicherheit.


## <a name="in-scope"></a>Im Bereich

Die folgenden Aufgaben sind in diesem Leitfaden beschrieben:
-   Einrichten von Azure Active Directory
-   Einrichten von Microsoft 365 Defender
    -   Registrieren Sie sich für die Testversion von Microsoft 365 E5, oder verwenden Sie Ihre Volllizenz, wenn Sie ein Pilotprojekt ausführen
    -   Konfigurieren der Domäne
    -   Zuweisen von Microsoft 365 E5-Lizenzen
    -   Abschließen des Setup-Assistenten im Portal
-   Konfigurieren aller Microsoft 365 Defender-Säulen basierend auf bewährten Methoden
    -   Microsoft Defender für Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App-Sicherheit
    -   Microsoft Defender für Endpunkt

## <a name="out-of-scope"></a>Nicht inbegriffen

Die folgenden Themen werden in diesem Bereitstellungshandbuch nicht beschrieben:

-   Konfiguration von Drittanbieterlösungen, die in Microsoft 365 Defender integriert werden können
-   Penetrationstests in der Produktionsumgebung

## <a name="next-step"></a>Nächster Schritt
[Phase 1: Vorbereiten](prepare-mtpeval.md) 
<br> Vorbereiten ihrer Microsoft 365 Defender-Testumgebung oder -Pilotumgebung
