---
title: Microsoft Defender für Endpunkt-Gerätesteuerung – Wechselmedienschutz Storage
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
ms.openlocfilehash: 55171429d3ea447de32eb7e2ec12b8b2c3542e95
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861707"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender für Endpunkt-Gerätesteuerung – Wechselmedienschutz Storage

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint Device Control Removable Storage Protection verhindert, dass Benutzer oder Computer oder beide nicht autorisierte Wechselmedien verwenden.

## <a name="protection-policies"></a>Schutzrichtlinien

### <a name="device-installation"></a>Geräteinstallation

**Funktionen** – Verhindern der Installation mit oder ohne Ausschluss basierend auf verschiedenen Geräteeigenschaften.

**Windows 10 Supportdetails**
- Auf Computerebene angewendet: Die gleiche Richtlinie gilt für jeden angemeldeten Benutzer.
- Unterstützt MEM und GPO.
- Unterstützt '[Geräteeigenschaften](#device-properties)' wie aufgeführt.
- Weitere Informationen zu Windows finden Sie unter [Steuern von USB-Geräten und anderen Wechselmedien mit Microsoft Defender für Endpunkt.](control-usb-devices-using-intune.md)

**Unterstützte Plattform** – Windows 10

**MacOS-Supportdetails**
- Auf Computerebene angewendet: Die gleiche Richtlinie gilt für jeden angemeldeten Benutzer
- MacOS-spezifische Informationen finden Sie unter [Gerätesteuerelement für macOS.](mac-device-control-overview.md)
 
**Unterstützte Plattform** – macOS- Wiesn 10.15.4+ (mit aktivierten Systemerweiterungen)

### <a name="removable-storage-access-control"></a>Zugriffssteuerung für Wechselmedien

**Capabilities**
- *Überwachung* Lese-, Schreib- oder Ausführungszugriff auf Wechselmedien basierend auf verschiedenen Geräteeigenschaften, mit oder ohne Ausschluss.
- *Verhindern* Lese- oder Schreibzugriff oder Ausführen des Zugriffs mit oder ohne Ausschluss – Zulassen eines bestimmten Geräts basierend auf verschiedenen Geräteeigenschaften.

**Windows 10 Supportdetails**
- Wird entweder auf computer oder benutzer oder beides angewendet – nur bestimmten Personen, die Lese-/Schreib-/Ausführungszugriff auf bestimmte Wechselmedien auf einem bestimmten Computer ausführen, gestatten.
- Unterstützt MEM-OMA-URI und GPO.
- Unterstützt '[Geräteeigenschaften](#device-properties)' wie aufgeführt.
- Informationen zum Feature in Windows finden Sie unter ["Zugriffssteuerung für Wechselmedien".](device-control-removable-storage-access-control.md)

**Unterstützte Plattform** – Windows 10

**MacOS-Supportdetails**
- Auf Computerebene angewendet: Die gleiche Richtlinie gilt für jeden angemeldeten Benutzer.
- MacOS-spezifische Informationen finden Sie unter [Gerätesteuerelement für macOS.](mac-device-control-overview.md)
 
**Unterstützte Plattform** – macOS- Wiesn 10.15.4+ (mit aktivierten Systemerweiterungen)

### <a name="windows-portable-device-access-control"></a>Windows Zugriffssteuerung für tragbare Geräte

**Funktionen** – Verweigern des Lese- oder Schreibzugriffs auf alle [Windows tragbaren Geräte,](/windows-hardware/drivers/portable/)z. B.: Tablet, iPhone.

**Beschreibung**
- Wird entweder auf Computer oder Benutzer oder auf beide Angewendet.
- Unterstützt MEM-OMA-URI und GPO.

**Unterstützte Plattform** – Windows 10

### <a name="endpoint-dlp-removable-storage"></a>Endpunkt-DLP-Wechselmedien

**Funktionen** – Überwachen oder Warnen oder Verhindern, dass ein Benutzer ein Element oder Informationen auf Wechselmedien oder USB-Geräte kopiert.

