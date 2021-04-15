---
title: Angeben der in der Cloud übermittelten Schutzstufe für Microsoft Defender Antivirus
description: Legen Sie Die Stufe des cloudbasierten Schutzes für Microsoft Defender Antivirus ein.
keywords: Microsoft Defender Antivirus, Antischalware, Sicherheit, Verteidiger, Cloud, Aggressivität, Schutzstufe
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: a0c73c8dd341c4940e3eddd4ede75240e57502d6
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764121"
---
# <a name="specify-the-cloud-delivered-protection-level"></a>Angeben der in der Cloud übermittelten Schutzstufe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können Ihren Grad an cloudbasiertem Schutz angeben, der von Microsoft Defender Antivirus angeboten wird, indem Sie Microsoft Endpoint Manager (empfohlen) oder Gruppenrichtlinien verwenden.

> [!TIP]
> Cloudschutz ist nicht nur Schutz für Dateien, die in der Cloud gespeichert sind. Der Microsoft Defender Antivirus-Clouddienst ist ein Mechanismus zum Bereitstellen aktualisierten Schutzes für Ihr Netzwerk und Ihre Geräte (auch Endpunkte genannt). Der Cloudschutz mit Microsoft Defender Antivirus verwendet verteilte Ressourcen und maschinelles Lernen, um Ihren Endpunkten Schutz zu bieten, die wesentlich schneller als herkömmliche Sicherheitsintelligenzupdates ist. Microsoft Intune und Microsoft Endpoint Manager sind jetzt Teil von [Microsoft Endpoint Manager](/mem/endpoint-manager-overview). 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a>Verwenden von Microsoft Endpoint Manager zum Angeben der Ebene des in der Cloud zugestellten Schutzes

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.

2. Wählen **Sie Endpoint security**  >  **Antivirus** aus.

3. Wählen Sie ein Antivirusprofil aus. (Wenn Sie noch kein Profil haben oder ein neues Profil erstellen möchten, lesen Sie Konfigurieren von Geräteeinschränkungseinstellungen [in Microsoft Intune](/intune/device-restrictions-configure).

4. Wählen Sie **Eigenschaften** aus. Wählen Sie dann neben **Konfigurationseinstellungen** bearbeiten **aus.**

5. Erweitern **Sie den** Cloudschutz, und wählen Sie dann in der Liste der von der Cloud übermittelten **Schutzebenen** eine der folgenden Optionen aus:

    1. **High**: Wendet eine starke Erkennungsstufe an.
    2. **High plus**: Verwendet die **High-Ebene** und wendet zusätzliche Schutzmaßnahmen an (kann sich auf die Clientleistung auswirken).
    3. **Nulltoleranz**: Blockiert alle unbekannten ausführbaren Dateien.

6. Wählen **Sie Überprüfen + Speichern** aus, und wählen Sie dann Speichern **aus.** 

> [!TIP]
> Benötigen Sie Hilfe? Informationen finden Sie in den folgenden Ressourcen:
> - [Konfigurieren von Endpunktschutz](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Hinzufügen von Endpunktschutzeinstellungen in Intune](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a>Verwenden von Gruppenrichtlinien zum Angeben der Ebene des in der Cloud übermittelten Schutzes

1.  Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **Bearbeiten**.

3.  Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**  >  **Administrative Vorlagen**.

4.  Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus**  >  **MpEngine**.

5.  Doppelklicken Sie auf **die Einstellung Cloudschutzstufe auswählen,** und legen Sie sie auf **Aktiviert .** Wählen Sie die Schutzebene aus:
    - **Die Standardblockierstufe** bietet eine starke Erkennung, ohne das Risiko zu erhöhen, legitime Dateien zu erkennen.
    - **Moderate Sperrstufe bietet** nur moderate Unterstützung für Erkennungen mit hoher Vertrauenssicherheit
    - **Bei hoher Blockierungsebene** wird eine starke Erkennungsebene angewendet, während die Clientleistung optimiert wird (sie kann ihnen jedoch auch eine höhere Wahrscheinlichkeit von falsch positiven Ergebnisse bieten).
    - **Hohe + Blockierungsstufe** wendet zusätzliche Schutzmaßnahmen an (kann sich auf die Clientleistung auswirken und die Wahrscheinlichkeit falsch positiver Ergebnisse erhöhen).
    - **Die Sperrstufe "Nulltoleranz"** blockiert alle unbekannten ausführbaren Dateien.
    
    > [!WARNING]
    > Obwohl es unwahrscheinlich ist, kann das Festlegen dieser Option auf **Hoch** oder **Hoch +** dazu führen, dass einige legitime Dateien erkannt werden (obwohl Sie die Blockierung aufheben oder diese Erkennung in Frage stellen können).

6. Klicken Sie auf **OK**.

7. Stellen Sie ihr aktualisiertes Gruppenrichtlinienobjekt zur Bereitstellung. Siehe [Gruppenrichtlinienverwaltungskonsole](/windows/win32/srvnodes/group-policy)

> [!TIP]
> Verwenden Sie Gruppenrichtlinienobjekte lokal? Sehen Sie, wie sie in der Cloud übersetzen. [Analysieren Sie Ihre lokalen Gruppenrichtlinienobjekte mithilfe von Gruppenrichtlinienanalysen in Microsoft Endpoint Manager – Vorschau](/mem/intune/configuration/group-policy-analytics). 
  
## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Aktivieren des in der Cloud übermittelten Schutzes](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Erstellen und Bereitstellen von Antischalwarerichtlinien: Cloudschutzdienst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)