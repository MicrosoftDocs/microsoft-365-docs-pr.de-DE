---
title: Kompatibilität der Antivirenlösung mit Defender for Endpoint
description: Erfahren Sie, wie Windows Defender Microsoft Defender for Endpoint funktioniert und wie es funktioniert, wenn ein Antischalwareclient eines Drittanbieters verwendet wird.
keywords: Windows Defender-Kompatibilität, Defender, Microsoft Defender für Endpoint, Defender für Endpunkt, Antivirus, mde
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
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: 84c523b721596d9c467f01cf6b8a0685b2091669
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274880"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Kompatibilität der Antivirenlösung mit Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

Der Microsoft Defender for Endpoint-Agent hängt von Microsoft Defender Antivirus für einige Funktionen wie dateiscannen ab.

>[!IMPORTANT]
>Defender for Endpoint hält sich nicht an die Microsoft Defender Antivirus Ausschlusseinstellungen. 

Sie müssen Sicherheitsintelligenzupdates auf den Defender for Endpoint-Geräten konfigurieren, Microsoft Defender Antivirus die aktive Antischalware ist oder nicht. Weitere Informationen finden Sie unter [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).

Wenn ein integriertes Gerät durch einen Antischalwareclient eines Drittanbieters geschützt ist, wird Microsoft Defender Antivirus diesem Endpunkt in den passiven Modus versetzt.

Microsoft Defender Antivirus erhalten weiterhin Updates, und der *mspeng.exe-Prozess* wird als ausgeführter Dienst aufgeführt, führt jedoch keine Überprüfungen durch und ersetzt nicht den ausgeführten Antischalwareclient eines Drittanbieters.

Die Microsoft Defender Antivirus-Schnittstelle wird deaktiviert, und Benutzer auf dem Gerät können Microsoft Defender Antivirus nicht verwenden, um Bedarfsscans durchzuführen oder die meisten Optionen zu konfigurieren.

Weitere Informationen finden Sie im [Thema Microsoft Defender Antivirus und Defender for Endpoint-Kompatibilität.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
