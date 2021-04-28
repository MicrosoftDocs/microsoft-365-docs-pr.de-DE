---
title: Get one remediation activity by Id
description: Gibt Informationen für die angegebene Korrekturaktivität zurück.
keywords: apis, remediation, remediation api, get, remediation tasks, list
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
ms.openlocfilehash: 40a7102a8c7dbf63641daaf47bbd9aa9f2e54649
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061132"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="22e65-104">Get one remediation activity by Id</span><span class="sxs-lookup"><span data-stu-id="22e65-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="22e65-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="22e65-105">**Applies to:**</span></span>

- [<span data-ttu-id="22e65-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="22e65-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="22e65-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22e65-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="22e65-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="22e65-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="22e65-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="22e65-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="22e65-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22e65-110">API description</span></span>

<span data-ttu-id="22e65-111">Gibt Informationen für die angegebene Korrekturaktivität zurück.</span><span class="sxs-lookup"><span data-stu-id="22e65-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="22e65-112">Stellt die gleichen Spalten wie Alle Korrekturaktivitäten "get all [remediation"](get-remediation-all-activities.md)dar, gibt jedoch nur Ergebnisse für die angegebene _Korrekturaktivität zurück._</span><span class="sxs-lookup"><span data-stu-id="22e65-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="22e65-113">[Erfahren Sie mehr über Korrekturaktivitäten](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="22e65-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="22e65-114">Auflisten einer angegebenen Korrekturaktivität für (id)</span><span class="sxs-lookup"><span data-stu-id="22e65-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="22e65-115">**URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="22e65-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

<span data-ttu-id="22e65-116">**Eigenschaftendetails**</span><span class="sxs-lookup"><span data-stu-id="22e65-116">**Properties** details</span></span>

<span data-ttu-id="22e65-117">Property (id)</span><span class="sxs-lookup"><span data-stu-id="22e65-117">Property (id)</span></span> | <span data-ttu-id="22e65-118">Datentyp</span><span class="sxs-lookup"><span data-stu-id="22e65-118">Data type</span></span> | <span data-ttu-id="22e65-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22e65-119">Description</span></span> | <span data-ttu-id="22e65-120">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="22e65-120">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="22e65-121">category</span><span class="sxs-lookup"><span data-stu-id="22e65-121">category</span></span> | <span data-ttu-id="22e65-122">String</span><span class="sxs-lookup"><span data-stu-id="22e65-122">String</span></span> | <span data-ttu-id="22e65-123">Kategorie der Korrekturaktivität (Software-/Sicherheitskonfiguration)</span><span class="sxs-lookup"><span data-stu-id="22e65-123">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="22e65-124">Software</span><span class="sxs-lookup"><span data-stu-id="22e65-124">Software</span></span>
<span data-ttu-id="22e65-125">completerEmail</span><span class="sxs-lookup"><span data-stu-id="22e65-125">completerEmail</span></span> | <span data-ttu-id="22e65-126">String</span><span class="sxs-lookup"><span data-stu-id="22e65-126">String</span></span> | <span data-ttu-id="22e65-127">Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre E-Mails.</span><span class="sxs-lookup"><span data-stu-id="22e65-127">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="22e65-128">null</span><span class="sxs-lookup"><span data-stu-id="22e65-128">null</span></span>
<span data-ttu-id="22e65-129">completerId</span><span class="sxs-lookup"><span data-stu-id="22e65-129">completerId</span></span> | <span data-ttu-id="22e65-130">String</span><span class="sxs-lookup"><span data-stu-id="22e65-130">String</span></span> | <span data-ttu-id="22e65-131">Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre Objekt-ID.</span><span class="sxs-lookup"><span data-stu-id="22e65-131">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="22e65-132">null</span><span class="sxs-lookup"><span data-stu-id="22e65-132">null</span></span>
<span data-ttu-id="22e65-133">completionMethod</span><span class="sxs-lookup"><span data-stu-id="22e65-133">completionMethod</span></span> | <span data-ttu-id="22e65-134">String</span><span class="sxs-lookup"><span data-stu-id="22e65-134">String</span></span> | <span data-ttu-id="22e65-135">Eine Korrekturaktivität kann "automatisch" (wenn alle Geräte gepatcht sind) oder "manuell" von einer Person abgeschlossen werden, die "als abgeschlossen markieren" auswählt.</span><span class="sxs-lookup"><span data-stu-id="22e65-135">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="22e65-136">Automatisch</span><span class="sxs-lookup"><span data-stu-id="22e65-136">Automatic</span></span>
<span data-ttu-id="22e65-137">createdOn</span><span class="sxs-lookup"><span data-stu-id="22e65-137">createdOn</span></span> | <span data-ttu-id="22e65-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="22e65-138">DateTime</span></span> | <span data-ttu-id="22e65-139">Zeitpunkt, zu dem diese Korrekturaktivität erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="22e65-139">Time this remediation activity was created</span></span> | <span data-ttu-id="22e65-140">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="22e65-140">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="22e65-141">description</span><span class="sxs-lookup"><span data-stu-id="22e65-141">description</span></span> | <span data-ttu-id="22e65-142">String</span><span class="sxs-lookup"><span data-stu-id="22e65-142">String</span></span> | <span data-ttu-id="22e65-143">Beschreibung dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="22e65-143">Description of this remediation activity</span></span> | <span data-ttu-id="22e65-144">Aktualisieren Sie Chrome auf eine spätere Version, um 1248 bekannte Sicherheitsrisiken zu verringern, die Ihre Geräte betreffen.</span><span class="sxs-lookup"><span data-stu-id="22e65-144">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="22e65-145">dueOn</span><span class="sxs-lookup"><span data-stu-id="22e65-145">dueOn</span></span> | <span data-ttu-id="22e65-146">DateTime</span><span class="sxs-lookup"><span data-stu-id="22e65-146">DateTime</span></span> | <span data-ttu-id="22e65-147">Fälligkeitsdatum, das der Ersteller für diese Korrekturaktivität festgelegt hat</span><span class="sxs-lookup"><span data-stu-id="22e65-147">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="22e65-148">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="22e65-148">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="22e65-149">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="22e65-149">fixedDevices</span></span> |  | <span data-ttu-id="22e65-150">Die Anzahl der geräte, die behoben wurden</span><span class="sxs-lookup"><span data-stu-id="22e65-150">The number of devices that have been fixed</span></span> | <span data-ttu-id="22e65-151">2</span><span class="sxs-lookup"><span data-stu-id="22e65-151">2</span></span>
<span data-ttu-id="22e65-152">id</span><span class="sxs-lookup"><span data-stu-id="22e65-152">id</span></span> | <span data-ttu-id="22e65-153">String</span><span class="sxs-lookup"><span data-stu-id="22e65-153">String</span></span> | <span data-ttu-id="22e65-154">ID dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="22e65-154">ID of this remediation activity</span></span> | <span data-ttu-id="22e65-155">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="22e65-155">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="22e65-156">nameId</span><span class="sxs-lookup"><span data-stu-id="22e65-156">nameId</span></span> | <span data-ttu-id="22e65-157">String</span><span class="sxs-lookup"><span data-stu-id="22e65-157">String</span></span> | <span data-ttu-id="22e65-158">Verwandter Produktname</span><span class="sxs-lookup"><span data-stu-id="22e65-158">Related product name</span></span> | <span data-ttu-id="22e65-159">chrome</span><span class="sxs-lookup"><span data-stu-id="22e65-159">chrome</span></span>
<span data-ttu-id="22e65-160">priority</span><span class="sxs-lookup"><span data-stu-id="22e65-160">priority</span></span> | <span data-ttu-id="22e65-161">String</span><span class="sxs-lookup"><span data-stu-id="22e65-161">String</span></span> | <span data-ttu-id="22e65-162">Priorität, die der Ersteller für diese Korrekturaktivität festgelegt hat (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="22e65-162">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="22e65-163">Hoch</span><span class="sxs-lookup"><span data-stu-id="22e65-163">High</span></span>
<span data-ttu-id="22e65-164">productId</span><span class="sxs-lookup"><span data-stu-id="22e65-164">productId</span></span> | <span data-ttu-id="22e65-165">String</span><span class="sxs-lookup"><span data-stu-id="22e65-165">String</span></span> | <span data-ttu-id="22e65-166">Verwandte Produkt-ID</span><span class="sxs-lookup"><span data-stu-id="22e65-166">Related product ID</span></span> | <span data-ttu-id="22e65-167">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="22e65-167">google-_-chrome</span></span>
<span data-ttu-id="22e65-168">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="22e65-168">productivityImpactRemediationType</span></span> | <span data-ttu-id="22e65-169">String</span><span class="sxs-lookup"><span data-stu-id="22e65-169">String</span></span> | <span data-ttu-id="22e65-170">Einige Konfigurationsänderungen konnten nur für Geräte ohne Benutzerwirkung angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="22e65-170">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="22e65-171">Dieser Wert gibt die Auswahl zwischen "allen verfügbar gemachten Geräten" oder "nur Geräten ohne Benutzerwirkung" an.</span><span class="sxs-lookup"><span data-stu-id="22e65-171">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="22e65-172">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="22e65-172">AllExposedAssets</span></span>
<span data-ttu-id="22e65-173">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="22e65-173">rbacGroupNames</span></span> | <span data-ttu-id="22e65-174">String</span><span class="sxs-lookup"><span data-stu-id="22e65-174">String</span></span> | <span data-ttu-id="22e65-175">Verwandte Gerätegruppennamen</span><span class="sxs-lookup"><span data-stu-id="22e65-175">Related device group names</span></span> | <span data-ttu-id="22e65-176">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="22e65-176">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="22e65-177">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="22e65-177">recommendedProgram</span></span> | <span data-ttu-id="22e65-178">String</span><span class="sxs-lookup"><span data-stu-id="22e65-178">String</span></span> | <span data-ttu-id="22e65-179">Empfohlenes Programm zum Upgrade auf</span><span class="sxs-lookup"><span data-stu-id="22e65-179">Recommended program to upgrade to</span></span> | <span data-ttu-id="22e65-180">null</span><span class="sxs-lookup"><span data-stu-id="22e65-180">null</span></span>
<span data-ttu-id="22e65-181">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="22e65-181">recommendedVendor</span></span> | <span data-ttu-id="22e65-182">String</span><span class="sxs-lookup"><span data-stu-id="22e65-182">String</span></span> | <span data-ttu-id="22e65-183">Empfohlener Anbieter zum Upgrade auf</span><span class="sxs-lookup"><span data-stu-id="22e65-183">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="22e65-184">null</span><span class="sxs-lookup"><span data-stu-id="22e65-184">null</span></span>
<span data-ttu-id="22e65-185">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="22e65-185">recommendedVersion</span></span> | <span data-ttu-id="22e65-186">String</span><span class="sxs-lookup"><span data-stu-id="22e65-186">String</span></span> | <span data-ttu-id="22e65-187">Empfohlene Version zum Aktualisieren/Aktualisieren auf</span><span class="sxs-lookup"><span data-stu-id="22e65-187">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="22e65-188">null</span><span class="sxs-lookup"><span data-stu-id="22e65-188">null</span></span>
<span data-ttu-id="22e65-189">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="22e65-189">relatedComponent</span></span> | <span data-ttu-id="22e65-190">String</span><span class="sxs-lookup"><span data-stu-id="22e65-190">String</span></span> | <span data-ttu-id="22e65-191">Verwandte Komponente dieser Korrekturaktivität (ähnlich der zugehörigen Komponente für eine Sicherheitsempfehlung)</span><span class="sxs-lookup"><span data-stu-id="22e65-191">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="22e65-192">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="22e65-192">Google Chrome</span></span>
<span data-ttu-id="22e65-193">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="22e65-193">requesterEmail</span></span> | <span data-ttu-id="22e65-194">String</span><span class="sxs-lookup"><span data-stu-id="22e65-194">String</span></span> | <span data-ttu-id="22e65-195">E-Mail-Adresse des Erstellers</span><span class="sxs-lookup"><span data-stu-id="22e65-195">Creator email address</span></span> | <span data-ttu-id="22e65-196">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22e65-196">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="22e65-197">requesterId</span><span class="sxs-lookup"><span data-stu-id="22e65-197">requesterId</span></span> | <span data-ttu-id="22e65-198">String</span><span class="sxs-lookup"><span data-stu-id="22e65-198">String</span></span> | <span data-ttu-id="22e65-199">Creator-Objekt-ID</span><span class="sxs-lookup"><span data-stu-id="22e65-199">Creator object id</span></span> | <span data-ttu-id="22e65-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="22e65-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="22e65-201">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="22e65-201">requesterNotes</span></span> | <span data-ttu-id="22e65-202">String</span><span class="sxs-lookup"><span data-stu-id="22e65-202">String</span></span> | <span data-ttu-id="22e65-203">Die Notizen (Freitext), die der Ersteller für diese Korrekturaktivität hinzugefügt hat</span><span class="sxs-lookup"><span data-stu-id="22e65-203">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="22e65-204">null</span><span class="sxs-lookup"><span data-stu-id="22e65-204">null</span></span>
<span data-ttu-id="22e65-205">scid</span><span class="sxs-lookup"><span data-stu-id="22e65-205">scid</span></span> | <span data-ttu-id="22e65-206">String</span><span class="sxs-lookup"><span data-stu-id="22e65-206">String</span></span> | <span data-ttu-id="22e65-207">SCID der zugehörigen Sicherheitsempfehlung</span><span class="sxs-lookup"><span data-stu-id="22e65-207">SCID of the related security recommendation</span></span> | <span data-ttu-id="22e65-208">null</span><span class="sxs-lookup"><span data-stu-id="22e65-208">null</span></span>
<span data-ttu-id="22e65-209">status</span><span class="sxs-lookup"><span data-stu-id="22e65-209">status</span></span> | <span data-ttu-id="22e65-210">String</span><span class="sxs-lookup"><span data-stu-id="22e65-210">String</span></span> | <span data-ttu-id="22e65-211">Status der Korrekturaktivität (Aktiv/Abgeschlossen)</span><span class="sxs-lookup"><span data-stu-id="22e65-211">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="22e65-212">Aktiv</span><span class="sxs-lookup"><span data-stu-id="22e65-212">Active</span></span>
<span data-ttu-id="22e65-213">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="22e65-213">statusLastModifiedOn</span></span> | <span data-ttu-id="22e65-214">DateTime</span><span class="sxs-lookup"><span data-stu-id="22e65-214">DateTime</span></span> | <span data-ttu-id="22e65-215">Datum, an dem das Statusfeld aktualisiert wurde</span><span class="sxs-lookup"><span data-stu-id="22e65-215">Date when the status field was updated</span></span> | <span data-ttu-id="22e65-216">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="22e65-216">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="22e65-217">targetDevices</span><span class="sxs-lookup"><span data-stu-id="22e65-217">targetDevices</span></span> | <span data-ttu-id="22e65-218">Long</span><span class="sxs-lookup"><span data-stu-id="22e65-218">Long</span></span> | <span data-ttu-id="22e65-219">Anzahl der verfügbar gemachten Geräte, auf die diese Behebung anwendbar ist</span><span class="sxs-lookup"><span data-stu-id="22e65-219">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="22e65-220">43</span><span class="sxs-lookup"><span data-stu-id="22e65-220">43</span></span>
<span data-ttu-id="22e65-221">title</span><span class="sxs-lookup"><span data-stu-id="22e65-221">title</span></span> | <span data-ttu-id="22e65-222">String</span><span class="sxs-lookup"><span data-stu-id="22e65-222">String</span></span> | <span data-ttu-id="22e65-223">Titel dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="22e65-223">Title of this remediation activity</span></span> | <span data-ttu-id="22e65-224">Aktualisieren von Google Chrome</span><span class="sxs-lookup"><span data-stu-id="22e65-224">Update Google Chrome</span></span>
<span data-ttu-id="22e65-225">type</span><span class="sxs-lookup"><span data-stu-id="22e65-225">type</span></span> | <span data-ttu-id="22e65-226">String</span><span class="sxs-lookup"><span data-stu-id="22e65-226">String</span></span> | <span data-ttu-id="22e65-227">Behebungstyp</span><span class="sxs-lookup"><span data-stu-id="22e65-227">Remediation type</span></span> | <span data-ttu-id="22e65-228">Update</span><span class="sxs-lookup"><span data-stu-id="22e65-228">Update</span></span>
<span data-ttu-id="22e65-229">vendorId</span><span class="sxs-lookup"><span data-stu-id="22e65-229">vendorId</span></span> | <span data-ttu-id="22e65-230">String</span><span class="sxs-lookup"><span data-stu-id="22e65-230">String</span></span> | <span data-ttu-id="22e65-231">Verwandter Herstellername</span><span class="sxs-lookup"><span data-stu-id="22e65-231">Related vendor name</span></span> | <span data-ttu-id="22e65-232">google</span><span class="sxs-lookup"><span data-stu-id="22e65-232">google</span></span>

## <a name="example"></a><span data-ttu-id="22e65-233">Beispiel</span><span class="sxs-lookup"><span data-stu-id="22e65-233">Example</span></span>

<span data-ttu-id="22e65-234">**Anforderungsbeispiel**</span><span class="sxs-lookup"><span data-stu-id="22e65-234">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

<span data-ttu-id="22e65-235">**Antwortbeispiel**</span><span class="sxs-lookup"><span data-stu-id="22e65-235">**Response** example</span></span>

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
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
```

## <a name="see-also"></a><span data-ttu-id="22e65-236">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22e65-236">See also</span></span>

- [<span data-ttu-id="22e65-237">Korrekturmethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="22e65-237">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="22e65-238">Auflisten aller Korrekturaktivitäten</span><span class="sxs-lookup"><span data-stu-id="22e65-238">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="22e65-239">Auflisten verfügbarer Geräte einer Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="22e65-239">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="22e65-240">Risikobasiertes Bedrohungsmanagement & Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="22e65-240">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="22e65-241">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="22e65-241">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
