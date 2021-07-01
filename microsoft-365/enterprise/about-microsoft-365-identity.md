---
title: Microsoft 365 Identitätsmodelle und Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Erfahren Sie, wie Sie den Azure AD-Benutzeridentitätsdienst in Microsoft 365 mithilfe von reinen Cloud- oder Hybrididentitätsmodellen verwalten.
ms.openlocfilehash: 93a37f39a4d96d7c2e434ed6edf4df588e672a0f
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228495"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="744db-103">Microsoft 365 Identitätsmodelle und Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="744db-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="744db-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="744db-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="744db-105">Microsoft 365 verwendet Azure Active Directory (Azure AD), einen cloudbasierten Benutzeridentitäts- und Authentifizierungsdienst, der in Ihrem Microsoft 365-Abonnement enthalten ist, um Identitäten und Authentifizierung für Microsoft 365 zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="744db-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="744db-106">Die richtige Konfiguration Ihrer Identitätsinfrastruktur ist für die Verwaltung Microsoft 365 Benutzerzugriffs und der Berechtigungen für Ihre Organisation von entscheidender Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="744db-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="744db-107">Bevor Sie beginnen, schauen Sie sich dieses Video an, um eine Übersicht über die Identitätsmodelle und Authentifizierung für Microsoft 365 zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="744db-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="744db-108"><p> </p></span><span class="sxs-lookup"><span data-stu-id="744db-108"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="744db-109">Ihre erste Wahl bei der Planung ist das Microsoft 365 Identitätsmodell.</span><span class="sxs-lookup"><span data-stu-id="744db-109">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="744db-110">Microsoft 365 Identitätsmodelle</span><span class="sxs-lookup"><span data-stu-id="744db-110">Microsoft 365 identity models</span></span>

<span data-ttu-id="744db-111">Um Benutzerkonten zu planen, müssen Sie zunächst die beiden Identitätsmodelle in Microsoft 365 verstehen.</span><span class="sxs-lookup"><span data-stu-id="744db-111">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="744db-112">Sie können die Identitäten Ihrer Organisation nur in der Cloud verwalten, oder Sie können Ihre lokalen AD DS-Identitäten (Active Directory Domain Services) verwalten und diese zur Authentifizierung verwenden, wenn Benutzer auf Microsoft 365-Clouddienste zugreifen.</span><span class="sxs-lookup"><span data-stu-id="744db-112">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>

<span data-ttu-id="744db-113">Nachfolgend finden Sie die beiden Identitätstypen sowie deren beste Anwendungsfälle und Vorteile.</span><span class="sxs-lookup"><span data-stu-id="744db-113">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="744db-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="744db-114">Attribute</span></span> | <span data-ttu-id="744db-115">Reine Cloudidentität</span><span class="sxs-lookup"><span data-stu-id="744db-115">Cloud-only identity</span></span> | <span data-ttu-id="744db-116">Hybrididentität</span><span class="sxs-lookup"><span data-stu-id="744db-116">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="744db-117">**Definition**</span><span class="sxs-lookup"><span data-stu-id="744db-117">**Definition**</span></span> | <span data-ttu-id="744db-118">Das Benutzerkonto ist nur im Azure AD-Mandanten für Ihr Microsoft 365-Abonnement vorhanden.</span><span class="sxs-lookup"><span data-stu-id="744db-118">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="744db-119">Ein Benutzerkonto ist in AD DS vorhanden, und eine Kopie befindet sich auch im Azure AD-Mandanten für Ihr Microsoft 365-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="744db-119">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="744db-120">Das Benutzerkonto in Azure AD kann auch eine Hashversion des bereits gehashten AD DS-Benutzerkontokennworts enthalten.</span><span class="sxs-lookup"><span data-stu-id="744db-120">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="744db-121">**Authentifizierung von Benutzeranmeldeinformationen durch Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="744db-121">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="744db-122">Der Azure AD-Mandant für Ihr Microsoft 365-Abonnement führt die Authentifizierung mit dem Cloudidentitätskonto durch.</span><span class="sxs-lookup"><span data-stu-id="744db-122">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="744db-123">Der Azure AD-Mandant für Ihr Microsoft 365-Abonnement behandelt verarbeitet entweder den Authentifizierungsprozess oder leitet den Benutzer an einen anderen Identitätsanbieter weiter.</span><span class="sxs-lookup"><span data-stu-id="744db-123">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="744db-124">**Ideal für**</span><span class="sxs-lookup"><span data-stu-id="744db-124">**Best for**</span></span> | <span data-ttu-id="744db-125">Organisationen, die keinen lokalen AD DS besitzen oder benötigen.</span><span class="sxs-lookup"><span data-stu-id="744db-125">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="744db-126">Organisationen, die AD DS oder einen anderen Identitätsanbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="744db-126">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="744db-127">**Größter Vorteil**</span><span class="sxs-lookup"><span data-stu-id="744db-127">**Greatest benefit**</span></span> | <span data-ttu-id="744db-128">Einfach zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="744db-128">Simple to use.</span></span> <span data-ttu-id="744db-129">Es sind keine zusätzlichen Verzeichnistools oder Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="744db-129">No extra directory tools or servers required.</span></span> | <span data-ttu-id="744db-130">Benutzer können dieselben Anmeldeinformationen verwenden, wenn sie auf lokale oder cloudbasierte Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="744db-130">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="744db-131">Reine Cloudidentität</span><span class="sxs-lookup"><span data-stu-id="744db-131">Cloud-only identity</span></span>

