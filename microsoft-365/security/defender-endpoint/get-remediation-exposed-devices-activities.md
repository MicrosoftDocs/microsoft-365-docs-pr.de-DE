---
title: Auflisten verfügbarer Geräte einer Korrekturaktivität
description: Gibt Informationen zu verfügbar gemachten Geräten für die angegebene Korrekturaufgabe zurück.
keywords: APIs, Wartung, Korrektur-API, abrufen, Wartungsaufgaben, bereitgestellte Geräte zur Problembehebung
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9b10659f76e5b05bea11f5c6c55ca7c2a34a2db5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772161"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="8c039-104">Auflisten verfügbarer Geräte einer Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="8c039-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8c039-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8c039-105">**Applies to:**</span></span>

- [<span data-ttu-id="8c039-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8c039-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8c039-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c039-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8c039-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="8c039-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8c039-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="8c039-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="8c039-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c039-110">API Description</span></span>

<span data-ttu-id="8c039-111">Gibt Informationen zu verfügbar gemachten Geräten für die angegebene Korrekturaufgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="8c039-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="8c039-112">[Erfahren Sie mehr über Korrekturaktivitäten.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="8c039-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="8c039-113">Auflisten verfügbarer Geräte, die einer Korrekturaufgabe zugeordnet sind (ID)</span><span class="sxs-lookup"><span data-stu-id="8c039-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="8c039-114">**URL:** GET: /api/remediationTasks/id \{ \} /machineReferences</span><span class="sxs-lookup"><span data-stu-id="8c039-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

## <a name="permissions"></a><span data-ttu-id="8c039-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8c039-115">Permissions</span></span>

<span data-ttu-id="8c039-116">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8c039-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8c039-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8c039-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="8c039-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="8c039-118">Permission type</span></span> | <span data-ttu-id="8c039-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8c039-119">Permission</span></span> | <span data-ttu-id="8c039-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8c039-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8c039-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="8c039-121">Application</span></span> | <span data-ttu-id="8c039-122">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="8c039-122">RemediationTask.Read.All</span></span> | <span data-ttu-id="8c039-123">\'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'</span><span class="sxs-lookup"><span data-stu-id="8c039-123">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="8c039-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="8c039-124">Delegated (work or school account)</span></span> | <span data-ttu-id="8c039-125">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="8c039-125">RemediationTask.Read.Read</span></span> | <span data-ttu-id="8c039-126">\'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'</span><span class="sxs-lookup"><span data-stu-id="8c039-126">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties-details"></a><span data-ttu-id="8c039-127">Eigenschaftendetails</span><span class="sxs-lookup"><span data-stu-id="8c039-127">Properties details</span></span>

<span data-ttu-id="8c039-128">Eigenschaft (ID)</span><span class="sxs-lookup"><span data-stu-id="8c039-128">Property (id)</span></span> | <span data-ttu-id="8c039-129">Datentyp</span><span class="sxs-lookup"><span data-stu-id="8c039-129">Data type</span></span> | <span data-ttu-id="8c039-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c039-130">Description</span></span> | <span data-ttu-id="8c039-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c039-131">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="8c039-132">id</span><span class="sxs-lookup"><span data-stu-id="8c039-132">id</span></span> | <span data-ttu-id="8c039-133">String</span><span class="sxs-lookup"><span data-stu-id="8c039-133">String</span></span> | <span data-ttu-id="8c039-134">Geräte-ID</span><span class="sxs-lookup"><span data-stu-id="8c039-134">Device ID</span></span> | <span data-ttu-id="8c039-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="8c039-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="8c039-136">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="8c039-136">computerDnsName</span></span> | <span data-ttu-id="8c039-137">String</span><span class="sxs-lookup"><span data-stu-id="8c039-137">String</span></span> | <span data-ttu-id="8c039-138">Gerätename</span><span class="sxs-lookup"><span data-stu-id="8c039-138">Device name</span></span> | <span data-ttu-id="8c039-139">PC-SRV2012R2Foo.UserNameVldNet.local</span><span class="sxs-lookup"><span data-stu-id="8c039-139">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="8c039-140">osPlatform</span><span class="sxs-lookup"><span data-stu-id="8c039-140">osPlatform</span></span> | <span data-ttu-id="8c039-141">String</span><span class="sxs-lookup"><span data-stu-id="8c039-141">String</span></span> | <span data-ttu-id="8c039-142">Betriebssystem des Geräts</span><span class="sxs-lookup"><span data-stu-id="8c039-142">Device operating system</span></span> | <span data-ttu-id="8c039-143">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="8c039-143">WindowsServer2012R2</span></span>
<span data-ttu-id="8c039-144">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="8c039-144">rbacGroupName</span></span> | <span data-ttu-id="8c039-145">String</span><span class="sxs-lookup"><span data-stu-id="8c039-145">String</span></span> | <span data-ttu-id="8c039-146">Name der Gerätegruppe, der dieses Gerät zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="8c039-146">Name of the device group this device is associated with</span></span> | <span data-ttu-id="8c039-147">Server</span><span class="sxs-lookup"><span data-stu-id="8c039-147">Servers</span></span>

## <a name="example"></a><span data-ttu-id="8c039-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c039-148">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="8c039-149">Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="8c039-149">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a><span data-ttu-id="8c039-150">Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="8c039-150">Response example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        }
]
}
```

## <a name="see-also"></a><span data-ttu-id="8c039-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c039-151">See also</span></span>

- [<span data-ttu-id="8c039-152">Korrekturmethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8c039-152">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="8c039-153">Erhalten einer Korrekturaktivität nach ID</span><span class="sxs-lookup"><span data-stu-id="8c039-153">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="8c039-154">Auflisten aller Korrekturaktivitäten</span><span class="sxs-lookup"><span data-stu-id="8c039-154">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="8c039-155">Risikobasierte Bedrohungs-& Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="8c039-155">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="8c039-156">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="8c039-156">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
