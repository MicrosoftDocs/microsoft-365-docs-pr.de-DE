---
title: Behandeln fehlender Ereignisse oder Warnungen für Microsoft Defender for Endpoint unter Linux
description: Behandeln fehlender Ereignisse oder Warnungen in Microsoft Defender for Endpoint unter Linux.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, events
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
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7de216c1397a7cc4806af8221257eeedd2290830
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933313"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Behandeln fehlender Ereignisse oder Warnungen für Microsoft Defender for Endpoint unter Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt unter Linux](microsoft-defender-endpoint-linux.md)

Dieser Artikel enthält einige allgemeine Schritte zum Verringern fehlender Ereignisse oder Warnungen im [Security Center-Portal.](https://securitycenter.windows.com/)

Sobald **Microsoft Defender for Endpoint** ordnungsgemäß auf  einem Gerät installiert wurde, wird im Portal eine Geräteseite generiert. Sie können alle aufgezeichneten Ereignisse auf der Registerkarte Zeitachse auf der Geräteseite oder auf der Erweiterten Suche überprüfen. In diesem Abschnitt wird der Fall behoben, dass einige oder alle erwarteten Ereignisse fehlen.
Wenn beispielsweise alle _CreatedFile-Ereignisse_ fehlen.

## <a name="missing-network-and-login-events"></a>Fehlende Netzwerk- und Anmeldeereignisse

Microsoft Defender for Endpoint nutzte `audit` framework from linux, um Netzwerk- und Anmeldeaktivitäten nachverfolgt zu werden.

1. Stellen Sie sicher, dass das Überwachungsframework funktioniert.

    ```bash
    service auditd status
    ```

    Erwartete Ausgabe:

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. Wenn `auditd` als beendet markiert ist, starten Sie es.

    ```bash
    service auditd start
    ```

**Auf SLES-Systemen** ist die SYSCALL-Überwachung in möglicherweise standardmäßig deaktiviert und kann für `auditd` fehlende Ereignisse berücksichtigt werden.

1. Um zu überprüfen, ob die SYSCALL-Überwachung nicht deaktiviert ist, listen Sie die aktuellen Überwachungsregeln auf:

    ```bash
    sudo auditctl -l
    ```

    Wenn die folgende Zeile vorhanden ist, entfernen Oder bearbeiten Sie sie, damit Microsoft Defender for Endpoint bestimmte SYSCALLs nachverfolgen kann.

    ```output
    -a task, never
    ```

    Überwachungsregeln befinden sich unter `/etc/audit/rules.d/audit.rules` .

## <a name="missing-file-events"></a>Fehlende Dateiereignisse

Dateiereignisse werden mit framework `fanotify` erfasst. Falls einige oder alle Dateiereignisse fehlen, stellen Sie sicher, dass auf dem Gerät aktiviert ist und das `fanotify` Dateisystem [unterstützt wird.](microsoft-defender-endpoint-linux.md#system-requirements)

Listet die Dateisysteme auf dem Computer auf mit:

```bash
df -Th
```
