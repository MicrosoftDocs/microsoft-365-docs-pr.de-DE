---
title: Kompatibilität von Antivirenlösungen mit Defender für Endpunkt
description: Erfahren Sie, wie Windows Defender mit Microsoft Defender für Endpunkt funktioniert und wie es funktioniert, wenn ein Antischadsoftwareclient eines Drittanbieters verwendet wird.
keywords: Windows Defender-Kompatibilität, Defender, Microsoft Defender für Endpunkt, Defender für Endpunkt, Antivirus, MDE
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
ms.openlocfilehash: f5a0db755f919cb47c4cd284857ddf4e27d16996
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782885"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Kompatibilität von Antivirenlösungen mit Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

Der Microsoft Defender für Endpunkt-Agent hängt von Microsoft Defender Antivirus für einige Funktionen wie die Dateiüberprüfung ab.

>[!IMPORTANT]
>Defender für Endpunkt hält sich nicht an die Einstellungen für Microsoft Defender Antivirus Ausschlüsse. 

Sie müssen Security Intelligence-Updates auf den Defender für Endpunkt-Geräten unabhängig davon konfigurieren, ob Microsoft Defender Antivirus die aktive Antischadsoftware ist oder nicht. Weitere Informationen finden Sie unter [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen.](manage-updates-baselines-microsoft-defender-antivirus.md)

Wenn ein integriertes Gerät durch einen Antischadsoftwareclient eines Drittanbieters geschützt ist, wechselt Microsoft Defender Antivirus auf diesem Endpunkt in den passiven Modus.

Microsoft Defender Antivirus erhalten weiterhin Updates, und der *mspeng.exe* Prozess wird als ausgeführter Dienst aufgeführt, führt jedoch keine Überprüfungen durch und ersetzt nicht den ausgeführten Antischadsoftwareclient eines Drittanbieters.

Die Microsoft Defender Antivirus Schnittstelle wird deaktiviert, und Benutzer auf dem Gerät können Microsoft Defender Antivirus nicht verwenden, um Scans bei Bedarf durchzuführen oder die meisten Optionen zu konfigurieren.

Weitere Informationen finden Sie im [Thema Microsoft Defender Antivirus und Defender für Endpunkt-Kompatibilität.](microsoft-defender-antivirus-compatibility.md)
