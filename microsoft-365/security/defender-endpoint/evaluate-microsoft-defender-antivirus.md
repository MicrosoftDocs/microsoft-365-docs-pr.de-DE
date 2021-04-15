---
title: Bewerten von Microsoft Defender Antivirus
description: Unternehmen aller Größen können dieses Handbuch verwenden, um den von Microsoft Defender Antivirus in Windows 10 angebotenen Schutz auszuwerten und zu testen.
keywords: Microsoft Defender Antivirus, Cloudschutz, Cloud, Antischalware, Sicherheit, Defender, Evaluieren, Testen, Schutz, Vergleichen, Echtzeitschutz
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7f3fa1ca854a75025f850c85637cd3e08678bdbc
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764831"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Bewerten von Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Verwenden Sie dieses Handbuch, um zu bestimmen, wie gut Microsoft Defender Antivirus Sie vor Viren, Schadsoftware und potenziell unerwünschten Anwendungen schützt.

>[!TIP]
>Sie können auch die Microsoft Defender for Endpoint-Demowebsite unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass die folgenden Features funktionieren und wie sie funktionieren:
>- In der Cloud zugestellter Schutz
>- Schnelles Lernen (einschließlich "Bei erster Sicht blockieren")
>- Potenziell unerwünschte Anwendungsblockierung

Es erläutert die wichtigen Schutzfunktionen der nächsten Generation von Microsoft Defender Antivirus, die sowohl für kleine als auch für große Unternehmen verfügbar sind, und wie sie die Erkennung und den Schutz von Schadsoftware im gesamten Netzwerk erhöhen.

Sie können jede Einstellung unabhängig oder alle gleichzeitig konfigurieren und auswerten. Wir haben ähnliche Einstellungen basierend auf typischen Auswertungsszenarien zusammengefasst und Anweisungen für die Verwendung von PowerShell zum Aktivieren der Einstellungen enthalten.

Das Handbuch ist im PDF-Format für die Offlineanzeige verfügbar:

- [Herunterladen des Handbuchs im PDF-Format](https://www.microsoft.com/download/details.aspx?id=54795)

Sie können auch eine PowerShell herunterladen, die alle in der Anleitung beschriebenen Einstellungen automatisch aktiviert. Sie können das Skript zusammen mit dem obigen PDF-Download oder einzeln im PowerShell Gallery abrufen:

- [Laden Sie das PowerShell-Skript herunter, um die Einstellungen automatisch zu konfigurieren.](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> Das Handbuch ist derzeit für die Auswertung von Microsoft Defender Antivirus auf einem Computer vorgesehen. Das Aktivieren aller Einstellungen in diesem Handbuch ist möglicherweise nicht für die bereitstellung in der realen Welt geeignet.
>
> Die neuesten Empfehlungen für die bereitstellung und Überwachung von Microsoft Defender Antivirus in einem Netzwerk finden Sie unter [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Bereitstellen von Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)