---
title: Festlegen von Einstellungen für Microsoft Defender for Endpoint auf Dem Mac
description: Konfigurieren Sie MMicrosoft Defender for Endpoint auf Dem Mac in Unternehmensorganisationen.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b706cb8dbd43d545768c1c573021b5ef401e3c09
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346402"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="68f72-104">Festlegen von Einstellungen für Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="68f72-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="68f72-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="68f72-105">**Applies to:**</span></span>

- [<span data-ttu-id="68f72-106">Microsoft Defender für Endpunkt unter Mac OS</span><span class="sxs-lookup"><span data-stu-id="68f72-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="68f72-107">Dieser Artikel enthält Anweisungen zum Festlegen von Einstellungen für Microsoft Defender for Endpoint auf macOS in Unternehmensorganisationen.</span><span class="sxs-lookup"><span data-stu-id="68f72-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="68f72-108">Informationen zum Konfigurieren von Microsoft Defender for Endpoint unter macOS über die Befehlszeilenschnittstelle finden Sie unter [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="68f72-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="68f72-109">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="68f72-109">Summary</span></span>

<span data-ttu-id="68f72-110">In Unternehmensorganisationen kann Microsoft Defender for Endpoint unter macOS über ein Konfigurationsprofil verwaltet werden, das mithilfe eines von mehreren Verwaltungstools bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="68f72-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="68f72-111">Einstellungen, die vom Sicherheitsbetriebsteam verwaltet werden, haben Vorrang vor Einstellungen, die lokal auf dem Gerät festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="68f72-112">Das Ändern der Einstellungen, die über das Konfigurationsprofil festgelegt werden, erfordert eskalierte Berechtigungen und ist für Benutzer ohne Administratorberechtigungen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="68f72-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="68f72-113">Dieser Artikel beschreibt die Struktur des Konfigurationsprofils, enthält ein empfohlenes Profil, das Sie für die ersten Schritte verwenden können, und enthält Anweisungen zum Bereitstellen des Profils.</span><span class="sxs-lookup"><span data-stu-id="68f72-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="68f72-114">Konfigurationsprofilstruktur</span><span class="sxs-lookup"><span data-stu-id="68f72-114">Configuration profile structure</span></span>

<span data-ttu-id="68f72-115">Das Konfigurationsprofil ist eine *.plist-Datei,* die aus Einträgen besteht, die durch einen Schlüssel identifiziert werden (der den Namen der Einstellung angibt), gefolgt von einem Wert, der von der Art der Einstellung abhängt.</span><span class="sxs-lookup"><span data-stu-id="68f72-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="68f72-116">Werte können entweder einfach (z. B. ein numerischer Wert) oder komplex sein, z. B. eine geschachtelte Liste von Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="68f72-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="68f72-117">Das Layout des Konfigurationsprofils hängt von der verwendeten Verwaltungskonsole ab.</span><span class="sxs-lookup"><span data-stu-id="68f72-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="68f72-118">Die folgenden Abschnitte enthalten Beispiele für Konfigurationsprofile für JAMF und Intune.</span><span class="sxs-lookup"><span data-stu-id="68f72-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="68f72-119">Die oberste Ebene des Konfigurationsprofils enthält produktweite Einstellungen und Einträge für Unterbereiche von Microsoft Defender for Endpoint, die in den nächsten Abschnitten ausführlicher erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="68f72-120">Einstellungen des Antivirusmoduls</span><span class="sxs-lookup"><span data-stu-id="68f72-120">Antivirus engine preferences</span></span>

<span data-ttu-id="68f72-121">Der *Abschnitt antivirusEngine* des Konfigurationsprofils wird verwendet, um die Einstellungen der Antiviruskomponente von Microsoft Defender for Endpoint zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="68f72-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="68f72-122">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-122">Section</span></span>|<span data-ttu-id="68f72-123">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-124">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-125">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-125">**Key**</span></span> | <span data-ttu-id="68f72-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="68f72-126">antivirusEngine</span></span> |
| <span data-ttu-id="68f72-127">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-127">**Data type**</span></span> | <span data-ttu-id="68f72-128">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="68f72-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="68f72-129">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-129">**Comments**</span></span> | <span data-ttu-id="68f72-130">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="68f72-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="68f72-131">Aktivieren/Deaktivieren des Echtzeitschutzes</span><span class="sxs-lookup"><span data-stu-id="68f72-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="68f72-132">Geben Sie an, ob der Echtzeitschutz aktiviert werden soll, der Dateien beim Zugriff überprüft.</span><span class="sxs-lookup"><span data-stu-id="68f72-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="68f72-133">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-133">Section</span></span>|<span data-ttu-id="68f72-134">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-135">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-136">**Key**</span></span> | <span data-ttu-id="68f72-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="68f72-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="68f72-138">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-138">**Data type**</span></span> | <span data-ttu-id="68f72-139">Boolesch</span><span class="sxs-lookup"><span data-stu-id="68f72-139">Boolean</span></span> |
| <span data-ttu-id="68f72-140">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-140">**Possible values**</span></span> | <span data-ttu-id="68f72-141">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="68f72-141">true (default)</span></span> <br/> <span data-ttu-id="68f72-142">false</span><span class="sxs-lookup"><span data-stu-id="68f72-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="68f72-143">Aktivieren/Deaktivieren des passiven Modus</span><span class="sxs-lookup"><span data-stu-id="68f72-143">Enable / disable passive mode</span></span>

<span data-ttu-id="68f72-144">Geben Sie an, ob das Antivirenmodul im passiven Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="68f72-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="68f72-145">Der passive Modus hat die folgenden Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="68f72-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="68f72-146">Echtzeitschutz ist deaktiviert</span><span class="sxs-lookup"><span data-stu-id="68f72-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="68f72-147">Die Überprüfung bei Bedarf ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="68f72-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="68f72-148">Automatische Bedrohungsbehebung ist deaktiviert</span><span class="sxs-lookup"><span data-stu-id="68f72-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="68f72-149">Sicherheitsintelligenzupdates sind aktiviert</span><span class="sxs-lookup"><span data-stu-id="68f72-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="68f72-150">Statusmenüsymbol ist ausgeblendet</span><span class="sxs-lookup"><span data-stu-id="68f72-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="68f72-151">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-151">Section</span></span>|<span data-ttu-id="68f72-152">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-153">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-154">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-154">**Key**</span></span> | <span data-ttu-id="68f72-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="68f72-155">passiveMode</span></span> |
| <span data-ttu-id="68f72-156">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-156">**Data type**</span></span> | <span data-ttu-id="68f72-157">Boolesch</span><span class="sxs-lookup"><span data-stu-id="68f72-157">Boolean</span></span> |
| <span data-ttu-id="68f72-158">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-158">**Possible values**</span></span> | <span data-ttu-id="68f72-159">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="68f72-159">false (default)</span></span> <br/> <span data-ttu-id="68f72-160">true</span><span class="sxs-lookup"><span data-stu-id="68f72-160">true</span></span> |
| <span data-ttu-id="68f72-161">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-161">**Comments**</span></span> | <span data-ttu-id="68f72-162">Verfügbar in Microsoft Defender for Endpoint, Version 100.67.60 oder höher.</span><span class="sxs-lookup"><span data-stu-id="68f72-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="68f72-163">Ausschlusszusammenführungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="68f72-163">Exclusion merge policy</span></span>

<span data-ttu-id="68f72-164">Geben Sie die Seriendruckrichtlinie für Ausschlüsse an.</span><span class="sxs-lookup"><span data-stu-id="68f72-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="68f72-165">Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Ausschlüssen ( ) oder nur vom Administrator definierten `merge` Ausschlüssen ( `admin_only` ) sein.</span><span class="sxs-lookup"><span data-stu-id="68f72-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="68f72-166">Diese Einstellung kann verwendet werden, um lokale Benutzer an der Definition eigener Ausschlüsse zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="68f72-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="68f72-167">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-167">Section</span></span>|<span data-ttu-id="68f72-168">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-169">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-170">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-170">**Key**</span></span> | <span data-ttu-id="68f72-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="68f72-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="68f72-172">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-172">**Data type**</span></span> | <span data-ttu-id="68f72-173">String</span><span class="sxs-lookup"><span data-stu-id="68f72-173">String</span></span> |
| <span data-ttu-id="68f72-174">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-174">**Possible values**</span></span> | <span data-ttu-id="68f72-175">merge (Standard)</span><span class="sxs-lookup"><span data-stu-id="68f72-175">merge (default)</span></span> <br/> <span data-ttu-id="68f72-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="68f72-176">admin_only</span></span> |
| <span data-ttu-id="68f72-177">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-177">**Comments**</span></span> | <span data-ttu-id="68f72-178">Verfügbar in Microsoft Defender for Endpoint, Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="68f72-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="68f72-179">Scannen von Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="68f72-179">Scan exclusions</span></span>

<span data-ttu-id="68f72-180">Geben Sie Entitäten an, die von der Gescannten ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="68f72-181">Ausschlüsse können durch vollständige Pfade, Erweiterungen oder Dateinamen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="68f72-182">(Ausschlüsse werden als Array von Elementen angegeben, der Administrator kann so viele Elemente wie nötig in beliebiger Reihenfolge angeben.)</span><span class="sxs-lookup"><span data-stu-id="68f72-182">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|<span data-ttu-id="68f72-183">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-183">Section</span></span>|<span data-ttu-id="68f72-184">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-184">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-185">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-185">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-186">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-186">**Key**</span></span> | <span data-ttu-id="68f72-187">Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="68f72-187">exclusions</span></span> |
| <span data-ttu-id="68f72-188">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-188">**Data type**</span></span> | <span data-ttu-id="68f72-189">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="68f72-189">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="68f72-190">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-190">**Comments**</span></span> | <span data-ttu-id="68f72-191">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="68f72-191">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="68f72-192">Art des Ausschlusses</span><span class="sxs-lookup"><span data-stu-id="68f72-192">Type of exclusion</span></span>

<span data-ttu-id="68f72-193">Geben Sie Inhalte an, die vom Typ ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-193">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="68f72-194">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-194">Section</span></span>|<span data-ttu-id="68f72-195">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-196">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-197">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-197">**Key**</span></span> | <span data-ttu-id="68f72-198">$type</span><span class="sxs-lookup"><span data-stu-id="68f72-198">$type</span></span> |
| <span data-ttu-id="68f72-199">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-199">**Data type**</span></span> | <span data-ttu-id="68f72-200">String</span><span class="sxs-lookup"><span data-stu-id="68f72-200">String</span></span> |
| <span data-ttu-id="68f72-201">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-201">**Possible values**</span></span> | <span data-ttu-id="68f72-202">excludedPath</span><span class="sxs-lookup"><span data-stu-id="68f72-202">excludedPath</span></span> <br/> <span data-ttu-id="68f72-203">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="68f72-203">excludedFileExtension</span></span> <br/> <span data-ttu-id="68f72-204">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="68f72-204">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="68f72-205">Pfad zu ausgeschlossenen Inhalten</span><span class="sxs-lookup"><span data-stu-id="68f72-205">Path to excluded content</span></span>

<span data-ttu-id="68f72-206">Geben Sie Inhalte an, die nicht durch den vollständigen Dateipfad gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-206">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="68f72-207">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-207">Section</span></span>|<span data-ttu-id="68f72-208">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-208">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-209">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-209">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-210">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-210">**Key**</span></span> | <span data-ttu-id="68f72-211">path</span><span class="sxs-lookup"><span data-stu-id="68f72-211">path</span></span> |
| <span data-ttu-id="68f72-212">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-212">**Data type**</span></span> | <span data-ttu-id="68f72-213">String</span><span class="sxs-lookup"><span data-stu-id="68f72-213">String</span></span> |
| <span data-ttu-id="68f72-214">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-214">**Possible values**</span></span> | <span data-ttu-id="68f72-215">gültige Pfade</span><span class="sxs-lookup"><span data-stu-id="68f72-215">valid paths</span></span> |
| <span data-ttu-id="68f72-216">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-216">**Comments**</span></span> | <span data-ttu-id="68f72-217">Gilt nur, *$type* *ausgeschlossen IstPath*</span><span class="sxs-lookup"><span data-stu-id="68f72-217">Applicable only if *$type* is *excludedPath*</span></span> |

## <a name="supported-exclusion-types"></a><span data-ttu-id="68f72-218">Unterstützte Ausschlusstypen</span><span class="sxs-lookup"><span data-stu-id="68f72-218">Supported exclusion types</span></span>

<span data-ttu-id="68f72-219">In der folgenden Tabelle sind die Ausschlusstypen aufgeführt, die von Defender for Endpoint auf Dem Mac unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-219">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="68f72-220">Ausschluss</span><span class="sxs-lookup"><span data-stu-id="68f72-220">Exclusion</span></span> | <span data-ttu-id="68f72-221">Definition</span><span class="sxs-lookup"><span data-stu-id="68f72-221">Definition</span></span> | <span data-ttu-id="68f72-222">Beispiele</span><span class="sxs-lookup"><span data-stu-id="68f72-222">Examples</span></span>
---|---|---
<span data-ttu-id="68f72-223">Dateierweiterung</span><span class="sxs-lookup"><span data-stu-id="68f72-223">File extension</span></span> | <span data-ttu-id="68f72-224">Alle Dateien mit der Erweiterung, überall auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="68f72-224">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="68f72-225">Datei</span><span class="sxs-lookup"><span data-stu-id="68f72-225">File</span></span> | <span data-ttu-id="68f72-226">Eine bestimmte Datei, die durch den vollständigen Pfad identifiziert wird</span><span class="sxs-lookup"><span data-stu-id="68f72-226">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="68f72-227">Ordner</span><span class="sxs-lookup"><span data-stu-id="68f72-227">Folder</span></span> | <span data-ttu-id="68f72-228">Alle Dateien unter dem angegebenen Ordner (rekursiv)</span><span class="sxs-lookup"><span data-stu-id="68f72-228">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="68f72-229">Prozess</span><span class="sxs-lookup"><span data-stu-id="68f72-229">Process</span></span> | <span data-ttu-id="68f72-230">Ein bestimmter Prozess (entweder durch den vollständigen Pfad oder Dateinamen angegeben) und alle dateien, die von diesem geöffnet werden</span><span class="sxs-lookup"><span data-stu-id="68f72-230">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="68f72-231">Die oben genannten Pfade müssen harte Links und keine symbolischen Verknüpfungen sein, um erfolgreich ausgeschlossen zu werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-231">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="68f72-232">Sie können überprüfen, ob ein Pfad ein symbolischer Link ist, indem Sie `file <path-name>` ausführen.</span><span class="sxs-lookup"><span data-stu-id="68f72-232">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="68f72-233">Datei-, Ordner- und Prozessausschlüsse unterstützen die folgenden Platzhalter:</span><span class="sxs-lookup"><span data-stu-id="68f72-233">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="68f72-234">Platzhalter</span><span class="sxs-lookup"><span data-stu-id="68f72-234">Wildcard</span></span> | <span data-ttu-id="68f72-235">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68f72-235">Description</span></span> | <span data-ttu-id="68f72-236">Beispiel</span><span class="sxs-lookup"><span data-stu-id="68f72-236">Example</span></span> | <span data-ttu-id="68f72-237">Übereinstimmungen</span><span class="sxs-lookup"><span data-stu-id="68f72-237">Matches</span></span> | <span data-ttu-id="68f72-238">Nicht übereinstimmend</span><span class="sxs-lookup"><span data-stu-id="68f72-238">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="68f72-239">Entspricht einer beliebigen Anzahl beliebiger Zeichen, einschließlich keines (beachten Sie, dass dieser Platzhalter nur einen Ordner ersetzt, wenn er innerhalb eines Pfads verwendet wird)</span><span class="sxs-lookup"><span data-stu-id="68f72-239">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="68f72-240">?</span><span class="sxs-lookup"><span data-stu-id="68f72-240">?</span></span> | <span data-ttu-id="68f72-241">Entspricht einem beliebigen einzelnen Zeichen</span><span class="sxs-lookup"><span data-stu-id="68f72-241">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a><span data-ttu-id="68f72-242">Pfadtyp (Datei/Verzeichnis)</span><span class="sxs-lookup"><span data-stu-id="68f72-242">Path type (file / directory)</span></span>

<span data-ttu-id="68f72-243">Gibt an, ob *die path-Eigenschaft* auf eine Datei oder ein Verzeichnis verweist.</span><span class="sxs-lookup"><span data-stu-id="68f72-243">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="68f72-244">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-244">Section</span></span>|<span data-ttu-id="68f72-245">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-245">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-246">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-246">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-247">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-247">**Key**</span></span> | <span data-ttu-id="68f72-248">isDirectory</span><span class="sxs-lookup"><span data-stu-id="68f72-248">isDirectory</span></span> |
| <span data-ttu-id="68f72-249">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-249">**Data type**</span></span> | <span data-ttu-id="68f72-250">Boolesch</span><span class="sxs-lookup"><span data-stu-id="68f72-250">Boolean</span></span> |
| <span data-ttu-id="68f72-251">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-251">**Possible values**</span></span> | <span data-ttu-id="68f72-252">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="68f72-252">false (default)</span></span> <br/> <span data-ttu-id="68f72-253">true</span><span class="sxs-lookup"><span data-stu-id="68f72-253">true</span></span> |
| <span data-ttu-id="68f72-254">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-254">**Comments**</span></span> | <span data-ttu-id="68f72-255">Gilt nur, *$type* *ausgeschlossen IstPath*</span><span class="sxs-lookup"><span data-stu-id="68f72-255">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="68f72-256">Dateierweiterung, die von der Überprüfung ausgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="68f72-256">File extension excluded from the scan</span></span>

<span data-ttu-id="68f72-257">Geben Sie Inhalte an, die von der Dateierweiterung nicht gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-257">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="68f72-258">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-258">Section</span></span>|<span data-ttu-id="68f72-259">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-259">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-260">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-260">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-261">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-261">**Key**</span></span> | <span data-ttu-id="68f72-262">erweiterung</span><span class="sxs-lookup"><span data-stu-id="68f72-262">extension</span></span> |
| <span data-ttu-id="68f72-263">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-263">**Data type**</span></span> | <span data-ttu-id="68f72-264">String</span><span class="sxs-lookup"><span data-stu-id="68f72-264">String</span></span> |
| <span data-ttu-id="68f72-265">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-265">**Possible values**</span></span> | <span data-ttu-id="68f72-266">Gültige Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="68f72-266">valid file extensions</span></span> |
| <span data-ttu-id="68f72-267">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-267">**Comments**</span></span> | <span data-ttu-id="68f72-268">Gilt nur, *$type* *ausgeschlossen istFileExtension*</span><span class="sxs-lookup"><span data-stu-id="68f72-268">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="68f72-269">Prozess, der von der Überprüfung ausgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="68f72-269">Process excluded from the scan</span></span>

<span data-ttu-id="68f72-270">Geben Sie einen Prozess an, für den alle Dateiaktivitäten von der Überprüfung ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-270">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="68f72-271">Der Prozess kann entweder durch seinen Namen (z. B. ) oder den vollständigen `cat` Pfad (z. B. ) angegeben werden. `/bin/cat`</span><span class="sxs-lookup"><span data-stu-id="68f72-271">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="68f72-272">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-272">Section</span></span>|<span data-ttu-id="68f72-273">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-273">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-274">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-274">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-275">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-275">**Key**</span></span> | <span data-ttu-id="68f72-276">name</span><span class="sxs-lookup"><span data-stu-id="68f72-276">name</span></span> |
| <span data-ttu-id="68f72-277">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-277">**Data type**</span></span> | <span data-ttu-id="68f72-278">String</span><span class="sxs-lookup"><span data-stu-id="68f72-278">String</span></span> |
| <span data-ttu-id="68f72-279">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-279">**Possible values**</span></span> | <span data-ttu-id="68f72-280">eine beliebige Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="68f72-280">any string</span></span> |
| <span data-ttu-id="68f72-281">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-281">**Comments**</span></span> | <span data-ttu-id="68f72-282">Gilt nur, *$type* *ausgeschlossen istFileName*</span><span class="sxs-lookup"><span data-stu-id="68f72-282">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="68f72-283">Zulässige Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="68f72-283">Allowed threats</span></span>

<span data-ttu-id="68f72-284">Geben Sie Bedrohungen nach Namen an, die nicht von Defender for Endpoint auf dem Mac blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-284">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="68f72-285">Diese Bedrohungen können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-285">These threats will be allowed to run.</span></span>

|<span data-ttu-id="68f72-286">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-286">Section</span></span>|<span data-ttu-id="68f72-287">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-287">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-288">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-288">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-289">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-289">**Key**</span></span> | <span data-ttu-id="68f72-290">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="68f72-290">allowedThreats</span></span> |
| <span data-ttu-id="68f72-291">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-291">**Data type**</span></span> | <span data-ttu-id="68f72-292">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="68f72-292">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="68f72-293">Unzulässige Bedrohungsaktionen</span><span class="sxs-lookup"><span data-stu-id="68f72-293">Disallowed threat actions</span></span>

<span data-ttu-id="68f72-294">Schränkt die Aktionen ein, die der lokale Benutzer eines Geräts ausführen kann, wenn Bedrohungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-294">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="68f72-295">Die in dieser Liste enthaltenen Aktionen werden nicht auf der Benutzeroberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68f72-295">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="68f72-296">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-296">Section</span></span>|<span data-ttu-id="68f72-297">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-298">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-299">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-299">**Key**</span></span> | <span data-ttu-id="68f72-300">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="68f72-300">disallowedThreatActions</span></span> |
| <span data-ttu-id="68f72-301">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-301">**Data type**</span></span> | <span data-ttu-id="68f72-302">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="68f72-302">Array of strings</span></span> |
| <span data-ttu-id="68f72-303">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-303">**Possible values**</span></span> | <span data-ttu-id="68f72-304">allow (schränkt ein, dass Benutzer Bedrohungen zulassen)</span><span class="sxs-lookup"><span data-stu-id="68f72-304">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="68f72-305">restore (schränkt benutzer das Wiederherstellen von Bedrohungen aus der Quarantäne ein)</span><span class="sxs-lookup"><span data-stu-id="68f72-305">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="68f72-306">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-306">**Comments**</span></span> | <span data-ttu-id="68f72-307">Verfügbar in Microsoft Defender for Endpoint, Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="68f72-307">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="68f72-308">Einstellungen für den Bedrohungstyp</span><span class="sxs-lookup"><span data-stu-id="68f72-308">Threat type settings</span></span>

<span data-ttu-id="68f72-309">Geben Sie an, wie bestimmte Bedrohungstypen von Microsoft Defender for Endpoint unter macOS behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-309">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="68f72-310">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-310">Section</span></span>|<span data-ttu-id="68f72-311">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-311">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-312">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-312">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-313">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-313">**Key**</span></span> | <span data-ttu-id="68f72-314">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="68f72-314">threatTypeSettings</span></span> |
| <span data-ttu-id="68f72-315">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-315">**Data type**</span></span> | <span data-ttu-id="68f72-316">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="68f72-316">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="68f72-317">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-317">**Comments**</span></span> | <span data-ttu-id="68f72-318">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="68f72-318">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="68f72-319">Bedrohungstyp</span><span class="sxs-lookup"><span data-stu-id="68f72-319">Threat type</span></span>

<span data-ttu-id="68f72-320">Geben Sie Bedrohungstypen an.</span><span class="sxs-lookup"><span data-stu-id="68f72-320">Specify threat types.</span></span>

|<span data-ttu-id="68f72-321">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-321">Section</span></span>|<span data-ttu-id="68f72-322">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-322">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-323">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-323">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-324">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-324">**Key**</span></span> | <span data-ttu-id="68f72-325">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="68f72-325">key</span></span> |
| <span data-ttu-id="68f72-326">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-326">**Data type**</span></span> | <span data-ttu-id="68f72-327">String</span><span class="sxs-lookup"><span data-stu-id="68f72-327">String</span></span> |
| <span data-ttu-id="68f72-328">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-328">**Possible values**</span></span> | <span data-ttu-id="68f72-329">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="68f72-329">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="68f72-330">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="68f72-330">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="68f72-331">Zu ergreifende Maßnahme</span><span class="sxs-lookup"><span data-stu-id="68f72-331">Action to take</span></span>

<span data-ttu-id="68f72-332">Geben Sie an, welche Aktion ausgeführt werden soll, wenn eine Bedrohung des im vorherigen Abschnitt angegebenen Typs erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="68f72-332">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="68f72-333">Wählen Sie aus den folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="68f72-333">Choose from the following options:</span></span>

- <span data-ttu-id="68f72-334">**Überwachung:** Ihr Gerät ist nicht vor dieser Art von Bedrohung geschützt, aber ein Eintrag über die Bedrohung wird protokolliert.</span><span class="sxs-lookup"><span data-stu-id="68f72-334">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="68f72-335">**Block**: Ihr Gerät ist vor dieser Art von Bedrohung geschützt, und Sie werden über die Benutzeroberfläche und die Sicherheitskonsole benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="68f72-335">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="68f72-336">**Aus**: Ihr Gerät ist nicht vor dieser Art von Bedrohung geschützt, und es wird nichts protokolliert.</span><span class="sxs-lookup"><span data-stu-id="68f72-336">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="68f72-337">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-337">Section</span></span>|<span data-ttu-id="68f72-338">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-338">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-339">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-339">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-340">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-340">**Key**</span></span> | <span data-ttu-id="68f72-341">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-341">value</span></span> |
| <span data-ttu-id="68f72-342">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-342">**Data type**</span></span> | <span data-ttu-id="68f72-343">String</span><span class="sxs-lookup"><span data-stu-id="68f72-343">String</span></span> |
| <span data-ttu-id="68f72-344">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-344">**Possible values**</span></span> | <span data-ttu-id="68f72-345">Überwachung (Standard)</span><span class="sxs-lookup"><span data-stu-id="68f72-345">audit (default)</span></span> <br/> <span data-ttu-id="68f72-346">block</span><span class="sxs-lookup"><span data-stu-id="68f72-346">block</span></span> <br/> <span data-ttu-id="68f72-347">off</span><span class="sxs-lookup"><span data-stu-id="68f72-347">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="68f72-348">Richtlinie zum Zusammenführen von Bedrohungstypeinstellungen</span><span class="sxs-lookup"><span data-stu-id="68f72-348">Threat type settings merge policy</span></span>

<span data-ttu-id="68f72-349">Geben Sie die Seriendruckrichtlinie für Bedrohungstypeinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="68f72-349">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="68f72-350">Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Einstellungen ( ) oder nur vom Administrator definierten Einstellungen `merge` ( ) `admin_only` sein.</span><span class="sxs-lookup"><span data-stu-id="68f72-350">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="68f72-351">Diese Einstellung kann verwendet werden, um lokale Benutzer an der Definition eigener Einstellungen für verschiedene Bedrohungstypen zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="68f72-351">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="68f72-352">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-352">Section</span></span>|<span data-ttu-id="68f72-353">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-353">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-354">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-354">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-355">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-355">**Key**</span></span> | <span data-ttu-id="68f72-356">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="68f72-356">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="68f72-357">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-357">**Data type**</span></span> | <span data-ttu-id="68f72-358">String</span><span class="sxs-lookup"><span data-stu-id="68f72-358">String</span></span> |
| <span data-ttu-id="68f72-359">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-359">**Possible values**</span></span> | <span data-ttu-id="68f72-360">merge (Standard)</span><span class="sxs-lookup"><span data-stu-id="68f72-360">merge (default)</span></span> <br/> <span data-ttu-id="68f72-361">admin_only</span><span class="sxs-lookup"><span data-stu-id="68f72-361">admin_only</span></span> |
| <span data-ttu-id="68f72-362">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-362">**Comments**</span></span> | <span data-ttu-id="68f72-363">Verfügbar in Microsoft Defender for Endpoint, Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="68f72-363">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="68f72-364">Aufbewahrung des Antivirusscanverlaufs (in Tagen)</span><span class="sxs-lookup"><span data-stu-id="68f72-364">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="68f72-365">Geben Sie die Anzahl der Tage an, die Ergebnisse im Scanverlauf auf dem Gerät aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-365">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="68f72-366">Alte Scanergebnisse werden aus dem Verlauf entfernt.</span><span class="sxs-lookup"><span data-stu-id="68f72-366">Old scan results are removed from the history.</span></span> <span data-ttu-id="68f72-367">Alte isolierte Dateien, die ebenfalls vom Datenträger entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="68f72-367">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="68f72-368">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-368">Section</span></span>|<span data-ttu-id="68f72-369">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-369">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-370">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-370">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-371">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-371">**Key**</span></span> | <span data-ttu-id="68f72-372">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="68f72-372">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="68f72-373">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-373">**Data type**</span></span> | <span data-ttu-id="68f72-374">String</span><span class="sxs-lookup"><span data-stu-id="68f72-374">String</span></span> |
| <span data-ttu-id="68f72-375">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-375">**Possible values**</span></span> | <span data-ttu-id="68f72-376">90 (Standard).</span><span class="sxs-lookup"><span data-stu-id="68f72-376">90 (default).</span></span> <span data-ttu-id="68f72-377">Zulässige Werte liegen zwischen 1 Tag und 180 Tagen.</span><span class="sxs-lookup"><span data-stu-id="68f72-377">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="68f72-378">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-378">**Comments**</span></span> | <span data-ttu-id="68f72-379">Verfügbar in Microsoft Defender for Endpoint, Version 101.07.23 oder höher.</span><span class="sxs-lookup"><span data-stu-id="68f72-379">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="68f72-380">Maximale Anzahl von Elementen im Antivirusscanverlauf</span><span class="sxs-lookup"><span data-stu-id="68f72-380">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="68f72-381">Geben Sie die maximale Anzahl von Einträgen an, die im Scanverlauf bleiben sollen.</span><span class="sxs-lookup"><span data-stu-id="68f72-381">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="68f72-382">Zu den Einträgen gehören alle in der Vergangenheit durchgeführten Bedarfsscans und alle Antivirenerkennungen.</span><span class="sxs-lookup"><span data-stu-id="68f72-382">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="68f72-383">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-383">Section</span></span>|<span data-ttu-id="68f72-384">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-384">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-385">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-385">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-386">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-386">**Key**</span></span> | <span data-ttu-id="68f72-387">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="68f72-387">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="68f72-388">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-388">**Data type**</span></span> | <span data-ttu-id="68f72-389">String</span><span class="sxs-lookup"><span data-stu-id="68f72-389">String</span></span> |
| <span data-ttu-id="68f72-390">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-390">**Possible values**</span></span> | <span data-ttu-id="68f72-391">10000 (Standard).</span><span class="sxs-lookup"><span data-stu-id="68f72-391">10000 (default).</span></span> <span data-ttu-id="68f72-392">Zulässige Werte liegen zwischen 5.000 und 15.000 Elementen.</span><span class="sxs-lookup"><span data-stu-id="68f72-392">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="68f72-393">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-393">**Comments**</span></span> | <span data-ttu-id="68f72-394">Verfügbar in Microsoft Defender for Endpoint, Version 101.07.23 oder höher.</span><span class="sxs-lookup"><span data-stu-id="68f72-394">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="68f72-395">Von der Cloud übermittelte Schutzeinstellungen</span><span class="sxs-lookup"><span data-stu-id="68f72-395">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="68f72-396">Konfigurieren Sie die cloudgesteuerten Schutzfunktionen von Microsoft Defender for Endpoint unter macOS.</span><span class="sxs-lookup"><span data-stu-id="68f72-396">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="68f72-397">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-397">Section</span></span>|<span data-ttu-id="68f72-398">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-399">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-400">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-400">**Key**</span></span> | <span data-ttu-id="68f72-401">cloudService</span><span class="sxs-lookup"><span data-stu-id="68f72-401">cloudService</span></span> |
| <span data-ttu-id="68f72-402">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-402">**Data type**</span></span> | <span data-ttu-id="68f72-403">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="68f72-403">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="68f72-404">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-404">**Comments**</span></span> | <span data-ttu-id="68f72-405">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="68f72-405">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="68f72-406">Aktivieren/Deaktivieren des in der Cloud übermittelten Schutzes</span><span class="sxs-lookup"><span data-stu-id="68f72-406">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="68f72-407">Geben Sie an, ob der in der Cloud zugestellte Schutz auf dem Gerät aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="68f72-407">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="68f72-408">Um die Sicherheit Ihrer Dienste zu verbessern, wird empfohlen, dieses Feature aktiviert zu halten.</span><span class="sxs-lookup"><span data-stu-id="68f72-408">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="68f72-409">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-409">Section</span></span>|<span data-ttu-id="68f72-410">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-410">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-411">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-411">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-412">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-412">**Key**</span></span> | <span data-ttu-id="68f72-413">aktiviert</span><span class="sxs-lookup"><span data-stu-id="68f72-413">enabled</span></span> |
| <span data-ttu-id="68f72-414">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-414">**Data type**</span></span> | <span data-ttu-id="68f72-415">Boolesch</span><span class="sxs-lookup"><span data-stu-id="68f72-415">Boolean</span></span> |
| <span data-ttu-id="68f72-416">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-416">**Possible values**</span></span> | <span data-ttu-id="68f72-417">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="68f72-417">true (default)</span></span> <br/> <span data-ttu-id="68f72-418">false</span><span class="sxs-lookup"><span data-stu-id="68f72-418">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="68f72-419">Diagnosesammlungsebene</span><span class="sxs-lookup"><span data-stu-id="68f72-419">Diagnostic collection level</span></span>

<span data-ttu-id="68f72-420">Diagnosedaten werden verwendet, um Microsoft Defender for Endpoint sicher und auf dem neuesten Stand zu halten, Probleme zu erkennen, zu diagnostizieren und zu beheben sowie Produktverbesserungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="68f72-420">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="68f72-421">Diese Einstellung bestimmt die Diagnosestufe, die von Microsoft Defender for Endpoint an Microsoft gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="68f72-421">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="68f72-422">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-422">Section</span></span>|<span data-ttu-id="68f72-423">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-424">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-424">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-425">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-425">**Key**</span></span> | <span data-ttu-id="68f72-426">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="68f72-426">diagnosticLevel</span></span> |
| <span data-ttu-id="68f72-427">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-427">**Data type**</span></span> | <span data-ttu-id="68f72-428">String</span><span class="sxs-lookup"><span data-stu-id="68f72-428">String</span></span> |
| <span data-ttu-id="68f72-429">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-429">**Possible values**</span></span> | <span data-ttu-id="68f72-430">optional (Standard)</span><span class="sxs-lookup"><span data-stu-id="68f72-430">optional (default)</span></span> <br/> <span data-ttu-id="68f72-431">erforderlich</span><span class="sxs-lookup"><span data-stu-id="68f72-431">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="68f72-432">Aktivieren/Deaktivieren automatischer Beispielübermittlungen</span><span class="sxs-lookup"><span data-stu-id="68f72-432">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="68f72-433">Bestimmt, ob verdächtige Beispiele (die wahrscheinlich Bedrohungen enthalten) an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-433">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="68f72-434">Sie werden aufgefordert, wenn die übermittelte Datei wahrscheinlich personenbezogene Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="68f72-434">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="68f72-435">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-435">Section</span></span>|<span data-ttu-id="68f72-436">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-436">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-437">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-437">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-438">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-438">**Key**</span></span> | <span data-ttu-id="68f72-439">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="68f72-439">automaticSampleSubmission</span></span> |
| <span data-ttu-id="68f72-440">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-440">**Data type**</span></span> | <span data-ttu-id="68f72-441">Boolesch</span><span class="sxs-lookup"><span data-stu-id="68f72-441">Boolean</span></span> |
| <span data-ttu-id="68f72-442">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-442">**Possible values**</span></span> | <span data-ttu-id="68f72-443">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="68f72-443">true (default)</span></span> <br/> <span data-ttu-id="68f72-444">false</span><span class="sxs-lookup"><span data-stu-id="68f72-444">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="68f72-445">Aktivieren/Deaktivieren automatischer Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="68f72-445">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="68f72-446">Bestimmt, ob Sicherheitsintelligenzupdates automatisch installiert werden:</span><span class="sxs-lookup"><span data-stu-id="68f72-446">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="68f72-447">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-447">Section</span></span>|<span data-ttu-id="68f72-448">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-448">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-449">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-449">**Key**</span></span> | <span data-ttu-id="68f72-450">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="68f72-450">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="68f72-451">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-451">**Data type**</span></span> | <span data-ttu-id="68f72-452">Boolesch</span><span class="sxs-lookup"><span data-stu-id="68f72-452">Boolean</span></span> |
| <span data-ttu-id="68f72-453">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-453">**Possible values**</span></span> | <span data-ttu-id="68f72-454">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="68f72-454">true (default)</span></span> <br/> <span data-ttu-id="68f72-455">false</span><span class="sxs-lookup"><span data-stu-id="68f72-455">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="68f72-456">Benutzeroberflächeneinstellungen</span><span class="sxs-lookup"><span data-stu-id="68f72-456">User interface preferences</span></span>

<span data-ttu-id="68f72-457">Verwalten Sie die Einstellungen für die Benutzeroberfläche von Microsoft Defender for Endpoint unter macOS.</span><span class="sxs-lookup"><span data-stu-id="68f72-457">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="68f72-458">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-458">Section</span></span>|<span data-ttu-id="68f72-459">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-459">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-460">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-460">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-461">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-461">**Key**</span></span> | <span data-ttu-id="68f72-462">userInterface</span><span class="sxs-lookup"><span data-stu-id="68f72-462">userInterface</span></span> |
| <span data-ttu-id="68f72-463">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-463">**Data type**</span></span> | <span data-ttu-id="68f72-464">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="68f72-464">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="68f72-465">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-465">**Comments**</span></span> | <span data-ttu-id="68f72-466">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="68f72-466">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="68f72-467">Symbol für Das Menü "Status anzeigen/ausblenden"</span><span class="sxs-lookup"><span data-stu-id="68f72-467">Show / hide status menu icon</span></span>

<span data-ttu-id="68f72-468">Geben Sie an, ob das Statusmenüsymbol in der oberen rechten Ecke des Bildschirms ein- oder ausgeblendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="68f72-468">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="68f72-469">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-469">Section</span></span>|<span data-ttu-id="68f72-470">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-470">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-471">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-471">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-472">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-472">**Key**</span></span> | <span data-ttu-id="68f72-473">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="68f72-473">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="68f72-474">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-474">**Data type**</span></span> | <span data-ttu-id="68f72-475">Boolesch</span><span class="sxs-lookup"><span data-stu-id="68f72-475">Boolean</span></span> |
| <span data-ttu-id="68f72-476">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-476">**Possible values**</span></span> | <span data-ttu-id="68f72-477">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="68f72-477">false (default)</span></span> <br/> <span data-ttu-id="68f72-478">true</span><span class="sxs-lookup"><span data-stu-id="68f72-478">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="68f72-479">Ein-/Ausblenden der Option zum Senden von Feedback</span><span class="sxs-lookup"><span data-stu-id="68f72-479">Show / hide option to send feedback</span></span>

<span data-ttu-id="68f72-480">Geben Sie an, ob Benutzer Feedback an Microsoft senden können, indem Sie zu `Help`  >  `Send Feedback` gehen.</span><span class="sxs-lookup"><span data-stu-id="68f72-480">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="68f72-481">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-481">Section</span></span>|<span data-ttu-id="68f72-482">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-482">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-483">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-483">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-484">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-484">**Key**</span></span> | <span data-ttu-id="68f72-485">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="68f72-485">userInitiatedFeedback</span></span> |
| <span data-ttu-id="68f72-486">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-486">**Data type**</span></span> | <span data-ttu-id="68f72-487">String</span><span class="sxs-lookup"><span data-stu-id="68f72-487">String</span></span> |
| <span data-ttu-id="68f72-488">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-488">**Possible values**</span></span> | <span data-ttu-id="68f72-489">aktiviert (Standard)</span><span class="sxs-lookup"><span data-stu-id="68f72-489">enabled (default)</span></span> <br/> <span data-ttu-id="68f72-490">deaktiviert</span><span class="sxs-lookup"><span data-stu-id="68f72-490">disabled</span></span> |
| <span data-ttu-id="68f72-491">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-491">**Comments**</span></span> | <span data-ttu-id="68f72-492">Verfügbar in Microsoft Defender for Endpoint, Version 101.19.61 oder höher.</span><span class="sxs-lookup"><span data-stu-id="68f72-492">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="68f72-493">Einstellungen für endpunkterkennung und -reaktion</span><span class="sxs-lookup"><span data-stu-id="68f72-493">Endpoint detection and response preferences</span></span>

<span data-ttu-id="68f72-494">Verwalten Sie die Einstellungen der EDR (EDR) von Microsoft Defender for Endpoint unter macOS.</span><span class="sxs-lookup"><span data-stu-id="68f72-494">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="68f72-495">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-495">Section</span></span>|<span data-ttu-id="68f72-496">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-496">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-497">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-497">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-498">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-498">**Key**</span></span> | <span data-ttu-id="68f72-499">edr</span><span class="sxs-lookup"><span data-stu-id="68f72-499">edr</span></span> |
| <span data-ttu-id="68f72-500">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-500">**Data type**</span></span> | <span data-ttu-id="68f72-501">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="68f72-501">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="68f72-502">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-502">**Comments**</span></span> | <span data-ttu-id="68f72-503">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="68f72-503">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="68f72-504">Gerätetags</span><span class="sxs-lookup"><span data-stu-id="68f72-504">Device tags</span></span>

<span data-ttu-id="68f72-505">Geben Sie einen Tagnamen und dessen Wert an.</span><span class="sxs-lookup"><span data-stu-id="68f72-505">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="68f72-506">Das GROUP-Tag tagt das Gerät mit dem angegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="68f72-506">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="68f72-507">Das Tag wird im Portal unter der Geräteseite angezeigt und kann zum Filtern und Gruppieren von Geräten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-507">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="68f72-508">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-508">Section</span></span>|<span data-ttu-id="68f72-509">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-509">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-510">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-510">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-511">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-511">**Key**</span></span> | <span data-ttu-id="68f72-512">tags</span><span class="sxs-lookup"><span data-stu-id="68f72-512">tags</span></span> |
| <span data-ttu-id="68f72-513">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-513">**Data type**</span></span> | <span data-ttu-id="68f72-514">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="68f72-514">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="68f72-515">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="68f72-515">**Comments**</span></span> | <span data-ttu-id="68f72-516">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="68f72-516">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="68f72-517">Tagtyp</span><span class="sxs-lookup"><span data-stu-id="68f72-517">Type of tag</span></span>

<span data-ttu-id="68f72-518">Gibt den Typ des Tags an.</span><span class="sxs-lookup"><span data-stu-id="68f72-518">Specifies the type of tag</span></span>

|<span data-ttu-id="68f72-519">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-519">Section</span></span>|<span data-ttu-id="68f72-520">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-520">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-521">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-521">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-522">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-522">**Key**</span></span> | <span data-ttu-id="68f72-523">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="68f72-523">key</span></span> |
| <span data-ttu-id="68f72-524">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-524">**Data type**</span></span> | <span data-ttu-id="68f72-525">String</span><span class="sxs-lookup"><span data-stu-id="68f72-525">String</span></span> |
| <span data-ttu-id="68f72-526">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-526">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="68f72-527">Wert des Tags</span><span class="sxs-lookup"><span data-stu-id="68f72-527">Value of tag</span></span>

<span data-ttu-id="68f72-528">Gibt den Wert des Tags an.</span><span class="sxs-lookup"><span data-stu-id="68f72-528">Specifies the value of tag</span></span>

|<span data-ttu-id="68f72-529">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68f72-529">Section</span></span>|<span data-ttu-id="68f72-530">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-530">Value</span></span>|
|:---|:---|
| <span data-ttu-id="68f72-531">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="68f72-531">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="68f72-532">**Key**</span><span class="sxs-lookup"><span data-stu-id="68f72-532">**Key**</span></span> | <span data-ttu-id="68f72-533">Wert</span><span class="sxs-lookup"><span data-stu-id="68f72-533">value</span></span> |
| <span data-ttu-id="68f72-534">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="68f72-534">**Data type**</span></span> | <span data-ttu-id="68f72-535">String</span><span class="sxs-lookup"><span data-stu-id="68f72-535">String</span></span> |
| <span data-ttu-id="68f72-536">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="68f72-536">**Possible values**</span></span> | <span data-ttu-id="68f72-537">eine beliebige Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="68f72-537">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="68f72-538">Pro Tagtyp kann nur ein Wert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-538">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="68f72-539">Der Typ von Tags ist eindeutig und sollte nicht im gleichen Konfigurationsprofil wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="68f72-539">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="68f72-540">Empfohlenes Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="68f72-540">Recommended configuration profile</span></span>

<span data-ttu-id="68f72-541">Für die ersten Schritte empfehlen wir die folgende Konfiguration für Ihr Unternehmen, um alle Von Microsoft Defender for Endpoint-Funktionen zur Nutzung zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="68f72-541">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="68f72-542">Das folgende Konfigurationsprofil (oder im Fall von JAMF eine Eigenschaftenliste, die in das Konfigurationsprofil für benutzerdefinierte Einstellungen hochgeladen werden könnte) wird verwendet:</span><span class="sxs-lookup"><span data-stu-id="68f72-542">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="68f72-543">Aktivieren des Echtzeitschutzes (Real-Time Protection, RTP)</span><span class="sxs-lookup"><span data-stu-id="68f72-543">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="68f72-544">Geben Sie an, wie die folgenden Bedrohungstypen behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="68f72-544">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="68f72-545">**Potenziell unerwünschte Anwendungen (PUA)** werden blockiert</span><span class="sxs-lookup"><span data-stu-id="68f72-545">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="68f72-546">**Archivangriffe** (Datei mit hoher Komprimierungsrate) werden bei Microsoft Defender für Endpunktprotokolle überwacht.</span><span class="sxs-lookup"><span data-stu-id="68f72-546">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="68f72-547">Aktivieren automatischer Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="68f72-547">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="68f72-548">Aus der Cloud bereitgestellten Schutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="68f72-548">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="68f72-549">Aktivieren der automatischen Beispielübermittlung</span><span class="sxs-lookup"><span data-stu-id="68f72-549">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="68f72-550">Eigenschaftenliste für das JAMF-Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="68f72-550">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="68f72-551">Intune-Profil</span><span class="sxs-lookup"><span data-stu-id="68f72-551">Intune profile</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="68f72-552">Beispiel für ein vollständiges Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="68f72-552">Full configuration profile example</span></span>

<span data-ttu-id="68f72-553">Die folgenden Vorlagen enthalten Einträge für alle in diesem Dokument beschriebenen Einstellungen und können für erweiterte Szenarien verwendet werden, in denen Sie mehr Kontrolle über Microsoft Defender for Endpoint unter macOS wünschen.</span><span class="sxs-lookup"><span data-stu-id="68f72-553">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="68f72-554">Eigenschaftenliste für das JAMF-Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="68f72-554">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="68f72-555">Intune-Profil</span><span class="sxs-lookup"><span data-stu-id="68f72-555">Intune profile</span></span>

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a><span data-ttu-id="68f72-556">Eigenschaftenlistenüberprüfung</span><span class="sxs-lookup"><span data-stu-id="68f72-556">Property list validation</span></span>

<span data-ttu-id="68f72-557">Die Eigenschaftenliste muss eine gültige *.plist-Datei* sein.</span><span class="sxs-lookup"><span data-stu-id="68f72-557">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="68f72-558">Dies kann durch Ausführen von:</span><span class="sxs-lookup"><span data-stu-id="68f72-558">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="68f72-559">Wenn die Datei wohlgeformt ist, wird mit dem obigen Befehl der `OK` Exitcode ausgegeben und `0` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="68f72-559">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="68f72-560">Andernfalls wird ein Fehler angezeigt, der das Problem beschreibt, und der Befehl gibt den Exitcode von `1` zurück.</span><span class="sxs-lookup"><span data-stu-id="68f72-560">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="68f72-561">Konfigurationsprofilbereitstellung</span><span class="sxs-lookup"><span data-stu-id="68f72-561">Configuration profile deployment</span></span>

<span data-ttu-id="68f72-562">Nachdem Sie das Konfigurationsprofil für Ihr Unternehmen erstellt haben, können Sie es über die Verwaltungskonsole bereitstellen, die Ihr Unternehmen verwendet.</span><span class="sxs-lookup"><span data-stu-id="68f72-562">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="68f72-563">In den folgenden Abschnitten finden Sie Anweisungen zum Bereitstellen dieses Profils mithilfe von JAMF und Intune.</span><span class="sxs-lookup"><span data-stu-id="68f72-563">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="68f72-564">JAMF-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="68f72-564">JAMF deployment</span></span>

<span data-ttu-id="68f72-565">Öffnen Sie in der JAMF-Konsole  >  **Computerkonfigurationsprofile,** navigieren Sie zu dem Konfigurationsprofil, das Sie verwenden möchten, und wählen Sie dann Benutzerdefinierte Einstellungen .</span><span class="sxs-lookup"><span data-stu-id="68f72-565">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="68f72-566">Erstellen Sie einen Eintrag `com.microsoft.wdav` mit als Einstellungsdomäne, und laden Sie die zuvor produzierte *.plist* hoch.</span><span class="sxs-lookup"><span data-stu-id="68f72-566">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="68f72-567">Sie müssen die richtige Einstellungsdomäne eingeben ( ); andernfalls werden die Einstellungen von `com.microsoft.wdav` Microsoft Defender for Endpoint nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="68f72-567">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="68f72-568">Intune-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="68f72-568">Intune deployment</span></span>

1. <span data-ttu-id="68f72-569">Öffnen **Sie**  >  **Gerätekonfiguration verwalten**.</span><span class="sxs-lookup"><span data-stu-id="68f72-569">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="68f72-570">Wählen **Sie Profil** erstellen von  >    >  **Profilen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="68f72-570">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="68f72-571">Wählen Sie einen Namen für das Profil aus.</span><span class="sxs-lookup"><span data-stu-id="68f72-571">Choose a name for the profile.</span></span> <span data-ttu-id="68f72-572">Ändern **sie Platform=macOS** in **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="68f72-572">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="68f72-573">Wählen Sie Konfigurieren aus.</span><span class="sxs-lookup"><span data-stu-id="68f72-573">Select Configure.</span></span>

3. <span data-ttu-id="68f72-574">Speichern Sie die .plist, die zuvor als erstellt `com.microsoft.wdav.xml` wurde.</span><span class="sxs-lookup"><span data-stu-id="68f72-574">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="68f72-575">Geben `com.microsoft.wdav` Sie als **benutzerdefinierter Konfigurationsprofilname ein.**</span><span class="sxs-lookup"><span data-stu-id="68f72-575">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="68f72-576">Öffnen Sie das Konfigurationsprofil, und laden Sie die Datei `com.microsoft.wdav.xml` hoch.</span><span class="sxs-lookup"><span data-stu-id="68f72-576">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="68f72-577">(Diese Datei wurde in Schritt 3 erstellt.)</span><span class="sxs-lookup"><span data-stu-id="68f72-577">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="68f72-578">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="68f72-578">Select **OK**.</span></span>

7. <span data-ttu-id="68f72-579">Wählen **Sie**  >  **Zuordnungen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="68f72-579">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="68f72-580">Wählen Sie **auf** der Registerkarte Include die Option **Allen Benutzern & Alle Geräte zuweisen aus.**</span><span class="sxs-lookup"><span data-stu-id="68f72-580">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="68f72-581">Sie müssen den richtigen namen des benutzerdefinierten Konfigurationsprofils eingeben. Andernfalls werden diese Einstellungen von Microsoft Defender for Endpoint nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="68f72-581">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="68f72-582">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="68f72-582">Resources</span></span>

- [<span data-ttu-id="68f72-583">Konfigurationsprofilreferenz (Apple-Entwicklerdokumentationen)</span><span class="sxs-lookup"><span data-stu-id="68f72-583">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
