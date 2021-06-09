---
title: Microsoft Defender für Endpunkt unter Android
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter Android installiert und verwendet wird
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Android, Installation, bereitstellen, Deinstallation, Intune
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
ms.openlocfilehash: 499ac9a6ee81bacb79cd83993d510f87e11c62c6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844718"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender für Endpunkt unter Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

In diesem Thema wird beschrieben, wie Sie Defender für Endpunkt unter Android installieren, konfigurieren, aktualisieren und verwenden.

> [!CAUTION]
> Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Defender für Endpunkt unter Android führt wahrscheinlich zu Leistungsproblemen und unvorhersehbaren Systemfehlern.


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>So installieren Sie Microsoft Defender für Endpunkt unter Android

### <a name="prerequisites"></a>Voraussetzungen

-   **Für Endbenutzer**

    -   Microsoft Defender für Endpunkt-Lizenz, die den Endbenutzern der App zugewiesen ist. Siehe [Microsoft Defender für Endpunkt-Lizenzierungsanforderungen](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Intune-Unternehmensportal App kann von [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) heruntergeladen werden und ist auf dem Android-Gerät verfügbar.

        -   Darüber hinaus können Geräte über die Intune-Unternehmensportal-App [registriert](/mem/intune/user-help/enroll-device-android-company-portal) werden, um Intune-Gerätecompliancerichtlinien zu erzwingen. Dies erfordert, dass dem Endbenutzer eine Microsoft Intune Lizenz zugewiesen wird.

    -   Weitere Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](/azure/active-directory/users-groups-roles/licensing-groups-assign)
        

-   **Für Administratoren**

    -   Zugriff auf das Microsoft Defender Security Center-Portal.

        > [!NOTE]
        > Microsoft Intune ist die einzige unterstützte Mdm-Lösung (Mobile Device Management) für die Bereitstellung von Microsoft Defender für Endpunkt unter Android. Derzeit werden nur registrierte Geräte unterstützt, um Defender für Endpunkt für Android-bezogene Gerätecompliancerichtlinien in Intune zu erzwingen. 

    -   Greifen Sie [auf Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu, um die App für registrierte Benutzergruppen in Ihrer Organisation bereitzustellen.
        
### <a name="network-requirements"></a>Netzwerkanforderungen

- Damit Microsoft Defender für Endpunkt unter Android funktioniert, wenn es mit einem Netzwerk verbunden ist, muss die Firewall/der Proxy konfiguriert werden, um [den Zugriff auf Microsoft Defender für Endpunktdienst-URLs zu ermöglichen.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

### <a name="system-requirements"></a>Systemanforderungen

-   Android-Geräte mit Android 6.0 und höher.
-   Intune-Unternehmensportal App wird von [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) heruntergeladen und installiert. Die Geräteregistrierung ist erforderlich, damit Intune-Gerätekompatibilitätsrichtlinien erzwungen werden.

### <a name="installation-instructions"></a>Installationsanweisungen

Microsoft Defender für Endpunkt unter Android unterstützt die Installation auf beiden Modi registrierter Geräte – dem Legacy-Geräteadministrator und android-Enterprise Modi.
**Derzeit werden persönliche Geräte mit Arbeitsprofil und vollständig verwalteten Benutzergeräteregistrierungen im Besitz des Unternehmens in Android Enterprise unterstützt. Unterstützung für andere Android-Enterprise modi wird angekündigt, wenn sie bereit sind.**

Die Bereitstellung von Microsoft Defender für Endpunkt unter Android erfolgt über Microsoft Intune (MDM).
Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Defender für Endpunkt unter Android mit Microsoft Intune.](android-intune.md)


> [!NOTE]
> **Microsoft Defender für Endpunkt unter Android ist jetzt in [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) verfügbar.** <br> Sie können von Intune aus eine Verbindung mit Google Play herstellen, um die Microsoft Defender für Endpunkt-App über Geräteadministrator- und Android-Enterprise-Registrierungsmodi bereitzustellen. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>So konfigurieren Sie Microsoft Defender für Endpunkt unter Android

Anleitungen zum Konfigurieren von Microsoft Defender für Endpunkt unter Android-Features finden Sie unter [Konfigurieren von Microsoft Defender für Endpunkt unter Android-Features.](android-configure.md)



## <a name="related-topics"></a>Verwandte Themen
- [Bereitstellen von Microsoft Defender für Endpunkt unter Android mit Microsoft Intune](android-intune.md)
- [Konfigurieren von Funktionen von Microsoft Defender für Endpunkt unter Android](android-configure.md)

