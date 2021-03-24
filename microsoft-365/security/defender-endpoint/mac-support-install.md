---
title: Beheben von Installationsproblemen für Microsoft Defender ATP für Mac
description: Beheben von Installationsproblemen in Microsoft Defender ATP für Mac.
keywords: microsoft, defender, atp, mac, install
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
ms.openlocfilehash: 60b50f3944a2cdd995b4877e22123018267ff044
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062239"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Beheben von Installationsproblemen für Microsoft Defender for Endpoint für Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpoint für Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a>Installation fehlgeschlagen

Für die manuelle Installation heißt es auf der Seite Zusammenfassung des Installations-Assistenten: "Bei der Installation ist ein Fehler aufgetreten. Beim Installer ist ein Fehler aufgetreten, der zu einem Fehler bei der Installation führte. Wenden Sie sich an den Softwarehersteller, um Unterstützung zu erhalten." Bei MDM-Bereitstellungen wird auch ein allgemeiner Installationsfehler angezeigt.

Wir zeigen dem Endbenutzer zwar keinen genauen Fehler an, aber wir behalten eine Protokolldatei mit dem Installationsfortschritt in `/Library/Logs/Microsoft/mdatp/install.log` bei. Jede Installationssitzung wird an diese Protokolldatei angefügt. Sie können die `sed` letzte Installationssitzung nur verwenden:

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

In diesem Beispiel wird dem tatsächlichen Grund das Präfix `[ERROR]` vorangestellt.
Die Installation ist fehlgeschlagen, da ein Downgrade zwischen diesen Versionen nicht unterstützt wird.

## <a name="mdatp-install-log-missing-or-not-updated"></a>MDATP-Installationsprotokoll fehlt oder wird nicht aktualisiert

In seltenen Fällen hinterlässt die Installation keine Ablaufverfolgung in der Datei /Library/Logs/Microsoft/mdatp/install.log von MDATP.
Sie können überprüfen, ob eine Installation ausgeführt wurde, und mögliche Fehler analysieren, indem Sie macOS-Protokolle abfragen (dies ist bei der MDM-Bereitstellung hilfreich, wenn keine Clientbenutzeroberfläche verfügbar ist). Es wird empfohlen, ein schmales Zeitfenster zum Ausführen einer Abfrage zu verwenden und nach dem Namen des Protokollierungsprozesses zu filtern, da eine große Menge an Informationen zur Verfügung steht.

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
