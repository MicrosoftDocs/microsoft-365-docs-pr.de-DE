---
title: Konfigurieren von Funktionen von Microsoft Defender für Endpunkt für Android
description: Beschreibt das Konfigurieren von Microsoft Defender for Endpoint für Android
keywords: microsoft, defender, atp, mde, android, configuration
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
ms.openlocfilehash: c395aafc8a468cfdeaea973ab02421212870192a
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587215"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a>Konfigurieren von Defender for Endpoint für Android-Features

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a>Bedingter Zugriff mit Defender for Endpoint für Android  
Microsoft Defender for Endpoint für Android ermöglicht zusammen mit Microsoft Intune und Azure Active Directory die Erzwingung der Gerätekonformität und Richtlinien für bedingten Zugriff basierend auf den Geräterisikostufen. Defender for Endpoint ist eine Mobile Threat Defense (MTD)-Lösung, die Sie bereitstellen können, um diese Funktion über Intune zu nutzen.

Weitere Informationen zum Einrichten von Defender for Endpoint für Android und bedingten Zugriff finden Sie unter [Defender for Endpoint und Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).

## <a name="configure-custom-indicators"></a>Konfigurieren benutzerdefinierter Indikatoren  

> [!NOTE]
> Defender for Endpoint für Android unterstützt nur das Erstellen benutzerdefinierter Indikatoren für IP-Adressen und URLs/Domänen.

Mit Defender for Endpoint für Android können Administratoren benutzerdefinierte Indikatoren konfigurieren, um auch Android-Geräte zu unterstützen. Weitere Informationen zum Konfigurieren benutzerdefinierter Indikatoren finden Sie unter [Manage indicators](manage-indicators.md).

## <a name="configure-web-protection"></a>Konfigurieren des Webschutzes
Defender for Endpoint für Android ermöglicht IT-Administratoren die Konfiguration des Webschutzfeatures. Diese Funktion ist im Microsoft Endpoint Manager Admin Center verfügbar.

> [!NOTE]
> Defender für Endpoint für Android würde ein VPN verwenden, um das Web Protection-Feature zur Verfügung zu stellen. Dies ist kein normales VPN und ein lokales VPN mit selbstschleifender Schleife, das keinen Datenverkehr außerhalb des Geräts verwendet. Weitere Informationen finden Sie unter [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über Microsoft Defender für Endpunkt für Android](microsoft-defender-endpoint-android.md)
- [Bereitstellen von Microsoft Defender für Endpunkt für Android mit Microsoft Intune](android-intune.md)
