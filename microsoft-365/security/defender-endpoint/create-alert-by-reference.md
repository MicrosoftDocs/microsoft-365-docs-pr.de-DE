---
title: Erstellen einer Warnung aus der Ereignis-API
description: Erfahren Sie, wie Sie mithilfe der Warnungs-API erstellen eine neue Warnung über Ereignis in Microsoft Defender for Endpoint erstellen.
keywords: apis, graph api, supported apis, get, alert, information, id
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9066bcdae549f7a6b1372714d567674eb03c1e51
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166674"
---
# <a name="create-alert-api"></a><span data-ttu-id="8dbab-104">Erstellen einer Warnungs-API</span><span class="sxs-lookup"><span data-stu-id="8dbab-104">Create alert API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8dbab-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8dbab-105">**Applies to:**</span></span>
- [<span data-ttu-id="8dbab-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8dbab-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8dbab-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8dbab-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="8dbab-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="8dbab-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8dbab-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="8dbab-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="8dbab-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8dbab-110">API description</span></span>
<span data-ttu-id="8dbab-111">Erstellt neue [Warnung](alerts.md) über **Ereignis**.</span><span class="sxs-lookup"><span data-stu-id="8dbab-111">Creates new [Alert](alerts.md) on top of **Event**.</span></span>
<br><span data-ttu-id="8dbab-112">**Microsoft Defender for Endpoint Event** ist für die Warnungserstellung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8dbab-112">**Microsoft Defender for Endpoint Event** is required for the alert creation.</span></span>
<br><span data-ttu-id="8dbab-113">Sie müssen 3 Parameter aus dem Ereignis in der Anforderung angeben: **Ereigniszeit**, **Computer-ID** und **Berichts-ID**.</span><span class="sxs-lookup"><span data-stu-id="8dbab-113">You will need to supply 3 parameters from the Event in the request: **Event Time**, **Machine ID** and **Report ID**.</span></span> <span data-ttu-id="8dbab-114">Siehe Beispiel unten.</span><span class="sxs-lookup"><span data-stu-id="8dbab-114">See example below.</span></span>
<br><span data-ttu-id="8dbab-115">Sie können ein Ereignis in advanced Hunting API oder Portal verwenden.</span><span class="sxs-lookup"><span data-stu-id="8dbab-115">You can use an event found in Advanced Hunting API or Portal.</span></span>
<br><span data-ttu-id="8dbab-116">Wenn auf demselben Gerät mit demselben Titel eine offene Warnung vorhanden ist, wird die neu erstellte Warnung mit ihr zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="8dbab-116">If there existing an open alert on the same Device with the same Title, the new created alert will be merged with it.</span></span>
<br><span data-ttu-id="8dbab-117">Eine automatische Untersuchung wird automatisch für Warnungen gestartet, die über die API erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="8dbab-117">An automatic investigation starts automatically on alerts created via the API.</span></span>


## <a name="limitations"></a><span data-ttu-id="8dbab-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8dbab-118">Limitations</span></span>
1. <span data-ttu-id="8dbab-119">Die Geschwindigkeitseinschränkungen für diese API sind 15 Aufrufe pro Minute.</span><span class="sxs-lookup"><span data-stu-id="8dbab-119">Rate limitations for this API are 15 calls per minute.</span></span>


## <a name="permissions"></a><span data-ttu-id="8dbab-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8dbab-120">Permissions</span></span>

<span data-ttu-id="8dbab-121">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8dbab-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8dbab-122">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8dbab-122">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8dbab-123">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="8dbab-123">Permission type</span></span> |   <span data-ttu-id="8dbab-124">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8dbab-124">Permission</span></span>  |   <span data-ttu-id="8dbab-125">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8dbab-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8dbab-126">Anwendung</span><span class="sxs-lookup"><span data-stu-id="8dbab-126">Application</span></span> |   <span data-ttu-id="8dbab-127">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8dbab-127">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="8dbab-128">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="8dbab-128">'Read and write all alerts'</span></span>
<span data-ttu-id="8dbab-129">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="8dbab-129">Delegated (work or school account)</span></span> | <span data-ttu-id="8dbab-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8dbab-130">Alert.ReadWrite</span></span> | <span data-ttu-id="8dbab-131">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="8dbab-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="8dbab-132">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="8dbab-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="8dbab-133">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Warnungsuntersuchung" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="8dbab-133">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="8dbab-134">Der Benutzer muss auf das Gerät zugreifen können, das der Warnung zugeordnet ist, basierend auf den Gerätegruppeneinstellungen (Weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen)</span><span class="sxs-lookup"><span data-stu-id="8dbab-134">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="8dbab-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="8dbab-135">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a><span data-ttu-id="8dbab-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="8dbab-136">Request headers</span></span>

<span data-ttu-id="8dbab-137">Name</span><span class="sxs-lookup"><span data-stu-id="8dbab-137">Name</span></span> | <span data-ttu-id="8dbab-138">Typ</span><span class="sxs-lookup"><span data-stu-id="8dbab-138">Type</span></span> | <span data-ttu-id="8dbab-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8dbab-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="8dbab-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="8dbab-140">Authorization</span></span> | <span data-ttu-id="8dbab-141">String</span><span class="sxs-lookup"><span data-stu-id="8dbab-141">String</span></span> | <span data-ttu-id="8dbab-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8dbab-142">Bearer {token}.</span></span> <span data-ttu-id="8dbab-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8dbab-143">**Required**.</span></span>
<span data-ttu-id="8dbab-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8dbab-144">Content-Type</span></span> | <span data-ttu-id="8dbab-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8dbab-145">String</span></span> | <span data-ttu-id="8dbab-146">application/json.</span><span class="sxs-lookup"><span data-stu-id="8dbab-146">application/json.</span></span> <span data-ttu-id="8dbab-147">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8dbab-147">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8dbab-148">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="8dbab-148">Request body</span></span>

<span data-ttu-id="8dbab-149">Geben Sie im Anforderungstext die folgenden Werte an (alle sind erforderlich):</span><span class="sxs-lookup"><span data-stu-id="8dbab-149">In the request body, supply the following values (all are required):</span></span>

<span data-ttu-id="8dbab-150">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8dbab-150">Property</span></span> | <span data-ttu-id="8dbab-151">Typ</span><span class="sxs-lookup"><span data-stu-id="8dbab-151">Type</span></span> | <span data-ttu-id="8dbab-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8dbab-152">Description</span></span>
:---|:---|:---
<span data-ttu-id="8dbab-153">eventTime</span><span class="sxs-lookup"><span data-stu-id="8dbab-153">eventTime</span></span> | <span data-ttu-id="8dbab-154">DateTime(UTC)</span><span class="sxs-lookup"><span data-stu-id="8dbab-154">DateTime(UTC)</span></span> | <span data-ttu-id="8dbab-155">Die genaue Uhrzeit des Ereignisses als Zeichenfolge, wie von der erweiterten Suche erhalten.</span><span class="sxs-lookup"><span data-stu-id="8dbab-155">The precise time of the event as string, as obtained from advanced hunting.</span></span> <span data-ttu-id="8dbab-156">z. B. ```2018-08-03T16:45:21.7115183Z``` **Erforderlich.**</span><span class="sxs-lookup"><span data-stu-id="8dbab-156">e.g. ```2018-08-03T16:45:21.7115183Z``` **Required**.</span></span>
<span data-ttu-id="8dbab-157">reportId</span><span class="sxs-lookup"><span data-stu-id="8dbab-157">reportId</span></span> | <span data-ttu-id="8dbab-158">String</span><span class="sxs-lookup"><span data-stu-id="8dbab-158">String</span></span> | <span data-ttu-id="8dbab-159">Die reportId des Ereignisses, wie von der erweiterten Suche erhalten.</span><span class="sxs-lookup"><span data-stu-id="8dbab-159">The reportId of the event, as obtained from advanced hunting.</span></span> <span data-ttu-id="8dbab-160">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8dbab-160">**Required**.</span></span>
<span data-ttu-id="8dbab-161">machineId</span><span class="sxs-lookup"><span data-stu-id="8dbab-161">machineId</span></span> | <span data-ttu-id="8dbab-162">String</span><span class="sxs-lookup"><span data-stu-id="8dbab-162">String</span></span> | <span data-ttu-id="8dbab-163">Id des Geräts, auf dem das Ereignis identifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="8dbab-163">Id of the device on which the event was identified.</span></span> <span data-ttu-id="8dbab-164">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8dbab-164">**Required**.</span></span>
<span data-ttu-id="8dbab-165">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="8dbab-165">severity</span></span> | <span data-ttu-id="8dbab-166">String</span><span class="sxs-lookup"><span data-stu-id="8dbab-166">String</span></span> | <span data-ttu-id="8dbab-167">Der Schweregrad der Warnung.</span><span class="sxs-lookup"><span data-stu-id="8dbab-167">Severity of the alert.</span></span> <span data-ttu-id="8dbab-168">Die Eigenschaftswerte sind: "Low", "Medium" und "High".</span><span class="sxs-lookup"><span data-stu-id="8dbab-168">The property values are: 'Low', 'Medium' and 'High'.</span></span> <span data-ttu-id="8dbab-169">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8dbab-169">**Required**.</span></span>
<span data-ttu-id="8dbab-170">title</span><span class="sxs-lookup"><span data-stu-id="8dbab-170">title</span></span> | <span data-ttu-id="8dbab-171">String</span><span class="sxs-lookup"><span data-stu-id="8dbab-171">String</span></span> | <span data-ttu-id="8dbab-172">Titel für die Warnung.</span><span class="sxs-lookup"><span data-stu-id="8dbab-172">Title for the alert.</span></span> <span data-ttu-id="8dbab-173">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8dbab-173">**Required**.</span></span>
<span data-ttu-id="8dbab-174">description</span><span class="sxs-lookup"><span data-stu-id="8dbab-174">description</span></span> | <span data-ttu-id="8dbab-175">String</span><span class="sxs-lookup"><span data-stu-id="8dbab-175">String</span></span> | <span data-ttu-id="8dbab-176">Beschreibung der Warnung.</span><span class="sxs-lookup"><span data-stu-id="8dbab-176">Description of the alert.</span></span> <span data-ttu-id="8dbab-177">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8dbab-177">**Required**.</span></span>
<span data-ttu-id="8dbab-178">recommendedAction</span><span class="sxs-lookup"><span data-stu-id="8dbab-178">recommendedAction</span></span>| <span data-ttu-id="8dbab-179">String</span><span class="sxs-lookup"><span data-stu-id="8dbab-179">String</span></span> | <span data-ttu-id="8dbab-180">Aktion, die vom Sicherheitsbeauftragten bei der Analyse der Warnung empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="8dbab-180">Action that is recommended to be taken by security officer when analyzing the alert.</span></span> <span data-ttu-id="8dbab-181">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8dbab-181">**Required**.</span></span>
<span data-ttu-id="8dbab-182">category</span><span class="sxs-lookup"><span data-stu-id="8dbab-182">category</span></span>| <span data-ttu-id="8dbab-183">String</span><span class="sxs-lookup"><span data-stu-id="8dbab-183">String</span></span> | <span data-ttu-id="8dbab-184">Die Kategorie der Warnung.</span><span class="sxs-lookup"><span data-stu-id="8dbab-184">Category of the alert.</span></span> <span data-ttu-id="8dbab-185">Die Eigenschaftswerte sind: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8dbab-185">The property values are: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span></span>

## <a name="response"></a><span data-ttu-id="8dbab-186">Antwort</span><span class="sxs-lookup"><span data-stu-id="8dbab-186">Response</span></span>

<span data-ttu-id="8dbab-187">Wenn die Methode erfolgreich ist, werden 200 OK und ein neues [Warnungsobjekt](alerts.md) im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8dbab-187">If successful, this method returns 200 OK, and a new [alert](alerts.md) object in the response body.</span></span> <span data-ttu-id="8dbab-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span><span class="sxs-lookup"><span data-stu-id="8dbab-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="8dbab-189">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8dbab-189">Example</span></span>

<span data-ttu-id="8dbab-190">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="8dbab-190">**Request**</span></span>

<span data-ttu-id="8dbab-191">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="8dbab-191">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
