---
title: Gewähren des Zugriffs auf verwaltete Sicherheitsdienstanbieter (Managed Security Service Provider, MSSP)
description: Ausführen der erforderlichen Schritte zum Konfigurieren der MSSP-Integration mit Microsoft Defender for Endpoint
keywords: Managed Security Service Provider, mssp, configure, integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 320355f838db5dbb1540350e95e4cc0645acd805
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932751"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a><span data-ttu-id="eaf00-104">Gewähren des Zugriffs auf verwalteten Sicherheitsdienstanbieter (Managed Security Service Provider, MSSP) (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="eaf00-104">Grant managed security service provider (MSSP) access (preview)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eaf00-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="eaf00-105">**Applies to:**</span></span>
- [<span data-ttu-id="eaf00-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="eaf00-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eaf00-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eaf00-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="eaf00-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="eaf00-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eaf00-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="eaf00-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
><span data-ttu-id="eaf00-110">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="eaf00-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="eaf00-111">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="eaf00-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="eaf00-112">Gehen Sie wie folgt vor, um eine mehr mandantendelegierte Zugriffslösung zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="eaf00-112">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="eaf00-113">Aktivieren [Sie die rollenbasierte Zugriffssteuerung](rbac.md) in Defender for Endpoint, und stellen Sie eine Verbindung mit Active Directory (AD)-Gruppen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="eaf00-113">Enable [role-based access control](rbac.md) in Defender for Endpoint and connect with Active Directory (AD) groups.</span></span>

2. <span data-ttu-id="eaf00-114">Konfigurieren [von Governance-Zugriffspaketen](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) für Zugriffsanforderung und -bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="eaf00-114">Configure [Governance Access Packages](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="eaf00-115">Verwalten von Zugriffsanforderungen und -überwachungen in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span><span class="sxs-lookup"><span data-stu-id="eaf00-115">Manage access requests and audits in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="eaf00-116">Aktivieren von rollenbasierten Zugriffssteuerelementen in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eaf00-116">Enable role-based access controls in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="eaf00-117">**Erstellen von Zugriffsgruppen für MSSP-Ressourcen in Customer AAD: Groups**</span><span class="sxs-lookup"><span data-stu-id="eaf00-117">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="eaf00-118">Diese Gruppen werden mit den Rollen verknüpft, die Sie in Defender for Endpoint erstellen.</span><span class="sxs-lookup"><span data-stu-id="eaf00-118">These groups will be linked to the Roles you create in Defender for Endpoint.</span></span> <span data-ttu-id="eaf00-119">Erstellen Sie dazu im Kunden-AD-Mandanten drei Gruppen.</span><span class="sxs-lookup"><span data-stu-id="eaf00-119">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="eaf00-120">In unserem Beispielansatz erstellen wir die folgenden Gruppen:</span><span class="sxs-lookup"><span data-stu-id="eaf00-120">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="eaf00-121">Tier 1 Analyst</span><span class="sxs-lookup"><span data-stu-id="eaf00-121">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="eaf00-122">Tier 2 Analyst</span><span class="sxs-lookup"><span data-stu-id="eaf00-122">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="eaf00-123">Genehmiger von MSSP-Analysten</span><span class="sxs-lookup"><span data-stu-id="eaf00-123">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="eaf00-124">Erstellen Sie Defender for Endpoint-Rollen für geeignete Zugriffsebenen in Customer Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="eaf00-124">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint.</span></span>

    <span data-ttu-id="eaf00-125">Um rbAC im Kundenkonto zu Microsoft Defender Security Center, greifen Sie auf **Einstellungen > Berechtigungen >** Rollen und "Rollen aktivieren" über ein Benutzerkonto mit globalen Administrator- oder Sicherheitsadministratorrechten zu.</span><span class="sxs-lookup"><span data-stu-id="eaf00-125">To enable RBAC in the customer Microsoft Defender Security Center, access **Settings > Permissions > Roles** and "Turn on roles", from a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Abbildung des MSSP-Zugriffs](images/mssp-access.png)

    <span data-ttu-id="eaf00-127">Erstellen Sie dann ROLLENAC-Rollen, um die Anforderungen der MSSP-SOC-Ebene zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="eaf00-127">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="eaf00-128">Verknüpfen Sie diese Rollen mit den erstellten Benutzergruppen über "Zugewiesene Benutzergruppen".</span><span class="sxs-lookup"><span data-stu-id="eaf00-128">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="eaf00-129">Zwei mögliche Rollen:</span><span class="sxs-lookup"><span data-stu-id="eaf00-129">Two possible roles:</span></span>

    - <span data-ttu-id="eaf00-130">**Analysten der Stufe 1**</span><span class="sxs-lookup"><span data-stu-id="eaf00-130">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="eaf00-131">Führen Sie alle Aktionen mit Ausnahme von Liveantworten aus und verwalten Sie Sicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="eaf00-131">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="eaf00-132">**Analysten der Stufe 2**</span><span class="sxs-lookup"><span data-stu-id="eaf00-132">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="eaf00-133">Funktionen der Stufe 1 mit der Ergänzung zur [Liveantwort](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="eaf00-133">Tier 1 capabilities with the addition to [live response](live-response.md)</span></span>

    <span data-ttu-id="eaf00-134">Weitere Informationen finden Sie unter [Verwenden der rollenbasierten Zugriffssteuerung](rbac.md).</span><span class="sxs-lookup"><span data-stu-id="eaf00-134">For more information, see [Use role-based access control](rbac.md).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="eaf00-135">Konfigurieren von Steuerungszugriffspaketen</span><span class="sxs-lookup"><span data-stu-id="eaf00-135">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="eaf00-136">**Hinzufügen von MSSP als verbundene Organisation in Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="eaf00-136">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="eaf00-137">Das Hinzufügen des MSSP als verbundene Organisation ermöglicht dem MSSP das Anfordern und Bereitstellen von Zugriffen.</span><span class="sxs-lookup"><span data-stu-id="eaf00-137">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="eaf00-138">Greifen Sie dazu im Kunden-AD-Mandanten auf Identity Governance: Verbundene Organisation zu.</span><span class="sxs-lookup"><span data-stu-id="eaf00-138">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="eaf00-139">Fügen Sie eine neue Organisation hinzu, und suchen Sie nach Ihrem MSSP Analyst-Mandanten über Mandanten-ID oder Domäne.</span><span class="sxs-lookup"><span data-stu-id="eaf00-139">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="eaf00-140">Wir empfehlen, einen separaten AD-Mandanten für Ihre MSSP-Analysten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eaf00-140">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="eaf00-141">**Erstellen eines Ressourcenkatalogs in Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="eaf00-141">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="eaf00-142">Ressourcenkataloge sind eine logische Auflistung von Zugriffspaketen, die im Kunden-AD-Mandanten erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="eaf00-142">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="eaf00-143">Greifen Sie dazu im Kunden-AD-Mandanten auf Identity Governance: Catalogs zu, und fügen Sie **neuen Katalog hinzu.**</span><span class="sxs-lookup"><span data-stu-id="eaf00-143">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="eaf00-144">In unserem Beispiel nennen wir es **MSSP Accesses**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-144">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![Abbildung des neuen Katalogs](images/goverance-catalog.png)

    <span data-ttu-id="eaf00-146">Weitere Informationen finden Sie unter [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span><span class="sxs-lookup"><span data-stu-id="eaf00-146">Further more information, see [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="eaf00-147">**Erstellen von Zugriffspaketen für MSSP-Ressourcen Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="eaf00-147">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="eaf00-148">Bei Zugriffspaketen handelt es sich um die Sammlung von Rechten und Zugriffen, die einem Anfordernden bei genehmigung erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="eaf00-148">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="eaf00-149">Greifen Sie dazu im Kunden-AD-Mandanten auf Identity Governance: Access Packages zu, und fügen Sie **New Access Package hinzu.**</span><span class="sxs-lookup"><span data-stu-id="eaf00-149">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="eaf00-150">Erstellen Sie ein Zugriffspaket für die MSSP-Genehmiger und die einzelnen Analystenebenen.</span><span class="sxs-lookup"><span data-stu-id="eaf00-150">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="eaf00-151">Die folgende Konfiguration von Tier 1 Analyst erstellt beispielsweise ein Zugriffspaket, das:</span><span class="sxs-lookup"><span data-stu-id="eaf00-151">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="eaf00-152">Erfordert, dass ein Mitglied der **AD-Gruppe MSSP Analyst Approvers** neue Anforderungen autorisiert</span><span class="sxs-lookup"><span data-stu-id="eaf00-152">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="eaf00-153">Verfügt über jährliche Zugriffsüberprüfungen, bei denen die SOC-Analysten eine Zugriffserweiterung anfordern können</span><span class="sxs-lookup"><span data-stu-id="eaf00-153">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="eaf00-154">Kann nur von Benutzern im MSSP-SOC-Mandanten angefordert werden</span><span class="sxs-lookup"><span data-stu-id="eaf00-154">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="eaf00-155">Access auto läuft nach 365 Tagen ab</span><span class="sxs-lookup"><span data-stu-id="eaf00-155">Access auto expires after 365 days</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="eaf00-156">![Abbildung des neuen Zugriffspakets](images/new-access-package.png)</span><span class="sxs-lookup"><span data-stu-id="eaf00-156">![Image of new access package](images/new-access-package.png)</span></span>

    <span data-ttu-id="eaf00-157">Weitere Informationen finden Sie unter [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span><span class="sxs-lookup"><span data-stu-id="eaf00-157">For more information, see [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="eaf00-158">**Bereitstellen eines Zugriffsanforderungslinks zu MSSP-Ressourcen vom Kunden-AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="eaf00-158">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="eaf00-159">Der Link My Access-Portal wird von MSSP SOC-Analysten verwendet, um zugriff über die erstellten Zugriffspakete an zu fordern.</span><span class="sxs-lookup"><span data-stu-id="eaf00-159">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="eaf00-160">Der Link ist dauerhaft, d. h. derselbe Link kann im Laufe der Zeit für neue Analysten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eaf00-160">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="eaf00-161">Die Analystenanforderung wird von den Genehmigern von MSSP Analysten in eine Warteschlange **eingereiht.**</span><span class="sxs-lookup"><span data-stu-id="eaf00-161">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="eaf00-162">![Abbildung der Zugriffseigenschaften](images/access-properties.png)</span><span class="sxs-lookup"><span data-stu-id="eaf00-162">![Image of access properties](images/access-properties.png)</span></span>

    <span data-ttu-id="eaf00-163">Der Link befindet sich auf der Übersichtsseite der einzelnen Zugriffspakete.</span><span class="sxs-lookup"><span data-stu-id="eaf00-163">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="eaf00-164">Zugriff verwalten</span><span class="sxs-lookup"><span data-stu-id="eaf00-164">Manage access</span></span> 

1. <span data-ttu-id="eaf00-165">Überprüfen und Autorisieren von Zugriffsanforderungen in Customer und/oder MSSP myaccess.</span><span class="sxs-lookup"><span data-stu-id="eaf00-165">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="eaf00-166">Zugriffsanforderungen werden im Kunden My Access von Mitgliedern der Gruppe "Genehmiger von MSSP Analysten" verwaltet.</span><span class="sxs-lookup"><span data-stu-id="eaf00-166">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="eaf00-167">Greifen Sie dazu auf myaccess des Kunden zu, indem Sie:  `https://myaccess.microsoft.com/@<Customer Domain >` .</span><span class="sxs-lookup"><span data-stu-id="eaf00-167">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="eaf00-168">Beispiel:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="eaf00-168">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="eaf00-169">Genehmigen oder Verweigern von Anforderungen im **Abschnitt Genehmigungen** der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="eaf00-169">Approve or deny requests in the **Approvals** section of the UI.</span></span>

    <span data-ttu-id="eaf00-170">Zu diesem Zeitpunkt wurde der Analystenzugriff bereitgestellt, und jeder Analyst sollte in der Lage sein, auf die Kundendaten Microsoft Defender Security Center:`https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span><span class="sxs-lookup"><span data-stu-id="eaf00-170">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft Defender Security Center: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="eaf00-171">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="eaf00-171">Related topics</span></span>
- [<span data-ttu-id="eaf00-172">Zugreifen auf das MSSP-Kundenportal</span><span class="sxs-lookup"><span data-stu-id="eaf00-172">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="eaf00-173">Warnungsbenachrichtigungen konfigurieren</span><span class="sxs-lookup"><span data-stu-id="eaf00-173">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="eaf00-174">Abrufen von Benachrichtigungen vom Kunden-Mandanten</span><span class="sxs-lookup"><span data-stu-id="eaf00-174">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)



 

