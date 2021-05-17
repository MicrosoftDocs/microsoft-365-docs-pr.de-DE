---
title: Angeben zusätzlicher Definitionssätze für die Überprüfung des Netzwerkdatenverkehrs für Microsoft Defender Antivirus
description: Geben Sie zusätzliche Definitionssätze für die Überprüfung des Netzwerkdatenverkehrs für Microsoft Defender Antivirus an.
keywords: Microsoft Defender Antivirus, Antischalware, Sicherheit, Defender, Überprüfung des Netzwerkdatenverkehrs
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
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300195"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a>Angeben zusätzlicher Definitionssätze für die Überprüfung des Netzwerkdatenverkehrs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können zusätzliche Definitionssätze für die Überprüfung des Netzwerkdatenverkehrs mithilfe von Gruppenrichtlinien angeben.

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a>Verwenden von Gruppenrichtlinien zum Angeben zusätzlicher Definitionssätze für die Überprüfung des Netzwerkdatenverkehrs

1. Öffnen Sie auf dem Endpunkt für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Wechseln Sie **zu Windows-Komponenten**  >  **Microsoft Defender Antivirus** Network Inspection  >  **System**. 

3. Wählen **Sie Zusätzliche Definitionssätze für die Überprüfung des Netzwerkdatenverkehrs angeben aus.** Standardmäßig ist diese Richtlinie auf **Nicht konfiguriert festgelegt.** 

4. Wählen Sie zum Bearbeiten der Richtlinie den **Link Richtlinieneinstellung** bearbeiten aus.

5. Wählen **Sie Aktiviert** aus, und wählen Sie dann im Abschnitt **Optionen** die Option **Anzeigen...** aus.

6. Fügen Sie der Liste Einträge hinzu, und wählen Sie dann **OK aus.** 

   Jeder Eintrag muss als Name-Wert-Paar aufgeführt werden, wobei der Name eine Zeichenfolgendarstellung einer GUID für Definitionssatz ist. Die GUID des Definitionssatz zum Aktivieren der Testsicherheitsintelligenz ist beispielsweise wie folgt definiert: `{b54b6ac9-a737-498e-9120-6616ad3bf590}` . Der Wert wird nicht verwendet, daher wird empfohlen, ihn auf zu `0` setzen. 

7. Wählen **Sie OK** aus, und stellen Sie dann das aktualisierte Gruppenrichtlinienobjekt aus. Weitere [Informationen finden Sie unter Gruppenrichtlinienverwaltungskonsole](/windows/win32/srvnodes/group-policy).

> [!TIP]
> Verwenden Sie Gruppenrichtlinienobjekte lokal? Sehen Sie, wie sie in der Cloud übersetzen. [Analysieren Sie Ihre lokalen Gruppenrichtlinienobjekte mithilfe von Gruppenrichtlinienanalysen in Microsoft Endpoint Manager – Vorschau](/mem/intune/configuration/group-policy-analytics). 
  
## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
 
- [Aus der Cloud bereitgestellten Schutz aktivieren](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Erstellen und Bereitstellen von Antischalwarerichtlinien: Cloudschutzdienst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)