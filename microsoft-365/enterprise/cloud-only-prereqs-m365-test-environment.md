---
title: Voraussetzungen für Identitäts- und Gerätezugriff für reine Cloudbereitstellung in Ihrer Microsoft 365-Testumgebung
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
description: Erstellen Sie eine Microsoft 365-Umgebung zum Testen des Identitäts- und Gerätezugriffs anhand der Voraussetzungen für die Authentifizierung der reinen Cloudbereitstellung.
ms.openlocfilehash: 1e659304eee330960937b641c9a39b03920f52e7
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233130"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="f4a83-103">Voraussetzungen für Identitäts- und Gerätezugriff für reine Cloudbereitstellung in Ihrer Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="f4a83-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="f4a83-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="f4a83-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="f4a83-105">[Identitäts- und Gerätezugriffskonfigurationen](../security/office-365-security/microsoft-365-policies-configurations.md) sind eine Reihe empfohlener Konfigurationen und Richtlinien für bedingten Zugriff zum Schutz des Zugriffs auf alle Dienste, die in Azure Active Directory (Azure AD) integriert sind.</span><span class="sxs-lookup"><span data-stu-id="f4a83-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="f4a83-106">In diesem Artikel wird beschrieben, wie eine Microsoft 365 Test-Umgebung konfiguriert wird, die die Anforderungen der [erforderlichen Konfiguration für die reine Cloudbereitstellung](../security/office-365-security/identity-access-prerequisites.md#prerequisites) für den Identitäts- und Gerätezugriff erfüllt.</span><span class="sxs-lookup"><span data-stu-id="f4a83-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="f4a83-107">Es gibt acht Hauptphasen bei der Einrichtung dieser Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="f4a83-107">There are eight phases to setting up this test environment:</span></span>

