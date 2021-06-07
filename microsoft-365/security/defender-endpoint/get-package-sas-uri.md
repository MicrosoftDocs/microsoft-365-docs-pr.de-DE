---
title: Abrufen der SAS-URI-PAKET-API
description: Verwenden Sie diese API, um einen URI abzurufen, der das Herunterladen eines Untersuchungspakets ermöglicht.
keywords: APIs, Graph-API, unterstützte APIs, Paket abrufen, SAS, URI
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 054db1766cdab3aa5b49da4940dcdddfe6086434
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770685"
---
# <a name="get-package-sas-uri-api"></a><span data-ttu-id="b2514-104">Abrufen der SAS-URI-PAKET-API</span><span class="sxs-lookup"><span data-stu-id="b2514-104">Get package SAS URI API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b2514-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b2514-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b2514-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="b2514-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b2514-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b2514-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="b2514-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2514-108">API description</span></span>
<span data-ttu-id="b2514-109">Rufen Sie einen URI ab, der das Herunterladen eines [Untersuchungspakets](collect-investigation-package.md)ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="b2514-109">Get a URI that allows downloading of an [Investigation package](collect-investigation-package.md).</span></span>


## <a name="permissions"></a><span data-ttu-id="b2514-110">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b2514-110">Permissions</span></span>
<span data-ttu-id="b2514-111">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b2514-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b2514-112">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b2514-112">To learn more, including how to choose permissions, see [Access the Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b2514-113">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="b2514-113">Permission type</span></span> |   <span data-ttu-id="b2514-114">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b2514-114">Permission</span></span>  |   <span data-ttu-id="b2514-115">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b2514-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b2514-116">Anwendung</span><span class="sxs-lookup"><span data-stu-id="b2514-116">Application</span></span> |   <span data-ttu-id="b2514-117">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="b2514-117">Machine.CollectForensics</span></span> |  <span data-ttu-id="b2514-118">"Forensik sammeln"</span><span class="sxs-lookup"><span data-stu-id="b2514-118">'Collect forensics'</span></span>
<span data-ttu-id="b2514-119">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="b2514-119">Delegated (work or school account)</span></span> | <span data-ttu-id="b2514-120">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="b2514-120">Machine.CollectForensics</span></span> | <span data-ttu-id="b2514-121">"Forensik sammeln"</span><span class="sxs-lookup"><span data-stu-id="b2514-121">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="b2514-122">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="b2514-122">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b2514-123">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Warnungsuntersuchung" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="b2514-123">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b2514-124">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="b2514-124">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b2514-125">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="b2514-125">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action id}/getPackageUri
```

## <a name="request-headers"></a><span data-ttu-id="b2514-126">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="b2514-126">Request headers</span></span>

<span data-ttu-id="b2514-127">Name</span><span class="sxs-lookup"><span data-stu-id="b2514-127">Name</span></span> | <span data-ttu-id="b2514-128">Typ</span><span class="sxs-lookup"><span data-stu-id="b2514-128">Type</span></span> | <span data-ttu-id="b2514-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2514-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="b2514-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="b2514-130">Authorization</span></span> | <span data-ttu-id="b2514-131">String</span><span class="sxs-lookup"><span data-stu-id="b2514-131">String</span></span> | <span data-ttu-id="b2514-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b2514-132">Bearer {token}.</span></span> <span data-ttu-id="b2514-133">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b2514-133">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b2514-134">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="b2514-134">Request body</span></span>

<span data-ttu-id="b2514-135">Empty</span><span class="sxs-lookup"><span data-stu-id="b2514-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b2514-136">Antwort</span><span class="sxs-lookup"><span data-stu-id="b2514-136">Response</span></span>

<span data-ttu-id="b2514-137">Bei erfolgreicher Ausführung gibt die Methode den Antwortcode 200,Ok mit dem Objekt zurück, das den Link zum Paket im Parameter "value" enthält.</span><span class="sxs-lookup"><span data-stu-id="b2514-137">If successful, this method returns 200, Ok response code with object that holds the link to the package in the “value” parameter.</span></span> <span data-ttu-id="b2514-138">Dieser Link ist sehr kurz gültig und sollte sofort zum Herunterladen des Pakets in einen lokalen Speicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b2514-138">This link is valid for a very short time and should be used immediately for downloading the package to a local storage.</span></span>


## <a name="example"></a><span data-ttu-id="b2514-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2514-139">Example</span></span>

<span data-ttu-id="b2514-140">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="b2514-140">**Request**</span></span>

<span data-ttu-id="b2514-141">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="b2514-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machineactions/7327b54fd718525cbca07dacde913b5ac3c85673/GetPackageUri

```

