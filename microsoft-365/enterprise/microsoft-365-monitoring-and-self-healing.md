---
title: Microsoft 365 – Überwachung und Selbstreparatur
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
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie mehr über die Überwachung und die Selbstheilungsfunktionen von Microsoft 365.
ms.openlocfilehash: 459fdb50577c255d3cf27a31dbbbdd5768392c44
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690853"
---
# <a name="microsoft-365-monitoring-and-self-healing"></a>Microsoft 365 – Überwachung und Selbstreparatur

Angesichts der Größenordnung von Microsoft 365 wäre es nicht möglich, Kundendaten widerstandsfähig und sicher vor Schadsoftware zu halten, ohne integrierte Überwachung, die intelligent ist und die Selbstheilung schnell und zuverlässig ist. Das Überwachen einer Reihe von Diensten in der Größenordnung von Microsoft 365 ist eine große Herausforderung. Neue Denkweise und Methodologien müssen eingeführt werden, und es müssen ganz neue Technologiegruppen erstellt werden, um den Dienst in einer verbundenen globalen Umgebung zu betreiben und zu verwalten. Wir haben uns vom herkömmlichen Überwachungsansatz der Datensammlung und-Filterung abgewandt, um Warnungen für einen Ansatz zu erstellen, der auf der Datenanalyse basiert. Signale annehmen und Vertrauen in diese Daten setzen und dann Automatisierung verwenden, um das Problem wiederherzustellen oder zu beheben. Dieser Ansatz hilft, Menschen aus der Wiederherstellungs Gleichung herausauszufiltern, was wiederum den Betrieb weniger kostspielig, schneller und weniger fehleranfällig macht. 

