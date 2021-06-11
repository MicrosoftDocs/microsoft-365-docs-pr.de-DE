---
title: Deaktivieren der Definition für Microsoft Defender Antivirus
description: Aktivieren Sie die Einstellung der Definition für Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, Antischadsoftware, Sicherheit, Defender, Einstellung der Definition
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 505270d319a78de20bf6fed01b7ca79c9fc2b400
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903804"
---
# <a name="turn-on-definition-retirement"></a>Deaktivieren der Definition

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können die Einstellung der Definition mithilfe von Gruppenrichtlinien konfigurieren. Die Einstellung der Definition überprüft, ob ein Computer über die erforderlichen Sicherheitsupdates verfügt, um ihn vor einer bestimmten Sicherheitslücke zu schützen. Wenn das System nicht anfällig für den durch eine Definition erkannten Exploit ist, wird diese Definition "eingestellt". Wenn alle Sicherheitsinformationen für ein bestimmtes Protokoll eingestellt werden, wird dieses Protokoll nicht mehr analysiert. Die Aktivierung dieses Features trägt zur Verbesserung der Leistung bei. Auf einem Computer, der mit den neuesten Sicherheitsupdates auf dem neuesten Stand ist, hat der Netzwerkschutz keine Auswirkungen auf die Netzwerkleistung.

## <a name="use-group-policy-to-configure-definition-retirement"></a>Konfigurieren der Einstellung von Definitionen mithilfe von Gruppenrichtlinien

1. Öffnen Sie auf Ihrem Gruppenrichtlinienverwaltungsendpunkt die [Gruppenrichtlinien-Verwaltungskonsole.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Wechseln Sie zu Administrative Vorlagen für die **Computerkonfiguration**  >    >  **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Netzwerküberprüfungssystem.** 

3. Wählen Sie "Deaktivieren der **Definition aktivieren" aus.** Diese Richtlinie ist standardmäßig aktiviert. Wenn **"Nicht konfiguriert" festgelegt** ist, ist die Einstellung der Definition aktiviert. 

4. Um die Richtlinie zu bearbeiten, wählen Sie den Link **"Richtlinieneinstellung bearbeiten"** aus.

5. Wählen Sie **"Aktiviert"** und dann **"OK"** aus.

6. Stellen Sie das aktualisierte Gruppenrichtlinienobjekt bereit. Siehe [Gruppenrichtlinien-Verwaltungskonsole.](/windows/win32/srvnodes/group-policy)

> [!TIP]
> Verwenden Sie gruppenrichtlinienobjekte lokal? Erfahren Sie, wie sie in der Cloud übersetzt werden. [Analysieren Sie Ihre lokalen Gruppenrichtlinienobjekte mithilfe von Gruppenrichtlinienanalysen in Microsoft Endpoint Manager – Vorschau](/mem/intune/configuration/group-policy-analytics). 
  
