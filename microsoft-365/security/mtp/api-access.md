---
title: Zugreifen auf die Microsoft 365 Defender-APIs
description: Informationen zum Zugreifen auf die Microsoft 365 Defender-APIs
keywords: Zugriff, APIs, Anwendungskontext, Benutzerkontext, AAD-Anwendung, Zugriffstoken
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ea787adfba0afb425da5f6ea0f6609f96e06b378
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932154"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="2e5ab-104">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="2e5ab-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2e5ab-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2e5ab-105">**Applies to:**</span></span>

- <span data-ttu-id="2e5ab-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e5ab-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e5ab-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2e5ab-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2e5ab-109">Microsoft 365 Defender macht einen Großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="2e5ab-110">Mit diesen APIs können Sie Workflows automatisieren und die Funktionen von Microsoft 365 Defender vollständig nutzen.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="2e5ab-111">Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="2e5ab-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="2e5ab-112">Erstellen einer Azure Active Directory-Anwendung</span><span class="sxs-lookup"><span data-stu-id="2e5ab-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="2e5ab-113">Erhalten eines Zugriffstokens mithilfe dieser Anwendung</span><span class="sxs-lookup"><span data-stu-id="2e5ab-113">Get an access token using this application</span></span>
- <span data-ttu-id="2e5ab-114">Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API</span><span class="sxs-lookup"><span data-stu-id="2e5ab-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="2e5ab-115">Für den Zugriff auf die API ist die OAuth2.0-Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="2e5ab-116">Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="2e5ab-116">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="2e5ab-117">Nachdem Sie diese Schritte durchgeführt haben, können Sie mithilfe eines bestimmten Kontexts auf die Microsoft 365 Defender-API zugreifen.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="2e5ab-118">Anwendungskontext (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="2e5ab-118">Application context (Recommended)</span></span>

<span data-ttu-id="2e5ab-119">Verwenden Sie diesen Kontext für Apps, die ohne angemeldeten Benutzer ausgeführt werden, z. B. Hintergrunddienste oder Daemons.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="2e5ab-120">Erstellen Sie eine Azure Active Directory-Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="2e5ab-121">Weisen Sie der Anwendung die gewünschten Berechtigungen zu.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="2e5ab-122">Erstellen Sie einen Schlüssel für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-122">Create a key for the application.</span></span>
4. <span data-ttu-id="2e5ab-123">Mit der Anwendung und ihrem Schlüssel können Sie ein Sicherheitstoken erhalten.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="2e5ab-124">Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="2e5ab-125">Weitere Informationen finden Sie unter **["Erstellen einer App für den Zugriff auf Microsoft 365 Defender ohne Benutzer".](api-create-app-web.md)**</span><span class="sxs-lookup"><span data-stu-id="2e5ab-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="2e5ab-126">Benutzerkontext</span><span class="sxs-lookup"><span data-stu-id="2e5ab-126">User context</span></span>

<span data-ttu-id="2e5ab-127">Verwenden Sie diesen Kontext, um Aktionen im Auftrag eines einzelnen Benutzers durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="2e5ab-128">Erstellen Sie eine systemeigene Azure Active Directory-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="2e5ab-129">Weisen Sie der Anwendung die gewünschte Berechtigung zu.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="2e5ab-130">Mit den Benutzeranmeldeinformationen für die Anwendung können Sie ein Sicherheitstoken erhalten.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="2e5ab-131">Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="2e5ab-132">Weitere Informationen finden Sie unter Erstellen einer App für den Zugriff auf **[Microsoft 365 Defender-APIs im Namen eines Benutzers.](api-create-app-user-context.md)**</span><span class="sxs-lookup"><span data-stu-id="2e5ab-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="2e5ab-133">Partnerkontext</span><span class="sxs-lookup"><span data-stu-id="2e5ab-133">Partner context</span></span>

<span data-ttu-id="2e5ab-134">Verwenden Sie diesen Kontext, wenn Sie eine App für viele Benutzer in [mehreren Mandanten bereitstellen müssen.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)</span><span class="sxs-lookup"><span data-stu-id="2e5ab-134">Use this context when you need to provide an app to many users across [multiple tenants](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="2e5ab-135">Erstellen Sie eine mehrstufige Azure Active Directory-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="2e5ab-136">Weisen Sie der Anwendung die gewünschte Berechtigung zu.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="2e5ab-137">Erhalten [Sie die Administratoreinwilligung](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) für die App von jedem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-137">Get [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="2e5ab-138">Erhalten Sie ein Sicherheitstoken mithilfe von Benutzeranmeldeinformationen basierend auf der Mandanten-ID eines Kunden.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="2e5ab-139">Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="2e5ab-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="2e5ab-140">Weitere Informationen finden Sie unter **[Erstellen einer App mit Partnerzugriff auf Microsoft 365 Defender-APIs.](api-partner-access.md)**</span><span class="sxs-lookup"><span data-stu-id="2e5ab-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2e5ab-141">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="2e5ab-141">Related articles</span></span>

- [<span data-ttu-id="2e5ab-142">Übersicht über Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="2e5ab-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="2e5ab-143">OAuth 2.0-Autorisierung für die Benutzerauthentifizierung und den Zugriff auf die API</span><span class="sxs-lookup"><span data-stu-id="2e5ab-143">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="2e5ab-144">Verwalten von geheimen Schlüsseln in Ihren Server-Apps mit Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="2e5ab-144">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="2e5ab-145">Erstellen einer "Hello world"-Anwendung, die auf die Microsoft 365-APIs zu zugegriffen hat</span><span class="sxs-lookup"><span data-stu-id="2e5ab-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)
