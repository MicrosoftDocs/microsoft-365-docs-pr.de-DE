---
title: Zugreifen auf die Microsoft Defender für Endpoint-APIs
ms.reviewer: ''
description: Erfahren Sie, wie Sie APIs verwenden können, um Workflows zu automatisieren und Innovationen basierend auf Microsoft Defender for Endpoint-Funktionen zu entwickeln.
keywords: apis, api, Microsoft Defender for Endpoint, open api, Microsoft Defender for Endpoint api, public api, supported apis, alerts, device, user, domain, ip, file, advanced hunting, query
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 87dce8ff4fde505eb8d4e458c8d9fb56556f4d78
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935105"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="597be-104">Zugreifen auf die Microsoft Defender für Endpoint-APIs</span><span class="sxs-lookup"><span data-stu-id="597be-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="597be-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="597be-105">**Applies to:**</span></span>
- [<span data-ttu-id="597be-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="597be-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="597be-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="597be-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="597be-108">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="597be-108">**Applies to:**</span></span> 
- [<span data-ttu-id="597be-109">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="597be-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="597be-110">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="597be-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="597be-111">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="597be-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="597be-112">Defender for Endpoint macht einen großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="597be-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="597be-113">Mit diesen APIs können Sie Workflows automatisieren und innovationen basierend auf defender for Endpoint-Funktionen entwickeln.</span><span class="sxs-lookup"><span data-stu-id="597be-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="597be-114">Für den API-Zugriff ist die OAuth2.0-Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="597be-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="597be-115">Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="597be-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="597be-116">Sehen Sie sich dieses Video an, um einen schnellen Überblick über die APIs von Defender for Endpoint zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="597be-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="597be-117">Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="597be-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="597be-118">Erstellen einer AAD-Anwendung</span><span class="sxs-lookup"><span data-stu-id="597be-118">Create an AAD application</span></span>
- <span data-ttu-id="597be-119">Zugreifen auf ein Zugriffstoken mithilfe dieser Anwendung</span><span class="sxs-lookup"><span data-stu-id="597be-119">Get an access token using this application</span></span>
- <span data-ttu-id="597be-120">Verwenden des Tokens für den Zugriff auf die Defender for Endpoint-API</span><span class="sxs-lookup"><span data-stu-id="597be-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="597be-121">Sie können auf defender for Endpoint-API **mit Anwendungskontext oder** **Benutzerkontext zugreifen.**</span><span class="sxs-lookup"><span data-stu-id="597be-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="597be-122">**Anwendungskontext: (Empfohlen)**</span><span class="sxs-lookup"><span data-stu-id="597be-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="597be-123">Wird von Apps verwendet, die ohne angemeldeten Benutzer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="597be-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="597be-124">Beispielsweise Apps, die als Hintergrunddienste oder Daemons ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="597be-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="597be-125">Schritte, die für den Zugriff auf die Defender for Endpoint-API mit Anwendungskontext erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="597be-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="597be-126">Erstellen Sie eine AAD-Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="597be-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="597be-127">Weisen Sie der Anwendung die gewünschte Berechtigung zu, z. B. "Warnungen lesen", "Computer isolieren".</span><span class="sxs-lookup"><span data-stu-id="597be-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="597be-128">Erstellen Sie einen Schlüssel für diese Anwendung.</span><span class="sxs-lookup"><span data-stu-id="597be-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="597be-129">Token mit der Anwendung mit ihrem Schlüssel abzurufen.</span><span class="sxs-lookup"><span data-stu-id="597be-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="597be-130">Verwenden des Tokens für den Zugriff auf Die Microsoft Defender for Endpoint-API</span><span class="sxs-lookup"><span data-stu-id="597be-130">Use the token to access Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="597be-131">Weitere Informationen finden Sie unter [Zugriff mit Anwendungskontext erhalten.](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="597be-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="597be-132">**Benutzerkontext:**</span><span class="sxs-lookup"><span data-stu-id="597be-132">**User Context:**</span></span> <br>
    <span data-ttu-id="597be-133">Wird verwendet, um Aktionen in der API im Namen eines Benutzers durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="597be-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="597be-134">Schritte zum Zugreifen auf die Defender for Endpoint-API mit Anwendungskontext:</span><span class="sxs-lookup"><span data-stu-id="597be-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="597be-135">Erstellen Sie AAD Native-Application.</span><span class="sxs-lookup"><span data-stu-id="597be-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="597be-136">Weisen Sie der Anwendung die gewünschte Berechtigung zu, z. B. "Warnungen lesen", "Computer isolieren" usw.</span><span class="sxs-lookup"><span data-stu-id="597be-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="597be-137">Token mithilfe der Anwendung mit Benutzeranmeldeinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="597be-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="597be-138">Verwenden des Tokens für den Zugriff auf Die Microsoft Defender for Endpoint-API</span><span class="sxs-lookup"><span data-stu-id="597be-138">Use the token to access Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="597be-139">Weitere Informationen finden Sie unter [Get access with user context](exposed-apis-create-app-nativeapp.md).</span><span class="sxs-lookup"><span data-stu-id="597be-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="597be-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="597be-140">Related topics</span></span>
- [<span data-ttu-id="597be-141">Microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="597be-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="597be-142">Zugreifen auf Microsoft Defender for Endpoint mit Anwendungskontext</span><span class="sxs-lookup"><span data-stu-id="597be-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="597be-143">Zugreifen auf Microsoft Defender for Endpoint mit Benutzerkontext</span><span class="sxs-lookup"><span data-stu-id="597be-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
