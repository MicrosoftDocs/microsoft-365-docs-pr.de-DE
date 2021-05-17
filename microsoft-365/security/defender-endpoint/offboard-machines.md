---
title: Offboardgeräte aus dem Microsoft Defender for Endpoint-Dienst
description: Onboarding Windows 10 Geräten, Servern, nicht Windows geräten aus dem Microsoft Defender for Endpoint-Dienst
keywords: offboarding, Microsoft Defender for Endpoint offboarding, offboarding
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
ms.openlocfilehash: 425e5b9e0be12b89c8fd3b7201010b0f776cc6a5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934153"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>Offboardgeräte aus dem Microsoft Defender for Endpoint-Dienst

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plattformen**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

Befolgen Sie die entsprechenden Anweisungen in Abhängigkeit von Ihrer bevorzugten Bereitstellungsmethode.

>[!NOTE]
> Der Status eines Geräts wird 7 Tage nach dem Offboarding in [Inaktiv](fix-unhealthy-sensors.md#inactive-devices) geschaltet. <br> Daten von Offboardgeräten (z. B. Zeitachse, Warnungen, Sicherheitsrisiken usw.) verbleiben im Portal, bis der [konfigurierte](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) Aufbewahrungszeitraum abläuft. <br>
> Das Geräteprofil (ohne Daten) bleibt [](machines-view-overview.md) nicht länger als 180 Tage in der Geräteliste.
> Darüber hinaus werden Geräte, die in den letzten 30 Tagen nicht aktiv sind, nicht mit [](tvm-exposure-score.md) den Daten in Verbindung stehen, die die Bedrohungs- und Sicherheitsrisikomanagement Belichtungssendpunktzahl ihrer Organisation und die Microsoft Secure Score für Geräte spiegeln. <br>
> Wenn Sie nur aktive Geräte anzeigen möchten, können Sie nach [Integritätsstatus,](machines-view-overview.md#health-state) [Gerätetags oder](machine-tags.md) [Computergruppen filtern.](machine-groups.md) 

## <a name="offboard-windows-10-devices"></a>Offboard-Windows 10 Geräte
- [Offboardgeräte mit einem lokalen Skript](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [Offboardgeräte mithilfe von Gruppenrichtlinien](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Offboardgeräte mit Mobile Device Management Tools](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>Offboardserver
- [Offboardserver](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>Offboard-Windows Geräte
- [Offboard-Windows Geräte](configure-endpoints-non-windows.md#offboard-non-windows-devices)

