---
title: Microsoft Defender für Endpunkt für iOS
ms.reviewer: ''
description: Beschreibt die Installation und Verwendung von Microsoft Defender for Endpoint unter iOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, overview, installation, deploy, deinstallation, intune
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cdf32e6daa26eb369d66a4b6c0ff3991093c67f9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935269"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender für Endpunkt für iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender for Endpoint unter iOS** bietet Schutz vor Phishing und unsicheren Netzwerkverbindungen von Websites, E-Mails und Apps. Alle Warnungen sind über einen einzelnen Fensterausschnitt im Microsoft Defender Security Center verfügbar. Das Portal bietet Sicherheitsteams eine zentrale Ansicht von Bedrohungen auf iOS-Geräten und anderen Plattformen.

> [!CAUTION]
> Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Defender for Endpoint unter iOS verursacht wahrscheinlich Leistungsprobleme und unvorhersehbare Systemfehler.

## <a name="pre-requisites"></a>Voraussetzungen

**Für Endbenutzer**

- Microsoft Defender for Endpoint-Lizenz, die den Endbenutzern der App zugewiesen ist. Weitere Informationen [finden Sie unter Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).

- Geräte werden über [](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) die Intune-Unternehmensportal-App registriert, um Intune-Gerätekonformitätsrichtlinien zu erzwingen. Dies erfordert, dass dem Endbenutzer eine Microsoft Intune-Lizenz zugewiesen wird.
    - Die Intune-Unternehmensportal-App kann aus dem [Apple App Store heruntergeladen werden.](https://apps.apple.com/us/app/intune-company-portal/id719171358)
    - Beachten Sie, dass Apple es Benutzern nicht erlaubt, andere Apps aus dem App Store herunterzuladen. Daher muss dieser Schritt vom Benutzer vor dem Onboarding in die Microsoft Defender for Endpoint-App durchgeführt werden.

- Weitere Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).

**Für Administratoren**

- Zugriff auf das Microsoft Defender Security Center-Portal.

    > [!NOTE]
    > Microsoft Intune ist die einzige unterstützte Mobile Device Management (MDM)-Lösung für die Bereitstellung von Microsoft Defender for Endpoint unter iOS. Derzeit werden nur registrierte Geräte zum Erzwingen von Defender for Endpoint auf iOS-bezogenen Geräte-Compliancerichtlinien in Intune unterstützt.

- Zugriff auf [Microsoft Endpoint Manager Admin Center,](https://go.microsoft.com/fwlink/?linkid=2109431)um die App für registrierte Benutzergruppen in Ihrer Organisation zu bereitstellen.

**Systemanforderungen**

- iOS-Geräte mit iOS 11.0 und höher. iPad-Geräte werden ab Version 1.1.15010101 offiziell unterstützt.

- Das Gerät wird bei der [Intune Company Portal-App registriert.](https://apps.apple.com/us/app/intune-company-portal/id719171358)

> [!NOTE]
> **Microsoft Defender ATP (Microsoft Defender for Endpoint) unter iOS ist jetzt im [Apple App Store verfügbar.](https://aka.ms/mdatpiosappstore)**

## <a name="installation-instructions"></a>Installationsanweisungen

Die Bereitstellung von Microsoft Defender for Endpoint unter iOS erfolgt über Microsoft Intune (MDM) und überwachte und nicht überwachte Geräte werden unterstützt.
Weitere Informationen finden Sie unter [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).

## <a name="resources"></a>Ressourcen

- Informieren Sie sich über bevorstehende Versionen unter [What's new in Microsoft Defender for Endpoint unter iOS](ios-whatsnew.md) oder in unserem [Blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).

- Bereitstellen von Feedback über das In-App-Feedbacksystem oder über [das SecOps-Portal](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Nächste Schritte

- [Bereitstellen von Microsoft Defender for Endpoint unter iOS](ios-install.md)
- [Konfigurieren von Microsoft Defender for Endpoint unter iOS-Features](ios-configure-features.md)
