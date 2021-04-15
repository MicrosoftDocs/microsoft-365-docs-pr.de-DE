---
title: Ausführen und Anpassen von Bedarfsscans in Microsoft Defender AV
description: Ausführen und Konfigurieren von Bedarfsscans mithilfe von PowerShell, Windows Management Instrumentation oder einzeln auf Endpunkten mit der Windows Security App
keywords: scan, on-demand, dos, intune, instant scan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 976531e1b7e1b87c4cd2dd2af66f294f68c5d4f1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764399"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Konfigurieren und Ausführen von Bedarfsscans von Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können eine Bedarfsscan auf einzelnen Endpunkten ausführen. Diese Überprüfungen werden sofort gestartet, und Sie können Parameter für die Überprüfung definieren, z. B. den Speicherort oder Typ.

## <a name="quick-scan-versus-full-scan"></a>Schnellscan im Vergleich zum vollständigen Scan

Die Schnellscans sehen sich alle Speicherorte an, an denen Schadsoftware registriert werden könnte, um mit dem System zu beginnen, z. B. Registrierungsschlüssel und bekannte Windows-Startordner.

> [!IMPORTANT]
> Microsoft Defender Antivirus wird beim Ausführen einer lokalen Überprüfung im Kontext des [LocalSystem-Kontos](/windows/win32/services/localsystem-account) ausgeführt. Für Netzwerkscans verwendet es den Kontext des Gerätekontos. Wenn das Domänengerätekonto nicht über die entsprechenden Berechtigungen für den Zugriff auf die Freigabe verfügt, funktioniert die Überprüfung nicht. Stellen Sie sicher, dass das Gerät über Berechtigungen für die Zugriffsnetzwerkfreigabe verfügt.

In Kombination mit der [Immer-on-Echtzeitschutzfunktion](configure-real-time-protection-microsoft-defender-antivirus.md), die Dateien überprüft, wenn sie geöffnet und geschlossen werden, und wenn ein Benutzer zu einem Ordner navigiert, bietet ein Schnellscan eine starke Abdeckung sowohl für Schadsoftware, die mit dem System beginnt, als auch für Schadsoftware auf Kernelebene.  

In den meisten Fällen ist eine schnelle Überprüfung ausreichend, um Schadsoftware zu finden, die nicht vom Echtzeitschutz aufgegriffen wurde.

Eine vollständige Überprüfung kann für Endpunkte nützlich sein, die eine Schadsoftwarebedrohung gemeldet haben. Bei der Überprüfung kann ermittelt werden, ob inaktive Komponenten enthalten sind, die eine gründlichere Bereinigung erfordern. Dies ist ideal, wenn In-Demand-Scans in Ihrer Organisation ausgeführt werden.

> [!NOTE]
> Standardmäßig werden Schnellscans auf angeschlossenen Wechselmedien ausgeführt, z. B. USB-Laufwerken.

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Ausführen einer Überprüfung mithilfe von Microsoft Endpoint Manager

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.
2. Wählen **Sie Endpoint security**  >  **Antivirus** aus.
3. Wählen Sie in der Liste der Registerkarten die Option **Fehlerhafte Endpunkte für Windows 10 aus.**
4. Wählen Sie in der Liste der bereitgestellten Aktionen **Schnellscan** oder **Vollständige Überprüfung aus.**

[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Weitere Informationen zur Verwendung von Microsoft Endpoint Manager zum Ausführen einer Überprüfung finden Sie unter [Antischalware- und Firewallaufgaben: Ausführen einer Anforderungsscan.](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>Verwenden des mpcmdrun.exe Befehlszeilenprogramms zum Ausführen einer Überprüfung

Verwenden Sie den folgenden `-scan` Parameter:

```console
mpcmdrun.exe -scan -scantype 1
```

Weitere Informationen zur Verwendung des Tools und zu zusätzlichen Parametern, z. B. zum Starten einer vollständigen Überprüfung oder zum Definieren von Pfaden, finden Sie unter Verwenden des Befehlszeilentools mpcmdrun.exe zum Konfigurieren und Verwalten von [Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).

## <a name="use-microsoft-intune-to-run-a-scan"></a>Ausführen einer Überprüfung mithilfe von Microsoft Intune

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.
2. Wählen Sie auf der Seitenleiste **Geräte > Alle Geräte aus,** und wählen Sie das Gerät aus, das Sie überprüfen möchten.
3. Wählen Sie **... aus. Weitere .** Wählen Sie in den Optionen **Schnellscan oder** **Vollständige Überprüfung aus.**

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Ausführen einer Überprüfung mithilfe der Windows Security-App

Anweisungen [zum Ausführen einer Überprüfung auf](microsoft-defender-security-center-antivirus.md) einzelnen Endpunkten finden Sie unter Ausführen einer Überprüfung in der Windows Security-App.

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>Verwenden von PowerShell-Cmdlets zum Ausführen einer Überprüfung

Verwenden Sie das folgende Cmdlet:

```PowerShell
Start-MpScan
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Use PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and run Microsoft Defender Antivirus and Defender [cmdlets](/powershell/module/defender/).

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Ausführen einer Überprüfung mithilfe von Windows Management Instruction (WMI)

Verwenden Sie [ **die Start-Methode**](/previous-versions/windows/desktop/defender/start-msft-mpscan) der **MSFT_MpScan** Klasse.

Weitere Informationen zu den zulässigen Parametern finden Sie [unter Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>Verwandte Artikel

- [Konfigurieren von Microsoft Defender Antivirus-Überprüfungsoptionen](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Konfigurieren geplanter Microsoft Defender Antivirus-Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)