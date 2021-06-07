---
title: Schritt 4. Bereitstellen der Endpunktverwaltung für Ihre Geräte, PCs und andere Endpunkte
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Verwenden Sie Microsoft Endpoint Manager zur Verwaltung Ihrer Geräte, PCs und anderen Endgeräte.
ms.openlocfilehash: ef43f447b819a6e5d9d0de1d979d7d30887e30fb
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789105"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>Schritt 4. Bereitstellen der Endpunktverwaltung für Ihre Geräte, PCs und andere Endpunkte

Bei Hybrid-Mitarbeitern müssen Sie eine wachsende Anzahl von persönlichen Geräten unterstützen. Die Endpunktverwaltung ist ein richtlinienbasierter Sicherheitsansatz, bei dem Geräte bestimmte Kriterien erfüllen müssen, bevor sie Zugriff auf Ressourcen erhalten. Microsoft Endpoint Manager bietet moderne Verwaltungsfunktionen, um Ihre Daten in der Cloud und vor Ort sicher zu halten. 

[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) bietet Dienste und Tools für die Verwaltung von mobilen Geräten, Desktop-Computern, virtuellen Maschinen, eingebetteten Geräten und Servern durch die Kombination der folgenden Dienste, die Sie möglicherweise bereits kennen und nutzen.

