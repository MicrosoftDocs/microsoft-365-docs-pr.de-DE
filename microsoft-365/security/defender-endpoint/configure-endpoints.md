---
title: Onboarding-Tools und -Methoden für Windows 10-Computer
description: Onboarding von Windows 10-Geräten, damit sie Sensordaten an den Microsoft Defender ATP-Sensor senden können
keywords: Onboarding von Windows 10-Geräten, Gruppenrichtlinie, Endpunktkonfigurations-Manager, Verwaltung mobiler Geräte, lokales Skript, gp, sccm, mdm, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 77b843f9526d8b100845403bc8d2df4bf3259471
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760212"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Onboarding-Tools und -Methoden für Windows 10-Computer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft 365 Endpoint Data Loss Prevention (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Microsoft 365 Insider Risk Management](/microsoft-365/compliance/insider-risk-management)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Geräte in Ihrer Organisation müssen so konfiguriert werden, dass der Defender for Endpoint-Dienst Sensordaten von ihnen erhalten kann. Es gibt verschiedene Methoden und Bereitstellungstools, die Sie zum Konfigurieren der Geräte in Ihrer Organisation verwenden können.

Die folgenden Bereitstellungstools und -methoden werden unterstützt:

- Gruppenrichtlinien
- Microsoft Endpoint Configuration Manager
- Verwaltung mobiler Geräte (einschließlich Microsoft Intune)
- Lokales Skript

## <a name="in-this-section"></a>Inhalt dieses Abschnitts
Thema | Beschreibung
:---|:---
[Onboarding von Windows 10-Geräten mithilfe von Gruppenrichtlinien](configure-endpoints-gp.md) | Verwenden Sie Gruppenrichtlinien zum Bereitstellen des Konfigurationspakets auf Geräten.
[Onboarding von Windows-Geräten mit Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) | Sie können entweder Microsoft Endpoint Manager (current branch) Version 1606 oder Microsoft Endpoint Manager (current branch) version 1602 oder früher verwenden, um das Konfigurationspaket auf Geräten zu bereitstellen.
[Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](configure-endpoints-mdm.md) | Verwenden Sie Tools für die mobile Geräteverwaltung oder Microsoft Intune, um das Konfigurationspaket auf dem Gerät bereitzustellen.
[Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](configure-endpoints-script.md) | Erfahren Sie, wie Sie das lokale Skript zum Bereitstellen des Konfigurationspakets auf Endpunkten verwenden.
[Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](configure-endpoints-vdi.md) | Erfahren Sie, wie Sie das Konfigurationspaket zum Konfigurieren von VDI-Geräten verwenden.


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
