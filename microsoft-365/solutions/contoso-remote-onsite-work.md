---
title: Antwort und Unterstützung von Contoso COVID-19 für Hybridarbeit
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erfahren Sie, wie die Contoso Corporation auf die COVID-19-Pandemie reagiert und ihre Softwareinstallations- und Updateinfrastruktur für hybride Arbeit entwickelt hat.
ms.openlocfilehash: 2d28b0513221f6c14526baba69bf0f5986154805
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788379"
---
# <a name="contosos-covid-19-response-and-support-for-hybrid-work"></a>Antwort und Unterstützung von Contoso COVID-19 für Hybridarbeit

Contoso hatte seine Remotemitarbeiter immer unterstützt, die über einen zentralen VPN-Server in der Zentrale von Paris auf lokale Ressourcen zugegriffen haben. Contoso hatte allen Remotemitarbeitern einen verwalteten Laptop ausgestellt. Lokale Mitarbeiter hatten eine Mischung aus Desktopcomputern und Laptops.

## <a name="contosos-response-to-covid-19"></a>Antwort von Contoso auf COVID-19

Mit dem Beginn der COVID-19-Pandemie waren plötzlich alle, aber wesentliche Mitarbeiter Remotemitarbeiter. Contoso reagierte, indem es seine Mitarbeiter zur Arbeit von zu Hause aus verlagern und seine primären Aktivitäten durch Remotezugriff auf lokale Ressourcen und online mit Microsoft 365 Clouddiensten durchführte.

Contoso verfügte über VPN-Server mit Remotezugriff in der Zentrale in Paris, um die 25 % seiner bereits remote-Mitarbeiter zu unterstützen, wurde jedoch schnell verschoben, um die Remotezugriffskapazität zu erhöhen, um 90 % seiner Mitarbeiter zu unterstützen. Contoso hat in jedem Satellitenbüro VPN-Server für den Remotezugriff bereitgestellt, sodass Remotemitarbeiter einen regional geschlossenen Einstiegspunkt für den Zugriff auf das Contoso-Intranet verwenden würden.

Contoso hat außerdem die Konfiguration von VPN-Clients aktualisiert, die auf Laptops, Tablets und Smartphones für geteilte Tunnel installiert sind, sodass der Datenverkehr für die Gruppe "Optimieren" von Office 365 Endpunkten die VPN-Verbindung umgeht und direkt über das Internet gesendet wurde. Weitere Informationen finden Sie unter [Optimieren Office 365 Konnektivität für Remotebenutzer mithilfe des geteilten VPN-Tunnels.](../enterprise/microsoft-365-vpn-split-tunnel.md)

Hier sehen Sie die resultierende Konfiguration mit VPN-Geräten, die in der Zentrale von Paris und in jedem der Satellitenstandorte installiert sind. 

