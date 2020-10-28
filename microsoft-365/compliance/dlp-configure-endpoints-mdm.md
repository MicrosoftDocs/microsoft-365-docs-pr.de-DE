---
title: Integrierte Windows 10-Geräte mit Tools zur Verwaltung mobiler Geräte
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Verwenden Sie die Tools für die Verwaltung mobiler Geräte, um das Konfigurationspaket auf Geräten bereitzustellen, damit diese in den Dienst eingehen.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769481"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Integrierte Windows 10-Geräte mit Tools zur Verwaltung mobiler Geräte

**Gilt für:**

- [Microsoft 365 Endpunkt-Datenverlust Verhinderung (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

Sie können MDM-Lösungen (Mobile Device Management) zum Konfigurieren von Geräten verwenden. Microsoft 365 Endpoint Data Loss Prevention unterstützt MDMs, indem OMA-URIs zum Erstellen von Richtlinien zum Verwalten von Geräten bereitgestellt wird.


## <a name="before-you-begin"></a>Bevor Sie beginnen
Wenn Sie Microsoft InTune verwenden, muss das Gerät MDM registriert sein. Andernfalls werden Einstellungen nicht erfolgreich angewendet. 

Weitere Informationen zum Aktivieren von MDM mit Microsoft InTune finden Sie unter [Device Enrollment (Microsoft InTune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).

## <a name="onboard-devices-using-microsoft-intune"></a>Integrierte Geräte mit Microsoft InTune

Befolgen Sie die Anweisungen von [InTune](https://docs.microsoft.com/intune/advanced-threat-protection).

> [!NOTE]
> - Der **Integritäts Status für die Richtlinie für integrierte Geräte** verwendet schreibgeschützte Eigenschaften und kann nicht wiederhergestellt werden.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Extern und Überwachen von Geräten mithilfe von Tools zur Verwaltung mobiler Geräte

Aus Sicherheitsgründen läuft das Paket, das für extern-Geräte verwendet wird, 30 Tage nach dem heruntergeladenen Datum ab. Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden zurückgewiesen. Wenn Sie ein offboarding-Paket herunterladen, werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch in den Paketnamen eingeschlossen.

> [!NOTE]
> Onboarding-und offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da dies andernfalls zu unvorhersehbaren Konflikten führen kann.

1. Rufen Sie das offboarding-Paket im [Microsoft Compliance Center](https://compliance.microsoft.com/)ab.

2. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Gerät Onboarding**  >  **Offboarding** .

3. Wählen Sie im Feld **Bereitstellungsmethode** die Option **Verwaltung mobiler Geräte/Microsoft InTune** aus.
    
4. Klicken Sie auf **Paket herunterladen** , und speichern Sie die ZIP-Datei.

5. Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen werden. Sie sollten über eine Datei mit dem Namen *DeviceCompliance_valid_until_YYYY-mm-dd. offboarding* verfügen.

6. Verwenden Sie die benutzerdefinierte Konfigurationsrichtlinie von Microsoft InTune, um die folgenden unterstützten Oma-URI-Einstellungen bereitzustellen.

      Oma-URI:./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Date-Typ: String      
      Wert: [Kopieren und Einfügen des Werts aus dem Inhalt der Datei DeviceCompliance_valid_until_YYYY-mm-dd. offboarding]

Weitere Informationen zu den Microsoft InTune-Richtlinieneinstellungen finden Sie unter [Windows 10-Richtlinieneinstellungen in Microsoft InTune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).

> [!NOTE]
> Der **Integritäts Status für** die Richtlinie für offboarded-Geräte verwendet schreibgeschützte Eigenschaften und kann nicht wiederhergestellt werden.

> [!IMPORTANT]
> Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber die Daten des Geräts, einschließlich des Verweises auf bereits gemachte Warnungen, werden bis zu 6 Monate aufbewahrt.

## <a name="related-topics"></a>Verwandte Themen
- [Integrierte Windows 10-Geräte mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md)
- [Onboard-Windows 10-Geräte mit Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboard-Windows 10-Geräte mithilfe eines lokalen Skripts](dlp-configure-endpoints-script.md)
- [Onboard-VDI-Geräte (Non-persistent Virtual Desktop Infrastructure)](dlp-configure-endpoints-vdi.md)
- [Problembehandlung bei Onboarding-Problemen bei Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
