---
title: Planen der Bereitstellung von Microsoft Defender for Endpoint
description: Wählen Sie die beste Microsoft Defender for Endpoint-Bereitstellungsstrategie für Ihre Umgebung aus.
keywords: deploy, plan, deployment strategy, cloud native, management, on prem, evaluation, onboarding, local, group policy, gp, endpoint manager, mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163575"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a>Planen der Bereitstellung von Microsoft Defender for Endpoint 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


Planen Sie Ihre Microsoft Defender for Endpoint-Bereitstellung, damit Sie die Sicherheitsfunktionen innerhalb der Suite maximieren und Ihr Unternehmen besser vor Cyberbedrohungen schützen können.


Diese Lösung enthält Anleitungen zum Identifizieren Ihrer Umgebungsarchitektur, zum Auswählen der Art des Bereitstellungstools, das Ihren Anforderungen am besten entspricht, und Anleitungen zum Konfigurieren von Funktionen.


![Abbildung des Bereitstellungsflusses](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a>Schritt 1: Identifizieren der Architektur
Wir wissen, dass jede Unternehmensumgebung einzigartig ist, daher haben wir verschiedene Optionen bereitgestellt, um Ihnen die Flexibilität bei der Auswahl der Bereitstellung des Diensts zu ermöglichen.

Je nach Ihrer Umgebung eignen sich einige Tools für bestimmte Architekturen besser. 

Verwenden Sie das folgende Material, um die geeignete Defender for Endpoint-Architektur auszuwählen, die am besten in Ihrer Organisation verwendet wird.

| Element | Beschreibung |
|:-----|:-----|
|[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) | Das Architekturmaterial hilft Ihnen bei der Planung der Bereitstellung für die folgenden Architekturen: <ul><li> Cloudspezifisch </li><li> Co-Management </li><li> Lokal</li><li>Auswertung und lokales Onboarding</li>



## <a name="step-2-select-deployment-method"></a>Schritt 2: Bereitstellungsmethode auswählen
Defender for Endpoint unterstützt eine Vielzahl von Endpunkten, die Sie in den Dienst integrieren können. 

In der folgenden Tabelle sind die unterstützten Endpunkte und das entsprechende Bereitstellungstool aufgeführt, das Sie verwenden können, damit Sie die Bereitstellung entsprechend planen können.

| Endpunkt     | Bereitstellungstool                       |
|--------------|------------------------------------------|
| **Windows**  |  [Lokales Skript (bis zu 10 Geräte)](configure-endpoints-script.md) <br>  [Gruppenrichtlinie](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI-Skripts](configure-endpoints-vdi.md)   |
| **macOS**    | [Lokales Skript](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Verwaltung mobiler Geräte - Mobile Device Management](mac-install-with-other-mdm.md) |
| **Linux Server** | [Lokales Skript](linux-install-manually.md) <br> [100](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [App-basiert](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a>Schritt 3: Konfigurieren von Funktionen
Konfigurieren Sie nach dem Onboarding von Endpunkten die Sicherheitsfunktionen in Defender for Endpoint, damit Sie den robusten Sicherheitsschutz maximieren können, der in der Suite verfügbar ist. Zu den Funktionen gehören:

- Erkennung und Reaktion am Endpunkt
- Schutz der nächsten Generation
- Angriffsfläche verringern


  
## <a name="related-topics"></a>Verwandte Themen
- [Bereitstellungsphasen](deployment-phases.md)
