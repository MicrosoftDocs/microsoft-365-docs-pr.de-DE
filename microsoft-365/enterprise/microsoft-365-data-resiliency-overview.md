---
title: Datenresilienz in Microsoft 365
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
description: In diesem Artikel erfahren Sie mehr über den Entwurf und die Grundsätze der Datenausfall Sicherheit und-Wiederherstellung in Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e6ca643fe9842a71102fbabd3c05324ba52b70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690475"
---
# <a name="data-resiliency-in-microsoft-365"></a>Datenresilienz in Microsoft 365

In Anbetracht des komplexen Charakters von Cloud-Computing ist Microsoft sich bewusst, dass es sich nicht um einen Fall handelt, in dem die Dinge schief gehen, sondern eher wenn. Wir entwerfen unsere Cloud-Dienste, um die Zuverlässigkeit zu maximieren und die negativen Auswirkungen auf die Kunden zu minimieren, wenn es schief geht. Wir haben uns über die herkömmliche Strategie hinweggesetzt, sich auf komplexe physische Infrastrukturen zu verlassen, und wir haben Redundanz direkt in unsere Cloud-Dienste integriert. Wir verwenden eine Kombination aus weniger komplexer physischer Infrastruktur und intelligenter Software, die Datensicherheit in unseren Diensten aufbaut und hohe Verfügbarkeit für unsere Kunden bietet. 

## <a name="resiliency-and-recoverability-are-built-in"></a>Ausfallsicherheit und Wiederherstellbarkeit sind integriert 

Das Erstellen von Ausfallsicherheit und Wiederherstellung beginnt mit der Annahme, dass die zugrunde liegende Infrastruktur und die Prozesse zu einem bestimmten Zeitpunkt fehlschlagen: Hardware (Infrastruktur) schlägt fehl, der Mensch wird Fehler machen, und Software hat Bugs. Es wäre zwar falsch zu sagen, dass Softwareentwickler nicht über diese Dinge vor der Cloud nachdachten, wie diese Probleme in einer typischen IT-Implementierung behandelt wurden, war jedoch vor der Cloud sehr unterschiedlich:

- Zunächst waren Hardware-und Infrastruktur Schutz relevant. Dies bedeutet, dass Rechenzentren mit einer Zuverlässigkeit von 99,99% erhebliche Strom-und Netzwerkredundanz erforderlich machten und Server mit hardwarebasiertem Clustering, dualen Netzteilen, dualen Netzwerkschnittstellen und ähnlichem implementiert wurden. 
- Zweitens war Prozess von größter Bedeutung. Betriebsteams behielten strenge Verfahren, Wechsel Fenster wurden verwendet, und es gab häufig einen erheblichen Overhead im Projektmanagement. 
- Drittens erfolgte die Bereitstellung in einem Gletscher Tempo. Die Bereitstellung von Code ohne Besitz der Quelle bedeutete, auf Patch-Versionen zu warten, und Hauptversions Versionen betrafen Hardwareaustausch und erhebliche Investitionen. Darüber hinaus war das Zurücksetzen des Problems die einzige Möglichkeit, ein Problem zu beheben. Daher würden die meisten IT-Organisationen nur Hauptversionen bereitstellen, um zu verhindern, dass die Arbeit auf dem neuesten Stand ist. 
- Schließlich war die Skalierung der bereitgestellten Systeme sowie die Ebene ihrer Vernetzung historisch viel kleiner als jetzt. 

Kunden erwarten heute kontinuierliche Innovationen von Microsoft ohne Kompromisse bei der Qualität, und dies ist einer der Gründe, warum die Dienste und Software von Microsoft mit Flexibilität und Wiederherstellbarkeit entwickelt werden. 

## <a name="microsoft-365-data-resiliency-principles"></a>Microsoft 365-Prinzipien für Datensicherheit

Ausfallsicherheit bezieht sich auf die Möglichkeit, dass ein Cloud-basierter Dienst bestimmten Arten von Fehlern Stand halten kann und dennoch aus Sicht der Kunden voll funktionsfähig bleibt. Datenausfall Sicherheit bedeutet, dass wichtige Kundendaten unabhängig von den auftretenden Fehlern in Microsoft 365 intakt bleiben und nicht betroffen sind. Zu diesem Zweck wurden Microsoft 365-Dienste um fünf spezifische Ausfall Sicherheitsprinzipien entwickelt:

- Es gibt wichtige und nicht kritische Daten. Nicht kritische Daten (beispielsweise, ob eine Nachricht gelesen wurde) können in Szenarien mit seltenen Fehlern gelöscht werden. Wichtige Daten (beispielsweise Kundendaten wie e-Mail-Nachrichten) sollten unter extremen Kosten geschützt werden. Als Entwurfsziel sind zugestellte e-Mail-Nachrichten immer kritisch und Dinge wie, ob eine Nachricht gelesen wurde, sind nicht kritisch. 
- Kopien von Kundendaten müssen in unterschiedliche Fehler Zonen oder so viele fehlerdomänen wie möglich aufgeteilt werden (beispielsweise Rechenzentren, zugänglich für einzelne Anmeldeinformationen (Prozess, Server oder Operator)), um die Ausfall Isolierung bereitzustellen. 
- Kritische Kundendaten müssen auf fehlerhafte Teile von Atomarität, Konsistenz, Isolierung, Lebensdauer (ACID) überwacht werden. 
- Kundendaten müssen vor Beschädigung geschützt sein. Es muss aktiv gescannt oder überwacht, repariert und wiederhergestellt werden. 
- Die meisten Datenverluste resultieren aus Kundenaktionen, sodass Kunden sich selbst über eine GUI erholen können, mit der Sie versehentlich gelöschte Elemente wiederherstellen können. 
 
Durch den Aufbau unserer Cloud-Dienste für diese Prinzipien, gepaart mit robustem testen und Validierung, kann Microsoft 365 die Anforderungen von Kunden erfüllen und übertreffen und gleichzeitig eine Plattform für kontinuierliche Innovationen und Verbesserungen sicherstellen. 

## <a name="related-links"></a>Links zu verwandten Themen

- [Umgang mit Datenbeschädigung](microsoft-365-dealing-with-data-corruption.md)
- [Schutz vor Schadsoftware und Ransomware](microsoft-365-malware-and-ransomware-protection.md)
- [Überwachung und Selbstreparatur](microsoft-365-monitoring-and-self-healing.md)
- [Exchange-Datenausfall Sicherheit](microsoft-365-exchange-data-resiliency.md)