<span data-ttu-id="b2514-142">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="b2514-142">**Response**</span></span>

<span data-ttu-id="b2514-143">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="b2514-143">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 Ok
Content-type: application/json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "\"https://userrequests-us.securitycenter.windows.com:443/safedownload/WDATP_Investigation_Package.zip?token=gbDyj7y%2fbWGAZjn2sFiZXlliBTXOCVG7yiJ6mXNaQ9pLByC2Wxeno9mENsPFP3xMk5l%2bZiJXjLvqAyNEzUNROxoM2I1er9dxzfVeBsxSmclJjPsAx%2btiNyxSz1Ax%2b5jaT5cL5bZg%2b8wgbwY9urXbTpGjAKh6FB1e%2b0ypcWkPm8UkfOwsmtC%2biZJ2%2bPqnkkeQk7SKMNoAvmh9%2fcqDIPKXGIBjMa0D9auzypOqd8bQXp7p2BnLSH136BxST8n9IHR4PILvRjAYW9kvtHkBpBitfydAsUW4g2oDZSPN3kCLBOoo1C4w4Lkc9Bc3GNU2IW6dfB7SHcp7G9p4BDkeJl3VuDs6esCaeBorpn9FKJ%2fXo7o9pdcI0hUPZ6Ds9hiPpwPUtz5J29CBE3QAopCK%2fsWlf6OW2WyXsrNRSnF1tVE5H3wXpREzuhD7S4AIA3OIEZKzC4jIPLeMu%2bazZU9xGwuc3gICOaokbwMJiZTqcUuK%2fV9YdBdjdg8wJ16NDU96Pl6%2fgew2KYuk6Wo7ZuHotgHI1abcsvdlpe4AvixDbqcRJthsg2PpLRaFLm5av44UGkeK6TJpFvxUn%2f9fg6Zk5yM1KUTHb8XGmutoCM8U9er6AzXZlY0gGc3D3bQOg41EJZkEZLyUEbk1hXJB36ku2%2bW01cG71t7MxMBYz7%2bdXobxpdo%3d%3bRWS%2bCeoDfTyDcfH5pkCg6hYDmCOPr%2fHYQuaUWUBNVnXURYkdyOzVHqp%2fe%2f1BNyPdVoVkpQHpz1pPS3b5g9h7IMmNKCk5gFq5m2nPx6kk9EYtzx8Ndoa2m9Yj%2bSaf8zIFke86YnfQL4AYewsnQNJJh4wc%2bXxGlBq7axDcoiOdX91rKzVicH3GSBkFoLFAKoegWWsF%2fEDZcVpF%2fXUA1K8HvB6dwyfy4y0sAqnNPxYTQ97mG7yHhxPt4Pe9YF2UPPAJVuEf8LNlQ%2bWHC9%2f7msF6UUI4%2fca%2ftpjFs%2fSNeRE8%2fyQj21TI8YTF1SowvaJuDc1ivEoeopNNGG%2bGI%2fX0SckaVxU9Hdkh0zbydSlT5SZwbSwescs0IpzECitBbaLUz4aT8KTs8T0lvx8D7Te3wVsKAJ1r3iFMQZrlk%2bS1WW8rvac7oHRx2HKURn1v7fDIQWgJr9aNsNlFz4fLJ50T2qSHuuepkLVbe93Va072aMGhvr09WVKoTpAf1j2bcFZZU6Za5PxI32mr0k90FgiYFJ1F%2f1vRDrGwvWVWUkR3Z33m4g0gHa52W1FMxQY0TJIwbovD6FaSNDx7xhKZSd5IJ7r6P91Gez49PaZRcAZPjd%2bfbul3JNm1VqQPTLohT7wa0ymRiXpSST74xtFzuEBzNSNATdbngj3%2fwV4JesTjZjIj5Dc%3d%3blumqauVlFuuO8MQffZgs0tLJ4Fq6fpeozPTdDf8Ll6XLegi079%2b4mSPFjTK0y6eohstxdoOdom2wAHiZwk0u4KLKmRkfYOdT1wHY79qKoBQ3ZDHFTys9V%2fcwKGl%2bl8IenWDutHygn5IcA1y7GTZj4g%3d%3d\""
}
```
