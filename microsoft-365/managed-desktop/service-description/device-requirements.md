---
title: Geräteanforderungen
description: Zusammenfassung der Mindesthardware- und Softwareanforderungen für Geräte, die mit Microsoft Managed Desktop funktionieren
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: baaebd185389e7ac1f2173aed092141067a5629f
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768890"
---
# <a name="device-requirements"></a>Geräteanforderungen

Microsoft Managed Desktop wertet regelmäßig Geräteanforderungen aus, die in den Dienst einbezogen werden sollen. In diesem Artikel werden die Hardware- und Softwareanforderungen beschrieben, die ein Gerät erfüllen muss, um mit Microsoft Managed Desktop arbeiten zu können. Sie können basierend auf diesen Anforderungen eine Liste der [bestimmten](device-list.md) Geräte überprüfen, die bereits für die Verwendung mit dem Dienst genehmigt wurden.

> [!NOTE]
> Diese Anforderungen können sich jederzeit ändern, wir werden jedoch 30 Tage über Änderungen an den Hardwareanforderungen in Diesem Fall verfügen. Die zuletzt geänderten Anforderungen sind mit **\*** gekennzeichnet. 

## <a name="check-hardware-requirements"></a>Überprüfen der Hardwareanforderungen

Neben der Überprüfung der Gerätespezifikationen können [](../get-ready/readiness-assessment-downloadable.md) Sie auch die Überprüfung der herunterladbaren Bereitschaftsbewertung verwenden, um zu überprüfen, ob ein bestimmtes Gerät die erforderlichen Anforderungen erfüllt. Dieses Tool überprüft auch Netzwerkeinstellungen und Endpunkte, die auch für die Dienstarbeit erforderlich sind.

## <a name="minimum-requirements"></a>Mindestanforderungen

Um bei Microsoft Managed Desktop registriert zu werden, muss ein Gerät alle diese Anforderungen erfüllen oder übertreffen.

### <a name="manufacturer"></a>Hersteller

Das Gerät muss von einem der folgenden Hersteller hergestellt worden sein:

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>Installierte Software

Auf dem Gerät muss diese Software vorinstalliert sein:

- Windows 10 Enterprise, Pro oder Pro Workstation Edition
- die 64-Bit-Version von Microsoft 365 Apps for Enterprise 
- Alle anwendbaren Gerätetreiber


### <a name="physical-features"></a>Physische Features

Geräte müssen über die folgenden Funktionen verfügen:

- Aktiviert für den sicheren Start von UEFI 
- Vertrauenswürdiges Plattformmodul 2.0 
- Virtualisierungsbasierte Sicherheit 
- [Hypervisorgeschützte Codeintegrität,](/windows-hardware/drivers/bringup/device-guard-and-credential-guard) die vom BIOS unterstützt wird

Weitere Informationen zu diesen Funktionen und den technologien, die der Dienst verwendet, finden Sie unter [Microsoft Managed Desktop-Technologien](../intro/technologies.md).

> [!NOTE]
> ARM Prozessoren werden nicht unterstützt.

Geräte sollten die folgenden Speicher- und Speichergrenzwerte erfüllen oder überschreiten:

- Das Startlaufwerk muss einen anderen Typ als eine Festplatte sein. Ssd-, NVMe- und eMMC-Laufwerke sind beispielsweise alle gültigen Optionen.
- Das Startlaufwerk muss eine Kapazität von mindestens 128 GB haben.
- Interner Gerätespeicher (RAM) muss mindestens 8 GB groß sein.

Wenn das Gerät nach dem 1. Juli 2020 hergestellt wurde, sollte es auch über eine IR-Kamera, einen Fingerabdruckleser oder beides verfügen, um [Windows Hello zu unterstützen.](/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-features"></a>Empfohlene Features

Ihre Benutzer haben eine wesentlich bessere Erfahrung, wenn Sie Geräte mit den folgenden Features auswählen:

- Entweder ein Intel vPro-Plattformprozessor oder ein AMD Ryzen Pro-Prozessor
- Startlaufwerk des SSD-Typs mit einer Kapazität von mindestens 256 GB
- Interner Gerätespeicher (RAM) von mindestens 16 GB
- Unterstützung für modernen Standbymodus
- Gerät vom Typ Secured-Core-PC
- Unterstützt Kernel-DMA-Schutz
