---
title: Optimieren der Bereitstellung und Erkennung von ASR-Regeln
description: Optimieren Sie Ihre Regeln zur Reduzierung der Angriffsfläche (Attack Surface Reduction, ASR), um typische Schadsoftware-Exploits zu identifizieren und zu verhindern.
keywords: Onboard, Intune-Verwaltung, Microsoft Defender for Endpoint, Microsoft Defender, Windows Defender, Attack Surface Reduction, ASR, Security Baseline
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
ms.openlocfilehash: 91295135c833c6b403078bdfd517c7b84ec7d630
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932847"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>Optimieren der Bereitstellung und Erkennung von ASR-Regeln

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).

[Regeln zur Reduzierung der Angriffsfläche (Attack Surface Reduction, ASR)](./attack-surface-reduction.md) identifizieren und verhindern typische Schadsoftware-Exploits. Sie steuern, wann und wie potenziell schädlicher Code ausgeführt werden kann. Beispielsweise können sie verhindern, dass JavaScript oder VBScript eine heruntergeladene ausführbare Datei startet, Win32-API-Aufrufe von Office-Makros blockieren und Prozesse blockieren, die von USB-Laufwerken ausgeführt werden.

![Angriffsoberflächenverwaltungskarte](images/secconmgmt_asr_card.png)<br>
*Angriffsoberflächenverwaltungskarte*

Die *Angriffsoberflächenverwaltungskarte* ist ein Einstiegspunkt für Tools in Microsoft 365 Security Center, die Sie verwenden können, um:

* Erfahren Sie, wie ASR-Regeln derzeit in Ihrer Organisation bereitgestellt werden.
* Überprüfen Sie ASR-Erkennungen, und identifizieren Sie mögliche falsche Erkennungen.
* Analysieren Sie die Auswirkungen von Ausschlüssen, und generieren Sie die Liste der auszuschließenden Dateipfade.

Wählen **Sie Go to attack surface management** Monitoring & reports > Attack surface reduction rules > Add  >  **exclusions** aus. Von dort aus können Sie zu anderen Abschnitten des Microsoft 365 navigieren.

![Hinzufügen der Registerkarte Ausschlüsse auf der Seite Attack surface reduction rules in Microsoft 365 Security Center](images/secconmgmt_asr_m365exlusions.png)<br>
Die ***Registerkarte Ausschlüsse hinzufügen** auf der Seite Attack surface reduction rules in Microsoft 365 Security Center*

> [!NOTE]
> Um auf Microsoft 365 Security Center zu zugreifen, benötigen Sie eine Microsoft 365 E3- oder E5-Lizenz und ein Konto mit bestimmten Rollen Azure Active Directory. [Lesen Sie mehr über erforderliche Lizenzen und Berechtigungen](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).

Weitere Informationen zur Bereitstellung von ASR-Regeln in Microsoft 365 Security Center finden Sie unter [Monitor and manage ASR rule deployment and detections](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).

**Verwandte Themen**

* [Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind](configure-machines.md)
* [Get devices onboarded to Microsoft Defender for Endpoint](configure-machines-onboarding.md)
* [Überwachen der Einhaltung der Microsoft Defender for Endpoint-Sicherheitsgrundlinie](configure-machines-security-baseline.md)
