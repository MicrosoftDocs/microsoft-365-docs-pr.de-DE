---
title: Hybride Identitäts-und Verzeichnissynchronisierung für Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 06/09/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Beschreibt die Verzeichnissynchronisierung mit Microsoft 365, Active Directory-Domänendienste Bereinigung und das Azure Active Directory Connect-Tool.
ms.openlocfilehash: 2d3161fb835073a22743ea4f3b00ac508479f0f2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690537"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="d460e-103">Hybride Identitäts-und Verzeichnissynchronisierung für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d460e-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="d460e-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d460e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d460e-105">Je nach Ihren geschäftlichen Anforderungen und technischen Anforderungen ist das hybride Identitätsmodell und die Verzeichnissynchronisierung die häufigste Wahl für Unternehmenskunden, die Microsoft 365 annehmen.</span><span class="sxs-lookup"><span data-stu-id="d460e-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="d460e-106">Mit der Verzeichnissynchronisierung können Sie Identitäten in Ihrer Active Directory-Domänendienste (AD DS) verwalten, und alle Aktualisierungen an Benutzerkonten, Gruppen und Kontakten werden mit dem Azure Active Directory (Azure AD)-Mandanten Ihres Microsoft 365-Abonnements synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="d460e-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="d460e-107">Wenn AD DS Benutzerkonten zum ersten Mal synchronisiert werden, werden Sie nicht automatisch eine Microsoft 365-Lizenz zugewiesen und können nicht auf Microsoft 365-Dienste wie e-Mail zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d460e-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="d460e-108">Sie müssen Ihnen zunächst einen Verwendungs Speicherort zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d460e-108">You must first assign them a usage location.</span></span> <span data-ttu-id="d460e-109">Weisen Sie dann diesen Benutzerkonten entweder einzeln oder dynamisch über die Gruppenmitgliedschaft eine Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="d460e-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="d460e-110">Authentifizierung für Hybrid Identität</span><span class="sxs-lookup"><span data-stu-id="d460e-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="d460e-111">Bei der Verwendung des Hybriden Identitätsmodells gibt es zwei Arten von Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="d460e-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="d460e-112">Verwaltete Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d460e-112">Managed authentication</span></span>

  <span data-ttu-id="d460e-113">Azure AD verarbeitet den Authentifizierungsprozess mithilfe einer lokal gespeicherten Hashversion des Kennworts oder sendet die Anmeldeinformationen an einen lokalen Software-Agent, der vom lokalen AD DS authentifiziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d460e-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="d460e-114">Verbundauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="d460e-114">Federated authentication</span></span>

  <span data-ttu-id="d460e-115">Azure AD leitet den Clientcomputer, der die Authentifizierung anfordert, an einen anderen Identitätsanbieter um.</span><span class="sxs-lookup"><span data-stu-id="d460e-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="d460e-116">Verwaltete Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d460e-116">Managed authentication</span></span>

