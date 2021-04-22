---
title: Festlegen von Einstellungen für Microsoft Defender for Endpoint unter Linux
ms.reviewer: ''
description: Beschreibt, wie Sie Microsoft Defender for Endpoint unter Linux in Unternehmen konfigurieren.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 7f3dd65aea0efa570ec5d6a1d27479b787e16831
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935281"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="aeec3-104">Festlegen von Einstellungen für Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="aeec3-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aeec3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="aeec3-105">**Applies to:**</span></span>
- [<span data-ttu-id="aeec3-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="aeec3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aeec3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aeec3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="aeec3-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="aeec3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aeec3-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="aeec3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="aeec3-110">Dieses Thema enthält Anweisungen zum Festlegen von Einstellungen für Defender for Endpoint unter Linux in Unternehmensumgebungen.</span><span class="sxs-lookup"><span data-stu-id="aeec3-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="aeec3-111">Wenn Sie das Produkt auf einem Gerät über die Befehlszeile konfigurieren möchten, lesen Sie [Ressourcen](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="aeec3-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="aeec3-112">In Unternehmensumgebungen kann Defender for Endpoint unter Linux über ein Konfigurationsprofil verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="aeec3-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="aeec3-113">Dieses Profil wird über das Verwaltungstool Ihrer Wahl bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="aeec3-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="aeec3-114">Vom Unternehmen verwaltete Einstellungen haben Vorrang vor den einstellungen, die lokal auf dem Gerät festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="aeec3-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="aeec3-115">Anders ausgedrückt: Benutzer in Ihrem Unternehmen können einstellungen, die über dieses Konfigurationsprofil festgelegt sind, nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="aeec3-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="aeec3-116">In diesem Artikel werden die Struktur dieses Profils (einschließlich eines empfohlenen Profils, das Sie für die ersten Schritte verwenden können) und Anweisungen zum Bereitstellen des Profils beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aeec3-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="aeec3-117">Konfigurationsprofilstruktur</span><span class="sxs-lookup"><span data-stu-id="aeec3-117">Configuration profile structure</span></span>

<span data-ttu-id="aeec3-118">Das Konfigurationsprofil ist eine JSON-Datei, die aus Einträgen besteht, die durch einen Schlüssel identifiziert werden (der den Namen der Einstellung angibt), gefolgt von einem Wert, der von der Art der Einstellung abhängt.</span><span class="sxs-lookup"><span data-stu-id="aeec3-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="aeec3-119">Werte können einfach sein, z. B. ein numerischer Wert oder komplex, z. B. eine geschachtelte Liste von Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="aeec3-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="aeec3-120">In der Regel würden Sie ein Konfigurationsverwaltungstool verwenden, um eine Datei mit dem Namen am ```mdatp_managed.json``` Speicherort zu ```/etc/opt/microsoft/mdatp/managed/``` pushen.</span><span class="sxs-lookup"><span data-stu-id="aeec3-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="aeec3-121">Die oberste Ebene des Konfigurationsprofils enthält produktweite Einstellungen und Einträge für Unterbereiche des Produkts, die in den nächsten Abschnitten ausführlicher erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="aeec3-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="aeec3-122">Einstellungen des Antivirusmoduls</span><span class="sxs-lookup"><span data-stu-id="aeec3-122">Antivirus engine preferences</span></span>

<span data-ttu-id="aeec3-123">Der *Abschnitt antivirusEngine* des Konfigurationsprofils wird zum Verwalten der Einstellungen der Antiviruskomponente des Produkts verwendet.</span><span class="sxs-lookup"><span data-stu-id="aeec3-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-124">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-124">**Key**</span></span> | <span data-ttu-id="aeec3-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="aeec3-125">antivirusEngine</span></span> |
| <span data-ttu-id="aeec3-126">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-126">**Data type**</span></span> | <span data-ttu-id="aeec3-127">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="aeec3-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="aeec3-128">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="aeec3-128">**Comments**</span></span> | <span data-ttu-id="aeec3-129">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="aeec3-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="aeec3-130">Aktivieren/Deaktivieren des Echtzeitschutzes</span><span class="sxs-lookup"><span data-stu-id="aeec3-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="aeec3-131">Bestimmt, ob der Echtzeitschutz (Scandateien, wie auf sie zugegriffen wird) aktiviert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="aeec3-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-132">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-132">**Key**</span></span> | <span data-ttu-id="aeec3-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="aeec3-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="aeec3-134">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-134">**Data type**</span></span> | <span data-ttu-id="aeec3-135">Boolesch</span><span class="sxs-lookup"><span data-stu-id="aeec3-135">Boolean</span></span> |
| <span data-ttu-id="aeec3-136">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-136">**Possible values**</span></span> | <span data-ttu-id="aeec3-137">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="aeec3-137">true (default)</span></span> <br/> <span data-ttu-id="aeec3-138">false</span><span class="sxs-lookup"><span data-stu-id="aeec3-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="aeec3-139">Aktivieren/Deaktivieren des passiven Modus</span><span class="sxs-lookup"><span data-stu-id="aeec3-139">Enable / disable passive mode</span></span>

<span data-ttu-id="aeec3-140">Bestimmt, ob das Antivirenmodul im passiven Modus ausgeführt wird oder nicht.</span><span class="sxs-lookup"><span data-stu-id="aeec3-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="aeec3-141">Im passiven Modus:</span><span class="sxs-lookup"><span data-stu-id="aeec3-141">In passive mode:</span></span>
- <span data-ttu-id="aeec3-142">Der Echtzeitschutz ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="aeec3-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="aeec3-143">Die Überprüfung bei Bedarf ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="aeec3-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="aeec3-144">Die automatische Bedrohungsbehebung ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="aeec3-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="aeec3-145">Sicherheitsintelligenzupdates sind aktiviert.</span><span class="sxs-lookup"><span data-stu-id="aeec3-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="aeec3-146">Das Symbol für das Statusmenü ist ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="aeec3-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-147">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-147">**Key**</span></span> | <span data-ttu-id="aeec3-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="aeec3-148">passiveMode</span></span> |
| <span data-ttu-id="aeec3-149">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-149">**Data type**</span></span> | <span data-ttu-id="aeec3-150">Boolesch</span><span class="sxs-lookup"><span data-stu-id="aeec3-150">Boolean</span></span> |
| <span data-ttu-id="aeec3-151">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-151">**Possible values**</span></span> | <span data-ttu-id="aeec3-152">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="aeec3-152">false (default)</span></span> <br/> <span data-ttu-id="aeec3-153">true</span><span class="sxs-lookup"><span data-stu-id="aeec3-153">true</span></span> |
| <span data-ttu-id="aeec3-154">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="aeec3-154">**Comments**</span></span> | <span data-ttu-id="aeec3-155">Verfügbar in Defender for Endpoint, Version 100.67.60 oder höher.</span><span class="sxs-lookup"><span data-stu-id="aeec3-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="aeec3-156">Ausschlusszusammenführungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="aeec3-156">Exclusion merge policy</span></span>

<span data-ttu-id="aeec3-157">Gibt die Seriendruckrichtlinie für Ausschlüsse an.</span><span class="sxs-lookup"><span data-stu-id="aeec3-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="aeec3-158">Es kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Ausschlüssen ( ) oder nur vom Administrator definierten `merge` Ausschlüssen ( ) sein. `admin_only`</span><span class="sxs-lookup"><span data-stu-id="aeec3-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="aeec3-159">Diese Einstellung kann verwendet werden, um lokale Benutzer an der Definition eigener Ausschlüsse zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="aeec3-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-160">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-160">**Key**</span></span> | <span data-ttu-id="aeec3-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="aeec3-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="aeec3-162">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-162">**Data type**</span></span> | <span data-ttu-id="aeec3-163">String</span><span class="sxs-lookup"><span data-stu-id="aeec3-163">String</span></span> |
| <span data-ttu-id="aeec3-164">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-164">**Possible values**</span></span> | <span data-ttu-id="aeec3-165">merge (Standard)</span><span class="sxs-lookup"><span data-stu-id="aeec3-165">merge (default)</span></span> <br/> <span data-ttu-id="aeec3-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="aeec3-166">admin_only</span></span> |
| <span data-ttu-id="aeec3-167">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="aeec3-167">**Comments**</span></span> | <span data-ttu-id="aeec3-168">Verfügbar in Defender for Endpoint, Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="aeec3-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="aeec3-169">Scannen von Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="aeec3-169">Scan exclusions</span></span>

<span data-ttu-id="aeec3-170">Entitäten, die von der Überprüfung ausgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="aeec3-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="aeec3-171">Ausschlüsse können durch vollständige Pfade, Erweiterungen oder Dateinamen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="aeec3-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-172">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-172">**Key**</span></span> | <span data-ttu-id="aeec3-173">Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="aeec3-173">exclusions</span></span> |
| <span data-ttu-id="aeec3-174">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-174">**Data type**</span></span> | <span data-ttu-id="aeec3-175">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="aeec3-175">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="aeec3-176">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="aeec3-176">**Comments**</span></span> | <span data-ttu-id="aeec3-177">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="aeec3-177">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="aeec3-178">**Art des Ausschlusses**</span><span class="sxs-lookup"><span data-stu-id="aeec3-178">**Type of exclusion**</span></span>

<span data-ttu-id="aeec3-179">Gibt den Typ des Inhalts an, der von der Überprüfung ausgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="aeec3-179">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-180">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-180">**Key**</span></span> | <span data-ttu-id="aeec3-181">$type</span><span class="sxs-lookup"><span data-stu-id="aeec3-181">$type</span></span> |
| <span data-ttu-id="aeec3-182">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-182">**Data type**</span></span> | <span data-ttu-id="aeec3-183">String</span><span class="sxs-lookup"><span data-stu-id="aeec3-183">String</span></span> |
| <span data-ttu-id="aeec3-184">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-184">**Possible values**</span></span> | <span data-ttu-id="aeec3-185">excludedPath</span><span class="sxs-lookup"><span data-stu-id="aeec3-185">excludedPath</span></span> <br/> <span data-ttu-id="aeec3-186">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="aeec3-186">excludedFileExtension</span></span> <br/> <span data-ttu-id="aeec3-187">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="aeec3-187">excludedFileName</span></span> |
|||

<span data-ttu-id="aeec3-188">**Pfad zu ausgeschlossenen Inhalten**</span><span class="sxs-lookup"><span data-stu-id="aeec3-188">**Path to excluded content**</span></span>

<span data-ttu-id="aeec3-189">Wird verwendet, um Inhalte nach vollständigem Dateipfad von der Überprüfung auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="aeec3-189">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-190">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-190">**Key**</span></span> | <span data-ttu-id="aeec3-191">path</span><span class="sxs-lookup"><span data-stu-id="aeec3-191">path</span></span> |
| <span data-ttu-id="aeec3-192">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-192">**Data type**</span></span> | <span data-ttu-id="aeec3-193">String</span><span class="sxs-lookup"><span data-stu-id="aeec3-193">String</span></span> |
| <span data-ttu-id="aeec3-194">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-194">**Possible values**</span></span> | <span data-ttu-id="aeec3-195">gültige Pfade</span><span class="sxs-lookup"><span data-stu-id="aeec3-195">valid paths</span></span> |
| <span data-ttu-id="aeec3-196">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="aeec3-196">**Comments**</span></span> | <span data-ttu-id="aeec3-197">Gilt nur, *$type* *ausgeschlossen IstPath*</span><span class="sxs-lookup"><span data-stu-id="aeec3-197">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="aeec3-198">**Pfadtyp (Datei/Verzeichnis)**</span><span class="sxs-lookup"><span data-stu-id="aeec3-198">**Path type (file / directory)**</span></span>

<span data-ttu-id="aeec3-199">Gibt an, ob *die path-Eigenschaft* auf eine Datei oder ein Verzeichnis verweist.</span><span class="sxs-lookup"><span data-stu-id="aeec3-199">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="aeec3-200">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-200">**Key**</span></span> | <span data-ttu-id="aeec3-201">isDirectory</span><span class="sxs-lookup"><span data-stu-id="aeec3-201">isDirectory</span></span> |
| <span data-ttu-id="aeec3-202">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-202">**Data type**</span></span> | <span data-ttu-id="aeec3-203">Boolesch</span><span class="sxs-lookup"><span data-stu-id="aeec3-203">Boolean</span></span> |
| <span data-ttu-id="aeec3-204">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-204">**Possible values**</span></span> | <span data-ttu-id="aeec3-205">false (Standard)</span><span class="sxs-lookup"><span data-stu-id="aeec3-205">false (default)</span></span> <br/> <span data-ttu-id="aeec3-206">true</span><span class="sxs-lookup"><span data-stu-id="aeec3-206">true</span></span> |
| <span data-ttu-id="aeec3-207">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="aeec3-207">**Comments**</span></span> | <span data-ttu-id="aeec3-208">Gilt nur, *$type* *ausgeschlossen IstPath*</span><span class="sxs-lookup"><span data-stu-id="aeec3-208">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="aeec3-209">**Dateierweiterung, die von der Überprüfung ausgeschlossen wurde**</span><span class="sxs-lookup"><span data-stu-id="aeec3-209">**File extension excluded from the scan**</span></span>

<span data-ttu-id="aeec3-210">Wird verwendet, um Inhalte von der Überprüfung nach Dateierweiterung auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="aeec3-210">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-211">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-211">**Key**</span></span> | <span data-ttu-id="aeec3-212">erweiterung</span><span class="sxs-lookup"><span data-stu-id="aeec3-212">extension</span></span> |
| <span data-ttu-id="aeec3-213">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-213">**Data type**</span></span> | <span data-ttu-id="aeec3-214">String</span><span class="sxs-lookup"><span data-stu-id="aeec3-214">String</span></span> |
| <span data-ttu-id="aeec3-215">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-215">**Possible values**</span></span> | <span data-ttu-id="aeec3-216">Gültige Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="aeec3-216">valid file extensions</span></span> |
| <span data-ttu-id="aeec3-217">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="aeec3-217">**Comments**</span></span> | <span data-ttu-id="aeec3-218">Gilt nur, *$type* *ausgeschlossen istFileExtension*</span><span class="sxs-lookup"><span data-stu-id="aeec3-218">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="aeec3-219">**Prozess, der von der Überprüfung ausgeschlossen wurde**</span><span class="sxs-lookup"><span data-stu-id="aeec3-219">**Process excluded from the scan**</span></span>

<span data-ttu-id="aeec3-220">Gibt einen Prozess an, für den alle Dateiaktivitäten von der Überprüfung ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="aeec3-220">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="aeec3-221">Der Prozess kann entweder durch seinen Namen (z. B. ) oder den `cat` vollständigen Pfad (z. B. ) angegeben werden. `/bin/cat`</span><span class="sxs-lookup"><span data-stu-id="aeec3-221">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-222">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-222">**Key**</span></span> | <span data-ttu-id="aeec3-223">name</span><span class="sxs-lookup"><span data-stu-id="aeec3-223">name</span></span> |
| <span data-ttu-id="aeec3-224">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-224">**Data type**</span></span> | <span data-ttu-id="aeec3-225">String</span><span class="sxs-lookup"><span data-stu-id="aeec3-225">String</span></span> |
| <span data-ttu-id="aeec3-226">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-226">**Possible values**</span></span> | <span data-ttu-id="aeec3-227">eine beliebige Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="aeec3-227">any string</span></span> |
| <span data-ttu-id="aeec3-228">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="aeec3-228">**Comments**</span></span> | <span data-ttu-id="aeec3-229">Gilt nur, *$type* *ausgeschlossen istFileName*</span><span class="sxs-lookup"><span data-stu-id="aeec3-229">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="aeec3-230">Zulässige Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="aeec3-230">Allowed threats</span></span>

<span data-ttu-id="aeec3-231">Liste der Bedrohungen (die durch ihren Namen identifiziert werden), die nicht vom Produkt blockiert werden und stattdessen ausgeführt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="aeec3-231">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-232">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-232">**Key**</span></span> | <span data-ttu-id="aeec3-233">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="aeec3-233">allowedThreats</span></span> |
| <span data-ttu-id="aeec3-234">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-234">**Data type**</span></span> | <span data-ttu-id="aeec3-235">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="aeec3-235">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="aeec3-236">Unzulässige Bedrohungsaktionen</span><span class="sxs-lookup"><span data-stu-id="aeec3-236">Disallowed threat actions</span></span>

<span data-ttu-id="aeec3-237">Schränkt die Aktionen ein, die der lokale Benutzer eines Geräts ausführen kann, wenn Bedrohungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="aeec3-237">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="aeec3-238">Die in dieser Liste enthaltenen Aktionen werden nicht auf der Benutzeroberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aeec3-238">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-239">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-239">**Key**</span></span> | <span data-ttu-id="aeec3-240">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="aeec3-240">disallowedThreatActions</span></span> |
| <span data-ttu-id="aeec3-241">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-241">**Data type**</span></span> | <span data-ttu-id="aeec3-242">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="aeec3-242">Array of strings</span></span> |
| <span data-ttu-id="aeec3-243">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-243">**Possible values**</span></span> | <span data-ttu-id="aeec3-244">allow (schränkt ein, dass Benutzer Bedrohungen zulassen)</span><span class="sxs-lookup"><span data-stu-id="aeec3-244">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="aeec3-245">restore (schränkt benutzer das Wiederherstellen von Bedrohungen aus der Quarantäne ein)</span><span class="sxs-lookup"><span data-stu-id="aeec3-245">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="aeec3-246">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="aeec3-246">**Comments**</span></span> | <span data-ttu-id="aeec3-247">Verfügbar in Defender for Endpoint, Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="aeec3-247">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="aeec3-248">Einstellungen für den Bedrohungstyp</span><span class="sxs-lookup"><span data-stu-id="aeec3-248">Threat type settings</span></span>

<span data-ttu-id="aeec3-249">Die *ThreatTypeSettings-Einstellung* im Antivirusmodul wird verwendet, um zu steuern, wie bestimmte Bedrohungstypen vom Produkt behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="aeec3-249">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-250">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-250">**Key**</span></span> | <span data-ttu-id="aeec3-251">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="aeec3-251">threatTypeSettings</span></span> |
| <span data-ttu-id="aeec3-252">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-252">**Data type**</span></span> | <span data-ttu-id="aeec3-253">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="aeec3-253">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="aeec3-254">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="aeec3-254">**Comments**</span></span> | <span data-ttu-id="aeec3-255">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="aeec3-255">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="aeec3-256">**Bedrohungstyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-256">**Threat type**</span></span>

<span data-ttu-id="aeec3-257">Typ der Bedrohung, für die das Verhalten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="aeec3-257">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-258">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-258">**Key**</span></span> | <span data-ttu-id="aeec3-259">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="aeec3-259">key</span></span> |
| <span data-ttu-id="aeec3-260">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-260">**Data type**</span></span> | <span data-ttu-id="aeec3-261">String</span><span class="sxs-lookup"><span data-stu-id="aeec3-261">String</span></span> |
| <span data-ttu-id="aeec3-262">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-262">**Possible values**</span></span> | <span data-ttu-id="aeec3-263">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="aeec3-263">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="aeec3-264">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="aeec3-264">archive_bomb</span></span> |
|||

<span data-ttu-id="aeec3-265">**Zu ergreifende Maßnahme**</span><span class="sxs-lookup"><span data-stu-id="aeec3-265">**Action to take**</span></span>

<span data-ttu-id="aeec3-266">Maßnahmen, die ausgeführt werden müssen, wenn eine Bedrohung des im vorherigen Abschnitt angegebenen Typs angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="aeec3-266">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="aeec3-267">Dies kann:</span><span class="sxs-lookup"><span data-stu-id="aeec3-267">Can be:</span></span>

- <span data-ttu-id="aeec3-268">**Überwachung**: Das Gerät ist nicht vor dieser Art von Bedrohung geschützt, aber ein Eintrag über die Bedrohung wird protokolliert.</span><span class="sxs-lookup"><span data-stu-id="aeec3-268">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="aeec3-269">**Block**: Das Gerät ist vor dieser Art von Bedrohung geschützt, und Sie werden in der Sicherheitskonsole benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="aeec3-269">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="aeec3-270">**Aus**: Das Gerät ist nicht vor dieser Art von Bedrohung geschützt, und es wird nichts protokolliert.</span><span class="sxs-lookup"><span data-stu-id="aeec3-270">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-271">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-271">**Key**</span></span> | <span data-ttu-id="aeec3-272">Wert</span><span class="sxs-lookup"><span data-stu-id="aeec3-272">value</span></span> |
| <span data-ttu-id="aeec3-273">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-273">**Data type**</span></span> | <span data-ttu-id="aeec3-274">String</span><span class="sxs-lookup"><span data-stu-id="aeec3-274">String</span></span> |
| <span data-ttu-id="aeec3-275">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-275">**Possible values**</span></span> | <span data-ttu-id="aeec3-276">Überwachung (Standard)</span><span class="sxs-lookup"><span data-stu-id="aeec3-276">audit (default)</span></span> <br/> <span data-ttu-id="aeec3-277">block</span><span class="sxs-lookup"><span data-stu-id="aeec3-277">block</span></span> <br/> <span data-ttu-id="aeec3-278">off</span><span class="sxs-lookup"><span data-stu-id="aeec3-278">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="aeec3-279">Richtlinie zum Zusammenführen von Bedrohungstypeinstellungen</span><span class="sxs-lookup"><span data-stu-id="aeec3-279">Threat type settings merge policy</span></span>

<span data-ttu-id="aeec3-280">Gibt die Seriendruckrichtlinie für Bedrohungstypeinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="aeec3-280">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="aeec3-281">Dies kann eine Kombination aus vom Administrator definierten und benutzerdefinierten Einstellungen ( ) oder nur vom Administrator definierten Einstellungen `merge` ( ) `admin_only` sein.</span><span class="sxs-lookup"><span data-stu-id="aeec3-281">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="aeec3-282">Diese Einstellung kann verwendet werden, um lokale Benutzer an der Definition eigener Einstellungen für verschiedene Bedrohungstypen zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="aeec3-282">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-283">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-283">**Key**</span></span> | <span data-ttu-id="aeec3-284">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="aeec3-284">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="aeec3-285">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-285">**Data type**</span></span> | <span data-ttu-id="aeec3-286">String</span><span class="sxs-lookup"><span data-stu-id="aeec3-286">String</span></span> |
| <span data-ttu-id="aeec3-287">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-287">**Possible values**</span></span> | <span data-ttu-id="aeec3-288">merge (Standard)</span><span class="sxs-lookup"><span data-stu-id="aeec3-288">merge (default)</span></span> <br/> <span data-ttu-id="aeec3-289">admin_only</span><span class="sxs-lookup"><span data-stu-id="aeec3-289">admin_only</span></span> |
| <span data-ttu-id="aeec3-290">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="aeec3-290">**Comments**</span></span> | <span data-ttu-id="aeec3-291">Verfügbar in Defender for Endpoint, Version 100.83.73 oder höher.</span><span class="sxs-lookup"><span data-stu-id="aeec3-291">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="aeec3-292">Aufbewahrung des Antivirusscanverlaufs (in Tagen)</span><span class="sxs-lookup"><span data-stu-id="aeec3-292">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="aeec3-293">Geben Sie die Anzahl der Tage an, die Ergebnisse im Scanverlauf auf dem Gerät aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="aeec3-293">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="aeec3-294">Alte Scanergebnisse werden aus dem Verlauf entfernt.</span><span class="sxs-lookup"><span data-stu-id="aeec3-294">Old scan results are removed from the history.</span></span> <span data-ttu-id="aeec3-295">Alte isolierte Dateien, die ebenfalls vom Datenträger entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="aeec3-295">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-296">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-296">**Key**</span></span> | <span data-ttu-id="aeec3-297">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="aeec3-297">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="aeec3-298">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-298">**Data type**</span></span> | <span data-ttu-id="aeec3-299">String</span><span class="sxs-lookup"><span data-stu-id="aeec3-299">String</span></span> |
| <span data-ttu-id="aeec3-300">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-300">**Possible values**</span></span> | <span data-ttu-id="aeec3-301">90 (Standard).</span><span class="sxs-lookup"><span data-stu-id="aeec3-301">90 (default).</span></span> <span data-ttu-id="aeec3-302">Zulässige Werte liegen zwischen 1 Tag und 180 Tagen.</span><span class="sxs-lookup"><span data-stu-id="aeec3-302">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="aeec3-303">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="aeec3-303">**Comments**</span></span> | <span data-ttu-id="aeec3-304">Verfügbar in Defender for Endpoint, Version 101.04.76 oder höher.</span><span class="sxs-lookup"><span data-stu-id="aeec3-304">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="aeec3-305">Maximale Anzahl von Elementen im Antivirusscanverlauf</span><span class="sxs-lookup"><span data-stu-id="aeec3-305">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="aeec3-306">Geben Sie die maximale Anzahl von Einträgen an, die im Scanverlauf bleiben sollen.</span><span class="sxs-lookup"><span data-stu-id="aeec3-306">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="aeec3-307">Zu den Einträgen gehören alle in der Vergangenheit durchgeführten Bedarfsscans und alle Antivirenerkennungen.</span><span class="sxs-lookup"><span data-stu-id="aeec3-307">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-308">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-308">**Key**</span></span> | <span data-ttu-id="aeec3-309">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="aeec3-309">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="aeec3-310">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-310">**Data type**</span></span> | <span data-ttu-id="aeec3-311">String</span><span class="sxs-lookup"><span data-stu-id="aeec3-311">String</span></span> |
| <span data-ttu-id="aeec3-312">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-312">**Possible values**</span></span> | <span data-ttu-id="aeec3-313">10000 (Standard).</span><span class="sxs-lookup"><span data-stu-id="aeec3-313">10000 (default).</span></span> <span data-ttu-id="aeec3-314">Zulässige Werte liegen zwischen 5.000 und 15.000 Elementen.</span><span class="sxs-lookup"><span data-stu-id="aeec3-314">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="aeec3-315">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="aeec3-315">**Comments**</span></span> | <span data-ttu-id="aeec3-316">Verfügbar in Defender for Endpoint, Version 101.04.76 oder höher.</span><span class="sxs-lookup"><span data-stu-id="aeec3-316">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="aeec3-317">Von der Cloud übermittelte Schutzeinstellungen</span><span class="sxs-lookup"><span data-stu-id="aeec3-317">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="aeec3-318">Der *cloudService-Eintrag* im Konfigurationsprofil wird verwendet, um das cloudgesteuerte Schutzfeature des Produkts zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="aeec3-318">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-319">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-319">**Key**</span></span> | <span data-ttu-id="aeec3-320">cloudService</span><span class="sxs-lookup"><span data-stu-id="aeec3-320">cloudService</span></span> |
| <span data-ttu-id="aeec3-321">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-321">**Data type**</span></span> | <span data-ttu-id="aeec3-322">Wörterbuch (geschachtelte Einstellung)</span><span class="sxs-lookup"><span data-stu-id="aeec3-322">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="aeec3-323">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="aeec3-323">**Comments**</span></span> | <span data-ttu-id="aeec3-324">Eine Beschreibung der Wörterbuchinhalte finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="aeec3-324">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="aeec3-325">Aktivieren/Deaktivieren des von der Cloud übermittelten Schutzes</span><span class="sxs-lookup"><span data-stu-id="aeec3-325">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="aeec3-326">Bestimmt, ob der in der Cloud zugestellte Schutz auf dem Gerät aktiviert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="aeec3-326">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="aeec3-327">Um die Sicherheit Ihrer Dienste zu verbessern, wird empfohlen, dieses Feature aktiviert zu halten.</span><span class="sxs-lookup"><span data-stu-id="aeec3-327">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-328">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-328">**Key**</span></span> | <span data-ttu-id="aeec3-329">aktiviert</span><span class="sxs-lookup"><span data-stu-id="aeec3-329">enabled</span></span> |
| <span data-ttu-id="aeec3-330">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-330">**Data type**</span></span> | <span data-ttu-id="aeec3-331">Boolesch</span><span class="sxs-lookup"><span data-stu-id="aeec3-331">Boolean</span></span> |
| <span data-ttu-id="aeec3-332">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-332">**Possible values**</span></span> | <span data-ttu-id="aeec3-333">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="aeec3-333">true (default)</span></span> <br/> <span data-ttu-id="aeec3-334">false</span><span class="sxs-lookup"><span data-stu-id="aeec3-334">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="aeec3-335">Diagnosesammlungsebene</span><span class="sxs-lookup"><span data-stu-id="aeec3-335">Diagnostic collection level</span></span>

<span data-ttu-id="aeec3-336">Diagnosedaten werden verwendet, um Defender for Endpoint sicher und auf dem neuesten Stand zu halten, Probleme zu erkennen, zu diagnostizieren und zu beheben sowie Produktverbesserungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="aeec3-336">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="aeec3-337">Diese Einstellung bestimmt die Diagnosestufe, die vom Produkt an Microsoft gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="aeec3-337">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-338">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-338">**Key**</span></span> | <span data-ttu-id="aeec3-339">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="aeec3-339">diagnosticLevel</span></span> |
| <span data-ttu-id="aeec3-340">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-340">**Data type**</span></span> | <span data-ttu-id="aeec3-341">String</span><span class="sxs-lookup"><span data-stu-id="aeec3-341">String</span></span> |
| <span data-ttu-id="aeec3-342">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-342">**Possible values**</span></span> | <span data-ttu-id="aeec3-343">optional (Standard)</span><span class="sxs-lookup"><span data-stu-id="aeec3-343">optional (default)</span></span> <br/> <span data-ttu-id="aeec3-344">erforderlich</span><span class="sxs-lookup"><span data-stu-id="aeec3-344">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="aeec3-345">Aktivieren/Deaktivieren automatischer Beispielübermittlungen</span><span class="sxs-lookup"><span data-stu-id="aeec3-345">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="aeec3-346">Bestimmt, ob verdächtige Beispiele (die wahrscheinlich Bedrohungen enthalten) an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="aeec3-346">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="aeec3-347">Es gibt drei Ebenen zum Steuern der Beispielübermittlung:</span><span class="sxs-lookup"><span data-stu-id="aeec3-347">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="aeec3-348">**Keine**: Es werden keine verdächtigen Beispiele an Microsoft übermittelt.</span><span class="sxs-lookup"><span data-stu-id="aeec3-348">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="aeec3-349">**Sicher:** Nur verdächtige Beispiele, die keine personenbezogenen Informationen (PII) enthalten, werden automatisch übermittelt.</span><span class="sxs-lookup"><span data-stu-id="aeec3-349">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="aeec3-350">Dies ist der Standardwert für diese Einstellung.</span><span class="sxs-lookup"><span data-stu-id="aeec3-350">This is the default value for this setting.</span></span>
- <span data-ttu-id="aeec3-351">**Alle**: Alle verdächtigen Beispiele werden an Microsoft übermittelt.</span><span class="sxs-lookup"><span data-stu-id="aeec3-351">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-352">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-352">**Key**</span></span> | <span data-ttu-id="aeec3-353">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="aeec3-353">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="aeec3-354">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-354">**Data type**</span></span> | <span data-ttu-id="aeec3-355">String</span><span class="sxs-lookup"><span data-stu-id="aeec3-355">String</span></span> |
| <span data-ttu-id="aeec3-356">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-356">**Possible values**</span></span> | <span data-ttu-id="aeec3-357">keine</span><span class="sxs-lookup"><span data-stu-id="aeec3-357">none</span></span> <br/> <span data-ttu-id="aeec3-358">sicher (Standard)</span><span class="sxs-lookup"><span data-stu-id="aeec3-358">safe (default)</span></span> <br/> <span data-ttu-id="aeec3-359">all</span><span class="sxs-lookup"><span data-stu-id="aeec3-359">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="aeec3-360">Aktivieren/Deaktivieren automatischer Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="aeec3-360">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="aeec3-361">Bestimmt, ob Sicherheitsintelligenzupdates automatisch installiert werden:</span><span class="sxs-lookup"><span data-stu-id="aeec3-361">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="aeec3-362">**Key**</span><span class="sxs-lookup"><span data-stu-id="aeec3-362">**Key**</span></span> | <span data-ttu-id="aeec3-363">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="aeec3-363">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="aeec3-364">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="aeec3-364">**Data type**</span></span> | <span data-ttu-id="aeec3-365">Boolesch</span><span class="sxs-lookup"><span data-stu-id="aeec3-365">Boolean</span></span> |
| <span data-ttu-id="aeec3-366">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="aeec3-366">**Possible values**</span></span> | <span data-ttu-id="aeec3-367">true (Standard)</span><span class="sxs-lookup"><span data-stu-id="aeec3-367">true (default)</span></span> <br/> <span data-ttu-id="aeec3-368">false</span><span class="sxs-lookup"><span data-stu-id="aeec3-368">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="aeec3-369">Empfohlenes Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="aeec3-369">Recommended configuration profile</span></span>

<span data-ttu-id="aeec3-370">Für die ersten Schritte wird das folgende Konfigurationsprofil für Ihr Unternehmen empfohlen, um alle Schutzfunktionen zu nutzen, die Defender for Endpoint bietet.</span><span class="sxs-lookup"><span data-stu-id="aeec3-370">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="aeec3-371">Das folgende Konfigurationsprofil hat Folgendes:</span><span class="sxs-lookup"><span data-stu-id="aeec3-371">The following configuration profile will:</span></span>

- <span data-ttu-id="aeec3-372">Aktivieren des Echtzeitschutzes (Real-Time Protection, RTP)</span><span class="sxs-lookup"><span data-stu-id="aeec3-372">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="aeec3-373">Geben Sie an, wie die folgenden Bedrohungstypen behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="aeec3-373">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="aeec3-374">**Potenziell unerwünschte Anwendungen (PUA)** werden blockiert</span><span class="sxs-lookup"><span data-stu-id="aeec3-374">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="aeec3-375">**Archivangriffe** (Datei mit hoher Komprimierungsrate) werden in den Produktprotokollen überwacht.</span><span class="sxs-lookup"><span data-stu-id="aeec3-375">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="aeec3-376">Aktivieren automatischer Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="aeec3-376">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="aeec3-377">Aktivieren des in der Cloud übermittelten Schutzes</span><span class="sxs-lookup"><span data-stu-id="aeec3-377">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="aeec3-378">Aktivieren der automatischen Beispielübermittlung auf `safe` Ebene</span><span class="sxs-lookup"><span data-stu-id="aeec3-378">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="aeec3-379">Beispielprofil</span><span class="sxs-lookup"><span data-stu-id="aeec3-379">Sample profile</span></span>

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
      "enabled":true
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="aeec3-380">Beispiel für ein vollständiges Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="aeec3-380">Full configuration profile example</span></span>

<span data-ttu-id="aeec3-381">Das folgende Konfigurationsprofil enthält Einträge für alle in diesem Dokument beschriebenen Einstellungen und kann für erweiterte Szenarien verwendet werden, in denen Sie mehr Kontrolle über das Produkt wünschen.</span><span class="sxs-lookup"><span data-stu-id="aeec3-381">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="aeec3-382">Vollständiges Profil</span><span class="sxs-lookup"><span data-stu-id="aeec3-382">Full profile</span></span>

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
            "path":"/home"
         },
         {
            "$type":"excludedFileExtension",
            "extension":"pdf"
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
      "automaticDefinitionUpdateEnabled":true
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="aeec3-383">Konfigurationsprofilüberprüfung</span><span class="sxs-lookup"><span data-stu-id="aeec3-383">Configuration profile validation</span></span>

<span data-ttu-id="aeec3-384">Das Konfigurationsprofil muss eine gültige JSON-formatierte Datei sein.</span><span class="sxs-lookup"><span data-stu-id="aeec3-384">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="aeec3-385">Es gibt eine Reihe von Tools, die verwendet werden können, um dies zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="aeec3-385">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="aeec3-386">Beispiel: Wenn Sie auf `python` Ihrem Gerät installiert sind:</span><span class="sxs-lookup"><span data-stu-id="aeec3-386">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="aeec3-387">Wenn das JSON wohlgeformt ist, gibt der obige Befehl es zurück an das Terminal aus und gibt den Exitcode von `0` zurück.</span><span class="sxs-lookup"><span data-stu-id="aeec3-387">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="aeec3-388">Andernfalls wird ein Fehler angezeigt, der das Problem beschreibt, und der Befehl gibt den Exitcode von `1` zurück.</span><span class="sxs-lookup"><span data-stu-id="aeec3-388">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="aeec3-389">Überprüfen, ob mdatp_managed.jsdatei wie erwartet funktioniert</span><span class="sxs-lookup"><span data-stu-id="aeec3-389">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="aeec3-390">Um zu überprüfen, ob /etc/opt/microsoft/mdatp/managed/mdatp_managed.json ordnungsgemäß funktioniert, sollten Sie neben den folgenden Einstellungen "[verwaltet]" sehen:</span><span class="sxs-lookup"><span data-stu-id="aeec3-390">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="aeec3-391">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="aeec3-391">cloud_enabled</span></span>
- <span data-ttu-id="aeec3-392">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="aeec3-392">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="aeec3-393">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="aeec3-393">passice_mode_enabled</span></span>
- <span data-ttu-id="aeec3-394">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="aeec3-394">real_time_protection_enabled</span></span>
- <span data-ttu-id="aeec3-395">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="aeec3-395">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="aeec3-396">Damit die mdatp_managed.jswirksam wird, ist kein Neustart des wdavdaemon erforderlich.</span><span class="sxs-lookup"><span data-stu-id="aeec3-396">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="aeec3-397">Konfigurationsprofilbereitstellung</span><span class="sxs-lookup"><span data-stu-id="aeec3-397">Configuration profile deployment</span></span>

<span data-ttu-id="aeec3-398">Nachdem Sie das Konfigurationsprofil für Ihr Unternehmen erstellt haben, können Sie es über das Verwaltungstool bereitstellen, das Ihr Unternehmen verwendet.</span><span class="sxs-lookup"><span data-stu-id="aeec3-398">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="aeec3-399">Defender for Endpoint unter Linux liest die verwaltete Konfiguration aus der *Datei /etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*</span><span class="sxs-lookup"><span data-stu-id="aeec3-399">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
