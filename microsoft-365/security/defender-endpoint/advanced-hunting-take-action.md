---
title: Ergreifen von Maßnahmen zu erweiterten Suchabfrageergebnissen in Microsoft Threat Protection
description: Schnelles Adressieren von Bedrohungen und betroffenen Ressourcen in ihren erweiterten Suchergebnissen
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Mdatp, Microsoft Defender Atp, wdatp-Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Timeout vermeiden, Befehlszeilen, Prozess-ID
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 79d720a8b996f826548b79834e5d5c2048e28c2b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067415"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="7ac2c-104">Ergreifen von Maßnahmen für erweiterte Suchabfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="7ac2c-104">Take action on advanced hunting query results</span></span>

<span data-ttu-id="7ac2c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7ac2c-105">**Applies to:**</span></span>
- [<span data-ttu-id="7ac2c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7ac2c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="7ac2c-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="7ac2c-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7ac2c-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="7ac2c-109">Mithilfe leistungsstarker und umfassender Aktionsoptionen können [](advanced-hunting-overview.md) Sie schnell Bedrohungen oder gefährdete Ressourcen in der erweiterten Suche enthalten.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-109">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="7ac2c-110">Mit diesen Optionen können Sie:</span><span class="sxs-lookup"><span data-stu-id="7ac2c-110">With these options, you can:</span></span>

- <span data-ttu-id="7ac2c-111">Ausführen verschiedener Aktionen auf Geräten</span><span class="sxs-lookup"><span data-stu-id="7ac2c-111">Take various actions on devices</span></span>
- <span data-ttu-id="7ac2c-112">Quarantänedateien</span><span class="sxs-lookup"><span data-stu-id="7ac2c-112">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="7ac2c-113">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7ac2c-113">Required permissions</span></span>

<span data-ttu-id="7ac2c-114">Um über erweiterte Suche Maßnahmen ergreifen zu können, benötigen Sie eine Rolle in Defender for Endpoint mit Berechtigungen zum Übermitteln von Korrekturaktionen [auf Geräten.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options)</span><span class="sxs-lookup"><span data-stu-id="7ac2c-114">To be able to take action through advanced hunting, you need a role in Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options).</span></span> <span data-ttu-id="7ac2c-115">Wenn Sie keine Aktion ergreifen können, wenden Sie sich an einen globalen Administrator, um die folgende Berechtigung zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="7ac2c-115">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="7ac2c-116">*Aktive Abhilfemaßnahmen > Bedrohungs- und Sicherheitsrisikoverwaltung – Behandlung von Abhilfemaßnahmen*</span><span class="sxs-lookup"><span data-stu-id="7ac2c-116">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="7ac2c-117">Ausführen verschiedener Aktionen auf Geräten</span><span class="sxs-lookup"><span data-stu-id="7ac2c-117">Take various actions on devices</span></span>

<span data-ttu-id="7ac2c-118">Sie können die folgenden Aktionen auf Geräten ausführen, die von der `DeviceId` Spalte in den Abfrageergebnissen identifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="7ac2c-118">You can take the following actions on devices identified by the `DeviceId` column in your query results:</span></span>

