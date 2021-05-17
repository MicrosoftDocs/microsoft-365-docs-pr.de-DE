---
title: Feedback-Loop-Blockierung
description: Das Blockieren von Feedbackschleifen, auch als schneller Schutz bezeichnet, ist Teil der Funktionen zum Blockieren und Eindähen von Verhaltensweisen in Microsoft Defender for Endpoint
keywords: Verhaltensblockierung, schneller Schutz, Feedbackblockierung, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: b1ec879a2f05a0354b1a49cf94fccacb4a382193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068575"
---
# <a name="feedback-loop-blocking"></a>Feedback-Loop-Blockierung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a>Übersicht

Das Blockieren von Feedbackschleifen, auch als schneller Schutz bezeichnet, ist eine Komponente von Funktionen zum Blockieren und Eindähen von Verhaltensweisen [in](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) Microsoft Defender [for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/). Durch das Blockieren von Feedbackschleifen sind Geräte in Ihrer Organisation besser vor Angriffen geschützt. 

## <a name="how-feedback-loop-blocking-works"></a>Funktionsweise der Feedbackschleifensperrung

Wenn ein verdächtiges Verhalten oder eine Datei erkannt wird, z. B. durch [Microsoft Defender Antivirus,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)werden Informationen zu diesem Artefakt an mehrere Klassifizierungen gesendet. Das Schnellschutzschleifenmodul prüft und korreliert die Informationen mit anderen Signalen, um eine Entscheidung darüber zu treffen, ob eine Datei blockiert werden soll. Das Überprüfen und Klassifizieren von Artefakten erfolgt schnell. Es führt zu einer schnellen Blockierung bestätigter Schadsoftware und treibt den Schutz im gesamten Ökosystem voran. 

Mit schnellem Schutz kann ein Angriff auf einem Gerät, auf anderen Geräten in der Organisation und auf Geräten in anderen Organisationen beendet werden, während ein Angriff versucht, seine Fußstapfen zu erweitern.


## <a name="configuring-feedback-loop-blocking"></a>Konfigurieren des Blockierens von Feedbackschleifen

Wenn Ihre Organisation Defender for Endpoint verwendet, ist das Blockieren von Feedbackschleifen standardmäßig aktiviert. Der schnelle Schutz erfolgt jedoch durch eine Kombination aus Defender for Endpoint-Funktionen, Funktionen zum Schutz von maschinellem Lernen und Signalfreigabe über Microsoft-Sicherheitsdienste hinweg. Stellen Sie sicher, dass die folgenden Features und Funktionen von Defender for Endpoint aktiviert und konfiguriert sind:

- [Microsoft Defender for Endpoint-Baselines](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [In Microsoft Defender for Endpoint integrierte Geräte](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [EDR im Blockmodus](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Verringerung der Angriffsfläche](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction):

- [Schutz der nächsten Generation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (Antivirus)

## <a name="related-articles"></a>Verwandte Artikel

- [Verhaltensbasiertes Blockieren und Eindämmen](behavioral-blocking-containment.md)

- [(Blog) Verhaltensblockierung und -eindämmung: Transformieren von Optik in Schutz](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [Hilfreiche Microsoft Defender for Endpoint-Ressourcen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
