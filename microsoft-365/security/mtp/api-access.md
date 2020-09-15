---
title: Zugreifen auf die Microsoft Threat Protection-APIs
description: Informationen zum Zugriff auf die Microsoft Threat Protection-APIs
keywords: Zugriff, APIs, Anwendungskontext, Benutzerkontext, AAD-Anwendung, Zugriffstoken
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 653c359c324852719688a374a6e863df0a1909ba
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650344"
---
# <a name="access-the-microsoft-threat-protection-apis"></a><span data-ttu-id="cb5f8-104">Zugreifen auf die Microsoft Threat Protection-APIs</span><span class="sxs-lookup"><span data-stu-id="cb5f8-104">Access the Microsoft Threat Protection APIs</span></span>

<span data-ttu-id="cb5f8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cb5f8-105">**Applies to:**</span></span>
- <span data-ttu-id="cb5f8-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cb5f8-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="cb5f8-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cb5f8-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="cb5f8-109">Microsoft Threat Protection macht einen Großteil seiner Daten und Aktionen über eine Reihe von programmgesteuerten APIs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-109">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="cb5f8-110">Mit diesen APIs können Sie Workflows Automatisieren und auf der Grundlage von Microsoft Threat Protection-Funktionen innovativ sein.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="cb5f8-111">Für den API-Zugriff ist die OAuth 2.0-Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="cb5f8-112">Weitere Informationen finden Sie unter [OAuth 2,0-Autorisierungs Code Fluss](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="cb5f8-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="cb5f8-113">Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="cb5f8-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="cb5f8-114">Erstellen einer Aad-Anwendung</span><span class="sxs-lookup"><span data-stu-id="cb5f8-114">Create an AAD application</span></span>
- <span data-ttu-id="cb5f8-115">Abrufen eines Zugriffstokens mithilfe dieser Anwendung</span><span class="sxs-lookup"><span data-stu-id="cb5f8-115">Get an access token using this application</span></span>
- <span data-ttu-id="cb5f8-116">Verwenden des Tokens für den Zugriff auf die Microsoft Threat Protection-API</span><span class="sxs-lookup"><span data-stu-id="cb5f8-116">Use the token to access  Microsoft Threat Protection API</span></span>


<span data-ttu-id="cb5f8-117">Sie können auf Microsoft Threat Protection-API mit **Anwendungskontext** oder **Benutzerkontext**zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-117">You can access  Microsoft Threat Protection API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="cb5f8-118">**Anwendungskontext: (empfohlen)**</span><span class="sxs-lookup"><span data-stu-id="cb5f8-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="cb5f8-119">Wird von apps verwendet, die ohne angemeldeten Benutzer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="cb5f8-120">beispielsweise apps, die als Hintergrunddienste oder Daemons ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="cb5f8-121">Schritte, die für den Zugriff auf die Microsoft Threat Protection-API mit Anwendungskontext ergriffen werden müssen:</span><span class="sxs-lookup"><span data-stu-id="cb5f8-121">Steps that need to be taken to access  Microsoft Threat Protection API with application context:</span></span>

  1. <span data-ttu-id="cb5f8-122">Erstellen Sie eine Aad-Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="cb5f8-123">Zuweisen der gewünschten Berechtigung zum applicationFor-Beispiel, **Incident. Read. all**, **AdvancedHunting. Read. all**.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-123">Assign the desired permission to the applicationFor example, **Incident.Read.All**, **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="cb5f8-124">Erstellen Sie einen Schlüssel für diese Anwendung.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="cb5f8-125">Get-Token mit der Anwendung mit dem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="cb5f8-126">Verwenden des Tokens für den Zugriff auf die Microsoft Threat Protection-API</span><span class="sxs-lookup"><span data-stu-id="cb5f8-126">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="cb5f8-127">Weitere Informationen finden Sie unter [Get Access with Application Context](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="cb5f8-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="cb5f8-128">**Benutzerkontext:**</span><span class="sxs-lookup"><span data-stu-id="cb5f8-128">**User Context:**</span></span> <br>
    <span data-ttu-id="cb5f8-129">Dient zum Ausführen von Aktionen in der API im Namen eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="cb5f8-130">Schritte, die für den Zugriff auf die Microsoft Threat Protection-API mit Anwendungskontext ergriffen werden müssen:</span><span class="sxs-lookup"><span data-stu-id="cb5f8-130">Steps that needs to be taken to access  Microsoft Threat Protection API with application context:</span></span>
  1. <span data-ttu-id="cb5f8-131">Erstellen einer nativen Aad-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="cb5f8-132">Weisen Sie der Anwendung die gewünschte Berechtigung zu.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="cb5f8-133">Beispiel: **Incident. Read**, **AdvancedHunting. Read**.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-133">For example, **Incident.Read**, **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="cb5f8-134">Abrufen eines Tokens mithilfe der Anwendung mit Benutzeranmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="cb5f8-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="cb5f8-135">Verwenden des Tokens für den Zugriff auf die Microsoft Threat Protection-API</span><span class="sxs-lookup"><span data-stu-id="cb5f8-135">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="cb5f8-136">Weitere Informationen finden Sie unter [Get Access with User Context](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="cb5f8-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="cb5f8-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cb5f8-137">Related topics</span></span>
- [<span data-ttu-id="cb5f8-138">Microsoft Threat Protection-APIs</span><span class="sxs-lookup"><span data-stu-id="cb5f8-138">Microsoft Threat Protection APIs</span></span>](api-supported.md)
- [<span data-ttu-id="cb5f8-139">Zugriff auf Microsoft Threat Protection mit Anwendungskontext</span><span class="sxs-lookup"><span data-stu-id="cb5f8-139">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="cb5f8-140">Zugriff auf Microsoft Threat Protection mit Benutzerkontext</span><span class="sxs-lookup"><span data-stu-id="cb5f8-140">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