- <span data-ttu-id="7ac2c-119">Isolieren betroffener Geräte, um eine Infektion zu enthalten oder zu verhindern, dass Angriffe sich lateral bewegen</span><span class="sxs-lookup"><span data-stu-id="7ac2c-119">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="7ac2c-120">Sammeln von Untersuchungspaketen, um weitere forensische Informationen zu erhalten</span><span class="sxs-lookup"><span data-stu-id="7ac2c-120">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="7ac2c-121">Ausführen einer Antivirenscan zum Suchen und Entfernen von Bedrohungen mithilfe der neuesten Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="7ac2c-121">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="7ac2c-122">Initiieren einer automatisierten Untersuchung zur Überprüfung und Behebung von Bedrohungen auf dem Gerät und möglicherweise anderen betroffenen Geräten</span><span class="sxs-lookup"><span data-stu-id="7ac2c-122">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="7ac2c-123">Beschränken der App-Ausführung auf von Microsoft signierte ausführbare Dateien, um nachfolgende Bedrohungsaktivitäten durch Schadsoftware oder andere nicht vertrauenswürdige ausführbare Dateien zu verhindern</span><span class="sxs-lookup"><span data-stu-id="7ac2c-123">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="7ac2c-124">Weitere Informationen dazu, wie diese Reaktionsaktionen über Defender for Endpoint ausgeführt werden, finden Sie [unter Reaktionsaktionen auf Geräten.](respond-machine-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="7ac2c-124">To learn more about how these response actions are performed through Defender for Endpoint, [read about response actions on devices](respond-machine-alerts.md).</span></span>

## <a name="quarantine-files"></a><span data-ttu-id="7ac2c-125">Quarantänedateien</span><span class="sxs-lookup"><span data-stu-id="7ac2c-125">Quarantine files</span></span>

<span data-ttu-id="7ac2c-126">Sie können die *Quarantäneaktion* für Dateien bereitstellen, sodass sie bei Auftreten automatisch isoliert werden.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-126">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="7ac2c-127">Beim Auswählen dieser Aktion können Sie zwischen den folgenden Spalten auswählen, um zu bestimmen, welche Dateien in Ihren Abfrageergebnissen isoliert werden sollen:</span><span class="sxs-lookup"><span data-stu-id="7ac2c-127">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="7ac2c-128">`SHA1` – In den meisten erweiterten Nachsuchetabellen ist dies sha-1 der Datei, die von der aufgezeichneten Aktion betroffen war.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-128">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="7ac2c-129">Wenn beispielsweise eine Datei kopiert wurde, wäre dies die kopierte Datei.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-129">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="7ac2c-130">`InitiatingProcessSHA1` – In den meisten erweiterten Nachsuchetabellen ist dies die Datei, die für das Initiieren der aufgezeichneten Aktion verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-130">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="7ac2c-131">Wenn beispielsweise ein untergeordneter Prozess gestartet wurde, wäre dies der übergeordnete Prozess.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-131">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="7ac2c-132">`SHA256` – Dies ist das SHA-256-Äquivalent der durch die Spalte identifizierten `SHA1` Datei.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-132">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="7ac2c-133">`InitiatingProcessSHA256` – Dies ist das SHA-256-Äquivalent der durch die Spalte identifizierten `InitiatingProcessSHA1` Datei.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-133">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="7ac2c-134">Weitere Informationen dazu, wie Quarantäneaktionen ergriffen werden und wie Dateien wiederhergestellt werden können, finden Sie unter [Reaktionsaktionen für Dateien](respond-file-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="7ac2c-134">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](respond-file-alerts.md).</span></span>

>[!NOTE]
><span data-ttu-id="7ac2c-135">Um Dateien zu suchen und unter Quarantäne zu stellen, sollten die Abfrageergebnisse auch `DeviceId` Werte als Gerätebezeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-135">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="7ac2c-136">Maßnahmen ergreifen</span><span class="sxs-lookup"><span data-stu-id="7ac2c-136">Take action</span></span>

<span data-ttu-id="7ac2c-137">Wenn Sie eine der beschriebenen Aktionen ausführen möchten, wählen Sie einen oder mehrere Datensätze in den Abfrageergebnissen aus, und wählen Sie **dann Aktionen ausführen aus.**</span><span class="sxs-lookup"><span data-stu-id="7ac2c-137">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="7ac2c-138">Ein Assistent führt Sie durch den Prozess der Auswahl und anschließenden Übermittlung Ihrer bevorzugten Aktionen.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-138">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Bild des ausgewählten Datensatzes mit Bereich zum Überprüfen des Datensatzes](images/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="7ac2c-140">Überprüfen der ergriffenen Aktionen</span><span class="sxs-lookup"><span data-stu-id="7ac2c-140">Review actions taken</span></span>

<span data-ttu-id="7ac2c-141">Jede Aktion wird einzeln im Aktionscenter unter **Aktionscenterverlauf**  >   ( security.microsoft.com/action-center/history )[aufgezeichnet.](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="7ac2c-141">Each action is individually recorded in the action center, under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="7ac2c-142">Wechseln Sie zum Aktionscenter, um den Status der einzelnen Aktionen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-142">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="7ac2c-143">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7ac2c-143">Related topics</span></span>

- [<span data-ttu-id="7ac2c-144">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="7ac2c-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7ac2c-145">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="7ac2c-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7ac2c-146">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="7ac2c-146">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="7ac2c-147">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="7ac2c-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="7ac2c-148">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="7ac2c-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="7ac2c-149">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="7ac2c-149">Custom detections overview</span></span>](overview-custom-detections.md)