<span data-ttu-id="d460e-117">Es gibt zwei Arten der verwalteten Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="d460e-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="d460e-118">Kennworthashsynchronisierung (Password hash synchronization, PHS)</span><span class="sxs-lookup"><span data-stu-id="d460e-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="d460e-119">Azure AD führt die Authentifizierung selbst durch.</span><span class="sxs-lookup"><span data-stu-id="d460e-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="d460e-120">Passthrough-Authentifizierung (PTA)</span><span class="sxs-lookup"><span data-stu-id="d460e-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="d460e-121">Azure AD lässt AD DS die Authentifizierung durchführen.</span><span class="sxs-lookup"><span data-stu-id="d460e-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="d460e-122">Kennworthashsynchronisierung (Password hash synchronization, PHS)</span><span class="sxs-lookup"><span data-stu-id="d460e-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="d460e-123">Mit PHS synchronisieren Sie Ihre AD DS Benutzerkonten mit Microsoft 365 und verwalten Ihre Benutzer lokal.</span><span class="sxs-lookup"><span data-stu-id="d460e-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="d460e-124">Hashwerte von Benutzerkennwörtern werden von Ihrem AD DS zu Azure AD synchronisiert, sodass die Benutzer das gleiche Kennwort lokal und in der Cloud haben.</span><span class="sxs-lookup"><span data-stu-id="d460e-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="d460e-125">Dies ist die einfachste Möglichkeit zum Aktivieren der Authentifizierung für AD DS Identitäten in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d460e-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![Kennworthashsynchronisierung (Password hash synchronization, PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="d460e-127">Wenn Kennwörter lokal geändert oder zurückgesetzt werden, werden die neuen Kennworthashs mit Azure AD synchronisiert, sodass Ihre Benutzer immer dasselbe Kennwort für Cloud-Ressourcen und lokale Ressourcen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d460e-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="d460e-128">Die Benutzerkennwörter werden nie an Azure AD gesendet oder in Azure AD in Klartext gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d460e-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="d460e-129">Einige Premium Features von Azure AD, beispielsweise Identitätsschutz, erfordern PHS, unabhängig davon, welche Authentifizierungsmethode ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="d460e-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="d460e-130">Weitere Informationen finden Sie unter [Auswählen der richtigen Authentifizierungsmethode](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) .</span><span class="sxs-lookup"><span data-stu-id="d460e-130">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="d460e-131">Passthrough-Authentifizierung (PTA)</span><span class="sxs-lookup"><span data-stu-id="d460e-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="d460e-132">PTA bietet eine einfache Kennwortüberprüfung für Azure AD Authentifizierungsdienste mit einem Software-Agent, der auf einem oder mehreren lokalen Servern läuft, um die Benutzer direkt mit Ihrem AD DS zu validieren.</span><span class="sxs-lookup"><span data-stu-id="d460e-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="d460e-133">Mit PTA synchronisieren Sie AD DS Benutzerkonten mit Microsoft 365 und verwalten Ihre Benutzer lokal.</span><span class="sxs-lookup"><span data-stu-id="d460e-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![Passthrough-Authentifizierung (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="d460e-135">PTA ermöglicht es Ihren Benutzern, sich über Ihr lokales Konto und Ihr Kennwort bei lokalen und Microsoft 365-Ressourcen und-Anwendungen anzumelden.</span><span class="sxs-lookup"><span data-stu-id="d460e-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="d460e-136">Mit dieser Konfiguration werden Benutzerkennwörter direkt für Ihr lokales AD DS überprüft, ohne dass Kennworthashs in Azure AD gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d460e-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="d460e-137">PTA richtet sich auch an Organisationen mit einer Sicherheitsanforderung, um lokale Benutzerkonto Zustände, Kennwortrichtlinien und Anmeldezeiten sofort zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="d460e-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="d460e-138">Weitere Informationen finden Sie unter [Auswählen der richtigen Authentifizierungsmethode](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) .</span><span class="sxs-lookup"><span data-stu-id="d460e-138">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="d460e-139">Verbundauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="d460e-139">Federated authentication</span></span>

<span data-ttu-id="d460e-140">Die Verbundauthentifizierung ist in erster Linie für große Unternehmensorganisationen mit komplexeren Authentifizierungsanforderungen geeignet.</span><span class="sxs-lookup"><span data-stu-id="d460e-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="d460e-141">AD DS Identitäten werden mit Microsoft 365 synchronisiert, und Benutzerkonten werden lokal verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d460e-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="d460e-142">Bei der Verbundauthentifizierung haben Benutzer das gleiche Kennwort lokal und in der Cloud, und Sie müssen sich nicht erneut anmelden, um Microsoft 365 zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d460e-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="d460e-143">Die Verbundauthentifizierung kann zusätzliche Authentifizierungsanforderungen wie Smartcard-basierte Authentifizierung oder mehrstufige Authentifizierung eines Drittanbieters unterstützen und ist in der Regel erforderlich, wenn Organisationen über eine Authentifizierungsanforderung verfügen, die nicht von Azure AD nativ unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="d460e-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="d460e-144">Weitere Informationen finden Sie unter [Auswählen der richtigen Authentifizierungsmethode](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) .</span><span class="sxs-lookup"><span data-stu-id="d460e-144">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="d460e-145">Authentifizierungs-und Identitätsanbieter von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="d460e-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="d460e-146">Lokale Verzeichnisobjekte können mit Microsoft 365 synchronisiert werden, und der Zugriff auf Cloud-Ressourcen wird in erster Linie von einem Drittanbieter-Identitätsanbieter (IDP) verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d460e-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="d460e-147">Wenn Ihre Organisation eine Drittanbieter-Verbundlösung verwendet, können Sie die Anmeldung mit dieser Lösung für Microsoft 365 konfigurieren, vorausgesetzt, die Drittanbieter-Verbundlösung ist mit Azure AD kompatibel.</span><span class="sxs-lookup"><span data-stu-id="d460e-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="d460e-148">Weitere Informationen finden Sie in der [Liste Azure AD Verbund Kompatibilität](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) .</span><span class="sxs-lookup"><span data-stu-id="d460e-148">See the [Azure AD federation compatibility list](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="d460e-149">AD DS Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="d460e-149">AD DS Preparation</span></span>

<span data-ttu-id="d460e-150">Um einen nahtlosen Übergang zu Microsoft 365 mithilfe der Synchronisierung sicherzustellen, müssen Sie Ihre AD DS Gesamtstruktur vorbereiten, bevor Sie mit der Bereitstellung von Microsoft 365 für die Verzeichnissynchronisierung beginnen.</span><span class="sxs-lookup"><span data-stu-id="d460e-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="d460e-151">Die Verzeichnis Vorbereitung sollte sich auf die folgenden Aufgaben konzentrieren:</span><span class="sxs-lookup"><span data-stu-id="d460e-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="d460e-152">Entfernen Sie doppelte **proxyAddress** -und **userPrincipalName** -Attribute.</span><span class="sxs-lookup"><span data-stu-id="d460e-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="d460e-153">Aktualisieren Sie leere und ungültige **userPrincipalName** -Attribute mit gültigen **userPrincipalName** -Attributen.</span><span class="sxs-lookup"><span data-stu-id="d460e-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="d460e-154">Entfernen Sie ungültige und fragwürdige Zeichen in den Attributen **givenName**, Name ( **SN** ), **sAMAccountName**, **DisplayName**, **Mail**, **proxyAddresses**, **mailNickname**und **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="d460e-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="d460e-155">Ausführliche Informationen zum Vorbereiten von Attributen finden Sie unter [Liste der Attribute, die mit dem Azure Active Directory Sync-Tool synchronisiert werden](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span><span class="sxs-lookup"><span data-stu-id="d460e-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d460e-156">Dabei handelt es sich um dieselben Attribute, die Azure AD Connect synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="d460e-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="d460e-157">Überlegungen zur Bereitstellung in mehreren Gesamtstrukturen</span><span class="sxs-lookup"><span data-stu-id="d460e-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="d460e-158">Verwenden Sie für mehrere Gesamtstrukturen und SSO-Optionen eine [benutzerdefinierte Installation von Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span><span class="sxs-lookup"><span data-stu-id="d460e-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span></span>
  
<span data-ttu-id="d460e-159">Wenn Ihre Organisation über mehrere Gesamtstrukturen für die Authentifizierung verfügt (Anmelde Gesamtstrukturen), wird dringend Folgendes empfohlen:</span><span class="sxs-lookup"><span data-stu-id="d460e-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="d460e-160">**Sie sollten die Gesamtstruktur konsolidieren.**</span><span class="sxs-lookup"><span data-stu-id="d460e-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="d460e-161">Im Allgemeinen ist mehr Aufwand erforderlich, um mehrere Gesamtstrukturen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="d460e-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="d460e-162">Wenn Ihre Organisation nicht über Sicherheitseinschränkungen verfügt, die separate Gesamtstrukturen erfordern, sollten Sie die lokale Umgebung vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="d460e-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="d460e-163">**Nur in der primären anmeldegesamtstruktur verwenden.**</span><span class="sxs-lookup"><span data-stu-id="d460e-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="d460e-164">Sie sollten Microsoft 365 nur in ihrer primären anmeldegesamtstruktur für die erste Einführung von Microsoft 365 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d460e-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="d460e-165">Wenn Sie Ihre AD DS-Bereitstellung mit mehreren Gesamtstrukturen nicht konsolidieren oder andere Verzeichnisdienste zum Verwalten von Identitäten verwenden, können Sie diese möglicherweise mit der Hilfe von Microsoft oder einem Partner synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="d460e-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="d460e-166">Weitere Informationen finden Sie unter [Topologien für Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) .</span><span class="sxs-lookup"><span data-stu-id="d460e-166">See [Topologies for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="d460e-167">Funktionen, die von der Verzeichnissynchronisierung abhängig sind</span><span class="sxs-lookup"><span data-stu-id="d460e-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="d460e-168">Die Verzeichnissynchronisierung ist für die folgenden Features und Funktionen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="d460e-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="d460e-169">Azure AD nahtloses einmaliges Anmelden (Single Sign-on, SSO)</span><span class="sxs-lookup"><span data-stu-id="d460e-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="d460e-170">Skype-Koexistenz</span><span class="sxs-lookup"><span data-stu-id="d460e-170">Skype coexistence</span></span>
- <span data-ttu-id="d460e-171">Exchange-hybridbereitstellung, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="d460e-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="d460e-172">Vollständig freigegebene globale Adressliste (GAL) zwischen Ihrer lokalen Exchange-Umgebung und Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d460e-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="d460e-173">Synchronisierung von GAL-Informationen aus unterschiedlichen E-Mail-Systemen.</span><span class="sxs-lookup"><span data-stu-id="d460e-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="d460e-174">Die Möglichkeit, Benutzer zu Microsoft 365-Dienst angeboten hinzuzufügen oder daraus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d460e-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="d460e-175">Dies erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d460e-175">This requires the following:</span></span>
  - <span data-ttu-id="d460e-176">Die bidirektionale Synchronisierung muss während der Verzeichnis synchronisierungseinrichtung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="d460e-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="d460e-177">Standardmäßig schreiben Verzeichnissynchronisierungstools Verzeichnisinformationen nur in die Cloud.</span><span class="sxs-lookup"><span data-stu-id="d460e-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="d460e-178">Wenn Sie die bidirektionale Synchronisierung konfigurieren, aktivieren Sie die Write-Back-Funktionalität, sodass eine beschränkte Anzahl von Objektattributen aus der Cloud kopiert und anschließend wieder in Ihre lokale AD DS geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="d460e-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="d460e-179">Write-Back wird auch als Exchange-Hybrid Modus bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d460e-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="d460e-180">Eine lokale Exchange-hybridbereitstellung</span><span class="sxs-lookup"><span data-stu-id="d460e-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="d460e-181">Die Möglichkeit, einige Benutzerpostfächer in Microsoft 365 zu verschieben und dabei andere Benutzerpostfächer lokal aufzubewahren.</span><span class="sxs-lookup"><span data-stu-id="d460e-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="d460e-182">Sichere Absender und blockierte Absender lokal werden nach Microsoft 365 repliziert.</span><span class="sxs-lookup"><span data-stu-id="d460e-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="d460e-183">Grundlegende Delegierung und Funktion zum Senden von E-Mails im Auftrag.</span><span class="sxs-lookup"><span data-stu-id="d460e-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="d460e-184">Sie verfügen über eine integrierte lokale Smartcard oder mehrstufige Authentifizierungslösung.</span><span class="sxs-lookup"><span data-stu-id="d460e-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="d460e-185">Synchronisierung von Fotos, Miniaturansichten, Konferenzräumen und Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="d460e-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="d460e-186">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d460e-186">Next step</span></span>

<span data-ttu-id="d460e-187">Wenn Sie bereit sind, die Hybrid Identität bereitzustellen, lesen Sie [Vorbereiten der Bereitstellung von Benutzern](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="d460e-187">When you are ready to deploy hybrid identity, see [prepare to provision users](prepare-for-directory-synchronization.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d460e-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d460e-188">See also</span></span>

[<span data-ttu-id="d460e-189">Übersicht zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d460e-189">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)

