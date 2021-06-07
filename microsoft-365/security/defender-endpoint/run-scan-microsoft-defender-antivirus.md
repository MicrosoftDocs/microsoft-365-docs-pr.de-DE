---
title: Ausführen und Anpassen von Scans bei Bedarf in Microsoft Defender Antivirus
description: Ausführen und Konfigurieren von Scans auf Anforderung mithilfe von PowerShell, Windows Verwaltungsinstrumentation oder einzeln auf Endpunkten mit der Windows-Sicherheit-App
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
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: fdca059633ab0993e07b5b1be0c6f33cfe327fcf
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789171"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Konfigurieren und Ausführen von bedarfsgesteuerten Scans durch Microsoft Defender Antivirus

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können einen On-Demand-Scan auf einzelnen Endpunkten ausführen. Diese Scans werden sofort gestartet, und Sie können Parameter für die Überprüfung definieren, z. B. den Standort oder Typ.

## <a name="quick-scan-versus-full-scan"></a>Schnellscan im Vergleich zum vollständigen Scan

Der Schnellscan überprüft alle Speicherorte, an denen Schadsoftware registriert werden könnte, um mit dem System zu beginnen, z. B. Registrierungsschlüssel und bekannte Windows Startordner.

> [!IMPORTANT]
> Microsoft Defender Antivirus wird im Kontext des [LocalSystem-Kontos](/windows/win32/services/localsystem-account) ausgeführt, wenn eine lokale Überprüfung ausgeführt wird. Für Netzwerkscans wird der Kontext des Gerätekontos verwendet. Wenn das Domänengerätekonto nicht über die entsprechenden Berechtigungen für den Zugriff auf die Freigabe verfügt, funktioniert die Überprüfung nicht. Stellen Sie sicher, dass das Gerät über Berechtigungen für die Zugriffsnetzwerkfreigabe verfügt.

In Kombination mit [der Immer-On-Echtzeitschutzfunktion](configure-real-time-protection-microsoft-defender-antivirus.md)bietet ein Schnellscan eine starke Abdeckung sowohl für Schadsoftware, die mit Schadsoftware auf System- als auch Kernelebene beginnt. Immer aktivierter Echtzeitschutz überprüft Dateien, wenn sie geöffnet und geschlossen werden und wenn ein Benutzer zu einem Ordner navigiert. Standardmäßig werden Schnellscans auf bereitgestellten Wechselmedien wie USB-Laufwerken ausgeführt. In den meisten Fällen ist ein Schnellscan ausreichend, um Schadsoftware zu finden, die nicht vom Echtzeitschutz erfasst wurde.

Eine vollständige Überprüfung kann nützlich sein, wenn eine Schadsoftware-Bedrohung auf einem Endpunkt gemeldet wird. Die Überprüfung kann ermitteln, ob es inaktive Komponenten gibt, die eine gründlicheere Bereinigung erfordern. Microsoft empfiehlt jedoch in der Regel die Verwendung von Schnellscans anstelle von vollständigen Scans. Ein vollständiger Scan kann einige Stunden oder Tage dauern, abhängig von der Menge und dem Typ der Daten, die gescannt werden müssen. 

> [!TIP]
> Weitere Informationen zu den Unterschieden zwischen schnellen und vollständigen Scans finden Sie unter ["Schnellscan" im Vergleich zum vollständigen Scan und benutzerdefiniertem Scan.](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan)

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Verwenden von Microsoft Endpoint Manager zum Ausführen einer Überprüfung

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.
2. Wählen Sie **Endpunktsicherheits-Antivirus**  >  aus.
3. Wählen Sie in der Liste der Registerkarten **Windows 10 fehlerhafte Endpunkte aus.**
4. Wählen Sie in der Liste der bereitgestellten Aktionen **"Schnellscan"** oder **"Vollständiger Scan"** aus.

[![BILD ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Weitere Informationen zur Verwendung von Microsoft Endpoint Manager zum Ausführen einer Überprüfung finden Sie unter [Antischadsoftware- und Firewallaufgaben: So führen](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)Sie eine Überprüfung nach Bedarf durch.

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>Verwenden sie das Befehlszeilenprogramm mpcmdrun.exe, um eine Überprüfung auszuführen.

Verwenden Sie den folgenden `-scan` Parameter:

```console
mpcmdrun.exe -scan -scantype 1
```

Weitere Informationen zur Verwendung des Tools und zu zusätzlichen Parametern, z. B. starten einer vollständigen Überprüfung oder Definieren von Pfaden, finden Sie unter [Verwenden des mpcmdrun.exe Befehlszeilentools zum Konfigurieren und Verwalten Microsoft Defender Antivirus.](command-line-arguments-microsoft-defender-antivirus.md)

## <a name="use-microsoft-intune-to-run-a-scan"></a>Verwenden von Microsoft Intune zum Ausführen einer Überprüfung

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.
2. Wählen Sie in der Seitenleiste **"Geräte > Alle Geräte"** aus, und wählen Sie das Gerät aus, das Sie scannen möchten.
3. Wählen Sie **... Weitere**. Wählen Sie in den Optionen **"Schnellscan"** oder **"Vollständiger Scan"** aus.

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Verwenden der Windows-Sicherheit-App zum Ausführen einer Überprüfung

Anweisungen zum Ausführen einer Überprüfung auf einzelnen Endpunkten finden Sie [unter Ausführen eines Scans in der Windows-Sicherheit-App.](microsoft-defender-security-center-antivirus.md)

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>Verwenden von PowerShell-Cmdlets zum Ausführen einer Überprüfung

Verwenden Sie das folgende Cmdlet:

```PowerShell
Start-MpScan
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Verwenden Windows Management Instruction (WMI) zum Ausführen einer Überprüfung

Verwenden Sie die [ **Start-Methode**](/previous-versions/windows/desktop/defender/start-msft-mpscan) der **MSFT_MpScan-Klasse.**

Weitere Informationen dazu, welche Parameter zulässig sind, finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>Verwandte Artikel

- [Konfigurieren der Scanoptionen von Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Konfigurieren von geplanten Microsoft Defender Antivirus Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)