---
title: Microsoft Defender für Endpunkt unter Android
ms.reviewer: ''
description: Beschreibt die Installation und Verwendung von Microsoft Defender for Endpoint unter Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, installation, deploy, deinstallation, intune
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3f8a8c04f608096e5c226d6899fbbd983bd8d8c1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246428"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender für Endpunkt unter Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

In diesem Thema wird beschrieben, wie Sie Defender for Endpoint unter Android installieren, konfigurieren, aktualisieren und verwenden.

> [!CAUTION]
> Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Defender for Endpoint auf Android verursacht wahrscheinlich Leistungsprobleme und unvorhersehbare Systemfehler.


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>Installieren von Microsoft Defender for Endpoint unter Android

### <a name="prerequisites"></a>Voraussetzungen

-   **Für Endbenutzer**

    -   Microsoft Defender for Endpoint-Lizenz, die den Endbenutzern der App zugewiesen ist. Siehe [Microsoft Defender for Endpoint-Lizenzierungsanforderungen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Intune-Unternehmensportal App kann von [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) heruntergeladen werden und ist auf dem Android-Gerät verfügbar.

        -   Darüber hinaus können Geräte [](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) über die app Intune-Unternehmensportal registriert werden, um Intune-Richtlinien zur Gerätekonformität zu erzwingen. Dies erfordert, dass dem Endbenutzer eine Lizenz Microsoft Intune wird.

    -   Weitere Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).
        

-   **Für Administratoren**

    -   Zugriff auf das Microsoft Defender Security Center Portal.

        > [!NOTE]
        > Microsoft Intune ist die einzige unterstützte Mobile Device Management (MDM)-Lösung für die Bereitstellung von Microsoft Defender for Endpoint unter Android. Derzeit werden nur registrierte Geräte für die Erzwingung von Defender for Endpoint auf Android-bezogenen Geräte-Compliancerichtlinien in Intune unterstützt. 

    -   Access [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), um die App für registrierte Benutzergruppen in Ihrer Organisation zu bereitstellen.
        
### <a name="network-requirements"></a>Netzwerkanforderungen

- Damit Microsoft Defender for Endpoint unter Android funktioniert, wenn es mit einem Netzwerk verbunden ist, muss die Firewall/der Proxy so konfiguriert werden, dass der Zugriff auf URLs des [Microsoft Defender for Endpoint-Diensts ermöglicht wird.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

### <a name="system-requirements"></a>Systemanforderungen

-   Android-Geräte mit Android 6.0 und höher.
-   Intune-Unternehmensportal App wird von [Google Play heruntergeladen](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) und installiert. Die Geräteregistrierung ist erforderlich, damit Intune-Gerätekonformitätsrichtlinien erzwungen werden.

### <a name="installation-instructions"></a>Installationsanweisungen

Microsoft Defender for Endpoint unter Android unterstützt die Installation auf beiden Modi registrierter Geräte – dem älteren Geräteadministrator und dem Android-Enterprise Modi.
**Derzeit werden persönliche Geräte mit Geschäftsprofil und unternehmenseigenen, vollständig verwalteten Benutzergeräteregistrierungen in Android-Geräten Enterprise. Unterstützung für andere Android-Enterprise Modi wird angekündigt, sobald sie bereit sind.**

Die Bereitstellung von Microsoft Defender for Endpoint unter Android erfolgt über Microsoft Intune (MDM).
Weitere Informationen finden Sie unter [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).


> [!NOTE]
> **Microsoft Defender für Endpoint unter Android ist jetzt auf [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) verfügbar.** <br> Sie können von Intune aus eine Verbindung mit Google Play herstellen, um Microsoft Defender for Endpoint-App über geräteadministrator- und android-Enterprise bereitzustellen. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Konfigurieren von Microsoft Defender for Endpoint unter Android

Anleitungen zum Konfigurieren von Microsoft Defender for Endpoint auf Android-Features finden Sie unter [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).



## <a name="related-topics"></a>Verwandte Themen
- [Bereitstellen von Microsoft Defender für Endpunkt unter Android mit Microsoft Intune](android-intune.md)
- [Konfigurieren von Funktionen von Microsoft Defender für Endpunkt unter Android](android-configure.md)

