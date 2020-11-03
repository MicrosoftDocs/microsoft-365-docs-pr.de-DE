---
title: Ausführen von Aktionen für erweiterte Jagd Abfrageergebnisse in Microsoft 365 Defender
description: Schnelles Adressieren von Bedrohungen und betroffenen Objekten in den Suchergebnissen der erweiterten Suche
keywords: Erweiterte Jagd, Bedrohungs Suche, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Take Action
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 506af82ec08ad6cd8dbeece5c1c2741e09e4817a
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842464"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="80e62-104">Aktionen für erweiterte Jagd Abfrageergebnisse ausführen</span><span class="sxs-lookup"><span data-stu-id="80e62-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="80e62-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="80e62-105">**Applies to:**</span></span>
- <span data-ttu-id="80e62-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80e62-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="80e62-107">Sie können schnell Bedrohungen enthalten oder gefährdete Objekte, die Sie in [Advanced Hunting](advanced-hunting-overview.md) finden, mit leistungsstarken und umfassenden Aktionsoptionen befassen.</span><span class="sxs-lookup"><span data-stu-id="80e62-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="80e62-108">Mit diesen Optionen können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="80e62-108">With these options, you can:</span></span>

- <span data-ttu-id="80e62-109">Ausführen verschiedener Aktionen auf Geräten</span><span class="sxs-lookup"><span data-stu-id="80e62-109">Take various actions on devices</span></span>
- <span data-ttu-id="80e62-110">Quarantänedateien</span><span class="sxs-lookup"><span data-stu-id="80e62-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="80e62-111">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="80e62-111">Required permissions</span></span>
<span data-ttu-id="80e62-112">Um durch erweiterte Jagd Aktionen durchführen zu können, benötigen Sie eine Rolle in Microsoft Defender für Endpoint mit [Berechtigungen zum Übermitteln von Korrekturaktionen auf Geräten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="80e62-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="80e62-113">Wenn Sie keine Aktion ausführen können, wenden Sie sich an einen globalen Administrator, um die folgende Berechtigung zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="80e62-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="80e62-114">*Aktive Korrekturaktionen > Threat and Vulnerability Management – Korrektur Behandlung*</span><span class="sxs-lookup"><span data-stu-id="80e62-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="80e62-115">Ausführen verschiedener Aktionen auf Geräten</span><span class="sxs-lookup"><span data-stu-id="80e62-115">Take various actions on devices</span></span>
<span data-ttu-id="80e62-116">Sie können die folgenden Aktionen auf Geräten durchführen, die von der `DeviceId` Spalte in den Abfrageergebnissen identifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="80e62-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="80e62-117">Isolieren der betroffenen Geräte für eine Infektion oder verhindern, dass Angriffe seitlich verschoben werden</span><span class="sxs-lookup"><span data-stu-id="80e62-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="80e62-118">Ermittlungs Paket sammeln, um mehr forensische Informationen zu erhalten</span><span class="sxs-lookup"><span data-stu-id="80e62-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="80e62-119">Ausführen eines Antivirus-Scans zum Auffinden und Entfernen von Bedrohungen mithilfe der neuesten Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="80e62-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="80e62-120">Initiieren einer automatisierten Untersuchung zum Überprüfen und Beheben von Bedrohungen auf dem Gerät und möglicherweise anderen betroffenen Geräten</span><span class="sxs-lookup"><span data-stu-id="80e62-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="80e62-121">Einschränken der APP-Ausführung auf nur von Microsoft signierte ausführbare Dateien, um nachfolgende Bedrohungen durch Schadsoftware oder andere nicht vertrauenswürdige ausführbare Dateien zu verhindern</span><span class="sxs-lookup"><span data-stu-id="80e62-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="80e62-122">Weitere Informationen zur Ausführung dieser Antwort Aktionen über Microsoft Defender for Endpoint finden [Sie unter Informationen zu Antwort Aktionen auf Geräten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span><span class="sxs-lookup"><span data-stu-id="80e62-122">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="80e62-123">Quarantänedateien</span><span class="sxs-lookup"><span data-stu-id="80e62-123">Quarantine files</span></span>
<span data-ttu-id="80e62-124">Sie können die *Quarantäne* -Aktion für Dateien bereitstellen, damit Sie automatisch isoliert werden, wenn Sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="80e62-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="80e62-125">Wenn Sie diese Aktion auswählen, können Sie zwischen den folgenden Spalten wählen, um zu ermitteln, welche Dateien in der Abfrage zu Quarantäne gehören:</span><span class="sxs-lookup"><span data-stu-id="80e62-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="80e62-126">`SHA1` — In den meisten erweiterten Jagd Tabellen ist dies der SHA-1 der Datei, der von der aufgezeichneten Aktion betroffen war.</span><span class="sxs-lookup"><span data-stu-id="80e62-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="80e62-127">Wenn beispielsweise eine Datei kopiert wurde, wäre dies die kopierte Datei.</span><span class="sxs-lookup"><span data-stu-id="80e62-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="80e62-128">`InitiatingProcessSHA1` — In den meisten erweiterten Jagd Tabellen ist dies die Datei, die für das Initiieren der aufgezeichneten Aktion zuständig ist.</span><span class="sxs-lookup"><span data-stu-id="80e62-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="80e62-129">Wenn beispielsweise ein untergeordneter Prozess gestartet wurde, wäre dies der übergeordnete Prozess.</span><span class="sxs-lookup"><span data-stu-id="80e62-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="80e62-130">`SHA256` – Dies ist das SHA-256-Äquivalent der Datei, die durch die Spalte identifiziert wird `SHA1` .</span><span class="sxs-lookup"><span data-stu-id="80e62-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="80e62-131">`InitiatingProcessSHA256` – Dies ist das SHA-256-Äquivalent der Datei, die durch die Spalte identifiziert wird `InitiatingProcessSHA1` .</span><span class="sxs-lookup"><span data-stu-id="80e62-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="80e62-132">Weitere Informationen zur Verwendung von Quarantäneaktionen und zur Wiederherstellung von Dateien finden [Sie unter Informationen zu Antwort Aktionen für Dateien](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span><span class="sxs-lookup"><span data-stu-id="80e62-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="80e62-133">Um Dateien zu finden und zu isolieren, sollten die Abfrageergebnisse auch `DeviceId` Werte als Gerätebezeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="80e62-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="80e62-134">Aktion ausführen</span><span class="sxs-lookup"><span data-stu-id="80e62-134">Take action</span></span>
<span data-ttu-id="80e62-135">Wenn Sie eine der beschriebenen Aktionen ausführen möchten, wählen Sie einen oder mehrere Datensätze in den Abfrageergebnissen aus, und wählen Sie dann **Take Actions** aus.</span><span class="sxs-lookup"><span data-stu-id="80e62-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="80e62-136">Ein Assistent führt Sie durch den Prozess des Auswählens und dann übermitteln Ihrer bevorzugten Aktionen.</span><span class="sxs-lookup"><span data-stu-id="80e62-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Bild des ausgewählten Datensatzes mit dem Bereich für die Überprüfung des Datensatzes](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="80e62-138">Überprüfen der ausgeführten Aktionen</span><span class="sxs-lookup"><span data-stu-id="80e62-138">Review actions taken</span></span>
<span data-ttu-id="80e62-139">Jede Aktion wird einzeln im [Action Center](mtp-action-center.md) unter dem Security.Microsoft.com/Action-Center/History ( **Action Center**  >  **History** ) aufgezeichnet. [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="80e62-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="80e62-140">Wechseln Sie zum Aktionscenter, um den Status der einzelnen Aktionen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="80e62-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="80e62-141">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="80e62-141">Related topics</span></span>
- [<span data-ttu-id="80e62-142">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="80e62-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="80e62-143">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="80e62-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="80e62-144">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="80e62-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="80e62-145">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="80e62-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="80e62-146">Übersicht über das Aktionscenter</span><span class="sxs-lookup"><span data-stu-id="80e62-146">Action center overview</span></span>](mtp-action-center.md)
