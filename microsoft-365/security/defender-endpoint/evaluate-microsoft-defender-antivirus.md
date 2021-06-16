---
title: Microsoft Defender Antivirus beurteilen
description: Unternehmen aller Größen können diesen Leitfaden verwenden, um den von Microsoft Defender Antivirus in Windows 10 gebotenen Schutz zu bewerten und zu testen.
keywords: Microsoft Defender Antivirus, Cloudschutz, Cloud, Antischadsoftware, Sicherheit, Defender, auswerten, testen, Schützen, vergleichen, Echtzeitschutz
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5c558a7799bff61a0ee80db31ee476ad611053c0
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926619"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Microsoft Defender Antivirus beurteilen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Verwenden Sie dieses Handbuch, um zu bestimmen, wie gut Microsoft Defender Antivirus Sie vor Viren, Schadsoftware und potenziell unerwünschten Anwendungen schützt.

>[!TIP]
>Sie können auch die Demowebsite von Microsoft Defender für Endpunkt unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass die folgenden Features funktionieren und wie sie funktionieren:
>- Aus der Cloud gelieferter Schutz
>- Schnelles Lernen (einschließlich "Bei erster Anzeige blockieren")
>- Blockieren potenziell unerwünschter Anwendungen

Es werden die wichtigen Schutzfeatures der nächsten Generation von Microsoft Defender Antivirus erläutert, die für kleine und große Unternehmen verfügbar sind, und wie sie die Erkennung und den Schutz von Schadsoftware in Ihrem Netzwerk erhöhen.

Sie können jede Einstellung unabhängig oder alle gleichzeitig konfigurieren und auswerten. Wir haben ähnliche Einstellungen basierend auf typischen Evaluierungsszenarien gruppiert und Anweisungen für die Verwendung von PowerShell zum Aktivieren der Einstellungen eingeschlossen.

Die Anleitung ist im PDF-Format für die Offlineanzeige verfügbar:

- [Herunterladen des Leitfadens im PDF-Format](https://www.microsoft.com/download/details.aspx?id=54795)

Sie können auch eine PowerShell herunterladen, die alle im Handbuch beschriebenen Einstellungen automatisch aktiviert. Sie können das Skript zusammen mit dem obigen PDF-Download oder einzeln über den PowerShell-Katalog abrufen:

- [Laden Sie das PowerShell-Skript herunter, um die Einstellungen automatisch zu konfigurieren](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> Die Anleitung ist derzeit für die Einzelcomputerbewertung von Microsoft Defender Antivirus vorgesehen. Das Aktivieren aller Einstellungen in diesem Handbuch ist möglicherweise nicht für die bereitstellung in der Praxis geeignet.
>
> Die neuesten Empfehlungen für die reale Bereitstellung und Überwachung von Microsoft Defender Antivirus über ein Netzwerk hinweg finden Sie unter [Bereitstellen Microsoft Defender Antivirus.](deploy-manage-report-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Bereitstellen von Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)