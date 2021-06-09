---
title: Konfigurieren von Funktionen von Microsoft Defender für Endpunkt unter Android
description: Beschreibt, wie Microsoft Defender für Endpunkt unter Android konfiguriert wird
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, MDE, Android, Konfiguration
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
ms.openlocfilehash: 264ebbe0ceb6d6b83c006dbd1dd071a78ae219c3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841351"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Konfigurieren von Defender für Endpunkt unter Android-Features

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Bedingter Zugriff mit Defender für Endpunkt unter Android  
Microsoft Defender für Endpunkt unter Android zusammen mit Microsoft Intune und Azure Active Directory ermöglicht das Erzwingen von Gerätekompatibilitäts- und Richtlinien für bedingten Zugriff basierend auf Geräterisikostufen. Defender für Endpunkt ist eine MTD-Lösung (Mobile Threat Defense), die Sie bereitstellen können, um diese Funktion über Intune zu nutzen.

Weitere Informationen zum Einrichten von Defender für Endpunkt unter Android und bedingtem Zugriff finden Sie unter [Defender für Endpunkt und Intune.](/mem/intune/protect/advanced-threat-protection)

## <a name="configure-custom-indicators"></a>Konfigurieren von benutzerdefinierten Indikatoren  

> [!NOTE]
> Defender für Endpunkt unter Android unterstützt nur das Erstellen benutzerdefinierter Indikatoren für IP-Adressen und URLs/Domänen.

Defender für Endpunkt unter Android ermöglicht Administratoren das Konfigurieren benutzerdefinierter Indikatoren zur Unterstützung von Android-Geräten. Weitere Informationen zum Konfigurieren von benutzerdefinierten Indikatoren finden Sie unter [Verwalten von Indikatoren.](manage-indicators.md)

## <a name="configure-web-protection"></a>Konfigurieren des Webschutzes
Defender für Endpunkt unter Android ermöglicht IT-Administratoren die Konfiguration des Webschutzfeatures. Diese Funktion ist im Microsoft Endpoint Manager Admin Center verfügbar.

> [!NOTE]
> Defender für Endpunkt unter Android würde ein VPN verwenden, um das Webschutzfeature bereitzustellen. Dies ist kein reguläres VPN und ein lokales/selbstschleifendes VPN, das keinen Datenverkehr außerhalb des Geräts aufnimmt. Weitere Informationen finden Sie unter [Konfigurieren des Webschutzes auf Geräten mit Android.](/mem/intune/protect/advanced-threat-protection-manage-android)

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über Microsoft Defender für Endpunkt unter Android](microsoft-defender-endpoint-android.md)
- [Bereitstellen von Microsoft Defender für Endpunkt unter Android mit Microsoft Intune](android-intune.md)
