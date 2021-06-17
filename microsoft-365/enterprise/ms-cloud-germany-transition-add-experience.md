---
title: Post-Migrationsaktivitäten für die Migration von Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Zusammenfassung: Post-Migrationsaktivitäten nach der Migration von Microsoft Cloud Germany (Microsoft Cloud Deutschland) nach Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen.'
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930415"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="86a00-103">Post-Migrationsaktivitäten für die Migration von Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="86a00-103">Post-migration activities for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="86a00-104">Die folgenden Abschnitte enthalten Post-Migrationsaktivitäten für mehrere Dienste nach dem Wechsel von Microsoft Cloud Deutschland zu Office 365-Diensten in der neuen deutschen Rechenzentrumsregion.</span><span class="sxs-lookup"><span data-stu-id="86a00-104">The following sections provide post-migration activities for multiple services after moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="86a00-105">Azure AD</span><span class="sxs-lookup"><span data-stu-id="86a00-105">Azure AD</span></span>
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a><span data-ttu-id="86a00-106">Azure AD-Verbundauthentifizierung mit AD FS</span><span class="sxs-lookup"><span data-stu-id="86a00-106">Azure AD federated authentication with AD FS</span></span>
<span data-ttu-id="86a00-107">**Gilt für:** Alle Kunden, die Verbundauthentifizierung mit AD FS verwenden</span><span class="sxs-lookup"><span data-stu-id="86a00-107">**Applies to:** All customers using federated authentication with AD FS</span></span>

| <span data-ttu-id="86a00-108">Schritte:</span><span class="sxs-lookup"><span data-stu-id="86a00-108">Step(s)</span></span> | <span data-ttu-id="86a00-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86a00-109">Description</span></span> | <span data-ttu-id="86a00-110">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="86a00-110">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="86a00-111">Entfernen Sie Vertrauensstellungen der vertrauenden Gruppen aus Microsoft Cloud Deutschland AD FS.</span><span class="sxs-lookup"><span data-stu-id="86a00-111">Remove relying party trusts from Microsoft Cloud Deutschland AD FS.</span></span> | <span data-ttu-id="86a00-112">Nach Abschluss der Übernahmemigration zu Azure AD verwendet die gesamte Organisation Office 365-Dienste und ist nicht mehr mit Microsoft Cloud Deutschland verbunden.</span><span class="sxs-lookup"><span data-stu-id="86a00-112">After the cut-over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="86a00-113">An diesem Punkt muss der Kunde die Vertrauensstellung der vertrauenden Gruppe zu den Microsoft Cloud Deutschland-Endpunkten entfernen.</span><span class="sxs-lookup"><span data-stu-id="86a00-113">At this point, the customer needs to remove the relying party trust to the Microsoft Cloud Deutschland endpoints.</span></span> <span data-ttu-id="86a00-114">Dies kann nur geschehen, wenn keine Anwendungen des Kunden auf Microsoft Cloud Deutschland-Endpunkte verweisen, wenn Azure AD als Identitätsanbieter (Identity Provider, IdP) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="86a00-114">This can only be done when none of the customer's applications points to Microsoft Cloud Deutschland endpoints when Azure AD is leveraged as an Identity Provider (IdP).</span></span> | <span data-ttu-id="86a00-115">Organisationen mit Verbundauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="86a00-115">Federated Authentication organizations</span></span> | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a><span data-ttu-id="86a00-116">Gruppengenehmigungen</span><span class="sxs-lookup"><span data-stu-id="86a00-116">Group approvals</span></span>
<span data-ttu-id="86a00-117">**Gilt für:** Endbenutzer, deren Azure AD-Gruppengenehmigungsanforderungen nicht in den letzten 30 Tagen vor der Migration genehmigt wurden</span><span class="sxs-lookup"><span data-stu-id="86a00-117">**Applies to:** End-users whose Azure AD group approval requests weren't approved in the last 30 days before migration</span></span> 

