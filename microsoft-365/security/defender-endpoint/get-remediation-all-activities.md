---
title: Auflisten aller Korrekturaktivitäten
description: Gibt Informationen zu allen Korrekturaktivitäten zurück.
keywords: apis, remediation, remediation api, get, remediation tasks,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061127"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="f0b61-104">Auflisten aller Korrekturaktivitäten</span><span class="sxs-lookup"><span data-stu-id="f0b61-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f0b61-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f0b61-105">**Applies to:**</span></span>

- [<span data-ttu-id="f0b61-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f0b61-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f0b61-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0b61-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f0b61-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f0b61-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f0b61-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f0b61-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="f0b61-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0b61-110">API description</span></span>

<span data-ttu-id="f0b61-111">Gibt Informationen zu allen Korrekturaktivitäten zurück.</span><span class="sxs-lookup"><span data-stu-id="f0b61-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="f0b61-112">[Erfahren Sie mehr über Korrekturaktivitäten](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="f0b61-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="f0b61-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="f0b61-113">**URL:** GET: /api/remediationTasks</span></span>

<span data-ttu-id="f0b61-114">**Eigenschaftendetails**</span><span class="sxs-lookup"><span data-stu-id="f0b61-114">**Properties** details</span></span>

<span data-ttu-id="f0b61-115">Property (id)</span><span class="sxs-lookup"><span data-stu-id="f0b61-115">Property (id)</span></span> | <span data-ttu-id="f0b61-116">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f0b61-116">Data type</span></span> | <span data-ttu-id="f0b61-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0b61-117">Description</span></span> | <span data-ttu-id="f0b61-118">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="f0b61-118">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="f0b61-119">category</span><span class="sxs-lookup"><span data-stu-id="f0b61-119">category</span></span> | <span data-ttu-id="f0b61-120">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-120">String</span></span> | <span data-ttu-id="f0b61-121">Kategorie der Korrekturaktivität (Software-/Sicherheitskonfiguration)</span><span class="sxs-lookup"><span data-stu-id="f0b61-121">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="f0b61-122">Software</span><span class="sxs-lookup"><span data-stu-id="f0b61-122">Software</span></span>
<span data-ttu-id="f0b61-123">completerEmail</span><span class="sxs-lookup"><span data-stu-id="f0b61-123">completerEmail</span></span> | <span data-ttu-id="f0b61-124">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-124">String</span></span> | <span data-ttu-id="f0b61-125">Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre E-Mails.</span><span class="sxs-lookup"><span data-stu-id="f0b61-125">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="f0b61-126">null</span><span class="sxs-lookup"><span data-stu-id="f0b61-126">null</span></span>
<span data-ttu-id="f0b61-127">completerId</span><span class="sxs-lookup"><span data-stu-id="f0b61-127">completerId</span></span> | <span data-ttu-id="f0b61-128">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-128">String</span></span> | <span data-ttu-id="f0b61-129">Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre Objekt-ID.</span><span class="sxs-lookup"><span data-stu-id="f0b61-129">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="f0b61-130">null</span><span class="sxs-lookup"><span data-stu-id="f0b61-130">null</span></span>
<span data-ttu-id="f0b61-131">completionMethod</span><span class="sxs-lookup"><span data-stu-id="f0b61-131">completionMethod</span></span> | <span data-ttu-id="f0b61-132">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-132">String</span></span> | <span data-ttu-id="f0b61-133">Eine Korrekturaktivität kann "automatisch" (wenn alle Geräte gepatcht sind) oder "manuell" von einer Person abgeschlossen werden, die "als abgeschlossen markieren" auswählt.</span><span class="sxs-lookup"><span data-stu-id="f0b61-133">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="f0b61-134">Automatisch</span><span class="sxs-lookup"><span data-stu-id="f0b61-134">Automatic</span></span>
<span data-ttu-id="f0b61-135">createdOn</span><span class="sxs-lookup"><span data-stu-id="f0b61-135">createdOn</span></span> | <span data-ttu-id="f0b61-136">DateTime</span><span class="sxs-lookup"><span data-stu-id="f0b61-136">DateTime</span></span> | <span data-ttu-id="f0b61-137">Zeitpunkt, zu dem diese Korrekturaktivität erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="f0b61-137">Time this remediation activity was created</span></span> | <span data-ttu-id="f0b61-138">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="f0b61-138">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="f0b61-139">description</span><span class="sxs-lookup"><span data-stu-id="f0b61-139">description</span></span> | <span data-ttu-id="f0b61-140">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-140">String</span></span> | <span data-ttu-id="f0b61-141">Beschreibung dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="f0b61-141">Description of this remediation activity</span></span> | <span data-ttu-id="f0b61-142">Aktualisieren Sie Chrome auf eine spätere Version, um 1248 bekannte Sicherheitsrisiken zu verringern, die Ihre Geräte betreffen.</span><span class="sxs-lookup"><span data-stu-id="f0b61-142">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="f0b61-143">dueOn</span><span class="sxs-lookup"><span data-stu-id="f0b61-143">dueOn</span></span> | <span data-ttu-id="f0b61-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="f0b61-144">DateTime</span></span> | <span data-ttu-id="f0b61-145">Fälligkeitsdatum, das der Ersteller für diese Korrekturaktivität festgelegt hat</span><span class="sxs-lookup"><span data-stu-id="f0b61-145">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="f0b61-146">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="f0b61-146">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="f0b61-147">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="f0b61-147">fixedDevices</span></span> | <span data-ttu-id="f0b61-148">.</span><span class="sxs-lookup"><span data-stu-id="f0b61-148">.</span></span> | <span data-ttu-id="f0b61-149">Die Anzahl der geräte, die behoben wurden</span><span class="sxs-lookup"><span data-stu-id="f0b61-149">The number of devices that have been fixed</span></span> | <span data-ttu-id="f0b61-150">2</span><span class="sxs-lookup"><span data-stu-id="f0b61-150">2</span></span>
<span data-ttu-id="f0b61-151">id</span><span class="sxs-lookup"><span data-stu-id="f0b61-151">id</span></span> | <span data-ttu-id="f0b61-152">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-152">String</span></span> | <span data-ttu-id="f0b61-153">ID dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="f0b61-153">ID of this remediation activity</span></span> | <span data-ttu-id="f0b61-154">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="f0b61-154">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="f0b61-155">nameId</span><span class="sxs-lookup"><span data-stu-id="f0b61-155">nameId</span></span> | <span data-ttu-id="f0b61-156">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-156">String</span></span> | <span data-ttu-id="f0b61-157">Verwandter Produktname</span><span class="sxs-lookup"><span data-stu-id="f0b61-157">Related product name</span></span> | <span data-ttu-id="f0b61-158">chrome</span><span class="sxs-lookup"><span data-stu-id="f0b61-158">chrome</span></span>
<span data-ttu-id="f0b61-159">priority</span><span class="sxs-lookup"><span data-stu-id="f0b61-159">priority</span></span> | <span data-ttu-id="f0b61-160">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-160">String</span></span> | <span data-ttu-id="f0b61-161">Priorität, die der Ersteller für diese Korrekturaktivität festgelegt hat (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="f0b61-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="f0b61-162">Hoch</span><span class="sxs-lookup"><span data-stu-id="f0b61-162">High</span></span>
<span data-ttu-id="f0b61-163">productId</span><span class="sxs-lookup"><span data-stu-id="f0b61-163">productId</span></span> | <span data-ttu-id="f0b61-164">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-164">String</span></span> | <span data-ttu-id="f0b61-165">Verwandte Produkt-ID</span><span class="sxs-lookup"><span data-stu-id="f0b61-165">Related product ID</span></span> | <span data-ttu-id="f0b61-166">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="f0b61-166">google-_-chrome</span></span>
<span data-ttu-id="f0b61-167">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="f0b61-167">productivityImpactRemediationType</span></span> | <span data-ttu-id="f0b61-168">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-168">String</span></span> | <span data-ttu-id="f0b61-169">Einige Konfigurationsänderungen konnten nur für Geräte ohne Benutzerwirkung angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="f0b61-169">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="f0b61-170">Dieser Wert gibt die Auswahl zwischen "allen verfügbar gemachten Geräten" oder "nur Geräten ohne Benutzerwirkung" an.</span><span class="sxs-lookup"><span data-stu-id="f0b61-170">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="f0b61-171">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="f0b61-171">AllExposedAssets</span></span>
<span data-ttu-id="f0b61-172">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="f0b61-172">rbacGroupNames</span></span> | <span data-ttu-id="f0b61-173">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-173">String</span></span> | <span data-ttu-id="f0b61-174">Verwandte Gerätegruppennamen</span><span class="sxs-lookup"><span data-stu-id="f0b61-174">Related device group names</span></span> | <span data-ttu-id="f0b61-175">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="f0b61-175">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="f0b61-176">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="f0b61-176">recommendedProgram</span></span> | <span data-ttu-id="f0b61-177">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-177">String</span></span> | <span data-ttu-id="f0b61-178">Empfohlenes Programm zum Upgrade auf</span><span class="sxs-lookup"><span data-stu-id="f0b61-178">Recommended program to upgrade to</span></span> | <span data-ttu-id="f0b61-179">null</span><span class="sxs-lookup"><span data-stu-id="f0b61-179">null</span></span>
<span data-ttu-id="f0b61-180">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="f0b61-180">recommendedVendor</span></span> | <span data-ttu-id="f0b61-181">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-181">String</span></span> | <span data-ttu-id="f0b61-182">Empfohlener Anbieter zum Upgrade auf</span><span class="sxs-lookup"><span data-stu-id="f0b61-182">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="f0b61-183">null</span><span class="sxs-lookup"><span data-stu-id="f0b61-183">null</span></span>
<span data-ttu-id="f0b61-184">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="f0b61-184">recommendedVersion</span></span> | <span data-ttu-id="f0b61-185">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-185">String</span></span> | <span data-ttu-id="f0b61-186">Empfohlene Version zum Aktualisieren/Aktualisieren auf</span><span class="sxs-lookup"><span data-stu-id="f0b61-186">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="f0b61-187">null</span><span class="sxs-lookup"><span data-stu-id="f0b61-187">null</span></span>
<span data-ttu-id="f0b61-188">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="f0b61-188">relatedComponent</span></span> | <span data-ttu-id="f0b61-189">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-189">String</span></span> | <span data-ttu-id="f0b61-190">Verwandte Komponente dieser Korrekturaktivität (ähnlich der zugehörigen Komponente für eine Sicherheitsempfehlung)</span><span class="sxs-lookup"><span data-stu-id="f0b61-190">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="f0b61-191">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="f0b61-191">Google Chrome</span></span>
<span data-ttu-id="f0b61-192">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="f0b61-192">requesterEmail</span></span> | <span data-ttu-id="f0b61-193">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-193">String</span></span> | <span data-ttu-id="f0b61-194">E-Mail-Adresse des Erstellers</span><span class="sxs-lookup"><span data-stu-id="f0b61-194">Creator email address</span></span> | <span data-ttu-id="f0b61-195">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0b61-195">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="f0b61-196">requesterId</span><span class="sxs-lookup"><span data-stu-id="f0b61-196">requesterId</span></span> | <span data-ttu-id="f0b61-197">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-197">String</span></span> | <span data-ttu-id="f0b61-198">Creator-Objekt-ID</span><span class="sxs-lookup"><span data-stu-id="f0b61-198">Creator object id</span></span> | <span data-ttu-id="f0b61-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="f0b61-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="f0b61-200">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="f0b61-200">requesterNotes</span></span> | <span data-ttu-id="f0b61-201">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-201">String</span></span> | <span data-ttu-id="f0b61-202">Die Notizen (Freitext), die der Ersteller für diese Korrekturaktivität hinzugefügt hat</span><span class="sxs-lookup"><span data-stu-id="f0b61-202">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="f0b61-203">null</span><span class="sxs-lookup"><span data-stu-id="f0b61-203">null</span></span>
<span data-ttu-id="f0b61-204">scid</span><span class="sxs-lookup"><span data-stu-id="f0b61-204">scid</span></span> | <span data-ttu-id="f0b61-205">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-205">String</span></span> | <span data-ttu-id="f0b61-206">SCID der zugehörigen Sicherheitsempfehlung</span><span class="sxs-lookup"><span data-stu-id="f0b61-206">SCID of the related security recommendation</span></span> | <span data-ttu-id="f0b61-207">null</span><span class="sxs-lookup"><span data-stu-id="f0b61-207">null</span></span>
<span data-ttu-id="f0b61-208">status</span><span class="sxs-lookup"><span data-stu-id="f0b61-208">status</span></span> | <span data-ttu-id="f0b61-209">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-209">String</span></span> | <span data-ttu-id="f0b61-210">Status der Korrekturaktivität (Aktiv/Abgeschlossen)</span><span class="sxs-lookup"><span data-stu-id="f0b61-210">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="f0b61-211">Aktiv</span><span class="sxs-lookup"><span data-stu-id="f0b61-211">Active</span></span>
<span data-ttu-id="f0b61-212">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="f0b61-212">statusLastModifiedOn</span></span> | <span data-ttu-id="f0b61-213">DateTime</span><span class="sxs-lookup"><span data-stu-id="f0b61-213">DateTime</span></span> | <span data-ttu-id="f0b61-214">Datum, an dem das Statusfeld aktualisiert wurde</span><span class="sxs-lookup"><span data-stu-id="f0b61-214">Date when the status field was updated</span></span> | <span data-ttu-id="f0b61-215">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="f0b61-215">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="f0b61-216">targetDevices</span><span class="sxs-lookup"><span data-stu-id="f0b61-216">targetDevices</span></span> | <span data-ttu-id="f0b61-217">Long</span><span class="sxs-lookup"><span data-stu-id="f0b61-217">Long</span></span> | <span data-ttu-id="f0b61-218">Anzahl der verfügbar gemachten Geräte, auf die diese Behebung anwendbar ist</span><span class="sxs-lookup"><span data-stu-id="f0b61-218">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="f0b61-219">43</span><span class="sxs-lookup"><span data-stu-id="f0b61-219">43</span></span>
<span data-ttu-id="f0b61-220">title</span><span class="sxs-lookup"><span data-stu-id="f0b61-220">title</span></span> | <span data-ttu-id="f0b61-221">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-221">String</span></span> | <span data-ttu-id="f0b61-222">Titel dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="f0b61-222">Title of this remediation activity</span></span> | <span data-ttu-id="f0b61-223">Aktualisieren von Google Chrome</span><span class="sxs-lookup"><span data-stu-id="f0b61-223">Update Google Chrome</span></span>
<span data-ttu-id="f0b61-224">type</span><span class="sxs-lookup"><span data-stu-id="f0b61-224">type</span></span> | <span data-ttu-id="f0b61-225">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-225">String</span></span> | <span data-ttu-id="f0b61-226">Behebungstyp</span><span class="sxs-lookup"><span data-stu-id="f0b61-226">Remediation type</span></span> | <span data-ttu-id="f0b61-227">Update</span><span class="sxs-lookup"><span data-stu-id="f0b61-227">Update</span></span>
<span data-ttu-id="f0b61-228">vendorId</span><span class="sxs-lookup"><span data-stu-id="f0b61-228">vendorId</span></span> | <span data-ttu-id="f0b61-229">String</span><span class="sxs-lookup"><span data-stu-id="f0b61-229">String</span></span> | <span data-ttu-id="f0b61-230">Verwandter Herstellername</span><span class="sxs-lookup"><span data-stu-id="f0b61-230">Related vendor name</span></span> | <span data-ttu-id="f0b61-231">google</span><span class="sxs-lookup"><span data-stu-id="f0b61-231">google</span></span>

## <a name="example"></a><span data-ttu-id="f0b61-232">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0b61-232">Example</span></span>

<span data-ttu-id="f0b61-233">**Anforderungsbeispiel**</span><span class="sxs-lookup"><span data-stu-id="f0b61-233">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

<span data-ttu-id="f0b61-234">**Antwortbeispiel**</span><span class="sxs-lookup"><span data-stu-id="f0b61-234">**Response** example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
            "relatedComponent": "Microsoft Silverlight",
            "targetDevices": 18511,
            "rbacGroupNames": [
                "UnassignedGroup",
                "hhh"
            ],
            "fixedDevices": 2866,
            "requesterNotes": "test",
            "dueOn": "2021-02-11T00:00:00Z",
            "category": "Software",
            "productivityImpactRemediationType": null,
            "priority": "Medium",
            "completionMethod": null,
            "completerId": null,
            "completerEmail": null,
            "scid": null,
            "type": "Update",
            "productId": "microsoft-_-silverlight",
            "vendorId": "microsoft",
            "nameId": "silverlight",
            "recommendedVersion": null,
            "recommendedVendor": null,
            "recommendedProgram": null
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="f0b61-235">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0b61-235">See also</span></span>

- [<span data-ttu-id="f0b61-236">Korrekturmethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f0b61-236">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="f0b61-237">Get one remediation activity by Id</span><span class="sxs-lookup"><span data-stu-id="f0b61-237">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="f0b61-238">Auflisten verfügbarer Geräte einer Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="f0b61-238">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="f0b61-239">Risikobasiertes Bedrohungsmanagement & Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="f0b61-239">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="f0b61-240">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="f0b61-240">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
