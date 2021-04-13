---
title: Konfigurieren von Microsoft Defender Antivirus mit WMI
description: Erfahren Sie, wie Sie Microsoft Defender Antivirus mithilfe von WMI-Skripts konfigurieren und verwalten, um Einstellungen in Microsoft Defender for Endpoint abzurufen, zu ändern und zu aktualisieren.
keywords: wmi, scripts, windows management instrumentation, configuration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8d24a08ae3b8db710ca1727821690e5c87f056c3
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690532"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>Konfigurieren und Verwalten von Microsoft Defender Antivirus mithilfe von Windows Management Instrumentation (WMI)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Windows Management Instrumentation (WMI) ist eine Skriptschnittstelle, mit der Sie Einstellungen abrufen, ändern und aktualisieren können.

Weitere Informationen zu WMI finden Sie in der [Microsoft Developer Network System Administration Library](/windows/win32/wmisdk/wmi-start-page).

Microsoft Defender Antivirus verfügt über eine Reihe spezifischer WMI-Klassen, die zum Ausführen der meisten der gleichen Funktionen wie Gruppenrichtlinien und andere Verwaltungstools verwendet werden können. Viele der Klassen sind mit [Defender PowerShell-Cmdlets vergleichbar.](use-powershell-cmdlets-microsoft-defender-antivirus.md)

Die [MSDN Windows Defender WMIv2-Anbieterreferenzbibliothek](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) listet die verfügbaren WMI-Klassen für Microsoft Defender Antivirus auf und enthält Beispielskripts.

Mit WMI vorgenommene Änderungen wirken sich auf lokale Einstellungen auf dem Endpunkt aus, an dem die Änderungen bereitgestellt oder vorgenommen werden. Dies bedeutet, dass Bereitstellungen von Richtlinien mit Gruppenrichtlinien, Microsoft Endpoint Configuration Manager oder Microsoft Intune mit WMI vorgenommene Änderungen überschreiben können. 

Sie können [konfigurieren, welche Einstellungen lokal mit](configure-local-policy-overrides-microsoft-defender-antivirus.md)lokalen Richtlinienüberschreibungen überschrieben werden können.

## <a name="related-topics"></a>Verwandte Themen

- [Referenzthemen für Verwaltungs- und Konfigurationstools](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)