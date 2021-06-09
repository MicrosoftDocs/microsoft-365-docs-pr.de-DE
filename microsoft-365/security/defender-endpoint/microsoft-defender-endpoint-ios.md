---
title: Microsoft Defender für Endpunkt für iOS
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter iOS installiert und verwendet wird
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, IOS, Übersicht, Installation, bereitstellen, Deinstallation, Intune
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
ms.openlocfilehash: b4c2d586cd23a346db1bcebf891689ff648b639b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844706"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender für Endpunkt für iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender für Endpunkt unter iOS** bietet Schutz vor Phishing und unsicheren Netzwerkverbindungen von Websites, E-Mails und Apps. Alle Warnungen werden über einen einzelnen Fensterausschnitt im Microsoft Defender Security Center verfügbar sein. Das Portal bietet Sicherheitsteams eine zentrale Übersicht über Bedrohungen auf iOS-Geräten und anderen Plattformen.

> [!CAUTION]
> Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Defender für Endpunkt unter iOS führt wahrscheinlich zu Leistungsproblemen und unvorhersehbaren Systemfehlern.

## <a name="pre-requisites"></a>Voraussetzungen

**Für Endbenutzer**

- Microsoft Defender für Endpunkt-Lizenz, die den Endbenutzern der App zugewiesen ist. Siehe [Microsoft Defender für Endpunkt-Lizenzierungsanforderungen.](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

- Geräte werden über die Intune-Unternehmensportal-App [registriert,](/mem/intune/user-help/enroll-your-device-in-intune-ios) um Intune-Gerätekompatibilitätsrichtlinien zu erzwingen. Dies erfordert, dass dem Endbenutzer eine Microsoft Intune Lizenz zugewiesen wird.
    - Intune-Unternehmensportal App kann aus der [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358)heruntergeladen werden.
    - Beachten Sie, dass Apple das Umleiten von Benutzern zum Herunterladen anderer Apps aus dem App Store nicht zulässt. Daher muss dieser Schritt vom Benutzer vor dem Onboarding in die Microsoft Defender für Endpunkt-App ausgeführt werden.

- Weitere Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](/azure/active-directory/users-groups-roles/licensing-groups-assign)

**Für Administratoren**

- Zugriff auf das Microsoft Defender Security Center-Portal.

    > [!NOTE]
    > Microsoft Intune ist die einzige unterstützte Unified Endpoint Management (UEM)-Lösung zum Bereitstellen von Microsoft Defender für Endpunkt und Erzwingen von Defender für Endpunkt-bezogenen Gerätekompatibilitätsrichtlinien in Intune.

- Zugriff auf [Microsoft Endpoint Manager Admin Center,](https://go.microsoft.com/fwlink/?linkid=2109431)um die App für registrierte Benutzergruppen in Ihrer Organisation bereitzustellen.

**Systemanforderungen**

- iOS-Geräte mit iOS 11.0 und höher. iPad Geräte werden ab Version 1.1.15010101 offiziell unterstützt.

- Das Gerät ist bei der [Intune-Unternehmensportal-App](https://apps.apple.com/us/app/intune-company-portal/id719171358)registriert.

## <a name="installation-instructions"></a>Installationsanweisungen

Die Bereitstellung von Microsoft Defender für Endpunkt unter iOS erfolgt über Microsoft Intune (MDM), und sowohl überwachte als auch nicht überwachte Geräte werden unterstützt. Endbenutzer können die App auch direkt aus dem [Apple App Store](https://aka.ms/mdatpiosappstore)installieren.
Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Defender für Endpunkt unter iOS.](ios-install.md)

## <a name="resources"></a>Ressourcen

- Informieren Sie sich über bevorstehende Versionen, indem Sie die [Neuigkeiten in Microsoft Defender für Endpunkt unter iOS](ios-whatsnew.md) oder in unserem [Blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)besuchen.

- Bereitstellen von Feedback über das In-App-Feedbacksystem oder über [das SecOps-Portal](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Nächste Schritte

- [Bereitstellen von Microsoft Defender für Endpunkt unter iOS](ios-install.md)
- [Konfigurieren von Microsoft Defender für Endpunkt unter iOS-Features](ios-configure-features.md)
