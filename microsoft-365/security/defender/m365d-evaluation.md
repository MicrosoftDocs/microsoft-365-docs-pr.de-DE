---
title: Microsoft 365 Defender testen
description: Richten Sie Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung ein, um die Sicherheitslösung zum Schutz von Geräten, Identität, Daten und Anwendungen in Ihrer Organisation auszuprobieren und zu testen.
keywords: Microsoft 365 Defender Testversion, testen Sie Microsoft 365 Defender, bewerten Sie Microsoft 365 Defender, Microsoft 365 Defender Evaluierungslabor, Microsoft 365 Defender Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
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
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458428"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Erstellen einer Microsoft 365 Defender Testumgebung oder Pilotumgebung 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender


Dieser Leitfaden hilft Ihnen beim Einrichten einer Lab-Umgebung mit Benutzern und Gruppen und führt Sie dann durch die Konfiguration der Funktionen in Microsoft 365 Defender, sodass Sie einen Bedrohungsangriff imitieren und ein aussagekräftiges Testergebnis erhalten können. 

Der Zweck der Erstellung dieser Testumgebung oder Pilotumgebung besteht darin, die umfassenden und integrierten Microsoft 365 Defender Funktionen zu veranschaulichen. Erfahren Sie, wie diese intelligente Sicherheitslösung fortschrittliche Bedrohungen in Ihrer Organisation erkennt, verhindert, automatisch untersucht und darauf reagiert. 


Sie werden durch die Schritte geführt, um ihre Microsoft 365 Defender Evaluierung basierend auf den empfohlenen Bereitstellungspfaden zu starten. Das Ziel besteht darin, Sie beim Einrichten der Sicherheitslösung entweder in einer Testumgebung mit einem Testkonto oder in einer Pilotumgebung in der Produktion mit einer Volllizenz zu unterstützen. Durch die Vorbereitung Ihrer Testumgebung oder Pilotumgebung können Sie Entscheidungsträgern in Ihrer Organisation Anwendungsfälle für den Sicherheitsvorgang präsentieren. Wenn Sie ihre Angriffssimulationen abgeschlossen haben und mit den Ergebnissen zufrieden sind, können Sie sie mithilfe von Microsoft Technical Sales Professionals oder Experten in Ihrer Organisation vollständig bereitstellen und in Ihrer Organisation operationalisieren. 

Dieser Leitfaden hilft Ihnen dabei:
- Einrichten des Lab-Servers und der Computer
- Konfigurieren von Active Directory mit Benutzern und Gruppen
- Einrichten und Konfigurieren von Microsoft Defender for Identity, Microsoft Defender für Office 365, Microsoft Defender für Endpunkt und Microsoft Cloud App Security
- Einrichten von lokalen Richtlinien für Ihren Server und Computer
- Imitieren eines Bedrohungsangriffs zum Generieren eines Testvorfalls oder einer Warnung in Microsoft 365 Defender

>[!IMPORTANT]
>Um optimale Ergebnisse zu erzielen, befolgen Sie die Anweisungen für die Laboreinrichtung so genau wie möglich.


## <a name="deployment-phases"></a>Bereitstellungsphasen

Es gibt drei Phasen beim Erstellen einer Microsoft 365 Defender Testumgebung.

![Bereitstellungsphasen: Vorbereiten, Einrichten, Onboarding](../../media/evaluation-guide-phases.png)

|Phase | Beschreibung | 
|:-------|:-----|
|[Phase 1: Vorbereiten](prepare-m365d-eval.md)| Erfahren Sie, was Sie berücksichtigen müssen, wenn Sie Microsoft 365 Defender in einer Testumgebung oder Pilotumgebung bereitstellen: <br><br>– Projektbeteiligten und Abmeldung <br> – Überlegungen zur Umgebung <br>– Zugriff <br>– Azure Active Directory Einrichten <br> - Konfigurationsreihenfolge
|[Phase 2: Setup](setup-m365deval.md)|  Führen Sie die ersten Schritte aus, um auf Microsoft 365 Security Center zuzugreifen, um Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung einzurichten. Sie werden zu folgenden Themen geführt:<br><br>– Registrieren für Microsoft 365 E5 Testversion <br>  - Konfigurieren der Domäne<br>– Zuweisen Microsoft 365 E5 Lizenzen<br>– Abschließen des Setup-Assistenten im Portal|
|[Phase 3: Konfigurieren & Onboarding](config-m365d-eval.md) | Konfigurieren Sie die einzelnen Microsoft 365 Defender Säulen und integrieren Sie Endpunkte. Sie werden zu folgenden Themen geführt:<br><br>– Konfigurieren von Microsoft Defender für Office 365<br>- Konfigurieren Microsoft Cloud App Security<br>– Konfigurieren von Microsoft Defender for Identity<br>– Konfigurieren von Microsoft Defender für Endpunkt


Nachdem Sie diesen Leitfaden abgeschlossen haben, hätten Sie die beteiligten Beteiligten und die erforderlichen Genehmigungen identifiziert, die richtigen Zugriffsberechtigungen haben, sich für testversionsbasierte, konfigurierte Domänen und jede der Microsoft 365 Defender Säulen angemeldet haben, und Ihre Endpunkte werden in den Dienst integriert.

## <a name="key-capabilities"></a>Wichtige Funktionen

Obwohl Microsoft 365 Defender viele Funktionen bietet, besteht der Hauptzweck dieses Bereitstellungshandbuchs darin, Ihnen die ersten Schritte beim Onboarding von Geräten zu ermöglichen. Zusätzlich zum Onboarding können Sie mit dieser Anleitung mit den folgenden Funktionen beginnen.


Funktion | Beschreibung 
:---|:---
Microsoft Defender für Office 365 | Trägt dazu bei, Ihre gesamte Office 365 Bedrohungen vor heutigen Bedrohungen zu schützen.
Microsoft Defender for Identity | Identifiziert und erkennt Bedrohungen für kompromittierte Identitäten und böswillige Insideraktionen.
Microsoft Cloud App Security | Bietet umfassende Sichtbarkeit, Kontrolle der Daten-Reise und Erkennung von Cyberbedrohungen über Clouddienste hinweg.
Microsoft Defender für Endpunkt | Verhindert, erkennt und bietet Reaktionsfunktionen auf fortgeschrittene Bedrohungen mit umfassender Endpunktsicherheit.


## <a name="in-scope"></a>Im Bereich

Die folgenden Aufgaben sind in diesem Leitfaden enthalten:
-   Einrichten Azure Active Directory
-   Einrichten Microsoft 365 Defender
    -   Registrieren Sie sich für Microsoft 365 E5 Testversion, oder verwenden Sie Ihre Volllizenz, wenn Sie ein Pilotprojekt ausführen
    -   Domäne konfigurieren
    -   Zuweisen Microsoft 365 E5 Lizenzen
    -   Abschließen des Setup-Assistenten im Portal
-   Konfigurieren aller Microsoft 365 Defender Säulen basierend auf bewährten Methoden
    -   Microsoft Defender für Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender für Endpunkt

## <a name="out-of-scope"></a>Nicht inbegriffen

Der Umfang dieses Bereitstellungshandbuchs wird nicht behandelt:

-   Konfiguration von Drittanbieterlösungen, die in Microsoft 365 Defender integriert werden können
-   Penetrationstests in der Produktionsumgebung

## <a name="next-step"></a>Nächster Schritt
[Phase 1: Vorbereiten](prepare-m365d-eval.md) 
<br> Vorbereiten ihrer Microsoft 365 Defender Testumgebung oder Pilotumgebung
