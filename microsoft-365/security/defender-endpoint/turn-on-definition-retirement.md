---
title: Aktivieren der Definitionsentgrenzung für Microsoft Defender Antivirus
description: Aktivieren sie die Definitionsentgrenzung für Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, Antischalware, Sicherheit, Verteidiger, Definitionsentgrenzung
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 66b2e882a0f6de21e27dabb3a4bfe2fe113bcb32
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296482"
---
# <a name="turn-on-definition-retirement"></a>Aktivieren der Definitionentgrenzung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können die Definitionentgrenzung mithilfe von Gruppenrichtlinien konfigurieren. Definitionsentgrenzung überprüft, ob ein Computer über die erforderlichen Sicherheitsupdates verfügt, um ihn vor einer bestimmten Sicherheitslücke zu schützen. Wenn das System nicht anfällig für den von einer Definition erkannten Exploit ist, ist diese Definition "eingestellt". Wenn alle Sicherheitsintelligenz für ein bestimmtes Protokoll eingestellt wird, wird dieses Protokoll nicht mehr analysiert. Wenn Sie dieses Feature aktivieren, können Sie die Leistung verbessern. Auf einem Computer, der mit allen neuesten Sicherheitsupdates auf dem neuesten Stand ist, hat der Netzwerkschutz keine Auswirkungen auf die Netzwerkleistung.

## <a name="use-group-policy-to-configure-definition-retirement"></a>Konfigurieren der Definitionsentgrenzung mithilfe von Gruppenrichtlinien

1. Öffnen Sie auf dem Endpunkt für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Wechseln Sie **zu Computerkonfiguration**  >  **Administrative Vorlagen** Windows  >  **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Netzwerkinspektionssystem**. 

3. Wählen **Sie Definitionsentgrenzung aktivieren aus.** Diese Richtlinie ist standardmäßig aktiviert. Wenn **"Nicht konfiguriert" festgelegt ist,** ist die Definitionsentgrenzung aktiviert. 

4. Wählen Sie zum Bearbeiten der Richtlinie den **Link Richtlinieneinstellung** bearbeiten aus.

5. Wählen **Sie Aktiviert** aus, und wählen Sie dann OK **aus.**

6. Stellen Sie ihr aktualisiertes Gruppenrichtlinienobjekt zur Bereitstellung. Weitere [Informationen finden Sie unter Gruppenrichtlinienverwaltungskonsole](/windows/win32/srvnodes/group-policy).

> [!TIP]
> Verwenden Sie Gruppenrichtlinienobjekte lokal? Sehen Sie, wie sie in der Cloud übersetzen. [Analysieren Sie Ihre lokalen Gruppenrichtlinienobjekte mithilfe der Gruppenrichtlinienanalyse in Microsoft Endpoint Manager – Vorschau](/mem/intune/configuration/group-policy-analytics). 
  
## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
 
- [Aus der Cloud bereitgestellten Schutz aktivieren](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Erstellen und Bereitstellen von Antischalwarerichtlinien: Cloudschutzdienst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)