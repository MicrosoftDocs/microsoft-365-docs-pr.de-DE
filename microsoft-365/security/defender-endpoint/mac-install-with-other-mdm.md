---
title: Bereitstellung mit einem anderen Mobile Device Management (MDM)-System für Microsoft Defender ATP für Mac
description: Installieren Sie Microsoft Defender ATP für Mac auf anderen Verwaltungslösungen.
keywords: microsoft, defender, atp, mac, installation, deploy, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 28e57f1749ea9dce22e1a8a210f73cc3c7993738
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066840"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-for-mac"></a>Bereitstellung mit einem anderen Mobile Device Management (MDM)-System für Microsoft Defender for Endpoint für Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>Voraussetzungen und Systemanforderungen

Bevor Sie beginnen, finden Sie auf der Hauptseite [von Microsoft Defender for Endpoint für Mac](microsoft-defender-endpoint-mac.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.

## <a name="approach"></a>Ansatz

> [!CAUTION]
> Derzeit unterstützt Microsoft offiziell nur Intune und JAMF für die Bereitstellung und Verwaltung von Microsoft Defender for Endpoint für Mac. Microsoft gibt keine ausdrücklichen oder impliziten Gewährleistungen in Bezug auf die unten angegebenen Informationen ab.

Wenn Ihre Organisation eine mobile Geräteverwaltungslösung (Mobile Device Management, MDM) verwendet, die offiziell nicht unterstützt wird, bedeutet dies nicht, dass Sie Microsoft Defender for Endpoint für Mac nicht bereitstellen oder ausführen können.

Microsoft Defender für Endpoint für Mac ist nicht von herstellerspezifischen Features abhängig. Es kann mit jeder beliebigen MDM-Lösung verwendet werden, die die folgenden Features unterstützt:

- Stellen Sie ein macOS .pkg auf verwalteten Geräten zur Verfügung.
- Bereitstellen von macOS-Systemkonfigurationsprofilen auf verwalteten Geräten.
- Führen Sie ein beliebiges vom Administrator konfiguriertes Tool/Skript auf verwalteten Geräten aus.

Die meisten modernen MDM-Lösungen enthalten diese Features, können sie jedoch anders aufrufen.

Sie können Defender jedoch ohne die letzte Anforderung aus der vorherigen Liste bereitstellen:

- Sie können den Status nicht zentral erfassen
- Wenn Sie sich für die Deinstallation von Defender entscheiden, müssen Sie sich lokal als Administrator am Clientgerät anmelden.

## <a name="deployment"></a>Bereitstellung)

Die meisten MDM-Lösungen verwenden dasselbe Modell für die Verwaltung von macOS-Geräten mit ähnlicher Terminologie. Verwenden [Sie die JAMF-basierte Bereitstellung](mac-install-with-jamf.md) als Vorlage.

### <a name="package"></a>Paket

Konfigurieren Sie die Bereitstellung eines [erforderlichen Anwendungspakets](mac-install-with-jamf.md)mit dem Installationspaket (wdav.pkg), das von [Microsoft Defender Security Center heruntergeladen wurde.](mac-install-with-jamf.md)

Verwenden Sie zum Bereitstellen des Pakets in Ihrem Unternehmen die Anweisungen, die Ihrer MDM-Lösung zugeordnet sind.

### <a name="license-settings"></a>Lizenzeinstellungen

Richten Sie [ein Systemkonfigurationsprofil ein.](mac-install-with-jamf.md) Ihre MDM-Lösung kann sie etwa als "Profil für benutzerdefinierte Einstellungen" bezeichnen, da Microsoft Defender for Endpoint für Mac nicht Teil von macOS ist.

Verwenden Sie die Eigenschaftenliste jamf/WindowsDefenderATPOnboarding.plist, die aus einem onboarding-Paket extrahiert werden kann, das aus [Microsoft Defender Security Center heruntergeladen wurde.](mac-install-with-jamf.md)
Ihr System unterstützt möglicherweise eine beliebige Eigenschaftenliste im XML-Format. Sie können die Datei jamf/WindowsDefenderATPOnboarding.plist wie in diesem Fall hochladen.
Alternativ müssen Sie die Eigenschaftenliste möglicherweise zuerst in ein anderes Format konvertieren.

In der Regel verfügt Ihr benutzerdefiniertes Profil über eine ID, einen Namen oder ein Domänenattribut. Sie müssen genau "com.microsoft.wdav.atp" für diesen Wert verwenden.
MDM verwendet sie zum Bereitstellen der **Einstellungsdatei in /Library/Managed Preferences/com.microsoft.wdav.atp.plist** auf einem Clientgerät, und Defender verwendet diese Datei zum Laden der Onboardinginformationen.

### <a name="kernel-extension-policy"></a>Kernelerweiterungsrichtlinie

Richten Sie eine KEXT- oder Kernelerweiterungsrichtlinie ein. Verwenden Sie die **Team-ID UBF8T346G9,** um von Microsoft bereitgestellte Kernelerweiterungen zu erlauben.

### <a name="system-extension-policy"></a>Systemerweiterungsrichtlinie

Richten Sie eine Systemerweiterungsrichtlinie ein. Verwenden Sie den **Teambezeichner UBF8T346G9,** und genehmigen Sie die folgenden Bündelbezeichner:

- com.microsoft.wdav.epsext
- com.microsoft.wdav.netext

### <a name="full-disk-access-policy"></a>Richtlinie für den vollständigen Datenträgerzugriff

Gewähren Des vollständigen Festplattenzugriffs auf die folgenden Komponenten:

- Microsoft Defender für Endpunkt
    - Bezeichner: `com.microsoft.wdav`
    - Bezeichnertyp: Bundle-ID
    - Codeanforderung: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

- Microsoft Defender for Endpoint Security Extension
    - Bezeichner: `com.microsoft.wdav.epsext`
    - Bezeichnertyp: Bundle-ID
    - Codeanforderung: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

### <a name="network-extension-policy"></a>Netzwerkerweiterungsrichtlinie

Im Rahmen der Endpunkterkennungs- und -reaktionsfunktionen prüft Microsoft Defender for Endpoint für Mac den Socketdatenverkehr und meldet diese Informationen an das Microsoft Defender Security Center-Portal. Mit der folgenden Richtlinie kann die Netzwerkerweiterung diese Funktionalität ausführen.

- Filtertyp: Plugin
- Plug-In-Bundle-ID: `com.microsoft.wdav`
- Filter data provider bundle identifier: `com.microsoft.wdav.netext`
- Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- Filtersockets: `true`

## <a name="check-installation-status"></a>Überprüfen des Installationsstatus

Führen [Sie Microsoft Defender for Endpoint](mac-install-with-jamf.md) auf einem Clientgerät aus, um den Onboardingstatus zu überprüfen.
