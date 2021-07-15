---
title: Geräteanforderungen
description: Zusammenfassung der Mindestanforderungen an Hardware und Software für Geräte, die mit Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b17585f7449f1151c7a5f5cd75d06b8e723fbe4b
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438012"
---
# <a name="device-requirements"></a>Geräteanforderungen

Microsoft Managed Desktop überprüft regelmäßig die Geräteanforderungen, die in den Dienst einbezogen werden sollen. In diesem Artikel werden die Hardware- und Softwareanforderungen beschrieben, die ein Gerät erfüllen muss, um mit Microsoft Managed Desktop arbeiten zu können. Anhand dieser Anforderungen können Sie eine Liste bestimmter Geräte überprüfen, die bereits für die Verwendung mit dem Dienst genehmigt wurden. Filtern nach Microsoft Managed Desktop auf der Website ["Shop Windows 10 Pro Business Devices"](https://www.microsoft.com/windowsforbusiness/view-all-devices)

> [!NOTE]
> Diese Anforderungen können sich jederzeit ändern, aber wir werden 30 Tage lang über Änderungen der Hardwareanforderungen informieren. Die anforderungen, die zuletzt geändert wurden, sind mit **\*** gekennzeichnet. 

## <a name="check-hardware-requirements"></a>Überprüfen der Hardwareanforderungen

Neben der Überprüfung von Gerätespezifikationen können Sie auch die herunterladbare [Bereitschaftsbewertungsprüfung](../get-ready/readiness-assessment-downloadable.md) verwenden, um zu überprüfen, ob ein bestimmtes Gerät die erforderlichen Anforderungen erfüllt. Dieses Tool überprüft auch die Netzwerkeinstellungen und Endpunkte, die auch erforderlich sind, damit der Dienst funktioniert.

## <a name="minimum-requirements"></a>Mindestanforderungen

Um in Microsoft Managed Desktop registriert zu werden, muss ein Gerät alle diese Anforderungen erfüllen oder überschreiten.

### <a name="manufacturer"></a>Hersteller

Das Gerät muss von einem dieser Hersteller erstellt worden sein:

- Dell
- Hp
- Lenovo
- Microsoft


### <a name="installed-software"></a>Installierte Software

Auf dem Gerät muss diese Software vorinstalliert sein:

- Windows 10 Enterprise, Pro oder Pro Workstation Edition
- die 64-Bit-Version von Microsoft 365 Apps for Enterprise 
- Alle anwendbaren Gerätetreiber

> [!NOTE]
> Windows 11 ist eine zusätzliche Option für vorinstallierte Software, sobald sie die allgemeine Verfügbarkeit erreicht hat.
>
### <a name="physical-features"></a>Physische Features

Geräte müssen über folgende Funktionen verfügen:

- Aktiviert für den sicheren UEFI-Start 
- Trusted Platform Module 2.0 
- Virtualisierungsbasierte Sicherheit 
- [Hypervisorgeschützte Codeintegrität,](/windows-hardware/drivers/bringup/device-guard-and-credential-guard) die vom BIOS unterstützt wird

Weitere Informationen zu diesen Funktionen und den damit verbundenen Technologien, die der Dienst verwendet, finden Sie unter [Microsoft Managed Desktop Technologien.](../intro/technologies.md)

> [!NOTE]
>- ARM-Prozessoren werden nicht unterstützt.
>- Windows 11 hat zusätzliche [Hardwareanforderungen.](/windows/whats-new/windows-11-requirements)

Geräte sollten die folgenden Grenzwerte für Speicher und Speicher erfüllen oder überschreiten:

- Das Startlaufwerk muss einen anderen Typ als eine Festplatte aufweisen. Beispielsweise sind SSD-, NVMe- und eMMC-Laufwerke gültige Optionen.
- Das Startlaufwerk muss über eine Kapazität von mindestens 128 GB verfügen.
- Der interne Gerätespeicher (RAM) muss gleich oder größer als 8 GB sein.

Wenn das Gerät nach dem 1. Juli 2020 erstellt wurde, sollte es auch über eine IR-Kamera, einen Fingerabdruckleser oder beides verfügen, um [Windows Hello](/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)zu unterstützen.

## <a name="recommended-features"></a>Empfohlene Features

Ihre Benutzer haben eine viel bessere Erfahrung, wenn Sie Geräte mit diesen Features auswählen:

- Entweder ein Intel vPro-Plattform-Prozessor oder ein AMD Pro prozessor
- Startlaufwerk des SSD-Typs mit einer Kapazität von mindestens 256 GB
- Interner Gerätespeicher (RAM) von mindestens 16 GB
- Unterstützung für modernen Standbymodus
- Das Gerät hat den PC-Typ "Secured-Core"
- Unterstützt Kernel-DMA-Schutz
