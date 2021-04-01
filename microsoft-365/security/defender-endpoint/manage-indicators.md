---
title: Indikatoren erstellen
ms.reviewer: ''
description: 'Erstellen Sie Indikatoren für einen Dateihash, eine #A0, URLs oder Domänen, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.'
keywords: manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 481051b74c1be88ba78bbd44e4fc0c174ed0bdad
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470893"
---
# <a name="create-indicators"></a>Indikatoren erstellen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Der Kompromissindikator (IoCs) ist ein wesentliches Feature in jeder Endpunktschutzlösung. Diese Funktion bietet SecOps die Möglichkeit, eine Liste von Indikatoren für die Erkennung und das Blockieren (Verhinderung und Reaktion) zu erstellen.

Erstellen Sie Indikatoren, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren. Sie können die zu ergreifende Aktion sowie die Dauer für die Anwendung der Aktion sowie den Bereich der Gerätegruppe definieren, auf die sie angewendet werden soll.

Derzeit unterstützte Quellen sind das Clouderkennungsmodul von Defender for Endpoint, das automatisierte Untersuchungs- und Korrekturmodul und das Modul zur Verhinderung von Endpunkten (Microsoft Defender Antivirus).

**Clouderkennungsmodul**<br>
Das Clouderkennungsmodul von Defender for Endpoint überprüft regelmäßig gesammelte Daten und versucht, die von Ihnen festgelegten Indikatoren zu entsprechen. Wenn eine Übereinstimmung vor liegt, werden die Aktionen entsprechend den Einstellungen ausgeführt, die Sie für das IoC angegeben haben.

**Endpoint Prevention Engine**<br>
Die gleiche Liste von Indikatoren wird vom Präventions-Agent berücksichtigt. Wenn Microsoft Defender AV die primäre AV-Konfiguration ist, werden die übereinstimmende Indikatoren entsprechend den Einstellungen behandelt. Wenn die Aktion z. B. "Warnung und Block" ist, verhindert Microsoft Defender AV Dateiausführungen (blockieren und beugen) und eine entsprechende Warnung wird ausgelöst. Wenn die Aktion jedoch auf "Zulassen" festgelegt ist, erkennt oder blockiert Microsoft Defender AV die Ausführung der Datei nicht.

**Automatisiertes Untersuchungs- und Korrekturmodul**<BR>
Die automatisierte Untersuchung und Korrektur verhält sich gleich. Wenn ein Indikator auf "Zulassen" festgelegt ist, ignoriert die automatisierte Untersuchung und Korrektur ein "schlechtes" Urteil dafür. Wenn sie auf "Block" festgelegt ist, wird die automatische Untersuchung und Korrektur als "schlecht" behandelt.

> [!NOTE]
> Die Einstellung EnableFileHashComputation berechnet den Dateihash für das Zertifikat und die Datei IoC während der Dateiscans. Es unterstützt die #A0 von Hashes und Certs gehören zu vertrauenswürdigen Anwendungen. Sie wird gleichzeitig aktiviert und mit der Einstellung "Zulassen" oder "Blockieren" deaktiviert. EnableFileHashComputation wird manuell über die Gruppenrichtlinie aktiviert und standardmäßig deaktiviert.


Die derzeit unterstützten Aktionen sind:
- Zulassen
- Nur Warnung
- Warnung und Blockierung


Sie können einen Indikator für:
- [Files](indicator-file.md)
- [IP-Adressen, URLs/Domänen](indicator-ip-domain.md)
- [Zertifikate](indicator-certificates.md)


> [!NOTE]
> Es gibt eine Grenze von 15.000 Indikatoren pro Mandant. Datei- und Zertifikatindikatoren blockieren keine [für Microsoft Defender Antivirus definierten Ausschlüsse.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus) Indikatoren werden in Microsoft Defender Antivirus nicht unterstützt, wenn sie sich im passiven Modus befinden. 


## <a name="related-topics"></a>Verwandte Themen

- [Erstellen von kontextbezogenem IoC](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [Verwenden der Microsoft Defender for Endpoint Indicators-API](ti-indicator.md)
- [Verwenden von partnerintegrierte Lösungen](partner-applications.md)
