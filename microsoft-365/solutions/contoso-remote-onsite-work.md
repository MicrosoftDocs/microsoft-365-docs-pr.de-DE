---
title: Contosos COVID-19-Antwort und -Unterstützung für Remote- und Vor-Ort-Arbeit
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
description: Verstehen Sie, wie die Contoso Corporation auf die COVID-19-Pandemie reagierte und ihre Softwareinstallations- und Updateinfrastruktur für Remote- und Vor-Ort-Arbeit entwickelt hat.
ms.openlocfilehash: 0bc7bc0e457b51e2f65337e355bcf9fced52274d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245444"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a>Contosos COVID-19-Antwort und -Unterstützung für Remote- und Vor-Ort-Arbeit

Contoso hatte seine Remotemitarbeiter immer unterstützt, die über einen zentralen VPN-Server in der Pariser Zentrale auf lokale Ressourcen zugegriffen haben. Contoso hatte allen Remotemitarbeitern einen verwalteten Laptop ausgestellt. Lokale Mitarbeiter hatten eine Mischung aus Desktopcomputern und Laptops.

## <a name="contosos-response-to-covid-19"></a>Contosos Antwort auf COVID-19

Mit Dem Beginn der COVID-19-Pandemie waren plötzlich alle, bis auf wesentliche Mitarbeiter, Remotemitarbeiter. Contoso reagierte, indem seine Mitarbeiter von zu Hause aus arbeiten und ihre primären Aktivitäten über den Remotezugriff auf lokale Ressourcen und online mithilfe von cloudbasierten Microsoft 365 durchführen.

Contoso hatte remote access-VPN-Server in der Pariser Zentrale, um die 25 % seiner bereits Remote-Mitarbeiter zu unterstützen, aber schnell verschoben, um die Remotezugriffskapazität zu skalieren, um 90 % der Mitarbeiter zu unterstützen. Contoso hat in jedem Satellitenbüro REMOTEzugriffs-VPN-Server bereitgestellt, sodass Remotemitarbeiter einen regional engen Einstiegspunkt für den Zugriff auf das Contoso-Intranet verwenden.

Contoso hat außerdem die Konfiguration von AUF Laptops, Tablets und Smartphones installierten VPN-Clients für geteiltes Tunneln aktualisiert, sodass datenverkehr für den Optimize-Satz von Office 365-Endpunkten die VPN-Verbindung umgangen und direkt über das Internet gesendet wurde. Weitere Informationen finden Sie unter [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).

Hier sehen Sie die resultierende Konfiguration mit VPN-Geräten, die in der Pariser Zentrale und in jedem der Satellitenbüros installiert sind. 

