---
title: Hybrididentität und Verzeichnissynchronisierung für Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
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
description: Beschreibt die Verzeichnissynchronisierung mit Microsoft 365, der Active Directory Domain Services-Bereinigung und dem Azure Active Directory Verbinden Tool.
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927544"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="b10f4-103">Hybrididentität und Verzeichnissynchronisierung für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b10f4-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="b10f4-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b10f4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b10f4-105">Je nach Ihren Geschäftsanforderungen und technischen Anforderungen ist das Hybrididentitätsmodell und die Verzeichnissynchronisierung die häufigste Wahl für Unternehmenskunden, die Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b10f4-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="b10f4-106">Mit der Verzeichnissynchronisierung können Sie Identitäten in Ihrem Active Directory Domain Services (AD DS) verwalten, und alle Updates für Benutzerkonten, Gruppen und Kontakte werden mit dem Azure Active Directory(Azure AD)-Mandanten Ihres Microsoft 365-Abonnements synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="b10f4-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="b10f4-107">Wenn AD DS-Benutzerkonten zum ersten Mal synchronisiert werden, erhalten sie nicht automatisch eine Microsoft 365-Lizenz und können nicht auf Microsoft 365 zugreifen, z. B. E-Mails.</span><span class="sxs-lookup"><span data-stu-id="b10f4-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="b10f4-108">Sie müssen ihnen zuerst einen Verwendungsspeicherort zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b10f4-108">You must first assign them a usage location.</span></span> <span data-ttu-id="b10f4-109">Weisen Sie anschließend diesen Benutzerkonten eine Lizenz zu, entweder einzeln oder dynamisch über die Gruppenmitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="b10f4-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="b10f4-110">Authentifizierung für Hybrididentität</span><span class="sxs-lookup"><span data-stu-id="b10f4-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="b10f4-111">Bei Verwendung des Hybrididentitätsmodells gibt es zwei Authentifizierungstypen:</span><span class="sxs-lookup"><span data-stu-id="b10f4-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="b10f4-112">Verwaltete Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="b10f4-112">Managed authentication</span></span>

  <span data-ttu-id="b10f4-113">Azure AD verarbeitet den Authentifizierungsprozess mithilfe einer lokal gespeicherten Hashversion des Kennworts oder sendet die Anmeldeinformationen an einen lokalen Software-Agent, der vom lokalen AD DS authentifiziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b10f4-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="b10f4-114">Verbundauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="b10f4-114">Federated authentication</span></span>

  <span data-ttu-id="b10f4-115">Azure AD leitet den Clientcomputer, der die Authentifizierung anfordert, an einen anderen Identitätsanbieter um.</span><span class="sxs-lookup"><span data-stu-id="b10f4-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="b10f4-116">Verwaltete Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="b10f4-116">Managed authentication</span></span>