| <span data-ttu-id="86a00-118">Schritte:</span><span class="sxs-lookup"><span data-stu-id="86a00-118">Step(s)</span></span> | <span data-ttu-id="86a00-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86a00-119">Description</span></span> | <span data-ttu-id="86a00-120">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="86a00-120">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="86a00-121">Anforderungen für den Beitritt einer Azure AD-Gruppe in den letzten 30 Tagen vor der Migration müssen erneut durchgeführt werden, wenn die ursprüngliche Anforderung nicht genehmigt wurde.</span><span class="sxs-lookup"><span data-stu-id="86a00-121">Requests to join an Azure AD group in the last 30 days before migration will need to be requested again if the original request wasn't approved.</span></span> | <span data-ttu-id="86a00-122">Kunden von Endbenutzern müssen den Zugriffsbereich verwenden, um erneut Anforderungen zum Beitritt zu einer Azure AD-Gruppe zu senden, wenn diese Anforderungen in den letzten 30 Tagen vor der Migration nicht genehmigt wurden.</span><span class="sxs-lookup"><span data-stu-id="86a00-122">End-user customers will need to use the Access panel to submit a request to join an Azure AD group again if those requests weren't approved in the last 30 days before the migration.</span></span> |  <span data-ttu-id="86a00-123">Als Endbenutzer:</span><span class="sxs-lookup"><span data-stu-id="86a00-123">As an end-user:</span></span> <ol><li><span data-ttu-id="86a00-124">Navigieren Sie zum [Zugriffsbereich](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span><span class="sxs-lookup"><span data-stu-id="86a00-124">Navigate to [Access panel](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span></span></li><li><span data-ttu-id="86a00-125">Suchen Sie eine Azure AD-Gruppe, für die innerhalb von 30 Tagen vor der Migration eine Mitgliedschaftsgenehmigung ausstehend war.</span><span class="sxs-lookup"><span data-stu-id="86a00-125">Find an Azure AD group for which membership approval was pending during the 30 days before migration.</span></span></li><li><span data-ttu-id="86a00-126">Fordern Sie den Beitritt zur Azure AD-Gruppe erneut an.</span><span class="sxs-lookup"><span data-stu-id="86a00-126">Request to join the Azure AD group again.</span></span></li></ol> <span data-ttu-id="86a00-127">Anforderungen zum Betritt zu einer Gruppe, die weniger als 30 Tage vor der Migration aktiv sind, können nicht genehmigt werden, es sei denn, sie werden nach der Migration wiederholt.</span><span class="sxs-lookup"><span data-stu-id="86a00-127">Requests to join a group that are active less than 30 days before migration cannot be approved, unless they're requested again after migration.</span></span> |
||||

## <a name="custom-dns-updates"></a><span data-ttu-id="86a00-128">Benutzerdefinierte DNS-Updates</span><span class="sxs-lookup"><span data-stu-id="86a00-128">Custom DNS updates</span></span>
<span data-ttu-id="86a00-129">**Gilt für:** Alle Kunden, die ihre eigenen DNS-Zonen verwalten</span><span class="sxs-lookup"><span data-stu-id="86a00-129">**Applies to:**  All customer managing their own DNS zones</span></span>

| <span data-ttu-id="86a00-130">Schritte:</span><span class="sxs-lookup"><span data-stu-id="86a00-130">Step(s)</span></span> | <span data-ttu-id="86a00-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86a00-131">Description</span></span> | <span data-ttu-id="86a00-132">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="86a00-132">Impact</span></span> |
|:------|:-------|:-------|
| <span data-ttu-id="86a00-133">Aktualisieren Sie lokale DNS-Dienste für Office 365-Dienstendpunkte.</span><span class="sxs-lookup"><span data-stu-id="86a00-133">Update on-premises DNS services for Office 365 services endpoints.</span></span> | <span data-ttu-id="86a00-134">Vom Kunden verwaltete DNS-Einträge, die auf Microsoft Cloud Deutschland verweisen, müssen aktualisiert werden, damit sie auf die Office 365 Global-Dienstendpunkte verweisen.</span><span class="sxs-lookup"><span data-stu-id="86a00-134">Customer-managed DNS entries that point to Microsoft Cloud Deutschland need to be updated to point to the Office 365 Global services endpoints.</span></span> <span data-ttu-id="86a00-135">Bitte schlagen Sie unter [Domänen im Microsoft 365 Admin Center](https://admin.microsoft.com/Adminportal/Home#/Domains) nach und übernehmen Sie die Änderungen in Ihre DNS-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="86a00-135">Please refer to [Domains in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home#/Domains) and apply the changes in your DNS configuration.</span></span> | <span data-ttu-id="86a00-136">Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Software-Clients führen.</span><span class="sxs-lookup"><span data-stu-id="86a00-136">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="third-party-services"></a><span data-ttu-id="86a00-137">Drittanbieterdienste</span><span class="sxs-lookup"><span data-stu-id="86a00-137">Third-party services</span></span>
<span data-ttu-id="86a00-138">**Gilt für:** Kunden, die Drittanbieterdienste für Office 365-Dienstendpunkte verwenden.</span><span class="sxs-lookup"><span data-stu-id="86a00-138">**Applies to:** Customers using third-party services for Office 365 services endpoints</span></span>

| <span data-ttu-id="86a00-139">Schritte:</span><span class="sxs-lookup"><span data-stu-id="86a00-139">Step(s)</span></span> | <span data-ttu-id="86a00-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86a00-140">Description</span></span> | <span data-ttu-id="86a00-141">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="86a00-141">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="86a00-142">Aktualisieren Sie Partner und Drittanbieterdienste für Office 365-Dienstendpunkte.</span><span class="sxs-lookup"><span data-stu-id="86a00-142">Update partners and third-party services for Office 365 services endpoints.</span></span> | <ul><li><span data-ttu-id="86a00-143">Drittanbieterdienste und Partner, die auf Office 365 Deutschland verweisen, müssen aktualisiert werden, damit sie auf die Office 365-Dienstendpunkte verweisen.</span><span class="sxs-lookup"><span data-stu-id="86a00-143">Third-party services and partners that point to Office 365 Germany need to be updated to point to the Office 365 services endpoints.</span></span> <span data-ttu-id="86a00-144">Beispiel: Registrieren Sie die Galerie-App-Version der Anwendungen, falls verfügbar, in Übereinstimmung mit Ihren Anbietern und Partnern neu.</span><span class="sxs-lookup"><span data-stu-id="86a00-144">Example: Re-register, in alignment with your vendors and partners, the gallery app version of applications, if available.</span></span> </li><li><span data-ttu-id="86a00-145">Verweisen Sie alle benutzerdefinierten Anwendungen, die die Graph-API von `graph.microsoft.de` verwenden, auf `graph.microsoft.com`.</span><span class="sxs-lookup"><span data-stu-id="86a00-145">Point all custom applications that leverage Graph API from `graph.microsoft.de` to `graph.microsoft.com`.</span></span> <span data-ttu-id="86a00-146">Andere APIs mit geänderten Endpunkten müssen ebenfalls aktualisiert werden, falls sie genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="86a00-146">Other APIs with changed endpoints also need to be updated, if leveraged.</span></span> </li><li><span data-ttu-id="86a00-147">Ändern Sie alle Unternehmensanwendungen von Drittanbietern so, dass sie zu den weltweiten Endpunkten umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="86a00-147">Change all non-first-party enterprise applications to redirect to the worldwide endpoints.</span></span> </li></ul>| <span data-ttu-id="86a00-p105">Erforderliche Aktion. Wird diese Aktion nicht ausgeführt, kann dies zu einem Ausfall des Diensts oder der Softwareclients führen.</span><span class="sxs-lookup"><span data-stu-id="86a00-p105">Required action. Failure to do so may result in failure of the service or of software clients.</span></span> |
||||