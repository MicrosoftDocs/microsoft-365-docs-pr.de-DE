---
title: Onboarding von Methoden und Tools für Windows 10 Geräte
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
description: Onboarding Windows 10 Geräte, damit sie Sensordaten an die Microsoft 365 Compliance-Lösungen senden können
ms.openlocfilehash: 676fb3a7ffcae8d108fd9b7fabe61bb78b7e1744
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341700"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Onboarding-Tools und -Methoden für Windows 10-Computer

**Gilt für:**
- [Microsoft 365 Verhinderung von Datenverlust am Endpunkt (Endpoint Data Loss Prevention, DLP)](./endpoint-dlp-learn-about.md)

Geräte in Ihrer Organisation müssen so konfiguriert sein, dass der Microsoft 365 Endpunkt-Dienst zur Verhinderung von Datenverlust Sensordaten von ihnen abrufen kann. Es gibt verschiedene Methoden und Bereitstellungstools, mit denen Sie die Geräte in Ihrer Organisation konfigurieren können.

Die folgenden Bereitstellungstools und -methoden werden unterstützt:

- Gruppenrichtlinie
- Microsoft Endpoint Configuration Manager
- Verwaltung mobiler Geräte (einschließlich Microsoft Intune)
- Lokales Skript

## <a name="in-this-section"></a>Inhalt dieses Abschnitts
Thema | Beschreibung
:---|:---
[Onboarding von Windows 10 Geräten mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md) | Verwenden Sie gruppenrichtlinien, um das Konfigurationspaket auf Geräten bereitzustellen.
[Onboarding von Windows Geräten mithilfe von Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md) | Sie können entweder Microsoft Endpoint Configuration Manager (aktuelle Verzweigung), Version 1606, oder Microsoft Endpoint Configuration Manager (aktuelle Verzweigung), Version 1602 oder früher, verwenden, um das Konfigurationspaket auf Geräten bereitzustellen.
[Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](dlp-configure-endpoints-mdm.md) | Verwenden Sie Tools für die mobile Geräteverwaltung oder Microsoft Intune, um das Konfigurationspaket auf dem Gerät bereitzustellen.
[Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](dlp-configure-endpoints-script.md) | Erfahren Sie, wie Sie das lokale Skript verwenden, um das Konfigurationspaket auf Endpunkten bereitzustellen.
[Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](dlp-configure-endpoints-vdi.md) | Erfahren Sie, wie Sie das Konfigurationspaket zum Konfigurieren von VDI-Geräten verwenden.