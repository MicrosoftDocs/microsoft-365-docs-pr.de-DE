---
title: Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten
description: Verwenden Sie Tools für die mobile Geräteverwaltung, um das Konfigurationspaket auf Geräten bereitzustellen, sodass die Geräte in den Dienst integriert werden.
keywords: Onboarding von Geräten mit mdm, Geräteverwaltung, Onboarding von Microsoft Defender für Endpunkt-Geräten, MDM
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f0a0a35d41d56abfcc7975c9e79ff7d537b72f40
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338577"
---
# <a name="onboard-the-windows-10-devices-using-mobile-device-management-tools"></a>Onboarding der Windows 10-Geräte mithilfe von Tools für die mobile Geräteverwaltung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

Sie können Lösungen für die mobile Geräteverwaltung (Mobile Device Management, MDM) verwenden, um Geräte zu konfigurieren. Defender für Endpunkt unterstützt MDMs, indem OMA-URIs zum Erstellen von Richtlinien zum Verwalten von Geräten bereitgestellt wird.

Weitere Informationen zur Verwendung von Defender für Endpunkt-CSP finden Sie in [der Datei "WindowsAdvancedThreatProtection CSP"](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) und ["WindowsAdvancedThreatProtection DDF".](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)

## <a name="before-you-begin"></a>Bevor Sie beginnen
Wenn Sie Microsoft Intune verwenden, müssen Sie das Gerät MDM registriert haben. Andernfalls werden die Einstellungen nicht erfolgreich angewendet. 

Weitere Informationen zum Aktivieren von MDM mit Microsoft Intune finden Sie unter [Geräteregistrierung (Microsoft Intune).](/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>Onboarding von Geräten mit Microsoft Intune

[![Abbildung der PDF-Datei mit onboarding devices to Defender for Endpoint using Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)

Sehen Sie sich die [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) oder [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Defender für Endpunkt anzuzeigen. 

Folgen Sie den Anweisungen von [Intune.](/intune/advanced-threat-protection)

Weitere Informationen zur Verwendung von Defender für Endpunkt-CSP finden Sie in [der Datei "WindowsAdvancedThreatProtection CSP"](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) und ["WindowsAdvancedThreatProtection DDF".](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)


> [!NOTE]
> - Der **Integritätsstatus für die** Richtlinie für integrierte Geräte verwendet schreibgeschützte Eigenschaften und kann nicht behoben werden.
> - Die Konfiguration der Berichterstattungshäufigkeit von Diagnosedaten ist nur für Geräte in Windows 10, Version 1703, verfügbar.


>[!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob ein Gerät ordnungsgemäß in den Dienst integriert ist. Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunkt-Gerät.](run-detection-test.md)


Sehen Sie sich die [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) oder [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Microsoft Defender für Endpunkt anzuzeigen.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboarding und Überwachen von Geräten mithilfe von Tools für die mobile Geräteverwaltung
Aus Sicherheitsgründen läuft das Paket, das für Offboard-Geräte verwendet wird, 30 Tage nach dem Datum ab, an dem es heruntergeladen wurde. Abgelaufene Offboardingpakete, die an ein Gerät gesendet werden, werden abgelehnt. Beim Herunterladen eines Offboardingpakets werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch im Paketnamen enthalten sein.

> [!NOTE]
> Onboarding- und Offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, andernfalls führt dies zu unvorhersehbaren Kollisionen.

1. Rufen Sie das Offboarding-Paket aus [Microsoft 365 Defender Portal](https://security.microsoft.com/)ab:

   1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Endpoints**  >  **Device Management**  >  **Offboarding** aus.

   1. Wählen Sie Windows 10 als Betriebssystem aus.

   1. Wählen Sie im Feld **"Bereitstellungsmethode"** die Option **"Verwaltung mobiler Geräte/Microsoft Intune"** aus.
    
   1. Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.

2. Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen. Sie sollten über eine Datei mit dem Namen *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding* verfügen.

3. Verwenden Sie die Microsoft Intune benutzerdefinierte Konfigurationsrichtlinie, um die folgenden unterstützten OMA-URI-Einstellungen bereitzustellen.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding<br/>
      Datumstyp: Zeichenfolge<br/>
      Wert: [Kopieren und Einfügen des Werts aus dem Inhalt der Datei WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding]

Weitere Informationen zu Microsoft Intune Richtlinieneinstellungen finden Sie [unter Windows 10 Richtlinieneinstellungen in Microsoft Intune.](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)


> [!NOTE]
> Der **Integritätsstatus für die Richtlinie für offboardierte Geräte** verwendet schreibgeschützte Eigenschaften und kann nicht behoben werden.

> [!IMPORTANT]
> Das Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweise auf warnungen, die es gesendet hat, werden bis zu 6 Monate lang aufbewahrt.

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10 Geräten mithilfe von Gruppenrichtlinien](configure-endpoints-gp.md)
- [Onboarding von Windows 10 Geräten mithilfe von Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](configure-endpoints-script.md)
- [Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunkt-Gerät](run-detection-test.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender für Endpunkten](troubleshoot-onboarding.md)
