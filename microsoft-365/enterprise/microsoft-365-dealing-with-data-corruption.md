---
title: Microsoft 365 Umgang mit Datenbeschädigung
ms.author: robmazz
author: robmazz
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
ms.custom: seo-marvel-apr2020
description: In diesem Artikel werden Datenbeschädigungen in Microsoft 365 und die von Microsoft unternommenen Anstrengungen zum verhindern und Wiederherstellen von Daten erläutert.
ms.openlocfilehash: 767be71bb08c49070488cc965165ac86e98836bd
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331872"
---
# <a name="dealing-with-data-corruption-in-microsoft-365"></a>Umgang mit Datenbeschädigung in Microsoft 365

Einer der Herausforderungen bei der Ausführung eines umfangreichen Cloud-Diensts besteht darin, dass angesichts der großen Datenmengen und unabhängigen Systeme Datenbeschädigungen umgangen werden. Die Beschädigung von Daten kann durch folgende Ursachen verursacht werden:

- Anwendungs-oder Infrastrukturfehler, die einen oder alle Anwendungszustände beschädigen
- Hardware Probleme, die zu Datenverlusten oder zum Lesen von Daten führen können
- Menschliche Betriebsfehler
- Böswillige Hacker und verärgerte Mitarbeiter
- Vorfälle in externen Diensten, die zu einem Datenverlust führen

Da höhere Ausfallsicherheit in der Datenintegrität weniger Daten Beschädigungs Vorfälle bedeutet, hat Microsoft in Microsoft 365-Schutzmechanismen integriert, um zu verhindern, dass eine Beschädigung stattfindet, sowie von Systemen und Prozessen, mit denen Daten bei Bedarf wiederhergestellt werden können. Checks and Processes sind in den verschiedenen Phasen des Engineering-Release-Prozesses vorhanden, um die Ausfallsicherheit bei Datenbeschädigung zu verbessern, einschließlich:

- System Design
- Code Organisation und-Struktur
- Code Überprüfung
- Komponententests, Integrationstests und Systemtests
- Trip Wires-Tests/Tore

In Microsoft 365-Produktionsumgebungen stellt die Peer Replikation zwischen Rechenzentren sicher, dass immer mehrere Live Kopien aller Daten vorhanden sind. Standard Bilder und-Skripts werden verwendet, um verloren gegangene Server wiederherzustellen, und replizierte Daten werden verwendet, um Kundendaten wiederherzustellen. Aufgrund der integrierten Überprüfungs-und Prozess Prozesse für die Datensicherheit unterhält Microsoft Sicherungen nur der Dokumentation zum Microsoft 365-Informationssystem (einschließlich sicherheitsbezogener Dokumentation) unter Verwendung der integrierten Replikation in SharePoint Online und unseres internen Code-Repository-Tools Source Depot. Die Systemdokumentation wird in SharePoint Online gespeichert, und das Quell Depot enthält System-und Anwendungsbilder. Sowohl SharePoint Online als auch das Quell Depot verwenden die Versionsverwaltung und werden nahezu in Echtzeit repliziert.
