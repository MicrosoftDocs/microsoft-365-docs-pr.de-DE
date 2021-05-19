---
title: Microsoft Defender for Endpoint Device Control Removable Storage Protection
description: Verstehen der "Funktionen, die verhindern, dass Benutzer oder Computer oder beide nicht autorisierte Wechselmedien verwenden
keywords: Wechselmedien
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c9b97c2157ba8090628af23b2ab54cf38f04d8c6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538387"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender for Endpoint Device Control Removable Storage Protection

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint Device Control Storage Protection verhindert, dass Benutzer oder Computer oder beide nicht autorisierte Wechselmedien verwenden.

## <a name="protection-policies"></a>Schutzrichtlinien

### <a name="device-installation"></a>Geräteinstallation

**Funktionen** – Verhindern der Installation mit oder ohne Ausschluss basierend auf verschiedenen Geräteeigenschaften.

**Beschreibung**
- Auf Computerebene angewendet: Die gleiche Richtlinie gilt für alle angemeldeten Benutzer.
- Unterstützt MEM und GPO.
- Unterstützte '[Geräteeigenschaften](#device-properties)' wie aufgeführt.
- Weitere Informationen zu Windows finden Sie unter Steuern von USB-Geräten und anderen Wechselmedien mithilfe [von Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).

**Unterstützte Plattform** – Windows 10

**Beschreibung**
- Auf Computerebene angewendet: Die gleiche Richtlinie gilt für alle angemeldeten Benutzer
- MacOS-spezifische Informationen finden Sie unter [Gerätesteuerelement für macOS](mac-device-control-overview.md).
 
**Unterstützte Plattform** – macOS Catalina 10.15.4+ (mit aktivierten Systemerweiterungen)

### <a name="removable-storage-access-control"></a>Zugriffssteuerung für Wechselmedien

**Capabilities**
- *Überwachung* Lese-, Schreib- oder Ausführungszugriff auf Wechseldatenträger basierend auf verschiedenen Geräteeigenschaften, mit oder ohne Ausschluss.
- *Verhindern* Lese- oder Schreibzugriff oder Ausführen des Zugriffs mit oder ohne Ausschluss – Zulassen eines bestimmten Geräts basierend auf verschiedenen Geräteeigenschaften.

**Beschreibung**
- Wird auf einem Computer oder Benutzer oder auf beiden Angewendet – nur bestimmten Personen, die Lese-/Schreib-/Ausführungszugriff auf bestimmte Wechseldatenträger auf einem bestimmten Computer ausführen, erlauben.
- Unterstützt MEM OMA-URI und GPO.
- Unterstützte '[Geräteeigenschaften](#device-properties)' wie aufgeführt.
- Informationen zu features in Windows finden Sie unter [Wechselmedienzugriffssteuerung](device-control-removable-storage-access-control.md).

**Unterstützte Plattform** – Windows 10

**Beschreibung**
- Auf Computerebene angewendet: Die gleiche Richtlinie gilt für alle angemeldeten Benutzer.
- MacOS-spezifische Informationen finden Sie unter [Gerätesteuerelement für macOS](mac-device-control-overview.md).
 
**Unterstützte Plattform** – macOS Catalina 10.15.4+ (mit aktivierten Systemerweiterungen)

### <a name="windows-portable-device-access-control"></a>Windows Zugriffssteuerung für tragbare Geräte

**Funktionen** – Verweigern des Lese- oder Schreibzugriffs auf [Windows tragbaren](/windows-hardware/drivers/portable/)Gerät, z. B. Tablet, iPhone.

**Beschreibung**
- Wird auf dem Computer oder Benutzer oder auf beiden angewendet.
- Unterstützt MEM OMA-URI und GPO.

**Unterstützte Plattform** – Windows 10

### <a name="endpoint-dlp-removable-storage"></a>Endpunkt-DLP-Wechseldatenträger

