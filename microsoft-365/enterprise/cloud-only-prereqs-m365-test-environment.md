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
ms.openlocfilehash: 927aa032e4181206b3a744da7076b696ac5cf4d4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199549"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="ac3d6-103">Voraussetzungen für Identitäts- und Gerätezugriff für reine Cloudbereitstellung in Ihrer Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="ac3d6-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="ac3d6-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="ac3d6-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="ac3d6-105">[Identitäts- und Gerätezugriffskonfigurationen](../security/office-365-security/microsoft-365-policies-configurations.md) sind eine Reihe empfohlener Konfigurationen und Richtlinien für bedingten Zugriff, um den Zugriff auf alle Dienste zu schützen, die in Azure Active Directory (Azure AD) integriert sind.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="ac3d6-106">In diesem Artikel wird beschrieben, wie eine Microsoft 365 Test-Umgebung konfiguriert wird, die die Anforderungen der [erforderlichen Konfiguration für die reine Cloudbereitstellung](../security/office-365-security/identity-access-prerequisites.md#prerequisites) für den Identitäts- und Gerätezugriff erfüllt.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="ac3d6-107">Es gibt acht Hauptphasen bei der Einrichtung dieser Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="ac3d6-107">There are eight phases to setting up this test environment:</span></span>

1. <span data-ttu-id="ac3d6-108">Erstellen einer einfachen Testumgebung</span><span class="sxs-lookup"><span data-stu-id="ac3d6-108">Build out your lightweight test environment</span></span>
2. <span data-ttu-id="ac3d6-109">Konfigurieren benannter Orte</span><span class="sxs-lookup"><span data-stu-id="ac3d6-109">Configure named locations</span></span>
3. <span data-ttu-id="ac3d6-110">Konfigurieren der Self-Service-Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="ac3d6-110">Configure self-service password reset</span></span>
4. <span data-ttu-id="ac3d6-111">Konfigurieren der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ac3d6-111">Configure multifactor authentication</span></span>
5. <span data-ttu-id="ac3d6-112">Aktivieren der automatischen Geräteregistrierung von In die Domäne Windows Computern</span><span class="sxs-lookup"><span data-stu-id="ac3d6-112">Enable automatic device registration of domain-joined Windows computers</span></span>
6. <span data-ttu-id="ac3d6-113">Konfigurieren des Azure AD-Kennwortschutzes</span><span class="sxs-lookup"><span data-stu-id="ac3d6-113">Configure Azure AD password protection</span></span> 
7. <span data-ttu-id="ac3d6-114">Aktivieren von Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="ac3d6-114">Enable Azure AD Identity Protection</span></span>
8. <span data-ttu-id="ac3d6-115">Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ac3d6-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="ac3d6-116">Phase 1: Erstellen einer einfachen Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="ac3d6-116">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="ac3d6-117">Befolgen Sie die Anweisungen unter [Einfache Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ac3d6-117">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="ac3d6-118">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-118">Here is the resulting configuration.</span></span>

![Einfache Microsoft 365 Enterprise-Testumgebung](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="ac3d6-120">Phase 2: Konfigurieren benannter Orte</span><span class="sxs-lookup"><span data-stu-id="ac3d6-120">Phase 2: Configure named locations</span></span>

<span data-ttu-id="ac3d6-121">Ermitteln Sie zunächst die öffentlichen IP-Adressen oder Adressbereiche, die von Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-121">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="ac3d6-122">Befolgen Sie dann die Anweisungen unter [Konfigurieren benannter Orte in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations), um die Adressen oder Adressbereiche als benannte Orte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-122">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-self-service-password-reset"></a><span data-ttu-id="ac3d6-123">Phase 3: Konfigurieren der Self-Service-Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="ac3d6-123">Phase 3: Configure self-service password reset</span></span>

<span data-ttu-id="ac3d6-124">Folgen Sie anschließend den Anweisungen unter [Phase 3 der Kennwortzurücksetzung](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) der Testumgebungsanleitungen.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-124">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="ac3d6-125">Wenn Sie das Zurücksetzen des Kennworts für die Konten in einer bestimmten Azure AD-Gruppe aktivieren, fügen Sie diese Konten der Gruppe **Kennwort zurücksetzen** hinzu:</span><span class="sxs-lookup"><span data-stu-id="ac3d6-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="ac3d6-126">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="ac3d6-126">User 2</span></span>
- <span data-ttu-id="ac3d6-127">Benutzer 3</span><span class="sxs-lookup"><span data-stu-id="ac3d6-127">User 3</span></span>
- <span data-ttu-id="ac3d6-128">Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="ac3d6-128">User 4</span></span>
- <span data-ttu-id="ac3d6-129">Benutzer 5</span><span class="sxs-lookup"><span data-stu-id="ac3d6-129">User 5</span></span>

<span data-ttu-id="ac3d6-130">Testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-130">Test password reset only for the User 2 account.</span></span>

## <a name="phase-4-configure-multi-factor-authentication"></a><span data-ttu-id="ac3d6-131">Phase 4: Konfigurieren der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ac3d6-131">Phase 4: Configure multi-factor authentication</span></span>

<span data-ttu-id="ac3d6-132">Befolgen Sie die Anweisungen unter [Phase 2 der mehrstufige Authentifizierung](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) der Testumgebungsanleitungen für die folgenden Benutzerkonten:</span><span class="sxs-lookup"><span data-stu-id="ac3d6-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="ac3d6-133">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="ac3d6-133">User 2</span></span>
- <span data-ttu-id="ac3d6-134">Benutzer 3</span><span class="sxs-lookup"><span data-stu-id="ac3d6-134">User 3</span></span>
- <span data-ttu-id="ac3d6-135">Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="ac3d6-135">User 4</span></span>
- <span data-ttu-id="ac3d6-136">Benutzer 5</span><span class="sxs-lookup"><span data-stu-id="ac3d6-136">User 5</span></span>

<span data-ttu-id="ac3d6-137">Testen der mehrstufigen Authentifizierung für das Konto „Benutzer 2“.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-137">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="ac3d6-138">Phase 5: Aktivieren der automatischen Geräteregistrierung von In die Domäne Windows Computern</span><span class="sxs-lookup"><span data-stu-id="ac3d6-138">Phase 5: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="ac3d6-139">Befolgen [Sie diese Anweisungen,](/azure/active-directory/devices/hybrid-azuread-join-plan) um die automatische Geräteregistrierung von Domänencomputern zu Windows aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-139">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-6-configure-azure-ad-password-protection"></a><span data-ttu-id="ac3d6-140">Phase 6: Konfigurieren des Azure AD-Kennwortschutzes</span><span class="sxs-lookup"><span data-stu-id="ac3d6-140">Phase 6: Configure Azure AD password protection</span></span> 

<span data-ttu-id="ac3d6-141">Befolgen [Sie diese Anweisungen,](/azure/active-directory/authentication/concept-password-ban-bad) um bekannte schwache Kennwörter und deren Varianten zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-141">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="ac3d6-142">Phase 7: Aktivieren von Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="ac3d6-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="ac3d6-143">Befolgen Sie die Anweisungen unter [Phase 2 der Testumgebungsanleitungen für Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="ac3d6-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="ac3d6-144">Phase 8: Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ac3d6-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="ac3d6-145">Befolgen Sie die [folgenden Anweisungen](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) für Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-145">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="ac3d6-146">Für Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="ac3d6-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="ac3d6-147">Stellen Sie eine Verbindung zu [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) her.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-147">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="ac3d6-148">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="ac3d6-149">Führen Sie den folgenden Befehl aus, um sich zu vergewissern, dass die Änderung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="ac3d6-150">Das Ergebnis ist eine Testumgebung, [](../security/office-365-security/identity-access-prerequisites.md#prerequisites) die die Anforderungen der nur in der Cloud erforderlichen Konfiguration für den Identitäts- und Gerätezugriff erfüllt.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-150">The result is a test environment that meets the requirements of the [cloud-only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="ac3d6-151">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="ac3d6-151">Next step</span></span>

<span data-ttu-id="ac3d6-152">Verwenden Sie [Gemeinsame Identitäts- und Gerätezugriffsrichtlinien](../security/office-365-security/identity-access-policies.md), um die Richtlinien zu konfigurieren, die auf den Voraussetzungen aufbauen und Identitäten und Geräte schützen.</span><span class="sxs-lookup"><span data-stu-id="ac3d6-152">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac3d6-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac3d6-153">See also</span></span>

[<span data-ttu-id="ac3d6-154">Testumgebungsanleitungen für zusätzliche Identitäten</span><span class="sxs-lookup"><span data-stu-id="ac3d6-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="ac3d6-155">Identitätsplan</span><span class="sxs-lookup"><span data-stu-id="ac3d6-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="ac3d6-156">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ac3d6-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ac3d6-157">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ac3d6-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ac3d6-158">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ac3d6-158">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
