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
ms.openlocfilehash: a6b5cbbcb2f48797130b080d9d1dd1e6427d4fb8
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110051"
---
# <a name="device-requirements"></a>Geräteanforderungen

Microsoft Managed Desktop wertet regelmäßig die Geräteanforderungen aus, die in den Dienst einbezogen werden sollen. In diesem Artikel werden die Hardware- und Softwareanforderungen beschrieben, die ein Gerät erfüllen muss, um mit Microsoft Managed Desktop arbeiten zu können. Sie können basierend auf [](device-list.md) diesen Anforderungen eine Liste bestimmter Geräte überprüfen, die bereits für die Verwendung mit dem Dienst genehmigt wurden.

> [!NOTE]
> Diese Anforderungen können sich jederzeit ändern, wir werden jedoch 30 Tage über Änderungen an den Hardwareanforderungen verfügen. Die Anforderungen, die zuletzt geändert wurden, sind mit **\*** gekennzeichnet. 

## <a name="check-hardware-requirements"></a>Überprüfen der Hardwareanforderungen

Neben der Überprüfung der Gerätespezifikationen können [](../get-ready/readiness-assessment-downloadable.md) Sie auch die herunterladbare Überprüfung der Bereitschaftsbewertung verwenden, um sicherzustellen, dass ein bestimmtes Gerät die erforderlichen Anforderungen erfüllt. Dieses Tool überprüft außerdem Netzwerkeinstellungen und Endpunkte, die auch für die Dienstarbeit erforderlich sind.

## <a name="minimum-requirements"></a>Mindestanforderungen

Um bei Microsoft Managed Desktop registriert zu werden, muss ein Gerät alle diese Anforderungen erfüllen oder überschreiten.

### <a name="manufacturer"></a>Hersteller

Das Gerät muss von einem der folgenden Hersteller hergestellt worden sein:

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>Installierte Software

Auf dem Gerät muss diese Software vorinstalliert sein:

- Windows 10 Enterprise, Pro oder Pro Workstation Edition
- Die 64-Bit-Version Microsoft Office Klick-und-Ausführen 
- Alle anwendbaren Gerätetreiber


### <a name="physical-features"></a>Physische Features

Geräte müssen über die folgenden Funktionen verfügen:

- Aktiviert für den sicheren Start von UEFI 
- Trusted Platform Module 2.0 
- Virtualisierungsbasierte Sicherheit 
- Unterstützt hypervisorgeschützte Codeintegrität 

Weitere Informationen zu diesen Funktionen und den zugehörigen Technologien, die der Dienst verwendet, finden Sie unter [Microsoft Managed Desktop-Technologien.](../intro/technologies.md)

> [!NOTE]
> ARM werden nicht unterstützt.

Geräte sollten die folgenden Grenzwerte für Speicher und Arbeitsspeicher erfüllen oder überschreiten:

- Das Startlaufwerk muss einen anderen Typ als eine Festplatte haben. Beispielsweise sind SSD-, NVMe- und eMMC-Laufwerke eine gültige Wahl.
- Das Startlaufwerk muss eine Kapazität von mindestens 128 GB haben.

Wenn das Gerät nach dem 1. Juli 2020 hergestellt wurde, sollte es auch über eine IR-Kamera, einen Fingerabdruckleser oder beides verfügen, um [Windows Hello zu unterstützen.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-requirements"></a>Empfohlene Anforderungen

Obwohl dies keine absoluten Anforderungen sind, ist die Benutzererfahrung wesentlich besser, wenn Sie Geräte mit den folgenden Features auswählen:

- Entweder ein Intel vPro-Plattform-Prozessor oder ein AMD Ryzen Pro-Prozessor
- Startlaufwerk des SSD-Typs mit einer Kapazität von mindestens 256 GB
- Unterstützung für modernen Standbymodus
- Gerät vom Typ "Gesicherter Kern-PC"
- Unterstützt Kernel-DMA-Schutz
