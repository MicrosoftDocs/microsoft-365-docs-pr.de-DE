---
title: Onboarding von Geräten in den Microsoft Defender for Endpoint-Dienst
description: Onboarding von Windows 10-Geräten, -Servern, Nicht-Windows-Geräten und Erfahren Sie, wie Sie einen Erkennungstest ausführen.
keywords: Onboarding, Microsoft Defender for Endpoint-Onboarding, sccm, Gruppenrichtlinie, MDM, lokales Skript, Erkennungstest
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
ms.openlocfilehash: 05cc5770df5bb05687bb8be69ad89a7abd6875ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933553"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a>Onboarding von Geräten in den Microsoft Defender for Endpoint-Dienst

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Sie müssen den Abschnitt Onboarding des Defender for Endpoint-Portals verwenden, um alle unterstützten Geräte zu integrieren. Je nach Gerät werden Sie mit den entsprechenden Schritten geführt und die für das Gerät geeigneten Verwaltungs- und Bereitstellungstooloptionen bereitgestellt. 

Im Allgemeinen, um Geräte in den Dienst zu integrieren:

- Überprüfen, ob das Gerät die [Mindestanforderungen erfüllt](minimum-requirements.md)
- Führen Sie je nach Gerät die Konfigurationsschritte aus, die im Abschnitt onboarding des Defender for Endpoint-Portals bereitgestellt werden.
- Verwenden des geeigneten Verwaltungstools und der bereitstellungsmethode für Ihre Geräte
- Führen Sie einen Erkennungstest aus, um zu überprüfen, ob die Geräte ordnungsgemäß onboardiert sind, und melden Sie den Dienst.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a>Onboardingtooloptionen
In der folgenden Tabelle sind die verfügbaren Tools aufgeführt, die auf dem Endpunkt basieren, den Sie integrieren müssen.

| Endpunkt     | Tooloptionen                       |
|--------------|------------------------------------------|
| **Windows**  |  [Lokales Skript (bis zu 10 Geräte)](configure-endpoints-script.md) <br>  [Gruppenrichtlinie](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI-Skripts](configure-endpoints-vdi.md)   |
| **macOS**    | [Lokale Skripts](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Verwaltung mobiler Geräte - Mobile Device Management](mac-install-with-other-mdm.md) |
| **Linux Server** | [Lokales Skript](linux-install-manually.md) <br> [100](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [App-basiert](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 




## <a name="in-this-section"></a>Inhalt dieses Abschnitts
Thema | Beschreibung
:---|:---
[Onboarding von früheren Windows-Versionen](onboard-downlevel.md)| Onboarding von Windows 7- und Windows 8.1-Geräten zu Defender for Endpoint. 
[Onboarding von Windows 10-Geräten](configure-endpoints.md) | Sie müssen Geräte integrieren, damit sie dem Defender for Endpoint-Dienst melden können. Erfahren Sie mehr über die Tools und Methoden, die Sie zum Konfigurieren von Geräten in Ihrem Unternehmen verwenden können.
[Onboarding von Servern](configure-server-endpoints.md) |  Onboarding Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) Version 1803 und höher, Windows Server 2019 und höher und Windows Server 2019 Core Edition zu Defender for Endpoint.
[Onboarding von Nicht-Windows-Geräten](configure-endpoints-non-windows.md) | Defender for Endpoint bietet eine zentrale Sicherheitsbetriebserfahrung für Windows- und Nicht-Windows-Plattformen. Sie können Warnungen von verschiedenen unterstützten Betriebssystemen im Microsoft Defender Security Center anzeigen und das Netzwerk Ihrer Organisation besser schützen. Diese Erfahrung nutzt sensorische Daten eines Drittanbieters für Sicherheitsprodukte. 
[Ausführen eines Erkennungstests auf einem neu integrierten Gerät](run-detection-test.md) | Führen Sie ein Skript auf einem neu integrierten Gerät aus, um sicherzustellen, dass es ordnungsgemäß an den Defender for Endpoint-Dienst berichtet.
[Konfigurieren von Proxy- und Interneteinstellungen](configure-proxy-internet.md)| Aktivieren Sie die Kommunikation mit dem Defender for Endpoint-Clouddienst, indem Sie die Proxy- und Internetverbindungseinstellungen konfigurieren.
[Behandeln von Onboarding-Problemen](troubleshoot-onboarding.md) | Erfahren Sie mehr über das Beheben von Problemen, die beim Onboarding auftreten können.

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
