---
title: Erstellen einer Warnung aus der Ereignis-API
description: Erfahren Sie, wie Sie die Api zum Erstellen von Warnungen verwenden, um eine neue Warnung über das Ereignis in Microsoft Defender für Endpunkt zu erstellen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnung, Informationen, ID
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7f8d3b10cee0b3c4a561dfd1f7567fa9818e7686
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289463"
---
# <a name="create-alert-api"></a><span data-ttu-id="35669-104">Erstellen der Warnungs-API</span><span class="sxs-lookup"><span data-stu-id="35669-104">Create alert API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="35669-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="35669-105">**Applies to:**</span></span>
- [<span data-ttu-id="35669-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="35669-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="35669-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35669-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="35669-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="35669-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="35669-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="35669-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="35669-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35669-110">API description</span></span>

<span data-ttu-id="35669-111">Erstellt neue [Warnung](alerts.md) am Anfang des **Ereignisses.**</span><span class="sxs-lookup"><span data-stu-id="35669-111">Creates new [Alert](alerts.md) on top of **Event**.</span></span>

- <span data-ttu-id="35669-112">**Das Microsoft Defender für Endpunkt-Ereignis** ist für die Erstellung von Warnungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="35669-112">**Microsoft Defender for Endpoint Event** is required for the alert creation.</span></span>
- <span data-ttu-id="35669-113">Sie müssen 3 Parameter aus dem Ereignis in der Anforderung angeben: **Ereigniszeit,** **Computer-ID** und **Berichts-ID.**</span><span class="sxs-lookup"><span data-stu-id="35669-113">You will need to supply 3 parameters from the Event in the request: **Event Time**, **Machine ID** and **Report ID**.</span></span> <span data-ttu-id="35669-114">Siehe Beispiel unten.</span><span class="sxs-lookup"><span data-stu-id="35669-114">See example below.</span></span>
- <span data-ttu-id="35669-115">Sie können ein Ereignis in der API für die erweiterte Suche oder im Portal verwenden.</span><span class="sxs-lookup"><span data-stu-id="35669-115">You can use an event found in Advanced Hunting API or Portal.</span></span>
- <span data-ttu-id="35669-116">Wenn auf demselben Gerät mit demselben Titel eine geöffnete Warnung vorhanden ist, wird die neu erstellte Warnung mit ihr zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="35669-116">If there existing an open alert on the same Device with the same Title, the new created alert will be merged with it.</span></span>
- <span data-ttu-id="35669-117">Bei warnungen, die über die API erstellt wurden, wird automatisch eine automatische Untersuchung gestartet.</span><span class="sxs-lookup"><span data-stu-id="35669-117">An automatic investigation starts automatically on alerts created via the API.</span></span>

## <a name="limitations"></a><span data-ttu-id="35669-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="35669-118">Limitations</span></span>

1. <span data-ttu-id="35669-119">Die Rateneinschränkungen für diese API sind 15 Aufrufe pro Minute.</span><span class="sxs-lookup"><span data-stu-id="35669-119">Rate limitations for this API are 15 calls per minute.</span></span>

## <a name="permissions"></a><span data-ttu-id="35669-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="35669-120">Permissions</span></span>

<span data-ttu-id="35669-121">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="35669-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="35669-122">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="35669-122">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="35669-123">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="35669-123">Permission type</span></span> | <span data-ttu-id="35669-124">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="35669-124">Permission</span></span> | <span data-ttu-id="35669-125">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="35669-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="35669-126">Anwendung</span><span class="sxs-lookup"><span data-stu-id="35669-126">Application</span></span> | <span data-ttu-id="35669-127">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="35669-127">Alerts.ReadWrite.All</span></span> | <span data-ttu-id="35669-128">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="35669-128">'Read and write all alerts'</span></span>
<span data-ttu-id="35669-129">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="35669-129">Delegated (work or school account)</span></span> | <span data-ttu-id="35669-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="35669-130">Alert.ReadWrite</span></span> | <span data-ttu-id="35669-131">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="35669-131">'Read and write alerts'</span></span>

> [!NOTE]
> <span data-ttu-id="35669-132">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="35669-132">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="35669-133">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Warnungsuntersuchung" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="35669-133">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="35669-134">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben, das der Warnung zugeordnet ist (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="35669-134">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="35669-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="35669-135">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a><span data-ttu-id="35669-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="35669-136">Request headers</span></span>

<span data-ttu-id="35669-137">Name</span><span class="sxs-lookup"><span data-stu-id="35669-137">Name</span></span> | <span data-ttu-id="35669-138">Typ</span><span class="sxs-lookup"><span data-stu-id="35669-138">Type</span></span> | <span data-ttu-id="35669-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35669-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="35669-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="35669-140">Authorization</span></span> | <span data-ttu-id="35669-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="35669-141">String</span></span> | <span data-ttu-id="35669-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="35669-142">Bearer {token}.</span></span> <span data-ttu-id="35669-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="35669-143">**Required**.</span></span>
<span data-ttu-id="35669-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="35669-144">Content-Type</span></span> | <span data-ttu-id="35669-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="35669-145">String</span></span> | <span data-ttu-id="35669-146">application/json.</span><span class="sxs-lookup"><span data-stu-id="35669-146">application/json.</span></span> <span data-ttu-id="35669-147">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="35669-147">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="35669-148">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="35669-148">Request body</span></span>

<span data-ttu-id="35669-149">Geben Sie im Anforderungstext die folgenden Werte an (alle sind erforderlich):</span><span class="sxs-lookup"><span data-stu-id="35669-149">In the request body, supply the following values (all are required):</span></span>

<span data-ttu-id="35669-150">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="35669-150">Property</span></span> | <span data-ttu-id="35669-151">Typ</span><span class="sxs-lookup"><span data-stu-id="35669-151">Type</span></span> | <span data-ttu-id="35669-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35669-152">Description</span></span>
:---|:---|:---
<span data-ttu-id="35669-153">eventTime</span><span class="sxs-lookup"><span data-stu-id="35669-153">eventTime</span></span> | <span data-ttu-id="35669-154">DateTime(UTC)</span><span class="sxs-lookup"><span data-stu-id="35669-154">DateTime(UTC)</span></span> | <span data-ttu-id="35669-155">Der genaue Zeitpunkt des Ereignisses als Zeichenfolge, wie er von der erweiterten Suche abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="35669-155">The precise time of the event as string, as obtained from advanced hunting.</span></span> <span data-ttu-id="35669-156">z. B. ```2018-08-03T16:45:21.7115183Z``` **Erforderlich.**</span><span class="sxs-lookup"><span data-stu-id="35669-156">e.g. ```2018-08-03T16:45:21.7115183Z``` **Required**.</span></span>
<span data-ttu-id="35669-157">reportId</span><span class="sxs-lookup"><span data-stu-id="35669-157">reportId</span></span> | <span data-ttu-id="35669-158">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="35669-158">String</span></span> | <span data-ttu-id="35669-159">Die reportId des Ereignisses, wie sie von der erweiterten Suche abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="35669-159">The reportId of the event, as obtained from advanced hunting.</span></span> <span data-ttu-id="35669-160">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="35669-160">**Required**.</span></span>
<span data-ttu-id="35669-161">machineId</span><span class="sxs-lookup"><span data-stu-id="35669-161">machineId</span></span> | <span data-ttu-id="35669-162">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="35669-162">String</span></span> | <span data-ttu-id="35669-163">ID des Geräts, auf dem das Ereignis identifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="35669-163">Id of the device on which the event was identified.</span></span> <span data-ttu-id="35669-164">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="35669-164">**Required**.</span></span>
<span data-ttu-id="35669-165">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="35669-165">severity</span></span> | <span data-ttu-id="35669-166">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="35669-166">String</span></span> | <span data-ttu-id="35669-167">Der Schweregrad der Warnung.</span><span class="sxs-lookup"><span data-stu-id="35669-167">Severity of the alert.</span></span> <span data-ttu-id="35669-168">Die Eigenschaftswerte sind: 'Low', 'Medium' und 'High'.</span><span class="sxs-lookup"><span data-stu-id="35669-168">The property values are: 'Low', 'Medium' and 'High'.</span></span> <span data-ttu-id="35669-169">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="35669-169">**Required**.</span></span>
<span data-ttu-id="35669-170">title</span><span class="sxs-lookup"><span data-stu-id="35669-170">title</span></span> | <span data-ttu-id="35669-171">String</span><span class="sxs-lookup"><span data-stu-id="35669-171">String</span></span> | <span data-ttu-id="35669-172">Titel für die Warnung.</span><span class="sxs-lookup"><span data-stu-id="35669-172">Title for the alert.</span></span> <span data-ttu-id="35669-173">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="35669-173">**Required**.</span></span>
<span data-ttu-id="35669-174">description</span><span class="sxs-lookup"><span data-stu-id="35669-174">description</span></span> | <span data-ttu-id="35669-175">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="35669-175">String</span></span> | <span data-ttu-id="35669-176">Beschreibung der Warnung.</span><span class="sxs-lookup"><span data-stu-id="35669-176">Description of the alert.</span></span> <span data-ttu-id="35669-177">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="35669-177">**Required**.</span></span>
<span data-ttu-id="35669-178">recommendedAction</span><span class="sxs-lookup"><span data-stu-id="35669-178">recommendedAction</span></span>| <span data-ttu-id="35669-179">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="35669-179">String</span></span> | <span data-ttu-id="35669-180">Aktion, die vom Sicherheitsbeauftragten bei der Analyse der Warnung empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="35669-180">Action that is recommended to be taken by security officer when analyzing the alert.</span></span> <span data-ttu-id="35669-181">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="35669-181">**Required**.</span></span>
<span data-ttu-id="35669-182">category</span><span class="sxs-lookup"><span data-stu-id="35669-182">category</span></span>| <span data-ttu-id="35669-183">String</span><span class="sxs-lookup"><span data-stu-id="35669-183">String</span></span> | <span data-ttu-id="35669-184">Die Kategorie der Warnung.</span><span class="sxs-lookup"><span data-stu-id="35669-184">Category of the alert.</span></span> <span data-ttu-id="35669-185">Die Eigenschaftswerte sind: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span><span class="sxs-lookup"><span data-stu-id="35669-185">The property values are: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span></span>

## <a name="response"></a><span data-ttu-id="35669-186">Antwort</span><span class="sxs-lookup"><span data-stu-id="35669-186">Response</span></span>

<span data-ttu-id="35669-187">Bei erfolgreicher Ausführung gibt die Methode 200 OK und ein neues [Warnungsobjekt](alerts.md) im Antworttext zurück.</span><span class="sxs-lookup"><span data-stu-id="35669-187">If successful, this method returns 200 OK, and a new [alert](alerts.md) object in the response body.</span></span> <span data-ttu-id="35669-188">Wenn das Ereignis mit den angegebenen Eigenschaften (_reportId_, _eventTime_ und _machineId_) nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="35669-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="35669-189">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35669-189">Example</span></span>

### <a name="request"></a><span data-ttu-id="35669-190">Anforderung</span><span class="sxs-lookup"><span data-stu-id="35669-190">Request</span></span>

<span data-ttu-id="35669-191">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="35669-191">Here is an example of the request.</span></span>

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
