---
title: Ergreifen von Aktionen für erweiterte Suchergebnisse in Microsoft 365 Defender
description: Schnelles Adressieren von Bedrohungen und betroffenen Ressourcen in ihren erweiterten Suchergebnissen
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, take action
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 15eebbba102640a92f9c7712194aaef685a96cfb
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952608"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="49001-104">Ergreifen von Maßnahmen für erweiterte Suchabfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="49001-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="49001-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="49001-105">**Applies to:**</span></span>
- <span data-ttu-id="49001-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49001-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="49001-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="49001-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="49001-108">Mithilfe leistungsstarker und umfassender Aktionsoptionen können [](advanced-hunting-overview.md) Sie schnell Bedrohungen oder gefährdete Ressourcen in der erweiterten Suche enthalten.</span><span class="sxs-lookup"><span data-stu-id="49001-108">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="49001-109">Mit diesen Optionen können Sie:</span><span class="sxs-lookup"><span data-stu-id="49001-109">With these options, you can:</span></span>

- <span data-ttu-id="49001-110">Ausführen verschiedener Aktionen auf Geräten</span><span class="sxs-lookup"><span data-stu-id="49001-110">Take various actions on devices</span></span>
- <span data-ttu-id="49001-111">Quarantänedateien</span><span class="sxs-lookup"><span data-stu-id="49001-111">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="49001-112">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="49001-112">Required permissions</span></span>
<span data-ttu-id="49001-113">Um maßnahmen über die erweiterte Suche ergreifen zu können, benötigen Sie eine Rolle in Microsoft Defender for Endpoint mit Berechtigungen zum Übermitteln von Korrekturaktionen [auf Geräten.](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)</span><span class="sxs-lookup"><span data-stu-id="49001-113">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="49001-114">Wenn Sie keine Aktion ergreifen können, wenden Sie sich an einen globalen Administrator, um die folgende Berechtigung zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="49001-114">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="49001-115">*Aktive Korrekturaktionen > Bedrohung und Sicherheitsrisikomanagement – Behandlung von Abhilfemaßnahmen*</span><span class="sxs-lookup"><span data-stu-id="49001-115">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="49001-116">Ausführen verschiedener Aktionen auf Geräten</span><span class="sxs-lookup"><span data-stu-id="49001-116">Take various actions on devices</span></span>
<span data-ttu-id="49001-117">Sie können die folgenden Aktionen auf Geräten ausführen, die von der `DeviceId` Spalte in Den Abfrageergebnissen identifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="49001-117">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="49001-118">Isolieren betroffener Geräte, um eine Infektion zu enthalten oder zu verhindern, dass Angriffe sich lateral bewegen</span><span class="sxs-lookup"><span data-stu-id="49001-118">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="49001-119">Sammeln von Untersuchungspaketen, um weitere forensische Informationen zu erhalten</span><span class="sxs-lookup"><span data-stu-id="49001-119">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="49001-120">Ausführen einer Antivirenscan zum Suchen und Entfernen von Bedrohungen mithilfe der neuesten Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="49001-120">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="49001-121">Initiieren einer automatisierten Untersuchung zur Überprüfung und Behebung von Bedrohungen auf dem Gerät und möglicherweise anderen betroffenen Geräten</span><span class="sxs-lookup"><span data-stu-id="49001-121">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="49001-122">Beschränken der App-Ausführung auf von Microsoft signierte ausführbare Dateien, um nachfolgende Bedrohungsaktivitäten durch Schadsoftware oder andere nicht vertrauenswürdige ausführbare Dateien zu verhindern</span><span class="sxs-lookup"><span data-stu-id="49001-122">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="49001-123">Weitere Informationen dazu, wie diese Reaktionsaktionen über Microsoft Defender for Endpoint ausgeführt werden, finden Sie [unter Reaktionsaktionen auf Geräten.](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)</span><span class="sxs-lookup"><span data-stu-id="49001-123">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="49001-124">Quarantänedateien</span><span class="sxs-lookup"><span data-stu-id="49001-124">Quarantine files</span></span>
<span data-ttu-id="49001-125">Sie können die *Quarantäneaktion* für Dateien bereitstellen, sodass sie bei Auftreten automatisch isoliert werden.</span><span class="sxs-lookup"><span data-stu-id="49001-125">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="49001-126">Beim Auswählen dieser Aktion können Sie zwischen den folgenden Spalten auswählen, um zu bestimmen, welche Dateien in Ihren Abfrageergebnissen isoliert werden sollen:</span><span class="sxs-lookup"><span data-stu-id="49001-126">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="49001-127">`SHA1` – In den meisten erweiterten Nachsuchetabellen ist dies sha-1 der Datei, die von der aufgezeichneten Aktion betroffen war.</span><span class="sxs-lookup"><span data-stu-id="49001-127">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="49001-128">Wenn beispielsweise eine Datei kopiert wurde, wäre dies die kopierte Datei.</span><span class="sxs-lookup"><span data-stu-id="49001-128">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="49001-129">`InitiatingProcessSHA1` – In den meisten erweiterten Nachsuchetabellen ist dies die Datei, die für das Initiieren der aufgezeichneten Aktion verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="49001-129">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="49001-130">Wenn beispielsweise ein untergeordneter Prozess gestartet wurde, wäre dies der übergeordnete Prozess.</span><span class="sxs-lookup"><span data-stu-id="49001-130">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="49001-131">`SHA256` – Dies ist das SHA-256-Äquivalent der durch die Spalte identifizierten `SHA1` Datei.</span><span class="sxs-lookup"><span data-stu-id="49001-131">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="49001-132">`InitiatingProcessSHA256` – Dies ist das SHA-256-Äquivalent der durch die Spalte identifizierten `InitiatingProcessSHA1` Datei.</span><span class="sxs-lookup"><span data-stu-id="49001-132">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="49001-133">Weitere Informationen dazu, wie Quarantäneaktionen ergriffen werden und wie Dateien wiederhergestellt werden können, finden Sie unter [Reaktionsaktionen für Dateien](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span><span class="sxs-lookup"><span data-stu-id="49001-133">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="49001-134">Um Dateien zu suchen und unter Quarantäne zu stellen, sollten die Abfrageergebnisse auch `DeviceId` Werte als Gerätebezeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="49001-134">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="49001-135">Maßnahmen ergreifen</span><span class="sxs-lookup"><span data-stu-id="49001-135">Take action</span></span>
<span data-ttu-id="49001-136">Wenn Sie eine der beschriebenen Aktionen ausführen möchten, wählen Sie einen oder mehrere Datensätze in den Abfrageergebnissen aus, und wählen Sie **dann Aktionen ausführen aus.**</span><span class="sxs-lookup"><span data-stu-id="49001-136">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="49001-137">Ein Assistent führt Sie durch den Prozess der Auswahl und anschließenden Übermittlung Ihrer bevorzugten Aktionen.</span><span class="sxs-lookup"><span data-stu-id="49001-137">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Bild des ausgewählten Datensatzes mit Bereich zum Überprüfen des Datensatzes](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="49001-139">Überprüfen der ergriffenen Aktionen</span><span class="sxs-lookup"><span data-stu-id="49001-139">Review actions taken</span></span>
<span data-ttu-id="49001-140">Jede Aktion wird einzeln im [](m365d-action-center.md) Aktionscenter unter **Aktionscenterverlauf**  >   ( security.microsoft.com/action-center/history )[aufgezeichnet.](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="49001-140">Each action is individually recorded in the [action center](m365d-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="49001-141">Wechseln Sie zum Aktionscenter, um den Status der einzelnen Aktionen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="49001-141">Go to the action center to check the status of each action.</span></span>
 
>[!NOTE]
><span data-ttu-id="49001-142">Einige Tabellen in diesem Artikel sind möglicherweise nicht in Microsoft Defender for Endpoint verfügbar.</span><span class="sxs-lookup"><span data-stu-id="49001-142">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="49001-143">[Aktivieren Sie Microsoft 365 Defender,](m365d-enable.md) um bedrohungen mithilfe von weiteren Datenquellen nach Bedrohungen zu fahnen.</span><span class="sxs-lookup"><span data-stu-id="49001-143">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="49001-144">Sie können Ihre workflows für die erweiterte Suche von Microsoft Defender for Endpoint zu Microsoft 365 Defender verschieben, indem Sie die Schritte unter [Migrate advanced hunting queries from Microsoft Defender for Endpoint ausführen.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="49001-144">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="49001-145">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="49001-145">Related topics</span></span>
- [<span data-ttu-id="49001-146">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="49001-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="49001-147">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="49001-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="49001-148">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="49001-148">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="49001-149">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="49001-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="49001-150">Übersicht über das Aktionscenter</span><span class="sxs-lookup"><span data-stu-id="49001-150">Action center overview</span></span>](m365d-action-center.md)
