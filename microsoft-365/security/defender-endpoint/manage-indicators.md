---
title: Indikatoren erstellen
ms.reviewer: ''
description: Erstellen sie Indikatoren für einen Dateihash, eine IP-Adresse, URLs oder Domänen, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.
keywords: verwalten, zulässig, blockiert, blockieren, sauber, bösartig, Dateihash, IP-Adresse, URLs, Domäne
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
ms.openlocfilehash: fb87f36c5289d622df2615046c5bb2fd8fad9543
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842242"
---
# <a name="create-indicators"></a>Indikatoren erstellen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Der Kompromissindikator (Indicator of Compromise, IoCs) ist ein wesentliches Feature in jeder Endpunktschutzlösung. Diese Funktion bietet SecOps die Möglichkeit, eine Liste von Indikatoren für die Erkennung und die Blockierung (Verhinderung und Reaktion) festzulegen.

Erstellen Sie Indikatoren, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren. Sie können die auszuführende Aktion sowie die Dauer für das Anwenden der Aktion sowie den Bereich der Gerätegruppe definieren, auf die sie angewendet werden soll.

Derzeit unterstützte Quellen sind das Clouderkennungsmodul von Defender für Endpunkt, das automatisierte Untersuchungs- und Wartungsmodul und das Modul zur Endpunktverhinderung (Microsoft Defender Antivirus).

**Cloud-Erkennungsmodul**<br>
Das Clouderkennungsmodul von Defender für Endpunkt überprüft regelmäßig gesammelte Daten und versucht, die von Ihnen festgelegten Indikatoren zuzuordnen. Wenn eine Übereinstimmung vorliegt, wird die Aktion gemäß den Einstellungen ausgeführt, die Sie für ioC angegeben haben.

**Endpunktverhütungsmodul**<br>
Die gleiche Liste von Indikatoren wird vom Präventions-Agent berücksichtigt. Wenn Microsoft Defender AV also der primäre konfigurierte AV ist, werden die übereinstimmenden Indikatoren entsprechend den Einstellungen behandelt. Wenn die Aktion z. B. "Warnung und Blockierung" lautet, verhindert Microsoft Defender AV Dateiausführungen (blockieren und korrigieren), und eine entsprechende Warnung wird ausgelöst. Wenn die Aktion hingegen auf "Zulassen" festgelegt ist, erkennt oder blockiert Microsoft Defender AV die Ausführung der Datei nicht.

**Automatisiertes Untersuchungs- und Wartungsmodul**<BR>
Die automatische Untersuchung und Korrektur verhält sich gleich. Wenn ein Indikator auf "Zulassen" festgelegt ist, ignoriert die automatisierte Untersuchung und Behebung ein "schlechtes" Bewertungszeichen dafür. Wenn sie auf "Blockieren" festgelegt ist, wird sie von der automatischen Untersuchung und Behebung als "schlecht" behandelt.

> [!NOTE]
> Die EnableFileHashComputation-Einstellung berechnet den Dateihash für das Zertifikat und die Datei-IoC während Dateiüberprüfungen. Es unterstützt die IoC-Erzwingung von Hashes und Zertifikaten, die zu vertrauenswürdigen Anwendungen gehören. Sie wird gleichzeitig aktiviert und mit der Einstellung "Datei zulassen" oder "Datei blockieren" deaktiviert. EnableFileHashComputation wird manuell über die Gruppenrichtlinie aktiviert und ist standardmäßig deaktiviert.


Die aktuellen unterstützten Aktionen sind:
- Zulassen
- Nur Warnung
- Warnung und Blockierung


Sie können einen Indikator für Folgendes erstellen:
- [Files](indicator-file.md)
- [IP-Adressen, URLs/Domänen](indicator-ip-domain.md)
- [Zertifikate](indicator-certificates.md)


> [!NOTE]
> Es gibt einen Grenzwert von 15.000 Indikatoren pro Mandant. Datei- und Zertifikatindikatoren blockieren keine [Ausschlüsse, die für Microsoft Defender Antivirus definiert sind.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus) Indikatoren werden in Microsoft Defender Antivirus nicht unterstützt, wenn sie sich im passiven Modus befinden. 


## <a name="related-topics"></a>Verwandte Themen

- [Erstellen von Kontext-IoC](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [Verwenden der Microsoft Defender für Endpunkt-Indikatoren-API](ti-indicator.md)
- [Verwenden von integrierten Partnerlösungen](partner-applications.md)
