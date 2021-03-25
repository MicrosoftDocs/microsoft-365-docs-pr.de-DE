---
title: Ergreifen von Maßnahmen für erweiterte Suchergebnisse in Microsoft 365 Defender
description: Schnelles Adressieren von Bedrohungen und betroffenen Ressourcen in ihren erweiterten Suchergebnissen
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Maßnahmen ergreifen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 4c90441bb7a492ac38c5fcb560d9246b3a0005b0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064727"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="3785d-104">Ergreifen von Maßnahmen für erweiterte Suchabfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="3785d-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3785d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3785d-105">**Applies to:**</span></span>
- <span data-ttu-id="3785d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3785d-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="3785d-107">Mithilfe leistungsstarker und umfassender Aktionsoptionen können [](advanced-hunting-overview.md) Sie schnell Bedrohungen oder gefährdete Ressourcen in der erweiterten Suche enthalten.</span><span class="sxs-lookup"><span data-stu-id="3785d-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="3785d-108">Mit diesen Optionen können Sie:</span><span class="sxs-lookup"><span data-stu-id="3785d-108">With these options, you can:</span></span>

- <span data-ttu-id="3785d-109">Ausführen verschiedener Aktionen auf Geräten</span><span class="sxs-lookup"><span data-stu-id="3785d-109">Take various actions on devices</span></span>
- <span data-ttu-id="3785d-110">Quarantänedateien</span><span class="sxs-lookup"><span data-stu-id="3785d-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="3785d-111">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3785d-111">Required permissions</span></span>
<span data-ttu-id="3785d-112">Um maßnahmen über die erweiterte Suche ergreifen zu können, benötigen Sie eine Rolle in Microsoft Defender for Endpoint mit Berechtigungen zum Übermitteln von Korrekturaktionen [auf Geräten.](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)</span><span class="sxs-lookup"><span data-stu-id="3785d-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="3785d-113">Wenn Sie keine Aktion ergreifen können, wenden Sie sich an einen globalen Administrator, um die folgende Berechtigung zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="3785d-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="3785d-114">*Aktive Abhilfemaßnahmen > Bedrohungs- und Sicherheitsrisikoverwaltung – Behandlung von Abhilfemaßnahmen*</span><span class="sxs-lookup"><span data-stu-id="3785d-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="3785d-115">Ausführen verschiedener Aktionen auf Geräten</span><span class="sxs-lookup"><span data-stu-id="3785d-115">Take various actions on devices</span></span>
<span data-ttu-id="3785d-116">Sie können die folgenden Aktionen auf Geräten ausführen, die von der `DeviceId` Spalte in Den Abfrageergebnissen identifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="3785d-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="3785d-117">Isolieren betroffener Geräte, um eine Infektion zu enthalten oder zu verhindern, dass Angriffe sich lateral bewegen</span><span class="sxs-lookup"><span data-stu-id="3785d-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="3785d-118">Sammeln von Untersuchungspaketen, um weitere forensische Informationen zu erhalten</span><span class="sxs-lookup"><span data-stu-id="3785d-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="3785d-119">Ausführen einer Antivirenscan zum Suchen und Entfernen von Bedrohungen mithilfe der neuesten Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="3785d-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="3785d-120">Initiieren einer automatisierten Untersuchung zur Überprüfung und Behebung von Bedrohungen auf dem Gerät und möglicherweise anderen betroffenen Geräten</span><span class="sxs-lookup"><span data-stu-id="3785d-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="3785d-121">Beschränken der App-Ausführung auf von Microsoft signierte ausführbare Dateien, um nachfolgende Bedrohungsaktivitäten durch Schadsoftware oder andere nicht vertrauenswürdige ausführbare Dateien zu verhindern</span><span class="sxs-lookup"><span data-stu-id="3785d-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="3785d-122">Weitere Informationen dazu, wie diese Reaktionsaktionen über Microsoft Defender for Endpoint ausgeführt werden, finden Sie [unter Reaktionsaktionen auf Geräten.](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)</span><span class="sxs-lookup"><span data-stu-id="3785d-122">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="3785d-123">Quarantänedateien</span><span class="sxs-lookup"><span data-stu-id="3785d-123">Quarantine files</span></span>
<span data-ttu-id="3785d-124">Sie können die *Quarantäneaktion* für Dateien bereitstellen, sodass sie bei Auftreten automatisch isoliert werden.</span><span class="sxs-lookup"><span data-stu-id="3785d-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="3785d-125">Beim Auswählen dieser Aktion können Sie zwischen den folgenden Spalten auswählen, um zu bestimmen, welche Dateien in Ihren Abfrageergebnissen isoliert werden sollen:</span><span class="sxs-lookup"><span data-stu-id="3785d-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="3785d-126">`SHA1` – In den meisten erweiterten Nachsuchetabellen ist dies sha-1 der Datei, die von der aufgezeichneten Aktion betroffen war.</span><span class="sxs-lookup"><span data-stu-id="3785d-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="3785d-127">Wenn beispielsweise eine Datei kopiert wurde, wäre dies die kopierte Datei.</span><span class="sxs-lookup"><span data-stu-id="3785d-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="3785d-128">`InitiatingProcessSHA1` – In den meisten erweiterten Nachsuchetabellen ist dies die Datei, die für das Initiieren der aufgezeichneten Aktion verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="3785d-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="3785d-129">Wenn beispielsweise ein untergeordneter Prozess gestartet wurde, wäre dies der übergeordnete Prozess.</span><span class="sxs-lookup"><span data-stu-id="3785d-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="3785d-130">`SHA256` – Dies ist das SHA-256-Äquivalent der durch die Spalte identifizierten `SHA1` Datei.</span><span class="sxs-lookup"><span data-stu-id="3785d-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="3785d-131">`InitiatingProcessSHA256` – Dies ist das SHA-256-Äquivalent der durch die Spalte identifizierten `InitiatingProcessSHA1` Datei.</span><span class="sxs-lookup"><span data-stu-id="3785d-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="3785d-132">Weitere Informationen dazu, wie Quarantäneaktionen ergriffen werden und wie Dateien wiederhergestellt werden können, finden Sie unter [Reaktionsaktionen für Dateien](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span><span class="sxs-lookup"><span data-stu-id="3785d-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="3785d-133">Um Dateien zu suchen und unter Quarantäne zu stellen, sollten die Abfrageergebnisse auch `DeviceId` Werte als Gerätebezeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="3785d-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="3785d-134">Maßnahmen ergreifen</span><span class="sxs-lookup"><span data-stu-id="3785d-134">Take action</span></span>
<span data-ttu-id="3785d-135">Wenn Sie eine der beschriebenen Aktionen ausführen möchten, wählen Sie einen oder mehrere Datensätze in den Abfrageergebnissen aus, und wählen Sie **dann Aktionen ausführen aus.**</span><span class="sxs-lookup"><span data-stu-id="3785d-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="3785d-136">Ein Assistent führt Sie durch den Prozess der Auswahl und anschließenden Übermittlung Ihrer bevorzugten Aktionen.</span><span class="sxs-lookup"><span data-stu-id="3785d-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Bild des ausgewählten Datensatzes mit Bereich zum Überprüfen des Datensatzes](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="3785d-138">Überprüfen der ergriffenen Aktionen</span><span class="sxs-lookup"><span data-stu-id="3785d-138">Review actions taken</span></span>
<span data-ttu-id="3785d-139">Jede Aktion wird einzeln im [](m365d-action-center.md) Aktionscenter unter **Aktionscenterverlauf**  >   ( security.microsoft.com/action-center/history )[aufgezeichnet.](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="3785d-139">Each action is individually recorded in the [action center](m365d-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="3785d-140">Wechseln Sie zum Aktionscenter, um den Status der einzelnen Aktionen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3785d-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="3785d-141">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3785d-141">Related topics</span></span>
- [<span data-ttu-id="3785d-142">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="3785d-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3785d-143">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="3785d-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3785d-144">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="3785d-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="3785d-145">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="3785d-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3785d-146">Übersicht über das Aktionscenter</span><span class="sxs-lookup"><span data-stu-id="3785d-146">Action center overview</span></span>](m365d-action-center.md)