<span data-ttu-id="b10f4-117">Es gibt zwei Arten von verwalteter Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="b10f4-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="b10f4-118">Kennworthashsynchronisierung (Password hash synchronization, PHS)</span><span class="sxs-lookup"><span data-stu-id="b10f4-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="b10f4-119">Azure AD führt die Authentifizierung selbst durch.</span><span class="sxs-lookup"><span data-stu-id="b10f4-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="b10f4-120">Passthrough-Authentifizierung (PTA)</span><span class="sxs-lookup"><span data-stu-id="b10f4-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="b10f4-121">Azure AD lässt AD DS die Authentifizierung durchführen.</span><span class="sxs-lookup"><span data-stu-id="b10f4-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="b10f4-122">Kennworthashsynchronisierung (Password hash synchronization, PHS)</span><span class="sxs-lookup"><span data-stu-id="b10f4-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="b10f4-123">Mit PHS synchronisieren Sie Ihre AD DS-Benutzerkonten mit Microsoft 365 und verwalten Ihre Benutzer lokal.</span><span class="sxs-lookup"><span data-stu-id="b10f4-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="b10f4-124">Hashes von Benutzerkennwörtern werden von Ad DS mit Azure AD synchronisiert, sodass die Benutzer lokal und in der Cloud dasselbe Kennwort haben.</span><span class="sxs-lookup"><span data-stu-id="b10f4-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="b10f4-125">Dies ist die einfachste Möglichkeit, die Authentifizierung für AD DS-Identitäten in Azure AD zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b10f4-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![Kennworthashsynchronisierung (Password hash synchronization, PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="b10f4-127">Wenn Kennwörter lokal geändert oder zurückgesetzt werden, werden die neuen Kennworthashes mit Azure AD synchronisiert, sodass Ihre Benutzer immer dasselbe Kennwort für Cloudressourcen und lokale Ressourcen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b10f4-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="b10f4-128">Die Benutzerkennwörter werden niemals an Azure AD gesendet oder in Azure AD im Klartext gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b10f4-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="b10f4-129">Einige Premiumfeatures von Azure AD, z. B. Identity Protection, erfordern PHS, unabhängig davon, welche Authentifizierungsmethode ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="b10f4-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="b10f4-130">Weitere Informationen finden Sie unter Auswählen [der richtigen Authentifizierungsmethode.](/azure/active-directory/hybrid/choose-ad-authn)</span><span class="sxs-lookup"><span data-stu-id="b10f4-130">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="b10f4-131">Passthrough-Authentifizierung (PTA)</span><span class="sxs-lookup"><span data-stu-id="b10f4-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="b10f4-132">PTA bietet eine einfache Kennwortüberprüfung für Azure AD-Authentifizierungsdienste mithilfe eines Software-Agents, der auf einem oder mehreren lokalen Servern ausgeführt wird, um die Benutzer direkt mit Ihrem AD DS zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b10f4-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="b10f4-133">Mit PTA synchronisieren Sie AD DS-Benutzerkonten mit Microsoft 365 und verwalten Ihre Benutzer lokal.</span><span class="sxs-lookup"><span data-stu-id="b10f4-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![Passthrough-Authentifizierung (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="b10f4-135">PTA ermöglicht Es Ihren Benutzern, sich sowohl bei lokalen als auch Microsoft 365 Ressourcen und Anwendungen mit ihrem lokalen Konto und Kennwort zu anmelden.</span><span class="sxs-lookup"><span data-stu-id="b10f4-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="b10f4-136">Diese Konfiguration überprüft Benutzerkennwörter direkt mit Ihrem lokalen AD DS, ohne Kennworthashes in Azure AD zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b10f4-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="b10f4-137">PTA ist auch für Organisationen mit einer Sicherheitsanforderung zum sofortigen Erzwingen von lokalen Benutzerkontozuständen, Kennwortrichtlinien und Anmeldezeiten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b10f4-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="b10f4-138">Weitere Informationen finden Sie unter Auswählen [der richtigen Authentifizierungsmethode.](/azure/active-directory/hybrid/choose-ad-authn)</span><span class="sxs-lookup"><span data-stu-id="b10f4-138">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="b10f4-139">Verbundauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="b10f4-139">Federated authentication</span></span>

<span data-ttu-id="b10f4-140">Die Verbundauthentifizierung ist in erster Linie für große Unternehmensorganisationen mit komplexeren Authentifizierungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="b10f4-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="b10f4-141">AD DS-Identitäten werden mit Microsoft 365 synchronisiert, und Benutzerkonten werden lokal verwaltet.</span><span class="sxs-lookup"><span data-stu-id="b10f4-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="b10f4-142">Bei der Verbundauthentifizierung verfügen Benutzer lokal und in der Cloud über dasselbe Kennwort, und sie müssen sich nicht erneut anmelden, um Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b10f4-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="b10f4-143">Die Verbundauthentifizierung kann zusätzliche Authentifizierungsanforderungen unterstützen, z. B. die smartcardbasierte Authentifizierung oder eine mehrstufige Authentifizierung eines Drittanbieters und ist in der Regel erforderlich, wenn Organisationen eine Authentifizierungsanforderung haben, die nicht systemeigene Unterstützung von Azure AD hat.</span><span class="sxs-lookup"><span data-stu-id="b10f4-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="b10f4-144">Weitere Informationen finden Sie unter Auswählen [der richtigen Authentifizierungsmethode.](/azure/active-directory/hybrid/choose-ad-authn)</span><span class="sxs-lookup"><span data-stu-id="b10f4-144">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="b10f4-145">Authentifizierungs- und Identitätsanbieter von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="b10f4-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="b10f4-146">Lokale Verzeichnisobjekte können mit Microsoft 365 synchronisiert werden, und der Zugriff auf Cloudressourcen wird hauptsächlich von einem Identitätsanbieter eines Drittanbieters (IdP) verwaltet.</span><span class="sxs-lookup"><span data-stu-id="b10f4-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="b10f4-147">Wenn Ihre Organisation eine Verbundlösung eines Drittanbieters verwendet, können Sie die Anmeldung mit dieser Lösung für Microsoft 365 konfigurieren, sofern die Verbundlösung eines Drittanbieters mit Azure AD kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="b10f4-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="b10f4-148">Weitere Informationen finden Sie in der [Kompatibilitätsliste des Azure](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) AD-Verbunds.</span><span class="sxs-lookup"><span data-stu-id="b10f4-148">See the [Azure AD federation compatibility list](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="b10f4-149">AD DS-Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="b10f4-149">AD DS Preparation</span></span>

<span data-ttu-id="b10f4-150">Um einen nahtlosen Übergang zu Microsoft 365 mithilfe der Synchronisierung sicherzustellen, müssen Sie Ihre AD DS-Gesamtstruktur vorbereiten, bevor Sie mit der Microsoft 365 der Verzeichnissynchronisierung beginnen.</span><span class="sxs-lookup"><span data-stu-id="b10f4-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="b10f4-151">Die Verzeichnisvorbereitung sollte sich auf die folgenden Aufgaben konzentrieren:</span><span class="sxs-lookup"><span data-stu-id="b10f4-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="b10f4-152">Entfernen Sie doppelte **proxyAddress-** und **userPrincipalName-Attribute.**</span><span class="sxs-lookup"><span data-stu-id="b10f4-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="b10f4-153">Aktualisieren Sie leere und ungültige **userPrincipalName-Attribute** mit **gültigen userPrincipalName-Attributen.**</span><span class="sxs-lookup"><span data-stu-id="b10f4-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="b10f4-154">Entfernen Sie ungültige und fragwürdige Zeichen in den Attributen **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname** und **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="b10f4-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="b10f4-155">Weitere Informationen zum Vorbereiten von Attributen finden Sie unter Liste der Attribute, die vom Azure Active Directory [synchronisiert werden.](https://go.microsoft.com/fwlink/p/?LinkId=396719)</span><span class="sxs-lookup"><span data-stu-id="b10f4-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="b10f4-156">Dies sind die gleichen Attribute, die Azure AD Verbinden synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="b10f4-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="b10f4-157">Überlegungen zur Bereitstellung mit mehreren Gesamtstrukturen</span><span class="sxs-lookup"><span data-stu-id="b10f4-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="b10f4-158">Verwenden Sie für mehrere Gesamtstrukturen und SSO-Optionen eine benutzerdefinierte [Installation von Azure AD Verbinden](/azure/active-directory/hybrid/how-to-connect-install-custom).</span><span class="sxs-lookup"><span data-stu-id="b10f4-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>
  
<span data-ttu-id="b10f4-159">Wenn Ihre Organisation über mehrere Gesamtstrukturen für die Authentifizierung (Anmelde gesamtstrukturen) verfügt, wird Folgendes dringend empfohlen:</span><span class="sxs-lookup"><span data-stu-id="b10f4-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="b10f4-160">**Erwägen Sie, Ihre Gesamtstrukturen zu konsolidieren.**</span><span class="sxs-lookup"><span data-stu-id="b10f4-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="b10f4-161">Im Allgemeinen ist mehr Aufwand für die Verwaltung mehrerer Gesamtstrukturen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b10f4-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="b10f4-162">Es sei denn, Ihre Organisation verfügt über Sicherheitseinschränkungen, die die Notwendigkeit separater Gesamtstrukturen erfordern, sollten Sie ihre lokale Umgebung vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="b10f4-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="b10f4-163">**Nur in der primären Anmelde gesamtstruktur verwenden.**</span><span class="sxs-lookup"><span data-stu-id="b10f4-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="b10f4-164">Erwägen Sie, Microsoft 365 nur in Ihrer primären Anmelde gesamtstruktur für den ersten Rollout von Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b10f4-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="b10f4-165">Wenn Sie Ihre AD DS-Bereitstellung mit mehreren Gesamtstrukturen nicht konsolidieren können oder andere Verzeichnisdienste zum Verwalten von Identitäten verwenden, können Sie diese möglicherweise mithilfe von Microsoft oder einem Partner synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="b10f4-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="b10f4-166">Weitere Informationen finden Sie unter [Topologies for Azure AD Verbinden.](/azure/active-directory/hybrid/plan-connect-topologies)</span><span class="sxs-lookup"><span data-stu-id="b10f4-166">See [Topologies for Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="b10f4-167">Features, die von der Verzeichnissynchronisierung abhängig sind</span><span class="sxs-lookup"><span data-stu-id="b10f4-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="b10f4-168">Die Verzeichnissynchronisierung ist für die folgenden Features und Funktionen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="b10f4-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="b10f4-169">Azure AD Seamless Single Sign-On (SSO)</span><span class="sxs-lookup"><span data-stu-id="b10f4-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="b10f4-170">Skype Koexistenz</span><span class="sxs-lookup"><span data-stu-id="b10f4-170">Skype coexistence</span></span>
- <span data-ttu-id="b10f4-171">Exchange Hybridbereitstellung, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="b10f4-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="b10f4-172">Vollständig freigegebene globale Adressliste (GAL) zwischen Ihrer lokalen Exchange und Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b10f4-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="b10f4-173">Synchronisierung von GAL-Informationen aus unterschiedlichen E-Mail-Systemen.</span><span class="sxs-lookup"><span data-stu-id="b10f4-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="b10f4-174">Die Möglichkeit, Benutzer zu hinzufügen und Benutzer aus Microsoft 365 zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b10f4-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="b10f4-175">Dies erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b10f4-175">This requires the following:</span></span>
  - <span data-ttu-id="b10f4-176">Die Zwei-Wege-Synchronisierung muss während des Setups der Verzeichnissynchronisierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b10f4-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="b10f4-177">Standardmäßig schreiben Verzeichnissynchronisierungstools Verzeichnisinformationen nur in die Cloud.</span><span class="sxs-lookup"><span data-stu-id="b10f4-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="b10f4-178">Wenn Sie die zweiwegs-Synchronisierung konfigurieren, aktivieren Sie die Rückschreibenfunktion, sodass eine begrenzte Anzahl von Objektattributen aus der Cloud kopiert und dann wieder in Ihren lokalen AD DS geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="b10f4-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="b10f4-179">Das Rückschreiben wird auch als Exchange bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b10f4-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="b10f4-180">Eine lokale Exchange Hybridbereitstellung</span><span class="sxs-lookup"><span data-stu-id="b10f4-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="b10f4-181">Die Möglichkeit, einige Benutzerpostfächer in Microsoft 365 zu verschieben, während andere Benutzerpostfächer lokal bleiben.</span><span class="sxs-lookup"><span data-stu-id="b10f4-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="b10f4-182">Sichere absender und blockierte Absender werden lokal auf Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b10f4-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="b10f4-183">Grundlegende Delegierung und Funktion zum Senden von E-Mails im Auftrag.</span><span class="sxs-lookup"><span data-stu-id="b10f4-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="b10f4-184">Sie verfügen über eine integrierte lokale Smartcard oder mehrstufige Authentifizierungslösung.</span><span class="sxs-lookup"><span data-stu-id="b10f4-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="b10f4-185">Synchronisierung von Fotos, Miniaturansichten, Konferenzräumen und Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="b10f4-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="b10f4-186">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b10f4-186">Next step</span></span>

<span data-ttu-id="b10f4-187">Wenn Sie zur Bereitstellung von Hybrididentität bereit sind, lesen [Sie Vorbereiten der Verzeichnissynchronisierung](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="b10f4-187">When you are ready to deploy hybrid identity, see [prepare for directory synchronization](prepare-for-directory-synchronization.md).</span></span>