**Beschreibung –** Weitere Informationen zu Windows finden Sie unter [ Informationen zu Microsoft 365 Verhinderung von Datenverlust](../../compliance/endpoint-dlp-learn-about.md)am Endpunkt .

**Unterstützte Plattform** – Windows 10

### <a name="bitlocker"></a>BitLocker 

**Capabilities**
- Blockieren Von Daten, die auf Wechseldatenträger geschrieben werden sollen, die nicht geschützt BitLocker sind.
- Blockieren des Zugriffs auf Wechseldatenträger, es sei denn, sie wurden auf einem Computer im Besitz Ihrer Organisation verschlüsselt.
 
**Beschreibung** – Weitere Informationen zu Windows finden Sie unter [BitLocker – Wechseldatenträger Einstellungen](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).

**Unterstützte Plattform** – Windows 10

## <a name="device-properties"></a>Geräteeigenschaften

Mit Microsoft Defender für Endpunkt-Gerätesteuerung ( Removable Storage Protection) können Sie den Wechselmedienzugriff basierend auf den in der folgenden Tabelle beschriebenen Eigenschaften einschränken:


|Eigenschaftenname  |Anwendbare Richtlinien  |Gilt für Betriebssysteme  |Beschreibung  |
|---------|---------|---------|---------|
|Geräteklasse    |     [Steuern von USB-Geräten und anderen Wechselmedien mit Microsoft Defender für Endpunkt](control-usb-devices-using-intune.md)     |   Windows      |  Informationen zu Geräte-ID-Formaten finden Sie unter [Geräteeinrichtungsklasse.](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors) **Hinweis:** Die Geräteinstallation kann auf alle Geräte angewendet werden, nicht nur auf Wechselmedien.       |
|Primäre ID   |     Zugriffssteuerung für Wechselmedien    |   Windows      |      Die primäre ID enthält Wechselmedien und CD/DVD.   |
|Geräte-ID     |  [Steuern von USB-Geräten und anderen Wechselmedien mit Microsoft Defender für Endpunkt;](control-usb-devices-using-intune.md) Zugriffssteuerung für Wechselmedien       |      Windows   |    Informationen zu Geräte-ID-Formaten finden Sie unter [Standard-USB-IDs,](/windows-hardware/drivers/install/standard-usb-identifiers)z. B. USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07      |
|Hardware-ID     |     [Steuern von USB-Geräten und anderen Wechselmedien mit Microsoft Defender für Endpunkt;](control-usb-devices-using-intune.md) Zugriffssteuerung für Wechselmedien    |     Windows    |    Eine Zeichenfolge identifiziert das Gerät im System, z. B. USBSTOR\DiskGeneric_Flash_Disk______8.07; **Hinweis:** Die Hardware-ID ist nicht eindeutig. unterschiedliche Geräte können denselben Wert aufweisen.|
|Instanz-ID    | Geräteinstallation; Zugriffssteuerung für Wechselmedien     |     Windows    |   Eine Zeichenfolge identifiziert das Gerät im System eindeutig, z. B. USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0      |
|Anzeigename     |     Zugriffssteuerung für Wechselmedien    |   Windows      |    Eine an das Gerät angefügte Zeichenfolge, z. B. generic Flash Disk USB Device     |
|Anbieter-ID/Produkt-ID     |  Zugriffssteuerung für Wechselmedien       |   Windows Mac      |     Die Anbieter-ID ist der vierstellige Anbietercode, den der USB-Ausschuss dem Anbieter zuweist. Die Produkt-ID ist der vierstellige Produktcode, den der Anbieter dem Gerät zuweist. Unterstützt Platzhalter.    |
|Seriennummern-ID     |     Zugriffssteuerung für Wechselmedien    |      Windows Mac   |     Beispiel: <SerialNumberId>002324B534BCB431B000058A</SerialNumberId>    |

## <a name="related-topic"></a>Verwandtes Thema

- [Microsoft Defender für Endpunkt-Gerätesteuerung – Wechselmedien Storage Zugriffssteuerung](device-control-removable-storage-access-control.md)

