---
title: Festlegen von Einstellungen für Microsoft Defender for Endpoint für Mac
description: Konfigurieren von Microsoft Defender für Endpoint für Mac in Unternehmensorganisationen.
keywords: microsoft, defender, atp, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: d2bea469031e2c5932e859fbad7d442ebe4d34ed
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860923"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="f2a89-104">Festlegen von Einstellungen für Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="f2a89-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f2a89-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f2a89-105">**Applies to:**</span></span>

- [<span data-ttu-id="f2a89-106">Microsoft Defender für Endpunkt unter Mac OS</span><span class="sxs-lookup"><span data-stu-id="f2a89-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="f2a89-107">Dieser Artikel enthält Anweisungen zum Festlegen von Einstellungen für Microsoft Defender for Endpoint auf macOS in Unternehmensorganisationen.</span><span class="sxs-lookup"><span data-stu-id="f2a89-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="f2a89-108">Informationen zum Konfigurieren von Microsoft Defender for Endpoint unter macOS über die Befehlszeilenschnittstelle finden Sie unter [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="f2a89-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="f2a89-109">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="f2a89-109">Summary</span></span>

<span data-ttu-id="f2a89-110">In Unternehmensorganisationen kann Microsoft Defender for Endpoint unter macOS über ein Konfigurationsprofil verwaltet werden, das mithilfe eines von mehreren Verwaltungstools bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f2a89-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="f2a89-111">Einstellungen, die vom Sicherheitsbetriebsteam verwaltet werden, haben Vorrang vor Einstellungen, die lokal auf dem Gerät festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="f2a89-112">Das Ändern der Einstellungen, die über das Konfigurationsprofil festgelegt werden, erfordert eskalierte Berechtigungen und ist für Benutzer ohne Administratorberechtigungen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f2a89-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="f2a89-113">Dieser Artikel beschreibt die Struktur des Konfigurationsprofils, enthält ein empfohlenes Profil, das Sie für die ersten Schritte verwenden können, und enthält Anweisungen zum Bereitstellen des Profils.</span><span class="sxs-lookup"><span data-stu-id="f2a89-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="f2a89-114">Konfigurationsprofilstruktur</span><span class="sxs-lookup"><span data-stu-id="f2a89-114">Configuration profile structure</span></span>

<span data-ttu-id="f2a89-115">Das Konfigurationsprofil ist eine *.plist-Datei,* die aus Einträgen besteht, die durch einen Schlüssel identifiziert werden (der den Namen der Einstellung angibt), gefolgt von einem Wert, der von der Art der Einstellung abhängt.</span><span class="sxs-lookup"><span data-stu-id="f2a89-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="f2a89-116">Werte können entweder einfach (z. B. ein numerischer Wert) oder komplex sein, z. B. eine geschachtelte Liste von Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="f2a89-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="f2a89-117">Das Layout des Konfigurationsprofils hängt von der verwendeten Verwaltungskonsole ab.</span><span class="sxs-lookup"><span data-stu-id="f2a89-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="f2a89-118">Die folgenden Abschnitte enthalten Beispiele für Konfigurationsprofile für JAMF und Intune.</span><span class="sxs-lookup"><span data-stu-id="f2a89-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="f2a89-119">Die oberste Ebene des Konfigurationsprofils enthält produktweite Einstellungen und Einträge für Unterbereiche von Microsoft Defender for Endpoint, die in den nächsten Abschnitten ausführlicher erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="f2a89-120">Einstellungen des Antivirusmoduls</span><span class="sxs-lookup"><span data-stu-id="f2a89-120">Antivirus engine preferences</span></span>

<span data-ttu-id="f2a89-121">Der *Abschnitt antivirusEngine* des Konfigurationsprofils wird verwendet, um die Einstellungen der Antiviruskomponente von Microsoft Defender for Endpoint zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f2a89-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="f2a89-122">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-122">Section</span></span>|<span data-ttu-id="f2a89-123">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-124">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-125">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-125">**Key**</span></span> | <span data-ttu-id="f2a89-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="f2a89-126">antivirusEngine</span></span> |
| <span data-ttu-id="f2a89-127">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-127">**Data type**</span></span> | <span data-ttu-id="f2a89-128">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="f2a89-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="f2a89-129">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-129">**Comments**</span></span> | <span data-ttu-id="f2a89-130">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="f2a89-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="f2a89-131">Aktivieren/Deaktivieren des Echtzeitschutzes</span><span class="sxs-lookup"><span data-stu-id="f2a89-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="f2a89-132">Geben Sie an, ob der Echtzeitschutz aktiviert werden soll, der Dateien beim Zugriff überprüft.</span><span class="sxs-lookup"><span data-stu-id="f2a89-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="f2a89-133">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-133">Section</span></span>|<span data-ttu-id="f2a89-134">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-135">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-136">**Key**</span></span> | <span data-ttu-id="f2a89-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="f2a89-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="f2a89-138">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-138">**Data type**</span></span> | <span data-ttu-id="f2a89-139">Boolesch</span><span class="sxs-lookup"><span data-stu-id="f2a89-139">Boolean</span></span> |
| <span data-ttu-id="f2a89-140">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-140">**Possible values**</span></span> | <span data-ttu-id="f2a89-141">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="f2a89-141">true (default)</span></span> <br/> <span data-ttu-id="f2a89-142">false</span><span class="sxs-lookup"><span data-stu-id="f2a89-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="f2a89-143">Aktivieren/Deaktivieren des passiven Modus</span><span class="sxs-lookup"><span data-stu-id="f2a89-143">Enable / disable passive mode</span></span>

<span data-ttu-id="f2a89-144">Geben Sie an, ob das Antivirenmodul im passiven Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f2a89-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="f2a89-145">Der passive Modus hat die folgenden Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="f2a89-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="f2a89-146">Echtzeitschutz ist deaktiviert</span><span class="sxs-lookup"><span data-stu-id="f2a89-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="f2a89-147">Die Überprüfung bei Bedarf ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f2a89-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="f2a89-148">Automatische Bedrohungsbehebung ist deaktiviert</span><span class="sxs-lookup"><span data-stu-id="f2a89-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="f2a89-149">Sicherheitsintelligenzupdates sind aktiviert</span><span class="sxs-lookup"><span data-stu-id="f2a89-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="f2a89-150">Statusmenüsymbol ist ausgeblendet</span><span class="sxs-lookup"><span data-stu-id="f2a89-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="f2a89-151">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-151">Section</span></span>|<span data-ttu-id="f2a89-152">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-153">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-154">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-154">**Key**</span></span> | <span data-ttu-id="f2a89-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="f2a89-155">passiveMode</span></span> |
| <span data-ttu-id="f2a89-156">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-156">**Data type**</span></span> | <span data-ttu-id="f2a89-157">Boolesch</span><span class="sxs-lookup"><span data-stu-id="f2a89-157">Boolean</span></span> |
| <span data-ttu-id="f2a89-158">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-158">**Possible values**</span></span> | <span data-ttu-id="f2a89-159">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="f2a89-159">false (default)</span></span> <br/> <span data-ttu-id="f2a89-160">true</span><span class="sxs-lookup"><span data-stu-id="f2a89-160">true</span></span> |
| <span data-ttu-id="f2a89-161">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-161">**Comments**</span></span> | <span data-ttu-id="f2a89-162">Verfügbar in Microsoft Defender for Endpoint, Version 100.67.60 oder höher.</span><span class="sxs-lookup"><span data-stu-id="f2a89-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="f2a89-163">Ausschlusszusammenführungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="f2a89-163">Exclusion merge policy</span></span>

<span data-ttu-id="f2a89-164">Geben Sie die Seriendruckrichtlinie für Ausschlüsse an.</span><span class="sxs-lookup"><span data-stu-id="f2a89-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="f2a89-165">Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Ausschlüssen ( ) oder nur vom Administrator definierten `merge` Ausschlüssen ( `admin_only` ) sein.</span><span class="sxs-lookup"><span data-stu-id="f2a89-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="f2a89-166">Diese Einstellung kann verwendet werden, um lokale Benutzer an der Definition eigener Ausschlüsse zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="f2a89-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="f2a89-167">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-167">Section</span></span>|<span data-ttu-id="f2a89-168">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-169">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-170">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-170">**Key**</span></span> | <span data-ttu-id="f2a89-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="f2a89-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="f2a89-172">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-172">**Data type**</span></span> | <span data-ttu-id="f2a89-173">String</span><span class="sxs-lookup"><span data-stu-id="f2a89-173">String</span></span> |
| <span data-ttu-id="f2a89-174">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-174">**Possible values**</span></span> | <span data-ttu-id="f2a89-175">merge (Standard)</span><span class="sxs-lookup"><span data-stu-id="f2a89-175">merge (default)</span></span> <br/> <span data-ttu-id="f2a89-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="f2a89-176">admin_only</span></span> |
| <span data-ttu-id="f2a89-177">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-177">**Comments**</span></span> | <span data-ttu-id="f2a89-178">Verfügbar in Microsoft Defender for Endpoint, Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="f2a89-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="f2a89-179">Scannen von Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="f2a89-179">Scan exclusions</span></span>

<span data-ttu-id="f2a89-180">Geben Sie Entitäten an, die von der Gescannten ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="f2a89-181">Ausschlüsse können durch vollständige Pfade, Erweiterungen oder Dateinamen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|<span data-ttu-id="f2a89-182">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-182">Section</span></span>|<span data-ttu-id="f2a89-183">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-183">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-184">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-184">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-185">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-185">**Key**</span></span> | <span data-ttu-id="f2a89-186">Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f2a89-186">exclusions</span></span> |
| <span data-ttu-id="f2a89-187">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-187">**Data type**</span></span> | <span data-ttu-id="f2a89-188">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="f2a89-188">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="f2a89-189">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-189">**Comments**</span></span> | <span data-ttu-id="f2a89-190">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="f2a89-190">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="f2a89-191">Art des Ausschlusses</span><span class="sxs-lookup"><span data-stu-id="f2a89-191">Type of exclusion</span></span>

<span data-ttu-id="f2a89-192">Geben Sie Inhalte an, die vom Typ ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-192">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="f2a89-193">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-193">Section</span></span>|<span data-ttu-id="f2a89-194">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-194">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-195">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-195">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-196">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-196">**Key**</span></span> | <span data-ttu-id="f2a89-197">$type</span><span class="sxs-lookup"><span data-stu-id="f2a89-197">$type</span></span> |
| <span data-ttu-id="f2a89-198">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-198">**Data type**</span></span> | <span data-ttu-id="f2a89-199">String</span><span class="sxs-lookup"><span data-stu-id="f2a89-199">String</span></span> |
| <span data-ttu-id="f2a89-200">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-200">**Possible values**</span></span> | <span data-ttu-id="f2a89-201">excludedPath</span><span class="sxs-lookup"><span data-stu-id="f2a89-201">excludedPath</span></span> <br/> <span data-ttu-id="f2a89-202">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="f2a89-202">excludedFileExtension</span></span> <br/> <span data-ttu-id="f2a89-203">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="f2a89-203">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="f2a89-204">Pfad zu ausgeschlossenen Inhalten</span><span class="sxs-lookup"><span data-stu-id="f2a89-204">Path to excluded content</span></span>

<span data-ttu-id="f2a89-205">Geben Sie Inhalte an, die nicht durch den vollständigen Dateipfad gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-205">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="f2a89-206">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-206">Section</span></span>|<span data-ttu-id="f2a89-207">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-207">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-208">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-209">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-209">**Key**</span></span> | <span data-ttu-id="f2a89-210">path</span><span class="sxs-lookup"><span data-stu-id="f2a89-210">path</span></span> |
| <span data-ttu-id="f2a89-211">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-211">**Data type**</span></span> | <span data-ttu-id="f2a89-212">String</span><span class="sxs-lookup"><span data-stu-id="f2a89-212">String</span></span> |
| <span data-ttu-id="f2a89-213">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-213">**Possible values**</span></span> | <span data-ttu-id="f2a89-214">gültige Pfade</span><span class="sxs-lookup"><span data-stu-id="f2a89-214">valid paths</span></span> |
| <span data-ttu-id="f2a89-215">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-215">**Comments**</span></span> | <span data-ttu-id="f2a89-216">Gilt nur, *$type* *ausgeschlossen IstPath*</span><span class="sxs-lookup"><span data-stu-id="f2a89-216">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="f2a89-217">Pfadtyp (Datei/Verzeichnis)</span><span class="sxs-lookup"><span data-stu-id="f2a89-217">Path type (file / directory)</span></span>

<span data-ttu-id="f2a89-218">Gibt an, ob *die path-Eigenschaft* auf eine Datei oder ein Verzeichnis verweist.</span><span class="sxs-lookup"><span data-stu-id="f2a89-218">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="f2a89-219">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-219">Section</span></span>|<span data-ttu-id="f2a89-220">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-220">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-221">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-221">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-222">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-222">**Key**</span></span> | <span data-ttu-id="f2a89-223">isDirectory</span><span class="sxs-lookup"><span data-stu-id="f2a89-223">isDirectory</span></span> |
| <span data-ttu-id="f2a89-224">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-224">**Data type**</span></span> | <span data-ttu-id="f2a89-225">Boolesch</span><span class="sxs-lookup"><span data-stu-id="f2a89-225">Boolean</span></span> |
| <span data-ttu-id="f2a89-226">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-226">**Possible values**</span></span> | <span data-ttu-id="f2a89-227">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="f2a89-227">false (default)</span></span> <br/> <span data-ttu-id="f2a89-228">true</span><span class="sxs-lookup"><span data-stu-id="f2a89-228">true</span></span> |
| <span data-ttu-id="f2a89-229">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-229">**Comments**</span></span> | <span data-ttu-id="f2a89-230">Gilt nur, *$type* *ausgeschlossen IstPath*</span><span class="sxs-lookup"><span data-stu-id="f2a89-230">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="f2a89-231">Dateierweiterung, die von der Überprüfung ausgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="f2a89-231">File extension excluded from the scan</span></span>

<span data-ttu-id="f2a89-232">Geben Sie Inhalte an, die von der Dateierweiterung nicht gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-232">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="f2a89-233">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-233">Section</span></span>|<span data-ttu-id="f2a89-234">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-234">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-235">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-235">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-236">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-236">**Key**</span></span> | <span data-ttu-id="f2a89-237">erweiterung</span><span class="sxs-lookup"><span data-stu-id="f2a89-237">extension</span></span> |
| <span data-ttu-id="f2a89-238">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-238">**Data type**</span></span> | <span data-ttu-id="f2a89-239">String</span><span class="sxs-lookup"><span data-stu-id="f2a89-239">String</span></span> |
| <span data-ttu-id="f2a89-240">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-240">**Possible values**</span></span> | <span data-ttu-id="f2a89-241">Gültige Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="f2a89-241">valid file extensions</span></span> |
| <span data-ttu-id="f2a89-242">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-242">**Comments**</span></span> | <span data-ttu-id="f2a89-243">Gilt nur, *$type* *ausgeschlossen istFileExtension*</span><span class="sxs-lookup"><span data-stu-id="f2a89-243">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="f2a89-244">Prozess, der von der Überprüfung ausgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="f2a89-244">Process excluded from the scan</span></span>

<span data-ttu-id="f2a89-245">Geben Sie einen Prozess an, für den alle Dateiaktivitäten von der Überprüfung ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-245">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="f2a89-246">Der Prozess kann entweder durch seinen Namen (z. B. ) oder den vollständigen `cat` Pfad (z. B. ) angegeben werden. `/bin/cat`</span><span class="sxs-lookup"><span data-stu-id="f2a89-246">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="f2a89-247">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-247">Section</span></span>|<span data-ttu-id="f2a89-248">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-248">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-249">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-250">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-250">**Key**</span></span> | <span data-ttu-id="f2a89-251">Name</span><span class="sxs-lookup"><span data-stu-id="f2a89-251">name</span></span> |
| <span data-ttu-id="f2a89-252">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-252">**Data type**</span></span> | <span data-ttu-id="f2a89-253">String</span><span class="sxs-lookup"><span data-stu-id="f2a89-253">String</span></span> |
| <span data-ttu-id="f2a89-254">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-254">**Possible values**</span></span> | <span data-ttu-id="f2a89-255">eine beliebige Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f2a89-255">any string</span></span> |
| <span data-ttu-id="f2a89-256">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-256">**Comments**</span></span> | <span data-ttu-id="f2a89-257">Gilt nur, *$type* *ausgeschlossen istFileName*</span><span class="sxs-lookup"><span data-stu-id="f2a89-257">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="f2a89-258">Zulässige Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="f2a89-258">Allowed threats</span></span>

<span data-ttu-id="f2a89-259">Geben Sie Bedrohungen nach Namen an, die nicht von Defender for Endpoint für Mac blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-259">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="f2a89-260">Diese Bedrohungen können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-260">These threats will be allowed to run.</span></span>

|<span data-ttu-id="f2a89-261">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-261">Section</span></span>|<span data-ttu-id="f2a89-262">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-262">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-263">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-263">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-264">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-264">**Key**</span></span> | <span data-ttu-id="f2a89-265">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="f2a89-265">allowedThreats</span></span> |
| <span data-ttu-id="f2a89-266">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-266">**Data type**</span></span> | <span data-ttu-id="f2a89-267">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f2a89-267">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="f2a89-268">Unzulässige Bedrohungsaktionen</span><span class="sxs-lookup"><span data-stu-id="f2a89-268">Disallowed threat actions</span></span>

<span data-ttu-id="f2a89-269">Schränkt die Aktionen ein, die der lokale Benutzer eines Geräts ausführen kann, wenn Bedrohungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-269">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="f2a89-270">Die in dieser Liste enthaltenen Aktionen werden nicht auf der Benutzeroberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2a89-270">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="f2a89-271">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-271">Section</span></span>|<span data-ttu-id="f2a89-272">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-272">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-273">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-273">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-274">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-274">**Key**</span></span> | <span data-ttu-id="f2a89-275">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="f2a89-275">disallowedThreatActions</span></span> |
| <span data-ttu-id="f2a89-276">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-276">**Data type**</span></span> | <span data-ttu-id="f2a89-277">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f2a89-277">Array of strings</span></span> |
| <span data-ttu-id="f2a89-278">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-278">**Possible values**</span></span> | <span data-ttu-id="f2a89-279">allow (schränkt ein, dass Benutzer Bedrohungen zulassen)</span><span class="sxs-lookup"><span data-stu-id="f2a89-279">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="f2a89-280">restore (schränkt benutzer das Wiederherstellen von Bedrohungen aus der Quarantäne ein)</span><span class="sxs-lookup"><span data-stu-id="f2a89-280">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="f2a89-281">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-281">**Comments**</span></span> | <span data-ttu-id="f2a89-282">Verfügbar in Microsoft Defender for Endpoint, Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="f2a89-282">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="f2a89-283">Einstellungen für den Bedrohungstyp</span><span class="sxs-lookup"><span data-stu-id="f2a89-283">Threat type settings</span></span>

<span data-ttu-id="f2a89-284">Geben Sie an, wie bestimmte Bedrohungstypen von Microsoft Defender for Endpoint unter macOS behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-284">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="f2a89-285">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-285">Section</span></span>|<span data-ttu-id="f2a89-286">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-286">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-287">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-287">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-288">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-288">**Key**</span></span> | <span data-ttu-id="f2a89-289">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="f2a89-289">threatTypeSettings</span></span> |
| <span data-ttu-id="f2a89-290">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-290">**Data type**</span></span> | <span data-ttu-id="f2a89-291">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="f2a89-291">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="f2a89-292">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-292">**Comments**</span></span> | <span data-ttu-id="f2a89-293">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="f2a89-293">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="f2a89-294">Bedrohungstyp</span><span class="sxs-lookup"><span data-stu-id="f2a89-294">Threat type</span></span>

<span data-ttu-id="f2a89-295">Geben Sie Bedrohungstypen an.</span><span class="sxs-lookup"><span data-stu-id="f2a89-295">Specify threat types.</span></span>

|<span data-ttu-id="f2a89-296">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-296">Section</span></span>|<span data-ttu-id="f2a89-297">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-298">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-299">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-299">**Key**</span></span> | <span data-ttu-id="f2a89-300">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="f2a89-300">key</span></span> |
| <span data-ttu-id="f2a89-301">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-301">**Data type**</span></span> | <span data-ttu-id="f2a89-302">String</span><span class="sxs-lookup"><span data-stu-id="f2a89-302">String</span></span> |
| <span data-ttu-id="f2a89-303">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-303">**Possible values**</span></span> | <span data-ttu-id="f2a89-304">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="f2a89-304">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="f2a89-305">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="f2a89-305">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="f2a89-306">Zu ergreifende Maßnahme</span><span class="sxs-lookup"><span data-stu-id="f2a89-306">Action to take</span></span>

<span data-ttu-id="f2a89-307">Geben Sie an, welche Aktion ausgeführt werden soll, wenn eine Bedrohung des im vorherigen Abschnitt angegebenen Typs erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="f2a89-307">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="f2a89-308">Wählen Sie aus den folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="f2a89-308">Choose from the following options:</span></span>

- <span data-ttu-id="f2a89-309">**Überwachung:** Ihr Gerät ist nicht vor dieser Art von Bedrohung geschützt, aber ein Eintrag über die Bedrohung wird protokolliert.</span><span class="sxs-lookup"><span data-stu-id="f2a89-309">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="f2a89-310">**Block**: Ihr Gerät ist vor dieser Art von Bedrohung geschützt, und Sie werden über die Benutzeroberfläche und die Sicherheitskonsole benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="f2a89-310">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="f2a89-311">**Aus**: Ihr Gerät ist nicht vor dieser Art von Bedrohung geschützt, und es wird nichts protokolliert.</span><span class="sxs-lookup"><span data-stu-id="f2a89-311">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="f2a89-312">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-312">Section</span></span>|<span data-ttu-id="f2a89-313">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-313">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-314">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-314">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-315">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-315">**Key**</span></span> | <span data-ttu-id="f2a89-316">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-316">value</span></span> |
| <span data-ttu-id="f2a89-317">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-317">**Data type**</span></span> | <span data-ttu-id="f2a89-318">String</span><span class="sxs-lookup"><span data-stu-id="f2a89-318">String</span></span> |
| <span data-ttu-id="f2a89-319">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-319">**Possible values**</span></span> | <span data-ttu-id="f2a89-320">Überwachung (Standard)</span><span class="sxs-lookup"><span data-stu-id="f2a89-320">audit (default)</span></span> <br/> <span data-ttu-id="f2a89-321">block</span><span class="sxs-lookup"><span data-stu-id="f2a89-321">block</span></span> <br/> <span data-ttu-id="f2a89-322">off</span><span class="sxs-lookup"><span data-stu-id="f2a89-322">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="f2a89-323">Richtlinie zum Zusammenführen von Bedrohungstypeinstellungen</span><span class="sxs-lookup"><span data-stu-id="f2a89-323">Threat type settings merge policy</span></span>

<span data-ttu-id="f2a89-324">Geben Sie die Seriendruckrichtlinie für Bedrohungstypeinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="f2a89-324">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="f2a89-325">Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Einstellungen ( ) oder nur vom Administrator definierten Einstellungen `merge` ( ) `admin_only` sein.</span><span class="sxs-lookup"><span data-stu-id="f2a89-325">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="f2a89-326">Diese Einstellung kann verwendet werden, um lokale Benutzer an der Definition eigener Einstellungen für verschiedene Bedrohungstypen zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="f2a89-326">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="f2a89-327">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-327">Section</span></span>|<span data-ttu-id="f2a89-328">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-328">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-329">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-329">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-330">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-330">**Key**</span></span> | <span data-ttu-id="f2a89-331">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="f2a89-331">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="f2a89-332">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-332">**Data type**</span></span> | <span data-ttu-id="f2a89-333">String</span><span class="sxs-lookup"><span data-stu-id="f2a89-333">String</span></span> |
| <span data-ttu-id="f2a89-334">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-334">**Possible values**</span></span> | <span data-ttu-id="f2a89-335">merge (Standard)</span><span class="sxs-lookup"><span data-stu-id="f2a89-335">merge (default)</span></span> <br/> <span data-ttu-id="f2a89-336">admin_only</span><span class="sxs-lookup"><span data-stu-id="f2a89-336">admin_only</span></span> |
| <span data-ttu-id="f2a89-337">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-337">**Comments**</span></span> | <span data-ttu-id="f2a89-338">Verfügbar in Microsoft Defender for Endpoint, Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="f2a89-338">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="f2a89-339">Aufbewahrung des Antivirusscanverlaufs (in Tagen)</span><span class="sxs-lookup"><span data-stu-id="f2a89-339">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="f2a89-340">Geben Sie die Anzahl der Tage an, die Ergebnisse im Scanverlauf auf dem Gerät aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-340">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="f2a89-341">Alte Scanergebnisse werden aus dem Verlauf entfernt.</span><span class="sxs-lookup"><span data-stu-id="f2a89-341">Old scan results are removed from the history.</span></span> <span data-ttu-id="f2a89-342">Alte isolierte Dateien, die ebenfalls vom Datenträger entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-342">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="f2a89-343">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-343">Section</span></span>|<span data-ttu-id="f2a89-344">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-344">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-345">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-345">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-346">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-346">**Key**</span></span> | <span data-ttu-id="f2a89-347">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="f2a89-347">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="f2a89-348">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-348">**Data type**</span></span> | <span data-ttu-id="f2a89-349">String</span><span class="sxs-lookup"><span data-stu-id="f2a89-349">String</span></span> |
| <span data-ttu-id="f2a89-350">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-350">**Possible values**</span></span> | <span data-ttu-id="f2a89-351">90 (Standard).</span><span class="sxs-lookup"><span data-stu-id="f2a89-351">90 (default).</span></span> <span data-ttu-id="f2a89-352">Zulässige Werte liegen zwischen 1 Tag und 180 Tagen.</span><span class="sxs-lookup"><span data-stu-id="f2a89-352">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="f2a89-353">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-353">**Comments**</span></span> | <span data-ttu-id="f2a89-354">Verfügbar in Microsoft Defender for Endpoint, Version 101.07.23 oder höher.</span><span class="sxs-lookup"><span data-stu-id="f2a89-354">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="f2a89-355">Maximale Anzahl von Elementen im Antivirusscanverlauf</span><span class="sxs-lookup"><span data-stu-id="f2a89-355">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="f2a89-356">Geben Sie die maximale Anzahl von Einträgen an, die im Scanverlauf bleiben sollen.</span><span class="sxs-lookup"><span data-stu-id="f2a89-356">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="f2a89-357">Zu den Einträgen gehören alle in der Vergangenheit durchgeführten Bedarfsscans und alle Antivirenerkennungen.</span><span class="sxs-lookup"><span data-stu-id="f2a89-357">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="f2a89-358">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-358">Section</span></span>|<span data-ttu-id="f2a89-359">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-359">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-360">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-360">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-361">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-361">**Key**</span></span> | <span data-ttu-id="f2a89-362">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="f2a89-362">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="f2a89-363">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-363">**Data type**</span></span> | <span data-ttu-id="f2a89-364">String</span><span class="sxs-lookup"><span data-stu-id="f2a89-364">String</span></span> |
| <span data-ttu-id="f2a89-365">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-365">**Possible values**</span></span> | <span data-ttu-id="f2a89-366">10000 (Standard).</span><span class="sxs-lookup"><span data-stu-id="f2a89-366">10000 (default).</span></span> <span data-ttu-id="f2a89-367">Zulässige Werte liegen zwischen 5.000 und 15.000 Elementen.</span><span class="sxs-lookup"><span data-stu-id="f2a89-367">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="f2a89-368">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-368">**Comments**</span></span> | <span data-ttu-id="f2a89-369">Verfügbar in Microsoft Defender for Endpoint, Version 101.07.23 oder höher.</span><span class="sxs-lookup"><span data-stu-id="f2a89-369">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="f2a89-370">Von der Cloud übermittelte Schutzeinstellungen</span><span class="sxs-lookup"><span data-stu-id="f2a89-370">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="f2a89-371">Konfigurieren Sie die cloudgesteuerten Schutzfunktionen von Microsoft Defender for Endpoint unter macOS.</span><span class="sxs-lookup"><span data-stu-id="f2a89-371">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="f2a89-372">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-372">Section</span></span>|<span data-ttu-id="f2a89-373">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-373">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-374">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-374">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-375">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-375">**Key**</span></span> | <span data-ttu-id="f2a89-376">cloudService</span><span class="sxs-lookup"><span data-stu-id="f2a89-376">cloudService</span></span> |
| <span data-ttu-id="f2a89-377">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-377">**Data type**</span></span> | <span data-ttu-id="f2a89-378">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="f2a89-378">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="f2a89-379">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-379">**Comments**</span></span> | <span data-ttu-id="f2a89-380">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="f2a89-380">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="f2a89-381">Aktivieren/Deaktivieren des in der Cloud übermittelten Schutzes</span><span class="sxs-lookup"><span data-stu-id="f2a89-381">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="f2a89-382">Geben Sie an, ob der in der Cloud zugestellte Schutz auf dem Gerät aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f2a89-382">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="f2a89-383">Um die Sicherheit Ihrer Dienste zu verbessern, wird empfohlen, dieses Feature aktiviert zu halten.</span><span class="sxs-lookup"><span data-stu-id="f2a89-383">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="f2a89-384">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-384">Section</span></span>|<span data-ttu-id="f2a89-385">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-385">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-386">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-386">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-387">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-387">**Key**</span></span> | <span data-ttu-id="f2a89-388">aktiviert</span><span class="sxs-lookup"><span data-stu-id="f2a89-388">enabled</span></span> |
| <span data-ttu-id="f2a89-389">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-389">**Data type**</span></span> | <span data-ttu-id="f2a89-390">Boolesch</span><span class="sxs-lookup"><span data-stu-id="f2a89-390">Boolean</span></span> |
| <span data-ttu-id="f2a89-391">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-391">**Possible values**</span></span> | <span data-ttu-id="f2a89-392">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="f2a89-392">true (default)</span></span> <br/> <span data-ttu-id="f2a89-393">false</span><span class="sxs-lookup"><span data-stu-id="f2a89-393">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="f2a89-394">Diagnosesammlungsebene</span><span class="sxs-lookup"><span data-stu-id="f2a89-394">Diagnostic collection level</span></span>

<span data-ttu-id="f2a89-395">Diagnosedaten werden verwendet, um Microsoft Defender for Endpoint sicher und auf dem neuesten Stand zu halten, Probleme zu erkennen, zu diagnostizieren und zu beheben sowie Produktverbesserungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f2a89-395">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="f2a89-396">Diese Einstellung bestimmt die Diagnosestufe, die von Microsoft Defender for Endpoint an Microsoft gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="f2a89-396">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="f2a89-397">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-397">Section</span></span>|<span data-ttu-id="f2a89-398">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-399">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-400">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-400">**Key**</span></span> | <span data-ttu-id="f2a89-401">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="f2a89-401">diagnosticLevel</span></span> |
| <span data-ttu-id="f2a89-402">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-402">**Data type**</span></span> | <span data-ttu-id="f2a89-403">String</span><span class="sxs-lookup"><span data-stu-id="f2a89-403">String</span></span> |
| <span data-ttu-id="f2a89-404">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-404">**Possible values**</span></span> | <span data-ttu-id="f2a89-405">optional (Standard)</span><span class="sxs-lookup"><span data-stu-id="f2a89-405">optional (default)</span></span> <br/> <span data-ttu-id="f2a89-406">erforderlich</span><span class="sxs-lookup"><span data-stu-id="f2a89-406">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="f2a89-407">Aktivieren/Deaktivieren automatischer Beispielübermittlungen</span><span class="sxs-lookup"><span data-stu-id="f2a89-407">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="f2a89-408">Bestimmt, ob verdächtige Beispiele (die wahrscheinlich Bedrohungen enthalten) an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-408">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="f2a89-409">Sie werden aufgefordert, wenn die übermittelte Datei wahrscheinlich personenbezogene Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="f2a89-409">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="f2a89-410">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-410">Section</span></span>|<span data-ttu-id="f2a89-411">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-411">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-412">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-412">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-413">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-413">**Key**</span></span> | <span data-ttu-id="f2a89-414">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="f2a89-414">automaticSampleSubmission</span></span> |
| <span data-ttu-id="f2a89-415">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-415">**Data type**</span></span> | <span data-ttu-id="f2a89-416">Boolesch</span><span class="sxs-lookup"><span data-stu-id="f2a89-416">Boolean</span></span> |
| <span data-ttu-id="f2a89-417">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-417">**Possible values**</span></span> | <span data-ttu-id="f2a89-418">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="f2a89-418">true (default)</span></span> <br/> <span data-ttu-id="f2a89-419">false</span><span class="sxs-lookup"><span data-stu-id="f2a89-419">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="f2a89-420">Aktivieren/Deaktivieren automatischer Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="f2a89-420">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="f2a89-421">Bestimmt, ob Sicherheitsintelligenzupdates automatisch installiert werden:</span><span class="sxs-lookup"><span data-stu-id="f2a89-421">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="f2a89-422">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-422">Section</span></span>|<span data-ttu-id="f2a89-423">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-424">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-424">**Key**</span></span> | <span data-ttu-id="f2a89-425">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="f2a89-425">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="f2a89-426">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-426">**Data type**</span></span> | <span data-ttu-id="f2a89-427">Boolesch</span><span class="sxs-lookup"><span data-stu-id="f2a89-427">Boolean</span></span> |
| <span data-ttu-id="f2a89-428">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-428">**Possible values**</span></span> | <span data-ttu-id="f2a89-429">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="f2a89-429">true (default)</span></span> <br/> <span data-ttu-id="f2a89-430">false</span><span class="sxs-lookup"><span data-stu-id="f2a89-430">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="f2a89-431">Benutzeroberflächeneinstellungen</span><span class="sxs-lookup"><span data-stu-id="f2a89-431">User interface preferences</span></span>

<span data-ttu-id="f2a89-432">Verwalten Sie die Einstellungen für die Benutzeroberfläche von Microsoft Defender for Endpoint unter macOS.</span><span class="sxs-lookup"><span data-stu-id="f2a89-432">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="f2a89-433">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-433">Section</span></span>|<span data-ttu-id="f2a89-434">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-434">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-435">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-435">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-436">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-436">**Key**</span></span> | <span data-ttu-id="f2a89-437">userInterface</span><span class="sxs-lookup"><span data-stu-id="f2a89-437">userInterface</span></span> |
| <span data-ttu-id="f2a89-438">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-438">**Data type**</span></span> | <span data-ttu-id="f2a89-439">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="f2a89-439">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="f2a89-440">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-440">**Comments**</span></span> | <span data-ttu-id="f2a89-441">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="f2a89-441">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="f2a89-442">Symbol für Das Menü "Status anzeigen/ausblenden"</span><span class="sxs-lookup"><span data-stu-id="f2a89-442">Show / hide status menu icon</span></span>

<span data-ttu-id="f2a89-443">Geben Sie an, ob das Statusmenüsymbol in der oberen rechten Ecke des Bildschirms ein- oder ausgeblendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f2a89-443">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="f2a89-444">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-444">Section</span></span>|<span data-ttu-id="f2a89-445">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-445">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-446">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-447">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-447">**Key**</span></span> | <span data-ttu-id="f2a89-448">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="f2a89-448">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="f2a89-449">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-449">**Data type**</span></span> | <span data-ttu-id="f2a89-450">Boolesch</span><span class="sxs-lookup"><span data-stu-id="f2a89-450">Boolean</span></span> |
| <span data-ttu-id="f2a89-451">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-451">**Possible values**</span></span> | <span data-ttu-id="f2a89-452">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="f2a89-452">false (default)</span></span> <br/> <span data-ttu-id="f2a89-453">true</span><span class="sxs-lookup"><span data-stu-id="f2a89-453">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="f2a89-454">Ein-/Ausblenden der Option zum Senden von Feedback</span><span class="sxs-lookup"><span data-stu-id="f2a89-454">Show / hide option to send feedback</span></span>

<span data-ttu-id="f2a89-455">Geben Sie an, ob Benutzer Feedback an Microsoft senden können, indem Sie zu `Help`  >  `Send Feedback` gehen.</span><span class="sxs-lookup"><span data-stu-id="f2a89-455">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="f2a89-456">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-456">Section</span></span>|<span data-ttu-id="f2a89-457">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-457">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-458">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-458">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-459">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-459">**Key**</span></span> | <span data-ttu-id="f2a89-460">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="f2a89-460">userInitiatedFeedback</span></span> |
| <span data-ttu-id="f2a89-461">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-461">**Data type**</span></span> | <span data-ttu-id="f2a89-462">String</span><span class="sxs-lookup"><span data-stu-id="f2a89-462">String</span></span> |
| <span data-ttu-id="f2a89-463">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-463">**Possible values**</span></span> | <span data-ttu-id="f2a89-464">aktiviert (Standard)</span><span class="sxs-lookup"><span data-stu-id="f2a89-464">enabled (default)</span></span> <br/> <span data-ttu-id="f2a89-465">deaktiviert</span><span class="sxs-lookup"><span data-stu-id="f2a89-465">disabled</span></span> |
| <span data-ttu-id="f2a89-466">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-466">**Comments**</span></span> | <span data-ttu-id="f2a89-467">Verfügbar in Microsoft Defender for Endpoint, Version 101.19.61 oder höher.</span><span class="sxs-lookup"><span data-stu-id="f2a89-467">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="f2a89-468">Einstellungen für endpunkterkennung und -reaktion</span><span class="sxs-lookup"><span data-stu-id="f2a89-468">Endpoint detection and response preferences</span></span>

<span data-ttu-id="f2a89-469">Verwalten Sie die Einstellungen der Endpunkterkennungs- und -antwortkomponente von Microsoft Defender for Endpoint unter macOS.</span><span class="sxs-lookup"><span data-stu-id="f2a89-469">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="f2a89-470">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-470">Section</span></span>|<span data-ttu-id="f2a89-471">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-471">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-472">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-472">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-473">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-473">**Key**</span></span> | <span data-ttu-id="f2a89-474">edr</span><span class="sxs-lookup"><span data-stu-id="f2a89-474">edr</span></span> |
| <span data-ttu-id="f2a89-475">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-475">**Data type**</span></span> | <span data-ttu-id="f2a89-476">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="f2a89-476">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="f2a89-477">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-477">**Comments**</span></span> | <span data-ttu-id="f2a89-478">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="f2a89-478">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="f2a89-479">Gerätetags</span><span class="sxs-lookup"><span data-stu-id="f2a89-479">Device tags</span></span>

<span data-ttu-id="f2a89-480">Geben Sie einen Tagnamen und dessen Wert an.</span><span class="sxs-lookup"><span data-stu-id="f2a89-480">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="f2a89-481">Das GROUP-Tag tagt das Gerät mit dem angegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="f2a89-481">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="f2a89-482">Das Tag wird im Portal unter der Geräteseite angezeigt und kann zum Filtern und Gruppieren von Geräten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-482">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="f2a89-483">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-483">Section</span></span>|<span data-ttu-id="f2a89-484">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-484">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-485">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-485">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-486">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-486">**Key**</span></span> | <span data-ttu-id="f2a89-487">tags</span><span class="sxs-lookup"><span data-stu-id="f2a89-487">tags</span></span> |
| <span data-ttu-id="f2a89-488">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-488">**Data type**</span></span> | <span data-ttu-id="f2a89-489">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="f2a89-489">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="f2a89-490">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="f2a89-490">**Comments**</span></span> | <span data-ttu-id="f2a89-491">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="f2a89-491">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="f2a89-492">Tagtyp</span><span class="sxs-lookup"><span data-stu-id="f2a89-492">Type of tag</span></span>

<span data-ttu-id="f2a89-493">Gibt den Typ des Tags an.</span><span class="sxs-lookup"><span data-stu-id="f2a89-493">Specifies the type of tag</span></span>

|<span data-ttu-id="f2a89-494">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-494">Section</span></span>|<span data-ttu-id="f2a89-495">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-495">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-496">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-496">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-497">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-497">**Key**</span></span> | <span data-ttu-id="f2a89-498">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="f2a89-498">key</span></span> |
| <span data-ttu-id="f2a89-499">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-499">**Data type**</span></span> | <span data-ttu-id="f2a89-500">String</span><span class="sxs-lookup"><span data-stu-id="f2a89-500">String</span></span> |
| <span data-ttu-id="f2a89-501">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-501">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="f2a89-502">Wert des Tags</span><span class="sxs-lookup"><span data-stu-id="f2a89-502">Value of tag</span></span>

<span data-ttu-id="f2a89-503">Gibt den Wert des Tags an.</span><span class="sxs-lookup"><span data-stu-id="f2a89-503">Specifies the value of tag</span></span>

|<span data-ttu-id="f2a89-504">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2a89-504">Section</span></span>|<span data-ttu-id="f2a89-505">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-505">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f2a89-506">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="f2a89-506">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f2a89-507">**Key**</span><span class="sxs-lookup"><span data-stu-id="f2a89-507">**Key**</span></span> | <span data-ttu-id="f2a89-508">Wert</span><span class="sxs-lookup"><span data-stu-id="f2a89-508">value</span></span> |
| <span data-ttu-id="f2a89-509">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f2a89-509">**Data type**</span></span> | <span data-ttu-id="f2a89-510">String</span><span class="sxs-lookup"><span data-stu-id="f2a89-510">String</span></span> |
| <span data-ttu-id="f2a89-511">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="f2a89-511">**Possible values**</span></span> | <span data-ttu-id="f2a89-512">eine beliebige Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f2a89-512">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="f2a89-513">Pro Tagtyp kann nur ein Wert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-513">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="f2a89-514">Der Typ von Tags ist eindeutig und sollte nicht im gleichen Konfigurationsprofil wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="f2a89-514">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="f2a89-515">Empfohlenes Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="f2a89-515">Recommended configuration profile</span></span>

<span data-ttu-id="f2a89-516">Für die ersten Schritte empfehlen wir die folgende Konfiguration für Ihr Unternehmen, um alle Von Microsoft Defender for Endpoint-Funktionen zur Nutzung zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="f2a89-516">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="f2a89-517">Das folgende Konfigurationsprofil (oder im Fall von JAMF eine Eigenschaftenliste, die in das Konfigurationsprofil für benutzerdefinierte Einstellungen hochgeladen werden könnte) wird verwendet:</span><span class="sxs-lookup"><span data-stu-id="f2a89-517">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="f2a89-518">Aktivieren des Echtzeitschutzes (Real-Time Protection, RTP)</span><span class="sxs-lookup"><span data-stu-id="f2a89-518">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="f2a89-519">Geben Sie an, wie die folgenden Bedrohungstypen behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="f2a89-519">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="f2a89-520">**Potenziell unerwünschte Anwendungen (PUA)** werden blockiert</span><span class="sxs-lookup"><span data-stu-id="f2a89-520">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="f2a89-521">**Archivangriffe** (Datei mit hoher Komprimierungsrate) werden bei Microsoft Defender für Endpunktprotokolle überwacht.</span><span class="sxs-lookup"><span data-stu-id="f2a89-521">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="f2a89-522">Aktivieren automatischer Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="f2a89-522">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="f2a89-523">Aktivieren des in der Cloud übermittelten Schutzes</span><span class="sxs-lookup"><span data-stu-id="f2a89-523">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="f2a89-524">Aktivieren der automatischen Beispielübermittlung</span><span class="sxs-lookup"><span data-stu-id="f2a89-524">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="f2a89-525">Eigenschaftenliste für das JAMF-Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="f2a89-525">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="f2a89-526">Intune-Profil</span><span class="sxs-lookup"><span data-stu-id="f2a89-526">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="f2a89-527">Beispiel für ein vollständiges Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="f2a89-527">Full configuration profile example</span></span>

<span data-ttu-id="f2a89-528">Die folgenden Vorlagen enthalten Einträge für alle in diesem Dokument beschriebenen Einstellungen und können für erweiterte Szenarien verwendet werden, in denen Sie mehr Kontrolle über Microsoft Defender for Endpoint unter macOS wünschen.</span><span class="sxs-lookup"><span data-stu-id="f2a89-528">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="f2a89-529">Eigenschaftenliste für das JAMF-Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="f2a89-529">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="f2a89-530">Intune-Profil</span><span class="sxs-lookup"><span data-stu-id="f2a89-530">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="f2a89-531">Eigenschaftenlistenüberprüfung</span><span class="sxs-lookup"><span data-stu-id="f2a89-531">Property list validation</span></span>

<span data-ttu-id="f2a89-532">Die Eigenschaftenliste muss eine gültige *.plist-Datei* sein.</span><span class="sxs-lookup"><span data-stu-id="f2a89-532">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="f2a89-533">Dies kann durch Ausführen von:</span><span class="sxs-lookup"><span data-stu-id="f2a89-533">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="f2a89-534">Wenn die Datei wohlgeformt ist, wird mit dem obigen Befehl der `OK` Exitcode ausgegeben und `0` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f2a89-534">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="f2a89-535">Andernfalls wird ein Fehler angezeigt, der das Problem beschreibt, und der Befehl gibt den Exitcode von `1` zurück.</span><span class="sxs-lookup"><span data-stu-id="f2a89-535">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="f2a89-536">Konfigurationsprofilbereitstellung</span><span class="sxs-lookup"><span data-stu-id="f2a89-536">Configuration profile deployment</span></span>

<span data-ttu-id="f2a89-537">Nachdem Sie das Konfigurationsprofil für Ihr Unternehmen erstellt haben, können Sie es über die Verwaltungskonsole bereitstellen, die Ihr Unternehmen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f2a89-537">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="f2a89-538">In den folgenden Abschnitten finden Sie Anweisungen zum Bereitstellen dieses Profils mithilfe von JAMF und Intune.</span><span class="sxs-lookup"><span data-stu-id="f2a89-538">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="f2a89-539">JAMF-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="f2a89-539">JAMF deployment</span></span>

<span data-ttu-id="f2a89-540">Öffnen Sie in der JAMF-Konsole  >  **Computerkonfigurationsprofile,** navigieren Sie zu dem Konfigurationsprofil, das Sie verwenden möchten, und wählen Sie dann **Benutzerdefinierte Einstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="f2a89-540">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="f2a89-541">Erstellen Sie einen Eintrag `com.microsoft.wdav` mit als Einstellungsdomäne, und laden Sie die zuvor produzierte *.plist* hoch.</span><span class="sxs-lookup"><span data-stu-id="f2a89-541">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="f2a89-542">Sie müssen die richtige Einstellungsdomäne eingeben ( ); andernfalls werden die Einstellungen von `com.microsoft.wdav` Microsoft Defender for Endpoint nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="f2a89-542">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="f2a89-543">Intune-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="f2a89-543">Intune deployment</span></span>

1. <span data-ttu-id="f2a89-544">Öffnen **Sie**  >  **Gerätekonfiguration verwalten**.</span><span class="sxs-lookup"><span data-stu-id="f2a89-544">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="f2a89-545">Wählen **Sie Profil** erstellen von  >    >  **Profilen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="f2a89-545">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="f2a89-546">Wählen Sie einen Namen für das Profil aus.</span><span class="sxs-lookup"><span data-stu-id="f2a89-546">Choose a name for the profile.</span></span> <span data-ttu-id="f2a89-547">Ändern **sie Platform=macOS** in **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="f2a89-547">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="f2a89-548">Wählen Sie Konfigurieren aus.</span><span class="sxs-lookup"><span data-stu-id="f2a89-548">Select Configure.</span></span>

3. <span data-ttu-id="f2a89-549">Speichern Sie die .plist, die zuvor als erstellt `com.microsoft.wdav.xml` wurde.</span><span class="sxs-lookup"><span data-stu-id="f2a89-549">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="f2a89-550">Geben `com.microsoft.wdav` Sie als **benutzerdefinierter Konfigurationsprofilname ein.**</span><span class="sxs-lookup"><span data-stu-id="f2a89-550">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="f2a89-551">Öffnen Sie das Konfigurationsprofil, und laden Sie die Datei `com.microsoft.wdav.xml` hoch.</span><span class="sxs-lookup"><span data-stu-id="f2a89-551">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="f2a89-552">(Diese Datei wurde in Schritt 3 erstellt.)</span><span class="sxs-lookup"><span data-stu-id="f2a89-552">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="f2a89-553">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="f2a89-553">Select **OK**.</span></span>

7. <span data-ttu-id="f2a89-554">Wählen **Sie**  >  **Zuordnungen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="f2a89-554">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="f2a89-555">Wählen Sie **auf** der Registerkarte Include die Option **Allen Benutzern & Alle Geräte zuweisen aus.**</span><span class="sxs-lookup"><span data-stu-id="f2a89-555">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="f2a89-556">Sie müssen den richtigen namen des benutzerdefinierten Konfigurationsprofils eingeben. Andernfalls werden diese Einstellungen von Microsoft Defender for Endpoint nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="f2a89-556">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="f2a89-557">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f2a89-557">Resources</span></span>

- [<span data-ttu-id="f2a89-558">Konfigurationsprofilreferenz (Apple-Entwicklerdokumentationen)</span><span class="sxs-lookup"><span data-stu-id="f2a89-558">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
