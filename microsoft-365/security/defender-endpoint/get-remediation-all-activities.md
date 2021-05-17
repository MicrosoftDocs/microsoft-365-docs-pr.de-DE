---
title: Auflisten aller Korrekturaktivitäten
description: Gibt Informationen zu allen Korrekturaktivitäten zurück.
keywords: apis, remediation, remediation api, get, remediation tasks, all remediation,
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
ms.openlocfilehash: cf7c79cb6cc76af88ce0293a013ba6edbf435d8c
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245492"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="2bf06-104">Auflisten aller Korrekturaktivitäten</span><span class="sxs-lookup"><span data-stu-id="2bf06-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2bf06-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2bf06-105">**Applies to:**</span></span>

- [<span data-ttu-id="2bf06-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2bf06-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2bf06-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2bf06-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2bf06-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="2bf06-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2bf06-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2bf06-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="2bf06-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2bf06-110">API description</span></span>

<span data-ttu-id="2bf06-111">Gibt Informationen zu allen Korrekturaktivitäten zurück.</span><span class="sxs-lookup"><span data-stu-id="2bf06-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="2bf06-112">[Erfahren Sie mehr über Korrekturaktivitäten](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="2bf06-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="2bf06-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="2bf06-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="2bf06-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2bf06-114">Permissions</span></span>

<span data-ttu-id="2bf06-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2bf06-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2bf06-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs for Details.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2bf06-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="2bf06-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="2bf06-117">Permission type</span></span> | <span data-ttu-id="2bf06-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="2bf06-118">Permission</span></span> | <span data-ttu-id="2bf06-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="2bf06-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2bf06-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="2bf06-120">Application</span></span> | <span data-ttu-id="2bf06-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="2bf06-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="2bf06-122">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="2bf06-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="2bf06-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="2bf06-123">Delegated (work or school account)</span></span> | <span data-ttu-id="2bf06-124">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="2bf06-124">RemediationTask.Read.Read</span></span> | <span data-ttu-id="2bf06-125">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="2bf06-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="2bf06-126">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2bf06-126">Properties</span></span>

<span data-ttu-id="2bf06-127">Property (id)</span><span class="sxs-lookup"><span data-stu-id="2bf06-127">Property (id)</span></span> | <span data-ttu-id="2bf06-128">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2bf06-128">Data type</span></span> | <span data-ttu-id="2bf06-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2bf06-129">Description</span></span> | <span data-ttu-id="2bf06-130">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="2bf06-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="2bf06-131">category</span><span class="sxs-lookup"><span data-stu-id="2bf06-131">category</span></span> | <span data-ttu-id="2bf06-132">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-132">String</span></span> | <span data-ttu-id="2bf06-133">Kategorie der Korrekturaktivität (Software-/Sicherheitskonfiguration)</span><span class="sxs-lookup"><span data-stu-id="2bf06-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="2bf06-134">Software</span><span class="sxs-lookup"><span data-stu-id="2bf06-134">Software</span></span>
<span data-ttu-id="2bf06-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="2bf06-135">completerEmail</span></span> | <span data-ttu-id="2bf06-136">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-136">String</span></span> | <span data-ttu-id="2bf06-137">Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre E-Mails.</span><span class="sxs-lookup"><span data-stu-id="2bf06-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="2bf06-138">null</span><span class="sxs-lookup"><span data-stu-id="2bf06-138">null</span></span>
<span data-ttu-id="2bf06-139">completerId</span><span class="sxs-lookup"><span data-stu-id="2bf06-139">completerId</span></span> | <span data-ttu-id="2bf06-140">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-140">String</span></span> | <span data-ttu-id="2bf06-141">Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre Objekt-ID.</span><span class="sxs-lookup"><span data-stu-id="2bf06-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="2bf06-142">null</span><span class="sxs-lookup"><span data-stu-id="2bf06-142">null</span></span>
<span data-ttu-id="2bf06-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="2bf06-143">completionMethod</span></span> | <span data-ttu-id="2bf06-144">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-144">String</span></span> | <span data-ttu-id="2bf06-145">Eine Korrekturaktivität kann "automatisch" (wenn alle Geräte gepatcht sind) oder "manuell" von einer Person abgeschlossen werden, die "als abgeschlossen markieren" auswählt.</span><span class="sxs-lookup"><span data-stu-id="2bf06-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="2bf06-146">Automatisch</span><span class="sxs-lookup"><span data-stu-id="2bf06-146">Automatic</span></span>
<span data-ttu-id="2bf06-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="2bf06-147">createdOn</span></span> | <span data-ttu-id="2bf06-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="2bf06-148">DateTime</span></span> | <span data-ttu-id="2bf06-149">Zeitpunkt, zu dem diese Korrekturaktivität erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="2bf06-149">Time this remediation activity was created</span></span> | <span data-ttu-id="2bf06-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="2bf06-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="2bf06-151">description</span><span class="sxs-lookup"><span data-stu-id="2bf06-151">description</span></span> | <span data-ttu-id="2bf06-152">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-152">String</span></span> | <span data-ttu-id="2bf06-153">Beschreibung dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="2bf06-153">Description of this remediation activity</span></span> | <span data-ttu-id="2bf06-154">Aktualisieren Sie Microsoft Silverlight auf eine spätere Version, um bekannte Sicherheitsrisiken für Ihre Geräte zu mindern.</span><span class="sxs-lookup"><span data-stu-id="2bf06-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="2bf06-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="2bf06-155">dueOn</span></span> | <span data-ttu-id="2bf06-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="2bf06-156">DateTime</span></span> | <span data-ttu-id="2bf06-157">Fälligkeitsdatum, das der Ersteller für diese Korrekturaktivität festgelegt hat</span><span class="sxs-lookup"><span data-stu-id="2bf06-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="2bf06-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="2bf06-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="2bf06-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="2bf06-159">fixedDevices</span></span> | <span data-ttu-id="2bf06-160">.</span><span class="sxs-lookup"><span data-stu-id="2bf06-160">.</span></span> | <span data-ttu-id="2bf06-161">Die Anzahl der geräte, die behoben wurden</span><span class="sxs-lookup"><span data-stu-id="2bf06-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="2bf06-162">2</span><span class="sxs-lookup"><span data-stu-id="2bf06-162">2</span></span>
<span data-ttu-id="2bf06-163">id</span><span class="sxs-lookup"><span data-stu-id="2bf06-163">id</span></span> | <span data-ttu-id="2bf06-164">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-164">String</span></span> | <span data-ttu-id="2bf06-165">ID dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="2bf06-165">ID of this remediation activity</span></span> | <span data-ttu-id="2bf06-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="2bf06-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="2bf06-167">nameId</span><span class="sxs-lookup"><span data-stu-id="2bf06-167">nameId</span></span> | <span data-ttu-id="2bf06-168">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-168">String</span></span> | <span data-ttu-id="2bf06-169">Verwandter Produktname</span><span class="sxs-lookup"><span data-stu-id="2bf06-169">Related product name</span></span> | <span data-ttu-id="2bf06-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="2bf06-170">Microsoft Silverlight</span></span>
<span data-ttu-id="2bf06-171">priority</span><span class="sxs-lookup"><span data-stu-id="2bf06-171">priority</span></span> | <span data-ttu-id="2bf06-172">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-172">String</span></span> | <span data-ttu-id="2bf06-173">Priorität, die der Ersteller für diese Korrekturaktivität festgelegt hat (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="2bf06-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="2bf06-174">Hoch</span><span class="sxs-lookup"><span data-stu-id="2bf06-174">High</span></span>
<span data-ttu-id="2bf06-175">productId</span><span class="sxs-lookup"><span data-stu-id="2bf06-175">productId</span></span> | <span data-ttu-id="2bf06-176">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-176">String</span></span> | <span data-ttu-id="2bf06-177">Verwandte Produkt-ID</span><span class="sxs-lookup"><span data-stu-id="2bf06-177">Related product ID</span></span> | <span data-ttu-id="2bf06-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="2bf06-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="2bf06-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="2bf06-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="2bf06-180">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-180">String</span></span> | <span data-ttu-id="2bf06-181">Einige Konfigurationsänderungen konnten nur für Geräte ohne Benutzerwirkung angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="2bf06-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="2bf06-182">Dieser Wert gibt die Auswahl zwischen "allen verfügbar gemachten Geräten" oder "nur Geräten ohne Benutzerwirkung" an.</span><span class="sxs-lookup"><span data-stu-id="2bf06-182">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="2bf06-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="2bf06-183">AllExposedAssets</span></span>
<span data-ttu-id="2bf06-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="2bf06-184">rbacGroupNames</span></span> | <span data-ttu-id="2bf06-185">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-185">String</span></span> | <span data-ttu-id="2bf06-186">Verwandte Gerätegruppennamen</span><span class="sxs-lookup"><span data-stu-id="2bf06-186">Related device group names</span></span> | <span data-ttu-id="2bf06-187">[ "Windows Server", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="2bf06-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="2bf06-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="2bf06-188">recommendedProgram</span></span> | <span data-ttu-id="2bf06-189">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-189">String</span></span> | <span data-ttu-id="2bf06-190">Empfohlenes Programm zum Upgrade auf</span><span class="sxs-lookup"><span data-stu-id="2bf06-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="2bf06-191">null</span><span class="sxs-lookup"><span data-stu-id="2bf06-191">null</span></span>
<span data-ttu-id="2bf06-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="2bf06-192">recommendedVendor</span></span> | <span data-ttu-id="2bf06-193">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-193">String</span></span> | <span data-ttu-id="2bf06-194">Empfohlener Anbieter zum Upgrade auf</span><span class="sxs-lookup"><span data-stu-id="2bf06-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="2bf06-195">null</span><span class="sxs-lookup"><span data-stu-id="2bf06-195">null</span></span>
<span data-ttu-id="2bf06-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="2bf06-196">recommendedVersion</span></span> | <span data-ttu-id="2bf06-197">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-197">String</span></span> | <span data-ttu-id="2bf06-198">Empfohlene Version zum Aktualisieren/Aktualisieren auf</span><span class="sxs-lookup"><span data-stu-id="2bf06-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="2bf06-199">null</span><span class="sxs-lookup"><span data-stu-id="2bf06-199">null</span></span>
<span data-ttu-id="2bf06-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="2bf06-200">relatedComponent</span></span> | <span data-ttu-id="2bf06-201">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-201">String</span></span> | <span data-ttu-id="2bf06-202">Verwandte Komponente dieser Korrekturaktivität (ähnlich der zugehörigen Komponente für eine Sicherheitsempfehlung)</span><span class="sxs-lookup"><span data-stu-id="2bf06-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="2bf06-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="2bf06-203">Microsoft Silverlight</span></span>
<span data-ttu-id="2bf06-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="2bf06-204">requesterEmail</span></span> | <span data-ttu-id="2bf06-205">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-205">String</span></span> | <span data-ttu-id="2bf06-206">E-Mail-Adresse des Erstellers</span><span class="sxs-lookup"><span data-stu-id="2bf06-206">Creator email address</span></span> | <span data-ttu-id="2bf06-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2bf06-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="2bf06-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="2bf06-208">requesterId</span></span> | <span data-ttu-id="2bf06-209">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-209">String</span></span> | <span data-ttu-id="2bf06-210">Creator-Objekt-ID</span><span class="sxs-lookup"><span data-stu-id="2bf06-210">Creator object id</span></span> | <span data-ttu-id="2bf06-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="2bf06-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="2bf06-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="2bf06-212">requesterNotes</span></span> | <span data-ttu-id="2bf06-213">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-213">String</span></span> | <span data-ttu-id="2bf06-214">Die Notizen (Freitext), die der Ersteller für diese Korrekturaktivität hinzugefügt hat</span><span class="sxs-lookup"><span data-stu-id="2bf06-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="2bf06-215">null</span><span class="sxs-lookup"><span data-stu-id="2bf06-215">null</span></span>
<span data-ttu-id="2bf06-216">scid</span><span class="sxs-lookup"><span data-stu-id="2bf06-216">scid</span></span> | <span data-ttu-id="2bf06-217">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-217">String</span></span> | <span data-ttu-id="2bf06-218">SCID der zugehörigen Sicherheitsempfehlung</span><span class="sxs-lookup"><span data-stu-id="2bf06-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="2bf06-219">null</span><span class="sxs-lookup"><span data-stu-id="2bf06-219">null</span></span>
<span data-ttu-id="2bf06-220">status</span><span class="sxs-lookup"><span data-stu-id="2bf06-220">status</span></span> | <span data-ttu-id="2bf06-221">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-221">String</span></span> | <span data-ttu-id="2bf06-222">Status der Korrekturaktivität (Aktiv/Abgeschlossen)</span><span class="sxs-lookup"><span data-stu-id="2bf06-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="2bf06-223">Aktiv</span><span class="sxs-lookup"><span data-stu-id="2bf06-223">Active</span></span>
<span data-ttu-id="2bf06-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="2bf06-224">statusLastModifiedOn</span></span> | <span data-ttu-id="2bf06-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="2bf06-225">DateTime</span></span> | <span data-ttu-id="2bf06-226">Datum, an dem das Statusfeld aktualisiert wurde</span><span class="sxs-lookup"><span data-stu-id="2bf06-226">Date when the status field was updated</span></span> | <span data-ttu-id="2bf06-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="2bf06-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="2bf06-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="2bf06-228">targetDevices</span></span> | <span data-ttu-id="2bf06-229">Long</span><span class="sxs-lookup"><span data-stu-id="2bf06-229">Long</span></span> | <span data-ttu-id="2bf06-230">Anzahl der verfügbar gemachten Geräte, auf die diese Behebung anwendbar ist</span><span class="sxs-lookup"><span data-stu-id="2bf06-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="2bf06-231">43</span><span class="sxs-lookup"><span data-stu-id="2bf06-231">43</span></span>
<span data-ttu-id="2bf06-232">title</span><span class="sxs-lookup"><span data-stu-id="2bf06-232">title</span></span> | <span data-ttu-id="2bf06-233">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-233">String</span></span> | <span data-ttu-id="2bf06-234">Titel dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="2bf06-234">Title of this remediation activity</span></span> | <span data-ttu-id="2bf06-235">Aktualisieren von Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="2bf06-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="2bf06-236">type</span><span class="sxs-lookup"><span data-stu-id="2bf06-236">type</span></span> | <span data-ttu-id="2bf06-237">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-237">String</span></span> | <span data-ttu-id="2bf06-238">Behebungstyp</span><span class="sxs-lookup"><span data-stu-id="2bf06-238">Remediation type</span></span> | <span data-ttu-id="2bf06-239">Aktualisieren</span><span class="sxs-lookup"><span data-stu-id="2bf06-239">Update</span></span>
<span data-ttu-id="2bf06-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="2bf06-240">vendorId</span></span> | <span data-ttu-id="2bf06-241">String</span><span class="sxs-lookup"><span data-stu-id="2bf06-241">String</span></span> | <span data-ttu-id="2bf06-242">Verwandter Herstellername</span><span class="sxs-lookup"><span data-stu-id="2bf06-242">Related vendor name</span></span> | <span data-ttu-id="2bf06-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="2bf06-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="2bf06-244">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2bf06-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="2bf06-245">Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="2bf06-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="2bf06-246">Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="2bf06-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2bf06-247">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2bf06-247">See also</span></span>

- [<span data-ttu-id="2bf06-248">Korrekturmethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2bf06-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="2bf06-249">Erhalten einer Korrekturaktivität nach ID</span><span class="sxs-lookup"><span data-stu-id="2bf06-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="2bf06-250">Auflisten verfügbarer Geräte einer Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="2bf06-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="2bf06-251">Risikobasierte Bedrohungsrisiken & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="2bf06-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="2bf06-252">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="2bf06-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
