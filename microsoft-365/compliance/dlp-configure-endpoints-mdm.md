---
title: Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten
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
description: Verwenden Sie Tools für die Verwaltung mobiler Geräte, um das Konfigurationspaket auf Geräten zu bereitstellen, sodass sie in den Dienst integrierte werden.
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917991"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten

**Gilt für:**

- [Microsoft 365 Endpoint Data Loss Prevention (DLP)](./endpoint-dlp-learn-about.md)

Sie können Mobile Device Management (MDM)-Lösungen verwenden, um Geräte zu konfigurieren. Microsoft 365 Endpoint Data Loss Prevention unterstützt MDMs, indem OMA-URIs richtlinien zum Verwalten von Geräten bereitstellen.


## <a name="before-you-begin"></a>Bevor Sie beginnen
Wenn Sie Microsoft Intune verwenden, muss das Gerät MDM registriert sein. Andernfalls werden einstellungen nicht erfolgreich angewendet. 

Weitere Informationen zum Aktivieren von MDM mit Microsoft Intune finden Sie unter [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).

## <a name="onboard-devices-using-microsoft-intune"></a>Onboarding von Geräten mithilfe von Microsoft Intune

Befolgen Sie die Anweisungen von [Intune](/intune/advanced-threat-protection).

> [!NOTE]
> - Die **Richtlinie Integritätsstatus für integrierte Geräte** verwendet schreibgeschützte Eigenschaften und kann nicht behoben werden.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboard und Überwachen von Geräten mithilfe von Mobile Device Management Tools

Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab. Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt. Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.

> [!NOTE]
> Onboarding- und Offboardingrichtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da andernfalls unvorhersehbare Kollisionen verursacht werden.

1. Holen Sie sich das offboarding-Paket aus [dem Microsoft Compliance Center](https://compliance.microsoft.com/).

2. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Geräte onboarding**  >  **Offboarding aus.**

3. Wählen Sie **im Feld Bereitstellungsmethode** die Option **Mobile Geräteverwaltung /Microsoft Intune aus.**
    
4. Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei.

5. Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen. Sie sollten über eine Datei namens *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding verfügen.*

6. Verwenden Sie die benutzerdefinierte Microsoft Intune-Konfigurationsrichtlinie, um die folgenden unterstützten OMA-URI-Einstellungen bereitzustellen.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Datumstyp: Zeichenfolge      
      Wert: [Kopieren und Einfügen des Werts aus dem Inhalt der DeviceCompliance_valid_until_YYYY-MM-DD.offboarding-Datei]

Weitere Informationen zu Microsoft Intune-Richtlinieneinstellungen finden Sie unter [Windows 10-Richtlinieneinstellungen in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).

> [!NOTE]
> Die **Richtlinie Integritätsstatus für Offboardgeräte** verwendet schreibgeschützte Eigenschaften und kann nicht behoben werden.

> [!IMPORTANT]
> Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweis auf alle Warnungen, die es erhalten hat, werden für bis zu 6 Monate aufbewahrt.

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10-Geräten mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md)
- [Onboarding von Windows 10-Geräten mithilfe von Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](dlp-configure-endpoints-script.md)
- [Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](dlp-configure-endpoints-vdi.md)
- [Behandeln von Problemen mit dem Microsoft Defender Advanced Threat Protection-Onboarding](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)