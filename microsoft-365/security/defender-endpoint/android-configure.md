---
title: Konfigurieren von Funktionen von Microsoft Defender für Endpunkt unter Android
description: Beschreibt das Konfigurieren von Microsoft Defender for Endpoint unter Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, configuration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 462fa6177ee35d5d988efa985422b499e2339ff4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935317"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Konfigurieren von Defender for Endpoint unter Android-Features

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Bedingter Zugriff mit Defender for Endpoint unter Android  
Microsoft Defender for Endpoint unter Android ermöglicht Microsoft Intune und Azure Active Directory die Erzwingung von Gerätekonformität und Richtlinien für bedingten Zugriff basierend auf Geräterisikostufen. Defender for Endpoint ist eine Mobile Threat Defense (MTD)-Lösung, die Sie bereitstellen können, um diese Funktion über Intune zu nutzen.

Weitere Informationen zum Einrichten von Defender for Endpoint unter Android und bedingten Zugriff finden Sie unter [Defender for Endpoint und Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).

## <a name="configure-custom-indicators"></a>Konfigurieren benutzerdefinierter Indikatoren  

> [!NOTE]
> Defender for Endpoint unter Android unterstützt nur das Erstellen benutzerdefinierter Indikatoren für IP-Adressen und URLs/Domänen.

Defender for Endpoint unter Android ermöglicht Administratoren die Konfiguration benutzerdefinierter Indikatoren zur Unterstützung von Android-Geräten. Weitere Informationen zum Konfigurieren benutzerdefinierter Indikatoren finden Sie unter [Manage indicators](manage-indicators.md).

## <a name="configure-web-protection"></a>Konfigurieren des Webschutzes
Defender für Endpoint unter Android ermöglicht IT-Administratoren die Konfiguration des Webschutzfeatures. Diese Funktion ist im Microsoft Endpoint Manager Admin Center verfügbar.

> [!NOTE]
> Defender für Endpoint unter Android würde ein VPN verwenden, um das Web Protection-Feature zur Verfügung zu stellen. Dies ist kein normales VPN und ein lokales VPN mit selbstschleifender Schleife, das keinen Datenverkehr außerhalb des Geräts verwendet. Weitere Informationen finden Sie unter [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über Microsoft Defender für Endpunkt unter Android](microsoft-defender-endpoint-android.md)
- [Bereitstellen von Microsoft Defender für Endpunkt unter Android mit Microsoft Intune](android-intune.md)
