---
title: Feedback-Loop-Blockierung
description: Das Blockieren von Feedbackschleifen, auch als schneller Schutz bezeichnet, ist Teil der Funktionen zum Blockieren und Eindämmen von Verhaltensweisen in Microsoft Defender für Endpunkt.
keywords: Verhaltensblockierung, schneller Schutz, Feedbackblockierung, Microsoft Defender für Endpunkt
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
ms.openlocfilehash: 7319ff5a89a20529eed7d36aa0d0b1522013abd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842458"
---
# <a name="feedback-loop-blocking"></a>Feedback-Loop-Blockierung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a>Übersicht

Das Blockieren von Feedbackschleifen, auch als schneller Schutz bezeichnet, ist eine Komponente der Funktionen zum [Blockieren und Eindämmen](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) von Verhaltensweisen in [Microsoft Defender für Endpunkt.](/windows/security/threat-protection/) Dank der Blockierung der Feedbackschleife sind Geräte in Ihrer Organisation besser vor Angriffen geschützt. 

## <a name="how-feedback-loop-blocking-works"></a>Funktionsweise der Blockierung von Feedbackschleifen

Wenn ein verdächtiges Verhalten oder eine Datei erkannt wird, z. B. durch [Microsoft Defender Antivirus,](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)werden Informationen zu diesem Artefakt an mehrere Klassifizierer gesendet. Das Modul für schnelle Schutzschleifen prüft und korreliert die Informationen mit anderen Signalen, um zu einer Entscheidung zu gelangen, ob eine Datei blockiert werden soll. Das Überprüfen und Klassifizieren von Artefakten erfolgt schnell. Dies führt zu einer schnellen Blockierung bestätigter Schadsoftware und treibt den Schutz im gesamten Ökosystem voran. 

Bei schnellem Schutz kann ein Angriff auf einem Gerät, auf anderen Geräten in der Organisation und auf Geräten in anderen Organisationen beendet werden, da ein Angriff versucht, seine Reichweite zu erweitern.


## <a name="configuring-feedback-loop-blocking"></a>Konfigurieren der Blockierung von Feedbackschleifen

Wenn Ihre Organisation Defender für Endpunkt verwendet, ist das Blockieren von Feedbackschleifen standardmäßig aktiviert. Der schnelle Schutz erfolgt jedoch durch eine Kombination aus Defender für Endpunkt-Funktionen, Machine Learning-Schutzfeatures und Signalfreigabe über Microsoft-Sicherheitsdienste hinweg. Stellen Sie sicher, dass die folgenden Features und Funktionen von Defender für Endpunkt aktiviert und konfiguriert sind:

- [Microsoft Defender für Endpunkt-Basispläne](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Geräte, die in Microsoft Defender für Endpunkt integriert sind](/microsoft-365/security/defender-endpoint/onboard-configure)

- [EDR im Blockmodus](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Verringerung der Angriffsfläche](/microsoft-365/security/defender-endpoint/attack-surface-reduction):

- [Schutz](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) der nächsten Generation (Antivirus)

## <a name="related-articles"></a>Verwandte Artikel

- [Verhaltensbasiertes Blockieren und Eindämmen](behavioral-blocking-containment.md)

- [(Blog) Blockieren und Eindämmen von Verhaltensweisen: Umwandeln von Optik in Schutz](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [Hilfreiche Microsoft Defender für Endpunkt-Ressourcen](/microsoft-365/security/defender-endpoint/helpful-resources)
