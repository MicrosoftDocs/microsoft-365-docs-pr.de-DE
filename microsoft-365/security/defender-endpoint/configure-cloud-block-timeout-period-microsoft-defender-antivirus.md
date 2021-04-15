---
title: Konfigurieren des Timeoutzeitraums für Microsoft Defender Antivirus-Cloudblocks
description: Sie können konfigurieren, wie lange Microsoft Defender Antivirus die Ausführung einer Datei blockiert, während Sie auf eine Cloudermittlung warten.
keywords: Microsoft Defender Antivirus, Antischalware, Sicherheit, Defender, Cloud, Timeout, Block, Zeitraum, Sekunden
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 372d679f45d6f87392b612f757e6bdf1c6c6b9ad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765803"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Konfigurieren des Timeoutzeitraums für Cloudblocks

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Wenn Microsoft Defender Antivirus eine verdächtige Datei findet, kann sie die Ausführung der Datei verhindern, während sie den [Microsoft Defender Antivirus-Clouddienst abfragt.](cloud-protection-microsoft-defender-antivirus.md)

Der Standardzeitraum, für den die Datei blockiert [wird,](configure-block-at-first-sight-microsoft-defender-antivirus.md) beträgt 10 Sekunden. Sie können einen zusätzlichen Zeitraum angeben, bis die Datei ausgeführt werden darf. Dadurch kann sichergestellt werden, dass genügend Zeit zur Verfügung steht, um eine ordnungsgemäße Bestimmung vom Microsoft Defender Antivirus-Clouddienst zu erhalten.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Voraussetzungen für die Verwendung des erweiterten Timeouts für Cloudblocks

[Beim ersten Blick blockieren](configure-block-at-first-sight-microsoft-defender-antivirus.md) und die erforderlichen Komponenten müssen aktiviert sein, bevor Sie einen längeren Timeoutzeitraum angeben können.

## <a name="specify-the-extended-timeout-period"></a>Angeben des erweiterten Timeoutzeitraums

Sie können gruppenrichtlinien verwenden, um ein erweitertes Timeout für Cloudüberprüfungen anzugeben.

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.

3. Erweitern der Struktur auf **Windows-Komponenten > Microsoft Defender Antivirus > MpEngine**

4. Doppelklicken Sie auf **Erweiterte Cloudüberprüfung konfigurieren,** und stellen Sie sicher, dass die Option aktiviert ist. Geben Sie den zusätzlichen Zeitraum an, um zu verhindern, dass die Datei ausgeführt wird, während sie auf eine Cloudermittlung wartet. Sie können die zusätzliche Zeit in Sekunden zwischen 1 Sekunde und 50 Sekunden angeben. Diese Zeit wird den standardmäßigen 10 Sekunden hinzugefügt.

5. Klicken Sie auf **OK**.

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Verwenden von Antivirentechnologien der nächsten Generation durch Cloud-basierten Schutz](cloud-protection-microsoft-defender-antivirus.md)
- [Konfigurieren von Block bei erster Sicht](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Aktivieren des in der Cloud übermittelten Schutzes](enable-cloud-protection-microsoft-defender-antivirus.md)