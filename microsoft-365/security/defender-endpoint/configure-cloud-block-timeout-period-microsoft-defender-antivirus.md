---
title: Konfigurieren des Timeoutzeitraums für Microsoft Defender Antivirus Cloudblock
description: Sie können konfigurieren, wie lange Microsoft Defender Antivirus die Ausführung einer Datei blockieren, während Sie auf eine Cloudermittlung warten.
keywords: Microsoft Defender Antivirus, Antischadsoftware, Sicherheit, Defender, Cloud, Timeout, blockieren, Zeitraum, Sekunden
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789087"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Konfigurieren des Timeoutzeitraums für Cloudblockierung

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Wenn Microsoft Defender Antivirus eine verdächtige Datei findet, kann sie verhindern, dass die Datei ausgeführt wird, während sie den [Microsoft Defender Antivirus Clouddienst](cloud-protection-microsoft-defender-antivirus.md)abfragt.

Der Standardzeitraum, für den die Datei [blockiert](configure-block-at-first-sight-microsoft-defender-antivirus.md) wird, beträgt 10 Sekunden. Wenn Sie ein Sicherheitsadministrator sind, können Sie mehr Zeit angeben, bis die Datei ausgeführt werden darf. Durch die Erweiterung des Cloudblock-Timeoutzeitraums kann sichergestellt werden, dass genügend Zeit für eine ordnungsgemäße Entscheidung vom Microsoft Defender Antivirus Clouddienst vorhanden ist.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Voraussetzungen für die Verwendung des erweiterten Cloudblock-Timeouts

["Beim ersten Sichten blockieren"](configure-block-at-first-sight-microsoft-defender-antivirus.md) und seine Voraussetzungen müssen aktiviert sein, bevor Sie einen erweiterten Timeoutzeitraum angeben können.

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>Angeben des erweiterten Timeoutzeitraums mithilfe von Microsoft Endpoint Manager

Sie können den Cloudblock-Timeoutzeitraum mit einer [Endpunktsicherheitsrichtlinie in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy)angeben.

1. Wechseln Sie zum Endpoint Manager Admin Center ( [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) ), und melden Sie sich an.

2. Wählen Sie **Endpunktsicherheit** aus, und wählen Sie dann unter **"Verwalten"** die Option **"Antivirus"** aus.

3. Wählen (oder erstellen) Sie eine Antivirenrichtlinie.

4. Erweitern Sie im Abschnitt **"Konfigurationseinstellungen"** den **Cloudschutz.** Geben Sie dann im Feld **"Defender Cloud Extended Timeout In Seconds"** die mehr Zeit (in Sekunden) von 1 Sekunde bis 50 Sekunden an. Alles, was Sie angeben, wird den Standardmäßigen 10 Sekunden hinzugefügt.

5. (Dieser Schritt ist optional) Nehmen Sie weitere Änderungen an Ihrer Antivirenrichtlinie vor. (Benötigen Sie Hilfe? Informationen [zu Microsoft Defender Antivirus Richtlinie in Microsoft Intune finden Sie unter Einstellungen.)](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)

6. Wählen Sie **"Weiter"** aus, und beenden Sie die Konfiguration Ihrer Richtlinie.

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>Angeben des erweiterten Timeoutzeitraums mithilfe von Gruppenrichtlinien

Mithilfe von Gruppenrichtlinien können Sie ein erweitertes Timeout für Cloudüberprüfungen angeben.

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.

3. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und wählen Sie dann **administrative Vorlagen** aus.

3. Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **MpEngine**.

4. Doppelklicken Sie auf **"Erweiterte Cloudüberprüfung konfigurieren",** und stellen Sie sicher, dass die Option aktiviert ist. 

   Geben Sie den zusätzlichen Zeitraum an, um zu verhindern, dass die Datei ausgeführt wird, während sie auf eine Cloudermittlung wartet. Geben Sie die zusätzliche Zeit in Sekunden von 1 Sekunde bis 50 Sekunden an. Alles, was Sie angeben, wird den Standardmäßigen 10 Sekunden hinzugefügt.

5. Wählen Sie **OK** aus.

 