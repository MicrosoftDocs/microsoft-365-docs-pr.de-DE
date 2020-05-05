---
title: 3. Bereitstellen der Endpunktverwaltung für Ihre Geräte, PCs und andere Endpunkte
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Verwenden Sie Microsoft Endpoint Manager zur Verwaltung Ihrer Geräte, PCs und anderen Endgeräte.
ms.openlocfilehash: 76e18d65865f4ec2bbc8a8d1554bb4cad6fee553
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011603"
---
# <a name="3-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>3. Bereitstellen der Endpunktverwaltung für Ihre Geräte, PCs und andere Endpunkte

Bei Remotemitarbeitern müssen Sie eine wachsende Anzahl von persönlichen Geräten unterstützen. Die Endpunktverwaltung ist ein richtlinienbasierter Sicherheitsansatz, bei dem Geräte bestimmte Kriterien erfüllen müssen, bevor sie Zugriff auf Ressourcen erhalten. Microsoft Endpoint Manager bietet einen modernen Arbeitsplatz und moderne Verwaltungsfunktionen, um Ihre Daten in der Cloud und vor Ort sicher zu halten. 

Endpoint Manager bietet Dienste und Tools für die Verwaltung von mobilen Geräten, Desktop-Computern, virtuellen Maschinen, eingebetteten Geräten und Servern durch die Kombination der folgenden Dienste, die Sie möglicherweise bereits kennen und nutzen.

## <a name="microsoft-intune"></a>Microsoft Intune

Intune soll Ihnen helfen, Daten zu schützen, wenn Sie die Geräte, die für den Zugriff auf Unternehmensdaten verwendet werden, nicht verwalten. Intune App-Schutzrichtlinien in Kombination mit Azure AD Conditional Access bieten granulare Kontrolle über Daten auf mobilen Geräten. Intune ermöglicht es Ihnen auch, umfassende Richtlinien zu definieren, die nur den richtigen Personen unter den richtigen Bedingungen den Zugriff auf Ihre Unternehmensdaten ermöglichen und sicherstellen, dass die Daten geschützt bleiben, indem kontrolliert wird, wie sie innerhalb von Office, Outlook und anderen mobilen Anwendungen verwendet werden.

Weitere Informationen finden Sie in dieser [Übersicht über Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager ist eine lokale Verwaltungslösung zur Verwaltung von Desktops, Servern und Laptops, die sich in Ihrem Netzwerk oder internetbasiert befinden. Sie können es für die Integration mit Intune, Azure AD, Microsoft Defender ATP und anderen Cloud-Diensten in der Cloud aktivieren. Verwenden Sie Configuration Manager zur Bereitstellung von Anwendungen, Software-Updates und Betriebssystemen. Sie können auch die Einhaltung von Vorschriften überwachen, Kunden in Echtzeit abfragen und auf sie einwirken und vieles mehr.

Weitere Informationen finden Sie in dieser [Übersicht über Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).

## <a name="co-management"></a>Co-Management

Co-Management kombiniert Ihre vorhandenen Investitionen in Configuration Manager vor Ort mit der Cloud unter Verwendung von Intune und anderen Microsoft 365 Cloud-Diensten. Sie wählen, ob Configuration Manager oder Intune die Verwaltungsautorität für die sieben verschiedenen Arbeitslastgruppen ist.

Als Teil von Endpoint Manager nutzt das Co-Management Cloud-Funktionen, einschließlich bedingtem Zugriff. Sie behalten einige Aufgaben lokal, während Sie andere Aufgaben mit Intune in der Cloud ausführen.

Weitere Informationen finden Sie in dieser [Übersicht über Co-Management](https://docs.microsoft.com/mem/configmgr/comanage/overview).

## <a name="desktop-analytics"></a>Desktop Analytics

Desktop Analytics ist ein Cloud-basierter Dienst, der in Configuration Manager integriert ist und Ihnen Einblicke und Informationen liefert, damit Sie fundierte Entscheidungen über Ihre Windows-Clients treffen können. Es kombiniert Daten aus Ihrem Unternehmen mit Daten, die aus Millionen von Geräten aggregiert wurden, die mit Microsoft Cloud Services verbunden sind. Mit Desktop Analytics können Sie ein Inventar der in Ihrem Unternehmen ausgeführten Anwendungen erstellen, die Kompatibilität von Anwendungen mit den neuesten Windows 10-Feature-Updates bewerten, Kompatibilitätsprobleme identifizieren und auf der Grundlage von Einblicken in Cloud-fähige Daten Vorschläge zur Risikominderung erhalten, Pilotgruppen erstellen, welche die gesamte Anwendungs- und Treiberkombination auf einem minimalen Satz von Geräten repräsentieren, und Windows 10 auf pilot- und produktionsverwalteten Geräten bereitstellen.

Weitere Informationen finden Sie in dieser [Übersicht über Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview).

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot ist eine Self-Service-Plattform für die Bereitstellung von Windows ohne manuelles Eingreifen. Es ist eine Sammlung von Technologien, mit denen neue Geräte eingerichtet und vorkonfiguriert werden, damit sie für die Nutzung in der Produktion bereit stehen. Sie können Windows Autopilot auch zum Zurücksetzen, Ändern des Zwecks und Wiederherstellen von Geräten verwenden. Diese Lösung versetzt eine IT-Abteilung in die Lage, das zuvor Genannte mithilfe einer geringen bis gar keiner zu verwaltenden Infrastruktur zu erzielen, und das über einen einfachen und schnellen Vorgang. Aus der Sicht des Benutzers sind nur ein paar einfache Vorgänge nötig, um sein Gerät einsatzbereit zu machen. Aus der Sicht der IT-Profis besteht die einzige Interaktion, die vom Endbenutzer verlangt wird, darin, sich mit einem Netzwerk zu verbinden und seine Anmeldeinformationen zu überprüfen.

Weitere Informationen finden Sie in dieser [Übersicht über Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).

## <a name="admin-technical-resources-for-endpoint-management"></a>Verwaltung technischer Ressourcen für die Endpunktverwaltung

- [Registrieren Sie verwaltete Geräte für die Sicherheit, nutzen Sie Anwendungseinstellungen für nicht verwaltete Geräte und verwenden Sie Geräte- und Anwendungsrichtlinien](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [Registrieren verschiedener Gerätetypen für die mobile Geräteverwaltung (MDM)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [Informieren Ihrer Endbenutzer über Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a>Ergebnisse von Schritt 3

Sie verwenden die Suite der Funktionen und Möglichkeiten von Endpoint Manager, um mobile Geräte, Desktop-Computer, virtuelle Maschinen, eingebettete Geräte und Server zu verwalten.

## <a name="next-step"></a>Nächster Schritt

Fahren Sie mit [Schritt 4](empower-people-to-work-remotely-teams-productivity-apps.md) fort, um den Remotezugriff auf lokale Apps und Dienste bereitzustellen.