![Contosos VPN-Infrastruktur](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

Ein Remotemitarbeiter mit dem installierten VPN-Client verwendet DNS, um das regional nächstgelegene Büro zu finden und stellt eine Verbindung mit dem dort installierten VPN-Gerät ein. Bei geteilten Tunneln wird der Datenverkehr zu Microsoft 365 Optimize-Endpunkten direkt an den regional nächstgelegenen Microsoft 365 gesendet. Der ganze andere Datenverkehr wird über die VPN-Verbindung zum VPN-Gerät gesendet.

## <a name="contosos-support-for-remote-and-onsite-work"></a>Contosos Unterstützung für Remote- und Vor-Ort-Arbeit

Nachdem die anfänglichen Änderungen vorgenommen wurden, um hauptsächlich Remotemitarbeiter während regionaler Sperrungen zu unterstützen, hat Contoso Infrastrukturänderungen vorgenommen, um Remote- und Vor-Ort-Arbeit zu unterstützen, bei der es sich bei einem Mitarbeiter um:

- Immer remote.
- Immer vor Ort.
- Eine Kombination aus vor Ort und Remote.

Microsoft 365 Identitäts-, Sicherheits- und Compliancefeatures sind für Zero Trust konzipiert und funktionieren unabhängig vom Standort des Benutzers und des Geräts. Weitere Informationen finden Sie unter [Zero Trust](https://www.microsoft.com/security/business/zero-trust).

Die Verwaltung neuer Installationen und Updates von Software hängt jedoch vom Standort des Geräts ab, da die zu installierende Software von einer lokalen oder einer Internetquelle stammen könnte. Contoso-IT-Architekten haben ihre neue Installations- und Aktualisierungsinfrastruktur basierend auf dem Standort des Geräts und nicht nach dem Worker entworfen.

Sie haben zwei Arten von Geräten festgelegt: dedizierte lokale Geräte und Roaming.

### <a name="dedicated-on-premises"></a>Dedizierte lokales

Ein dediziertes lokales Gerät ist ein Desktop- oder Servercomputer, der das Contoso-Intranet nie verlässt und keinen VPN-Client installiert hat. Diese lokalen Geräte verwenden weiterhin Microsoft Endpoint Configuration Manager und die Verteilungspunkte für Installationen und Updates von Windows 10, Microsoft 365 Apps for Enterprise und dem Edgebrowser.

### <a name="roaming"></a>Roaming

Ein Roaminggerät kann das Contoso-Intranet verlassen und Laptops enthalten, die für viele Büromitarbeiter und alle Remotemitarbeiter und andere Geräte im Besitz der Organisation ausgestellt wurden, z. B. Smartphones und Tablets, auf dem der Contoso-VPN-Client installiert ist. 

Da diese Geräte jederzeit mit dem Internet verbunden werden können, verwenden sie Intune oder andere cloudbasierte Dienste für Installationen und Updates von Windows 10, Microsoft 365 Apps for Enterprise und Edge. Sie verwenden nicht die vorhandenen lokalen Configuration Manager-Verteilungspunkte.

Dies bedeutet, dass einige der Installationen und Updates für Roaminggeräte über das Internet erfolgen, während sie lokal und mit dem Intranet verbunden sind. Contoso-IT-Architekten haben jedoch entschieden, dass einfachheit der Konfiguration wichtiger ist als die Optimierung der Intranetbandbreite mit dem Internet, insbesondere dann, wenn die meisten Remotemitarbeiter nur selten mit dem Intranet verbunden sind.

Hier sehen Sie die resultierende Infrastruktur.

![Die Installations- und Aktualisierungsinfrastruktur von Contoso](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

Das Installations- und Updateverhalten wird bestimmt, indem die Computerkonten von Geräten Mitglied einer der folgenden Gruppen werden:

- OnPremDevices

  Der Configuration Manager-Client auf dem Gerät verwendet Verteilungspunkte für Installationen und Updates.

- RoamingDevices

  Intune und andere Einstellungen auf dem Gerät geben die Verwendung des Microsoft 365 für Installationen und Updates an.

## <a name="new-onboarding-process"></a>Neuer Onboardingprozess

Für ein neues dediziertes lokales Gerät, das einem neuen Mitarbeiter oder einem neuen Server in einem Rechenzentrum ausgestellt wurde, lädt der Configuration Manager-Client, der auf der Mitgliedschaft des Geräts in der OnPremDevices-Gruppe basiert, die neuesten Updates für Windows 10, Microsoft 365 Apps for Enterprise und Edge von lokalen Configuration Manager-Verteilungspunkten herunter und installiert sie. Nach Abschluss des Vorgangs ist das dedizierte lokale Gerät einsatzbereit und verwendet diese Verteilungspunkte für laufende Updates.

Bei einem neuen Remotegerät, das für einen neuen Mitarbeiter ausgestellt wurde, kontaktiert das Gerät, basierend auf seiner Mitgliedschaft in der Gruppe RoamingDevices, den Intune-Clouddienst und andere Dienste und lädt die neuesten Updates für Windows 10, Microsoft 365 Apps for Enterprise und Edge herunter und installiert sie. Nach Abschluss des Vorgangs ist das Remotegerät einsatzbereit und verwendet den installierten VPN-Client für den Zugriff auf lokale Ressourcen und das Microsoft 365 für laufende Updates.

## <a name="next-step"></a>Nächster Schritt

[Richten Sie Ihre Infrastruktur für Remotearbeit](empower-people-to-work-remotely.md) in Ihrer Organisation ein.