![Die Komponenten der Endpunktverwaltung für Microsoft 365](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intune ist ein Cloud-basierter Dienst, der sich auf die Verwaltung mobiler Geräte (MDM) und die mobile Anwendungsverwaltung (MAM) bezieht und ein Bestandteil von Microsoft 365 ist. 

- **MDM:** Sie können über Geräte im Besitz der Organisation die vollständige Kontrolle ausüben, einschließlich der Einstellungen, Features und Sicherheit. Geräte werden in Intune "registriert", wo Sie Intune-Richtlinien mit Regeln und Einstellungen erhalten. Sie können z. b. die Anforderungen für Kennwort und PIN festlegen, eine VPN-Verbindung erstellen, den Bedrohungsschutz einrichten und vieles mehr.

- **MAM:** Remotemitarbeiter möchten möglicherweise nicht, dass Sie die vollständige Kontrolle über ihre persönlichen Geräte haben, auch bekannt als BYOD-Geräte (Bring-your-own Device). Sie können Ihren Hybrid-Mitarbeiter Optionen anbieten und Ihre Organisation trotzdem schützen. So können beispielsweise Hybrid-Mitarbeiter Ihre Geräte registrieren, wenn Sie Vollzugriff auf die Ressourcen Ihrer Organisation wünschen. Wenn diese Benutzer jedoch nur Zugriff auf E-Mail oder Microsoft Teams haben möchten, verwenden Sie die APP-Schutzrichtlinien, bei denen die mehrstufige Authentifizierung (MFA) erforderlich ist, um diese Apps zu verwenden.

Weitere Informationen finden Sie in dieser [Übersicht über Microsoft Intune](/intune/fundamentals/what-is-intune).

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager ist eine lokale Verwaltungslösung zur Verwaltung von Desktops, Servern und Laptops, die sich in Ihrem Netzwerk oder internetbasiert befinden. Verwenden Sie Configuration Manager zur Bereitstellung von Anwendungen, Software-Updates und Betriebssystemen. Sie können auch die Einhaltung von Vorschriften überwachen, Kunden in Echtzeit abfragen und auf sie einwirken und vieles mehr. Sie können es für die Integration mit Intune, Azure AD, Microsoft Defender für Endpunkt und anderen Cloud-Diensten in der Cloud aktivieren. 

Weitere Informationen finden Sie in dieser [Übersicht über Configuration Manager](/mem/configmgr/core/understand/introduction).

## <a name="co-management"></a>Co-Management

Co-Management kombiniert Ihre vorhandenen Investitionen in Configuration Manager vor Ort mit der Cloud unter Verwendung von Intune und anderen Microsoft 365 Cloud-Diensten. Sie wählen, ob Configuration Manager oder Intune die Verwaltungsautorität für verschiedenen Arbeitslasten ist. 

Das Co-Management verwendet Intune-basierte Cloud-Funktionen, einschließlich bedingtem Zugriff und erzwingen der Gerätekompatibilität. Sie behalten einige Aufgaben lokal, während Sie andere Aufgaben in der Cloud ausführen.

Weitere Informationen finden Sie in dieser [Übersicht über Co-Management](/mem/configmgr/comanage/overview).

## <a name="desktop-analytics"></a>Desktop Analytics

Desktop Analytics ist ein Cloud-basierter Dienst, der in Configuration Manager integriert ist und Ihnen Einblicke und Informationen liefert, damit Sie fundierte Entscheidungen über Ihre Windows-Clients treffen können. Es kombiniert Daten aus Ihrem Unternehmen mit Daten, die aus Millionen von anderen Geräten aggregiert wurden, die mit Microsoft Cloud Services verbunden sind. 

Mithilfe von Desktop Analytics können Sie:

- ein Inventar der in Ihrem Unternehmen ausgeführten Anwendungen erstellen.
- die Kompatibilität von Anwendungen mit den neuesten Windows 10-Feature-Updates bewerten.
- Kompatibilitätsprobleme identifizieren und auf der Grundlage von Einblicken in Cloud-fähige Daten Vorschläge zur Risikominderung erhalten.
- Pilotgruppen erstellen, welche die gesamte Anwendungs- und Treiberkombination auf einem minimalen Satz von Geräten repräsentieren.
- Windows 10 auf pilot- und produktionsverwalteten Geräten bereitstellen.

Weitere Informationen finden Sie in dieser [Übersicht über Desktop Analytics](/mem/configmgr/desktop-analytics/overview).

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot ist eine Self-Service-Plattform für die Bereitstellung von Windows ohne manuelles Eingreifen. Es ist eine Sammlung von Technologien, mit denen Sie neue Geräte eingerichtet und vorkonfiguriert können, damit sie für die Nutzung in der Produktion bereit stehen. Sie können Windows Autopilot auch zum Zurücksetzen, Ändern des Zwecks und Wiederherstellen von Geräten verwenden. 

Windows Autopilot versetzt eine IT-Abteilung in die Lage, Geräte mithilfe einer geringen bis gar keiner zu verwaltenden Infrastruktur vorzukonfigurieren, und das über einen einfachen und schnellen Vorgang. 

- Aus der Sicht des Benutzers sind nur ein paar einfache Vorgänge nötig, um sein Gerät einsatzbereit zu machen. 
- Aus der Sicht der IT-Profis besteht die einzige Interaktion, die vom Endbenutzer verlangt wird, darin, sich mit einem Netzwerk zu verbinden und seine Anmeldeinformationen zu überprüfen.

Weitere Informationen finden Sie in dieser [Übersicht über Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot).

## <a name="admin-technical-resources-for-endpoint-management"></a>Verwaltung technischer Ressourcen für die Endpunktverwaltung

- [Roadmap für die Verwaltung mobiler Geräte für Microsoft 365](../enterprise/device-management-roadmap-microsoft-365.md)
- [Registrieren verschiedener Gerätetypen für die mobile Geräteverwaltung](/mem/intune/enrollment/device-enrollment)
- [Informieren Ihrer Endbenutzer über Microsoft Intune](/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-4"></a>Ergebnisse von Schritt 4

Sie verwenden die Suite der Funktionen und Möglichkeiten von Endpoint Manager, um mobile Geräte, Desktop-Computer, virtuelle Maschinen, eingebettete Geräte und Server zu verwalten.

## <a name="next-step"></a>Nächster Schritt

[![Schritt 5: Bereitstellen von Produktivitätsanwendungen und -diensten für Remotemitarbeiter](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)

Fahren Sie mit [Schritt 5](empower-people-to-work-remotely-teams-productivity-apps.md) fort, um Ihre Hybrid-Mitarbeiter mit Microsoft 365 Produktivitäts-Apps wie Microsoft Teams auszustatten.