<span data-ttu-id="744db-132">Bei der reinen Cloudidentität werden Benutzerkonten verwendet, die nur in Azure AD vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="744db-132">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="744db-133">Reine Cloudidentität wird in der Regel von kleinen Organisationen verwendet, die nicht über lokale Server verfügen oder AD DS nicht zum Verwalten lokaler Identitäten verwenden.</span><span class="sxs-lookup"><span data-stu-id="744db-133">Cloud-only identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span>

<span data-ttu-id="744db-134">Hier sind die grundlegenden Komponenten der reinen Cloudidentität.</span><span class="sxs-lookup"><span data-stu-id="744db-134">Here are the basic components of cloud-only identity.</span></span>

![Grundlegende Komponenten der reinen Cloudidentität](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="744db-136">Sowohl lokale als auch Remotebenutzer (Onlinebenutzer) verwenden ihre Azure AD-Benutzerkonten und Kennwörter, um auf Microsoft 365 Clouddienste zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="744db-136">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="744db-137">Azure AD authentifiziert Benutzeranmeldeinformationen basierend auf den gespeicherten Benutzerkonten und Kennwörtern.</span><span class="sxs-lookup"><span data-stu-id="744db-137">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="744db-138">Verwaltung</span><span class="sxs-lookup"><span data-stu-id="744db-138">Administration</span></span>
<span data-ttu-id="744db-139">Da Benutzerkonten nur in Azure AD gespeichert sind, verwalten Sie Cloudidentitäten mit Tools wie [Microsoft 365 Admin Center](../admin/add-users/index.yml) und [Windows PowerShell.](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="744db-139">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](../admin/add-users/index.yml) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span>

## <a name="hybrid-identity"></a><span data-ttu-id="744db-140">Hybrididentität</span><span class="sxs-lookup"><span data-stu-id="744db-140">Hybrid identity</span></span>

<span data-ttu-id="744db-141">Die Hybrididentität verwendet Konten, die von einem lokalen AD DS stammen und eine Kopie im Azure AD-Mandanten eines Microsoft 365-Abonnements aufweisen.</span><span class="sxs-lookup"><span data-stu-id="744db-141">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="744db-142">Die meisten Änderungen fließen jedoch nur in eine Richtung.</span><span class="sxs-lookup"><span data-stu-id="744db-142">However, most changes only flow one way.</span></span> <span data-ttu-id="744db-143">Änderungen, die Sie an AD DS-Benutzerkonten vornehmen, werden mit Ihrer Kopie in Azure AD synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="744db-143">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="744db-144">Änderungen, die in cloudbasierten Konten in Azure AD vorgenommen wurden, wie z. B. neue Benutzerkonten, werden jedoch nicht mit AD DS synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="744db-144">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="744db-145">Azure AD Connect bietet die laufende Kontosynchronisierung.</span><span class="sxs-lookup"><span data-stu-id="744db-145">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="744db-146">Es wird auf einem lokalen Server ausgeführt, überprüft auf Änderungen in AD DS und leitet diese Änderungen an Azure AD weiter.</span><span class="sxs-lookup"><span data-stu-id="744db-146">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="744db-147">Azure AD Connect bietet die Möglichkeit zu filtern, welche Konten synchronisiert werden, und ob eine Hashversion der Benutzerkennwörter synchronisiert werden soll; dies wird als „Kennworthashsynchronisierung“ (Password hash synchronization, PHS) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="744db-147">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="744db-148">Wenn Sie die Hybrididentität implementieren, ist Ihr lokales AD DS die autorisierende Quelle für Kontoinformationen.</span><span class="sxs-lookup"><span data-stu-id="744db-148">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="744db-149">Dies bedeutet, dass Sie Verwaltungsaufgaben hauptsächlich lokal durchführen, die dann mit Azure AD synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="744db-149">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span>

<span data-ttu-id="744db-150">Nachfolgend finden Sie die Komponenten der Hybrididentität.</span><span class="sxs-lookup"><span data-stu-id="744db-150">Here are the components of hybrid identity.</span></span>

![Komponenten der Hybrididentität](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="744db-152">Der Azure AD-Mandant hat eine Kopie der AD DS-Konten.</span><span class="sxs-lookup"><span data-stu-id="744db-152">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="744db-153">In dieser Konfiguration authentifizieren sich sowohl lokale als auch Remotebenutzer beim Zugriff auf Microsoft 365-Clouddienste bei Azure AD.</span><span class="sxs-lookup"><span data-stu-id="744db-153">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

> [!NOTE]
> <span data-ttu-id="744db-154">Sie müssen immer Azure AD Connect verwenden, um Benutzerkonten für die Hybrididentität zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="744db-154">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="744db-155">Sie benötigen die synchronisierten Benutzerkonten in Azure AD, um die Lizenzzuweisung und Gruppenverwaltung durchzuführen, um Berechtigungen zu konfigurieren und um andere Verwaltungsaufgaben auszuführen, die Benutzerkonten umfassen.</span><span class="sxs-lookup"><span data-stu-id="744db-155">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>

### <a name="administration"></a><span data-ttu-id="744db-156">Verwaltung</span><span class="sxs-lookup"><span data-stu-id="744db-156">Administration</span></span>

<span data-ttu-id="744db-157">Da die ursprünglichen und autorisierenden Benutzerkonten im lokalen AD DS gespeichert sind, verwalten Sie Ihre Identitäten mit denselben Tools wie Ihre AD DS.</span><span class="sxs-lookup"><span data-stu-id="744db-157">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as you manage your AD DS.</span></span>

<span data-ttu-id="744db-158">Sie verwenden nicht die Microsoft 365 Admin Center oder PowerShell für Microsoft 365, um synchronisierte Benutzerkonten in Azure AD zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="744db-158">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="744db-159">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="744db-159">Next step</span></span>

<span data-ttu-id="744db-160">Wenn Sie das reine Cloudidentitätsmodell benötigen, lesen Sie ["Reine Cloudidentität".](cloud-only-identities.md)</span><span class="sxs-lookup"><span data-stu-id="744db-160">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="744db-161">Wenn Sie das Hybrididentitätsmodell benötigen, finden Sie weitere Informationen unter ["Hybrididentität".](plan-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="744db-161">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="744db-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="744db-162">See also</span></span>

[<span data-ttu-id="744db-163">Übersicht zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="744db-163">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
