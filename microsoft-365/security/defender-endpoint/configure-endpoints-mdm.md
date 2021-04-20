---
title: Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten
description: Verwenden Sie Tools für die Verwaltung mobiler Geräte, um das Konfigurationspaket auf Geräten zu bereitstellen, sodass sie in den Dienst integrierte werden.
keywords: Onboarding von Geräten mithilfe von mdm, Geräteverwaltung, Onboarding von Windows ATP-Geräten, Onboarding von Microsoft Defender for Endpoint-Geräten, mdm
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
ms.openlocfilehash: f3042ef9ced11ebc5439308d2781528d5267975f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893613"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

Sie können Mobile Device Management (MDM)-Lösungen verwenden, um Geräte zu konfigurieren. Defender for Endpoint unterstützt MDMs, indem OMA-URIs zum Erstellen von Richtlinien zum Verwalten von Geräten bereitstellen.

Weitere Informationen zur Verwendung von Defender for Endpoint CSP finden Sie unter [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) und [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).

## <a name="before-you-begin"></a>Vorbereitung
Wenn Sie Microsoft Intune verwenden, muss das Gerät MDM registriert sein. Andernfalls werden einstellungen nicht erfolgreich angewendet. 

Weitere Informationen zum Aktivieren von MDM mit Microsoft Intune finden Sie unter [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).

## <a name="onboard-devices-using-microsoft-intune"></a>Onboarding von Geräten mithilfe von Microsoft Intune

[![Abbildung der PDF mit Onboardinggeräten für Defender for Endpoint mithilfe von Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)

Sehen Sie sich [die PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  oder  [Visio-Datei](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Defender for Endpoint zu sehen. 

Befolgen Sie die Anweisungen von [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).

Weitere Informationen zur Verwendung von Defender for Endpoint CSP finden Sie unter [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) und [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).


> [!NOTE]
> - Die **Richtlinie Integritätsstatus für integrierte Geräte** verwendet schreibgeschützte Eigenschaften und kann nicht behoben werden.
> - Die Konfiguration der Häufigkeit der Diagnosedatenberichte ist nur für Geräte unter Windows 10, Version 1703, verfügbar.


>[!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob ein Gerät ordnungsgemäß in den Dienst integrierte wurde. Weitere Informationen finden Sie unter Ausführen eines Erkennungstests auf einem neu integrierten [Microsoft Defender for Endpoint-Gerät.](run-detection-test.md)


Sehen Sie sich [die PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  oder  [Visio-Datei](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Microsoft Defender for Endpoint zu sehen.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboard und Überwachen von Geräten mithilfe von Mobile Device Management Tools
Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab. Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt. Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.

> [!NOTE]
> Onboarding- und Offboardingrichtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da andernfalls unvorhersehbare Kollisionen verursacht werden.

1. Das offboarding-Paket aus [dem Microsoft Defender Security Center erhalten:](https://securitycenter.windows.com/)

   1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Offboarding aus.**

   1. Wählen Sie Windows 10 als Betriebssystem aus.

   1. Wählen Sie **im Feld Bereitstellungsmethode** die Option **Mobile Geräteverwaltung /Microsoft Intune aus.**
    
   1. Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei.

2. Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen. Sie sollten über eine Datei namens *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding verfügen.*

3. Verwenden Sie die benutzerdefinierte Microsoft Intune-Konfigurationsrichtlinie, um die folgenden unterstützten OMA-URI-Einstellungen bereitzustellen.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding<br/>
      Datumstyp: Zeichenfolge<br/>
      Wert: [Kopieren und Einfügen des Werts aus dem Inhalt der WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding-Datei]

Weitere Informationen zu Microsoft Intune-Richtlinieneinstellungen finden Sie unter [Windows 10-Richtlinieneinstellungen in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).


> [!NOTE]
> Die **Richtlinie Integritätsstatus für Offboardgeräte** verwendet schreibgeschützte Eigenschaften und kann nicht behoben werden.

> [!IMPORTANT]
> Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweis auf alle Warnungen, die es erhalten hat, werden für bis zu 6 Monate aufbewahrt.

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10-Geräten mithilfe von Gruppenrichtlinien](configure-endpoints-gp.md)
- [Onboarding von Windows 10-Geräten mithilfe von Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](configure-endpoints-script.md)
- [Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender for Endpoint-Gerät](run-detection-test.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender for Endpoint](troubleshoot-onboarding.md)
