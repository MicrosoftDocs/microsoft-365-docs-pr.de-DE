---
title: Microsoft 365 Überwachung und Testen von Mandanten Grenzen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, wie Microsoft Mandanten Grenzen für Microsoft 365 kontinuierlich überwacht und testet.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd0aa3f88de3a8e22ef67283b20ecfae9959cb05
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690250"
---
# <a name="monitoring-and-testing-tenant-boundaries"></a>Überwachen und Testen von Mandantengrenzen

Microsoft überwacht und testet explizit auf Schwächen und Schwachstellen in Mandanten Grenzen, einschließlich Überwachung von Intrusionsversuchen, Berechtigungs Verletzungen und Ressourcenknappheit. Wir verwenden auch mehrere interne Systeme zur kontinuierlichen Überwachung der unangemessenen Ressourcennutzung, die, wenn Sie erkannt wird, die integrierte Einschränkung auslöst.

Microsoft 365 verfügt über interne Überwachungssysteme, die kontinuierlich für jeden Fehler überwachen und die automatische Wiederherstellung steuern, wenn ein Fehler erkannt wird. Microsoft 365-Systeme analysieren Abweichungen im Dienstverhalten und initiieren selbst Heilungsprozesse, die in das System integriert sind. Microsoft 365 verwendet außerdem eine externe Überwachung, bei der die Überwachung von mehreren Standorten aus vertrauenswürdigen Drittanbieterdiensten (für unabhängige SLA-Überprüfungen) und eigenen Rechenzentren zum Auslösen von Warnungen ausgeführt wird. Für die Diagnose verfügen wir über umfangreiche Protokollierung, Überwachung und Ablaufverfolgung. Die detaillierte Ablaufverfolgung und Überwachung hilft uns beim Isolieren von Problemen und bei der Durchführung einer schnellen und effektiven Ursachenanalyse.

Während Microsoft 365 möglicherweise automatisierte Wiederherstellungsaktionen durchführt, stehen Microsoft-Techniker mit On-Call 24X7 zur Verfügung, um alle Sicherheits Eskalationen für Schweregrade 1 zu untersuchen, und Post-mortem-Überprüfungen jedes Dienst Ereignisses tragen zur kontinuierlichen Weiterbildung und Verbesserung bei Dieses Team umfasst Supporttechniker, Produktentwickler, Programmmanager, Produktmanager und Führungskräfte. Unsere On-Call-Experten bieten rechtzeitige Sicherung und können häufig Wiederherstellungsaktionen automatisieren, sodass das nächste Mal, wenn ein Ereignis eintritt, es selbst geheilt werden kann.

