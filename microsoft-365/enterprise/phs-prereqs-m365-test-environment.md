---
title: Identitäts- und Gerätezugriffsvoraussetzungen für die Kennworthashsynchronisierung in Ihrer Microsoft 365-Umgebung
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erstellen Sie eine Microsoft 365-Umgebung zum Testen des Identitäts- und Gerätezugriffs anhand der Voraussetzungen für die Authentifizierung der Kennworthashsynchronisierung.
ms.openlocfilehash: 8e8db4aae39acda0762f9b6394b23ab047727ea5
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233784"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="100d7-103">Identitäts- und Gerätezugriffsvoraussetzungen für die Kennworthashsynchronisierung in Ihrer Microsoft 365-Umgebung</span><span class="sxs-lookup"><span data-stu-id="100d7-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="100d7-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="100d7-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="100d7-105">[Identitäts-](../security/office-365-security/microsoft-365-policies-configurations.md) und Gerätezugriffskonfigurationen sind eine Reihe von Konfigurationen und Richtlinien für bedingten Zugriff zum Schutz des Zugriffs auf alle Dienste in Microsoft 365 Enterprise, die in Azure Active Directory (Azure AD) integriert sind.</span><span class="sxs-lookup"><span data-stu-id="100d7-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="100d7-106">In diesem Artikel wird beschrieben, wie Sie eine Microsoft 365-Testumgebung konfigurieren, die die Anforderungen der Hybridbereitstellung mit Kennworthashsynchronisierungs-Authentifizierungsvoraussetzungen [für](../security/office-365-security/identity-access-prerequisites.md#prerequisites) den Identitäts- und Gerätezugriff erfüllt.</span><span class="sxs-lookup"><span data-stu-id="100d7-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [hybrid with password hash sync authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="100d7-107">Es gibt zehn Phasen zum Einrichten dieser Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="100d7-107">There are ten phases to setting up this test environment:</span></span>

1. <span data-ttu-id="100d7-108">Erstellen eines simulierten Unternehmens mit Kennworthashsynchronisierung für die Testumgebung</span><span class="sxs-lookup"><span data-stu-id="100d7-108">Create a simulated enterprise with password hash sync test environment</span></span>
2. <span data-ttu-id="100d7-109">Konfigurieren des nahtlosen einmaligen Anmeldens in Azure AD</span><span class="sxs-lookup"><span data-stu-id="100d7-109">Configure Azure AD seamless single sign-on</span></span>
3. <span data-ttu-id="100d7-110">Konfigurieren benannter Orte</span><span class="sxs-lookup"><span data-stu-id="100d7-110">Configure named locations</span></span>
4. <span data-ttu-id="100d7-111">Konfigurieren von Kennwortrückschreiben</span><span class="sxs-lookup"><span data-stu-id="100d7-111">Configure password writeback</span></span>
5. <span data-ttu-id="100d7-112">Konfigurieren der Self-Service-Kennwortzurücksetzung für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="100d7-112">Configure self-service password reset for all user accounts</span></span>
6. <span data-ttu-id="100d7-113">Konfigurieren der mehrstufigen Authentifizierung für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="100d7-113">Configure multifactor authentication for all user accounts</span></span>
7. <span data-ttu-id="100d7-114">Aktivieren der automatischen Geräteregistrierung für in die Domäne beigetretene Windows-Computer</span><span class="sxs-lookup"><span data-stu-id="100d7-114">Enable automatic device registration of domain-joined Windows computers</span></span>
8. <span data-ttu-id="100d7-115">Konfigurieren des Azure AD-Kennwortschutzes</span><span class="sxs-lookup"><span data-stu-id="100d7-115">Configure Azure AD password protection</span></span> 
9. <span data-ttu-id="100d7-116">Aktivieren von Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="100d7-116">Enable Azure AD Identity Protection</span></span>
10. <span data-ttu-id="100d7-117">Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="100d7-117">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="100d7-118">Phase 1: Erstellen eines simulierten Unternehmens mit Kennworthashsynchronisierung für die Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="100d7-118">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="100d7-119">Befolgen Sie die Anweisungen in der Testumgebungsanleitung [zur Kennworthashsynchronisierung.](password-hash-sync-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="100d7-119">Follow the instructions in [the password hash synchronization](password-hash-sync-m365-ent-test-environment.md) Test Lab Guide.</span></span>
<span data-ttu-id="100d7-120">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="100d7-120">Here is the resulting configuration.</span></span>

![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="100d7-122">Phase 2: Konfigurieren des nahtlosen einmaligen Anmeldens in Azure AD</span><span class="sxs-lookup"><span data-stu-id="100d7-122">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="100d7-123">Befolgen Sie die Anweisungen unter [Phase 2: Konfigurieren des nahtlosen einmaligen Anmeldens in Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) der Testumgebungsanleitungen.</span><span class="sxs-lookup"><span data-stu-id="100d7-123">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="100d7-124">Phase 3: Konfigurieren benannter Orte</span><span class="sxs-lookup"><span data-stu-id="100d7-124">Phase 3: Configure named locations</span></span>

<span data-ttu-id="100d7-125">Ermitteln Sie zunächst die öffentlichen IP-Adressen oder Adressbereiche, die von Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="100d7-125">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="100d7-126">Befolgen Sie dann die Anweisungen unter [Konfigurieren benannter Orte in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations), um die Adressen oder Adressbereiche als benannte Orte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="100d7-126">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="100d7-127">Phase 4: Konfigurieren von Kennwortrückschreiben</span><span class="sxs-lookup"><span data-stu-id="100d7-127">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="100d7-128">Folgen Sie anschließend den Anweisungen unter [Phase 2 der Kennwortrückschreibung](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) der Testumgebungsanleitungen.</span><span class="sxs-lookup"><span data-stu-id="100d7-128">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="100d7-129">Phase 5: Konfigurieren der Self-Service-Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="100d7-129">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="100d7-130">Folgen Sie anschließend den Anweisungen unter [Phase 3 der Kennwortzurücksetzung](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) der Testumgebungsanleitungen.</span><span class="sxs-lookup"><span data-stu-id="100d7-130">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="100d7-131">Wenn Sie das Zurücksetzen des Kennworts für die Konten in einer bestimmten Azure AD-Gruppe aktivieren, fügen Sie diese Konten der Gruppe **Kennwort zurücksetzen** hinzu:</span><span class="sxs-lookup"><span data-stu-id="100d7-131">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="100d7-132">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="100d7-132">User 2</span></span>
- <span data-ttu-id="100d7-133">Benutzer 3</span><span class="sxs-lookup"><span data-stu-id="100d7-133">User 3</span></span>
- <span data-ttu-id="100d7-134">Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="100d7-134">User 4</span></span>
- <span data-ttu-id="100d7-135">Benutzer 5</span><span class="sxs-lookup"><span data-stu-id="100d7-135">User 5</span></span>

<span data-ttu-id="100d7-136">Testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.</span><span class="sxs-lookup"><span data-stu-id="100d7-136">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="100d7-137">Phase 6: Konfigurieren der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="100d7-137">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="100d7-138">Befolgen Sie die Anweisungen unter [Phase 2 der mehrstufige Authentifizierung](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) der Testumgebungsanleitungen für die folgenden Benutzerkonten:</span><span class="sxs-lookup"><span data-stu-id="100d7-138">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="100d7-139">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="100d7-139">User 2</span></span>
- <span data-ttu-id="100d7-140">Benutzer 3</span><span class="sxs-lookup"><span data-stu-id="100d7-140">User 3</span></span>
- <span data-ttu-id="100d7-141">Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="100d7-141">User 4</span></span>
- <span data-ttu-id="100d7-142">Benutzer 5</span><span class="sxs-lookup"><span data-stu-id="100d7-142">User 5</span></span>

<span data-ttu-id="100d7-143">Testen der mehrstufigen Authentifizierung für das Konto „Benutzer 2“.</span><span class="sxs-lookup"><span data-stu-id="100d7-143">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="100d7-144">Phase 7: Aktivieren der automatischen Geräteregistrierung für in die Domäne beigetretene Windows-Computer</span><span class="sxs-lookup"><span data-stu-id="100d7-144">Phase 7: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="100d7-145">Führen [Sie die folgenden Anweisungen](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) aus, um die automatische Geräteregistrierung für in die Domäne beigetretene Windows-Computer zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="100d7-145">Follow [these instructions](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-8-configure-azure-ad-password-protection"></a><span data-ttu-id="100d7-146">Phase 8: Konfigurieren des Azure AD-Kennwortschutzes</span><span class="sxs-lookup"><span data-stu-id="100d7-146">Phase 8: Configure Azure AD password protection</span></span> 

<span data-ttu-id="100d7-147">Befolgen [Sie diese Anweisungen,](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) um bekannte schwache Kennwörter und deren Varianten zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="100d7-147">Follow [these instructions](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-9-enable-azure-ad-identity-protection"></a><span data-ttu-id="100d7-148">Phase 9: Aktivieren von Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="100d7-148">Phase 9: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="100d7-149">Befolgen Sie die Anweisungen unter [Phase 2 der Testumgebungsanleitungen für Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="100d7-149">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="100d7-150">Phase 10: Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="100d7-150">Phase 10: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="100d7-151">Befolgen Sie die [folgenden Anweisungen](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) für Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="100d7-151">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="100d7-152">Für Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="100d7-152">For Skype for Business Online:</span></span>

1. <span data-ttu-id="100d7-153">Stellen Sie eine Verbindung zu [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) her.</span><span class="sxs-lookup"><span data-stu-id="100d7-153">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="100d7-154">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="100d7-154">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="100d7-155">Führen Sie den folgenden Befehl aus, um sich zu vergewissern, dass die Änderung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="100d7-155">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="100d7-156">Das Ergebnis ist eine Test-Umgebung, die die Anforderungen von [Active Directory mit der erforderlichen Konfiguration für die Kennworthashsynchronisierung ](../security/office-365-security/identity-access-prerequisites.md#prerequisites) für den Identitäts- und Gerätezugriff erfüllt.</span><span class="sxs-lookup"><span data-stu-id="100d7-156">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="100d7-157">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="100d7-157">Next step</span></span>

<span data-ttu-id="100d7-158">Verwenden Sie [Gemeinsame Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md), um die Richtlinien zu konfigurieren, die auf den Voraussetzungen aufbauen und Identitäten und Geräte schützen.</span><span class="sxs-lookup"><span data-stu-id="100d7-158">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="100d7-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="100d7-159">See also</span></span>

[<span data-ttu-id="100d7-160">Testumgebungsanleitungen für zusätzliche Identitäten</span><span class="sxs-lookup"><span data-stu-id="100d7-160">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="100d7-161">Identitätsplan</span><span class="sxs-lookup"><span data-stu-id="100d7-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="100d7-162">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="100d7-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="100d7-163">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="100d7-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="100d7-164">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="100d7-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