Grundlegend für die Microsoft 365-Überwachung ist eine Sammlung von Technologien, die aus unserem Data Insights-Modul besteht, das auf Azure-, SQL Azure-und [Open-Source-Streaming-Datenbanktechnologie](https://cassandra.apache.org/)basiert. Es dient zum Sammeln und Aggregieren von Daten sowie zum Erreichen von Schlussfolgerungen. Derzeit werden mehr als 500 Millionen Ereignisse pro Stunde von mehr als 100.000 Servern (~ 15 TB pro Tag) auf Dutzende von Rechenzentren in vielen Regionen verteilt, und diese Zahlen wachsen. 

Microsoft 365 verwendet *outside-in-Überwachung*, die das Erstellen synthetischer Transaktionen umfasst, um alles zu testen, was wichtig ist. Beispielsweise testet jedes Szenario in Exchange Online jeder Datenbank alle fünf Minuten auf eine verteilte Art und Weise und bietet nahezu eine kontinuierliche Abdeckung aller Elemente, die im System Leben. Von mehreren Standorten aus werden 250 Millionen Testtransaktionen pro Tag durchgeführt, um eine stabile Basislinie oder einen Takt für den Dienst zu erstellen. 

Microsoft 365 verwendet auch das Konzept der *roten Warnung*, das alle Überwachungssignale von allen Computern in unseren Rechenzentren auf etwas reduziert, das von einem Menschen verwaltet werden kann. Das Konzept ist ganz einfach: Wenn etwas über mehrere Signale geschieht, muss etwas passieren. Es geht nicht darum, Vertrauen in ein Signal zu schaffen, sondern darum, für jedes Signal eine angemessene Treue zu haben, damit Sie eine höhere Genauigkeit erhalten. Dieses Überwachungssystem ist so leistungsfähig, dass wir keine 24X7-Mitarbeiter haben, die unsere Monitore beobachten; alles, was wir haben, ist die Maschinerie, die aufwacht, wenn Sie ein Problem erkennt, in diesem Fall wird das entsprechende Personal auf dem Anrufseite, oder öfters, wie es der Fall ist, wird es einfach weiter gehen und das Problem lösen. Sobald wir mit dem Sammeln von Signalen beginnen und rote Warnungen abgeschaltet haben, können wir mit der Triangulation für alle unsere Dienst Partitionen beginnen. 

Basierend auf der Kombination aus der Fehlermeldung und den roten Warnungen gibt diese Warnung an, welche Komponenten ein Problem aufweisen könnten und dass das System versuchen wird, das Problem selbst zu beheben, indem ein Postfachserver neu gestartet wird. 

Zusätzlich zu den Selbstheilungsfunktionen wie der Wiederherstellung einzelner Seiten umfasst Exchange Online mehrere Features, die einen Ansatz zur Überwachung und Selbstheilung, die sich auf die Beibehaltung der Endbenutzeroberfläche konzentrieren. Diese Features umfassen die *verwaltete Verfügbarkeit*, die integrierte Überwachungs-und Wiederherstellungsaktionen bereitstellt, sowie AutoReseed, die die Datenbankredundanz nach einem Datenträgerausfall automatisch wieder herstellt. 

## <a name="managed-availability"></a>Verwaltete Verfügbarkeit 

Die verwaltete Verfügbarkeit bietet eine systemeigene Integritätsprüfung und-Wiederherstellungslösung, die die Benutzererfahrung durch Wiederherstellungs orientierte Aktionen überwacht und schützt. Die verwaltete Verfügbarkeit ist die Integration integrierter Überwachungs-und Wiederherstellungsaktionen mit der Exchange-Plattform für hohe Verfügbarkeit. Sie ist dafür vorgesehen, vom System erkannte Probleme sofort zu ermitteln und zu beheben. Im Gegensatz zu früheren externen Überwachungslösungen und -techniken für Exchange versucht die verwaltete Verfügbarkeit nicht, die eigentliche Ursache eines Problems zu ermitteln oder zu kommunizieren. Stattdessen konzentrieren Sie sich auf Wiederherstellungs Aspekte, die drei wichtige Bereiche der Endbenutzererfahrung behandeln:

- **Verfügbarkeit** – können Benutzer auf den Dienst zugreifen? 
- **Latenz** – wie ist die Benutzeroberfläche für Benutzer? 
- **Fehler** – können Benutzer erreichen, was Sie wünschen? 

Die verwaltete Verfügbarkeit ist ein internes Feature, das auf jedem Microsoft 365-Server mit Exchange Online ausgeführt wird. Dabei werden in jeder Sekunde Hunderte von Integritätsmetriken abgerufen. Wenn ein Fehler festgestellt wird, wird die meiste Zeit automatisch behoben. Es gibt jedoch immer Probleme, dass die verwaltete Verfügbarkeit nicht eigenständig behoben werden kann. In diesen Fällen eskaliert die verwaltete Verfügbarkeit das Problem mithilfe der Ereignisprotokollierung an ein Microsoft 365-Support Team.

## <a name="autoreseed"></a>AutoReseed

Exchange Online Server werden in einer Konfiguration bereitgestellt, in der mehrere Datenbanken und deren Protokolldatenströme auf demselben nicht-RAID-Datenträger gespeichert werden. Diese Konfiguration wird häufig *nur als ein Haufen von Datenträgern* (JBOD) bezeichnet, da keine Speicherredundanz Mechanismen wie RAID verwendet werden, um die Daten auf dem Datenträger zu duplizieren. Wenn ein Datenträger in einer JBOD-Umgebung fehlschlägt, gehen die Daten auf diesem Datenträger verloren. 

In Anbetracht der Größe von Exchange Online und der Tatsache, dass darin bereitgestellt werden, sind Millionen von Laufwerken, Festplatten-Fehler sind ein reguläres Ereignis in Exchange Online. Tatsächlich Scheitern mehr als 100 täglich. Wenn ein Datenträger in einer lokalen Unternehmensbereitstellung fehlschlägt, muss ein Administrator den ausgefallenen Datenträger manuell ersetzen und die betroffenen Daten wiederherstellen. In einer Cloud-Bereitstellung ist die Größe von Microsoft 365, wenn Operatoren (Cloud-Administratoren) manuell Datenträger ersetzen, weder praktisch noch wirtschaftlich machbar. 

Automatisches erneutes Seeding oder *AutoReseed*ist ein Feature, das die normalerweise vom Operator abhängige Aktion als Reaktion auf einen Datenträgerfehler, ein Daten Bank Beschädigungs Ereignis oder ein anderes Problem ersetzt, das ein erneutes Seeding einer Datenbankkopie erfordert. AutoReseed wurde entwickelt, um die Datenbankredundanz nach einem Datenträgerausfall mithilfe von Ersatz Datenträgern, die im System bereitgestellt wurden, automatisch wiederherzustellen. Wenn ein Datenträger ausfällt, werden die auf diesem Datenträger gespeicherten Datenbankkopien automatisch auf einen vorkonfigurierten Ersatzdatenträger auf dem Server umgestellt, wodurch die Redundanz wiederhergestellt wird. 