Microsoft führt bei jedem Auftreten eines Microsoft 365-Sicherheitsvorfalls unabhängig von der Größe der Auswirkungen eine gründliche nach Prüfung durch. Eine Überprüfung nach dem Vorfall besteht aus einer Analyse der Ereignisse, der Reaktion und der Art und Weise, wie wir in Zukunft ähnliche Vorfälle verhindern. Im Interesse von Transparenz und Verantwortlichkeit teilen wir die Post-Incident-Überprüfung für alle wichtigen Dienst Vorfälle mit betroffenen Kunden. Detaillierte Informationen finden Sie unter [Office 365 Security Incident Management](https://aka.ms/Office365SIM).

## <a name="assume-breach-methodology"></a>Annahme einer Verletzungs Methodik

Basierend auf einer detaillierten Analyse der Sicherheitstrends befürwortet und unterstreicht Microsoft die Notwendigkeit zusätzlicher Investitionen in reaktive Sicherheitsprozesse und-Technologien, die sich auf die Erkennung und Reaktion auf neue Bedrohungen konzentrieren und nicht nur auf die Vermeidung dieser Bedrohungen. Aufgrund von Änderungen an der Bedrohungslandschaft und der eingehenden Analyse hat Microsoft seine Sicherheitsstrategie weiterentwickelt, um Sicherheitsverletzungen nur zu verhindern, wenn es sich um eine besser ausgestattete Lösung für Verstöße handelt – eine Strategie, bei der wichtige Sicherheitsereignisse nicht als eine Frage, wenn, aber wann betrachtet werden.

Während die von Microsoft [angenommenen Verstöße](https://www.microsoft.com/TrustCenter/Security/default.aspx) in der Praxis seit vielen Jahren bestehen, erkennen viele Kunden nicht, welche Arbeit hinter den Kulissen unternommen wurde, um die Microsoft-Cloud zu verhärten. Angenommen, die Verletzung ist eine Denkweise, die Sicherheitsinvestitionen, Entwurfsentscheidungen und Betriebs Sicherheitsverfahren leitet. Angenommen, die Verletzung schränkt die Vertrauensstellung in Anwendungen, Dienste, Identitäten und Netzwerke ein, indem Sie Sie alle – intern und extern – als unsicher und bereits kompromittiert behandelt. Obwohl die Annahme einer Sicherheits Verletzungs Strategie nicht von einer tatsächlichen Verletzung von Microsoft Enterprise oder Cloud Services getragen wurde, wurde erkannt, dass viele Organisationen in der gesamten Branche trotz aller Versuche, dies zu verhindern, verletzt wurden. Während das verhindern von Sicherheitsverletzungen ein wichtiger Bestandteil der Vorgänge in einer Organisation ist, müssen diese Verfahren kontinuierlich getestet und erweitert werden, um moderne Gegner und Fortgeschrittene Bedrohungen effektiv zu bekämpfen. Damit sich eine Organisation auf einen Verstoß vorbereiten kann, müssen Sie zunächst robuste, wiederholbare und sorgfältig getestete Sicherheitsantwort Verfahren erstellen und aufrecht erhalten.

Während Sicherheitsprozesse, wie beispielsweise Bedrohungsmodellierung, Codeüberprüfungen und Sicherheitstests, im Rahmen des [Sicherheitsentwicklungszyklus](https://www.microsoft.com/securityengineering/sdl/)sehr nützlich sind, wird angenommen, dass ein Verstoß zahlreiche Vorteile bietet, die die allgemeine Sicherheit durch das ausüben und Messen von reaktiven Funktionen im Falle einer Verletzung unterstützen.

Bei Microsoft haben wir uns dazu durch fortlaufende Übungen im Kriegsspiel und Live-Website Durchdringungstests unserer Sicherheits Reaktionspläne mit dem Ziel durchgesetzt, unsere Erkennungs-und Reaktionsfähigkeit zu verbessern. Microsoft simuliert regelmäßige Verstöße gegen die reale Welt, führt eine kontinuierliche Sicherheitsüberwachung durch und praktiziert das Sicherheitsvorfall-Management, um die Sicherheit von Microsoft 365, Azure und anderen Microsoft Cloud-Diensten zu validieren und zu verbessern.

Microsoft führt die Sicherheitsstrategie "übernehmen" mit zwei Kerngruppen aus:
- Rote Teams (Angreifer)
- Blaue Teams (Verteidiger)

Sowohl Microsoft Azure-als auch Microsoft 365-Mitarbeiter trennen in Vollzeit rote Teams und blaue Teams.

Als "[rotes Teaming](https://go.microsoft.com/fwlink/?linkid=518599)" bezeichnet, besteht der Ansatz darin, Azure-und Microsoft 365-Systeme und-Vorgänge mit denselben Taktiken, Techniken und Verfahren wie echte Gegner gegen die Live-Produktionsinfrastruktur zu testen, ohne die Vorwissen der Engineering-oder Operations Teams. Dadurch werden die Sicherheits Erkennungs-und-Antwortfunktionen von Microsoft getestet, und es werden Produktions Schwachstellen, Konfigurationsfehler, ungültige Annahmen und andere Sicherheitsprobleme auf kontrollierte Weise ermittelt. Auf jede rote Team Verletzung folgt eine vollständige Offenlegung zwischen beiden Teams, um Lücken zu identifizieren, Ergebnisse zu beheben und die Verletzungs Reaktion zu verbessern.

**Hinweis**: beim Red-Teaming oder Live-Website Durchdringungstests werden keine Kundendaten absichtlich gezielt. Die Tests sind gegen Microsoft 365 und Azure-Infrastruktur und-Plattformen sowie die eigenen Mandanten, Anwendungen und Daten von Microsoft. Kundenmandanten, Anwendungen und Inhalte, die in Microsoft 365 oder Azure gehostet werden, werden nie gezielt.

## <a name="red-teams"></a>Rote Teams

Das Red-Team ist eine Gruppe von Vollzeitmitarbeitern in Microsoft, die sich auf die Verletzung der Infrastruktur von Microsoft, der Plattform und von Microsofts eigenen Mandanten und Anwendungen konzentrieren. Sie sind der dedizierte Widersacher (eine Gruppe von ethischen Hackern), der gezielte und anhaltende Angriffe auf Online Dienste ausführt (Microsoft-Infrastruktur, Plattformen und Anwendungen, aber keine Anwendungen oder Inhalte von Endkunden).

Die Rolle des roten Teams besteht darin, Umgebungen anzugreifen und durchdringen, indem Sie die gleichen Schritte wie ein Gegner ausführen:
 
![Bruch Stufen](../media/office-365-isolation-breach-stages.png)

Unter anderem versuchen rote Teams, die Isolations Grenzen für Mandanten zu verletzen, um Fehler oder Lücken in unserem Isolierungs Design zu finden.

## <a name="blue-teams"></a>Blaue Teams

Das Team Blue besteht entweder aus einer dedizierten Gruppe von Sicherheits beantwortern oder Mitgliedern aus der Sicherheitsvorfalls-Antwort-, Engineering-und Operations Organisation. Unabhängig von Ihrem Make-up sind Sie unabhängig und arbeiten separat vom roten Team. Das Team Blau folgt etablierten Sicherheitsprozessen und verwendet die neuesten Tools und Technologien zum erkennen und reagieren auf Angriffe und Durchdringung. Genau wie bei realen Angriffen weiß das Team blau nicht, wann oder wie die Angriffe des roten Teams auftreten oder welche Methoden verwendet werden können. Ihre Aufgabe, ob es sich um einen roten Team Angriff oder einen tatsächlichen Angriff handelt, besteht darin, alle Sicherheitsvorfälle zu erkennen und darauf zu reagieren. Aus diesem Grund ist das Team "blau" ständig auf Abruf und muss auf die gleiche Weise wie bei anderen Verstößen auf rote Team Verletzungen reagieren.

Wenn ein Gegner, beispielsweise ein rotes Team, eine Umgebung verletzt hat, muss das Team Blau:

- Sammeln von beweisen, die vom Gegner hinterlassen wurden
- Erkennen des Beweismaterials als Anhaltspunkt für einen Kompromiss
- Benachrichtigen der entsprechenden Teams für Technik und Betrieb
- Selektieren Sie die Warnungen, um festzustellen, ob Sie weitere Untersuchungen rechtfertigen.
- Zusammenfassen des Kontexts aus der Umgebung zum Umfang der Verletzung
- Behebungs Plan zum eindämmen oder Entfernen des Gegners bilden
- Ausführen des Korrektur Plans und Wiederherstellen nach einem Verstoß

Diese Schritte bilden die Antwort auf Sicherheitsvorfälle, die parallel zum Widersacher ausgeführt wird, wie unten dargestellt:
 
![Reaktionsphasen für Verstöße](../media/office-365-isolation-breach-response-stages.png)

Verstöße gegen das rote Team ermöglichen, dass die Fähigkeit des blauen Teams, End-to-End-Angriffe auf reale Angriffe zu erkennen und zu reagieren, ermöglicht wird. Am wichtigsten ist, dass es für geübte Sicherheitsvorfälle Antwort vor einer echten Verletzung ermöglicht. Außerdem erhöht das Blue-Team aufgrund von Red-Team Verletzungen sein Situationsbewusstsein, was bei zukünftigen Verstößen (ob aus dem roten Team oder einem anderen Gegner) wertvoll sein kann. Während des Erkennungs-und Antwort Prozesses erstellt das Blue-Teamaktionen für die Nachrichtenverarbeitung und erhält Einblick in die tatsächlichen Bedingungen der Umgebung (en), die Sie zu verteidigen versuchen. Dies geschieht häufig über Datenanalyse und Forensik, die von dem blauen Team ausgeführt werden, wenn Sie auf rote Team Angriffe reagieren und Bedrohungs Indikatoren wie Indikatoren für Kompromisse festlegen. Ähnlich wie das rote Team Lücken in der Sicherheitsgeschichte identifiziert, identifizieren blaue Teams Lücken in ihrer Fähigkeit zu erkennen und zu reagieren. Da die roten Teams auch reale Angriffe modellieren, kann das Blue-Team genau auf seine Fähigkeit oder Unfähigkeit hin geprüft werden, um mit festgestellten und hartnäckigen Gegnern zu kämpfen. Schließlich messen rote Team Verstöße sowohl die Bereitschaft als auch die Auswirkungen unserer Verletzungs Reaktion.
