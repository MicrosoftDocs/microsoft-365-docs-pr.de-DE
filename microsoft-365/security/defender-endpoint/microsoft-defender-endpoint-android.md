---
title: Microsoft Defender ATP für Android
ms.reviewer: ''
description: Beschreibt die Installation und Verwendung von Microsoft Defender ATP für Android
keywords: microsoft, defender, atp, android, installation, deploy, deinstallation, intune
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
ms.openlocfilehash: 6518b86861fd5d03533bb787d4ee005d7ace1a0c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068831"
---
# <a name="microsoft-defender-for-endpoint-for-android"></a>Microsoft Defender für Endpoint für Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

In diesem Thema wird beschrieben, wie Sie Defender for Endpoint für Android installieren, konfigurieren, aktualisieren und verwenden.

> [!CAUTION]
> Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Defender for Endpoint für Android verursacht wahrscheinlich Leistungsprobleme und unvorhersehbare Systemfehler.


## <a name="how-to-install-microsoft-defender-for-endpoint-for-android"></a>Installieren von Microsoft Defender for Endpoint für Android

### <a name="prerequisites"></a>Voraussetzungen

-   **Für Endbenutzer**

    -   Microsoft Defender for Endpoint-Lizenz, die den Endbenutzern der App zugewiesen ist. Siehe [Microsoft Defender for Endpoint-Lizenzierungsanforderungen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Die Intune-Unternehmensportal-App kann von [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) heruntergeladen werden und ist auf dem Android-Gerät verfügbar.

        -   Darüber hinaus können Geräte [](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) über die Intune-Unternehmensportal-App registriert werden, um Intune-Gerätekonformitätsrichtlinien zu erzwingen. Dies erfordert, dass dem Endbenutzer eine Microsoft Intune-Lizenz zugewiesen wird.

    -   Weitere Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).
        

-   **Für Administratoren**

    -   Zugriff auf das Microsoft Defender Security Center-Portal.

        > [!NOTE]
        > Microsoft Intune ist die einzige unterstützte Mobile Device Management (MDM)-Lösung für die Bereitstellung von Microsoft Defender for Endpoint für Android. Derzeit werden nur registrierte Geräte unterstützt, um Defender for Endpoint für Android-bezogene Gerätekonformitätsrichtlinien in Intune zu erzwingen. 

    -   Greifen [Sie auf Microsoft Endpoint Manager Admin Center zu,](https://go.microsoft.com/fwlink/?linkid=2109431)um die App für registrierte Benutzergruppen in Ihrer Organisation zu bereitstellen.

### <a name="system-requirements"></a>Systemanforderungen

-   Android-Geräte mit Android 6.0 und höher.
-   Die Intune-Unternehmensportal-App wird von [Google Play heruntergeladen und](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) installiert. Die Geräteregistrierung ist erforderlich, damit Intune-Gerätekonformitätsrichtlinien erzwungen werden.

### <a name="installation-instructions"></a>Installationsanweisungen

Microsoft Defender für Endpoint für Android unterstützt die Installation auf beiden Modi von registrierten Geräten – dem älteren Geräteadministrator und dem Android Enterprise-Modus.
**Derzeit werden persönliche Geräte mit Geschäftsprofil und unternehmenseigenen, vollständig verwalteten Benutzergeräten in Android Enterprise unterstützt. Unterstützung für andere Android Enterprise-Modi wird angekündigt, sobald sie bereit sind.**

Die Bereitstellung von Microsoft Defender for Endpoint für Android erfolgt über Microsoft Intune (MDM).
Weitere Informationen finden Sie unter [Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune](android-intune.md).


> [!NOTE]
> **Microsoft Defender für Endpoint für Android ist jetzt auf [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) verfügbar.** <br> Sie können von Intune aus eine Verbindung mit Google Play herstellen, um Microsoft Defender for Endpoint-App über geräteadministrator- und Android Enterprise-Entrollmentmodi bereitzustellen. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-android"></a>Konfigurieren von Microsoft Defender for Endpoint für Android

Anleitungen zum Konfigurieren von Microsoft Defender for Endpoint für Android-Features finden Sie unter [Configure Microsoft Defender for Endpoint for Android features](android-configure.md).



## <a name="related-topics"></a>Verwandte Themen
- [Bereitstellen von Microsoft Defender for Endpoint für mit Microsoft Intune](android-intune.md)
- [Konfigurieren von Microsoft Defender for Endpoint für Android-Features](android-configure.md)

