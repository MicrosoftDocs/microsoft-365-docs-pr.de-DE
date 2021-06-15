---
title: Angeben der über die Cloud bereitgestellten Schutzebene für Microsoft Defender Antivirus
description: Legen Sie die Ebene des über die Cloud bereitgestellten Schutzes für Microsoft Defender Antivirus fest.
keywords: Microsoft Defender Antivirus, Antischadsoftware, Sicherheit, Defender, Cloud, Aggressivität, Schutzebene
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: fb4dd3114c411385f1a38cf7b0fd391a1b159b99
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924471"
---
# <a name="specify-the-cloud-delivered-protection-level"></a>Stufe des über die Cloud bereitgestellten Schutzes festlegen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Mit Microsoft Endpoint Manager (empfohlen) oder Gruppenrichtlinien können Sie den von Microsoft Defender Antivirus bereitgestellten Schutz in der Cloud angeben.

> [!TIP]
> Cloudschutz ist nicht nur Schutz für Dateien, die in der Cloud gespeichert sind. Der Microsoft Defender Antivirus Clouddienst ist ein Mechanismus zum Bereitstellen eines aktualisierten Schutzes für Ihr Netzwerk und Ihre Geräte (auch endpunkte genannt). Der Cloudschutz mit Microsoft Defender Antivirus verwendet verteilte Ressourcen und maschinelles Lernen, um Ihren Endpunkten einen Schutz zu bieten, der wesentlich schneller als herkömmliche Security Intelligence-Updates ist. Microsoft Intune und Microsoft Endpoint Manager sind jetzt Teil von [Microsoft Endpoint Manager.](/mem/endpoint-manager-overview) 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a>Verwenden sie Microsoft Endpoint Manager, um die Ebene des über die Cloud bereitgestellten Schutzes anzugeben.

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie **Endpunktsicherheits-Antivirus**  >  aus.

3. Wählen Sie ein Antivirusprofil aus. (Wenn Sie noch kein Profil haben oder ein neues Profil erstellen möchten, lesen Sie die Informationen unter [Konfigurieren von Einstellungen für Geräteeinschränkungen in Microsoft Intune.](/intune/device-restrictions-configure)

4. Wählen Sie **Eigenschaften** aus. Wählen Sie dann neben den **Konfigurationseinstellungen** **"Bearbeiten"** aus.

5. Erweitern Sie den **Cloudschutz,** und wählen Sie dann in der Liste der über die **Cloud bereitgestellten Schutzebene** eine der folgenden Optionen aus:

    1. **Hoch:** Wendet eine starke Erkennungsstufe an.
    2. **Hoch plus:** Verwendet die **Stufe "High"** und wendet zusätzliche Schutzmaßnahmen an (kann sich auf die Clientleistung auswirken).
    3. **Nulltoleranz:** Blockiert alle unbekannten ausführbaren Dateien.

6. Wählen Sie **"Überprüfen" und "Speichern"** und dann **"Speichern"** aus. 

> [!TIP]
> Benötigen Sie Hilfe? Informationen finden Sie in den folgenden Ressourcen:
> - [Konfigurieren Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Hinzufügen von Endpunktschutzeinstellungen in Intune](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a>Verwenden von Gruppenrichtlinien zum Angeben der Ebene des über die Cloud bereitgestellten Schutzes

1.  Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **"Bearbeiten".**

3.  Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu administrativen Vorlagen für die **Computerkonfiguration.**  >  

4.  Erweitern Sie die Struktur bis **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **MpEngine**.

5.  Doppelklicken Sie auf die Einstellung **"Cloudschutzebene auswählen",** und legen Sie sie auf **"Aktiviert"** fest. Wählen Sie die Schutzebene aus:
    - **Die Standardblockierungsstufe** bietet eine starke Erkennung, ohne das Risiko zu erhöhen, dass seriöse Dateien erkannt werden.
    - **Moderate Blockierungsstufe** bietet nur für Erkennungen mit hoher Konfidenz moderat
    - **Die hohe Blockierungsebene** wendet eine starke Erkennungsstufe bei gleichzeitiger Optimierung der Clientleistung an (kann aber auch eine höhere Wahrscheinlichkeit für falsch positive Ergebnisse bieten).
    - **Hohe + Blockierungsebene** wendet zusätzliche Schutzmaßnahmen an (kann sich auf die Clientleistung auswirken und Ihre Wahrscheinlichkeit falsch positiver Ergebnisse erhöhen).
    - **Die Blockierungsstufe Nulltoleranz** blockiert alle unbekannten ausführbaren Dateien.
    
    > [!WARNING]
    > Obwohl dies unwahrscheinlich ist, kann das Festlegen dieses Schalters auf **"Hoch"** oder **"Hoch +"** dazu führen, dass einige legitime Dateien erkannt werden (obwohl Sie die Möglichkeit haben, diese Erkennung aufzuheben oder zu infrage zu stellen).

6. Klicken Sie auf **OK**.

7. Stellen Sie das aktualisierte Gruppenrichtlinienobjekt bereit. Siehe [Gruppenrichtlinien-Verwaltungskonsole](/windows/win32/srvnodes/group-policy)

> [!TIP]
> Verwenden Sie gruppenrichtlinienobjekte lokal? Erfahren Sie, wie sie in der Cloud übersetzt werden. [Analysieren Sie Ihre lokalen Gruppenrichtlinienobjekte mithilfe von Gruppenrichtlinienanalysen in Microsoft Endpoint Manager – Vorschau](/mem/intune/configuration/group-policy-analytics). 
  
## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Aus der Cloud bereitgestellten Schutz aktivieren](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Erstellen und Bereitstellen von Antischadsoftwarerichtlinien: Cloud-Schutzdienst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)