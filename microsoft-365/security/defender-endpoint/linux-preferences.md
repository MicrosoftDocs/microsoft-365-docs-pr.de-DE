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
ms.openlocfilehash: 00f6bdac66ae286bf55a875599f7097b14b06cb3
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861551"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="d5458-104">Festlegen von Einstellungen für Microsoft Defender für Endpunkt unter Linux</span><span class="sxs-lookup"><span data-stu-id="d5458-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d5458-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d5458-105">**Applies to:**</span></span>
- [<span data-ttu-id="d5458-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d5458-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d5458-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5458-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d5458-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="d5458-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d5458-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d5458-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="d5458-110">Dieses Thema enthält Anweisungen zum Festlegen von Einstellungen für Defender für Endpunkt unter Linux in Unternehmensumgebungen.</span><span class="sxs-lookup"><span data-stu-id="d5458-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="d5458-111">Wenn Sie das Produkt über die Befehlszeile auf einem Gerät konfigurieren möchten, finden Sie weitere Informationen unter ["Ressourcen".](linux-resources.md#configure-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="d5458-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="d5458-112">In Unternehmensumgebungen kann Defender für Endpunkt unter Linux über ein Konfigurationsprofil verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d5458-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="d5458-113">Dieses Profil wird über das Verwaltungstool Ihrer Wahl bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d5458-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="d5458-114">Vom Unternehmen verwaltete Einstellungen haben Vorrang vor den Einstellungen, die lokal auf dem Gerät festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="d5458-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="d5458-115">Mit anderen Worten: Benutzer in Ihrem Unternehmen können keine Einstellungen ändern, die über dieses Konfigurationsprofil festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d5458-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="d5458-116">In diesem Artikel werden die Struktur dieses Profils (einschließlich eines empfohlenen Profils, das Sie für die ersten Schritte verwenden können) und Anweisungen zum Bereitstellen des Profils beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d5458-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="d5458-117">Konfigurationsprofilstruktur</span><span class="sxs-lookup"><span data-stu-id="d5458-117">Configuration profile structure</span></span>

<span data-ttu-id="d5458-118">Das Konfigurationsprofil ist eine JSON-Datei, die aus Einträgen besteht, die durch einen Schlüssel identifiziert werden (der den Namen der Einstellung angibt), gefolgt von einem Wert, der von der Art der Einstellung abhängt.</span><span class="sxs-lookup"><span data-stu-id="d5458-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="d5458-119">Werte können einfach sein, z. B. ein numerischer Wert, oder komplex sein, z. B. eine geschachtelte Liste von Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="d5458-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="d5458-120">In der Regel verwenden Sie ein Konfigurationsverwaltungstool, um eine Datei mit dem Namen am Speicherort zu ```mdatp_managed.json``` ```/etc/opt/microsoft/mdatp/managed/``` übertragen.</span><span class="sxs-lookup"><span data-stu-id="d5458-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="d5458-121">Die oberste Ebene des Konfigurationsprofils enthält produktweite Einstellungen und Einträge für Unterbereiche des Produkts, die in den nächsten Abschnitten ausführlicher erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="d5458-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="d5458-122">Einstellungen des Antivirusmoduls</span><span class="sxs-lookup"><span data-stu-id="d5458-122">Antivirus engine preferences</span></span>

<span data-ttu-id="d5458-123">Der Abschnitt *"antivirusEngine"* des Konfigurationsprofils wird verwendet, um die Einstellungen der Antivirenkomponente des Produkts zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="d5458-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-124">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-124">**Key**</span></span> | <span data-ttu-id="d5458-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="d5458-125">antivirusEngine</span></span> |
| <span data-ttu-id="d5458-126">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-126">**Data type**</span></span> | <span data-ttu-id="d5458-127">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="d5458-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d5458-128">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d5458-128">**Comments**</span></span> | <span data-ttu-id="d5458-129">Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="d5458-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="d5458-130">Aktivieren/Deaktivieren des Echtzeitschutzes</span><span class="sxs-lookup"><span data-stu-id="d5458-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="d5458-131">Bestimmt, ob der Echtzeitschutz (Beim Zugriff auf Dateien scannen) aktiviert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="d5458-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-132">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-132">**Key**</span></span> | <span data-ttu-id="d5458-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="d5458-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="d5458-134">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-134">**Data type**</span></span> | <span data-ttu-id="d5458-135">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5458-135">Boolean</span></span> |
| <span data-ttu-id="d5458-136">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-136">**Possible values**</span></span> | <span data-ttu-id="d5458-137">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5458-137">true (default)</span></span> <br/> <span data-ttu-id="d5458-138">false</span><span class="sxs-lookup"><span data-stu-id="d5458-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="d5458-139">Aktivieren/Deaktivieren des passiven Modus</span><span class="sxs-lookup"><span data-stu-id="d5458-139">Enable / disable passive mode</span></span>

<span data-ttu-id="d5458-140">Bestimmt, ob das Antivirenmodul im passiven Modus ausgeführt wird oder nicht.</span><span class="sxs-lookup"><span data-stu-id="d5458-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="d5458-141">Im passiven Modus:</span><span class="sxs-lookup"><span data-stu-id="d5458-141">In passive mode:</span></span>
- <span data-ttu-id="d5458-142">Der Echtzeitschutz ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d5458-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="d5458-143">On-Demand-Überprüfung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d5458-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="d5458-144">Die automatische Bedrohungsbehebung ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d5458-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="d5458-145">Sicherheitsupdates sind aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d5458-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="d5458-146">Das Statusmenüsymbol ist ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d5458-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-147">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-147">**Key**</span></span> | <span data-ttu-id="d5458-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="d5458-148">passiveMode</span></span> |
| <span data-ttu-id="d5458-149">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-149">**Data type**</span></span> | <span data-ttu-id="d5458-150">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5458-150">Boolean</span></span> |
| <span data-ttu-id="d5458-151">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-151">**Possible values**</span></span> | <span data-ttu-id="d5458-152">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5458-152">false (default)</span></span> <br/> <span data-ttu-id="d5458-153">true</span><span class="sxs-lookup"><span data-stu-id="d5458-153">true</span></span> |
| <span data-ttu-id="d5458-154">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d5458-154">**Comments**</span></span> | <span data-ttu-id="d5458-155">Verfügbar in Defender für Endpunkt Version 100.67.60 oder höher.</span><span class="sxs-lookup"><span data-stu-id="d5458-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="d5458-156">Richtlinie zum Zusammenführen von Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="d5458-156">Exclusion merge policy</span></span>

<span data-ttu-id="d5458-157">Gibt die Zusammenführungsrichtlinie für Ausschlüsse an.</span><span class="sxs-lookup"><span data-stu-id="d5458-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="d5458-158">Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Ausschlüssen ( `merge` ) oder nur von einem Administrator definierten Ausschlüssen ( ) `admin_only` sein.</span><span class="sxs-lookup"><span data-stu-id="d5458-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="d5458-159">Diese Einstellung kann verwendet werden, um lokale Benutzer daran zu hindern, ihre eigenen Ausschlüsse zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d5458-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-160">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-160">**Key**</span></span> | <span data-ttu-id="d5458-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="d5458-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="d5458-162">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-162">**Data type**</span></span> | <span data-ttu-id="d5458-163">String</span><span class="sxs-lookup"><span data-stu-id="d5458-163">String</span></span> |
| <span data-ttu-id="d5458-164">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-164">**Possible values**</span></span> | <span data-ttu-id="d5458-165">Zusammenführen (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5458-165">merge (default)</span></span> <br/> <span data-ttu-id="d5458-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="d5458-166">admin_only</span></span> |
| <span data-ttu-id="d5458-167">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d5458-167">**Comments**</span></span> | <span data-ttu-id="d5458-168">Verfügbar in Defender für Endpunkt Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="d5458-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="d5458-169">Scanausschlüsse</span><span class="sxs-lookup"><span data-stu-id="d5458-169">Scan exclusions</span></span>

<span data-ttu-id="d5458-170">Entitäten, die von der Überprüfung ausgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="d5458-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="d5458-171">Ausschlüsse können durch vollständige Pfade, Erweiterungen oder Dateinamen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d5458-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="d5458-172">(Ausschlüsse werden als Array von Elementen angegeben, der Administrator kann beliebig viele Elemente angeben.)</span><span class="sxs-lookup"><span data-stu-id="d5458-172">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-173">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-173">**Key**</span></span> | <span data-ttu-id="d5458-174">Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="d5458-174">exclusions</span></span> |
| <span data-ttu-id="d5458-175">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-175">**Data type**</span></span> | <span data-ttu-id="d5458-176">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="d5458-176">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d5458-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d5458-177">**Comments**</span></span> | <span data-ttu-id="d5458-178">Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="d5458-178">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="d5458-179">**Art des Ausschlusses**</span><span class="sxs-lookup"><span data-stu-id="d5458-179">**Type of exclusion**</span></span>

<span data-ttu-id="d5458-180">Gibt den Vom Scan ausgeschlossenen Inhaltstyp an.</span><span class="sxs-lookup"><span data-stu-id="d5458-180">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-181">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-181">**Key**</span></span> | <span data-ttu-id="d5458-182">$type</span><span class="sxs-lookup"><span data-stu-id="d5458-182">$type</span></span> |
| <span data-ttu-id="d5458-183">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-183">**Data type**</span></span> | <span data-ttu-id="d5458-184">String</span><span class="sxs-lookup"><span data-stu-id="d5458-184">String</span></span> |
| <span data-ttu-id="d5458-185">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-185">**Possible values**</span></span> | <span data-ttu-id="d5458-186">excludedPath</span><span class="sxs-lookup"><span data-stu-id="d5458-186">excludedPath</span></span> <br/> <span data-ttu-id="d5458-187">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="d5458-187">excludedFileExtension</span></span> <br/> <span data-ttu-id="d5458-188">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="d5458-188">excludedFileName</span></span> |
|||

<span data-ttu-id="d5458-189">**Pfad zu ausgeschlossenen Inhalten**</span><span class="sxs-lookup"><span data-stu-id="d5458-189">**Path to excluded content**</span></span>

<span data-ttu-id="d5458-190">Wird verwendet, um Inhalte vom Scan nach vollständigem Dateipfad auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="d5458-190">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-191">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-191">**Key**</span></span> | <span data-ttu-id="d5458-192">path</span><span class="sxs-lookup"><span data-stu-id="d5458-192">path</span></span> |
| <span data-ttu-id="d5458-193">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-193">**Data type**</span></span> | <span data-ttu-id="d5458-194">String</span><span class="sxs-lookup"><span data-stu-id="d5458-194">String</span></span> |
| <span data-ttu-id="d5458-195">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-195">**Possible values**</span></span> | <span data-ttu-id="d5458-196">Gültige Pfade</span><span class="sxs-lookup"><span data-stu-id="d5458-196">valid paths</span></span> |
| <span data-ttu-id="d5458-197">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d5458-197">**Comments**</span></span> | <span data-ttu-id="d5458-198">Gilt nur, wenn *$type* *ausgeschlossenPath* ist</span><span class="sxs-lookup"><span data-stu-id="d5458-198">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="d5458-199">**Pfadtyp (Datei/Verzeichnis)**</span><span class="sxs-lookup"><span data-stu-id="d5458-199">**Path type (file / directory)**</span></span>

<span data-ttu-id="d5458-200">Gibt an, ob die *Pfadeigenschaft* auf eine Datei oder ein Verzeichnis verweist.</span><span class="sxs-lookup"><span data-stu-id="d5458-200">Indicates if the *path* property refers to a file or directory.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-201">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-201">**Key**</span></span> | <span data-ttu-id="d5458-202">Isdirectory</span><span class="sxs-lookup"><span data-stu-id="d5458-202">isDirectory</span></span> |
| <span data-ttu-id="d5458-203">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-203">**Data type**</span></span> | <span data-ttu-id="d5458-204">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5458-204">Boolean</span></span> |
| <span data-ttu-id="d5458-205">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-205">**Possible values**</span></span> | <span data-ttu-id="d5458-206">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5458-206">false (default)</span></span> <br/> <span data-ttu-id="d5458-207">true</span><span class="sxs-lookup"><span data-stu-id="d5458-207">true</span></span> |
| <span data-ttu-id="d5458-208">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d5458-208">**Comments**</span></span> | <span data-ttu-id="d5458-209">Gilt nur, wenn *$type* *ausgeschlossenPath* ist</span><span class="sxs-lookup"><span data-stu-id="d5458-209">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="d5458-210">**Dateierweiterung, die von der Überprüfung ausgeschlossen ist**</span><span class="sxs-lookup"><span data-stu-id="d5458-210">**File extension excluded from the scan**</span></span>

<span data-ttu-id="d5458-211">Wird verwendet, um Inhalte von der Überprüfung mithilfe der Dateierweiterung auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="d5458-211">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-212">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-212">**Key**</span></span> | <span data-ttu-id="d5458-213">Erweiterung</span><span class="sxs-lookup"><span data-stu-id="d5458-213">extension</span></span> |
| <span data-ttu-id="d5458-214">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-214">**Data type**</span></span> | <span data-ttu-id="d5458-215">String</span><span class="sxs-lookup"><span data-stu-id="d5458-215">String</span></span> |
| <span data-ttu-id="d5458-216">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-216">**Possible values**</span></span> | <span data-ttu-id="d5458-217">gültige Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="d5458-217">valid file extensions</span></span> |
| <span data-ttu-id="d5458-218">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d5458-218">**Comments**</span></span> | <span data-ttu-id="d5458-219">Gilt nur, wenn *$type* *ausgeschlossen istFileExtension*</span><span class="sxs-lookup"><span data-stu-id="d5458-219">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="d5458-220">**Vom Scan ausgeschlossener Prozess**</span><span class="sxs-lookup"><span data-stu-id="d5458-220">**Process excluded from the scan**</span></span>

<span data-ttu-id="d5458-221">Gibt einen Prozess an, für den alle Dateiaktivitäten von der Überprüfung ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="d5458-221">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="d5458-222">Der Prozess kann entweder durch seinen Namen (z. `cat` B. ) oder durch den vollständigen Pfad (z. B. ) angegeben `/bin/cat` werden.</span><span class="sxs-lookup"><span data-stu-id="d5458-222">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-223">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-223">**Key**</span></span> | <span data-ttu-id="d5458-224">name</span><span class="sxs-lookup"><span data-stu-id="d5458-224">name</span></span> |
| <span data-ttu-id="d5458-225">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-225">**Data type**</span></span> | <span data-ttu-id="d5458-226">String</span><span class="sxs-lookup"><span data-stu-id="d5458-226">String</span></span> |
| <span data-ttu-id="d5458-227">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-227">**Possible values**</span></span> | <span data-ttu-id="d5458-228">Eine beliebige Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5458-228">any string</span></span> |
| <span data-ttu-id="d5458-229">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d5458-229">**Comments**</span></span> | <span data-ttu-id="d5458-230">Gilt nur, wenn *$type* *ausgeschlossen IstFileName*</span><span class="sxs-lookup"><span data-stu-id="d5458-230">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="d5458-231">Zulässige Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="d5458-231">Allowed threats</span></span>

<span data-ttu-id="d5458-232">Liste der Bedrohungen (identifiziert durch ihren Namen), die nicht vom Produkt blockiert werden und stattdessen ausgeführt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="d5458-232">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-233">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-233">**Key**</span></span> | <span data-ttu-id="d5458-234">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="d5458-234">allowedThreats</span></span> |
| <span data-ttu-id="d5458-235">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-235">**Data type**</span></span> | <span data-ttu-id="d5458-236">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="d5458-236">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="d5458-237">Unzulässige Bedrohungsaktionen</span><span class="sxs-lookup"><span data-stu-id="d5458-237">Disallowed threat actions</span></span>

<span data-ttu-id="d5458-238">Schränkt die Aktionen ein, die der lokale Benutzer eines Geräts ausführen kann, wenn Bedrohungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="d5458-238">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="d5458-239">Die in dieser Liste enthaltenen Aktionen werden nicht auf der Benutzeroberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d5458-239">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-240">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-240">**Key**</span></span> | <span data-ttu-id="d5458-241">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="d5458-241">disallowedThreatActions</span></span> |
| <span data-ttu-id="d5458-242">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-242">**Data type**</span></span> | <span data-ttu-id="d5458-243">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="d5458-243">Array of strings</span></span> |
| <span data-ttu-id="d5458-244">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-244">**Possible values**</span></span> | <span data-ttu-id="d5458-245">zulassen (verhindert, dass Benutzer Bedrohungen zulassen)</span><span class="sxs-lookup"><span data-stu-id="d5458-245">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="d5458-246">Wiederherstellen (verhindert, dass Benutzer Bedrohungen aus der Quarantäne wiederherstellen)</span><span class="sxs-lookup"><span data-stu-id="d5458-246">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="d5458-247">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d5458-247">**Comments**</span></span> | <span data-ttu-id="d5458-248">Verfügbar in Defender für Endpunkt Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="d5458-248">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="d5458-249">Einstellungen für den Bedrohungstyp</span><span class="sxs-lookup"><span data-stu-id="d5458-249">Threat type settings</span></span>

<span data-ttu-id="d5458-250">Die *Einstellung "threatTypeSettings"* im Antivirenmodul wird verwendet, um zu steuern, wie bestimmte Bedrohungstypen vom Produkt behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="d5458-250">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-251">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-251">**Key**</span></span> | <span data-ttu-id="d5458-252">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="d5458-252">threatTypeSettings</span></span> |
| <span data-ttu-id="d5458-253">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-253">**Data type**</span></span> | <span data-ttu-id="d5458-254">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="d5458-254">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d5458-255">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d5458-255">**Comments**</span></span> | <span data-ttu-id="d5458-256">Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="d5458-256">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="d5458-257">**Bedrohungstyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-257">**Threat type**</span></span>

<span data-ttu-id="d5458-258">Art der Bedrohung, für die das Verhalten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d5458-258">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-259">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-259">**Key**</span></span> | <span data-ttu-id="d5458-260">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="d5458-260">key</span></span> |
| <span data-ttu-id="d5458-261">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-261">**Data type**</span></span> | <span data-ttu-id="d5458-262">String</span><span class="sxs-lookup"><span data-stu-id="d5458-262">String</span></span> |
| <span data-ttu-id="d5458-263">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-263">**Possible values**</span></span> | <span data-ttu-id="d5458-264">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="d5458-264">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="d5458-265">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="d5458-265">archive_bomb</span></span> |
|||

<span data-ttu-id="d5458-266">**Zu ergreifende Maßnahme**</span><span class="sxs-lookup"><span data-stu-id="d5458-266">**Action to take**</span></span>

<span data-ttu-id="d5458-267">Auszuführende Aktion, wenn eine Bedrohung des im vorherigen Abschnitt angegebenen Typs angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d5458-267">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="d5458-268">Dies kann folgende sein:</span><span class="sxs-lookup"><span data-stu-id="d5458-268">Can be:</span></span>

- <span data-ttu-id="d5458-269">**Überwachung:** Das Gerät ist nicht vor dieser Art von Bedrohung geschützt, aber ein Eintrag über die Bedrohung wird protokolliert.</span><span class="sxs-lookup"><span data-stu-id="d5458-269">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="d5458-270">**Blockieren:** Das Gerät ist vor dieser Art von Bedrohung geschützt, und Sie werden in der Sicherheitskonsole benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="d5458-270">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="d5458-271">**Deaktiviert:** Das Gerät ist nicht vor dieser Art von Bedrohung geschützt, und es wird nichts protokolliert.</span><span class="sxs-lookup"><span data-stu-id="d5458-271">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-272">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-272">**Key**</span></span> | <span data-ttu-id="d5458-273">Wert</span><span class="sxs-lookup"><span data-stu-id="d5458-273">value</span></span> |
| <span data-ttu-id="d5458-274">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-274">**Data type**</span></span> | <span data-ttu-id="d5458-275">String</span><span class="sxs-lookup"><span data-stu-id="d5458-275">String</span></span> |
| <span data-ttu-id="d5458-276">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-276">**Possible values**</span></span> | <span data-ttu-id="d5458-277">Überwachung (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5458-277">audit (default)</span></span> <br/> <span data-ttu-id="d5458-278">Block</span><span class="sxs-lookup"><span data-stu-id="d5458-278">block</span></span> <br/> <span data-ttu-id="d5458-279">Aus</span><span class="sxs-lookup"><span data-stu-id="d5458-279">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="d5458-280">Richtlinie zum Zusammenführen von Bedrohungstypeinstellungen</span><span class="sxs-lookup"><span data-stu-id="d5458-280">Threat type settings merge policy</span></span>

<span data-ttu-id="d5458-281">Gibt die Zusammenführungsrichtlinie für Einstellungen für den Bedrohungstyp an.</span><span class="sxs-lookup"><span data-stu-id="d5458-281">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="d5458-282">Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Einstellungen ( `merge` ) oder nur administratordefinierten Einstellungen ( `admin_only` ) sein.</span><span class="sxs-lookup"><span data-stu-id="d5458-282">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="d5458-283">Diese Einstellung kann verwendet werden, um zu verhindern, dass lokale Benutzer ihre eigenen Einstellungen für unterschiedliche Bedrohungstypen definieren.</span><span class="sxs-lookup"><span data-stu-id="d5458-283">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-284">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-284">**Key**</span></span> | <span data-ttu-id="d5458-285">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="d5458-285">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="d5458-286">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-286">**Data type**</span></span> | <span data-ttu-id="d5458-287">String</span><span class="sxs-lookup"><span data-stu-id="d5458-287">String</span></span> |
| <span data-ttu-id="d5458-288">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-288">**Possible values**</span></span> | <span data-ttu-id="d5458-289">Zusammenführen (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5458-289">merge (default)</span></span> <br/> <span data-ttu-id="d5458-290">admin_only</span><span class="sxs-lookup"><span data-stu-id="d5458-290">admin_only</span></span> |
| <span data-ttu-id="d5458-291">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d5458-291">**Comments**</span></span> | <span data-ttu-id="d5458-292">Verfügbar in Defender für Endpunkt Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="d5458-292">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="d5458-293">Aufbewahrung des Antivirusscanverlaufs (in Tagen)</span><span class="sxs-lookup"><span data-stu-id="d5458-293">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="d5458-294">Geben Sie die Anzahl der Tage an, für die die Ergebnisse im Scanverlauf auf dem Gerät aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="d5458-294">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="d5458-295">Alte Scanergebnisse werden aus dem Verlauf entfernt.</span><span class="sxs-lookup"><span data-stu-id="d5458-295">Old scan results are removed from the history.</span></span> <span data-ttu-id="d5458-296">Alte isolierte Dateien, die ebenfalls vom Datenträger entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="d5458-296">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-297">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-297">**Key**</span></span> | <span data-ttu-id="d5458-298">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="d5458-298">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="d5458-299">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-299">**Data type**</span></span> | <span data-ttu-id="d5458-300">String</span><span class="sxs-lookup"><span data-stu-id="d5458-300">String</span></span> |
| <span data-ttu-id="d5458-301">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-301">**Possible values**</span></span> | <span data-ttu-id="d5458-302">90 (Standard).</span><span class="sxs-lookup"><span data-stu-id="d5458-302">90 (default).</span></span> <span data-ttu-id="d5458-303">Zulässige Werte liegen zwischen 1 Tag und 180 Tagen.</span><span class="sxs-lookup"><span data-stu-id="d5458-303">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="d5458-304">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d5458-304">**Comments**</span></span> | <span data-ttu-id="d5458-305">Verfügbar in Defender für Endpunkt Version 101.04.76 oder höher.</span><span class="sxs-lookup"><span data-stu-id="d5458-305">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="d5458-306">Maximale Anzahl von Elementen im Antivirusscanverlauf</span><span class="sxs-lookup"><span data-stu-id="d5458-306">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="d5458-307">Geben Sie die maximale Anzahl von Einträgen an, die im Scanverlauf beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d5458-307">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="d5458-308">Die Einträge enthalten alle on-Demand-Scans, die in der Vergangenheit durchgeführt wurden, sowie alle Antivirenerkennungen.</span><span class="sxs-lookup"><span data-stu-id="d5458-308">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-309">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-309">**Key**</span></span> | <span data-ttu-id="d5458-310">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="d5458-310">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="d5458-311">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-311">**Data type**</span></span> | <span data-ttu-id="d5458-312">String</span><span class="sxs-lookup"><span data-stu-id="d5458-312">String</span></span> |
| <span data-ttu-id="d5458-313">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-313">**Possible values**</span></span> | <span data-ttu-id="d5458-314">10000 (Standard).</span><span class="sxs-lookup"><span data-stu-id="d5458-314">10000 (default).</span></span> <span data-ttu-id="d5458-315">Zulässige Werte liegen zwischen 5000 Elementen und 15.000 Elementen.</span><span class="sxs-lookup"><span data-stu-id="d5458-315">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="d5458-316">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d5458-316">**Comments**</span></span> | <span data-ttu-id="d5458-317">Verfügbar in Defender für Endpunkt Version 101.04.76 oder höher.</span><span class="sxs-lookup"><span data-stu-id="d5458-317">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="d5458-318">Über die Cloud bereitgestellte Schutzeinstellungen</span><span class="sxs-lookup"><span data-stu-id="d5458-318">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="d5458-319">Der *cloudService-Eintrag* im Konfigurationsprofil wird verwendet, um das cloudgesteuerte Schutzfeature des Produkts zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d5458-319">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-320">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-320">**Key**</span></span> | <span data-ttu-id="d5458-321">cloudService</span><span class="sxs-lookup"><span data-stu-id="d5458-321">cloudService</span></span> |
| <span data-ttu-id="d5458-322">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-322">**Data type**</span></span> | <span data-ttu-id="d5458-323">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="d5458-323">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d5458-324">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d5458-324">**Comments**</span></span> | <span data-ttu-id="d5458-325">Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="d5458-325">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="d5458-326">Aktivieren/Deaktivieren des über die Cloud bereitgestellten Schutzes</span><span class="sxs-lookup"><span data-stu-id="d5458-326">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="d5458-327">Bestimmt, ob der über die Cloud bereitgestellte Schutz auf dem Gerät aktiviert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="d5458-327">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="d5458-328">Um die Sicherheit Ihrer Dienste zu verbessern, empfehlen wir, dieses Feature aktiviert zu halten.</span><span class="sxs-lookup"><span data-stu-id="d5458-328">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-329">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-329">**Key**</span></span> | <span data-ttu-id="d5458-330">aktiviert</span><span class="sxs-lookup"><span data-stu-id="d5458-330">enabled</span></span> |
| <span data-ttu-id="d5458-331">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-331">**Data type**</span></span> | <span data-ttu-id="d5458-332">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5458-332">Boolean</span></span> |
| <span data-ttu-id="d5458-333">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-333">**Possible values**</span></span> | <span data-ttu-id="d5458-334">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5458-334">true (default)</span></span> <br/> <span data-ttu-id="d5458-335">false</span><span class="sxs-lookup"><span data-stu-id="d5458-335">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="d5458-336">Diagnosesammlungsebene</span><span class="sxs-lookup"><span data-stu-id="d5458-336">Diagnostic collection level</span></span>

<span data-ttu-id="d5458-337">Diagnosedaten werden verwendet, um Defender für Endpunkt sicher und auf dem neuesten Stand zu halten, Probleme zu erkennen, zu diagnostizieren und zu beheben sowie Produktverbesserungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d5458-337">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="d5458-338">Diese Einstellung bestimmt die Diagnosestufe, die vom Produkt an Microsoft gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="d5458-338">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-339">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-339">**Key**</span></span> | <span data-ttu-id="d5458-340">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="d5458-340">diagnosticLevel</span></span> |
| <span data-ttu-id="d5458-341">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-341">**Data type**</span></span> | <span data-ttu-id="d5458-342">String</span><span class="sxs-lookup"><span data-stu-id="d5458-342">String</span></span> |
| <span data-ttu-id="d5458-343">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-343">**Possible values**</span></span> | <span data-ttu-id="d5458-344">optional (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5458-344">optional (default)</span></span> <br/> <span data-ttu-id="d5458-345">erforderlich</span><span class="sxs-lookup"><span data-stu-id="d5458-345">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="d5458-346">Aktivieren/Deaktivieren automatischer Beispielübermittlungen</span><span class="sxs-lookup"><span data-stu-id="d5458-346">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="d5458-347">Bestimmt, ob verdächtige Beispiele (die wahrscheinlich Bedrohungen enthalten) an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d5458-347">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="d5458-348">Es gibt drei Ebenen zum Steuern der Beispielübermittlung:</span><span class="sxs-lookup"><span data-stu-id="d5458-348">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="d5458-349">**Keine:** Es werden keine verdächtigen Beispiele an Microsoft übermittelt.</span><span class="sxs-lookup"><span data-stu-id="d5458-349">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="d5458-350">**Sicher:** Nur verdächtige Beispiele, die keine personenbezogenen Informationen (PII) enthalten, werden automatisch übermittelt.</span><span class="sxs-lookup"><span data-stu-id="d5458-350">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="d5458-351">Dies ist der Standardwert für diese Einstellung.</span><span class="sxs-lookup"><span data-stu-id="d5458-351">This is the default value for this setting.</span></span>
- <span data-ttu-id="d5458-352">**Alle:** Alle verdächtigen Beispiele werden an Microsoft übermittelt.</span><span class="sxs-lookup"><span data-stu-id="d5458-352">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-353">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-353">**Key**</span></span> | <span data-ttu-id="d5458-354">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="d5458-354">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="d5458-355">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-355">**Data type**</span></span> | <span data-ttu-id="d5458-356">String</span><span class="sxs-lookup"><span data-stu-id="d5458-356">String</span></span> |
| <span data-ttu-id="d5458-357">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-357">**Possible values**</span></span> | <span data-ttu-id="d5458-358">keine</span><span class="sxs-lookup"><span data-stu-id="d5458-358">none</span></span> <br/> <span data-ttu-id="d5458-359">sicher (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5458-359">safe (default)</span></span> <br/> <span data-ttu-id="d5458-360">Alle</span><span class="sxs-lookup"><span data-stu-id="d5458-360">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="d5458-361">Aktivieren/Deaktivieren automatischer Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="d5458-361">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="d5458-362">Bestimmt, ob Sicherheitsupdates automatisch installiert werden:</span><span class="sxs-lookup"><span data-stu-id="d5458-362">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="d5458-363">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d5458-363">**Key**</span></span> | <span data-ttu-id="d5458-364">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="d5458-364">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="d5458-365">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d5458-365">**Data type**</span></span> | <span data-ttu-id="d5458-366">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5458-366">Boolean</span></span> |
| <span data-ttu-id="d5458-367">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="d5458-367">**Possible values**</span></span> | <span data-ttu-id="d5458-368">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5458-368">true (default)</span></span> <br/> <span data-ttu-id="d5458-369">false</span><span class="sxs-lookup"><span data-stu-id="d5458-369">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="d5458-370">Empfohlenes Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="d5458-370">Recommended configuration profile</span></span>

<span data-ttu-id="d5458-371">Für die ersten Schritte empfehlen wir das folgende Konfigurationsprofil für Ihr Unternehmen, um alle Schutzfunktionen zu nutzen, die Defender für Endpunkt bietet.</span><span class="sxs-lookup"><span data-stu-id="d5458-371">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="d5458-372">Das folgende Konfigurationsprofil sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d5458-372">The following configuration profile will:</span></span>

- <span data-ttu-id="d5458-373">Aktivieren des Echtzeitschutzes (Real-Time Protection, RTP)</span><span class="sxs-lookup"><span data-stu-id="d5458-373">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="d5458-374">Geben Sie an, wie die folgenden Bedrohungstypen behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="d5458-374">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="d5458-375">**Potenziell unerwünschte Anwendungen (PUA)** werden blockiert</span><span class="sxs-lookup"><span data-stu-id="d5458-375">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="d5458-376">**Archivdateien** (Datei mit hoher Komprimierungsrate) werden in den Produktprotokollen überwacht.</span><span class="sxs-lookup"><span data-stu-id="d5458-376">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="d5458-377">Automatische Security Intelligence-Updates aktivieren</span><span class="sxs-lookup"><span data-stu-id="d5458-377">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="d5458-378">Aus der Cloud bereitgestellten Schutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="d5458-378">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="d5458-379">Aktivieren der automatischen Beispielübermittlung `safe` auf Ebene</span><span class="sxs-lookup"><span data-stu-id="d5458-379">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="d5458-380">Beispielprofil</span><span class="sxs-lookup"><span data-stu-id="d5458-380">Sample profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="d5458-381">Beispiel für ein vollständiges Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="d5458-381">Full configuration profile example</span></span>

<span data-ttu-id="d5458-382">Das folgende Konfigurationsprofil enthält Einträge für alle in diesem Dokument beschriebenen Einstellungen und kann für komplexere Szenarien verwendet werden, in denen Sie mehr Kontrolle über das Produkt wünschen.</span><span class="sxs-lookup"><span data-stu-id="d5458-382">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="d5458-383">Vollständiges Profil</span><span class="sxs-lookup"><span data-stu-id="d5458-383">Full profile</span></span>

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

## <a name="configuration-profile-validation"></a><span data-ttu-id="d5458-384">Überprüfung des Konfigurationsprofils</span><span class="sxs-lookup"><span data-stu-id="d5458-384">Configuration profile validation</span></span>

<span data-ttu-id="d5458-385">Das Konfigurationsprofil muss eine gültige JSON-formatierte Datei sein.</span><span class="sxs-lookup"><span data-stu-id="d5458-385">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="d5458-386">Es gibt eine Reihe von Tools, die verwendet werden können, um dies zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d5458-386">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="d5458-387">Wenn Sie beispielsweise `python` auf Ihrem Gerät installiert haben:</span><span class="sxs-lookup"><span data-stu-id="d5458-387">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="d5458-388">Wenn der JSON-Code wohlgeformt ist, gibt der obige Befehl ihn zurück an das Terminal und gibt den Exitcode `0` von zurück.</span><span class="sxs-lookup"><span data-stu-id="d5458-388">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="d5458-389">Andernfalls wird ein Fehler angezeigt, der das Problem beschreibt, und der Befehl gibt den Exitcode `1` .</span><span class="sxs-lookup"><span data-stu-id="d5458-389">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="d5458-390">Überprüfen, ob die mdatp_managed.json-Datei wie erwartet funktioniert</span><span class="sxs-lookup"><span data-stu-id="d5458-390">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="d5458-391">Um zu überprüfen, ob /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsordnungsgemäß funktioniert, sollte neben diesen Einstellungen "[verwaltet]" angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="d5458-391">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>
- <span data-ttu-id="d5458-392">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="d5458-392">cloud_enabled</span></span>
- <span data-ttu-id="d5458-393">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="d5458-393">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="d5458-394">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="d5458-394">passice_mode_enabled</span></span>
- <span data-ttu-id="d5458-395">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="d5458-395">real_time_protection_enabled</span></span>
- <span data-ttu-id="d5458-396">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="d5458-396">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="d5458-397">Damit die mdatp_managed.jswirksam wird, ist kein Neustart des Wdavdaemon erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d5458-397">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="d5458-398">Bereitstellung von Konfigurationsprofilen</span><span class="sxs-lookup"><span data-stu-id="d5458-398">Configuration profile deployment</span></span>

<span data-ttu-id="d5458-399">Nachdem Sie das Konfigurationsprofil für Ihr Unternehmen erstellt haben, können Sie es über das von Ihrem Unternehmen verwendeten Verwaltungstool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d5458-399">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="d5458-400">Defender für Endpunkt unter Linux liest die verwaltete Konfiguration aus der Datei *"/etc/opt/microsoft/mdatp/managed/mdatp_managed.json".*</span><span class="sxs-lookup"><span data-stu-id="d5458-400">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
