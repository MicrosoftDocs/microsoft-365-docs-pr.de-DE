---
title: Onboarding-Tools und -Methoden für Windows 10-Computer
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Onboarding Windows 10-Geräten, damit sie Sensordaten an die Microsoft 365 Senden von Compliancelösungen senden können
ms.openlocfilehash: 7cbadc343c5cee1aa7704bcb9da8be2a152726ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917851"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Onboarding-Tools und -Methoden für Windows 10-Computer

**Gilt für:**
- [Microsoft 365 Verhinderung von Endpunktdatenverlusten (Endpoint Data Loss Prevention, DLP)](./endpoint-dlp-learn-about.md)

Geräte in Ihrer Organisation müssen so konfiguriert sein, dass Microsoft 365 Endpoint Data Loss Prevention Service Sensordaten von ihnen erhalten kann. Es gibt verschiedene Methoden und Bereitstellungstools, die Sie zum Konfigurieren der Geräte in Ihrer Organisation verwenden können.

Die folgenden Bereitstellungstools und -methoden werden unterstützt:

- Gruppenrichtlinie
- Microsoft Endpoint Configuration Manager
- Verwaltung mobiler Geräte (einschließlich Microsoft Intune)
- lokales Skript

## <a name="in-this-section"></a>Inhalt dieses Abschnitts
Thema | Beschreibung
:---|:---
[Onboarding Windows 10 Geräte mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md) | Verwenden Sie Gruppenrichtlinien zum Bereitstellen des Konfigurationspakets auf Geräten.
[Onboarding Windows Geräte mithilfe Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md) | Sie können entweder Microsoft Endpoint Configuration Manager (aktuelle Verzweigung) Version 1606 oder Microsoft Endpoint Configuration Manager (current branch) version 1602 oder früher verwenden, um das Konfigurationspaket auf Geräten zu bereitstellen.
[Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](dlp-configure-endpoints-mdm.md) | Verwenden Sie Tools für die mobile Geräteverwaltung oder Microsoft Intune, um das Konfigurationspaket auf dem Gerät zu bereitstellen.
[Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](dlp-configure-endpoints-script.md) | Erfahren Sie, wie Sie das lokale Skript zum Bereitstellen des Konfigurationspakets auf Endpunkten verwenden.
[Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](dlp-configure-endpoints-vdi.md) | Erfahren Sie, wie Sie das Konfigurationspaket zum Konfigurieren von VDI-Geräten verwenden.