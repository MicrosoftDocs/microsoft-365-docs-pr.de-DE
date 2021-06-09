---
title: Optimieren der Bereitstellung und Erkennung von ASR-Regeln
description: Optimieren Sie Ihre Regeln zur Verringerung der Angriffsfläche (Attack Surface Reduction, ASR), um typische Schadsoftware-Exploits zu identifizieren und zu verhindern.
keywords: Onboarding, Intune-Verwaltung, Microsoft Defender für Endpunkt, Microsoft Defender, Windows Defender, Verringerung der Angriffsfläche, ASR, Sicherheitsgrundwerte
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
ms.openlocfilehash: a5590e62e7838bb9f611320b6d0e5c573b2be084
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841558"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>Optimieren der Bereitstellung und Erkennung von ASR-Regeln

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

[Regeln zur Verringerung der Angriffsfläche (Attack Surface Reduction, ASR)](./attack-surface-reduction.md) identifizieren und verhindern typische Schadsoftware-Exploits. Sie steuern, wann und wie potenziell schädlicher Code ausgeführt werden kann. Sie können beispielsweise verhindern, dass JavaScript oder VBScript eine heruntergeladene ausführbare Datei startet, Win32-API-Aufrufe von Office Makros blockiert und Prozesse blockiert, die von USB-Laufwerken ausgeführt werden.

![Karte für die Angriffsflächenverwaltung](images/secconmgmt_asr_card.png)<br>
*Karte für die Angriffsflächenverwaltung*

Die *Attack Surface Management-Karte* ist ein Einstiegspunkt für Tools in Microsoft 365 Security Center, die Sie für Folgendes verwenden können:

* Erfahren Sie, wie ASR-Regeln derzeit in Ihrer Organisation bereitgestellt werden.
* Überprüfen Sie ASR-Erkennungen, und identifizieren Sie mögliche falsche Erkennungen.
* Analysieren Sie die Auswirkungen von Ausschlüssen, und generieren Sie die Liste der auszuschließenden Dateipfade.

Wählen Sie **"Zu Angriffsflächenverwaltungsüberwachung**  >  **wechseln& Berichte > Attack Surface Reduction-Regeln > Ausschlüsse hinzufügen.** Von dort aus können Sie zu anderen Abschnitten des Microsoft 365 Security Centers navigieren.

![Hinzufügen der Registerkarte "Ausschlüsse" auf der Seite "Attack Surface Reduction Rules" im Microsoft 365 Security Center](images/secconmgmt_asr_m365exlusions.png)<br>
Die Registerkarte ***"Ausschlüsse hinzufügen"** auf der Seite "Attack Surface Reduction Rules" im Microsoft 365 Security Center*

> [!NOTE]
> Für den Zugriff auf Microsoft 365 Security Center benötigen Sie eine Microsoft 365 E3- oder E5-Lizenz und ein Konto mit bestimmten Rollen für Azure Active Directory. [Lesen Sie mehr über erforderliche Lizenzen und Berechtigungen.](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)

Weitere Informationen zur Bereitstellung von ASR-Regel in Microsoft 365 Security Center finden Sie unter Überwachen und Verwalten der Bereitstellung und Erkennung von [ASR-Regeln.](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)

**Verwandte Themen**

* [Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind](configure-machines.md)
* [Geräte in Microsoft Defender für Endpunkt integrieren](configure-machines-onboarding.md)
* [Überwachen der Einhaltung der Sicherheitsgrundwerte von Microsoft Defender für Endpunkt](configure-machines-security-baseline.md)
