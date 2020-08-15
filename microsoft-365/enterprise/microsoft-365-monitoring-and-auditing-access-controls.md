---
title: Microsoft 365 Überwachung und Überwachung von Zugriffssteuerungen
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
description: 'Zusammenfassung: eine Zusammenfassung der verschiedenen Überwachungs-und Überwachungs Zugriffssteuerungen, die in Microsoft 365 verfügbar sind.'
ms.openlocfilehash: f1302c4056bfd605e35aae08d8f5355f8d204db2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690611"
---
# <a name="monitoring-and-auditing-access-controls-in-microsoft-365"></a>Überwachen und Überwachen von Zugriffssteuerungen in Microsoft 365

Microsoft führt eine umfassende Überwachung und Überwachung aller Delegierungen, Berechtigungen und Vorgänge durch, die in Microsoft 365 ausgeführt werden. Microsoft 365 Zugriffssteuerung ist ein automatisierter Prozess, der auf dem Prinzip der geringsten Rechte basiert und Datenzugriffs Steuerelemente und-Überprüfungen integriert:

- Alle zulässigen Zugriffe können auf einen eindeutigen Benutzer zurückgeführt werden. Administratoren sind für die Verarbeitung von Kundeninhalten verantwortlich.
- Zugriffssteuerungsanforderungen, Genehmigungen und Administrative Operations Protokolle werden zur Analyse von Sicherheit und böswilligen Ereignissen erfasst.
- Zugriffsebenen werden basierend auf der Sicherheitsgruppenmitgliedschaft nahezu in Echtzeit überprüft, um sicherzustellen, dass nur Benutzer mit autorisierten geschäftlichen Begründungen und den Berechtigungsanforderungen Zugriff auf die Systeme haben.
- Microsoft 365, die Zugriffssteuerung und die unterstützenden Dienste, einschließlich Azure Active Directory und physische Rechenzentren, werden regelmäßig von unabhängigen Drittanbietern für die Einhaltung von [ISO/IEC 27001](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/TrustCenter/Compliance/SOC), [FedRAMP](https://www.microsoft.com/TrustCenter/Compliance/FedRAMP)und anderen [Standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)überwacht.
- Microsoft 365-Techniker müssen jährliche Sicherheitsschulungen durchführen, die bewährten Methoden für erhöhten Zugriff überprüfen und die Sicherheits-und Datenschutzrichtlinien von Microsoft anerkennen, um die Berechtigungen für den Dienst beizubehalten.

Automatische Warnungen werden ausgelöst, wenn verdächtige Aktivitäten erkannt werden, beispielsweise mehrere fehlgeschlagene Anmeldungen innerhalb eines kurzen Zeitraums. Das Microsoft 365-Sicherheitsantwort Team verwendet Maschinelles Lernen und eine große Datenanalyse, um Aktivitäten zu überprüfen und zu analysieren, nach unregelmäßigen Zugriffsmustern zu suchen und proaktiv auf anomale und unerlaubte Aktivitäten zu reagieren. Microsoft beschäftigt außerdem ein dediziertes Team von Penetrations Testern und engagiert sich in regelmäßigen roten Team-und blauen Teamübungen, um Sicherheits-und Zugriffssteuerungsprobleme im Dienst zu finden. Kunden können die Effektivität von Zugriffs Steuerungssystemen mithilfe von Überwachungsberichten und der von Microsoft 365 bereitgestellten Verwaltungs Aktivitäts-API überprüfen.

Weitere Informationen finden Sie unter [Office 365 Management Activity API Reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) and [Auditing and Reporting in Microsoft 365](microsoft-365-auditing-and-reporting-overview.md).
