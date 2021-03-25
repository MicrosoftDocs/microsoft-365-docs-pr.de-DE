---
title: Behandeln von Problemen mit der Kernelerweiterung in Microsoft Defender ATP für Mac
description: Behandeln von Problemen mit kernelerweiterungsbezogenen Problemen in Microsoft Defender ATP für Mac.
keywords: microsoft, defender, atp, mac, kernel, extension
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ee6f34a16c4c924bbc73af89029c529dfc766568
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064072"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-for-mac"></a>Behandeln von Problemen mit der Kernelerweiterung in Microsoft Defender for Endpoint für Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpoint für Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Dieser Artikel enthält Informationen zum Behandeln von Problemen mit der Kernelerweiterung, die als Teil von Microsoft Defender for Endpoint für Mac installiert ist.

Ab macOS High Sierra (10.13) muss macOS alle Kernelerweiterungen explizit genehmigt werden, bevor sie auf dem Gerät ausgeführt werden dürfen.

Wenn Sie die Kernelerweiterung während der Bereitstellung/Installation von Microsoft Defender for Endpoint für Mac nicht genehmigt haben, zeigt die Anwendung ein Banner an, in dem Sie aufgefordert werden, sie zu aktivieren:

   ![Deaktivierter Screenshot von RTP](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-32-main-app-fix)

Sie können auch ```mdatp health``` ausführen. Es wird berichtet, ob der Echtzeitschutz aktiviert ist, aber nicht verfügbar ist. Dies bedeutet, dass die Kernelerweiterung nicht für die Ausführung auf Ihrem Gerät genehmigt ist.

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

In den folgenden Abschnitten finden Sie Anleitungen zur Behandlung dieses Problems, abhängig von der Methode, die Sie zum Bereitstellen von Microsoft Defender for Endpoint für Mac verwendet haben.

## <a name="managed-deployment"></a>Verwaltete Bereitstellung

Weitere Informationen finden Sie in den Anweisungen zum Verwaltungstool, das Sie zum Bereitstellen des Produkts verwendet haben:

- [JAMF-basierte Bereitstellung](mac-install-with-jamf.md)
- [Microsoft Intune-basierte Bereitstellung](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a>Manuelle Bereitstellung

Wenn seit der Installation des Produkts weniger als 30 Minuten vergangen sind, navigieren Sie zu **Systemeinstellungen** Sicherheit & Datenschutz , wo Sie Systemsoftware von  >  Entwicklern  "Microsoft Corporation" zulassen müssen.

Wenn diese Aufforderung nicht angezeigt wird, bedeutet dies, dass 30 oder mehr Minuten vergangen sind und die Kernelerweiterung weiterhin nicht genehmigt wurde, um auf Ihrem Gerät ausgeführt zu werden:

![Sicherheits- und Datenschutzfenster nach ablaufend abgelaufener Eingabeaufforderung](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-33-securityprivacysettings-noprompt)

In diesem Fall müssen Sie die folgenden Schritte ausführen, um den Genehmigungsfluss erneut auszulösen.

1. Versuchen Sie im Terminal, den Treiber zu installieren. Beim folgenden Vorgang wird ein Fehler ausgeführt, da die Kernelerweiterung nicht für die Ausführung auf dem Gerät genehmigt wurde. Der Genehmigungsfluss wird jedoch erneut ausgelöst.

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. Öffnen **Sie Systemeinstellungen**  >  **Sicherheit & Datenschutz im** Menü. (Schließen Sie es zuerst, wenn es geöffnet ist.)

3. **Zulassen** von Systemsoftware von Entwicklern "Microsoft Corporation"

4. Installieren Sie im Terminal den Treiber erneut. Dieses Mal wird der Vorgang erfolgreich sein:

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    Das Banner sollte aus der Defender-Anwendung verschwinden und nun melden, dass der Echtzeitschutz aktiviert und ```mdatp health``` verfügbar ist:

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```