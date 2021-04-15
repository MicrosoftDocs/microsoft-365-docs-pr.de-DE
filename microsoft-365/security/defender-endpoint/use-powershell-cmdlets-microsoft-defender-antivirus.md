---
title: Konfigurieren und Ausführen von Microsoft Defender AV mithilfe von PowerShell-Cmdlets
description: In Windows 10 können Sie PowerShell-Cmdlets zum Ausführen von Scans, Aktualisieren der Sicherheitsintelligenz und Ändern von Einstellungen in Microsoft Defender Antivirus verwenden.
keywords: Scan, Befehlszeile, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d6fb8dc510e004fa88bf99583cc2cc33ae8c63bb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765299"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>Verwenden von PowerShell-Cmdlets zum Konfigurieren und Verwalten von Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können PowerShell verwenden, um verschiedene Funktionen in Windows Defender. Ähnlich wie die Eingabeaufforderung oder Befehlszeile ist PowerShell eine aufgabenbasierte Befehlszeilenshell und Skriptsprache, die speziell für die Systemverwaltung entwickelt wurde. Weitere Informationen dazu finden Sie im [PowerShell-Hub auf MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).

Eine Liste der Cmdlets mit ihren Funktionen und verfügbaren Parametern finden Sie im [Thema Defender-Cmdlets.](/powershell/module/defender)

PowerShell-Cmdlets sind am nützlichsten in Windows Server-Umgebungen, die nicht auf einer grafischen Benutzeroberfläche (GUI) zum Konfigurieren von Software angewiesen sind.

> [!NOTE]
> PowerShell-Cmdlets sollten nicht als Ersatz für eine vollständige Netzwerkrichtlinienverwaltungsinfrastruktur verwendet werden, z. B. [Microsoft Endpoint Configuration Manager,](/configmgr) [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))oder Microsoft Defender Antivirus Group [Policy ADMX-Vorlagen.](https://www.microsoft.com/download/101445)

Mit PowerShell vorgenommene Änderungen wirken sich auf lokale Einstellungen auf dem Endpunkt aus, an dem die Änderungen bereitgestellt oder vorgenommen werden. Dies bedeutet, dass Bereitstellungen von Richtlinien mit Gruppenrichtlinien, Microsoft Endpoint Configuration Manager oder Microsoft Intune änderungen überschreiben können, die mit PowerShell vorgenommen wurden.

Sie können [konfigurieren, welche Einstellungen lokal mit](configure-local-policy-overrides-microsoft-defender-antivirus.md)lokalen Richtlinienüberschreibungen überschrieben werden können.

PowerShell wird in der Regel unter dem Ordner `%SystemRoot%\system32\WindowsPowerShell` installiert.

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>Verwenden von Microsoft Defender Antivirus PowerShell-Cmdlets

1. Geben Sie in der Windows-Suchleiste **powershell ein.**
2. Wählen **Windows PowerShell** aus den Ergebnissen aus, um die Schnittstelle zu öffnen.
3. Geben Sie den Befehl PowerShell und alle Parameter ein.

> [!NOTE]
> Möglicherweise müssen Sie PowerShell im Administratormodus öffnen. Klicken Sie im Menü Start mit der rechten Maustaste auf das Element, klicken Sie auf Als Administrator **ausführen,** und klicken Sie an der Berechtigungsaufforderung **auf** Ja.

Geben Sie folgendes ein, um die Onlinehilfe für eines der Cmdlets zu öffnen:

```PowerShell
Get-Help <cmdlet> -Online
```

Lassen Sie den `-online` Parameter weg, um lokal zwischengespeicherte Hilfe zu erhalten.

## <a name="related-topics"></a>Verwandte Themen

- [Referenzthemen für Verwaltungs- und Konfigurationstools](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus-Cmdlets](/powershell/module/defender)