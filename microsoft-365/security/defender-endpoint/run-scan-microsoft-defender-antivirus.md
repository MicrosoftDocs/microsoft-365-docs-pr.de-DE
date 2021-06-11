---
title: Ausführen und Anpassen von Scans bei Bedarf in Microsoft Defender Antivirus
description: Ausführen und Konfigurieren von Scans bei Bedarf mithilfe von PowerShell, Windows Verwaltungsinstrumentation oder einzeln auf Endpunkten mit der Windows-Sicherheit-App
keywords: scan, on-demand, dos, intune, instant scan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 3ee37d7220527c9032b630e02258c684b6c860b3
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878808"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Konfigurieren und Ausführen von bedarfsgesteuerten Scans durch Microsoft Defender Antivirus

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können einen On-Demand-Scan auf einzelnen Endpunkten ausführen. Diese Scans werden sofort gestartet, und Sie können Parameter für die Überprüfung definieren, z. B. den Standort oder Typ. Wenn Sie einen Scan ausführen, können Sie zwischen drei Typen auswählen: Schnellscan, vollständiger Scan und benutzerdefinierter Scan. Verwenden Sie in den meisten Fällen einen Schnellscan. Ein Schnellscan überprüft alle Speicherorte, an denen Schadsoftware registriert werden könnte, um mit dem System zu beginnen, z. B. Registrierungsschlüssel und bekannte Windows Startordner. 

In Kombination mit always-on-Echtzeitschutz, der Dateien überprüft, wenn sie geöffnet und geschlossen werden, und wenn ein Benutzer zu einem Ordner navigiert, bietet ein Schnellscan starken Schutz vor Schadsoftware, die mit dem System und Schadsoftware auf Kernelebene beginnt. In den meisten Fällen ist ein Schnellscan ausreichend und die empfohlene Option für geplante oder bedarfsgesteuerte Scans.  [Weitere Informationen zu Scantypen.](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)

> [!IMPORTANT]
> Microsoft Defender Antivirus wird im Kontext des [LocalSystem-Kontos](/windows/win32/services/localsystem-account) ausgeführt, wenn eine lokale Überprüfung ausgeführt wird. Für Netzwerkscans wird der Kontext des Gerätekontos verwendet. Wenn das Domänengerätekonto nicht über die entsprechenden Berechtigungen für den Zugriff auf die Freigabe verfügt, funktioniert die Überprüfung nicht. Stellen Sie sicher, dass das Gerät über Berechtigungen für die Zugriffsnetzwerkfreigabe verfügt.

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Verwenden Microsoft Endpoint Manager zum Ausführen einer Überprüfung

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie **Endpunktsicherheits-Antivirus**  >  aus.

3. Wählen Sie in der Liste der Registerkarten **Windows 10 fehlerhafte Endpunkte aus.**

4. Wählen Sie in der Liste der bereitgestellten Aktionen **den Schnellscan** (empfohlen) oder **den vollständigen Scan** aus.

[![BILD ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Weitere Informationen zur Verwendung von Microsoft Endpoint Manager zum Ausführen einer Überprüfung finden Sie unter [Antischadsoftware- und Firewallaufgaben: So führen](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)Sie eine Überprüfung nach Bedarf durch.

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>Verwenden sie das Befehlszeilenprogramm mpcmdrun.exe, um eine Überprüfung auszuführen.

Verwenden Sie den folgenden `-scan` Parameter:

```console
mpcmdrun.exe -scan -scantype 1
```

Weitere Informationen zur Verwendung des Tools und zu zusätzlichen Parametern, z. B. zum Starten einer vollständigen Überprüfung oder zum Definieren von Pfaden, finden Sie unter [Verwenden des mpcmdrun.exe-Befehlszeilentools zum Konfigurieren und Verwalten Microsoft Defender Antivirus.](command-line-arguments-microsoft-defender-antivirus.md)

## <a name="use-microsoft-intune-to-run-a-scan"></a>Verwenden von Microsoft Intune zum Ausführen einer Überprüfung

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie in der Randleiste **"Geräte**  >  **alle Geräte"** aus, und wählen Sie das Gerät aus, das Sie scannen möchten.

3. Wählen Sie **... Weitere**. Wählen Sie in den Optionen **"Schnellscan** " (empfohlen) oder **"Vollständiger Scan"** aus.

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Verwenden der Windows-Sicherheit-App zum Ausführen einer Überprüfung

Anweisungen zum Ausführen einer Überprüfung auf einzelnen Endpunkten finden Sie [unter Ausführen eines Scans in der Windows-Sicherheit-App.](microsoft-defender-security-center-antivirus.md)

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>Verwenden von PowerShell-Cmdlets zum Ausführen einer Überprüfung

Verwenden Sie das folgende Cmdlet:

```PowerShell
Start-MpScan
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Verwenden Windows Management Instruction (WMI) zum Ausführen einer Überprüfung

Verwenden Sie die [ **Start-Methode**](/previous-versions/windows/desktop/defender/start-msft-mpscan) der **MSFT_MpScan** Klasse.

Weitere Informationen dazu, welche Parameter zulässig sind, finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

