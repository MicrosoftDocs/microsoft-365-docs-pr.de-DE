---
title: Bereitstellen des Zugriffs auf verwaltete Sicherheitsdienstanbieter (Managed Security Service Provider, MSSP)
description: Erfahren Sie mehr über Änderungen vom Microsoft Defender Security Center zum Microsoft 365 Security Center
keywords: Erste Schritte mit dem Microsoft 365 Security Center, Microsoft Defender für Office 365, Microsoft Defender für Endpunkt, MDO, MDE, einzelner Bereich, konvergentes Portal, Sicherheitsportal, Defender-Sicherheitsportal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: ddc28149ca2ab43b7c14d3bdbaeeecdad1b18387
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289763"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="12cfc-104">Bereitstellen des Zugriffs auf verwaltete Sicherheitsdienstanbieter (Managed Security Service Provider, MSSP)</span><span class="sxs-lookup"><span data-stu-id="12cfc-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="12cfc-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="12cfc-105">**Applies to:**</span></span>

- [<span data-ttu-id="12cfc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12cfc-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="12cfc-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="12cfc-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="12cfc-108">Führen Sie die folgenden Schritte aus, um eine mehrinstanzenfähige lösung für delegierten Zugriff zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="12cfc-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="12cfc-109">Aktivieren Sie die [rollenbasierte Zugriffssteuerung](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender für Endpunkt im Microsoft 365 Security Center, und stellen Sie eine Verbindung mit Azure Active Directory (Azure AD)-Gruppen her.</span><span class="sxs-lookup"><span data-stu-id="12cfc-109">Enable [role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="12cfc-110">Konfigurieren von [Governance-Zugriffspaketen](/azure/active-directory/governance/identity-governance-overview) für Zugriffsanfragen und -bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="12cfc-110">Configure [Governance Access Packages](/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="12cfc-111">Verwalten von Zugriffsanforderungen und Überwachungen in [Microsoft Myaccess.](/azure/active-directory/governance/entitlement-management-request-approve)</span><span class="sxs-lookup"><span data-stu-id="12cfc-111">Manage access requests and audits in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="12cfc-112">Aktivieren von rollenbasierten Zugriffssteuerungen in Microsoft Defender für Endpunkt im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="12cfc-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="12cfc-113">**Erstellen von Zugriffsgruppen für MSSP-Ressourcen in Customer AAD: Groups**</span><span class="sxs-lookup"><span data-stu-id="12cfc-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="12cfc-114">Diese Gruppen werden mit den Rollen verknüpft, die Sie in Defender für Endpunkt im Microsoft 365 Security Center erstellen.</span><span class="sxs-lookup"><span data-stu-id="12cfc-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="12cfc-115">Erstellen Sie dazu im AD-Mandanten des Kunden drei Gruppen.</span><span class="sxs-lookup"><span data-stu-id="12cfc-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="12cfc-116">In unserem Beispielansatz erstellen wir die folgenden Gruppen:</span><span class="sxs-lookup"><span data-stu-id="12cfc-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="12cfc-117">Analyst der Stufe 1</span><span class="sxs-lookup"><span data-stu-id="12cfc-117">Tier 1 Analyst</span></span>
    - <span data-ttu-id="12cfc-118">Analyst der Stufe 2</span><span class="sxs-lookup"><span data-stu-id="12cfc-118">Tier 2 Analyst</span></span>
    - <span data-ttu-id="12cfc-119">Genehmiger für MSSP-Analysten</span><span class="sxs-lookup"><span data-stu-id="12cfc-119">MSSP Analyst Approvers</span></span>  

2. <span data-ttu-id="12cfc-120">Erstellen Sie Defender für Endpunkt-Rollen für die entsprechenden Zugriffsebenen in Customer Defender für Endpunkt in Microsoft 365 Sicherheitscenterrollen und -gruppen.</span><span class="sxs-lookup"><span data-stu-id="12cfc-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="12cfc-121">Um RBAC im Kunden-Microsoft 365 Security Center zu aktivieren, greifen Sie auf **Die Rollen "Berechtigungen > Endpunkte" & Gruppen > Rollen** mit einem Benutzerkonto mit globalen Administrator- oder Sicherheitsadministratorrechten zu.</span><span class="sxs-lookup"><span data-stu-id="12cfc-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Abbildung des MSSP-Zugriffs](../../media/mssp-access.png)

    <span data-ttu-id="12cfc-123">Erstellen Sie dann RBAC-Rollen, um die Anforderungen der MSSP-SOC-Ebene zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="12cfc-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="12cfc-124">Verknüpfen Sie diese Rollen mit den erstellten Benutzergruppen über "Zugewiesene Benutzergruppen".</span><span class="sxs-lookup"><span data-stu-id="12cfc-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="12cfc-125">Zwei mögliche Rollen:</span><span class="sxs-lookup"><span data-stu-id="12cfc-125">Two possible roles:</span></span>

    - <span data-ttu-id="12cfc-126">**Analysten der Stufe 1**</span><span class="sxs-lookup"><span data-stu-id="12cfc-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="12cfc-127">Führen Sie alle Aktionen mit Ausnahme von Liveantworten aus, und verwalten Sie Sicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="12cfc-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="12cfc-128">**Analysten der Stufe 2**</span><span class="sxs-lookup"><span data-stu-id="12cfc-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="12cfc-129">Funktionen der Stufe 1 mit zusätzlicher [Liveantwort](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="12cfc-129">Tier 1 capabilities with the addition to [live response](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="12cfc-130">Weitere Informationen finden Sie unter [Verwenden der rollenbasierten Zugriffssteuerung.](/windows/security/threat-protection/microsoft-defender-atp/rbac)</span><span class="sxs-lookup"><span data-stu-id="12cfc-130">For more information, see [Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>

## <a name="configure-governance-access-packages"></a><span data-ttu-id="12cfc-131">Konfigurieren von Governance-Zugriffspaketen</span><span class="sxs-lookup"><span data-stu-id="12cfc-131">Configure Governance Access Packages</span></span>

1. <span data-ttu-id="12cfc-132">**Hinzufügen von MSSP als verbundene Organisation in Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="12cfc-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="12cfc-133">Das Hinzufügen des MSSP als verbundene Organisation ermöglicht es dem MSSP, Zugriffe anzufordern und bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="12cfc-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="12cfc-134">Greifen Sie dazu im AD-Mandanten des Kunden auf Identity Governance: verbundene Organisation zu.</span><span class="sxs-lookup"><span data-stu-id="12cfc-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="12cfc-135">Fügen Sie eine neue Organisation hinzu, und suchen Sie nach Ihrem MSSP-Analystenmandanten über die Mandanten-ID oder Domäne.</span><span class="sxs-lookup"><span data-stu-id="12cfc-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="12cfc-136">Wir empfehlen, einen separaten AD-Mandanten für Ihre MSSP-Analysten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="12cfc-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="12cfc-137">**Erstellen eines Ressourcenkatalogs in Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="12cfc-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="12cfc-138">Ressourcenkataloge sind eine logische Sammlung von Zugriffspaketen, die im AD-Mandanten des Kunden erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="12cfc-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="12cfc-139">Greifen Sie dazu im AD-Mandanten des Kunden auf Identity Governance: Kataloge zu, und fügen Sie **neuen Katalog** hinzu.</span><span class="sxs-lookup"><span data-stu-id="12cfc-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="12cfc-140">In unserem Beispiel wird es **MSSP Accesses** nennen.</span><span class="sxs-lookup"><span data-stu-id="12cfc-140">In our example, we will call it **MSSP Accesses**.</span></span>

    ![Abbildung des neuen Katalogs](../../media/goverance-catalog.png)

    <span data-ttu-id="12cfc-142">Weitere Informationen finden Sie unter [Erstellen eines Ressourcenkatalogs.](/azure/active-directory/governance/entitlement-management-catalog-create)</span><span class="sxs-lookup"><span data-stu-id="12cfc-142">Further more information, see [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>

3. <span data-ttu-id="12cfc-143">**Erstellen von Zugriffspaketen für MSSP-Ressourcen Kunden-AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="12cfc-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="12cfc-144">Zugriffspakete sind die Sammlung von Rechten und Zugriffen, die einem Anforderer nach Genehmigung gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="12cfc-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="12cfc-145">Greifen Sie dazu im AD-Mandanten des Kunden auf Identity Governance zu: Zugriffspakete, und fügen Sie **ein neues Zugriffspaket hinzu.**</span><span class="sxs-lookup"><span data-stu-id="12cfc-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="12cfc-146">Erstellen Sie ein Zugriffspaket für die MSSP-Genehmiger und jede Analystenebene.</span><span class="sxs-lookup"><span data-stu-id="12cfc-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="12cfc-147">Die folgende Analystenkonfiguration der Stufe 1 erstellt beispielsweise ein Zugriffspaket, das:</span><span class="sxs-lookup"><span data-stu-id="12cfc-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="12cfc-148">Erfordert ein Mitglied der AD-Gruppe **MSSP Analyst Approvers,** um neue Anforderungen zu autorisieren</span><span class="sxs-lookup"><span data-stu-id="12cfc-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="12cfc-149">Verfügt über jährliche Zugriffsüberprüfungen, bei denen die SOC-Analysten eine Zugriffserweiterung anfordern können.</span><span class="sxs-lookup"><span data-stu-id="12cfc-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="12cfc-150">Kann nur von Benutzern im MSSP-SOC-Mandanten angefordert werden</span><span class="sxs-lookup"><span data-stu-id="12cfc-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="12cfc-151">Automatischer Zugriff läuft nach 365 Tagen ab</span><span class="sxs-lookup"><span data-stu-id="12cfc-151">Access auto expires after 365 days</span></span>

    ![Abbildung des neuen Zugriffspakets](../../media/new-access-package.png)

    <span data-ttu-id="12cfc-153">Weitere Informationen finden Sie unter [Erstellen eines neuen Zugriffspakets.](/azure/active-directory/governance/entitlement-management-access-package-create)</span><span class="sxs-lookup"><span data-stu-id="12cfc-153">For more information, see [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>

4. <span data-ttu-id="12cfc-154">**Bereitstellen eines Zugriffsanforderungslinks zu MSSP-Ressourcen von Kunden-AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="12cfc-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="12cfc-155">Der My Access-Portallink wird von MSSP SOC-Analysten verwendet, um den Zugriff über die erstellten Zugriffspakete anzufordern.</span><span class="sxs-lookup"><span data-stu-id="12cfc-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="12cfc-156">Der Link ist dauerhaft, d. h. derselbe Link kann im Laufe der Zeit für neue Analysten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="12cfc-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="12cfc-157">Die Analystenanforderung wird zur Genehmigung durch die **Genehmigenden von MSSP-Analysten** in eine Warteschlange eingereiht.</span><span class="sxs-lookup"><span data-stu-id="12cfc-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    ![Abbildung der Zugriffseigenschaften](../../media/access-properties.png)

    <span data-ttu-id="12cfc-159">Der Link befindet sich auf der Übersichtsseite jedes Zugriffspakets.</span><span class="sxs-lookup"><span data-stu-id="12cfc-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="12cfc-160">Zugriff verwalten</span><span class="sxs-lookup"><span data-stu-id="12cfc-160">Manage access</span></span>

1. <span data-ttu-id="12cfc-161">Überprüfen und autorisieren Sie Zugriffsanforderungen in "Customer" und/oder "MSSP myaccess".</span><span class="sxs-lookup"><span data-stu-id="12cfc-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="12cfc-162">Zugriffsanfragen werden im Kunden "My Access" von Mitgliedern der Gruppe der Genehmiger für MSSP-Analysten verwaltet.</span><span class="sxs-lookup"><span data-stu-id="12cfc-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="12cfc-163">Um dies zu tun, greifen Sie auf das MyAccess des Kunden zu, indem Sie: `https://myaccess.microsoft.com/@<Customer Domain>` .</span><span class="sxs-lookup"><span data-stu-id="12cfc-163">To do so, access the customer's myaccess using: `https://myaccess.microsoft.com/@<Customer Domain>`.</span></span>

    <span data-ttu-id="12cfc-164">Beispiel: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="12cfc-164">Example: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>

2. <span data-ttu-id="12cfc-165">Genehmigen oder Verweigern von Anforderungen im Abschnitt **"Genehmigungen"** der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="12cfc-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="12cfc-166">Zu diesem Zeitpunkt wurde der Analystenzugriff bereitgestellt, und jeder Analyst sollte in der Lage sein, auf das Microsoft 365 Security Center des Kunden zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="12cfc-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span>

    <span data-ttu-id="12cfc-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` mit den Berechtigungen und Rollen, die ihnen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="12cfc-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="12cfc-168">Der delegierte Zugriff auf Microsoft Defender für Endpunkt im Microsoft 365 Security Center ermöglicht derzeit den Zugriff auf einen einzelnen Mandanten pro Browserfenster.</span><span class="sxs-lookup"><span data-stu-id="12cfc-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span>