1. <span data-ttu-id="f4a83-108">Erstellen einer einfachen Testumgebung</span><span class="sxs-lookup"><span data-stu-id="f4a83-108">Build out your lightweight test environment</span></span>
2. <span data-ttu-id="f4a83-109">Konfigurieren benannter Orte</span><span class="sxs-lookup"><span data-stu-id="f4a83-109">Configure named locations</span></span>
3. <span data-ttu-id="f4a83-110">Konfigurieren der Self-Service-Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="f4a83-110">Configure self-service password reset</span></span>
4. <span data-ttu-id="f4a83-111">Konfigurieren der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="f4a83-111">Configure multifactor authentication</span></span>
5. <span data-ttu-id="f4a83-112">Aktivieren der automatischen Geräteregistrierung für in die Domäne beigetretene Windows-Computer</span><span class="sxs-lookup"><span data-stu-id="f4a83-112">Enable automatic device registration of domain-joined Windows computers</span></span>
6. <span data-ttu-id="f4a83-113">Konfigurieren des Azure AD-Kennwortschutzes</span><span class="sxs-lookup"><span data-stu-id="f4a83-113">Configure Azure AD password protection</span></span> 
7. <span data-ttu-id="f4a83-114">Aktivieren von Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="f4a83-114">Enable Azure AD Identity Protection</span></span>
8. <span data-ttu-id="f4a83-115">Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f4a83-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="f4a83-116">Phase 1: Erstellen einer einfachen Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="f4a83-116">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="f4a83-117">Befolgen Sie die Anweisungen unter [Einfache Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f4a83-117">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="f4a83-118">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f4a83-118">Here is the resulting configuration.</span></span>

![Einfache Microsoft 365 Enterprise-Testumgebung](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="f4a83-120">Phase 2: Konfigurieren benannter Orte</span><span class="sxs-lookup"><span data-stu-id="f4a83-120">Phase 2: Configure named locations</span></span>

<span data-ttu-id="f4a83-121">Ermitteln Sie zunächst die öffentlichen IP-Adressen oder Adressbereiche, die von Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f4a83-121">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="f4a83-122">Befolgen Sie dann die Anweisungen unter [Konfigurieren benannter Orte in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations), um die Adressen oder Adressbereiche als benannte Orte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f4a83-122">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-self-service-password-reset"></a><span data-ttu-id="f4a83-123">Phase 3: Konfigurieren der Self-Service-Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="f4a83-123">Phase 3: Configure self-service password reset</span></span>

<span data-ttu-id="f4a83-124">Folgen Sie anschließend den Anweisungen unter [Phase 3 der Kennwortzurücksetzung](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) der Testumgebungsanleitungen.</span><span class="sxs-lookup"><span data-stu-id="f4a83-124">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="f4a83-125">Wenn Sie das Zurücksetzen des Kennworts für die Konten in einer bestimmten Azure AD-Gruppe aktivieren, fügen Sie diese Konten der Gruppe **Kennwort zurücksetzen** hinzu:</span><span class="sxs-lookup"><span data-stu-id="f4a83-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="f4a83-126">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="f4a83-126">User 2</span></span>
- <span data-ttu-id="f4a83-127">Benutzer 3</span><span class="sxs-lookup"><span data-stu-id="f4a83-127">User 3</span></span>
- <span data-ttu-id="f4a83-128">Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="f4a83-128">User 4</span></span>
- <span data-ttu-id="f4a83-129">Benutzer 5</span><span class="sxs-lookup"><span data-stu-id="f4a83-129">User 5</span></span>

<span data-ttu-id="f4a83-130">Testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.</span><span class="sxs-lookup"><span data-stu-id="f4a83-130">Test password reset only for the User 2 account.</span></span>

## <a name="phase-4-configure-multi-factor-authentication"></a><span data-ttu-id="f4a83-131">Phase 4: Konfigurieren der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="f4a83-131">Phase 4: Configure multi-factor authentication</span></span>

<span data-ttu-id="f4a83-132">Befolgen Sie die Anweisungen unter [Phase 2 der mehrstufige Authentifizierung](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) der Testumgebungsanleitungen für die folgenden Benutzerkonten:</span><span class="sxs-lookup"><span data-stu-id="f4a83-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="f4a83-133">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="f4a83-133">User 2</span></span>
- <span data-ttu-id="f4a83-134">Benutzer 3</span><span class="sxs-lookup"><span data-stu-id="f4a83-134">User 3</span></span>
- <span data-ttu-id="f4a83-135">Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="f4a83-135">User 4</span></span>
- <span data-ttu-id="f4a83-136">Benutzer 5</span><span class="sxs-lookup"><span data-stu-id="f4a83-136">User 5</span></span>

<span data-ttu-id="f4a83-137">Testen der mehrstufigen Authentifizierung für das Konto „Benutzer 2“.</span><span class="sxs-lookup"><span data-stu-id="f4a83-137">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="f4a83-138">Phase 5: Aktivieren der automatischen Geräteregistrierung für in die Domäne beigetretene Windows-Computer</span><span class="sxs-lookup"><span data-stu-id="f4a83-138">Phase 5: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="f4a83-139">Führen [Sie die folgenden Anweisungen](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) aus, um die automatische Geräteregistrierung für in die Domäne beigetretene Windows-Computer zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f4a83-139">Follow [these instructions](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-6-configure-azure-ad-password-protection"></a><span data-ttu-id="f4a83-140">Phase 6: Konfigurieren des Azure AD-Kennwortschutzes</span><span class="sxs-lookup"><span data-stu-id="f4a83-140">Phase 6: Configure Azure AD password protection</span></span> 

<span data-ttu-id="f4a83-141">Befolgen [Sie diese Anweisungen,](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) um bekannte schwache Kennwörter und deren Varianten zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="f4a83-141">Follow [these instructions](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="f4a83-142">Phase 7: Aktivieren von Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="f4a83-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="f4a83-143">Befolgen Sie die Anweisungen unter [Phase 2 der Testumgebungsanleitungen für Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="f4a83-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="f4a83-144">Phase 8: Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f4a83-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="f4a83-145">Befolgen Sie die [folgenden Anweisungen](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) für Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f4a83-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="f4a83-146">Für Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="f4a83-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="f4a83-147">Stellen Sie eine Verbindung zu [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) her.</span><span class="sxs-lookup"><span data-stu-id="f4a83-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="f4a83-148">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="f4a83-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="f4a83-149">Führen Sie den folgenden Befehl aus, um sich zu vergewissern, dass die Änderung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="f4a83-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="f4a83-150">Das Ergebnis ist eine Testumgebung, die die Anforderungen der nur für die [Cloud](../security/office-365-security/identity-access-prerequisites.md#prerequisites) erforderlichen Konfiguration für den Identitäts- und Gerätezugriff erfüllt.</span><span class="sxs-lookup"><span data-stu-id="f4a83-150">The result is a test environment that meets the requirements of the [cloud-only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="f4a83-151">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f4a83-151">Next step</span></span>

<span data-ttu-id="f4a83-152">Verwenden Sie [Gemeinsame Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md), um die Richtlinien zu konfigurieren, die auf den Voraussetzungen aufbauen und Identitäten und Geräte schützen.</span><span class="sxs-lookup"><span data-stu-id="f4a83-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4a83-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4a83-153">See also</span></span>

[<span data-ttu-id="f4a83-154">Testumgebungsanleitungen für zusätzliche Identitäten</span><span class="sxs-lookup"><span data-stu-id="f4a83-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="f4a83-155">Identitätsplan</span><span class="sxs-lookup"><span data-stu-id="f4a83-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="f4a83-156">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4a83-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f4a83-157">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4a83-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="f4a83-158">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4a83-158">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