![CONTOSO-VPN-Infrastruktur](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

Ein Remotemitarbeiter mit dem installierten VPN-Client verwendet DNS, um das regional nächstgelegene Büro zu finden, und stellt eine Verbindung mit dem dort installierten VPN-Gerät her. Bei geteilten Tunneln wird Datenverkehr an Microsoft 365 Optimize-Endpunkte direkt an den regional nächstgelegenen Microsoft 365 Netzwerkstandort gesendet. Der gesamte andere Datenverkehr wird über die VPN-Verbindung an das VPN-Gerät gesendet.

## <a name="contosos-support-for-hybrid-work"></a>Contoso-Unterstützung für Hybridarbeit

Nachdem die ersten Änderungen vorgenommen wurden, um hauptsächlich Remotemitarbeiter während der regionalen Sperrzeiten zu unterstützen, hat Contoso Infrastrukturänderungen vorgenommen, um Hybridarbeit zu unterstützen, bei der ein Mitarbeiter folgendermaßen arbeiten könnte:

- Immer remote.
- Immer vor Ort.
- Eine Kombination aus vor Ort und Remote.

Microsoft 365 Identitäts-, Sicherheits- und Compliancefeatures sind auf Zero Trust ausgelegt und können unabhängig vom Standort des Benutzers und seines Geräts verwendet werden. Weitere Informationen finden Sie unter [Zero Trust](https://www.microsoft.com/security/business/zero-trust).

Die Verwaltung neuer Installationen und Softwareupdates hängt jedoch vom Standort des Geräts ab, da die zu installierende Software von einer lokalen oder einer Internetquelle stammen kann. It-Architekten von Contoso haben ihre neuen Installationen und Updates für die Infrastruktur basierend auf dem Standort des Geräts und nicht dem Mitarbeiter entworfen.

Sie haben zwei Arten von Geräten festgelegt: dedizierte lokale Geräte und Roaming.

### <a name="dedicated-on-premises"></a>Dedizierte lokale Bereitstellung

Ein dediziertes lokales Gerät ist ein Desktop- oder Servercomputer, der niemals das Contoso-Intranet verlässt und keinen VPN-Client installiert hat. Diese lokalen Geräte verwenden weiterhin Microsoft Endpoint Configuration Manager und ihre Verteilungspunkte für Installationen und Updates von Windows 10, Microsoft 365 Apps for Enterprise und dem Edgebrowser.

### <a name="roaming"></a>Roaming

Ein Roaminggerät kann das Contoso-Intranet verlassen und umfasst Laptops, die für viele Büroangestellte und alle Remotemitarbeiter und andere Unternehmensgeräte wie Smartphones und Tablets mit installierten Contoso-VPN-Clients ausgestellt wurden. 

Da diese Geräte jederzeit mit dem Internet verbunden werden können, verwenden sie Intune oder andere cloudbasierte Dienste für Installationen und Updates von Windows 10, Microsoft 365 Apps for Enterprise und Edge. Sie verwenden nicht die vorhandenen lokalen Configuration Manager-Verteilungspunkte.

Dies bedeutet, dass einige der Installationen und Updates für Roaminggeräte über das Internet erfolgen, während sie lokal und mit dem Intranet verbunden sind. It-Architekten von Contoso haben jedoch entschieden, dass die Einfachheit der Konfiguration wichtiger ist als die Optimierung der Intranetbandbreite für das Internet, insbesondere, wenn die meisten Remotemitarbeiter selten mit dem Intranet verbunden sind.

Hier sehen Sie die resultierende Infrastruktur.

![Contosos Infrastruktur für Installationen und Updates](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

Das Installations- und Updateverhalten wird bestimmt, indem die Computerkonten von Geräten zu einem Mitglied einer der folgenden Gruppen werden:

- OnPremDevices

  Der Configuration Manager-Client auf dem Gerät verwendet Verteilungspunkte für Installationen und Updates.

- RoamingDevices

  Intune und andere Einstellungen auf dem Gerät geben die Verwendung des Microsoft 365-Netzwerks für Installationen und Updates an.

## <a name="new-onboarding-process"></a>Neuer Onboardingprozess

Bei einem neuen dedizierten lokalen Gerät, das für einen neuen Mitarbeiter oder für einen neuen Server in einem Rechenzentrum ausgestellt wurde, lädt der Configuration Manager-Client basierend auf der Mitgliedschaft des Geräts in der OnPremDevices-Gruppe die neuesten Updates für Windows 10, Microsoft 365 Apps for Enterprise und Edge von lokalen Configuration Manager-Verteilungspunkten herunter und installiert diese. Nach Abschluss des Vorgangs ist das dedizierte lokale Gerät einsatzbereit und verwendet diese Verteilungspunkte für laufende Updates.

Bei einem neuen Remotegerät, das einem neuen Mitarbeiter ausgestellt wurde, kontaktiert das Gerät, wenn er sich anmeldet, basierend auf seiner Mitgliedschaft in der RoamingDevices-Gruppe den Intune-Clouddienst und andere Dienste und lädt die neuesten Updates für Windows 10, Microsoft 365 Apps for Enterprise und Edge herunter und installiert sie. Nach Abschluss des Vorgangs ist das Remotegerät einsatzbereit und verwendet den installierten VPN-Client für den Zugriff auf lokale Ressourcen und das Microsoft 365-Netzwerk für laufende Updates.

## <a name="next-step"></a>Nächster Schritt

[Richten Sie Ihre Infrastruktur für hybride Arbeit](empower-people-to-work-remotely.md) in Ihrer Organisation ein.
