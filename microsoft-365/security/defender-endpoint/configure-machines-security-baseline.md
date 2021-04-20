---
title: Erhöhen der Einhaltung der Microsoft Defender for Endpoint-Sicherheitsgrundlinie
description: Die Microsoft Defender for Endpoint-Sicherheitsgrundlinie legt Sicherheitssteuerelemente fest, um optimalen Schutz zu bieten.
keywords: Intune-Verwaltung, MDATP, WDATP, MDE, Microsoft Defender for Endpoint, erweiterte Bedrohungsschutz-ASR, Sicherheitsgrundlinie
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 19a2276955b253a23ee1552a3f1d4d0345dfe247
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893541"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a>Erhöhen der Einhaltung der Microsoft Defender for Endpoint-Sicherheitsgrundlinie

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Sicherheitsgrundwerte stellen sicher, dass Sicherheitsfeatures gemäß den Anweisungen von Sicherheitsexperten und erfahrenen Windows-Systemadministratoren konfiguriert werden. Bei der Bereitstellung legt die Sicherheitsgrundlinie von Defender for Endpoint die Sicherheitssteuerelemente für Defender for Endpoint so fest, dass ein optimaler Schutz bereitgestellt wird.

Informationen zu Sicherheitsgrundwerten und deren Zugewiesenung in Intune mithilfe von Konfigurationsprofilen finden Sie [in diesen Häufig gestellten Fragen](https://docs.microsoft.com/intune/security-baselines#q--a).

Bevor Sie die Einhaltung von Sicherheitsgrundwerten bereitstellen und nachverfolgen können:
- [Registrieren Ihrer Geräte bei der Intune-Verwaltung](configure-machines.md#enroll-devices-to-intune-management)
- [Sicherstellen, dass Sie über die erforderlichen Berechtigungen verfügen](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a>Vergleichen der Microsoft Defender for Endpoint- und Windows Intune-Sicherheitsgrundwerte
Die Windows Intune-Sicherheitsgrundlinie enthält eine umfassende Reihe empfohlener Einstellungen, die zum sicheren Konfigurieren von Geräten unter Windows erforderlich sind, einschließlich Browsereinstellungen, PowerShell-Einstellungen sowie Einstellungen für einige Sicherheitsfeatures wie Microsoft Defender Antivirus. Im Gegensatz dazu enthält die Defender for Endpoint-Baseline Einstellungen, mit denen alle Sicherheitssteuerelemente im Defender for Endpoint-Stapel optimiert werden, einschließlich Einstellungen für endpunkterkennung und -reaktion (Endpoint Detection and Response, EDR) sowie Einstellungen, die auch in der Windows Intune-Sicherheitsgrundlinie zu finden sind. Weitere Informationen zu den einzelnen Baselines finden Sie unter:

- [Windows-Sicherheitsgrundeinstellungen für Intune](https://docs.microsoft.com/intune/security-baseline-settings-windows)
- [Basiseinstellungen für Microsoft Defender for Endpoint für Intune](https://docs.microsoft.com/intune/security-baseline-settings-defender-atp)

Im Idealfall werden die in Defender for Endpoint integrierten Geräte beide Basiswerte bereitgestellt: die Windows Intune-Sicherheitsgrundlinie zum anfänglichen Sichern von Windows und anschließend die Defender for Endpoint-Sicherheitsgrundlinie, die sich auf einer Schicht befindet, um die Defender for Endpoint-Sicherheitssteuerelemente optimal zu konfigurieren. Um von den neuesten Daten zu Risiken und Bedrohungen zu profitieren und Konflikte bei der Entwicklung der Basiswerte zu minimieren, wenden Sie immer die neuesten Versionen der Basiswerte für alle Produkte an, sobald sie veröffentlicht werden.

>[!NOTE]
>Die Sicherheitsgrundlinie von Defender for Endpoint wurde für physische Geräte optimiert und wird derzeit nicht für die Verwendung auf virtuellen Computern (VMs) oder VDI-Endpunkten empfohlen. Bestimmte Basiseinstellungen können sich auf interaktive Remotesitzungen in virtualisierten Umgebungen auswirken.

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a>Überwachen der Einhaltung der Sicherheitsgrundlinie für Defender for Endpoint

Die **Sicherheitsgrundkarte** für die [Gerätekonfigurationsverwaltung](configure-machines.md) bietet eine Übersicht über die Kompatibilität auf Windows 10-Geräten, denen die Sicherheitsbasislinie Defender for Endpoint zugewiesen wurde.

![Sicherheitsgrundkarte](images/secconmgmt_baseline_card.png)<br>
*Karte, auf der die Einhaltung der Sicherheitsgrundlinie für Defender for Endpoint angezeigt wird*

Jedem Gerät wird einer der folgenden Statustypen gegeben:

- **Entspricht dem Basisplan**– Geräteeinstellungen entsprechen allen Einstellungen in der Basislinie
- **Nicht mit dem Basisplan** übereinstimmen – mindestens eine Geräteeinstellung ist nicht mit der Basislinie übereinstimmend
- **Falsch konfiguriert –** Mindestens eine Basiseinstellung ist auf dem Gerät nicht ordnungsgemäß konfiguriert und befindet sich in einem Konflikt-, Fehler- oder Ausstehendzustand.
- **Nicht zutreffend**– Mindestens eine Basiseinstellung gilt nicht auf dem Gerät

Wählen Sie Zum Überprüfen bestimmter Geräte **die Option Sicherheitsbasisplan auf** der Karte konfigurieren aus. Dies führt Sie zur Intune-Geräteverwaltung. Wählen Sie dort **Gerätestatus** für die Namen und Status der Geräte aus.

>[!NOTE]
>Möglicherweise gibt es Abweichungen in aggregierten Daten, die auf der Seite für die Gerätekonfigurationsverwaltung angezeigt werden, und in den auf Übersichtsbildschirmen in Intune angezeigten Daten.

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a>Überprüfen und Zuweisen der Microsoft Defender for Endpoint-Sicherheitsgrundlinie

Die Gerätekonfigurationsverwaltung überwacht die Grundlegende Kompatibilität nur von Windows 10-Geräten, denen speziell die Microsoft Defender for Endpoint-Sicherheitsbasis zugewiesen wurde. Sie können die Basislinie bequem überprüfen und sie Geräten in der Intune-Geräteverwaltung zuweisen.

1. Wählen **Sie Sicherheitsbasisplan konfigurieren** auf der **Basiskarte Sicherheit** aus, um zu Intune-Geräteverwaltung zu wechseln. Eine ähnliche Übersicht über die Basiskonformität wird angezeigt.

   >[!TIP]
   > Alternativ können Sie im Microsoft Azure-Portal von Allen Diensten > Intune > Gerätesicherheit > Sicherheitsgrundlinien > Microsoft Defender ATP-Basislinie zur Sicherheitsbasislinie von Defender for Endpoint **navigieren.**


2. Erstellen Sie ein neues Profil.

   ![Übersicht über die Sicherheitsgrundlinie von Microsoft Defender for Endpoint in Intune](images/secconmgmt_baseline_intuneprofile1.png)<br>
   *Übersicht über die Sicherheitsgrundlinie von Microsoft Defender for Endpoint in Intune*

3. Während der Profilerstellung können Sie bestimmte Einstellungen für den Basisplan überprüfen und anpassen.

   ![Sicherheitsgrundlinienoptionen während der Profilerstellung in Intune](images/secconmgmt_baseline_intuneprofile2.png)<br>
   *Sicherheitsgrundlinienoptionen während der Profilerstellung in Intune*

4. Weisen Sie das Profil der entsprechenden Gerätegruppe zu.

   ![Sicherheitsgrundlinienprofile in Intune](images/secconmgmt_baseline_intuneprofile3.png)<br>
   *Zuweisen des Sicherheitsgrundlinienprofils in Intune*

5. Erstellen Sie das Profil, um es zu speichern und in der zugewiesenen Gerätegruppe zu bereitstellen.

   ![Zuweisen der Sicherheitsgrundlinie in Intune](images/secconmgmt_baseline_intuneprofile4.png)<br>
   *Erstellen des Sicherheitsgrundprofils in Intune*

>[!TIP]
>Sicherheitsgrundwerte in Intune bieten eine bequeme Möglichkeit, Ihre Geräte umfassend zu sichern und zu schützen. [Erfahren Sie mehr über Sicherheitsgrundwerte in Intune](https://docs.microsoft.com/intune/security-baselines).

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>Verwandte Themen
- [Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind](configure-machines.md)
- [Get devices onboarded to Microsoft Defender for Endpoint](configure-machines-onboarding.md)
- [Optimieren der Bereitstellung und Erkennung von ASR-Regeln](configure-machines-asr.md)
