---
title: Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunkt-Gerät
description: Führen Sie das Erkennungsskript auf einem neu integrierten Gerät aus, um zu überprüfen, ob es ordnungsgemäß in den Microsoft Defender für Endpunkt-Dienst integriert ist.
keywords: Erkennungstest, Erkennung, PowerShell, Skript, überprüfen, Onboarding, Microsoft Defender für Endpunkt-Onboarding, Clients, Server, Testen
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 10090fdd1dff6b020d06c82afa8456d7a157ff91
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843306"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunkt-Gerät 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- Unterstützte versionen Windows 10
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server, Version 1803
- Windows Server, 2019
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Führen Sie das folgende PowerShell-Skript auf einem neu integrierten Gerät aus, um sicherzustellen, dass es ordnungsgemäß an den Defender für Endpunkt-Dienst meldet.

1. Erstellen Sie einen Ordner: "C:\test-MDATP-test".
2. Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:

   1. Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

   1. Klicken Sie mit der rechten Maustaste auf **"Eingabeaufforderung",** und wählen Sie **"Als Administrator ausführen"** aus.

      ![Startmenü des Fensters, das auf "Als Administrator ausführen" verweist](images/run-as-admin.png)

3. Kopieren Sie an der Eingabeaufforderung den folgenden Befehl, und führen Sie ihn aus:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Das Eingabeaufforderungsfenster wird automatisch geschlossen. Bei erfolgreicher Ausführung wird der Erkennungstest als abgeschlossen gekennzeichnet, und in ca. 10 Minuten wird eine neue Warnung im Portal für das integrierte Gerät angezeigt.

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10-Geräten](configure-endpoints.md)
- [Onboarding von Servern](configure-server-endpoints.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender für Endpunkten](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
