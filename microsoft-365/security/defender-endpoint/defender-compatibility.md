---
title: Microsoft Defender Antivirus-Kompatibilität mit Defender for Endpoint
description: Erfahren Sie, wie Windows Defender Microsoft Defender for Endpoint funktioniert und wie es funktioniert, wenn ein Antischalwareclient eines Drittanbieters verwendet wird.
keywords: Windows Defender-Kompatibilität, Defender, Microsoft Defender Atp, Defender für Endpunkt, Antivirus, mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 63dca2694dae5dee924c9a0a02a660003907c42b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165957"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a>Microsoft Defender Antivirus-Kompatibilität mit Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

Der Microsoft Defender for Endpoint-Agent ist für einige Funktionen wie die Dateiprüfung von Microsoft Defender Antivirus abhängig.

>[!IMPORTANT]
>Defender for Endpoint hält sich nicht an die Microsoft Defender Antivirus-Ausschlusseinstellungen. 

Sie müssen Sicherheitsintelligenzupdates auf den Defender for Endpoint-Geräten konfigurieren, unabhängig davon, ob Microsoft Defender Antivirus die aktive Antischalware ist oder nicht. Weitere Informationen finden Sie unter [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).

Wenn ein integriertes Gerät durch einen Antischalwareclient eines Drittanbieters geschützt ist, wechselt Microsoft Defender Antivirus auf diesem Endpunkt in den passiven Modus.

Microsoft Defender Antivirus erhält weiterhin Updates, und der *mspeng.exe-Prozess* wird als ausgeführter Dienst aufgeführt, führt jedoch keine Überprüfungen durch und ersetzt nicht den ausgeführten Antischsoftwareclient eines Drittanbieters.

Die Microsoft Defender Antivirus-Schnittstelle wird deaktiviert, und Benutzer auf dem Gerät können Microsoft Defender Antivirus nicht verwenden, um Bedarfsscans durchzuführen oder die meisten Optionen zu konfigurieren.

Weitere Informationen finden Sie im [Thema zur Kompatibilität von Microsoft Defender Antivirus und Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