**Funktionen** – Überwachen oder Warnen oder Verhindern, dass ein Benutzer ein Element oder Informationen auf Wechselmedien oder USB-Geräte kopiert.

**Beschreibung** – Weitere Informationen zu Windows finden Sie [unter Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).

**Unterstützte Plattform** – Windows 10

### <a name="bitlocker"></a>BitLocker 

**Capabilities**
- Blockieren von Daten, die auf Wechseldatenträger geschrieben werden sollen, die nicht BitLocker sind.
- Blockieren des Zugriffs auf Wechseldatenträger, es sei denn, sie wurden auf einem Computer im Besitz Ihrer Organisation verschlüsselt.
 
**Beschreibung** – Weitere Informationen zu Windows finden Sie [unter BitLocker – Wechseldatenträger Einstellungen](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).

**Unterstützte Plattform** – Windows 10

## <a name="device-properties"></a>Geräteeigenschaften

Mit Microsoft Defender for Endpoint Device Control Removable Storage Protection können Sie den Wechselspeicherzugriff basierend auf den in der folgenden Tabelle beschriebenen Eigenschaften einschränken:


|Eigenschaftenname  |Anwendbare Richtlinien  |Gilt für Betriebssysteme  |Beschreibung  |
|---------|---------|---------|---------|
|Geräteklasse    |     [Steuern von USB-Geräten und anderen Wechselmedien mithilfe von Microsoft Defender for Endpoint](control-usb-devices-using-intune.md)     |   Windows      |  Weitere Informationen zu Geräte-ID-Formaten finden Sie unter [Geräteeinrichtungsklasse](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors). **Hinweis:** Die Geräteinstallation kann auf alle Geräte angewendet werden, nicht nur auf Wechselmedien.       |
|Primäre ID   |     Zugriffssteuerung für Wechselmedien    |   Windows      |      Die primäre ID umfasst Wechseldatenträger und CD/DVD.   |
|Geräte-ID     |  [Steuern von #A0 und anderen Wechselmedien mithilfe von Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Zugriffssteuerung für Wechselmedien       |      Windows   |    Weitere Informationen zu Geräte-ID-Formaten finden Sie unter [Standard USB Identifiers,](/windows-hardware/drivers/install/standard-usb-identifiers)z. B. USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07      |
|Hardware-ID     |     [Steuern von #A0 und anderen Wechselmedien mithilfe von Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Zugriffssteuerung für Wechselmedien    |     Windows    |    Eine Zeichenfolge hat das Gerät im System identifiziert, z. B. USBSTOR\DiskGeneric_Flash_Disk______8.07; **Hinweis:** Hardware-ID ist nicht eindeutig; unterschiedliche Geräte können denselben Wert haben.|
|Instanz-ID    | Geräteinstallation; Zugriffssteuerung für Wechselmedien     |     Windows    |   Eine Zeichenfolge identifiziert das Gerät im System eindeutig, z. B. USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0      |
|Anzeigename     |     Zugriffssteuerung für Wechselmedien    |   Windows      |    Eine zeichenfolge, die an das Gerät angefügt ist, z. B. generic Flash Disk USB Device     |
|Hersteller-ID/Produkt-ID     |  Zugriffssteuerung für Wechselmedien       |   Windows Mac      |     Die Hersteller-ID ist der vierstellige Anbietercode, den der USB-Ausschuss dem Anbieter zurentsprecht. Die Produkt-ID ist der vierstellige Produktcode, den der Hersteller dem Gerät zur zuordnen hat. Unterstützung eines Platzhalters.    |
|Serial NumberId     |     Zugriffssteuerung für Wechselmedien    |      Windows Mac   |     Beispiel: <SerialNumberId>002324B534BCB431B000058A</SerialNumberId>    |

## <a name="related-topic"></a>Verwandtes Thema

- [Microsoft Defender for Endpoint Device Control Wechseldatenträger Storage Zugriffssteuerung](device-control-removable-storage-access-control.md)

