---
title: Untersuchen von Problemen mit der Integrität von Agents
description: Informationen zu den beim Ausführen des mdatp-Integritätsbefehls zurückgegebenen Werten
keywords: mdatp health, command, health, status, command, onboarding status
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
ms.openlocfilehash: acc75a931cb14a7aab729c09a7b835fb9f26d1d1
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281176"
---
# <a name="investigate-agent-health-issues"></a>Untersuchen von Problemen mit der Integrität von Agents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Die folgende Tabelle enthält Informationen zu den beim Ausführen des Befehls zurückgegebenen Werten und `mdatp health` den entsprechenden Beschreibungen.

| Wert | Beschreibung |
|-|-|
| automatic_definition_update_enabled | True, wenn automatische Antivirendefinitionsupdates aktiviert sind, andernfalls false. |
|  cloud_automatic_sample_submission_consent | Aktuelle Beispielübermittlungsstufe. Kann einer der folgenden Werte sein:     <br><br>  - **Keine**: Es werden keine verdächtigen Beispiele an Microsoft übermittelt.  <br> <br>     - **Sicher:** Nur verdächtige Beispiele, die keine personenbezogenen Informationen (PII) enthalten, werden automatisch übermittelt. Dies ist der Standardwert für diese Einstellung.    <br> <br>   - **Alle**: Alle verdächtigen Beispiele werden an Microsoft übermittelt.   |
| cloud_diagnostic_enabled | True, wenn die optionale Diagnosedatensammlung aktiviert ist, andernfalls false. Weitere Informationen zu Defender for Endpoint und anderen Produkten und Diensten wie Microsoft Defender Antivirus und Windows 10 finden Sie unter [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=827576). |
| cloud_enabled | True, wenn der in der Cloud übermittelte Schutz aktiviert ist, andernfalls false. |
| conflicting_applications | Liste der Anwendungen, die möglicherweise in Konflikt mit Microsoft Defender for Endpoint stehen. Diese Liste enthält, aber nicht beschränkt auf, andere Sicherheitsprodukte und andere Anwendungen, die Bekannte sind, um Kompatibilitätsprobleme zu verursachen. |
| definitions_status | Status der Antivirendefinitionen. |
| definitions_updated | Datum und Uhrzeit des letzten Antivirusdefinitionsupdates. |
| definitions_updated_minutes_ago | Anzahl der Minuten seit dem letzten Antivirendefinitionsupdate. |
| definitions_version | Antivirusdefinitionsversion. |
| edr_client_version | Version des EDR, der auf dem Gerät ausgeführt wird. |
| edr_configuration_version | EDR Konfigurationsversion. |
| edr_device_tags | Liste der dem Gerät zugeordneten Tags. |
| edr_group_ids | Gruppen-ID, der das Gerät zugeordnet ist. |
| edr_machine_id | Geräte-ID, die in Microsoft Defender Security Center. |
| engine_version | Version des Antivirusmoduls. |
| healthy | True, wenn das Produkt fehlerfrei ist, andernfalls false. |
| lizenziert | True, wenn das Gerät in einen Mandanten onboarded ist, andernfalls false. |
| log_level | Aktuelle Protokollebene für das Produkt. |
| machine_guid | Eindeutige Computer-ID, die von der Antivirenkomponente verwendet wird. |
| network_protection_status                 | Status der Netzwerkschutzkomponente (nur macOS). Kann einer der folgenden Werte sein:       <br> <br>- **start** – Netzwerkschutz wird gestartet  <br> <br>     - **failed_to_start** – Netzwerkschutz konnte aufgrund eines Fehlers nicht gestartet werden   <br> <br>    - **gestartet** – Netzwerkschutz wird derzeit auf dem Gerät ausgeführt     <br> <br>  - **Neustart :** Netzwerkschutz wird derzeit neu gestartet   <br> <br>    - **beenden** – Netzwerkschutz wird beendet     <br> <br>  - **beendet** – Netzwerkschutz wird nicht ausgeführt |
| org_id | Organisation, in die das Gerät onboardiert ist. Wenn das Gerät noch nicht in eine Organisation onboardiert ist, wird dies nicht gedruckt. Weitere Informationen zum Onboarding finden Sie [unter Onboarding bei Microsoft Defender for Endpoint](onboarding.md). |
| passive_mode_enabled | True, wenn die Antivirenkomponente im passiven Modus ausgeführt werden soll, andernfalls false. |
| product_expiration | Datum und Uhrzeit, zu dem die aktuelle Produktversion das Ende der Unterstützung erreicht. |
| real_time_protection_available | True, wenn die Echtzeitschutzkomponente fehlerfrei ist, andernfalls false. |
| real_time_protection_enabled | True, wenn der Echtzeit-Antivirusschutz aktiviert ist, andernfalls false. |
| real_time_protection_subsystem | Subsystem, das zum Schutz in Echtzeit verwendet wird. Wenn der Echtzeitschutz nicht wie erwartet ausgeführt wird, wird nicht gedruckt. |
| release_ring | Freigabering. Weitere Informationen finden Sie unter   [Bereitstellungsringe](deployment-rings.md). |