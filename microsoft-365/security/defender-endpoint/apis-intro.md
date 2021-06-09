---
title: Zugreifen auf die Microsoft Defender für Endpoint-APIs
ms.reviewer: ''
description: Erfahren Sie, wie Sie APIs verwenden können, um Workflows zu automatisieren und Innovationen basierend auf den Microsoft Defender für Endpunkt-Funktionen zu automatisieren.
keywords: APIs, API, wdatp, offene API, Microsoft Defender für Endpunkt-API, Microsoft Defender atp, öffentliche API, unterstützte APIs, Warnungen, Gerät, Benutzer, Domäne, IP, Datei, erweiterte Suche, Abfrage
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9d3f4431825193d189f7ea1d73b6a99163cac428
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843698"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="4562d-104">Zugreifen auf die Microsoft Defender für Endpoint-APIs</span><span class="sxs-lookup"><span data-stu-id="4562d-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4562d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4562d-105">**Applies to:**</span></span>
- [<span data-ttu-id="4562d-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4562d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4562d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4562d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="4562d-108">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4562d-108">**Applies to:**</span></span> 
- [<span data-ttu-id="4562d-109">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4562d-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="4562d-110">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="4562d-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4562d-111">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4562d-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="4562d-112">Defender für Endpunkt macht einen Großteil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4562d-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="4562d-113">Diese APIs ermöglichen es Ihnen, Workflows zu automatisieren und Innovationen basierend auf den Defender für Endpunkt-Funktionen zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="4562d-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="4562d-114">Der API-Zugriff erfordert die OAuth2.0-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4562d-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="4562d-115">Weitere Informationen finden Sie unter [OAuth 2.0-Autorisierungscode Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="4562d-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="4562d-116">Sehen Sie sich dieses Video an, um einen schnellen Überblick über die APIs von Defender für Endpunkt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4562d-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="4562d-117">Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="4562d-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="4562d-118">Erstellen einer [AAD-Anwendung](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span><span class="sxs-lookup"><span data-stu-id="4562d-118">Create an [AAD application](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span></span>
- <span data-ttu-id="4562d-119">Abrufen eines Zugriffstokens mithilfe dieser Anwendung</span><span class="sxs-lookup"><span data-stu-id="4562d-119">Get an access token using this application</span></span>
- <span data-ttu-id="4562d-120">Verwenden des Tokens für den Zugriff auf die Defender für Endpunkt-API</span><span class="sxs-lookup"><span data-stu-id="4562d-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="4562d-121">Sie können auf die Defender für Endpunkt-API mit **Anwendungskontext** oder **Benutzerkontext** zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4562d-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="4562d-122">**Anwendungskontext: (Empfohlen)**</span><span class="sxs-lookup"><span data-stu-id="4562d-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="4562d-123">Wird von Apps verwendet, die ohne angemeldeten Benutzer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4562d-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="4562d-124">Beispielsweise Apps, die als Hintergrunddienste oder Daemons ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4562d-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="4562d-125">Schritte, die für den Zugriff auf die Defender für Endpunkt-API mit Anwendungskontext ausgeführt werden müssen:</span><span class="sxs-lookup"><span data-stu-id="4562d-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="4562d-126">Erstellen Sie eine AAD-Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="4562d-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="4562d-127">Weisen Sie der Anwendung die gewünschte Berechtigung zu, z. B. "Warnungen lesen", "Computer isolieren".</span><span class="sxs-lookup"><span data-stu-id="4562d-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="4562d-128">Erstellen Sie einen Schlüssel für diese Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4562d-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="4562d-129">Token mithilfe der Anwendung mit ihrem Schlüssel abrufen.</span><span class="sxs-lookup"><span data-stu-id="4562d-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="4562d-130">Verwenden des Tokens für den Zugriff auf die Microsoft Defender für Endpunkt-API</span><span class="sxs-lookup"><span data-stu-id="4562d-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="4562d-131">Weitere Informationen finden Sie unter ["Zugriff mit Anwendungskontext erhalten".](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="4562d-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="4562d-132">**Benutzerkontext:**</span><span class="sxs-lookup"><span data-stu-id="4562d-132">**User Context:**</span></span> <br>
    <span data-ttu-id="4562d-133">Wird verwendet, um Aktionen in der API im Auftrag eines Benutzers auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4562d-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="4562d-134">Schritte für den Zugriff auf die Defender für Endpunkt-API mit Anwendungskontext:</span><span class="sxs-lookup"><span data-stu-id="4562d-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="4562d-135">Erstellen Sie AAD Native-Application.</span><span class="sxs-lookup"><span data-stu-id="4562d-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="4562d-136">Weisen Sie der Anwendung die gewünschte Berechtigung zu, z. B. "Warnungen lesen", "Computer isolieren" usw.</span><span class="sxs-lookup"><span data-stu-id="4562d-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="4562d-137">Token mithilfe der Anwendung mit Benutzeranmeldeinformationen abrufen.</span><span class="sxs-lookup"><span data-stu-id="4562d-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="4562d-138">Verwenden des Tokens für den Zugriff auf die Microsoft Defender für Endpunkt-API</span><span class="sxs-lookup"><span data-stu-id="4562d-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="4562d-139">Weitere Informationen finden Sie unter ["Zugriff mit Benutzerkontext erhalten".](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="4562d-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="4562d-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4562d-140">Related topics</span></span>
- [<span data-ttu-id="4562d-141">Microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="4562d-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="4562d-142">Zugreifen auf Microsoft Defender für Endpunkt mit Anwendungskontext</span><span class="sxs-lookup"><span data-stu-id="4562d-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="4562d-143">Zugreifen auf Microsoft Defender für Endpunkt mit Benutzerkontext</span><span class="sxs-lookup"><span data-stu-id="4562d-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
