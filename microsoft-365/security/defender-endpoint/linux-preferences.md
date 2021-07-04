---
title: Festlegen von Einstellungen für Microsoft Defender für Endpunkt unter Linux
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter Linux in Unternehmen konfiguriert wird.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Linux, Installation, bereitstellen, Deinstallation, entinstallation, ansible, linux, redhat, ubuntu, git, sles, suse, centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7998e878ad03fdfb64c314dc8b7234ece46164ce
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289487"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="32a89-104">Festlegen von Einstellungen für Microsoft Defender für Endpunkt unter Linux</span><span class="sxs-lookup"><span data-stu-id="32a89-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="32a89-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="32a89-105">**Applies to:**</span></span>
- [<span data-ttu-id="32a89-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="32a89-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="32a89-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="32a89-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="32a89-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="32a89-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="32a89-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="32a89-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="32a89-110">Dieses Thema enthält Anweisungen zum Festlegen von Einstellungen für Defender für Endpunkt unter Linux in Unternehmensumgebungen.</span><span class="sxs-lookup"><span data-stu-id="32a89-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="32a89-111">Wenn Sie an der Konfiguration des Produkts auf einem Gerät über die Befehlszeile interessiert sind, finden Sie weitere Informationen unter ["Ressourcen".](linux-resources.md#configure-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="32a89-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="32a89-112">In Unternehmensumgebungen kann Defender für Endpunkt unter Linux über ein Konfigurationsprofil verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="32a89-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="32a89-113">Dieses Profil wird über das Verwaltungstool Ihrer Wahl bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="32a89-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="32a89-114">Vom Unternehmen verwaltete Einstellungen haben Vorrang vor den Einstellungen, die lokal auf dem Gerät festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="32a89-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="32a89-115">Mit anderen Worten: Benutzer in Ihrem Unternehmen können keine Einstellungen ändern, die über dieses Konfigurationsprofil festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="32a89-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="32a89-116">In diesem Artikel werden die Struktur dieses Profils (einschließlich eines empfohlenen Profils, das Sie für die ersten Schritte verwenden können) und Anweisungen zum Bereitstellen des Profils beschrieben.</span><span class="sxs-lookup"><span data-stu-id="32a89-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="32a89-117">Konfigurationsprofilstruktur</span><span class="sxs-lookup"><span data-stu-id="32a89-117">Configuration profile structure</span></span>

<span data-ttu-id="32a89-118">Das Konfigurationsprofil ist eine JSON-Datei, die aus Einträgen besteht, die durch einen Schlüssel identifiziert werden (der den Namen der Einstellung angibt), gefolgt von einem Wert, der von der Art der Einstellung abhängt.</span><span class="sxs-lookup"><span data-stu-id="32a89-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="32a89-119">Werte können einfach sein, z. B. ein numerischer Wert, oder komplex sein, z. B. eine geschachtelte Liste von Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="32a89-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="32a89-120">In der Regel verwenden Sie ein Konfigurationsverwaltungstool, um eine Datei mit dem Namen am Speicherort zu ```mdatp_managed.json``` ```/etc/opt/microsoft/mdatp/managed/``` übertragen.</span><span class="sxs-lookup"><span data-stu-id="32a89-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="32a89-121">Die oberste Ebene des Konfigurationsprofils enthält produktweite Einstellungen und Einträge für Unterbereiche des Produkts, die in den nächsten Abschnitten ausführlicher erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="32a89-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="32a89-122">Einstellungen des Antivirusmoduls</span><span class="sxs-lookup"><span data-stu-id="32a89-122">Antivirus engine preferences</span></span>

<span data-ttu-id="32a89-123">Der Abschnitt *"antivirusEngine"* des Konfigurationsprofils wird verwendet, um die Einstellungen der Antivirenkomponente des Produkts zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="32a89-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

<br>

****

|<span data-ttu-id="32a89-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-124">Description</span></span>|<span data-ttu-id="32a89-125">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-125">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-126">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-126">**Key**</span></span>|<span data-ttu-id="32a89-127">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="32a89-127">antivirusEngine</span></span>|
|<span data-ttu-id="32a89-128">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-128">**Data type**</span></span>|<span data-ttu-id="32a89-129">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="32a89-129">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="32a89-130">**Comments**</span><span class="sxs-lookup"><span data-stu-id="32a89-130">**Comments**</span></span>|<span data-ttu-id="32a89-131">Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="32a89-131">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="32a89-132">Aktivieren/Deaktivieren des Echtzeitschutzes</span><span class="sxs-lookup"><span data-stu-id="32a89-132">Enable / disable real-time protection</span></span>

<span data-ttu-id="32a89-133">Bestimmt, ob der Echtzeitschutz (Beim Zugriff auf Dateien scannen) aktiviert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="32a89-133">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

<br>

****

|<span data-ttu-id="32a89-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-134">Description</span></span>|<span data-ttu-id="32a89-135">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-135">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-136">**Key**</span></span>|<span data-ttu-id="32a89-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="32a89-137">enableRealTimeProtection</span></span>|
|<span data-ttu-id="32a89-138">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-138">**Data type**</span></span>|<span data-ttu-id="32a89-139">Boolesch</span><span class="sxs-lookup"><span data-stu-id="32a89-139">Boolean</span></span>|
|<span data-ttu-id="32a89-140">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-140">**Possible values**</span></span>|<span data-ttu-id="32a89-141">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="32a89-141">true (default)</span></span> <p> <span data-ttu-id="32a89-142">false</span><span class="sxs-lookup"><span data-stu-id="32a89-142">false</span></span>|
|

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="32a89-143">Aktivieren/Deaktivieren des passiven Modus</span><span class="sxs-lookup"><span data-stu-id="32a89-143">Enable / disable passive mode</span></span>

<span data-ttu-id="32a89-144">Bestimmt, ob das Antivirenmodul im passiven Modus ausgeführt wird oder nicht.</span><span class="sxs-lookup"><span data-stu-id="32a89-144">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="32a89-145">Im passiven Modus:</span><span class="sxs-lookup"><span data-stu-id="32a89-145">In passive mode:</span></span>

- <span data-ttu-id="32a89-146">Der Echtzeitschutz ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="32a89-146">Real-time protection is turned off.</span></span>
- <span data-ttu-id="32a89-147">On-Demand-Überprüfung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="32a89-147">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="32a89-148">Die automatische Bedrohungsbehebung ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="32a89-148">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="32a89-149">Sicherheitsupdates sind aktiviert.</span><span class="sxs-lookup"><span data-stu-id="32a89-149">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="32a89-150">Das Statusmenüsymbol ist ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="32a89-150">Status menu icon is hidden.</span></span>

<br>

****

|<span data-ttu-id="32a89-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-151">Description</span></span>|<span data-ttu-id="32a89-152">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-152">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-153">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-153">**Key**</span></span>|<span data-ttu-id="32a89-154">passiveMode</span><span class="sxs-lookup"><span data-stu-id="32a89-154">passiveMode</span></span>|
|<span data-ttu-id="32a89-155">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-155">**Data type**</span></span>|<span data-ttu-id="32a89-156">Boolesch</span><span class="sxs-lookup"><span data-stu-id="32a89-156">Boolean</span></span>|
|<span data-ttu-id="32a89-157">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-157">**Possible values**</span></span>|<span data-ttu-id="32a89-158">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="32a89-158">false (default)</span></span> <p> <span data-ttu-id="32a89-159">true</span><span class="sxs-lookup"><span data-stu-id="32a89-159">true</span></span>|
|<span data-ttu-id="32a89-160">**Comments**</span><span class="sxs-lookup"><span data-stu-id="32a89-160">**Comments**</span></span>|<span data-ttu-id="32a89-161">Verfügbar in Defender für Endpunkt Version 100.67.60 oder höher.</span><span class="sxs-lookup"><span data-stu-id="32a89-161">Available in Defender for Endpoint version 100.67.60 or higher.</span></span>|
|

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="32a89-162">Richtlinie zum Zusammenführen von Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="32a89-162">Exclusion merge policy</span></span>

<span data-ttu-id="32a89-163">Gibt die Zusammenführungsrichtlinie für Ausschlüsse an.</span><span class="sxs-lookup"><span data-stu-id="32a89-163">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="32a89-164">Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Ausschlüssen ( `merge` ) oder nur von einem Administrator definierten Ausschlüssen ( ) `admin_only` sein.</span><span class="sxs-lookup"><span data-stu-id="32a89-164">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="32a89-165">Diese Einstellung kann verwendet werden, um lokale Benutzer daran zu hindern, ihre eigenen Ausschlüsse zu definieren.</span><span class="sxs-lookup"><span data-stu-id="32a89-165">This setting can be used to restrict local users from defining their own exclusions.</span></span>

<br>

****

|<span data-ttu-id="32a89-166">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-166">Description</span></span>|<span data-ttu-id="32a89-167">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-167">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-168">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-168">**Key**</span></span>|<span data-ttu-id="32a89-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="32a89-169">exclusionsMergePolicy</span></span>|
|<span data-ttu-id="32a89-170">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-170">**Data type**</span></span>|<span data-ttu-id="32a89-171">String</span><span class="sxs-lookup"><span data-stu-id="32a89-171">String</span></span>|
|<span data-ttu-id="32a89-172">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-172">**Possible values**</span></span>|<span data-ttu-id="32a89-173">Zusammenführen (Standard)</span><span class="sxs-lookup"><span data-stu-id="32a89-173">merge (default)</span></span> <p> <span data-ttu-id="32a89-174">admin_only</span><span class="sxs-lookup"><span data-stu-id="32a89-174">admin_only</span></span>|
|<span data-ttu-id="32a89-175">**Comments**</span><span class="sxs-lookup"><span data-stu-id="32a89-175">**Comments**</span></span>|<span data-ttu-id="32a89-176">Verfügbar in Defender für Endpunkt Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="32a89-176">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="scan-exclusions"></a><span data-ttu-id="32a89-177">Scanausschlüsse</span><span class="sxs-lookup"><span data-stu-id="32a89-177">Scan exclusions</span></span>

<span data-ttu-id="32a89-178">Entitäten, die von der Überprüfung ausgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="32a89-178">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="32a89-179">Ausschlüsse können durch vollständige Pfade, Erweiterungen oder Dateinamen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="32a89-179">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="32a89-180">(Ausschlüsse werden als Array von Elementen angegeben, der Administrator kann beliebig viele Elemente angeben.)</span><span class="sxs-lookup"><span data-stu-id="32a89-180">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

<br>

****

|<span data-ttu-id="32a89-181">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-181">Description</span></span>|<span data-ttu-id="32a89-182">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-182">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-183">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-183">**Key**</span></span>|<span data-ttu-id="32a89-184">Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="32a89-184">exclusions</span></span>|
|<span data-ttu-id="32a89-185">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-185">**Data type**</span></span>|<span data-ttu-id="32a89-186">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="32a89-186">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="32a89-187">**Comments**</span><span class="sxs-lookup"><span data-stu-id="32a89-187">**Comments**</span></span>|<span data-ttu-id="32a89-188">Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="32a89-188">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="type-of-exclusion"></a><span data-ttu-id="32a89-189">Art des Ausschlusses</span><span class="sxs-lookup"><span data-stu-id="32a89-189">Type of exclusion</span></span>

<span data-ttu-id="32a89-190">Gibt den Vom Scan ausgeschlossenen Inhaltstyp an.</span><span class="sxs-lookup"><span data-stu-id="32a89-190">Specifies the type of content excluded from the scan.</span></span>

<br>

****

|<span data-ttu-id="32a89-191">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-191">Description</span></span>|<span data-ttu-id="32a89-192">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-192">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-193">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-193">**Key**</span></span>|<span data-ttu-id="32a89-194">$type</span><span class="sxs-lookup"><span data-stu-id="32a89-194">$type</span></span>|
|<span data-ttu-id="32a89-195">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-195">**Data type**</span></span>|<span data-ttu-id="32a89-196">String</span><span class="sxs-lookup"><span data-stu-id="32a89-196">String</span></span>|
|<span data-ttu-id="32a89-197">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-197">**Possible values**</span></span>|<span data-ttu-id="32a89-198">excludedPath</span><span class="sxs-lookup"><span data-stu-id="32a89-198">excludedPath</span></span> <p> <span data-ttu-id="32a89-199">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="32a89-199">excludedFileExtension</span></span> <p> <span data-ttu-id="32a89-200">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="32a89-200">excludedFileName</span></span>|
|

##### <a name="path-to-excluded-content"></a><span data-ttu-id="32a89-201">Pfad zu ausgeschlossenen Inhalten</span><span class="sxs-lookup"><span data-stu-id="32a89-201">Path to excluded content</span></span>

<span data-ttu-id="32a89-202">Wird verwendet, um Inhalte vom Scan nach vollständigem Dateipfad auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="32a89-202">Used to exclude content from the scan by full file path.</span></span>

<br>

****

|<span data-ttu-id="32a89-203">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-203">Description</span></span>|<span data-ttu-id="32a89-204">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-204">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-205">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-205">**Key**</span></span>|<span data-ttu-id="32a89-206">path</span><span class="sxs-lookup"><span data-stu-id="32a89-206">path</span></span>|
|<span data-ttu-id="32a89-207">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-207">**Data type**</span></span>|<span data-ttu-id="32a89-208">String</span><span class="sxs-lookup"><span data-stu-id="32a89-208">String</span></span>|
|<span data-ttu-id="32a89-209">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-209">**Possible values**</span></span>|<span data-ttu-id="32a89-210">Gültige Pfade</span><span class="sxs-lookup"><span data-stu-id="32a89-210">valid paths</span></span>|
|<span data-ttu-id="32a89-211">**Comments**</span><span class="sxs-lookup"><span data-stu-id="32a89-211">**Comments**</span></span>|<span data-ttu-id="32a89-212">Gilt nur, wenn *$type* *ausgeschlossen IstPath*</span><span class="sxs-lookup"><span data-stu-id="32a89-212">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="path-type-file--directory"></a><span data-ttu-id="32a89-213">Pfadtyp (Datei/Verzeichnis)</span><span class="sxs-lookup"><span data-stu-id="32a89-213">Path type (file / directory)</span></span>

<span data-ttu-id="32a89-214">Gibt an, ob die *Pfadeigenschaft* auf eine Datei oder ein Verzeichnis verweist.</span><span class="sxs-lookup"><span data-stu-id="32a89-214">Indicates if the *path* property refers to a file or directory.</span></span>

<br>

****

|<span data-ttu-id="32a89-215">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-215">Description</span></span>|<span data-ttu-id="32a89-216">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-216">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-217">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-217">**Key**</span></span>|<span data-ttu-id="32a89-218">Isdirectory</span><span class="sxs-lookup"><span data-stu-id="32a89-218">isDirectory</span></span>|
|<span data-ttu-id="32a89-219">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-219">**Data type**</span></span>|<span data-ttu-id="32a89-220">Boolesch</span><span class="sxs-lookup"><span data-stu-id="32a89-220">Boolean</span></span>|
|<span data-ttu-id="32a89-221">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-221">**Possible values**</span></span>|<span data-ttu-id="32a89-222">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="32a89-222">false (default)</span></span> <p> <span data-ttu-id="32a89-223">true</span><span class="sxs-lookup"><span data-stu-id="32a89-223">true</span></span>|
|<span data-ttu-id="32a89-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="32a89-224">**Comments**</span></span>|<span data-ttu-id="32a89-225">Gilt nur, wenn *$type* *ausgeschlossen IstPath*</span><span class="sxs-lookup"><span data-stu-id="32a89-225">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="32a89-226">Dateierweiterung, die von der Überprüfung ausgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="32a89-226">File extension excluded from the scan</span></span>

<span data-ttu-id="32a89-227">Wird verwendet, um Inhalte von der Überprüfung mithilfe der Dateierweiterung auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="32a89-227">Used to exclude content from the scan by file extension.</span></span>

<br>

****

|<span data-ttu-id="32a89-228">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-228">Description</span></span>|<span data-ttu-id="32a89-229">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-229">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-230">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-230">**Key**</span></span>|<span data-ttu-id="32a89-231">Erweiterung</span><span class="sxs-lookup"><span data-stu-id="32a89-231">extension</span></span>|
|<span data-ttu-id="32a89-232">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-232">**Data type**</span></span>|<span data-ttu-id="32a89-233">String</span><span class="sxs-lookup"><span data-stu-id="32a89-233">String</span></span>|
|<span data-ttu-id="32a89-234">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-234">**Possible values**</span></span>|<span data-ttu-id="32a89-235">gültige Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="32a89-235">valid file extensions</span></span>|
|<span data-ttu-id="32a89-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="32a89-236">**Comments**</span></span>|<span data-ttu-id="32a89-237">Gilt nur, wenn *$type* *ausgeschlossen istFileExtension*</span><span class="sxs-lookup"><span data-stu-id="32a89-237">Applicable only if *$type* is *excludedFileExtension*</span></span>|
|

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="32a89-238">Vom Scan ausgeschlossener Prozess\*</span><span class="sxs-lookup"><span data-stu-id="32a89-238">Process excluded from the scan\*</span></span>

<span data-ttu-id="32a89-239">Gibt einen Prozess an, für den alle Dateiaktivitäten von der Überprüfung ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="32a89-239">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="32a89-240">Der Prozess kann entweder durch seinen Namen (z. `cat` B. ) oder durch den vollständigen Pfad (z. B. ) angegeben `/bin/cat` werden.</span><span class="sxs-lookup"><span data-stu-id="32a89-240">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

<br>

****

|<span data-ttu-id="32a89-241">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-241">Description</span></span>|<span data-ttu-id="32a89-242">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-242">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-243">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-243">**Key**</span></span>|<span data-ttu-id="32a89-244">name</span><span class="sxs-lookup"><span data-stu-id="32a89-244">name</span></span>|
|<span data-ttu-id="32a89-245">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-245">**Data type**</span></span>|<span data-ttu-id="32a89-246">String</span><span class="sxs-lookup"><span data-stu-id="32a89-246">String</span></span>|
|<span data-ttu-id="32a89-247">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-247">**Possible values**</span></span>|<span data-ttu-id="32a89-248">Eine beliebige Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="32a89-248">any string</span></span>|
|<span data-ttu-id="32a89-249">**Comments**</span><span class="sxs-lookup"><span data-stu-id="32a89-249">**Comments**</span></span>|<span data-ttu-id="32a89-250">Gilt nur, wenn *$type* *ausgeschlossen IstFileName*</span><span class="sxs-lookup"><span data-stu-id="32a89-250">Applicable only if *$type* is *excludedFileName*</span></span>|
|

#### <a name="allowed-threats"></a><span data-ttu-id="32a89-251">Zulässige Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="32a89-251">Allowed threats</span></span>

<span data-ttu-id="32a89-252">Liste der Bedrohungen (identifiziert durch ihren Namen), die nicht vom Produkt blockiert werden und stattdessen ausgeführt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="32a89-252">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

<br>

****

|<span data-ttu-id="32a89-253">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-253">Description</span></span>|<span data-ttu-id="32a89-254">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-254">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-255">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-255">**Key**</span></span>|<span data-ttu-id="32a89-256">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="32a89-256">allowedThreats</span></span>|
|<span data-ttu-id="32a89-257">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-257">**Data type**</span></span>|<span data-ttu-id="32a89-258">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="32a89-258">Array of strings</span></span>|
|

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="32a89-259">Unzulässige Bedrohungsaktionen</span><span class="sxs-lookup"><span data-stu-id="32a89-259">Disallowed threat actions</span></span>

<span data-ttu-id="32a89-260">Schränkt die Aktionen ein, die der lokale Benutzer eines Geräts ausführen kann, wenn Bedrohungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="32a89-260">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="32a89-261">Die in dieser Liste enthaltenen Aktionen werden nicht auf der Benutzeroberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="32a89-261">The actions included in this list are not displayed in the user interface.</span></span>

<br>

****

|<span data-ttu-id="32a89-262">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-262">Description</span></span>|<span data-ttu-id="32a89-263">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-263">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-264">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-264">**Key**</span></span>|<span data-ttu-id="32a89-265">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="32a89-265">disallowedThreatActions</span></span>|
|<span data-ttu-id="32a89-266">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-266">**Data type**</span></span>|<span data-ttu-id="32a89-267">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="32a89-267">Array of strings</span></span>|
|<span data-ttu-id="32a89-268">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-268">**Possible values**</span></span>|<span data-ttu-id="32a89-269">zulassen (verhindert, dass Benutzer Bedrohungen zulassen)</span><span class="sxs-lookup"><span data-stu-id="32a89-269">allow (restricts users from allowing threats)</span></span> <p> <span data-ttu-id="32a89-270">Wiederherstellen (verhindert, dass Benutzer Bedrohungen aus der Quarantäne wiederherstellen)</span><span class="sxs-lookup"><span data-stu-id="32a89-270">restore (restricts users from restoring threats from the quarantine)</span></span>|
|<span data-ttu-id="32a89-271">**Comments**</span><span class="sxs-lookup"><span data-stu-id="32a89-271">**Comments**</span></span>|<span data-ttu-id="32a89-272">Verfügbar in Defender für Endpunkt Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="32a89-272">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="threat-type-settings"></a><span data-ttu-id="32a89-273">Einstellungen für den Bedrohungstyp</span><span class="sxs-lookup"><span data-stu-id="32a89-273">Threat type settings</span></span>

<span data-ttu-id="32a89-274">Die *Einstellung "threatTypeSettings"* im Antivirenmodul wird verwendet, um zu steuern, wie bestimmte Bedrohungstypen vom Produkt behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="32a89-274">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

<br>

****

|<span data-ttu-id="32a89-275">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-275">Description</span></span>|<span data-ttu-id="32a89-276">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-276">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-277">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-277">**Key**</span></span>|<span data-ttu-id="32a89-278">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="32a89-278">threatTypeSettings</span></span>|
|<span data-ttu-id="32a89-279">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-279">**Data type**</span></span>|<span data-ttu-id="32a89-280">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="32a89-280">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="32a89-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="32a89-281">**Comments**</span></span>|<span data-ttu-id="32a89-282">Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="32a89-282">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="threat-type"></a><span data-ttu-id="32a89-283">Bedrohungstyp</span><span class="sxs-lookup"><span data-stu-id="32a89-283">Threat type</span></span>

<span data-ttu-id="32a89-284">Art der Bedrohung, für die das Verhalten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="32a89-284">Type of threat for which the behavior is configured.</span></span>

<br>

****

|<span data-ttu-id="32a89-285">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-285">Description</span></span>|<span data-ttu-id="32a89-286">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-286">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-287">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-287">**Key**</span></span>|<span data-ttu-id="32a89-288">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="32a89-288">key</span></span>|
|<span data-ttu-id="32a89-289">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-289">**Data type**</span></span>|<span data-ttu-id="32a89-290">String</span><span class="sxs-lookup"><span data-stu-id="32a89-290">String</span></span>|
|<span data-ttu-id="32a89-291">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-291">**Possible values**</span></span>|<span data-ttu-id="32a89-292">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="32a89-292">potentially_unwanted_application</span></span> <p> <span data-ttu-id="32a89-293">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="32a89-293">archive_bomb</span></span>|
|

##### <a name="action-to-take"></a><span data-ttu-id="32a89-294">Zu ergreifende Maßnahme</span><span class="sxs-lookup"><span data-stu-id="32a89-294">Action to take</span></span>

<span data-ttu-id="32a89-295">Auszuführende Aktion, wenn eine Bedrohung des im vorherigen Abschnitt angegebenen Typs angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="32a89-295">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="32a89-296">Dies kann folgende sein:</span><span class="sxs-lookup"><span data-stu-id="32a89-296">Can be:</span></span>

- <span data-ttu-id="32a89-297">**Überwachung:** Das Gerät ist nicht vor dieser Art von Bedrohung geschützt, aber ein Eintrag über die Bedrohung wird protokolliert.</span><span class="sxs-lookup"><span data-stu-id="32a89-297">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="32a89-298">**Blockieren:** Das Gerät ist vor dieser Art von Bedrohung geschützt, und Sie werden in der Sicherheitskonsole benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="32a89-298">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="32a89-299">**Deaktiviert:** Das Gerät ist nicht vor dieser Art von Bedrohung geschützt, und es wird nichts protokolliert.</span><span class="sxs-lookup"><span data-stu-id="32a89-299">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

<br>

****

|<span data-ttu-id="32a89-300">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-300">Description</span></span>|<span data-ttu-id="32a89-301">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-301">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-302">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-302">**Key**</span></span>|<span data-ttu-id="32a89-303">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-303">value</span></span>|
|<span data-ttu-id="32a89-304">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-304">**Data type**</span></span>|<span data-ttu-id="32a89-305">String</span><span class="sxs-lookup"><span data-stu-id="32a89-305">String</span></span>|
|<span data-ttu-id="32a89-306">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-306">**Possible values**</span></span>|<span data-ttu-id="32a89-307">Überwachung (Standard)</span><span class="sxs-lookup"><span data-stu-id="32a89-307">audit (default)</span></span> <p> <span data-ttu-id="32a89-308">Block</span><span class="sxs-lookup"><span data-stu-id="32a89-308">block</span></span> <p> <span data-ttu-id="32a89-309">Aus</span><span class="sxs-lookup"><span data-stu-id="32a89-309">off</span></span>|
|

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="32a89-310">Richtlinie zum Zusammenführen von Bedrohungstypeinstellungen</span><span class="sxs-lookup"><span data-stu-id="32a89-310">Threat type settings merge policy</span></span>

<span data-ttu-id="32a89-311">Gibt die Zusammenführungsrichtlinie für Einstellungen für den Bedrohungstyp an.</span><span class="sxs-lookup"><span data-stu-id="32a89-311">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="32a89-312">Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Einstellungen ( `merge` ) oder nur administratordefinierten Einstellungen ( `admin_only` ) sein.</span><span class="sxs-lookup"><span data-stu-id="32a89-312">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="32a89-313">Diese Einstellung kann verwendet werden, um zu verhindern, dass lokale Benutzer ihre eigenen Einstellungen für unterschiedliche Bedrohungstypen definieren.</span><span class="sxs-lookup"><span data-stu-id="32a89-313">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

<br>

****

|<span data-ttu-id="32a89-314">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-314">Description</span></span>|<span data-ttu-id="32a89-315">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-315">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-316">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-316">**Key**</span></span>|<span data-ttu-id="32a89-317">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="32a89-317">threatTypeSettingsMergePolicy</span></span>|
|<span data-ttu-id="32a89-318">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-318">**Data type**</span></span>|<span data-ttu-id="32a89-319">String</span><span class="sxs-lookup"><span data-stu-id="32a89-319">String</span></span>|
|<span data-ttu-id="32a89-320">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-320">**Possible values**</span></span>|<span data-ttu-id="32a89-321">Zusammenführen (Standard)</span><span class="sxs-lookup"><span data-stu-id="32a89-321">merge (default)</span></span> <p> <span data-ttu-id="32a89-322">admin_only</span><span class="sxs-lookup"><span data-stu-id="32a89-322">admin_only</span></span>|
|<span data-ttu-id="32a89-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="32a89-323">**Comments**</span></span>|<span data-ttu-id="32a89-324">Verfügbar in Defender für Endpunkt Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="32a89-324">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="32a89-325">Aufbewahrung des Antivirusscanverlaufs (in Tagen)</span><span class="sxs-lookup"><span data-stu-id="32a89-325">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="32a89-326">Geben Sie die Anzahl der Tage an, für die die Ergebnisse im Scanverlauf auf dem Gerät aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="32a89-326">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="32a89-327">Alte Scanergebnisse werden aus dem Verlauf entfernt.</span><span class="sxs-lookup"><span data-stu-id="32a89-327">Old scan results are removed from the history.</span></span> <span data-ttu-id="32a89-328">Alte isolierte Dateien, die ebenfalls vom Datenträger entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="32a89-328">Old quarantined files that are also removed from the disk.</span></span>

<br>

****

|<span data-ttu-id="32a89-329">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-329">Description</span></span>|<span data-ttu-id="32a89-330">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-330">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-331">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-331">**Key**</span></span>|<span data-ttu-id="32a89-332">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="32a89-332">scanResultsRetentionDays</span></span>|
|<span data-ttu-id="32a89-333">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-333">**Data type**</span></span>|<span data-ttu-id="32a89-334">String</span><span class="sxs-lookup"><span data-stu-id="32a89-334">String</span></span>|
|<span data-ttu-id="32a89-335">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-335">**Possible values**</span></span>|<span data-ttu-id="32a89-336">90 (Standard).</span><span class="sxs-lookup"><span data-stu-id="32a89-336">90 (default).</span></span> <span data-ttu-id="32a89-337">Zulässige Werte liegen zwischen 1 Tag und 180 Tagen.</span><span class="sxs-lookup"><span data-stu-id="32a89-337">Allowed values are from 1 day to 180 days.</span></span>|
|<span data-ttu-id="32a89-338">**Comments**</span><span class="sxs-lookup"><span data-stu-id="32a89-338">**Comments**</span></span>|<span data-ttu-id="32a89-339">Verfügbar in Defender für Endpunkt Version 101.04.76 oder höher.</span><span class="sxs-lookup"><span data-stu-id="32a89-339">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="32a89-340">Maximale Anzahl von Elementen im Antivirusscanverlauf</span><span class="sxs-lookup"><span data-stu-id="32a89-340">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="32a89-341">Geben Sie die maximale Anzahl von Einträgen an, die im Scanverlauf beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="32a89-341">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="32a89-342">Die Einträge enthalten alle on-Demand-Scans, die in der Vergangenheit durchgeführt wurden, sowie alle Antivirenerkennungen.</span><span class="sxs-lookup"><span data-stu-id="32a89-342">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

<br>

****

|<span data-ttu-id="32a89-343">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-343">Description</span></span>|<span data-ttu-id="32a89-344">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-344">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-345">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-345">**Key**</span></span>|<span data-ttu-id="32a89-346">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="32a89-346">scanHistoryMaximumItems</span></span>|
|<span data-ttu-id="32a89-347">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-347">**Data type**</span></span>|<span data-ttu-id="32a89-348">String</span><span class="sxs-lookup"><span data-stu-id="32a89-348">String</span></span>|
|<span data-ttu-id="32a89-349">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-349">**Possible values**</span></span>|<span data-ttu-id="32a89-350">10000 (Standard).</span><span class="sxs-lookup"><span data-stu-id="32a89-350">10000 (default).</span></span> <span data-ttu-id="32a89-351">Zulässige Werte liegen zwischen 5000 Elementen und 15.000 Elementen.</span><span class="sxs-lookup"><span data-stu-id="32a89-351">Allowed values are from 5000 items to 15000 items.</span></span>|
|<span data-ttu-id="32a89-352">**Comments**</span><span class="sxs-lookup"><span data-stu-id="32a89-352">**Comments**</span></span>|<span data-ttu-id="32a89-353">Verfügbar in Defender für Endpunkt Version 101.04.76 oder höher.</span><span class="sxs-lookup"><span data-stu-id="32a89-353">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="32a89-354">Über die Cloud bereitgestellte Schutzeinstellungen</span><span class="sxs-lookup"><span data-stu-id="32a89-354">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="32a89-355">Der *cloudService-Eintrag* im Konfigurationsprofil wird verwendet, um das cloudgesteuerte Schutzfeature des Produkts zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="32a89-355">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

<br>

****

|<span data-ttu-id="32a89-356">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-356">Description</span></span>|<span data-ttu-id="32a89-357">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-357">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-358">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-358">**Key**</span></span>|<span data-ttu-id="32a89-359">cloudService</span><span class="sxs-lookup"><span data-stu-id="32a89-359">cloudService</span></span>|
|<span data-ttu-id="32a89-360">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-360">**Data type**</span></span>|<span data-ttu-id="32a89-361">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="32a89-361">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="32a89-362">**Comments**</span><span class="sxs-lookup"><span data-stu-id="32a89-362">**Comments**</span></span>|<span data-ttu-id="32a89-363">Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="32a89-363">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="32a89-364">Aktivieren/Deaktivieren des über die Cloud bereitgestellten Schutzes</span><span class="sxs-lookup"><span data-stu-id="32a89-364">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="32a89-365">Bestimmt, ob der über die Cloud bereitgestellte Schutz auf dem Gerät aktiviert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="32a89-365">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="32a89-366">Um die Sicherheit Ihrer Dienste zu verbessern, empfehlen wir, dieses Feature aktiviert zu halten.</span><span class="sxs-lookup"><span data-stu-id="32a89-366">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

<br>

****

|<span data-ttu-id="32a89-367">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-367">Description</span></span>|<span data-ttu-id="32a89-368">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-368">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-369">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-369">**Key**</span></span>|<span data-ttu-id="32a89-370">aktiviert</span><span class="sxs-lookup"><span data-stu-id="32a89-370">enabled</span></span>|
|<span data-ttu-id="32a89-371">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-371">**Data type**</span></span>|<span data-ttu-id="32a89-372">Boolesch</span><span class="sxs-lookup"><span data-stu-id="32a89-372">Boolean</span></span>|
|<span data-ttu-id="32a89-373">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-373">**Possible values**</span></span>|<span data-ttu-id="32a89-374">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="32a89-374">true (default)</span></span> <p> <span data-ttu-id="32a89-375">false</span><span class="sxs-lookup"><span data-stu-id="32a89-375">false</span></span>|
|

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="32a89-376">Diagnosesammlungsebene</span><span class="sxs-lookup"><span data-stu-id="32a89-376">Diagnostic collection level</span></span>

<span data-ttu-id="32a89-377">Diagnosedaten werden verwendet, um Defender für Endpunkt sicher und auf dem neuesten Stand zu halten, Probleme zu erkennen, zu diagnostizieren und zu beheben sowie Produktverbesserungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="32a89-377">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="32a89-378">Diese Einstellung bestimmt die Diagnosestufe, die vom Produkt an Microsoft gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="32a89-378">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="32a89-379">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-379">Description</span></span>|<span data-ttu-id="32a89-380">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-380">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-381">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-381">**Key**</span></span>|<span data-ttu-id="32a89-382">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="32a89-382">diagnosticLevel</span></span>|
|<span data-ttu-id="32a89-383">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-383">**Data type**</span></span>|<span data-ttu-id="32a89-384">String</span><span class="sxs-lookup"><span data-stu-id="32a89-384">String</span></span>|
|<span data-ttu-id="32a89-385">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-385">**Possible values**</span></span>|<span data-ttu-id="32a89-386">optional (Standard)</span><span class="sxs-lookup"><span data-stu-id="32a89-386">optional (default)</span></span> <p> <span data-ttu-id="32a89-387">erforderlich</span><span class="sxs-lookup"><span data-stu-id="32a89-387">required</span></span>|
|

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="32a89-388">Aktivieren/Deaktivieren automatischer Beispielübermittlungen</span><span class="sxs-lookup"><span data-stu-id="32a89-388">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="32a89-389">Bestimmt, ob verdächtige Beispiele (die wahrscheinlich Bedrohungen enthalten) an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="32a89-389">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="32a89-390">Es gibt drei Ebenen zum Steuern der Beispielübermittlung:</span><span class="sxs-lookup"><span data-stu-id="32a89-390">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="32a89-391">**Keine:** Es werden keine verdächtigen Beispiele an Microsoft übermittelt.</span><span class="sxs-lookup"><span data-stu-id="32a89-391">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="32a89-392">**Tresor:** nur verdächtige Beispiele, die keine personenbezogenen Informationen (PII) enthalten, werden automatisch übermittelt.</span><span class="sxs-lookup"><span data-stu-id="32a89-392">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="32a89-393">Dies ist der Standardwert für diese Einstellung.</span><span class="sxs-lookup"><span data-stu-id="32a89-393">This is the default value for this setting.</span></span>
- <span data-ttu-id="32a89-394">**Alle:** Alle verdächtigen Beispiele werden an Microsoft übermittelt.</span><span class="sxs-lookup"><span data-stu-id="32a89-394">**All**: all suspicious samples are submitted to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="32a89-395">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-395">Description</span></span>|<span data-ttu-id="32a89-396">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-396">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-397">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-397">**Key**</span></span>|<span data-ttu-id="32a89-398">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="32a89-398">automaticSampleSubmissionConsent</span></span>|
|<span data-ttu-id="32a89-399">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-399">**Data type**</span></span>|<span data-ttu-id="32a89-400">String</span><span class="sxs-lookup"><span data-stu-id="32a89-400">String</span></span>|
|<span data-ttu-id="32a89-401">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-401">**Possible values**</span></span>|<span data-ttu-id="32a89-402">keine</span><span class="sxs-lookup"><span data-stu-id="32a89-402">none</span></span> <p> <span data-ttu-id="32a89-403">sicher (Standard)</span><span class="sxs-lookup"><span data-stu-id="32a89-403">safe (default)</span></span> <p> <span data-ttu-id="32a89-404">Alle</span><span class="sxs-lookup"><span data-stu-id="32a89-404">all</span></span>|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="32a89-405">Aktivieren/Deaktivieren automatischer Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="32a89-405">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="32a89-406">Bestimmt, ob Sicherheitsupdates automatisch installiert werden:</span><span class="sxs-lookup"><span data-stu-id="32a89-406">Determines whether security intelligence updates are installed automatically:</span></span>

<br>

****

|<span data-ttu-id="32a89-407">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32a89-407">Description</span></span>|<span data-ttu-id="32a89-408">Wert</span><span class="sxs-lookup"><span data-stu-id="32a89-408">Value</span></span>|
|---|---|
|<span data-ttu-id="32a89-409">**Key**</span><span class="sxs-lookup"><span data-stu-id="32a89-409">**Key**</span></span>|<span data-ttu-id="32a89-410">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="32a89-410">automaticDefinitionUpdateEnabled</span></span>|
|<span data-ttu-id="32a89-411">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="32a89-411">**Data type**</span></span>|<span data-ttu-id="32a89-412">Boolesch</span><span class="sxs-lookup"><span data-stu-id="32a89-412">Boolean</span></span>|
|<span data-ttu-id="32a89-413">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="32a89-413">**Possible values**</span></span>|<span data-ttu-id="32a89-414">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="32a89-414">true (default)</span></span> <p> <span data-ttu-id="32a89-415">false</span><span class="sxs-lookup"><span data-stu-id="32a89-415">false</span></span>|
|

## <a name="recommended-configuration-profile"></a><span data-ttu-id="32a89-416">Empfohlenes Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="32a89-416">Recommended configuration profile</span></span>

<span data-ttu-id="32a89-417">Für die ersten Schritte empfehlen wir das folgende Konfigurationsprofil für Ihr Unternehmen, um alle Schutzfunktionen zu nutzen, die Defender für Endpunkt bietet.</span><span class="sxs-lookup"><span data-stu-id="32a89-417">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="32a89-418">Das folgende Konfigurationsprofil sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="32a89-418">The following configuration profile will:</span></span>

- <span data-ttu-id="32a89-419">Aktivieren des Echtzeitschutzes (Real-Time Protection, RTP)</span><span class="sxs-lookup"><span data-stu-id="32a89-419">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="32a89-420">Geben Sie an, wie die folgenden Bedrohungstypen behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="32a89-420">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="32a89-421">**Potenziell unerwünschte Anwendungen (PUA)** werden blockiert</span><span class="sxs-lookup"><span data-stu-id="32a89-421">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="32a89-422">**Archivdateien** (Datei mit hoher Komprimierungsrate) werden in den Produktprotokollen überwacht.</span><span class="sxs-lookup"><span data-stu-id="32a89-422">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="32a89-423">Automatische Security Intelligence-Updates aktivieren</span><span class="sxs-lookup"><span data-stu-id="32a89-423">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="32a89-424">Aus der Cloud bereitgestellten Schutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="32a89-424">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="32a89-425">Aktivieren der automatischen Beispielübermittlung `safe` auf Ebene</span><span class="sxs-lookup"><span data-stu-id="32a89-425">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="32a89-426">Beispielprofil</span><span class="sxs-lookup"><span data-stu-id="32a89-426">Sample profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="32a89-427">Beispiel für ein vollständiges Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="32a89-427">Full configuration profile example</span></span>

<span data-ttu-id="32a89-428">Das folgende Konfigurationsprofil enthält Einträge für alle in diesem Dokument beschriebenen Einstellungen und kann für komplexere Szenarien verwendet werden, in denen Sie mehr Kontrolle über das Produkt wünschen.</span><span class="sxs-lookup"><span data-stu-id="32a89-428">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="32a89-429">Vollständiges Profil</span><span class="sxs-lookup"><span data-stu-id="32a89-429">Full profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
         },
         {
            "$type":"excludedFileExtension",
            "extension":".pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="32a89-430">Überprüfung des Konfigurationsprofils</span><span class="sxs-lookup"><span data-stu-id="32a89-430">Configuration profile validation</span></span>

<span data-ttu-id="32a89-431">Das Konfigurationsprofil muss eine gültige JSON-formatierte Datei sein.</span><span class="sxs-lookup"><span data-stu-id="32a89-431">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="32a89-432">Es gibt eine Reihe von Tools, die verwendet werden können, um dies zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="32a89-432">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="32a89-433">Wenn Sie beispielsweise `python` auf Ihrem Gerät installiert haben:</span><span class="sxs-lookup"><span data-stu-id="32a89-433">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="32a89-434">Wenn der JSON-Code wohlgeformt ist, gibt der obige Befehl ihn zurück an das Terminal und gibt den Exitcode `0` von zurück.</span><span class="sxs-lookup"><span data-stu-id="32a89-434">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="32a89-435">Andernfalls wird ein Fehler angezeigt, der das Problem beschreibt, und der Befehl gibt den Exitcode `1` .</span><span class="sxs-lookup"><span data-stu-id="32a89-435">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="32a89-436">Überprüfen, ob die mdatp_managed.json-Datei wie erwartet funktioniert</span><span class="sxs-lookup"><span data-stu-id="32a89-436">Verifying that the mdatp_managed.json file is working as expected</span></span>

<span data-ttu-id="32a89-437">Um zu überprüfen, ob /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsordnungsgemäß funktioniert, sollte neben diesen Einstellungen "[verwaltet]" angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="32a89-437">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>

- <span data-ttu-id="32a89-438">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="32a89-438">cloud_enabled</span></span>
- <span data-ttu-id="32a89-439">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="32a89-439">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="32a89-440">passive_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="32a89-440">passive_mode_enabled</span></span>
- <span data-ttu-id="32a89-441">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="32a89-441">real_time_protection_enabled</span></span>
- <span data-ttu-id="32a89-442">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="32a89-442">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="32a89-443">Damit die mdatp_managed.jswirksam wird, ist kein Neustart des Wdavdaemon erforderlich.</span><span class="sxs-lookup"><span data-stu-id="32a89-443">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="32a89-444">Bereitstellung von Konfigurationsprofilen</span><span class="sxs-lookup"><span data-stu-id="32a89-444">Configuration profile deployment</span></span>

<span data-ttu-id="32a89-445">Nachdem Sie das Konfigurationsprofil für Ihr Unternehmen erstellt haben, können Sie es über das von Ihrem Unternehmen verwendeten Verwaltungstool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="32a89-445">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="32a89-446">Defender für Endpunkt unter Linux liest die verwaltete Konfiguration aus der Datei *"/etc/opt/microsoft/mdatp/managed/mdatp_managed.json".*</span><span class="sxs-lookup"><span data-stu-id="32a89-446">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
