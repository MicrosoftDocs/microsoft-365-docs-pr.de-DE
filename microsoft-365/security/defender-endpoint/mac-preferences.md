---
title: Festlegen von Einstellungen für Microsoft Defender ATP für Mac
description: Konfigurieren von Microsoft Defender ATP für Mac in Unternehmensorganisationen.
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
ms.openlocfilehash: 578830d44a9a69c3ccafd78ceaf59ddfe100e43f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068895"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="8e064-104">Festlegen von Einstellungen für Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="8e064-104">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8e064-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8e064-105">**Applies to:**</span></span>

- [<span data-ttu-id="8e064-106">Microsoft Defender für Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="8e064-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="8e064-107">Dieser Artikel enthält Anweisungen zum Festlegen von Einstellungen für Microsoft Defender for Endpoint für Mac in Unternehmensorganisationen.</span><span class="sxs-lookup"><span data-stu-id="8e064-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint for Mac in enterprise organizations.</span></span> <span data-ttu-id="8e064-108">Informationen zum Konfigurieren von Microsoft Defender for Endpoint für Mac über die Befehlszeilenschnittstelle finden Sie unter [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="8e064-108">To configure Microsoft Defender for Endpoint for Mac using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="8e064-109">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="8e064-109">Summary</span></span>

<span data-ttu-id="8e064-110">In Unternehmensorganisationen kann Microsoft Defender for Endpoint für Mac über ein Konfigurationsprofil verwaltet werden, das mithilfe eines von mehreren Verwaltungstools bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8e064-110">In enterprise organizations, Microsoft Defender for Endpoint for Mac can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="8e064-111">Einstellungen, die vom Sicherheitsbetriebsteam verwaltet werden, haben Vorrang vor Einstellungen, die lokal auf dem Gerät festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="8e064-112">Das Ändern der Einstellungen, die über das Konfigurationsprofil festgelegt werden, erfordert eskalierte Berechtigungen und ist für Benutzer ohne Administratorberechtigungen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8e064-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="8e064-113">Dieser Artikel beschreibt die Struktur des Konfigurationsprofils, enthält ein empfohlenes Profil, das Sie für die ersten Schritte verwenden können, und enthält Anweisungen zum Bereitstellen des Profils.</span><span class="sxs-lookup"><span data-stu-id="8e064-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="8e064-114">Konfigurationsprofilstruktur</span><span class="sxs-lookup"><span data-stu-id="8e064-114">Configuration profile structure</span></span>

<span data-ttu-id="8e064-115">Das Konfigurationsprofil ist eine *.plist-Datei,* die aus Einträgen besteht, die durch einen Schlüssel identifiziert werden (der den Namen der Einstellung angibt), gefolgt von einem Wert, der von der Art der Einstellung abhängt.</span><span class="sxs-lookup"><span data-stu-id="8e064-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="8e064-116">Werte können entweder einfach (z. B. ein numerischer Wert) oder komplex sein, z. B. eine geschachtelte Liste von Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="8e064-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="8e064-117">Das Layout des Konfigurationsprofils hängt von der verwendeten Verwaltungskonsole ab.</span><span class="sxs-lookup"><span data-stu-id="8e064-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="8e064-118">Die folgenden Abschnitte enthalten Beispiele für Konfigurationsprofile für JAMF und Intune.</span><span class="sxs-lookup"><span data-stu-id="8e064-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="8e064-119">Die oberste Ebene des Konfigurationsprofils enthält produktweite Einstellungen und Einträge für Unterbereiche von Microsoft Defender for Endpoint, die in den nächsten Abschnitten ausführlicher erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="8e064-120">Einstellungen des Antivirusmoduls</span><span class="sxs-lookup"><span data-stu-id="8e064-120">Antivirus engine preferences</span></span>

<span data-ttu-id="8e064-121">Der *Abschnitt antivirusEngine* des Konfigurationsprofils wird verwendet, um die Einstellungen der Antiviruskomponente von Microsoft Defender for Endpoint zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="8e064-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-122">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-123">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-123">**Key**</span></span> | <span data-ttu-id="8e064-124">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="8e064-124">antivirusEngine</span></span> |
| <span data-ttu-id="8e064-125">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-125">**Data type**</span></span> | <span data-ttu-id="8e064-126">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="8e064-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8e064-127">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-127">**Comments**</span></span> | <span data-ttu-id="8e064-128">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="8e064-128">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="8e064-129">Aktivieren/Deaktivieren des Echtzeitschutzes</span><span class="sxs-lookup"><span data-stu-id="8e064-129">Enable / disable real-time protection</span></span>

<span data-ttu-id="8e064-130">Geben Sie an, ob der Echtzeitschutz aktiviert werden soll, der Dateien beim Zugriff überprüft.</span><span class="sxs-lookup"><span data-stu-id="8e064-130">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-131">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-132">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-132">**Key**</span></span> | <span data-ttu-id="8e064-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="8e064-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="8e064-134">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-134">**Data type**</span></span> | <span data-ttu-id="8e064-135">Boolesch</span><span class="sxs-lookup"><span data-stu-id="8e064-135">Boolean</span></span> |
| <span data-ttu-id="8e064-136">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-136">**Possible values**</span></span> | <span data-ttu-id="8e064-137">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="8e064-137">true (default)</span></span> <br/> <span data-ttu-id="8e064-138">false</span><span class="sxs-lookup"><span data-stu-id="8e064-138">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="8e064-139">Aktivieren/Deaktivieren des passiven Modus</span><span class="sxs-lookup"><span data-stu-id="8e064-139">Enable / disable passive mode</span></span>

<span data-ttu-id="8e064-140">Geben Sie an, ob das Antivirenmodul im passiven Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8e064-140">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="8e064-141">Der passive Modus hat die folgenden Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="8e064-141">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="8e064-142">Echtzeitschutz ist deaktiviert</span><span class="sxs-lookup"><span data-stu-id="8e064-142">Real-time protection is turned off</span></span>
- <span data-ttu-id="8e064-143">Die Überprüfung bei Bedarf ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8e064-143">On-demand scanning is turned on</span></span>
- <span data-ttu-id="8e064-144">Automatische Bedrohungsbehebung ist deaktiviert</span><span class="sxs-lookup"><span data-stu-id="8e064-144">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="8e064-145">Sicherheitsintelligenzupdates sind aktiviert</span><span class="sxs-lookup"><span data-stu-id="8e064-145">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="8e064-146">Statusmenüsymbol ist ausgeblendet</span><span class="sxs-lookup"><span data-stu-id="8e064-146">Status menu icon is hidden</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-147">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-147">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-148">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-148">**Key**</span></span> | <span data-ttu-id="8e064-149">passiveMode</span><span class="sxs-lookup"><span data-stu-id="8e064-149">passiveMode</span></span> |
| <span data-ttu-id="8e064-150">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-150">**Data type**</span></span> | <span data-ttu-id="8e064-151">Boolesch</span><span class="sxs-lookup"><span data-stu-id="8e064-151">Boolean</span></span> |
| <span data-ttu-id="8e064-152">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-152">**Possible values**</span></span> | <span data-ttu-id="8e064-153">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="8e064-153">false (default)</span></span> <br/> <span data-ttu-id="8e064-154">true</span><span class="sxs-lookup"><span data-stu-id="8e064-154">true</span></span> |
| <span data-ttu-id="8e064-155">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-155">**Comments**</span></span> | <span data-ttu-id="8e064-156">Verfügbar in Microsoft Defender for Endpoint, Version 100.67.60 oder höher.</span><span class="sxs-lookup"><span data-stu-id="8e064-156">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="8e064-157">Ausschlusszusammenführungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="8e064-157">Exclusion merge policy</span></span>

<span data-ttu-id="8e064-158">Geben Sie die Seriendruckrichtlinie für Ausschlüsse an.</span><span class="sxs-lookup"><span data-stu-id="8e064-158">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="8e064-159">Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Ausschlüssen ( ) oder nur vom Administrator definierten `merge` Ausschlüssen ( `admin_only` ) sein.</span><span class="sxs-lookup"><span data-stu-id="8e064-159">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="8e064-160">Diese Einstellung kann verwendet werden, um lokale Benutzer an der Definition eigener Ausschlüsse zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="8e064-160">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-161">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-161">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-162">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-162">**Key**</span></span> | <span data-ttu-id="8e064-163">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="8e064-163">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="8e064-164">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-164">**Data type**</span></span> | <span data-ttu-id="8e064-165">String</span><span class="sxs-lookup"><span data-stu-id="8e064-165">String</span></span> |
| <span data-ttu-id="8e064-166">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-166">**Possible values**</span></span> | <span data-ttu-id="8e064-167">merge (Standard)</span><span class="sxs-lookup"><span data-stu-id="8e064-167">merge (default)</span></span> <br/> <span data-ttu-id="8e064-168">admin_only</span><span class="sxs-lookup"><span data-stu-id="8e064-168">admin_only</span></span> |
| <span data-ttu-id="8e064-169">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-169">**Comments**</span></span> | <span data-ttu-id="8e064-170">Verfügbar in Microsoft Defender for Endpoint, Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="8e064-170">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="8e064-171">Scannen von Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="8e064-171">Scan exclusions</span></span>

<span data-ttu-id="8e064-172">Geben Sie Entitäten an, die von der Gescannten ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-172">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="8e064-173">Ausschlüsse können durch vollständige Pfade, Erweiterungen oder Dateinamen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-173">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-174">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-174">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-175">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-175">**Key**</span></span> | <span data-ttu-id="8e064-176">Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="8e064-176">exclusions</span></span> |
| <span data-ttu-id="8e064-177">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-177">**Data type**</span></span> | <span data-ttu-id="8e064-178">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="8e064-178">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8e064-179">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-179">**Comments**</span></span> | <span data-ttu-id="8e064-180">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="8e064-180">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="8e064-181">Art des Ausschlusses</span><span class="sxs-lookup"><span data-stu-id="8e064-181">Type of exclusion</span></span>

<span data-ttu-id="8e064-182">Geben Sie Inhalte an, die vom Typ ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-182">Specify content excluded from being scanned by type.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-183">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-184">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-184">**Key**</span></span> | <span data-ttu-id="8e064-185">$type</span><span class="sxs-lookup"><span data-stu-id="8e064-185">$type</span></span> |
| <span data-ttu-id="8e064-186">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-186">**Data type**</span></span> | <span data-ttu-id="8e064-187">String</span><span class="sxs-lookup"><span data-stu-id="8e064-187">String</span></span> |
| <span data-ttu-id="8e064-188">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-188">**Possible values**</span></span> | <span data-ttu-id="8e064-189">excludedPath</span><span class="sxs-lookup"><span data-stu-id="8e064-189">excludedPath</span></span> <br/> <span data-ttu-id="8e064-190">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="8e064-190">excludedFileExtension</span></span> <br/> <span data-ttu-id="8e064-191">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="8e064-191">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="8e064-192">Pfad zu ausgeschlossenen Inhalten</span><span class="sxs-lookup"><span data-stu-id="8e064-192">Path to excluded content</span></span>

<span data-ttu-id="8e064-193">Geben Sie Inhalte an, die nicht durch den vollständigen Dateipfad gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-193">Specify content excluded from being scanned by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-194">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-194">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-195">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-195">**Key**</span></span> | <span data-ttu-id="8e064-196">path</span><span class="sxs-lookup"><span data-stu-id="8e064-196">path</span></span> |
| <span data-ttu-id="8e064-197">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-197">**Data type**</span></span> | <span data-ttu-id="8e064-198">String</span><span class="sxs-lookup"><span data-stu-id="8e064-198">String</span></span> |
| <span data-ttu-id="8e064-199">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-199">**Possible values**</span></span> | <span data-ttu-id="8e064-200">gültige Pfade</span><span class="sxs-lookup"><span data-stu-id="8e064-200">valid paths</span></span> |
| <span data-ttu-id="8e064-201">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-201">**Comments**</span></span> | <span data-ttu-id="8e064-202">Gilt nur, *$type* *ausgeschlossen IstPath*</span><span class="sxs-lookup"><span data-stu-id="8e064-202">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="8e064-203">Pfadtyp (Datei/Verzeichnis)</span><span class="sxs-lookup"><span data-stu-id="8e064-203">Path type (file / directory)</span></span>

<span data-ttu-id="8e064-204">Gibt an, ob *die path-Eigenschaft* auf eine Datei oder ein Verzeichnis verweist.</span><span class="sxs-lookup"><span data-stu-id="8e064-204">Indicate if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="8e064-205">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-205">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-206">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-206">**Key**</span></span> | <span data-ttu-id="8e064-207">isDirectory</span><span class="sxs-lookup"><span data-stu-id="8e064-207">isDirectory</span></span> |
| <span data-ttu-id="8e064-208">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-208">**Data type**</span></span> | <span data-ttu-id="8e064-209">Boolesch</span><span class="sxs-lookup"><span data-stu-id="8e064-209">Boolean</span></span> |
| <span data-ttu-id="8e064-210">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-210">**Possible values**</span></span> | <span data-ttu-id="8e064-211">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="8e064-211">false (default)</span></span> <br/> <span data-ttu-id="8e064-212">true</span><span class="sxs-lookup"><span data-stu-id="8e064-212">true</span></span> |
| <span data-ttu-id="8e064-213">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-213">**Comments**</span></span> | <span data-ttu-id="8e064-214">Gilt nur, *$type* *ausgeschlossen IstPath*</span><span class="sxs-lookup"><span data-stu-id="8e064-214">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="8e064-215">Dateierweiterung, die von der Überprüfung ausgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="8e064-215">File extension excluded from the scan</span></span>

<span data-ttu-id="8e064-216">Geben Sie Inhalte an, die von der Dateierweiterung nicht gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-216">Specify content excluded from being scanned by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-217">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-217">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-218">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-218">**Key**</span></span> | <span data-ttu-id="8e064-219">erweiterung</span><span class="sxs-lookup"><span data-stu-id="8e064-219">extension</span></span> |
| <span data-ttu-id="8e064-220">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-220">**Data type**</span></span> | <span data-ttu-id="8e064-221">String</span><span class="sxs-lookup"><span data-stu-id="8e064-221">String</span></span> |
| <span data-ttu-id="8e064-222">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-222">**Possible values**</span></span> | <span data-ttu-id="8e064-223">Gültige Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="8e064-223">valid file extensions</span></span> |
| <span data-ttu-id="8e064-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-224">**Comments**</span></span> | <span data-ttu-id="8e064-225">Gilt nur, *$type* *ausgeschlossen istFileExtension*</span><span class="sxs-lookup"><span data-stu-id="8e064-225">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="8e064-226">Prozess, der von der Überprüfung ausgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="8e064-226">Process excluded from the scan</span></span>

<span data-ttu-id="8e064-227">Geben Sie einen Prozess an, für den alle Dateiaktivitäten von der Überprüfung ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-227">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="8e064-228">Der Prozess kann entweder durch seinen Namen (z. B. ) oder den vollständigen `cat` Pfad (z. B. ) angegeben werden. `/bin/cat`</span><span class="sxs-lookup"><span data-stu-id="8e064-228">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-229">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-229">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-230">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-230">**Key**</span></span> | <span data-ttu-id="8e064-231">Name</span><span class="sxs-lookup"><span data-stu-id="8e064-231">name</span></span> |
| <span data-ttu-id="8e064-232">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-232">**Data type**</span></span> | <span data-ttu-id="8e064-233">String</span><span class="sxs-lookup"><span data-stu-id="8e064-233">String</span></span> |
| <span data-ttu-id="8e064-234">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-234">**Possible values**</span></span> | <span data-ttu-id="8e064-235">eine beliebige Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8e064-235">any string</span></span> |
| <span data-ttu-id="8e064-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-236">**Comments**</span></span> | <span data-ttu-id="8e064-237">Gilt nur, *$type* *ausgeschlossen istFileName*</span><span class="sxs-lookup"><span data-stu-id="8e064-237">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="8e064-238">Zulässige Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="8e064-238">Allowed threats</span></span>

<span data-ttu-id="8e064-239">Geben Sie Bedrohungen nach Namen an, die nicht von Defender for Endpoint für Mac blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-239">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="8e064-240">Diese Bedrohungen können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-240">These threats will be allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-241">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-241">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-242">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-242">**Key**</span></span> | <span data-ttu-id="8e064-243">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="8e064-243">allowedThreats</span></span> |
| <span data-ttu-id="8e064-244">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-244">**Data type**</span></span> | <span data-ttu-id="8e064-245">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="8e064-245">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="8e064-246">Unzulässige Bedrohungsaktionen</span><span class="sxs-lookup"><span data-stu-id="8e064-246">Disallowed threat actions</span></span>

<span data-ttu-id="8e064-247">Schränkt die Aktionen ein, die der lokale Benutzer eines Geräts ausführen kann, wenn Bedrohungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-247">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="8e064-248">Die in dieser Liste enthaltenen Aktionen werden nicht auf der Benutzeroberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e064-248">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-249">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-250">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-250">**Key**</span></span> | <span data-ttu-id="8e064-251">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="8e064-251">disallowedThreatActions</span></span> |
| <span data-ttu-id="8e064-252">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-252">**Data type**</span></span> | <span data-ttu-id="8e064-253">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="8e064-253">Array of strings</span></span> |
| <span data-ttu-id="8e064-254">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-254">**Possible values**</span></span> | <span data-ttu-id="8e064-255">allow (schränkt ein, dass Benutzer Bedrohungen zulassen)</span><span class="sxs-lookup"><span data-stu-id="8e064-255">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="8e064-256">restore (schränkt benutzer das Wiederherstellen von Bedrohungen aus der Quarantäne ein)</span><span class="sxs-lookup"><span data-stu-id="8e064-256">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="8e064-257">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-257">**Comments**</span></span> | <span data-ttu-id="8e064-258">Verfügbar in Microsoft Defender for Endpoint, Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="8e064-258">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="8e064-259">Einstellungen für den Bedrohungstyp</span><span class="sxs-lookup"><span data-stu-id="8e064-259">Threat type settings</span></span>

<span data-ttu-id="8e064-260">Geben Sie an, wie bestimmte Bedrohungstypen von Microsoft Defender for Endpoint für Mac behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-260">Specify how certain threat types are handled by Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-261">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-261">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-262">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-262">**Key**</span></span> | <span data-ttu-id="8e064-263">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="8e064-263">threatTypeSettings</span></span> |
| <span data-ttu-id="8e064-264">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-264">**Data type**</span></span> | <span data-ttu-id="8e064-265">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="8e064-265">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8e064-266">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-266">**Comments**</span></span> | <span data-ttu-id="8e064-267">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="8e064-267">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="8e064-268">Bedrohungstyp</span><span class="sxs-lookup"><span data-stu-id="8e064-268">Threat type</span></span>

<span data-ttu-id="8e064-269">Geben Sie Bedrohungstypen an.</span><span class="sxs-lookup"><span data-stu-id="8e064-269">Specify threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-270">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-270">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-271">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-271">**Key**</span></span> | <span data-ttu-id="8e064-272">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="8e064-272">key</span></span> |
| <span data-ttu-id="8e064-273">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-273">**Data type**</span></span> | <span data-ttu-id="8e064-274">String</span><span class="sxs-lookup"><span data-stu-id="8e064-274">String</span></span> |
| <span data-ttu-id="8e064-275">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-275">**Possible values**</span></span> | <span data-ttu-id="8e064-276">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="8e064-276">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="8e064-277">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="8e064-277">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="8e064-278">Zu ergreifende Maßnahme</span><span class="sxs-lookup"><span data-stu-id="8e064-278">Action to take</span></span>

<span data-ttu-id="8e064-279">Geben Sie an, welche Aktion ausgeführt werden soll, wenn eine Bedrohung des im vorherigen Abschnitt angegebenen Typs erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="8e064-279">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="8e064-280">Wählen Sie aus den folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="8e064-280">Choose from the following options:</span></span>

- <span data-ttu-id="8e064-281">**Überwachung:** Ihr Gerät ist nicht vor dieser Art von Bedrohung geschützt, aber ein Eintrag über die Bedrohung wird protokolliert.</span><span class="sxs-lookup"><span data-stu-id="8e064-281">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="8e064-282">**Block**: Ihr Gerät ist vor dieser Art von Bedrohung geschützt, und Sie werden über die Benutzeroberfläche und die Sicherheitskonsole benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="8e064-282">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="8e064-283">**Aus**: Ihr Gerät ist nicht vor dieser Art von Bedrohung geschützt, und es wird nichts protokolliert.</span><span class="sxs-lookup"><span data-stu-id="8e064-283">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-284">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-284">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-285">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-285">**Key**</span></span> | <span data-ttu-id="8e064-286">Wert</span><span class="sxs-lookup"><span data-stu-id="8e064-286">value</span></span> |
| <span data-ttu-id="8e064-287">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-287">**Data type**</span></span> | <span data-ttu-id="8e064-288">String</span><span class="sxs-lookup"><span data-stu-id="8e064-288">String</span></span> |
| <span data-ttu-id="8e064-289">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-289">**Possible values**</span></span> | <span data-ttu-id="8e064-290">Überwachung (Standard)</span><span class="sxs-lookup"><span data-stu-id="8e064-290">audit (default)</span></span> <br/> <span data-ttu-id="8e064-291">block</span><span class="sxs-lookup"><span data-stu-id="8e064-291">block</span></span> <br/> <span data-ttu-id="8e064-292">off</span><span class="sxs-lookup"><span data-stu-id="8e064-292">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="8e064-293">Richtlinie zum Zusammenführen von Bedrohungstypeinstellungen</span><span class="sxs-lookup"><span data-stu-id="8e064-293">Threat type settings merge policy</span></span>

<span data-ttu-id="8e064-294">Geben Sie die Seriendruckrichtlinie für Bedrohungstypeinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="8e064-294">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="8e064-295">Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Einstellungen ( ) oder nur vom Administrator definierten Einstellungen `merge` ( ) `admin_only` sein.</span><span class="sxs-lookup"><span data-stu-id="8e064-295">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="8e064-296">Diese Einstellung kann verwendet werden, um lokale Benutzer an der Definition eigener Einstellungen für verschiedene Bedrohungstypen zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="8e064-296">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-297">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-297">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-298">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-298">**Key**</span></span> | <span data-ttu-id="8e064-299">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="8e064-299">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="8e064-300">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-300">**Data type**</span></span> | <span data-ttu-id="8e064-301">String</span><span class="sxs-lookup"><span data-stu-id="8e064-301">String</span></span> |
| <span data-ttu-id="8e064-302">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-302">**Possible values**</span></span> | <span data-ttu-id="8e064-303">merge (Standard)</span><span class="sxs-lookup"><span data-stu-id="8e064-303">merge (default)</span></span> <br/> <span data-ttu-id="8e064-304">admin_only</span><span class="sxs-lookup"><span data-stu-id="8e064-304">admin_only</span></span> |
| <span data-ttu-id="8e064-305">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-305">**Comments**</span></span> | <span data-ttu-id="8e064-306">Verfügbar in Microsoft Defender for Endpoint, Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="8e064-306">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="8e064-307">Aufbewahrung des Antivirusscanverlaufs (in Tagen)</span><span class="sxs-lookup"><span data-stu-id="8e064-307">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="8e064-308">Geben Sie die Anzahl der Tage an, die Ergebnisse im Scanverlauf auf dem Gerät aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-308">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="8e064-309">Alte Scanergebnisse werden aus dem Verlauf entfernt.</span><span class="sxs-lookup"><span data-stu-id="8e064-309">Old scan results are removed from the history.</span></span> <span data-ttu-id="8e064-310">Alte isolierte Dateien, die ebenfalls vom Datenträger entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="8e064-310">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-311">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-311">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-312">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-312">**Key**</span></span> | <span data-ttu-id="8e064-313">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="8e064-313">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="8e064-314">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-314">**Data type**</span></span> | <span data-ttu-id="8e064-315">String</span><span class="sxs-lookup"><span data-stu-id="8e064-315">String</span></span> |
| <span data-ttu-id="8e064-316">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-316">**Possible values**</span></span> | <span data-ttu-id="8e064-317">90 (Standard).</span><span class="sxs-lookup"><span data-stu-id="8e064-317">90 (default).</span></span> <span data-ttu-id="8e064-318">Zulässige Werte liegen zwischen 1 Tag und 180 Tagen.</span><span class="sxs-lookup"><span data-stu-id="8e064-318">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="8e064-319">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-319">**Comments**</span></span> | <span data-ttu-id="8e064-320">Verfügbar in Microsoft Defender for Endpoint, Version 101.07.23 oder höher.</span><span class="sxs-lookup"><span data-stu-id="8e064-320">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="8e064-321">Maximale Anzahl von Elementen im Antivirusscanverlauf</span><span class="sxs-lookup"><span data-stu-id="8e064-321">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="8e064-322">Geben Sie die maximale Anzahl von Einträgen an, die im Scanverlauf bleiben sollen.</span><span class="sxs-lookup"><span data-stu-id="8e064-322">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="8e064-323">Zu den Einträgen gehören alle in der Vergangenheit durchgeführten Bedarfsscans und alle Antivirenerkennungen.</span><span class="sxs-lookup"><span data-stu-id="8e064-323">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-324">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-324">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-325">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-325">**Key**</span></span> | <span data-ttu-id="8e064-326">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="8e064-326">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="8e064-327">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-327">**Data type**</span></span> | <span data-ttu-id="8e064-328">String</span><span class="sxs-lookup"><span data-stu-id="8e064-328">String</span></span> |
| <span data-ttu-id="8e064-329">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-329">**Possible values**</span></span> | <span data-ttu-id="8e064-330">10000 (Standard).</span><span class="sxs-lookup"><span data-stu-id="8e064-330">10000 (default).</span></span> <span data-ttu-id="8e064-331">Zulässige Werte liegen zwischen 5.000 und 15.000 Elementen.</span><span class="sxs-lookup"><span data-stu-id="8e064-331">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="8e064-332">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-332">**Comments**</span></span> | <span data-ttu-id="8e064-333">Verfügbar in Microsoft Defender for Endpoint, Version 101.07.23 oder höher.</span><span class="sxs-lookup"><span data-stu-id="8e064-333">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="8e064-334">Von der Cloud übermittelte Schutzeinstellungen</span><span class="sxs-lookup"><span data-stu-id="8e064-334">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="8e064-335">Konfigurieren Sie die cloudgesteuerten Schutzfunktionen von Microsoft Defender for Endpoint für Mac.</span><span class="sxs-lookup"><span data-stu-id="8e064-335">Configure the cloud-driven protection features of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-336">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-336">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-337">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-337">**Key**</span></span> | <span data-ttu-id="8e064-338">cloudService</span><span class="sxs-lookup"><span data-stu-id="8e064-338">cloudService</span></span> |
| <span data-ttu-id="8e064-339">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-339">**Data type**</span></span> | <span data-ttu-id="8e064-340">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="8e064-340">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8e064-341">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-341">**Comments**</span></span> | <span data-ttu-id="8e064-342">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="8e064-342">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="8e064-343">Aktivieren/Deaktivieren des in der Cloud übermittelten Schutzes</span><span class="sxs-lookup"><span data-stu-id="8e064-343">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="8e064-344">Geben Sie an, ob der in der Cloud zugestellte Schutz auf dem Gerät aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8e064-344">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="8e064-345">Um die Sicherheit Ihrer Dienste zu verbessern, wird empfohlen, dieses Feature aktiviert zu halten.</span><span class="sxs-lookup"><span data-stu-id="8e064-345">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-346">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-346">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-347">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-347">**Key**</span></span> | <span data-ttu-id="8e064-348">aktiviert</span><span class="sxs-lookup"><span data-stu-id="8e064-348">enabled</span></span> |
| <span data-ttu-id="8e064-349">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-349">**Data type**</span></span> | <span data-ttu-id="8e064-350">Boolesch</span><span class="sxs-lookup"><span data-stu-id="8e064-350">Boolean</span></span> |
| <span data-ttu-id="8e064-351">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-351">**Possible values**</span></span> | <span data-ttu-id="8e064-352">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="8e064-352">true (default)</span></span> <br/> <span data-ttu-id="8e064-353">false</span><span class="sxs-lookup"><span data-stu-id="8e064-353">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="8e064-354">Diagnosesammlungsebene</span><span class="sxs-lookup"><span data-stu-id="8e064-354">Diagnostic collection level</span></span>

<span data-ttu-id="8e064-355">Diagnosedaten werden verwendet, um Microsoft Defender for Endpoint sicher und auf dem neuesten Stand zu halten, Probleme zu erkennen, zu diagnostizieren und zu beheben sowie Produktverbesserungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="8e064-355">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="8e064-356">Diese Einstellung bestimmt die Diagnosestufe, die von Microsoft Defender for Endpoint an Microsoft gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="8e064-356">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-357">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-357">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-358">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-358">**Key**</span></span> | <span data-ttu-id="8e064-359">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="8e064-359">diagnosticLevel</span></span> |
| <span data-ttu-id="8e064-360">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-360">**Data type**</span></span> | <span data-ttu-id="8e064-361">String</span><span class="sxs-lookup"><span data-stu-id="8e064-361">String</span></span> |
| <span data-ttu-id="8e064-362">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-362">**Possible values**</span></span> | <span data-ttu-id="8e064-363">optional (Standard)</span><span class="sxs-lookup"><span data-stu-id="8e064-363">optional (default)</span></span> <br/> <span data-ttu-id="8e064-364">erforderlich</span><span class="sxs-lookup"><span data-stu-id="8e064-364">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="8e064-365">Aktivieren/Deaktivieren automatischer Beispielübermittlungen</span><span class="sxs-lookup"><span data-stu-id="8e064-365">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="8e064-366">Bestimmt, ob verdächtige Beispiele (die wahrscheinlich Bedrohungen enthalten) an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-366">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="8e064-367">Sie werden aufgefordert, wenn die übermittelte Datei wahrscheinlich personenbezogene Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="8e064-367">You are prompted if the submitted file is likely to contain personal information.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-368">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-368">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-369">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-369">**Key**</span></span> | <span data-ttu-id="8e064-370">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="8e064-370">automaticSampleSubmission</span></span> |
| <span data-ttu-id="8e064-371">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-371">**Data type**</span></span> | <span data-ttu-id="8e064-372">Boolesch</span><span class="sxs-lookup"><span data-stu-id="8e064-372">Boolean</span></span> |
| <span data-ttu-id="8e064-373">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-373">**Possible values**</span></span> | <span data-ttu-id="8e064-374">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="8e064-374">true (default)</span></span> <br/> <span data-ttu-id="8e064-375">false</span><span class="sxs-lookup"><span data-stu-id="8e064-375">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="8e064-376">Aktivieren/Deaktivieren automatischer Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="8e064-376">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="8e064-377">Bestimmt, ob Sicherheitsintelligenzupdates automatisch installiert werden:</span><span class="sxs-lookup"><span data-stu-id="8e064-377">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-378">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-378">**Key**</span></span> | <span data-ttu-id="8e064-379">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="8e064-379">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="8e064-380">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-380">**Data type**</span></span> | <span data-ttu-id="8e064-381">Boolesch</span><span class="sxs-lookup"><span data-stu-id="8e064-381">Boolean</span></span> |
| <span data-ttu-id="8e064-382">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-382">**Possible values**</span></span> | <span data-ttu-id="8e064-383">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="8e064-383">true (default)</span></span> <br/> <span data-ttu-id="8e064-384">false</span><span class="sxs-lookup"><span data-stu-id="8e064-384">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="8e064-385">Benutzeroberflächeneinstellungen</span><span class="sxs-lookup"><span data-stu-id="8e064-385">User interface preferences</span></span>

<span data-ttu-id="8e064-386">Verwalten Sie die Einstellungen für die Benutzeroberfläche von Microsoft Defender for Endpoint für Mac.</span><span class="sxs-lookup"><span data-stu-id="8e064-386">Manage the preferences for the user interface of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-387">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-387">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-388">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-388">**Key**</span></span> | <span data-ttu-id="8e064-389">userInterface</span><span class="sxs-lookup"><span data-stu-id="8e064-389">userInterface</span></span> |
| <span data-ttu-id="8e064-390">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-390">**Data type**</span></span> | <span data-ttu-id="8e064-391">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="8e064-391">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8e064-392">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-392">**Comments**</span></span> | <span data-ttu-id="8e064-393">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="8e064-393">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="8e064-394">Symbol für Das Menü "Status anzeigen/ausblenden"</span><span class="sxs-lookup"><span data-stu-id="8e064-394">Show / hide status menu icon</span></span>

<span data-ttu-id="8e064-395">Geben Sie an, ob das Statusmenüsymbol in der oberen rechten Ecke des Bildschirms ein- oder ausgeblendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8e064-395">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-396">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-396">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-397">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-397">**Key**</span></span> | <span data-ttu-id="8e064-398">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="8e064-398">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="8e064-399">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-399">**Data type**</span></span> | <span data-ttu-id="8e064-400">Boolesch</span><span class="sxs-lookup"><span data-stu-id="8e064-400">Boolean</span></span> |
| <span data-ttu-id="8e064-401">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-401">**Possible values**</span></span> | <span data-ttu-id="8e064-402">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="8e064-402">false (default)</span></span> <br/> <span data-ttu-id="8e064-403">true</span><span class="sxs-lookup"><span data-stu-id="8e064-403">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="8e064-404">Ein-/Ausblenden der Option zum Senden von Feedback</span><span class="sxs-lookup"><span data-stu-id="8e064-404">Show / hide option to send feedback</span></span>

<span data-ttu-id="8e064-405">Geben Sie an, ob Benutzer Feedback an Microsoft senden können, indem Sie zu `Help`  >  `Send Feedback` gehen.</span><span class="sxs-lookup"><span data-stu-id="8e064-405">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-406">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-406">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-407">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-407">**Key**</span></span> | <span data-ttu-id="8e064-408">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="8e064-408">userInitiatedFeedback</span></span> |
| <span data-ttu-id="8e064-409">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-409">**Data type**</span></span> | <span data-ttu-id="8e064-410">String</span><span class="sxs-lookup"><span data-stu-id="8e064-410">String</span></span> |
| <span data-ttu-id="8e064-411">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-411">**Possible values**</span></span> | <span data-ttu-id="8e064-412">aktiviert (Standard)</span><span class="sxs-lookup"><span data-stu-id="8e064-412">enabled (default)</span></span> <br/> <span data-ttu-id="8e064-413">deaktiviert</span><span class="sxs-lookup"><span data-stu-id="8e064-413">disabled</span></span> |
| <span data-ttu-id="8e064-414">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-414">**Comments**</span></span> | <span data-ttu-id="8e064-415">Verfügbar in Microsoft Defender for Endpoint, Version 101.19.61 oder höher.</span><span class="sxs-lookup"><span data-stu-id="8e064-415">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="8e064-416">Einstellungen für endpunkterkennung und -reaktion</span><span class="sxs-lookup"><span data-stu-id="8e064-416">Endpoint detection and response preferences</span></span>

<span data-ttu-id="8e064-417">Verwalten Sie die Einstellungen der Endpunkterkennungs- und -antwortkomponente (EDR) von Microsoft Defender for Endpoint für Mac.</span><span class="sxs-lookup"><span data-stu-id="8e064-417">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-418">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-418">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-419">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-419">**Key**</span></span> | <span data-ttu-id="8e064-420">edr</span><span class="sxs-lookup"><span data-stu-id="8e064-420">edr</span></span> |
| <span data-ttu-id="8e064-421">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-421">**Data type**</span></span> | <span data-ttu-id="8e064-422">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="8e064-422">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8e064-423">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-423">**Comments**</span></span> | <span data-ttu-id="8e064-424">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="8e064-424">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="8e064-425">Gerätetags</span><span class="sxs-lookup"><span data-stu-id="8e064-425">Device tags</span></span>

<span data-ttu-id="8e064-426">Geben Sie einen Tagnamen und dessen Wert an.</span><span class="sxs-lookup"><span data-stu-id="8e064-426">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="8e064-427">Das GROUP-Tag tagt das Gerät mit dem angegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="8e064-427">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="8e064-428">Das Tag wird im Portal unter der Geräteseite angezeigt und kann zum Filtern und Gruppieren von Geräten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-428">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-429">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-429">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-430">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-430">**Key**</span></span> | <span data-ttu-id="8e064-431">tags</span><span class="sxs-lookup"><span data-stu-id="8e064-431">tags</span></span> |
| <span data-ttu-id="8e064-432">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-432">**Data type**</span></span> | <span data-ttu-id="8e064-433">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="8e064-433">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8e064-434">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8e064-434">**Comments**</span></span> | <span data-ttu-id="8e064-435">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="8e064-435">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="8e064-436">Tagtyp</span><span class="sxs-lookup"><span data-stu-id="8e064-436">Type of tag</span></span>

<span data-ttu-id="8e064-437">Gibt den Typ des Tags an.</span><span class="sxs-lookup"><span data-stu-id="8e064-437">Specifies the type of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-438">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-438">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-439">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-439">**Key**</span></span> | <span data-ttu-id="8e064-440">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="8e064-440">key</span></span> |
| <span data-ttu-id="8e064-441">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-441">**Data type**</span></span> | <span data-ttu-id="8e064-442">String</span><span class="sxs-lookup"><span data-stu-id="8e064-442">String</span></span> |
| <span data-ttu-id="8e064-443">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-443">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="8e064-444">Wert des Tags</span><span class="sxs-lookup"><span data-stu-id="8e064-444">Value of tag</span></span>

<span data-ttu-id="8e064-445">Gibt den Wert des Tags an.</span><span class="sxs-lookup"><span data-stu-id="8e064-445">Specifies the value of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="8e064-446">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="8e064-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8e064-447">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8e064-447">**Key**</span></span> | <span data-ttu-id="8e064-448">Wert</span><span class="sxs-lookup"><span data-stu-id="8e064-448">value</span></span> |
| <span data-ttu-id="8e064-449">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8e064-449">**Data type**</span></span> | <span data-ttu-id="8e064-450">String</span><span class="sxs-lookup"><span data-stu-id="8e064-450">String</span></span> |
| <span data-ttu-id="8e064-451">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="8e064-451">**Possible values**</span></span> | <span data-ttu-id="8e064-452">eine beliebige Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8e064-452">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="8e064-453">Pro Tagtyp kann nur ein Wert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-453">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="8e064-454">Der Typ von Tags ist eindeutig und sollte nicht im gleichen Konfigurationsprofil wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="8e064-454">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="8e064-455">Empfohlenes Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="8e064-455">Recommended configuration profile</span></span>

<span data-ttu-id="8e064-456">Für die ersten Schritte empfehlen wir die folgende Konfiguration für Ihr Unternehmen, um alle Von Microsoft Defender for Endpoint-Funktionen zur Nutzung zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="8e064-456">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="8e064-457">Das folgende Konfigurationsprofil (oder im Fall von JAMF eine Eigenschaftenliste, die in das Konfigurationsprofil für benutzerdefinierte Einstellungen hochgeladen werden könnte) wird verwendet:</span><span class="sxs-lookup"><span data-stu-id="8e064-457">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="8e064-458">Aktivieren des Echtzeitschutzes (Real-Time Protection, RTP)</span><span class="sxs-lookup"><span data-stu-id="8e064-458">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="8e064-459">Geben Sie an, wie die folgenden Bedrohungstypen behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="8e064-459">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="8e064-460">**Potenziell unerwünschte Anwendungen (PUA)** werden blockiert</span><span class="sxs-lookup"><span data-stu-id="8e064-460">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="8e064-461">**Archivangriffe** (Datei mit hoher Komprimierungsrate) werden bei Microsoft Defender für Endpunktprotokolle überwacht.</span><span class="sxs-lookup"><span data-stu-id="8e064-461">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="8e064-462">Aktivieren automatischer Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="8e064-462">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="8e064-463">Aktivieren des in der Cloud übermittelten Schutzes</span><span class="sxs-lookup"><span data-stu-id="8e064-463">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="8e064-464">Aktivieren der automatischen Beispielübermittlung</span><span class="sxs-lookup"><span data-stu-id="8e064-464">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="8e064-465">Eigenschaftenliste für das JAMF-Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="8e064-465">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="8e064-466">Intune-Profil</span><span class="sxs-lookup"><span data-stu-id="8e064-466">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="8e064-467">Beispiel für ein vollständiges Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="8e064-467">Full configuration profile example</span></span>

<span data-ttu-id="8e064-468">Die folgenden Vorlagen enthalten Einträge für alle in diesem Dokument beschriebenen Einstellungen und können für erweiterte Szenarien verwendet werden, in denen Sie mehr Kontrolle über Microsoft Defender for Endpoint für Mac wünschen.</span><span class="sxs-lookup"><span data-stu-id="8e064-468">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="8e064-469">Eigenschaftenliste für das JAMF-Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="8e064-469">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="8e064-470">Intune-Profil</span><span class="sxs-lookup"><span data-stu-id="8e064-470">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="8e064-471">Eigenschaftenlistenüberprüfung</span><span class="sxs-lookup"><span data-stu-id="8e064-471">Property list validation</span></span>

<span data-ttu-id="8e064-472">Die Eigenschaftenliste muss eine gültige *.plist-Datei* sein.</span><span class="sxs-lookup"><span data-stu-id="8e064-472">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="8e064-473">Dies kann durch Ausführen von:</span><span class="sxs-lookup"><span data-stu-id="8e064-473">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="8e064-474">Wenn die Datei wohlgeformt ist, wird mit dem obigen Befehl der `OK` Exitcode ausgegeben und `0` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8e064-474">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="8e064-475">Andernfalls wird ein Fehler angezeigt, der das Problem beschreibt, und der Befehl gibt den Exitcode von `1` zurück.</span><span class="sxs-lookup"><span data-stu-id="8e064-475">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="8e064-476">Konfigurationsprofilbereitstellung</span><span class="sxs-lookup"><span data-stu-id="8e064-476">Configuration profile deployment</span></span>

<span data-ttu-id="8e064-477">Nachdem Sie das Konfigurationsprofil für Ihr Unternehmen erstellt haben, können Sie es über die Verwaltungskonsole bereitstellen, die Ihr Unternehmen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8e064-477">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="8e064-478">In den folgenden Abschnitten finden Sie Anweisungen zum Bereitstellen dieses Profils mithilfe von JAMF und Intune.</span><span class="sxs-lookup"><span data-stu-id="8e064-478">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="8e064-479">JAMF-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="8e064-479">JAMF deployment</span></span>

<span data-ttu-id="8e064-480">Öffnen Sie in der JAMF-Konsole  >  **Computerkonfigurationsprofile,** navigieren Sie zu dem Konfigurationsprofil, das Sie verwenden möchten, und wählen Sie dann **Benutzerdefinierte Einstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="8e064-480">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="8e064-481">Erstellen Sie einen Eintrag `com.microsoft.wdav` mit als Einstellungsdomäne, und laden Sie die zuvor produzierte *.plist* hoch.</span><span class="sxs-lookup"><span data-stu-id="8e064-481">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="8e064-482">Sie müssen die richtige Einstellungsdomäne eingeben ( ); andernfalls werden die Einstellungen von `com.microsoft.wdav` Microsoft Defender for Endpoint nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="8e064-482">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="8e064-483">Intune-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="8e064-483">Intune deployment</span></span>

1. <span data-ttu-id="8e064-484">Öffnen **Sie**  >  **Gerätekonfiguration verwalten**.</span><span class="sxs-lookup"><span data-stu-id="8e064-484">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="8e064-485">Wählen **Sie Profil** erstellen von  >    >  **Profilen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="8e064-485">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="8e064-486">Wählen Sie einen Namen für das Profil aus.</span><span class="sxs-lookup"><span data-stu-id="8e064-486">Choose a name for the profile.</span></span> <span data-ttu-id="8e064-487">Ändern **sie Platform=macOS** in **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="8e064-487">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="8e064-488">Wählen Sie Konfigurieren aus.</span><span class="sxs-lookup"><span data-stu-id="8e064-488">Select Configure.</span></span>

3. <span data-ttu-id="8e064-489">Speichern Sie die .plist, die zuvor als erstellt `com.microsoft.wdav.xml` wurde.</span><span class="sxs-lookup"><span data-stu-id="8e064-489">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="8e064-490">Geben `com.microsoft.wdav` Sie als **benutzerdefinierter Konfigurationsprofilname ein.**</span><span class="sxs-lookup"><span data-stu-id="8e064-490">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="8e064-491">Öffnen Sie das Konfigurationsprofil, und laden Sie die Datei `com.microsoft.wdav.xml` hoch.</span><span class="sxs-lookup"><span data-stu-id="8e064-491">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="8e064-492">(Diese Datei wurde in Schritt 3 erstellt.)</span><span class="sxs-lookup"><span data-stu-id="8e064-492">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="8e064-493">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="8e064-493">Select **OK**.</span></span>

7. <span data-ttu-id="8e064-494">Wählen **Sie**  >  **Zuordnungen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="8e064-494">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="8e064-495">Wählen Sie **auf** der Registerkarte Include die Option **Allen Benutzern & Alle Geräte zuweisen aus.**</span><span class="sxs-lookup"><span data-stu-id="8e064-495">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="8e064-496">Sie müssen den richtigen namen des benutzerdefinierten Konfigurationsprofils eingeben. Andernfalls werden diese Einstellungen von Microsoft Defender for Endpoint nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="8e064-496">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="8e064-497">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="8e064-497">Resources</span></span>

- [<span data-ttu-id="8e064-498">Konfigurationsprofilreferenz (Apple-Entwicklerdokumentationen)</span><span class="sxs-lookup"><span data-stu-id="8e064-498">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
