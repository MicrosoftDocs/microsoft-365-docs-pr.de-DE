---
title: Ausführen des Pilotprojekts Microsoft 365 Defender-Projekts
description: Führen Sie Ihr Microsoft 365 Defender-Projekt in der Produktion aus, um die Vorteile und die Akzeptanz von Defender Microsoft 365 bestimmen.
keywords: Microsoft 365 Defender-Pilot, Ausführen eines Pilotprojekts Microsoft 365 Defender-Projekt, Evaluieren von Microsoft 365 Defender in der Produktion, Microsoft 365 Defender-Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Geräte, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
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
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b1616b39597a90ff8e8f7b4c92f29f75c62fea18
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934429"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Ausführen des Pilotprojekts Microsoft 365 Defender-Projekts 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender


Dieses Handbuch hilft Ihnen bei der Ausführung eines Pilotprojekts, indem Sie Zeiger bereitstellen, um sicherzustellen, dass Sie über einen gut strukturierten Plan verfügen, Sie durch die Verwendung des Angriffssimulationsfeatures führen und schließlich das Pilotprojekt mit wichtigen Take-Aways für Sie zum Reflektieren und Dokumentieren von Ergebnissen enth fen.

![Phasen beim Ausführen eines Microsoft 365 Defender-Pilot](../../media/pilotphases.png)


Das Ausführen eines Pilotprojekts hilft Ihnen, den Nutzen der Einführung von Microsoft 365 zu ermitteln. Bevor Sie Microsoft 365 Defender in Ihrer Produktionsumgebung aktivieren und Ihre Verwendungsfälle starten, sollten Sie die Aufgaben für Ihr Pilotprojekt ermitteln und die Erfolgskriterien festlegen. 


## <a name="how-to-use-this-pilot-playbook"></a>Verwenden dieses Pilotspielbuchs

Dieses Handbuch bietet eine Übersicht über Microsoft 365 Defender und schrittweise Anweisungen zum Einrichten Ihres Pilotprojekts. 

Microsoft 365 Defender ist eine einheitliche Vor- und Nachverletzungs-Enterprise-Defense-Suite, die Schutz, Erkennung, Verhinderung, Untersuchung und Reaktion auf Endpunkte, Identitäten, E-Mails und Anwendungen nativ koordiniert, um integrierten Schutz vor komplexen Angriffen zu bieten. Dazu werden die folgenden Funktionen in einer einzigen Sicherheitslösung kombiniert und orchestriert:
  - Microsoft Defender for Endpoint (Endpoints)
  - Microsoft Defender für Office 365 (E-Mail) 
  - Microsoft Defender for Identity (Identity) 
  - Microsoft Cloud App Security (Apps)

![Image of_Microsoft 365 Defender solution for users, Microsoft Defender for Identity, for endpoints Microsoft Defender for Endpoint, for cloud apps, Microsoft Cloud App Security, and for data, Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

Mit der integrierten Microsoft 365 Defender-Lösung können Sicherheitsexperten die Bedrohungssignale, die Microsoft Defender for Endpoint, Microsoft Defender für Office 365, Microsoft Defender for Identity und Microsoft Cloud App Security empfangen, zusammenbringen und den umfang und die Auswirkungen der Bedrohung, den Ein-/Aus-Umgebungs-, Denk- und Wirkungsbereich der Bedrohung bestimmen. Microsoft 365 Defender ergreift automatische Maßnahmen, um den Angriff zu verhindern oder zu beenden und betroffene Postfächer, Endpunkte und Benutzeridentitäten selbst zu beenden. Weitere Informationen [finden Microsoft 365 defender overview.](microsoft-365-defender.md)



Die folgende Beispielzeitachse variiert je nach den richtigen Ressourcen in Ihrer Umgebung. Einige Erkennungen und Workflows benötigen möglicherweise mehr Lernzeit als die anderen.

![Beispielzeitachse beim Ausführen eines Microsoft 365 Defender-Pilot](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Befolgen Sie die Pilotanweisungen so genau wie möglich, um optimale Ergebnisse zu erzielen.


### <a name="pilot-playbook-phases"></a>Pilot-Playbook-Phasen 

Es gibt vier Phasen beim Ausführen eines Microsoft 365 Defender-Piloten:

|Phase | Beschreibung | 
|:-------|:-----|
| [Planung](m365d-pilot-plan.md)<br> ~ 1 Tag| Erfahren Sie, was Sie berücksichtigen müssen, bevor Sie Ihr Microsoft 365 Defender-Pilotprojekt ausführen: <br><br>– Bereich <br> - Use cases <br>– Anforderungen <br>- Testplan <br> – Erfolgskriterien <br> - Scorecard 
| [Vorbereitung](m365d-evaluation.md) <br>~2 Tage|  Access Microsoft 365 Security Center zum Einrichten ihrer Microsoft 365 Defender-Pilotumgebung. Sie werden geführt zu:<br><br>– Identifizieren von Beteiligten und Abmelden für Ihr Pilotprojekt <br> – Überlegungen zur Umgebung <br>- Access <br>- Azure Active Directory Setup <br> - Konfigurationsreihenfolge <br> – Registrieren für Microsoft 365 E5 Testversion <br> - Konfigurieren der Domäne <br>- Zuweisen Microsoft 365 E5 Lizenzen <br> – Abschließen des Setup-Assistenten im Portal|
| [Angriffssimulator](m365d-pilot-simulate.md) <br>~2 Tage| Um einen Angriff zu simulieren, werden Sie geführt zu:<br><br>– Überprüfen der Anforderungen an die Testumgebung <br>– Ausführen der Simulation <br>- Untersuchen eines Vorfalls <br>– Beheben des Vorfalls 
| [Schließen und Zusammenfassung](m365d-pilot-close.md) <br>~ 1 Tag| Wenn Sie das Ende des Prozesses erreicht haben, werden Sie geführt zu:<br><br>- Gehen Sie durch Die endgültige Ausgabe<br>– Präsentieren Sie Ihre Ergebnisse ihren Beteiligten <br>- Feedback bereitstellen <br>– Ausführen der nächsten Schritte 

## <a name="next-step"></a>Nächster Schritt
|[Planungsphase](m365d-pilot-plan.md) | Planen Ihres Microsoft 365 Defender-Pilotprojekts 
|:-------|:-----|
