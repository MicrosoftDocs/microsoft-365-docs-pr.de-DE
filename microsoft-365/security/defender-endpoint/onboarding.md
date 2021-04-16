---
title: Onboarding für den Microsoft Defender for Endpoint-Dienst
description: Informationen zum Onboarding von Endpunkten in den Microsoft Defender for Endpoint-Dienst
keywords: microsoft defender for endpoint, onboard, deploy
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2a3325a290dc985bdb99a5a843b4b9e1f642a62b
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861803"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>Onboarding für den Microsoft Defender for Endpoint-Dienst

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Erfahren Sie mehr über die verschiedenen Phasen der Bereitstellung von Microsoft Defender for Endpoint und über die Konfiguration der Funktionen innerhalb der Lösung. 

Die Bereitstellung von Defender for Endpoint ist ein drei phasenweiser Prozess:

| [![Bereitstellungsphase – Vorbereiten](images/phase-diagrams/prepare.png)](prepare-deployment.md)<br>[Phase 1: Vorbereiten](prepare-deployment.md) | [![Bereitstellungsphase – Setup](images/phase-diagrams/setup.png)](production-deployment.md)<br>[Phase 2: Setup](production-deployment.md) | ![Bereitstellungsphase – onboard](images/phase-diagrams/onboard.png)<br>Phase 3: Onboarding |
| ----- | ----- | ----- |
| | |*Sie sind hier!*|

Sie befinden sich derzeit in der Onboardingphase.

Dies sind die Schritte, die Sie zum Bereitstellen von Defender for Endpoint ausführen müssen:

- Schritt 1: Onboarding von Endpunkten für den Dienst 
- Schritt 2: Konfigurieren von Funktionen 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Schritt 1: Onboarding von Endpunkten mithilfe eines der unterstützten Verwaltungstools
Im [Thema Bereitstellung planen](deployment-strategy.md) werden die allgemeinen Schritte beschrieben, die Sie zum Bereitstellen von Defender for Endpoint ausführen müssen.  


Sehen Sie sich dieses Video an, um einen schnellen Überblick über den Onboardingprozess zu erhalten, und erfahren Sie mehr über die verfügbaren Tools und Methoden.
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



Nachdem Sie Ihre Architektur identifiziert haben, müssen Sie entscheiden, welche Bereitstellungsmethode verwendet werden soll. Das von Ihnen auswählende Bereitstellungstool beeinflusst, wie Sie Endpunkte in den Dienst integrieren. 

### <a name="onboarding-tool-options"></a>Onboardingtooloptionen

In der folgenden Tabelle sind die verfügbaren Tools aufgeführt, die auf dem Endpunkt basieren, den Sie integrieren müssen.

| Endpunkt     | Tooloptionen                       |
|--------------|------------------------------------------|
| **Windows**  |  [Lokales Skript (bis zu 10 Geräte)](configure-endpoints-script.md) <br>  [Gruppenrichtlinie](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Device Manager](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI-Skripts](configure-endpoints-vdi.md) <br> [Azure Security Center](configure-server-endpoints.md#integration-with-azure-security-center) |
| **macOS**    | [Lokale Skripts](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Verwaltung mobiler Geräte - Mobile Device Management](mac-install-with-other-mdm.md) |
| **Linux Server** | [Lokales Skript](linux-install-manually.md) <br> [100](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [App-basiert](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a>Schritt 2: Konfigurieren von Funktionen
Nach dem Onboarding der Endpunkte konfigurieren Sie die verschiedenen Funktionen, z. B. Endpunkterkennung und -reaktion, Schutz der nächsten Generation und Reduzierung der Angriffsfläche. 


## <a name="example-deployments"></a>Beispielbereitstellungen
In diesem Bereitstellungshandbuch führen wir Sie durch die Verwendung von zwei Bereitstellungstools zum Onboarding von Endpunkten und zum Konfigurieren von Funktionen.

Die Tools in den Beispielbereitstellungen sind:
- [Onboarding mithilfe des Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Onboarding mithilfe des Microsoft Endpoint Manager](onboarding-endpoint-manager.md)

Mithilfe der oben genannten Bereitstellungstools werden Sie dann bei der Konfiguration der folgenden Defender for Endpoint-Funktionen geführt:
- Endpunkterkennung und Reaktionskonfiguration
- Schutzkonfiguration der nächsten Generation
- Konfiguration der Attack Surface Reduction

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding mithilfe des Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Onboarding mithilfe des Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
- [Sichere Dokumente in Microsoft 365 E5](../office-365-security/safe-docs.md)
