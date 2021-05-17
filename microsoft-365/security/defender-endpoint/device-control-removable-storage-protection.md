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
ms.openlocfilehash: ec5cfa78852d65db808c4e853f90f5639df25d6f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300208"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender for Endpoint Device Control Removable Storage Protection

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint Device Control Removable Storage Protection verhindert, dass Benutzer oder Computer nicht autorisierte Wechselmedien verwenden.

**Microsoft Defender for Endpoint Removable Storage Protection**


|Richtlinie  |Funktion |Beschreibung  |
|---------|---------|---------|
|Geräteinstallation    |  Verhindern der Installation mit oder ohne Ausschluss – Zulassen bestimmter Geräte basierend auf verschiedenen Eigenschaften; Weitere Informationen finden Sie im Abschnitt [Geräteeigenschaften](#device-properties) unten.        |    Funktioniert auf dem Computer: Unterschiedliche Benutzer, die sich beim gleichen Computer anmelden, werden durch dieselbe Richtlinie eingeschränkt. Weitere Informationen finden Sie unter [Steuern von USB-Geräten und](control-usb-devices-using-intune.md)anderen Wechselmedien mithilfe von Microsoft Defender for Endpoint .     |
|Zugriffssteuerung für Wechselmedien      | (1) Überwachung des Lese-, Schreib- oder Ausführungszugriffs auf Wechseldatenträger basierend auf verschiedenen Geräteeigenschaften, mit oder ohne Ausnahme. Weitere Informationen finden Sie im Abschnitt [Geräteeigenschaften](#device-properties) unten. (2) Verhindern des Lese-, Schreib- oder Ausführungszugriffs mit oder ohne Ausschluss – Bestimmte Geräte basierend auf verschiedenen Geräteeigenschaften zulassen; Weitere Informationen zu den Geräteeigenschaften finden Sie im Abschnitt [Geräteeigenschaften](#device-properties) unten.     |     Funktioniert auf einem Computer oder einem Benutzer oder auf beiden: Nur bestimmten Personen, die Lese-/Schreib-/Ausführungszugriff auf bestimmte Wechseldatenträger auf einem bestimmten Computer ausführen, erlauben; Informationen zum Feature in Windows finden Sie unter [Wechselmedienzugriffssteuerung](device-control-removable-storage-access-control.md); Informationen zum Feature in Mac finden Sie [unter Gerätesteuerung für macOS](mac-device-control-overview.md).     |
|Endpunkt-DLP-Wechseldatenträger      |    Überwachen oder warnen oder verhindern, dass ein Benutzer ein Element oder Informationen auf Wechselmedien oder USB-Geräte kopiert.     |  Weitere Informationen finden Sie unter [Microsoft Endpoint DLP](/compliance/endpoint-dlp-learn-about.md).       |
|BitLocker    |     Blockieren von Daten, die auf Wechseldatenträger geschrieben werden sollen, die nicht bitLocker geschützt sind: Blockieren sie den Zugriff auf Wechseldatenträger, es sei denn, sie wurden auf einem Computer verschlüsselt, der sich im Besitz Ihrer Organisation befindet.    |   Weitere Informationen finden Sie unter BitLocker – [Wechseldatenträgereinstellungen](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings#bitlocker---removable-drive-settings.md).      |

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

- [Microsoft Defender for Endpoint Device Control Wechseldatenträgerzugriffssteuerung](device-control-removable-storage-access-control.md)
